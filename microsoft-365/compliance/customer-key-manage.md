---
title: Gestire il codice Cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Dopo aver configurato Customer Key, scopri come gestirlo ripristinando le chiavi AKV e gestendo le autorizzazioni e creando e assegnando criteri di crittografia dei dati.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345059"
---
# <a name="manage-customer-key"></a><span data-ttu-id="3fa70-103">Gestire il codice Cliente</span><span class="sxs-lookup"><span data-stu-id="3fa70-103">Manage Customer Key</span></span>

<span data-ttu-id="3fa70-104">Dopo aver configurato customer key per Office 365, è necessario creare e assegnare uno o più criteri di crittografia dei dati(DEP).</span><span class="sxs-lookup"><span data-stu-id="3fa70-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="3fa70-105">Dopo aver assegnato i CRITERI di gruppo, è possibile gestire le chiavi come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="3fa70-106">Per ulteriori informazioni, vedere Customer Key negli argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="3fa70-107">Creare una protezione esecuzione programmi da utilizzare con più carichi di lavoro per tutti gli utenti tenant</span><span class="sxs-lookup"><span data-stu-id="3fa70-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="3fa70-108">Prima di iniziare, assicurati di aver completato le attività necessarie per configurare Customer.</span><span class="sxs-lookup"><span data-stu-id="3fa70-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="3fa70-109">Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3fa70-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3fa70-110">Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3fa70-111">Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3fa70-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3fa70-112">Per creare una protezione esecuzione programmi con più carichi di lavoro, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="3fa70-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="3fa70-113">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3fa70-114">Per creare una protezione esecuzione programmi, utilizzare il cmdlet New-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="3fa70-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="3fa70-115">Dove:</span><span class="sxs-lookup"><span data-stu-id="3fa70-115">Where:</span></span>

   - <span data-ttu-id="3fa70-116">*PolicyName* è il nome che si desidera utilizzare per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3fa70-117">I nomi non possono contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-117">Names can't contain spaces.</span></span> <span data-ttu-id="3fa70-118">Ad esempio, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3fa70-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="3fa70-119">*KeyVaultURI1* è l'URI per la prima chiave nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3fa70-120">Ad esempio, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="3fa70-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="3fa70-121">*KeyVaultURI2* è l'URI per la seconda chiave nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3fa70-122">Ad esempio, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="3fa70-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="3fa70-123">Separare i due URI con una virgola e uno spazio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="3fa70-124">*Descrizione* criterio è una descrizione facile da usare del criterio che consente di ricordare a cosa si sta a fare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3fa70-125">È possibile includere spazi nella descrizione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-125">You can include spaces in the description.</span></span> <span data-ttu-id="3fa70-126">Ad esempio, "Criteri radice per più carichi di lavoro per tutti gli utenti nel tenant.".</span><span class="sxs-lookup"><span data-stu-id="3fa70-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="3fa70-127">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="3fa70-128">Assegnare criteri multi-carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="3fa70-128">Assign multi-workload policy</span></span>

