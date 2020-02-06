---
title: Gestire la chiave del cliente per Office 365
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
ms.openlocfilehash: 112bdee7658334c251418903761866841625ff17
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804814"
---
# <a name="manage-customer-key-for-office-365"></a><span data-ttu-id="b51aa-103">Gestire la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b51aa-103">Manage Customer Key for Office 365</span></span>

<span data-ttu-id="b51aa-104">Dopo aver configurato Customer Key per Office 365, è possibile gestire le chiavi come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="b51aa-105">Per ulteriori informazioni, vedere Key Customer negli argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="b51aa-106">Ripristinare le chiavi del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="b51aa-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="b51aa-107">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite da soft delete.</span><span class="sxs-lookup"><span data-stu-id="b51aa-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="b51aa-108">Tutte le chiavi utilizzate con la chiave Customer devono essere abilitate per l'eliminazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="b51aa-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="b51aa-109">Delete Soft agisce come un cestino e consente il ripristino per un massimo di 90 giorni senza che sia necessario ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="b51aa-110">Il ripristino deve essere necessario solo in caso di circostanze estreme o inusuali, ad esempio se la chiave o la chiave del Vault è persa.</span><span class="sxs-lookup"><span data-stu-id="b51aa-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="b51aa-111">Se è necessario ripristinare una chiave da utilizzare con la chiave Customer, in Azure PowerShell, eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b51aa-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="b51aa-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b51aa-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="b51aa-113">Se il Vault della chiave contiene già un tasto con lo stesso nome, l'operazione di ripristino avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="b51aa-114">Restore-AzKeyVaultKey Ripristina tutte le versioni principali e tutti i metadati per la chiave, incluso il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="b51aa-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="b51aa-115">Gestire le autorizzazioni del Vault Key</span><span class="sxs-lookup"><span data-stu-id="b51aa-115">Manage key vault permissions</span></span>

