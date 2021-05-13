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
# <a name="manage-customer-key"></a>Gestire il codice Cliente

Dopo aver configurato customer key per Office 365, è necessario creare e assegnare uno o più criteri di crittografia dei dati(DEP). Dopo aver assegnato i CRITERI di gruppo, è possibile gestire le chiavi come descritto in questo articolo. Per ulteriori informazioni, vedere Customer Key negli argomenti correlati.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Creare una protezione esecuzione programmi da utilizzare con più carichi di lavoro per tutti gli utenti tenant

Prima di iniziare, assicurati di aver completato le attività necessarie per configurare Customer. Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md). Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione. Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Per creare una protezione esecuzione programmi con più carichi di lavoro, attenersi alla seguente procedura:
  
1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.

2. Per creare una protezione esecuzione programmi, utilizzare il cmdlet New-M365DataAtRestEncryptionPolicy.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Dove:

   - *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, Contoso_Global.

   - *KeyVaultURI1* è l'URI per la prima chiave nel criterio. Ad esempio, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* è l'URI per la seconda chiave nel criterio. Ad esempio, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Separare i due URI con una virgola e uno spazio.

   - *Descrizione* criterio è una descrizione facile da usare del criterio che consente di ricordare a cosa si sta a fare il criterio. È possibile includere spazi nella descrizione. Ad esempio, "Criteri radice per più carichi di lavoro per tutti gli utenti nel tenant.".

Esempio:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Assegnare criteri multi-carico di lavoro

Assegnare Protezione esecuzione programmi utilizzando il cmdlet Set-M365DataAtRestEncryptionPolicyAssignment. Dopo aver assegnato il criterio, Microsoft 365 i dati con la chiave identificata nella protezione esecuzione programmi.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Dove *PolicyName* è il nome del criterio. Ad esempio, Contoso_Global.

Esempio:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Creare una protezione esecuzione programmi da utilizzare con Exchange Online cassette postali

Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure Key Vault. Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md). Questi passaggi verranno completati connettendosi in remoto a Exchange Online con Windows PowerShell.

Una protezione esecuzione programmi è associata a un set di chiavi archiviate in Azure Key Vault. Si assegna una protezione esecuzione programmi a una cassetta postale in Microsoft 365. Microsoft 365 verranno quindi utilizzate le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione. Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Ricordati! Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi insiemi di credenziali delle chiavi di Azure. Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.

Per creare una protezione esecuzione programmi da utilizzare con una cassetta postale, attenersi alla seguente procedura:
  
1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di Exchange Online nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.

2. Per creare una protezione esecuzione programmi, utilizzare New-DataEncryptionPolicy cmdlet digitando il comando seguente.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dove:

   - *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.

   - *Descrizione* criterio è una descrizione facile da usare del criterio che consente di ricordare a cosa si sta a fare il criterio. È possibile includere spazi nella descrizione. Ad esempio, "Root key for mailboxes in USA and its territories".

   - *KeyVaultURI1* è l'URI per la prima chiave nel criterio. Ad esempio, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* è l'URI per la seconda chiave nel criterio. Ad esempio, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separare i due URI con una virgola e uno spazio.

   Esempio:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Assegnare una protezione esecuzione programmi a una cassetta postale

Assegnare Protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Microsoft 365 crittografare la cassetta postale con la chiave identificata nella protezione esecuzione programmi.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailboxIdParameter* specifica una cassetta postale utente. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Negli ambienti ibridi, è possibile assegnare una protezione esecuzione programmi ai dati delle cassette postali locali sincronizzati nel tenant Exchange Online locale. Per assegnare una protezione esecuzione programmi ai dati sincronizzati della cassetta postale, si utilizzerà il cmdlet Set-MailUser. Per ulteriori informazioni sui dati delle cassette postali nell'ambiente ibrido, vedere Cassette postali locali che usano [Outlook per iOS](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)e Android con autenticazione moderna ibrida.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailUserIdParameter* specifica un utente di posta (noto anche come utente abilitato alla posta). Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](/powershell/module/exchange/set-mailuser).

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Creare una protezione esecuzione programmi da utilizzare con SharePoint Online, OneDrive for Business e Teams file

Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure Key Vault. Per informazioni, vedere [Set up Customer Key](customer-key-set-up.md).
  
Per configurare il codice "Customer Key" per i file di SharePoint Online, OneDrive for Business e Teams, completare questi passaggi connettendosi in remoto a SharePoint Online con Windows PowerShell.
  
