---
title: Gestire il codice Cliente
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
description: Dopo aver configurato Customer Key, scopri come gestirlo ripristinando le chiavi AKV e gestendo le autorizzazioni e i criteri di crittografia dei dati.
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909948"
---
# <a name="manage-customer-key"></a><span data-ttu-id="38d37-103">Gestire il codice Cliente</span><span class="sxs-lookup"><span data-stu-id="38d37-103">Manage Customer Key</span></span>

<span data-ttu-id="38d37-104">Dopo aver configurato customer key per Office 365, è possibile gestire le chiavi come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="38d37-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="38d37-105">Per ulteriori informazioni, vedere Customer Key negli argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="38d37-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="38d37-106">Ripristinare le chiavi dell'insieme di credenziali delle chiavi di Azure</span><span class="sxs-lookup"><span data-stu-id="38d37-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="38d37-107">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione recidiva.</span><span class="sxs-lookup"><span data-stu-id="38d37-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="38d37-108">Tutte le chiavi utilizzate con customer key devono avere l'eliminazione soft abilitata.</span><span class="sxs-lookup"><span data-stu-id="38d37-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="38d37-109">L'eliminazione recidiva funziona come un Cestino e consente il ripristino per un massimo di 90 giorni senza la necessità di eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="38d37-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="38d37-110">Il ripristino deve essere necessario solo in circostanze estreme o insolite, ad esempio in caso di perdita della chiave o dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="38d37-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="38d37-111">Se è necessario ripristinare una chiave da utilizzare con customer key, in Azure PowerShell eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38d37-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="38d37-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38d37-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="38d37-113">Se l'insieme di credenziali delle chiavi contiene già una chiave con lo stesso nome, l'operazione di ripristino ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="38d37-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="38d37-114">Restore-AzKeyVaultKey ripristina tutte le versioni chiave e tutti i metadati per la chiave, incluso il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="38d37-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="38d37-115">Gestire le autorizzazioni dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="38d37-115">Manage key vault permissions</span></span>

