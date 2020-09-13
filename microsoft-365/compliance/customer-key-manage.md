---
title: Gestione della chiave del cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Una volta configurata la chiave del cliente, informazioni su come gestirla ripristinando le chiavi di AKV e gestendo le autorizzazioni e i criteri di crittografia dei dati.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547086"
---
# <a name="manage-customer-key"></a><span data-ttu-id="de287-103">Gestione della chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="de287-103">Manage Customer Key</span></span>

<span data-ttu-id="de287-104">Dopo aver configurato Customer Key per Office 365, è possibile gestire le chiavi come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="de287-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="de287-105">Per ulteriori informazioni, vedere Key Customer negli argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="de287-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="de287-106">Ripristinare le chiavi del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="de287-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="de287-107">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite da soft delete.</span><span class="sxs-lookup"><span data-stu-id="de287-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="de287-108">Tutte le chiavi utilizzate con la chiave Customer devono essere abilitate per l'eliminazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="de287-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="de287-109">Delete Soft agisce come un cestino e consente il ripristino per un massimo di 90 giorni senza che sia necessario ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="de287-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="de287-110">Il ripristino deve essere necessario solo in caso di circostanze estreme o inusuali, ad esempio se la chiave o la chiave del Vault è persa.</span><span class="sxs-lookup"><span data-stu-id="de287-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="de287-111">Se è necessario ripristinare una chiave da utilizzare con la chiave Customer, in Azure PowerShell, eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="de287-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="de287-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="de287-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="de287-113">Se il Vault della chiave contiene già un tasto con lo stesso nome, l'operazione di ripristino avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="de287-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="de287-114">Restore-AzKeyVaultKey Ripristina tutte le versioni principali e tutti i metadati per la chiave, incluso il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="de287-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="de287-115">Gestire le autorizzazioni del Vault Key</span><span class="sxs-lookup"><span data-stu-id="de287-115">Manage key vault permissions</span></span>