È possibile associare una protezione esecuzione programmi a un set di chiavi archiviate in Azure Key Vault. Si applica una protezione esecuzione programmi a tutti i dati in un'unica posizione geografica, denominata anche geo. Se usi la funzionalità multi-geo di Office 365, puoi creare una protezione esecuzione programmi per ogni area geografica con la possibilità di usare chiavi diverse per ogni geo. Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi nell'organizzazione per l'utilizzo con SharePoint Online, OneDrive for Business e Teams file. Microsoft 365 le chiavi identificate nella protezione esecuzione programmi per crittografare i dati in tale area geografica. Per creare Protezione esecuzione programmi, sono necessari gli URI dell'insieme di credenziali delle chiavi ottenuti durante l'installazione. Per informazioni, vedere [Ottenere l'URI per ogni chiave dell'insieme di credenziali delle chiavi di Azure.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)
  
Ricordati! Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi insiemi di credenziali delle chiavi di Azure. Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare una protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online utilizzando Windows PowerShell.
  
1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, Connessione [a SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)

2. In Microsoft SharePoint Online Management Shell eseguire il cmdlet Register-SPODataEncryptionPolicy seguente:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Esempio:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Quando si registra protezione esecuzione programmi, la crittografia inizia sui dati nel geo. La crittografia può richiedere del tempo. Per ulteriori informazioni sull'utilizzo di questo parametro, [vedere Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Visualizzare i dep creati per le Exchange Online postali

Per visualizzare un elenco di tutti i DEP creati per le cassette postali, utilizzare il cmdlet Get-DataEncryptionPolicy PowerShell.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Per restituire tutti i criteri di configurazione dell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Assegnare una protezione esecuzione programmi prima di eseguire la migrazione di una cassetta postale nel cloud

Quando si assegna protezione esecuzione programmi, Microsoft 365 il contenuto della cassetta postale utilizzando la protezione esecuzione programmi assegnata durante la migrazione. Questo processo è più efficiente della migrazione della cassetta postale, dell'assegnazione di Protezione esecuzione programmi e quindi dell'attesa della crittografia, che può richiedere ore o probabilmente giorni.

Per assegnare una protezione esecuzione programmi a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in Exchange Online PowerShell:

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DataEncryptionPolicyIdParameter* è l'ID della protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinare la protezione esecuzione programmi assegnata a una cassetta postale

Per determinare la protezione esecuzione programmi assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce un identificatore univoco (GUID).
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).
  
2. Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della protezione esecuzione programmi a cui è assegnata la cassetta postale.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificare che customer key abbia completato la crittografia

Sia che sia stato eseguito il rollover di una chiave cliente, sia che sia stata assegnata una nuova protezione esecuzione programmi o sia stata eseguita la migrazione di una cassetta postale, utilizzare la procedura descritta in questa sezione per verificare che la crittografia sia stata completata.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Verificare il completamento della crittografia per Exchange Online cassette postali

La crittografia di una cassetta postale può richiedere del tempo. Per la prima crittografia, la cassetta postale deve inoltre spostarsi completamente da un database a un altro prima che il servizio possa crittografare la cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata. Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui si assegna una protezione esecuzione programmi per la prima volta e dalle dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stata assegnata la funzionalità Protezione esecuzione programmi, contattare Microsoft.

Il cmdlet New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali. Per ulteriori [informazioni, fare](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) riferimento a questo annuncio.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verificare il completamento della crittografia per SharePoint online, OneDrive for Business e Teams file

Verificare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy seguente:

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

L'output di questo cmdlet include:
  
- URI della chiave primaria.

- URI della chiave secondaria.

- Stato di crittografia per la posizione geografica. Gli stati possibili includono:

  - **Non registrato:** La crittografia della chiave del cliente non è ancora stata applicata.

  - **Registrazione:** La crittografia della chiave del cliente è stata applicata e i file sono in fase di crittografia. Se la chiave per la posizione geografica è in corso di registrazione, verranno visualizzate anche informazioni sulla percentuale di siti nel geo completati in modo da poter monitorare l'avanzamento della crittografia.

  - **Registrato:** La crittografia della chiave del cliente è stata applicata e tutti i file in tutti i siti sono stati crittografati.

  - **Rolling:** È in corso un roll-key. Se la chiave per la posizione geografica è in esecuzione, verranno visualizzate anche informazioni sulla percentuale di siti che hanno completato l'operazione di rollio delle chiavi in modo da poter monitorare lo stato.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Ottenere informazioni dettagliate sui criteri di dep da usare con più carichi di lavoro