<span data-ttu-id="3fa70-129">Assegnare Protezione esecuzione programmi utilizzando il cmdlet Set-M365DataAtRestEncryptionPolicyAssignment.</span><span class="sxs-lookup"><span data-stu-id="3fa70-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="3fa70-130">Dopo aver assegnato il criterio, Microsoft 365 i dati con la chiave identificata nella protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="3fa70-131">Dove *PolicyName* è il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="3fa70-132">Ad esempio, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3fa70-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="3fa70-133">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="3fa70-134">Creare una protezione esecuzione programmi da utilizzare con Exchange Online cassette postali</span><span class="sxs-lookup"><span data-stu-id="3fa70-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="3fa70-135">Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3fa70-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3fa70-136">Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3fa70-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3fa70-137">Questi passaggi verranno completati connettendosi in remoto a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="3fa70-138">Una protezione esecuzione programmi è associata a un set di chiavi archiviate in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3fa70-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3fa70-139">Si assegna una protezione esecuzione programmi a una cassetta postale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fa70-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="3fa70-140">Microsoft 365 verranno quindi utilizzate le chiavi identificate nel criterio per crittografare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="3fa70-141">Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3fa70-142">Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3fa70-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3fa70-143">Ricordati!</span><span class="sxs-lookup"><span data-stu-id="3fa70-143">Remember!</span></span> <span data-ttu-id="3fa70-144">Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi insiemi di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="3fa70-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3fa70-145">Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="3fa70-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="3fa70-146">Per creare una protezione esecuzione programmi da utilizzare con una cassetta postale, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="3fa70-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="3fa70-147">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di Exchange Online nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3fa70-148">Per creare una protezione esecuzione programmi, utilizzare New-DataEncryptionPolicy cmdlet digitando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3fa70-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="3fa70-149">Dove:</span><span class="sxs-lookup"><span data-stu-id="3fa70-149">Where:</span></span>

   - <span data-ttu-id="3fa70-150">*PolicyName* è il nome che si desidera utilizzare per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3fa70-151">I nomi non possono contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-151">Names can't contain spaces.</span></span> <span data-ttu-id="3fa70-152">Ad esempio, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="3fa70-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="3fa70-153">*Descrizione* criterio è una descrizione facile da usare del criterio che consente di ricordare a cosa si sta a fare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3fa70-154">È possibile includere spazi nella descrizione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-154">You can include spaces in the description.</span></span> <span data-ttu-id="3fa70-155">Ad esempio, "Root key for mailboxes in USA and its territories".</span><span class="sxs-lookup"><span data-stu-id="3fa70-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="3fa70-156">*KeyVaultURI1* è l'URI per la prima chiave nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3fa70-157">Ad esempio, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="3fa70-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="3fa70-158">*KeyVaultURI2* è l'URI per la seconda chiave nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3fa70-159">Ad esempio, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="3fa70-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="3fa70-160">Separare i due URI con una virgola e uno spazio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="3fa70-161">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="3fa70-162">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="3fa70-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="3fa70-163">Assegnare una protezione esecuzione programmi a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="3fa70-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="3fa70-164">Assegnare Protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="3fa70-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="3fa70-165">Dopo aver assegnato il criterio, Microsoft 365 crittografare la cassetta postale con la chiave identificata nella protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3fa70-166">Dove *MailboxIdParameter* specifica una cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="3fa70-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="3fa70-167">Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="3fa70-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="3fa70-168">Negli ambienti ibridi, è possibile assegnare una protezione esecuzione programmi ai dati delle cassette postali locali sincronizzati nel tenant Exchange Online locale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="3fa70-169">Per assegnare una protezione esecuzione programmi ai dati sincronizzati della cassetta postale, si utilizzerà il cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="3fa70-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="3fa70-170">Per ulteriori informazioni sui dati delle cassette postali nell'ambiente ibrido, vedere Cassette postali locali che usano [Outlook per iOS](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)e Android con autenticazione moderna ibrida.</span><span class="sxs-lookup"><span data-stu-id="3fa70-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3fa70-171">Dove *MailUserIdParameter* specifica un utente di posta (noto anche come utente abilitato alla posta).</span><span class="sxs-lookup"><span data-stu-id="3fa70-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="3fa70-172">Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="3fa70-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3fa70-173">Creare una protezione esecuzione programmi da utilizzare con SharePoint Online, OneDrive for Business e Teams file</span><span class="sxs-lookup"><span data-stu-id="3fa70-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3fa70-174">Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3fa70-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3fa70-175">Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3fa70-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="3fa70-176">Per configurare il codice "Customer Key" per i file di SharePoint Online, OneDrive for Business e Teams, completare questi passaggi connettendosi in remoto a SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="3fa70-177">È possibile associare una protezione esecuzione programmi a un set di chiavi archiviate in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3fa70-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3fa70-178">Si applica una protezione esecuzione programmi a tutti i dati in un'unica posizione geografica, denominata anche geo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="3fa70-179">Se usi la funzionalità multi-geo di Office 365, puoi creare una protezione esecuzione programmi per ogni area geografica con la possibilità di usare chiavi diverse per ogni geo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="3fa70-180">Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi nell'organizzazione per l'utilizzo con SharePoint Online, OneDrive for Business e Teams file.</span><span class="sxs-lookup"><span data-stu-id="3fa70-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="3fa70-181">Microsoft 365 le chiavi identificate nella protezione esecuzione programmi per crittografare i dati in tale area geografica.</span><span class="sxs-lookup"><span data-stu-id="3fa70-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="3fa70-182">Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3fa70-183">Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3fa70-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="3fa70-184">Ricordati!</span><span class="sxs-lookup"><span data-stu-id="3fa70-184">Remember!</span></span> <span data-ttu-id="3fa70-185">Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi insiemi di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="3fa70-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3fa70-186">Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="3fa70-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3fa70-187">Per creare una protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="3fa70-188">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, Connessione [a SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3fa70-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="3fa70-189">In Microsoft SharePoint Online Management Shell eseguire il cmdlet Register-SPODataEncryptionPolicy seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="3fa70-190">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="3fa70-191">Quando si registra protezione esecuzione programmi, la crittografia inizia sui dati nel geo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="3fa70-192">La crittografia può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-192">Encryption can take some time.</span></span> <span data-ttu-id="3fa70-193">Per ulteriori informazioni sull'utilizzo di questo parametro, [vedere Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="3fa70-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="3fa70-194">Visualizzare i dep creati per le Exchange Online postali</span><span class="sxs-lookup"><span data-stu-id="3fa70-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="3fa70-195">Per visualizzare un elenco di tutti i DEP creati per le cassette postali, utilizzare il cmdlet Get-DataEncryptionPolicy PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3fa70-196">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fa70-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3fa70-197">Per restituire tutti i criteri di configurazione dell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.</span><span class="sxs-lookup"><span data-stu-id="3fa70-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="3fa70-198">Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="3fa70-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="3fa70-199">Assegnare una protezione esecuzione programmi prima di eseguire la migrazione di una cassetta postale nel cloud</span><span class="sxs-lookup"><span data-stu-id="3fa70-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="3fa70-200">Quando si assegna protezione esecuzione programmi, Microsoft 365 il contenuto della cassetta postale utilizzando la protezione esecuzione programmi assegnata durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="3fa70-201">Questo processo è più efficiente della migrazione della cassetta postale, dell'assegnazione di Protezione esecuzione programmi e quindi dell'attesa della crittografia, che può richiedere ore o probabilmente giorni.</span><span class="sxs-lookup"><span data-stu-id="3fa70-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="3fa70-202">Per assegnare una protezione esecuzione programmi a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3fa70-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="3fa70-203">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fa70-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3fa70-204">Eseguire il cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="3fa70-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="3fa70-205">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DataEncryptionPolicyIdParameter* è l'ID della protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="3fa70-206">Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="3fa70-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3fa70-207">Determinare la protezione esecuzione programmi assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="3fa70-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="3fa70-208">Per determinare la protezione esecuzione programmi assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="3fa70-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3fa70-209">Il cmdlet restituisce un identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="3fa70-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="3fa70-210">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fa70-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="3fa70-211">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="3fa70-212">Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="3fa70-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="3fa70-213">Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della protezione esecuzione programmi a cui è assegnata la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="3fa70-214">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3fa70-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="3fa70-215">Verificare che customer key abbia completato la crittografia</span><span class="sxs-lookup"><span data-stu-id="3fa70-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="3fa70-216">Sia che sia stato eseguito il rollover di una chiave cliente, sia che sia stata assegnata una nuova protezione esecuzione programmi o sia stata eseguita la migrazione di una cassetta postale, utilizzare la procedura descritta in questa sezione per verificare che la crittografia sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="3fa70-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="3fa70-217">Verificare il completamento della crittografia per Exchange Online cassette postali</span><span class="sxs-lookup"><span data-stu-id="3fa70-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="3fa70-218">La crittografia di una cassetta postale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3fa70-219">Per la prima crittografia, la cassetta postale deve inoltre spostarsi completamente da un database a un altro prima che il servizio possa crittografare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="3fa70-220">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.</span><span class="sxs-lookup"><span data-stu-id="3fa70-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3fa70-221">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.</span><span class="sxs-lookup"><span data-stu-id="3fa70-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="3fa70-222">Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui si assegna una protezione esecuzione programmi per la prima volta e dalle dimensioni delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="3fa70-223">Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stata assegnata la funzionalità Protezione esecuzione programmi, contattare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fa70-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="3fa70-224">Il cmdlet New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="3fa70-225">Per ulteriori [informazioni, fare](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) riferimento a questo annuncio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3fa70-226">Verificare il completamento della crittografia per SharePoint online, OneDrive for Business e Teams file</span><span class="sxs-lookup"><span data-stu-id="3fa70-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3fa70-227">Verificare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3fa70-228">L'output di questo cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="3fa70-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3fa70-229">URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3fa70-229">The URI of the primary key.</span></span>

- <span data-ttu-id="3fa70-230">URI della chiave secondaria.</span><span class="sxs-lookup"><span data-stu-id="3fa70-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="3fa70-231">Stato di crittografia per la posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="3fa70-231">The encryption status for the geo.</span></span> <span data-ttu-id="3fa70-232">Gli stati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="3fa70-232">Possible states include:</span></span>

  - <span data-ttu-id="3fa70-233">**Non registrato:** La crittografia della chiave del cliente non è ancora stata applicata.</span><span class="sxs-lookup"><span data-stu-id="3fa70-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="3fa70-234">**Registrazione:** La crittografia della chiave del cliente è stata applicata e i file sono in fase di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3fa70-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3fa70-235">Se la chiave per la posizione geografica è in corso di registrazione, verranno visualizzate anche informazioni sulla percentuale di siti nel geo completati in modo da poter monitorare l'avanzamento della crittografia.</span><span class="sxs-lookup"><span data-stu-id="3fa70-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="3fa70-236">**Registrato:** La crittografia della chiave del cliente è stata applicata e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="3fa70-237">**Rolling:** È in corso un roll-key.</span><span class="sxs-lookup"><span data-stu-id="3fa70-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3fa70-238">Se la chiave per la posizione geografica è in esecuzione, verranno visualizzate anche informazioni sulla percentuale di siti che hanno completato l'operazione di rollio delle chiavi in modo da poter monitorare lo stato.</span><span class="sxs-lookup"><span data-stu-id="3fa70-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="3fa70-239">Ottenere informazioni dettagliate sui criteri di dep da usare con più carichi di lavoro</span><span class="sxs-lookup"><span data-stu-id="3fa70-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="3fa70-240">Per ottenere informazioni dettagliate su tutti i dep creati per l'utilizzo con più carichi di lavoro, completare questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="3fa70-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3fa70-241">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="3fa70-242">Per restituire l'elenco di tutti i DEP multi-carico di lavoro nell'organizzazione, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="3fa70-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="3fa70-243">Per ottenere informazioni dettagliate su una protezione esecuzione programmi specifica, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="3fa70-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="3fa70-244">In questo esempio vengono restituite informazioni dettagliate per la protezione esecuzione programmi denominata "Contoso_Global".</span><span class="sxs-lookup"><span data-stu-id="3fa70-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="3fa70-245">Ottenere informazioni sull'assegnazione di Protezione esecuzione programmi multi-carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="3fa70-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="3fa70-246">Per scoprire quale protezione esecuzione programmi è attualmente assegnata al tenant, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3fa70-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="3fa70-247">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3fa70-248">Digitare questo comando.</span><span class="sxs-lookup"><span data-stu-id="3fa70-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="3fa70-249">Disabilitare protezione esecuzione programmi con più carichi di lavoro</span><span class="sxs-lookup"><span data-stu-id="3fa70-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="3fa70-250">Prima di disabilitare protezione esecuzione programmi con più carichi di lavoro, annullare l'assegnazione di Protezione esecuzione programmi dai carichi di lavoro nel tenant.</span><span class="sxs-lookup"><span data-stu-id="3fa70-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="3fa70-251">Per disabilitare una funzionalità Protezione esecuzione programmi utilizzata con più carichi di lavoro, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3fa70-252">Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3fa70-253">Eseguire il cmdlet Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="3fa70-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="3fa70-254">Dove *PolicyName* è il nome o l'ID univoco del criterio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="3fa70-255">Ad esempio, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="3fa70-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="3fa70-256">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3fa70-257">Ripristinare le chiavi dell'insieme di credenziali delle chiavi di Azure</span><span class="sxs-lookup"><span data-stu-id="3fa70-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="3fa70-258">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione recidiva.</span><span class="sxs-lookup"><span data-stu-id="3fa70-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3fa70-259">Tutte le chiavi utilizzate con customer key devono avere l'eliminazione soft abilitata.</span><span class="sxs-lookup"><span data-stu-id="3fa70-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3fa70-260">L'eliminazione recidiva funziona come un Cestino e consente il ripristino per un massimo di 90 giorni senza la necessità di eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="3fa70-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3fa70-261">Il ripristino deve essere necessario solo in circostanze estreme o insolite, ad esempio in caso di perdita della chiave o dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3fa70-262">Se è necessario ripristinare una chiave da utilizzare con customer key, in Azure PowerShell eseguire il cmdlet Restore-AzureKeyVaultKey seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="3fa70-263">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3fa70-264">Se l'insieme di credenziali delle chiavi contiene già una chiave con lo stesso nome, l'operazione di ripristino ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3fa70-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="3fa70-265">Restore-AzKeyVaultKey ripristina tutte le versioni chiave e tutti i metadati per la chiave, incluso il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="3fa70-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="3fa70-266">Gestire le autorizzazioni dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="3fa70-266">Manage key vault permissions</span></span>

<span data-ttu-id="3fa70-267">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3fa70-268">Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="3fa70-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="3fa70-269">Per ognuna di queste attività, verrà utilizzato Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="3fa70-270">Per informazioni su Azure PowerShell, vedere [Overview of Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="3fa70-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="3fa70-271">Per visualizzare le autorizzazioni dell'insieme di credenziali delle chiavi, eseguire il cmdlet Get-AzKeyVault chiave.</span><span class="sxs-lookup"><span data-stu-id="3fa70-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="3fa70-272">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3fa70-273">Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="3fa70-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="3fa70-274">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa70-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="3fa70-275">Eseguire il rollback da Customer Key alle chiavi gestite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3fa70-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="3fa70-276">Se è necessario ripristinare le chiavi gestite da Microsoft, è possibile.</span><span class="sxs-lookup"><span data-stu-id="3fa70-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="3fa70-277">Quando si esegue l'offboard, i dati vengono crittografati di nuovo utilizzando la crittografia predefinita supportata da ogni singolo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3fa70-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="3fa70-278">Ad esempio, Exchange Online supporta la crittografia predefinita tramite chiavi gestite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fa70-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fa70-279">L'offboarding non corrisponde a un'eliminazione di dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="3fa70-280">Un'eliminazione dei dati elimina definitivamente i dati dell'organizzazione da Microsoft 365, l'offboarding non lo fa.</span><span class="sxs-lookup"><span data-stu-id="3fa70-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="3fa70-281">Non è possibile eseguire un'eliminazione dei dati per un criterio di più carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3fa70-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="3fa70-282">Se decidi di non usare più il codice "Customer Key" per l'assegnazione di DEP multi-carico di lavoro, dovrai contattare il supporto Tecnico Microsoft con una richiesta di "offboard" da Customer Key.</span><span class="sxs-lookup"><span data-stu-id="3fa70-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="3fa70-283">Chiedere al team di supporto di eseguire una richiesta di servizio Microsoft 365 team customer key.</span><span class="sxs-lookup"><span data-stu-id="3fa70-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="3fa70-284">Contatta il m365-ck@service.microsoft.com se hai domande.</span><span class="sxs-lookup"><span data-stu-id="3fa70-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="3fa70-285">Se non si desidera più crittografare singole cassette postali utilizzando dep a livello di cassetta postale, è possibile annullare l'assegnazione dei DEP a livello di cassetta postale da tutte le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="3fa70-286">Per annullare l'assegnazione dei DEP delle cassette postali, utilizzare il cmdlet Set-Mailbox PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa70-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3fa70-287">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fa70-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3fa70-288">Eseguire il cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="3fa70-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="3fa70-289">L'esecuzione di questo cmdlet annulla l'assegnazione della protezione esecuzione programmi attualmente assegnata e ricrittografa la cassetta postale utilizzando la protezione esecuzione programmi associata alle chiavi gestite da Microsoft predefinite.</span><span class="sxs-lookup"><span data-stu-id="3fa70-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="3fa70-290">Non è possibile annullare l'assegnazione di Protezione esecuzione programmi utilizzata dalle chiavi gestite Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fa70-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="3fa70-291">Se non si desidera utilizzare le chiavi gestite da Microsoft, è possibile assegnare un'altra protezione esecuzione programmi chiave cliente alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="3fa70-292">Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="3fa70-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="3fa70-293">Puoi controllare la revoca di tutte le chiavi radice, inclusa la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3fa70-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="3fa70-294">Customer Key fornisce il controllo dell'aspetto della pianificazione dell'uscita dei requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="3fa70-295">Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio elimina la chiave di disponibilità al termine del processo di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="3fa70-296">Questa funzionalità è supportata per i CRITERI chiave del cliente assegnati a singole cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="3fa70-297">Microsoft 365 controlla e convalida il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="3fa70-298">Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3fa70-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="3fa70-299">Inoltre, Microsoft consiglia i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fa70-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="3fa70-300">Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari in Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="3fa70-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="3fa70-301">Considerazioni sulla pianificazione dell'uscita da O365</span><span class="sxs-lookup"><span data-stu-id="3fa70-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="3fa70-302">L'eliminazione di Protezione esecuzione programmi multi-carico di lavoro non è supportata per Microsoft 365 customer key.</span><span class="sxs-lookup"><span data-stu-id="3fa70-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="3fa70-303">La funzionalità Protezione esecuzione programmi multi-carico di lavoro viene utilizzata per crittografare i dati in più carichi di lavoro tra tutti gli utenti tenant.</span><span class="sxs-lookup"><span data-stu-id="3fa70-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="3fa70-304">Se si elimina tale protezione esecuzione programmi, i dati provenienti da più carichi di lavoro diventeranno inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="3fa70-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="3fa70-305">Se si decide di uscire completamente Microsoft 365 servizi, è possibile seguire il percorso di eliminazione del tenant per il processo documentato.</span><span class="sxs-lookup"><span data-stu-id="3fa70-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="3fa70-306">Informazioni [su come eliminare un tenant in Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="3fa70-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3fa70-307">Revocare le chiavi cliente e la chiave di disponibilità per Exchange Online e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3fa70-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3fa70-308">Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for Business, si imposta una richiesta di eliminazione dei dati permanente in una protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="3fa70-309">In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la funzionalità Protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="3fa70-310">Poiché è possibile eseguire il cmdlet PowerShell solo su una funzionalità Protezione esecuzione programmi alla volta, è consigliabile riassegnare una singola protezione esecuzione programmi a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="3fa70-311">Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="3fa70-312">Questo processo è destinato solo ai clienti che escno dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3fa70-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="3fa70-313">Per avviare il percorso di eliminazione dei dati, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="3fa70-314">Rimuovere le autorizzazioni di wrapping e annullamento del wrapping per "O365 Exchange Online" dagli insiemi di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="3fa70-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="3fa70-315">Utilizzando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale [nell'organizzazione, connettersi a Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3fa70-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="3fa70-316">Per ogni protezione esecuzione programmi contenente le cassette postali che si desidera eliminare, eseguire il cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3fa70-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="3fa70-317">Se il comando ha esito negativo, assicurarsi di aver rimosso le autorizzazioni Exchange Online da entrambe le chiavi in Azure Key Vault, come specificato in precedenza in questa attività.</span><span class="sxs-lookup"><span data-stu-id="3fa70-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="3fa70-318">Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non sarà più possibile assegnare la funzionalità Protezione esecuzione programmi alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3fa70-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="3fa70-319">Contattare il supporto Tecnico Microsoft e richiedere l'eDocument di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="3fa70-320">Su richiesta dell'utente, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="3fa70-321">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="3fa70-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3fa70-322">In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="3fa70-323">Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="3fa70-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="3fa70-324">Una volta ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati che prima elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva, quindi elimina la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3fa70-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="3fa70-325">Al termine del processo di eliminazione dei dati, i dati sono stati eliminati, non sono accessibili Exchange Online e non sono ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="3fa70-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3fa70-326">Revocare le chiavi cliente e la chiave di disponibilità per SharePoint online, OneDrive for Business e Teams file</span><span class="sxs-lookup"><span data-stu-id="3fa70-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3fa70-327">Per avviare il percorso di eliminazione dei dati per SharePoint online, OneDrive for Business e Teams file, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3fa70-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="3fa70-328">Revocare l'accesso all'insieme di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="3fa70-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="3fa70-329">Tutti gli amministratori dell'insieme di credenziali delle chiavi devono accettare di revocare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3fa70-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="3fa70-330">Non eliminare Azure Key Vault per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3fa70-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="3fa70-331">Gli insiemi di credenziali delle chiavi possono essere condivisi tra SharePoint tenant e dep online.</span><span class="sxs-lookup"><span data-stu-id="3fa70-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="3fa70-332">Contattare Microsoft per eliminare la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3fa70-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="3fa70-333">Quando si contatta Microsoft per eliminare la chiave di disponibilità, verrà inviato un documento legale.</span><span class="sxs-lookup"><span data-stu-id="3fa70-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="3fa70-334">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="3fa70-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3fa70-335">In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3fa70-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="3fa70-336">Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="3fa70-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="3fa70-337">Una volta ricevuto il documento legale, Microsoft esegue cmdlet per attivare l'eliminazione dei dati che esegue l'eliminazione crittografica della chiave tenant, della chiave del sito e di tutte le singole chiavi per documento, interrompendo irrevocabilmente la gerarchia delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="3fa70-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="3fa70-338">Al termine dei cmdlet di eliminazione dei dati, i dati sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="3fa70-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3fa70-339">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="3fa70-339">Related articles</span></span>

- [<span data-ttu-id="3fa70-340">Crittografia del servizio con Customer Key</span><span class="sxs-lookup"><span data-stu-id="3fa70-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3fa70-341">Informazioni sulla chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="3fa70-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="3fa70-342">Configurare il codice "Customer Key"</span><span class="sxs-lookup"><span data-stu-id="3fa70-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3fa70-343">Implementare o distribuire una Customer Key o una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="3fa70-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3fa70-344">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="3fa70-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="3fa70-345">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="3fa70-345">Service Encryption</span></span>](office-365-service-encryption.md)