<span data-ttu-id="b51aa-116">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, di rimuovere le autorizzazioni chiave del Vault.</span><span class="sxs-lookup"><span data-stu-id="b51aa-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="b51aa-117">Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="b51aa-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="b51aa-118">Per ognuna di queste attività, si utilizzerà Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b51aa-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="b51aa-119">Per informazioni su Azure PowerShell, vedere [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="b51aa-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="b51aa-120">Per visualizzare le autorizzazioni per il Vault chiave, eseguire il cmdlet Get-AzKeyVault.</span><span class="sxs-lookup"><span data-stu-id="b51aa-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="b51aa-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b51aa-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="b51aa-122">Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="b51aa-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="b51aa-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b51aa-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="b51aa-124">Gestire i criteri di crittografia dei dati con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="b51aa-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="b51aa-125">La chiave Customer gestisce DEPs in modo diverso tra i diversi servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b51aa-125">Customer Key handles DEPs differently between the different Office 365 services.</span></span> <span data-ttu-id="b51aa-126">Ad esempio, è possibile creare un numero diverso di DEPs per i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="b51aa-127">**Exchange Online e Skype for business:** È possibile creare fino a 50 DEPs.</span><span class="sxs-lookup"><span data-stu-id="b51aa-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="b51aa-128">Per istruzioni, vedere [creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="b51aa-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="b51aa-129">**File di SharePoint Online, OneDrive for business e teams:** Una DEP si applica ai dati in una posizione geografica, denominata anche _Geo_.</span><span class="sxs-lookup"><span data-stu-id="b51aa-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="b51aa-130">Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="b51aa-131">Se non si utilizza multi-Geo, è possibile creare una DEP.</span><span class="sxs-lookup"><span data-stu-id="b51aa-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="b51aa-132">In genere, si crea la funzionalità DEP quando si configura la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="b51aa-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="b51aa-133">Per istruzioni, vedere [creare un criterio di crittografia dei dati (DEP, Data Encryption Policy) per ogni server di SharePoint Online e OneDrive for business Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="b51aa-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b51aa-134">Visualizzare il DEPs creato per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="b51aa-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="b51aa-135">Per visualizzare un elenco di tutti i DEPs creati per Exchange Online e Skype for business utilizzando il cmdlet Get-DataEncryptionPolicy di PowerShell, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b51aa-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="b51aa-136">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-136">Using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="b51aa-137">Per restituire tutti i DEPs nell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.</span><span class="sxs-lookup"><span data-stu-id="b51aa-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="b51aa-138">Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="b51aa-139">Assegnare una DEP prima di eseguire la migrazione di una cassetta postale nel cloud</span><span class="sxs-lookup"><span data-stu-id="b51aa-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="b51aa-140">Quando si assegna la funzionalità DEP, Office 365 crittografa il contenuto della cassetta postale utilizzando la funzionalità DEP assegnata durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b51aa-140">When you assign the DEP, Office 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="b51aa-141">Questo processo è più efficiente della migrazione della cassetta postale, assegnando la funzionalità DEP e quindi in attesa che venga eseguita la crittografia, che può richiedere ore o eventualmente giorni.</span><span class="sxs-lookup"><span data-stu-id="b51aa-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="b51aa-142">Per assegnare una DEP a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="b51aa-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="b51aa-143">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-143">Using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="b51aa-144">Eseguire il cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="b51aa-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="b51aa-145">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DATAENCRYPTIONPOLICYIDPARAMETER* è l'ID della funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="b51aa-146">Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="b51aa-147">Determinare la funzionalità DEP assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b51aa-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="b51aa-148">Per determinare la funzionalità DEP assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="b51aa-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="b51aa-149">Il cmdlet restituisce un identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="b51aa-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="b51aa-150">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-150">Using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="b51aa-151">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="b51aa-152">Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="b51aa-153">Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della funzionalità DEP a cui è assegnata la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="b51aa-154">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b51aa-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="b51aa-155">Verificare che la chiave del cliente abbia completato la crittografia</span><span class="sxs-lookup"><span data-stu-id="b51aa-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="b51aa-156">Se è stata appena eseguita una chiave del cliente, è stata assegnata una nuova DEP o ha eseguito la migrazione di una cassetta postale, attenersi alla procedura descritta in questa sezione per assicurarsi che la crittografia venga completata.</span><span class="sxs-lookup"><span data-stu-id="b51aa-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b51aa-157">Verifica del completamento della crittografia per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="b51aa-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="b51aa-158">La crittografia di una cassetta postale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="b51aa-159">È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="b51aa-160">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.</span><span class="sxs-lookup"><span data-stu-id="b51aa-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="b51aa-161">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.</span><span class="sxs-lookup"><span data-stu-id="b51aa-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="b51aa-162">Il tempo necessario per completare gli spostamenti delle cassette postali dipende dalle dimensioni della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="b51aa-163">Se la chiave del cliente non ha completamente crittografato la cassetta postale dopo 72 ore dal momento in cui viene assegnata una nuova protezione esecuzione programmi, avviare lo spostamento di una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, initiate a mailbox move.</span></span> <span data-ttu-id="b51aa-164">A tale scopo, utilizzare il cmdlet New-MoveRequest e specificare l'alias della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-164">To do this, use the New-MoveRequest cmdlet and provide the alias of the mailbox.</span></span> <span data-ttu-id="b51aa-165">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b51aa-165">For example:</span></span>
  
```powershell
New-MoveRequest <alias>
```

<span data-ttu-id="b51aa-166">Per ulteriori informazioni su questo cmdlet, vedere [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-166">For more information about this cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps).</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="b51aa-167">Verifica del completamento della crittografia per i file di SharePoint Online, OneDrive for business e teams</span><span class="sxs-lookup"><span data-stu-id="b51aa-167">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="b51aa-168">Controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b51aa-168">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="b51aa-169">L'output di questo cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="b51aa-169">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="b51aa-170">URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b51aa-170">The URI of the primary key.</span></span>

- <span data-ttu-id="b51aa-171">URI del tasto secondario.</span><span class="sxs-lookup"><span data-stu-id="b51aa-171">The URI of the secondary key.</span></span>

- <span data-ttu-id="b51aa-172">Lo stato di crittografia per il Geo.</span><span class="sxs-lookup"><span data-stu-id="b51aa-172">The encryption status for the geo.</span></span> <span data-ttu-id="b51aa-173">Gli stati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="b51aa-173">Possible states include:</span></span>

  - <span data-ttu-id="b51aa-174">Non **registrato:** La crittografia a chiave del cliente non è stata ancora applicata.</span><span class="sxs-lookup"><span data-stu-id="b51aa-174">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="b51aa-175">**Registrazione:** È stata applicata la crittografia a chiave del cliente e i file sono in fase di crittografazione.</span><span class="sxs-lookup"><span data-stu-id="b51aa-175">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="b51aa-176">Se si sta registrando la chiave per il Geo, verranno visualizzate anche informazioni sulla percentuale di siti in Geo che sono stati completati in modo da poter monitorare lo stato della crittografia.</span><span class="sxs-lookup"><span data-stu-id="b51aa-176">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="b51aa-177">**Registrato:** È stata applicata la crittografia a chiave del cliente e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-177">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="b51aa-178">**Rolling:** È in corso un roll Key.</span><span class="sxs-lookup"><span data-stu-id="b51aa-178">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="b51aa-179">Se la chiave per il servizio Geo è in corso, verranno visualizzate anche informazioni su quale percentuale di siti è stata completata l'operazione di roll Key in modo da poter monitorare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="b51aa-179">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="b51aa-180">Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b51aa-180">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="b51aa-181">È possibile controllare la revoca di tutte le chiavi radice incluso il tasto disponibilità.</span><span class="sxs-lookup"><span data-stu-id="b51aa-181">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="b51aa-182">La chiave del cliente fornisce il controllo dell'aspetto di pianificazione dell'uscita dei requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-182">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="b51aa-183">Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio eliminerà la chiave di disponibilità dopo il completamento del processo di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-183">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="b51aa-184">Office 365 verifica e convalida il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-184">Office 365 audits and validates the data purge path.</span></span> <span data-ttu-id="b51aa-185">Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b51aa-185">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="b51aa-186">Microsoft consiglia inoltre i seguenti documenti:</span><span class="sxs-lookup"><span data-stu-id="b51aa-186">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="b51aa-187">Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari nel cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="b51aa-187">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="b51aa-188">Considerazioni sulla pianificazione dell'uscita di O365</span><span class="sxs-lookup"><span data-stu-id="b51aa-188">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="b51aa-189">Il percorso di eliminazione dei dati differisce leggermente tra i diversi servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b51aa-189">The data purge path differs slightly between the different Office 365 services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b51aa-190">Revocare le chiavi dei clienti e la chiave di disponibilità per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="b51aa-190">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="b51aa-191">Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for business, è possibile impostare una richiesta di eliminazione dei dati permanenti su una funzionalità di protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-191">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="b51aa-192">In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la DEP.</span><span class="sxs-lookup"><span data-stu-id="b51aa-192">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="b51aa-193">Poiché è possibile eseguire solo il cmdlet di PowerShell su una DEP alla volta, valutare la possibilità di riassegnare una singola funzionalità DEP a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-193">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="b51aa-194">Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="b51aa-194">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="b51aa-195">Questo processo è destinato solo ai clienti che sono in uscita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b51aa-195">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="b51aa-196">Per avviare il percorso di eliminazione dei dati, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b51aa-196">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="b51aa-197">Rimuovere le autorizzazioni wrap e unwrap per "O365 Exchange Online" dai Vault delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="b51aa-197">Remove wrap and unwrap permissions for “O365 Exchange Online” from Azure Key Vaults.</span></span>

2. <span data-ttu-id="b51aa-198">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b51aa-198">Using a work or school account that has global administrator privileges in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="b51aa-199">Per ogni DEP che contiene le cassette postali che si desidera eliminare, eseguire il cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b51aa-199">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="b51aa-200">Se il comando ha esito negativo, verificare di aver rimosso le autorizzazioni di Exchange Online da entrambe le chiavi in Azure Key Vault come specificato in precedenza in questa attività.</span><span class="sxs-lookup"><span data-stu-id="b51aa-200">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="b51aa-201">Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non è più possibile assegnare questa funzionalità DEP alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="b51aa-201"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="b51aa-202">Contattare il supporto tecnico Microsoft e richiedere l'eliminazione dei dati eDocument.</span><span class="sxs-lookup"><span data-stu-id="b51aa-202">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="b51aa-203">Su richiesta, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-203">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="b51aa-204">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="b51aa-204">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="b51aa-205">In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b51aa-205">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="b51aa-206">Una volta che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (di solito tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="b51aa-206">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="b51aa-207">Dopo che Microsoft ha ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati, che prima Elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva e quindi Elimina il codice di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="b51aa-207">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="b51aa-208">Dopo il completamento del processo di eliminazione dei dati, i dati sono stati eliminati, sono inaccessibili per Exchange Online e non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="b51aa-208">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="b51aa-209">Revocare le chiavi dei clienti e la chiave di disponibilità per i file di SharePoint Online, OneDrive for business e teams</span><span class="sxs-lookup"><span data-stu-id="b51aa-209">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="b51aa-210">Per avviare il percorso di eliminazione dei dati per i file di SharePoint Online, OneDrive for business e teams, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b51aa-210">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="b51aa-211">Revocare l'accesso all'archivio delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="b51aa-211">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="b51aa-212">Tutti gli amministratori di Key Vault devono accettare di revocare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b51aa-212">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="b51aa-213">Non è possibile eliminare l'archiviazione delle chiavi di Azure per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b51aa-213">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="b51aa-214">I Vault chiave possono essere condivisi tra più tenant e DEPs di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b51aa-214">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="b51aa-215">Per eliminare il codice di disponibilità, contattare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b51aa-215">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="b51aa-216">Quando si contatta Microsoft per eliminare la chiave di disponibilità, è possibile inviare un documento legale.</span><span class="sxs-lookup"><span data-stu-id="b51aa-216">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="b51aa-217">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="b51aa-217">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="b51aa-218">In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda che è legalmente autorizzata a firmare la documentazione per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b51aa-218">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="b51aa-219">Una volta che il rappresentante firmerà il documento legale, lo restituirà a Microsoft (di solito tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="b51aa-219">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="b51aa-220">Dopo la ricezione del documento legale da parte di Microsoft, vengono eseguiti i cmdlet per attivare l'eliminazione dei dati, che consente di eliminare la chiave tenant, la chiave del sito e tutti i singoli tasti per documento, infrangendo irrevocabilmente la gerarchia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b51aa-220">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="b51aa-221">Dopo aver completato i cmdlet per l'eliminazione dei dati, i dati sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="b51aa-221">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b51aa-222">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b51aa-222">Related articles</span></span>

- [<span data-ttu-id="b51aa-223">Crittografia del servizio con la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b51aa-223">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b51aa-224">Informazioni sulla chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="b51aa-224">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="b51aa-225">Configurare la chiave cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b51aa-225">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b51aa-226">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="b51aa-226">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b51aa-227">Archivio protetto dei clienti in Office 365</span><span class="sxs-lookup"><span data-stu-id="b51aa-227">Customer Lockbox in Office 365</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="b51aa-228">Servizio di crittografia di Office 365</span><span class="sxs-lookup"><span data-stu-id="b51aa-228">Office 365 Service Encryption</span></span>](office-365-service-encryption.md)