Per ottenere informazioni dettagliate su tutti i dep creati per l'utilizzo con più carichi di lavoro, completare questi passaggi:

1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.

   - Per restituire l'elenco di tutti i DEP multi-carico di lavoro nell'organizzazione, eseguire questo comando.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Per ottenere informazioni dettagliate su una protezione esecuzione programmi specifica, eseguire questo comando. In questo esempio vengono restituite informazioni dettagliate per la protezione esecuzione programmi denominata "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Ottenere informazioni sull'assegnazione di Protezione esecuzione programmi multi-carico di lavoro

Per scoprire quale protezione esecuzione programmi è attualmente assegnata al tenant, seguire questa procedura. 

1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.

2. Digitare questo comando.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Disabilitare protezione esecuzione programmi con più carichi di lavoro

Prima di disabilitare protezione esecuzione programmi con più carichi di lavoro, annullare l'assegnazione di Protezione esecuzione programmi dai carichi di lavoro nel tenant. Per disabilitare una funzionalità Protezione esecuzione programmi utilizzata con più carichi di lavoro, eseguire la procedura seguente:

1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale o amministratore di conformità nell'organizzazione, connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in una finestra Windows PowerShell.

2. Eseguire il cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Dove *PolicyName* è il nome o l'ID univoco del criterio. Ad esempio, Contoso_Global.

Esempio:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Ripristinare le chiavi dell'insieme di credenziali delle chiavi di Azure

Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione recidiva. Tutte le chiavi utilizzate con customer key devono avere l'eliminazione soft abilitata. L'eliminazione recidiva funziona come un Cestino e consente il ripristino per un massimo di 90 giorni senza la necessità di eseguire il ripristino. Il ripristino deve essere necessario solo in circostanze estreme o insolite, ad esempio in caso di perdita della chiave o dell'insieme di credenziali delle chiavi. Se è necessario ripristinare una chiave da utilizzare con customer key, in Azure PowerShell eseguire il cmdlet Restore-AzureKeyVaultKey seguente:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Ad esempio:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se l'insieme di credenziali delle chiavi contiene già una chiave con lo stesso nome, l'operazione di ripristino ha esito negativo. Restore-AzKeyVaultKey ripristina tutte le versioni chiave e tutti i metadati per la chiave, incluso il nome della chiave.
  
## <a name="manage-key-vault-permissions"></a>Gestire le autorizzazioni dell'insieme di credenziali delle chiavi

Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni dell'insieme di credenziali delle chiavi. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team. Per ognuna di queste attività, verrà utilizzato Azure PowerShell. Per informazioni su Azure PowerShell, vedere [Overview of Azure PowerShell](/powershell/azure/).

Per visualizzare le autorizzazioni dell'insieme di credenziali delle chiavi, eseguire il cmdlet Get-AzKeyVault chiave.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Ad esempio:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Ad esempio:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Eseguire il rollback da Customer Key alle chiavi gestite da Microsoft

Se è necessario ripristinare le chiavi gestite da Microsoft, è possibile. Quando si esegue l'offboard, i dati vengono crittografati di nuovo utilizzando la crittografia predefinita supportata da ogni singolo carico di lavoro. Ad esempio, Exchange Online supporta la crittografia predefinita tramite chiavi gestite da Microsoft.

> [!IMPORTANT]
> L'offboarding non corrisponde a un'eliminazione di dati. Un'eliminazione dei dati elimina definitivamente i dati dell'organizzazione da Microsoft 365, l'offboarding non lo fa. Non è possibile eseguire un'eliminazione dei dati per un criterio di più carichi di lavoro.

Se decidi di non usare più il codice "Customer Key" per l'assegnazione di DEP multi-carico di lavoro, dovrai contattare il supporto Tecnico Microsoft con una richiesta di "offboard" da Customer Key. Chiedere al team di supporto di eseguire una richiesta di servizio Microsoft 365 team customer key. Contatta il m365-ck@service.microsoft.com se hai domande.

Se non si desidera più crittografare singole cassette postali utilizzando dep a livello di cassetta postale, è possibile annullare l'assegnazione dei DEP a livello di cassetta postale da tutte le cassette postali.

Per annullare l'assegnazione dei DEP delle cassette postali, utilizzare il cmdlet Set-Mailbox PowerShell.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