<span data-ttu-id="38d37-116">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="38d37-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="38d37-117">Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="38d37-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="38d37-118">Per ognuna di queste attività, si userà Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38d37-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="38d37-119">Per informazioni su Azure PowerShell, vedere [Panoramica di Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="38d37-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="38d37-120">Per visualizzare le autorizzazioni dell'insieme di credenziali delle chiavi, eseguire il cmdlet Get-AzKeyVault chiave.</span><span class="sxs-lookup"><span data-stu-id="38d37-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="38d37-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38d37-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="38d37-122">Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="38d37-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="38d37-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38d37-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="38d37-124">Gestire i criteri di crittografia dei dati (DEP) con customer key</span><span class="sxs-lookup"><span data-stu-id="38d37-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="38d37-125">Customer Key gestisce i criteri di configurazione in modo diverso tra i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="38d37-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="38d37-126">Ad esempio, è possibile creare un numero diverso di DEP per i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="38d37-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="38d37-127">**Exchange Online e Skype for Business:** È possibile creare fino a 50 DEP.</span><span class="sxs-lookup"><span data-stu-id="38d37-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="38d37-128">Per istruzioni, vedere [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="38d37-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="38d37-129">**File di SharePoint Online, OneDrive for Business e Teams:** Una protezione esecuzione programmi si applica ai dati in una posizione geografica, denominata anche _geo._</span><span class="sxs-lookup"><span data-stu-id="38d37-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="38d37-130">Se si usa la funzionalità multi-geo di Office 365, è possibile creare una protezione esecuzione programmi per ogni area geografica.</span><span class="sxs-lookup"><span data-stu-id="38d37-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="38d37-131">Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="38d37-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="38d37-132">In genere, la protezione esecuzione programmi viene creata quando si configura il codice "Customer Key".</span><span class="sxs-lookup"><span data-stu-id="38d37-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="38d37-133">Per istruzioni, vedere [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)</span><span class="sxs-lookup"><span data-stu-id="38d37-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="38d37-134">Visualizzare i dep creati per Exchange Online e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="38d37-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="38d37-135">Per visualizzare un elenco di tutti i dep creati per Exchange Online e Skype for Business utilizzando il cmdlet powershell Get-DataEncryptionPolicy, completare questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="38d37-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="38d37-136">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38d37-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="38d37-137">Per restituire tutti i criteri di configurazione dell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.</span><span class="sxs-lookup"><span data-stu-id="38d37-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="38d37-138">Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="38d37-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="38d37-139">Assegnare una protezione esecuzione programmi prima di eseguire la migrazione di una cassetta postale nel cloud</span><span class="sxs-lookup"><span data-stu-id="38d37-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="38d37-140">Quando si assegna protezione esecuzione programmi, Microsoft 365 crittografa il contenuto della cassetta postale utilizzando la protezione esecuzione programmi assegnata durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="38d37-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="38d37-141">Questo processo è più efficiente della migrazione della cassetta postale, dell'assegnazione di Protezione esecuzione programmi e quindi dell'attesa della crittografia, che può richiedere ore o probabilmente giorni.</span><span class="sxs-lookup"><span data-stu-id="38d37-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="38d37-142">Per assegnare una protezione esecuzione programmi a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="38d37-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="38d37-143">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38d37-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="38d37-144">Eseguire il cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="38d37-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="38d37-145">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DataEncryptionPolicyIdParameter* è l'ID della protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="38d37-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="38d37-146">Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="38d37-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="38d37-147">Determinare la protezione esecuzione programmi assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="38d37-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="38d37-148">Per determinare la protezione esecuzione programmi assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="38d37-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="38d37-149">Il cmdlet restituisce un identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="38d37-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="38d37-150">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38d37-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="38d37-151">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="38d37-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="38d37-152">Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="38d37-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="38d37-153">Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della protezione esecuzione programmi a cui è assegnata la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="38d37-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="38d37-154">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="38d37-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="38d37-155">Verificare che customer key abbia completato la crittografia</span><span class="sxs-lookup"><span data-stu-id="38d37-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="38d37-156">Indipendentemente dal fatto che sia stato appena eseguito il rollover di una chiave cliente, che sia stata assegnata una nuova protezione esecuzione programmi o sia stata eseguita la migrazione di una cassetta postale, eseguire la procedura descritta in questa sezione per verificare che la crittografia sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="38d37-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="38d37-157">Verificare il completamento della crittografia per Exchange Online e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="38d37-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="38d37-158">La crittografia di una cassetta postale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="38d37-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="38d37-159">È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato protezione esecuzione programmi o la prima volta che si assegna una protezione esecuzione programmi a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="38d37-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="38d37-160">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.</span><span class="sxs-lookup"><span data-stu-id="38d37-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="38d37-161">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.</span><span class="sxs-lookup"><span data-stu-id="38d37-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="38d37-162">Il tempo necessario per completare gli spostamenti delle cassette postali dipende dalle dimensioni della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="38d37-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="38d37-163">Se customer key non ha completamente crittografato la cassetta postale dopo 72 ore dal momento in cui si assegna una nuova protezione esecuzione programmi, contattare il supporto Tecnico Microsoft per assistenza.</span><span class="sxs-lookup"><span data-stu-id="38d37-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="38d37-164">Il cmdlet New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="38d37-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="38d37-165">Per ulteriori [informazioni, fare](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) riferimento a questo annuncio.</span><span class="sxs-lookup"><span data-stu-id="38d37-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="38d37-166">Verificare il completamento della crittografia per i file di SharePoint Online, OneDrive for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="38d37-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="38d37-167">Verificare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy seguente:</span><span class="sxs-lookup"><span data-stu-id="38d37-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="38d37-168">L'output di questo cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="38d37-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="38d37-169">URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="38d37-169">The URI of the primary key.</span></span>

- <span data-ttu-id="38d37-170">URI della chiave secondaria.</span><span class="sxs-lookup"><span data-stu-id="38d37-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="38d37-171">Stato di crittografia per la posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="38d37-171">The encryption status for the geo.</span></span> <span data-ttu-id="38d37-172">Gli stati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="38d37-172">Possible states include:</span></span>

  - <span data-ttu-id="38d37-173">**Non registrato:** La crittografia della chiave del cliente non è ancora stata applicata.</span><span class="sxs-lookup"><span data-stu-id="38d37-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="38d37-174">**Registrazione:** La crittografia della chiave del cliente è stata applicata e i file sono in fase di crittografia.</span><span class="sxs-lookup"><span data-stu-id="38d37-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="38d37-175">Se la chiave per la posizione geografica è in corso di registrazione, verranno visualizzate anche informazioni sulla percentuale di siti nel geo completati in modo da poter monitorare l'avanzamento della crittografia.</span><span class="sxs-lookup"><span data-stu-id="38d37-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="38d37-176">**Registrato:** La crittografia della chiave del cliente è stata applicata e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="38d37-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="38d37-177">**Rolling:** È in corso un roll-key.</span><span class="sxs-lookup"><span data-stu-id="38d37-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="38d37-178">Se la chiave per la posizione geografica è in esecuzione, verranno visualizzate anche informazioni sulla percentuale di siti che hanno completato l'operazione di rollio delle chiavi in modo da poter monitorare lo stato.</span><span class="sxs-lookup"><span data-stu-id="38d37-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="38d37-179">Annullare l'assegnazione di protezione esecuzione programmi da una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="38d37-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="38d37-180">Per annullare l'assegnazione di protezione esecuzione programmi da una cassetta postale, utilizzare il cmdlet Set-mailbox di PowerShell e impostare `DataEncryptionPolicy` su `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="38d37-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="38d37-181">L'esecuzione di questo cmdlet annulla l'assegnazione della protezione esecuzione programmi attualmente assegnata e ricrittografa la cassetta postale utilizzando la protezione esecuzione programmi associata alle chiavi gestite Microsoft predefinite.</span><span class="sxs-lookup"><span data-stu-id="38d37-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="38d37-182">Non è possibile annullare l'assegnazione di Protezione esecuzione programmi utilizzata dalle chiavi gestite Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38d37-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="38d37-183">Se non si desidera utilizzare le chiavi gestite microsoft, è possibile assegnare un'altra protezione esecuzione programmi alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="38d37-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="38d37-184">Per annullare l'assegnazione di Protezione esecuzione programmi da una cassetta postale utilizzando il cmdlet Set-Mailbox PowerShell, completare questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="38d37-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="38d37-185">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38d37-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="38d37-186">Eseguire il cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="38d37-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="38d37-187">Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="38d37-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="38d37-188">Puoi controllare la revoca di tutte le chiavi radice, inclusa la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="38d37-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="38d37-189">Customer Key fornisce il controllo dell'aspetto della pianificazione dell'uscita dei requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="38d37-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="38d37-190">Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio elimina la chiave di disponibilità al termine del processo di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="38d37-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="38d37-191">Microsoft 365 controlla e convalida il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="38d37-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="38d37-192">Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="38d37-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="38d37-193">Inoltre, Microsoft consiglia i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38d37-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="38d37-194">Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari in Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="38d37-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="38d37-195">Considerazioni sulla pianificazione dell'uscita da O365</span><span class="sxs-lookup"><span data-stu-id="38d37-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="38d37-196">Il percorso di eliminazione dei dati è leggermente diverso tra i diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="38d37-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="38d37-197">Revocare le chiavi del cliente e la chiave di disponibilità per Exchange Online e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="38d37-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="38d37-198">Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for Business, si imposta una richiesta di eliminazione dei dati permanente in una protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="38d37-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="38d37-199">In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la funzionalità Protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="38d37-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="38d37-200">Poiché è possibile eseguire il cmdlet PowerShell solo su una funzionalità Protezione esecuzione programmi alla volta, è consigliabile riassegnare una singola protezione esecuzione programmi a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="38d37-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="38d37-201">Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="38d37-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="38d37-202">Questo processo è destinato solo ai clienti che escno dal servizio.</span><span class="sxs-lookup"><span data-stu-id="38d37-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="38d37-203">Per avviare il percorso di eliminazione dei dati, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="38d37-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="38d37-204">Rimuovere le autorizzazioni di wrapping e annullamento del wrapping per "O365 Exchange Online" dagli insiemi di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="38d37-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="38d37-205">Utilizzando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38d37-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="38d37-206">Per ogni protezione esecuzione programmi contenente le cassette postali che si desidera eliminare, eseguire il cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="38d37-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="38d37-207">Se il comando ha esito negativo, assicurarsi di aver rimosso le autorizzazioni di Exchange Online da entrambe le chiavi in Azure Key Vault come specificato in precedenza in questa attività.</span><span class="sxs-lookup"><span data-stu-id="38d37-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="38d37-208">Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non sarà più possibile assegnare la funzionalità Protezione esecuzione programmi alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="38d37-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="38d37-209">Contattare il supporto Tecnico Microsoft e richiedere l'eDocument di eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="38d37-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="38d37-210">Su richiesta dell'utente, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="38d37-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="38d37-211">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="38d37-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="38d37-212">In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38d37-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="38d37-213">Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="38d37-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="38d37-214">Una volta ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati che prima elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva, quindi elimina la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="38d37-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="38d37-215">Al termine del processo di eliminazione dei dati, i dati sono stati eliminati, non sono accessibili a Exchange Online e non sono ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="38d37-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="38d37-216">Revocare le chiavi del cliente e la chiave di disponibilità per i file di SharePoint Online, OneDrive for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="38d37-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="38d37-217">Per avviare il percorso di eliminazione dei dati per i file di SharePoint Online, OneDrive for Business e Teams, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="38d37-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="38d37-218">Revocare l'accesso all'insieme di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="38d37-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="38d37-219">Tutti gli amministratori dell'insieme di credenziali delle chiavi devono accettare di revocare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="38d37-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="38d37-220">Non eliminare l'insieme di credenziali delle chiavi di Azure per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38d37-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="38d37-221">Gli insiemi di credenziali delle chiavi possono essere condivisi tra diversi tenant e dep di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38d37-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="38d37-222">Contattare Microsoft per eliminare la chiave di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="38d37-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="38d37-223">Quando si contatta Microsoft per eliminare la chiave di disponibilità, verrà inviato un documento legale.</span><span class="sxs-lookup"><span data-stu-id="38d37-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="38d37-224">La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento.</span><span class="sxs-lookup"><span data-stu-id="38d37-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="38d37-225">In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38d37-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="38d37-226">Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).</span><span class="sxs-lookup"><span data-stu-id="38d37-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="38d37-227">Una volta ricevuto il documento legale, Microsoft esegue cmdlet per attivare l'eliminazione dei dati che esegue l'eliminazione crittografica della chiave tenant, della chiave del sito e di tutte le singole chiavi per documento, interrompendo irrevocabilmente la gerarchia delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="38d37-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="38d37-228">Al termine dei cmdlet di eliminazione dei dati, i dati sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="38d37-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="38d37-229">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="38d37-229">Related articles</span></span>

- [<span data-ttu-id="38d37-230">Crittografia del servizio con Customer Key</span><span class="sxs-lookup"><span data-stu-id="38d37-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="38d37-231">Informazioni sulla chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="38d37-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="38d37-232">Configurare il codice "Customer Key"</span><span class="sxs-lookup"><span data-stu-id="38d37-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="38d37-233">Implementare o distribuire una Customer Key o una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="38d37-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="38d37-234">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="38d37-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="38d37-235">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="38d37-235">Service Encryption</span></span>](office-365-service-encryption.md)