<span data-ttu-id="de287-116">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, di rimuovere le autorizzazioni chiave del Vault.</span><span class="sxs-lookup"><span data-stu-id="de287-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="de287-117">Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="de287-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="de287-118">Per ognuna di queste attività, si utilizzerà Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de287-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="de287-119">Per informazioni su Azure PowerShell, vedere [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="de287-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="de287-120">Per visualizzare le autorizzazioni per il Vault chiave, eseguire il cmdlet Get-AzKeyVault.</span><span class="sxs-lookup"><span data-stu-id="de287-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="de287-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="de287-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="de287-122">Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="de287-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="de287-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="de287-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="de287-124">Gestire i criteri di crittografia dei dati con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="de287-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="de287-125">La chiave Customer gestisce il DEPs in modo diverso tra i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="de287-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="de287-126">Ad esempio, è possibile creare un numero diverso di DEPs per i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="de287-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="de287-127">**Exchange Online e Skype for business:** È possibile creare fino a 50 DEPs.</span><span class="sxs-lookup"><span data-stu-id="de287-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="de287-128">Per istruzioni, vedere [creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="de287-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="de287-129">**File di SharePoint Online, OneDrive for business e teams:** Una DEP si applica ai dati in una posizione geografica, denominata anche _Geo_.</span><span class="sxs-lookup"><span data-stu-id="de287-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="de287-130">Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo.</span><span class="sxs-lookup"><span data-stu-id="de287-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="de287-131">Se non si utilizza multi-Geo, è possibile creare una DEP.</span><span class="sxs-lookup"><span data-stu-id="de287-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="de287-132">In genere, si crea la funzionalità DEP quando si configura la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="de287-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="de287-133">Per istruzioni, vedere [creare un criterio di crittografia dei dati (DEP, Data Encryption Policy) per ogni server di SharePoint Online e OneDrive for business Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="de287-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="de287-134">Visualizzare il DEPs creato per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="de287-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="de287-135">Per visualizzare un elenco di tutti i DEPs creati per Exchange Online e Skype for business utilizzando il cmdlet Get-DataEncryptionPolicy di PowerShell, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="de287-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="de287-136">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de287-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="de287-137">Per restituire tutti i DEPs nell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.</span><span class="sxs-lookup"><span data-stu-id="de287-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="de287-138">Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="de287-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="de287-139">Assegnare una DEP prima di eseguire la migrazione di una cassetta postale nel cloud</span><span class="sxs-lookup"><span data-stu-id="de287-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="de287-140">Quando si assegna la funzionalità DEP, Microsoft 365 crittografa il contenuto della cassetta postale utilizzando la funzionalità DEP assegnata durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="de287-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="de287-141">Questo processo è più efficiente della migrazione della cassetta postale, assegnando la funzionalità DEP e quindi in attesa che venga eseguita la crittografia, che può richiedere ore o eventualmente giorni.</span><span class="sxs-lookup"><span data-stu-id="de287-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="de287-142">Per assegnare una DEP a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="de287-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="de287-143">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de287-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="de287-144">Eseguire il cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="de287-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="de287-145">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DATAENCRYPTIONPOLICYIDPARAMETER* è l'ID della funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="de287-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="de287-146">Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="de287-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="de287-147">Determinare la funzionalità DEP assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="de287-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="de287-148">Per determinare la funzionalità DEP assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="de287-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="de287-149">Il cmdlet restituisce un identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="de287-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="de287-150">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de287-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="de287-151">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="de287-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="de287-152">Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="de287-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="de287-153">Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della funzionalità DEP a cui è assegnata la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="de287-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="de287-154">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="de287-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="de287-155">Verificare che la chiave del cliente abbia completato la crittografia</span><span class="sxs-lookup"><span data-stu-id="de287-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="de287-156">Se è stata appena eseguita una chiave del cliente, è stata assegnata una nuova DEP o ha eseguito la migrazione di una cassetta postale, attenersi alla procedura descritta in questa sezione per assicurarsi che la crittografia venga completata.</span><span class="sxs-lookup"><span data-stu-id="de287-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="de287-157">Verifica del completamento della crittografia per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="de287-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="de287-158">La crittografia di una cassetta postale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="de287-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="de287-159">È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="de287-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="de287-160">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.</span><span class="sxs-lookup"><span data-stu-id="de287-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="de287-161">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.</span><span class="sxs-lookup"><span data-stu-id="de287-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="de287-162">Il tempo necessario per completare gli spostamenti delle cassette postali dipende dalle dimensioni della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="de287-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="de287-163">Se la chiave del cliente non ha crittografato completamente la cassetta postale dopo 72 ore dal momento in cui viene assegnata una nuova protezione esecuzione programmi, contattare il supporto tecnico Microsoft per assistenza.</span><span class="sxs-lookup"><span data-stu-id="de287-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="de287-164">Il cmdlet New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="de287-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="de287-165">Per ulteriori informazioni, fare riferimento a [questo annuncio](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) .</span><span class="sxs-lookup"><span data-stu-id="de287-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="de287-166">Verifica del completamento della crittografia per i file di SharePoint Online, OneDrive for business e teams</span><span class="sxs-lookup"><span data-stu-id="de287-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="de287-167">Controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="de287-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="de287-168">L'output di questo cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="de287-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="de287-169">URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="de287-169">The URI of the primary key.</span></span>

- <span data-ttu-id="de287-170">URI del tasto secondario.</span><span class="sxs-lookup"><span data-stu-id="de287-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="de287-171">Lo stato di crittografia per il Geo.</span><span class="sxs-lookup"><span data-stu-id="de287-171">The encryption status for the geo.</span></span> <span data-ttu-id="de287-172">Gli stati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="de287-172">Possible states include:</span></span>

  - <span data-ttu-id="de287-173">Non **registrato:** La crittografia a chiave del cliente non è stata ancora applicata.</span><span class="sxs-lookup"><span data-stu-id="de287-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="de287-174">**Registrazione:** È stata applicata la crittografia a chiave del cliente e i file sono in fase di crittografazione.</span><span class="sxs-lookup"><span data-stu-id="de287-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="de287-175">Se si sta registrando la chiave per il Geo, verranno visualizzate anche informazioni sulla percentuale di siti in Geo che sono stati completati in modo da poter monitorare lo stato della crittografia.</span><span class="sxs-lookup"><span data-stu-id="de287-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="de287-176">**Registrato:** È stata applicata la crittografia a chiave del cliente e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="de287-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="de287-177">**Rolling:** È in corso un roll Key.</span><span class="sxs-lookup"><span data-stu-id="de287-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="de287-178">Se la chiave per il servizio Geo è in corso, verranno visualizzate anche informazioni su quale percentuale di siti è stata completata l'operazione di roll Key in modo da poter monitorare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="de287-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="de287-179">Annullamento dell'assegnazione di una funzionalità di protezione da una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="de287-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="de287-180">Per annullare l'assegnazione di una funzionalità di protezione esecuzione programmi da una cassetta postale, utilizzare il cmdlet Set-Mailbox PowerShell e impostare `DataEncryptionPolicy` su `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="de287-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="de287-181">L'esecuzione di questo cmdlet Annulla l'assegnazione della funzionalità DEP correntemente assegnata e la riesegue la crittografia della cassetta postale utilizzando la funzionalità DEP associata alle chiavi gestite Microsoft predefinite.</span><span class="sxs-lookup"><span data-stu-id="de287-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="de287-182">Non è possibile annullare l'assegnazione della funzionalità DEP utilizzata dalle chiavi gestite Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de287-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="de287-183">Se non si desidera utilizzare le chiavi gestite Microsoft, è possibile assegnare un altro DEP alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="de287-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="de287-184">Per annullare l'assegnazione di DEP da una cassetta postale utilizzando il cmdlet Set-Mailbox PowerShell, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="de287-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="de287-185">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de287-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="de287-186">Eseguire il cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="de287-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="de287-187">Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="de287-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="de287-188">È possibile controllare la revoca di tutte le chiavi radice incluso il tasto disponibilità.</span><span class="sxs-lookup"><span data-stu-id="de287-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="de287-189">La chiave del cliente fornisce il controllo dell'aspetto di pianificazione dell'uscita dei requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="de287-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="de287-190">Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio eliminerà la chiave di disponibilità dopo il completamento del processo di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="de287-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="de287-191">Microsoft 365 verifica e convalida il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="de287-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="de287-192">Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="de287-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="de287-193">Microsoft consiglia inoltre i seguenti documenti:</span><span class="sxs-lookup"><span data-stu-id="de287-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="de287-194">Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari nel cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="de287-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="de287-195">Considerazioni sulla pianificazione dell'uscita di O365</span><span class="sxs-lookup"><span data-stu-id="de287-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="de287-196">Il percorso di eliminazione dei dati differisce leggermente tra i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="de287-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="de287-197">Revocare le chiavi dei clienti e la chiave di disponibilità per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="de287-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="de287-198">Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for business, è possibile impostare una richiesta di eliminazione dei dati permanenti su una funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="de287-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="de287-199">In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la DEP.</span><span class="sxs-lookup"><span data-stu-id="de287-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="de287-200">Poiché è possibile eseguire solo il cmdlet di PowerShell su una DEP alla volta, valutare la possibilità di riassegnare una singola funzionalità DEP a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="de287-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="de287-201">Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="de287-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="de287-202">Questo processo è destinato solo ai clienti che sono in uscita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="de287-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="de287-203">Per avviare il percorso di eliminazione dei dati, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="de287-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="de287-204">Rimuovere le autorizzazioni wrap e unwrap per "O365 Exchange Online" dai Vault delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="de287-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="de287-205">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de287-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="de287-206">Per ogni DEP che contiene le cassette postali che si desidera eliminare, eseguire il cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="de287-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="de287-207">Se il comando ha esito negativo, verificare di aver rimosso le autorizzazioni di Exchange Online da entrambe le chiavi in Azure Key Vault come specificato in precedenza in questa attività.</span><span class="sxs-lookup"><span data-stu-id="de287-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="de287-208">Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non è più possibile assegnare questa funzionalità DEP alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="de287-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="de287-209">Contattare il supporto tecnico Microsoft e richiedere l'eliminazione dei dati eDocument.</span><span class="sxs-lookup"><span data-stu-id="de287-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="de287-210">Su richiesta, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="de287-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="de287-211">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="de287-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="de287-212">In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de287-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="de287-213">Una volta che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (di solito tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="de287-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="de287-214">Dopo che Microsoft ha ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati, che prima Elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva e quindi Elimina il codice di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="de287-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="de287-215">Dopo il completamento del processo di eliminazione dei dati, i dati sono stati eliminati, sono inaccessibili per Exchange Online e non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="de287-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="de287-216">Revocare le chiavi dei clienti e la chiave di disponibilità per i file di SharePoint Online, OneDrive for business e teams</span><span class="sxs-lookup"><span data-stu-id="de287-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="de287-217">Per avviare il percorso di eliminazione dei dati per i file di SharePoint Online, OneDrive for business e teams, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="de287-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="de287-218">Revocare l'accesso all'archivio delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="de287-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="de287-219">Tutti gli amministratori di Key Vault devono accettare di revocare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="de287-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="de287-220">Non è possibile eliminare l'archiviazione delle chiavi di Azure per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="de287-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="de287-221">I Vault chiave possono essere condivisi tra più tenant e DEPs di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="de287-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="de287-222">Per eliminare il codice di disponibilità, contattare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de287-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="de287-223">Quando si contatta Microsoft per eliminare la chiave di disponibilità, è possibile inviare un documento legale.</span><span class="sxs-lookup"><span data-stu-id="de287-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="de287-224">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="de287-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="de287-225">In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda che è legalmente autorizzata a firmare la documentazione per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de287-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="de287-226">Una volta che il rappresentante firmerà il documento legale, lo restituirà a Microsoft (di solito tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="de287-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="de287-227">Dopo la ricezione del documento legale da parte di Microsoft, vengono eseguiti i cmdlet per attivare l'eliminazione dei dati, che consente di eliminare la chiave tenant, la chiave del sito e tutti i singoli tasti per documento, infrangendo irrevocabilmente la gerarchia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="de287-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="de287-228">Dopo aver completato i cmdlet per l'eliminazione dei dati, i dati sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="de287-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="de287-229">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="de287-229">Related articles</span></span>

- [<span data-ttu-id="de287-230">Crittografia del servizio con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="de287-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="de287-231">Informazioni sulla chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="de287-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="de287-232">Configurare la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="de287-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="de287-233">Implementare o distribuire una Customer Key o una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="de287-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="de287-234">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="de287-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="de287-235">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="de287-235">Service Encryption</span></span>](office-365-service-encryption.md)