L'esecuzione di questo cmdlet annulla l'assegnazione della protezione esecuzione programmi attualmente assegnata e ricrittografa la cassetta postale utilizzando la protezione esecuzione programmi associata alle chiavi gestite da Microsoft predefinite. Non è possibile annullare l'assegnazione di Protezione esecuzione programmi utilizzata dalle chiavi gestite Microsoft. Se non si desidera utilizzare le chiavi gestite da Microsoft, è possibile assegnare un'altra protezione esecuzione programmi chiave cliente alla cassetta postale.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati

Puoi controllare la revoca di tutte le chiavi radice, inclusa la chiave di disponibilità. Customer Key fornisce il controllo dell'aspetto della pianificazione dell'uscita dei requisiti normativi. Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio elimina la chiave di disponibilità al termine del processo di eliminazione dei dati. Questa funzionalità è supportata per i CRITERI chiave del cliente assegnati a singole cassette postali.

Microsoft 365 controlla e convalida il percorso di eliminazione dei dati. Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal.](https://servicetrust.microsoft.com/) Inoltre, Microsoft consiglia i documenti seguenti:

- [Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari in Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerazioni sulla pianificazione dell'uscita da O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

L'eliminazione di Protezione esecuzione programmi multi-carico di lavoro non è supportata per Microsoft 365 customer key. La funzionalità Protezione esecuzione programmi multi-carico di lavoro viene utilizzata per crittografare i dati in più carichi di lavoro tra tutti gli utenti tenant. Se si elimina tale protezione esecuzione programmi, i dati provenienti da più carichi di lavoro diventeranno inaccessibili. Se si decide di uscire completamente Microsoft 365 servizi, è possibile seguire il percorso di eliminazione del tenant per il processo documentato. Informazioni [su come eliminare un tenant in Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocare le chiavi cliente e la chiave di disponibilità per Exchange Online e Skype for Business

Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for Business, si imposta una richiesta di eliminazione dei dati permanente in una protezione esecuzione programmi. In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la funzionalità Protezione esecuzione programmi.

Poiché è possibile eseguire il cmdlet PowerShell solo su una funzionalità Protezione esecuzione programmi alla volta, è consigliabile riassegnare una singola protezione esecuzione programmi a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.

> [!WARNING]
> Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali. Questo processo è destinato solo ai clienti che escno dal servizio.

Per avviare il percorso di eliminazione dei dati, completare la procedura seguente:

1. Rimuovere le autorizzazioni di wrapping e annullamento del wrapping per "O365 Exchange Online" dagli insiemi di credenziali delle chiavi di Azure.

2. Utilizzando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale [nell'organizzazione, connettersi a Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Per ogni protezione esecuzione programmi contenente le cassette postali che si desidera eliminare, eseguire il cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se il comando ha esito negativo, assicurarsi di aver rimosso le autorizzazioni Exchange Online da entrambe le chiavi in Azure Key Vault, come specificato in precedenza in questa attività.Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non sarà più possibile assegnare la funzionalità Protezione esecuzione programmi alle cassette postali.

4. Contattare il supporto Tecnico Microsoft e richiedere l'eDocument di eliminazione dei dati.

    Su richiesta dell'utente, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.

5. Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).

    Una volta ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati che prima elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva, quindi elimina la chiave di disponibilità. Al termine del processo di eliminazione dei dati, i dati sono stati eliminati, non sono accessibili Exchange Online e non sono ripristinabili.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Revocare le chiavi cliente e la chiave di disponibilità per SharePoint online, OneDrive for Business e Teams file

Per avviare il percorso di eliminazione dei dati per SharePoint online, OneDrive for Business e Teams file, completare la procedura seguente:

1. Revocare l'accesso all'insieme di credenziali delle chiavi di Azure. Tutti gli amministratori dell'insieme di credenziali delle chiavi devono accettare di revocare l'accesso.

   Non eliminare Azure Key Vault per SharePoint Online. Gli insiemi di credenziali delle chiavi possono essere condivisi tra SharePoint tenant e dep online.

2. Contattare Microsoft per eliminare la chiave di disponibilità.

    Quando si contatta Microsoft per eliminare la chiave di disponibilità, verrà inviato un documento legale. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata dell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.

3. Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).

   Una volta ricevuto il documento legale, Microsoft esegue cmdlet per attivare l'eliminazione dei dati che esegue l'eliminazione crittografica della chiave tenant, della chiave del sito e di tutte le singole chiavi per documento, interrompendo irrevocabilmente la gerarchia delle chiavi. Al termine dei cmdlet di eliminazione dei dati, i dati sono stati eliminati.

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Configurare il codice "Customer Key"](customer-key-set-up.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)