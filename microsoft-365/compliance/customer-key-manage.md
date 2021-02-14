---
title: Gestire Customer Key
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
description: Dopo aver configurato Customer Key, scopri come gestirla ripristinando le chiavi AKV e gestendo le autorizzazioni e i criteri di crittografia dei dati.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547086"
---
# <a name="manage-customer-key"></a>Gestire Customer Key

Dopo aver configurato Customer Key per Office 365, è possibile gestire le chiavi come descritto in questo articolo. Altre informazioni su Customer Key sono disponibili negli argomenti correlati.

## <a name="restore-azure-key-vault-keys"></a>Ripristinare le chiavi di Azure Key Vault

Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione rescisa. Tutte le chiavi usate con Customer Key devono avere l'eliminazione soft abilitata. L'eliminazione rescisa agisce come un Cestino e consente il ripristino per un massimo di 90 giorni senza la necessità di eseguire il ripristino. Il ripristino deve essere necessario solo in circostanze estreme o insolite, ad esempio in caso di perdita della chiave o dell'insieme di credenziali delle chiavi. Se è necessario ripristinare una chiave da utilizzare con Customer Key, in Azure PowerShell eseguire il cmdlet Restore-AzureKeyVaultKey seguente:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Ad esempio:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se l'insieme di credenziali delle chiavi contiene già una chiave con lo stesso nome, l'operazione di ripristino non riesce. Restore-AzKeyVaultKey ripristina tutte le versioni chiave e tutti i metadati per la chiave, incluso il nome della chiave.
  
## <a name="manage-key-vault-permissions"></a>Gestire le autorizzazioni dell'insieme di credenziali delle chiavi

Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni dell'insieme di credenziali delle chiavi. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team. Per ognuna di queste attività, si userà Azure PowerShell. Per informazioni su Azure PowerShell, vedere [Panoramica di Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)

Per visualizzare le autorizzazioni dell'insieme di credenziali delle chiavi, eseguire Get-AzKeyVault cmdlet.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Ad esempio:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzKeyVaultAccessPolicy seguente:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Ad esempio:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Gestire i criteri di crittografia dei dati (DEP) con Customer Key

Customer Key gestisce i criteri di dep in modo diverso tra i diversi servizi. Ad esempio, è possibile creare un numero diverso di DEP per i diversi servizi.

**Exchange Online e Skype for Business:** È possibile creare fino a 50 DEP. Per istruzioni, vedere Creare un criterio di crittografia dei dati da utilizzare [con Exchange Online e Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

**File di SharePoint Online, OneDrive for Business e Teams:** Protezione esecuzione programmi si applica ai dati in una posizione geografica, detta anche _geo._ Se si usa la funzionalità multi-geo di Office 365, è possibile creare una protezione esecuzione programmi per ogni area geografica. Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi. In genere, si crea Protezione esecuzione programmi quando si configura Customer Key. Per istruzioni, vedere Creare un criterio di crittografia dei dati per ogni posizione geografica di SharePoint Online e [OneDrive for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Visualizzare i dep creati per Exchange Online e Skype for Business

Per visualizzare un elenco di tutti i dep creati per Exchange Online e Skype for Business usando il cmdlet powershell di Get-DataEncryptionPolicy, completare questi passaggi.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Per restituire tutti i criteri di configurazione dell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza alcun parametro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Assegnare una protezione esecuzione programmi prima di eseguire la migrazione di una cassetta postale nel cloud

Quando si assegna Protezione esecuzione programmi, Microsoft 365 crittografa il contenuto della cassetta postale utilizzando protezione esecuzione programmi assegnata durante la migrazione. Questo processo è più efficiente della migrazione della cassetta postale, dell'assegnazione di Protezione esecuzione programmi e quindi dell'attesa della crittografia, che può richiedere ore o probabilmente giorni.

Per assegnare una protezione esecuzione programmi a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in PowerShell di Exchange Online:

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet Set-MailUser seguente.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DataEncryptionPolicyIdParameter* è l'ID di Protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinare la protezione esecuzione programmi assegnata a una cassetta postale

Per determinare la protezione esecuzione programmi assegnata a una cassetta postale, utilizzare Get-MailboxStatistics cmdlet. Il cmdlet restituisce un identificatore univoco (GUID).
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID di Protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics.](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)
  
2. Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo di Protezione esecuzione programmi a cui è assegnata la cassetta postale.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificare che Customer Key abbia completato la crittografia

Indipendentemente dal fatto che sia stata appena eseguita la migrazione di una chiave cliente, che sia stata assegnata una nuova protezione esecuzione programmi o che sia stata eseguita la migrazione di una cassetta postale, seguire i passaggi descritti in questa sezione per assicurarsi che la crittografia sia stata completata.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Verificare che la crittografia sia stata completata per Exchange Online e Skype for Business

La crittografia di una cassetta postale può richiedere del tempo. Si consiglia di attendere 72 ore prima di tentare di convalidare la crittografia dopo la modifica di Protezione esecuzione programmi o la prima volta che si assegna protezione esecuzione programmi a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.

Il tempo necessario per completare gli spostamenti delle cassette postali dipende dalle dimensioni della cassetta postale. Se Customer Key non ha completamente crittografato la cassetta postale dopo 72 ore dal momento in cui si assegna una nuova protezione esecuzione programmi, contattare il supporto tecnico Microsoft per assistenza. Il New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali. Per ulteriori [informazioni, fare](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) riferimento a questo annuncio.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Verificare che la crittografia sia stata completata per i file di SharePoint Online, OneDrive for Business e Teams

Controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy seguente:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

L'output di questo cmdlet include:
  
- URI della chiave primaria.

- URI della chiave secondaria.

- Stato di crittografia per la posizione geografica. Gli stati possibili includono:

  - **Non registrato:** La crittografia customer key non è ancora stata applicata.

  - **Registrazione:** La crittografia customer key è stata applicata e i file sono in fase di crittografia. Se la chiave per la posizione geografica è in corso di registrazione, verranno visualizzate anche informazioni sulla percentuale di siti nella posizione geografica completa, in modo da poter monitorare l'avanzamento della crittografia.

  - **Registrato:** La crittografia customer key è stata applicata e tutti i file in tutti i siti sono stati crittografati.

  - **Rolling:** È in corso un rollio delle chiavi. Se la chiave per la posizione geografica è in esecuzione, verranno visualizzate anche informazioni sulla percentuale di siti che hanno completato l'operazione di roll delle chiavi in modo da poter monitorare lo stato.

## <a name="unassign-a-dep-from-a-mailbox"></a>Annullare l'assegnazione di Protezione esecuzione programmi da una cassetta postale

È possibile annullare l'assegnazione di Protezione esecuzione programmi da una cassetta postale utilizzando il cmdlet Set-mailbox di PowerShell e impostando su `DataEncryptionPolicy` `$NULL` . L'esecuzione di questo cmdlet annulla l'assegnazione di Protezione esecuzione programmi attualmente assegnata e ricryptizza la cassetta postale utilizzando protezione esecuzione programmi associata alle chiavi gestite microsoft predefinite. Non è possibile annullare l'assegnazione di Protezione esecuzione programmi utilizzata dalle chiavi gestite da Microsoft. Se non si desidera utilizzare le chiavi gestite di Microsoft, è possibile assegnare un'altra protezione esecuzione programmi alla cassetta postale.

Per annullare l'assegnazione di Protezione esecuzione programmi da una cassetta postale utilizzando Set-Mailbox cmdlet di PowerShell, completare questi passaggi.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet Set-Mailbox seguente.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati

Puoi controllare la revoca di tutte le chiavi radice, inclusa la chiave di disponibilità. Customer Key fornisce il controllo dell'aspetto della pianificazione dell'uscita dei requisiti normativi. Se decidi di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio elimina la chiave di disponibilità al termine del processo di eliminazione dei dati.

Microsoft 365 controlla e convalida il percorso di eliminazione dei dati. Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal.](https://servicetrust.microsoft.com/) Inoltre, Microsoft consiglia i documenti seguenti:

- [Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari in Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerazioni sulla pianificazione dell'uscita da O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Il percorso di eliminazione dei dati varia leggermente tra i diversi servizi.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocare le chiavi del cliente e la chiave di disponibilità per Exchange Online e Skype for Business

Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for Business, si imposta una richiesta di eliminazione dei dati permanente su protezione esecuzione programmi. In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnato protezione esecuzione programmi.

Poiché è possibile eseguire il cmdlet di PowerShell su un solo servizio Protezione esecuzione programmi alla volta, è consigliabile riassegnare una singola protezione esecuzione programmi a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.

> [!WARNING]
> Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali. Questo processo è destinato solo ai clienti che stanno uscendo dal servizio.

Per avviare il percorso di eliminazione dei dati, completare questi passaggi:

1. Rimuovere le autorizzazioni di wrapping e annullamento del wrapping per "O365 Exchange Online" dagli insiemi di credenziali delle chiavi di Azure.

2. Utilizzando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

3. Per ogni protezione esecuzione programmi contenente le cassette postali che si desidera eliminare, eseguire il cmdlet [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se il comando ha esito negativo, assicurarsi di aver rimosso le autorizzazioni di Exchange Online da entrambe le chiavi in Azure Key Vault come specificato in precedenza in questa attività.Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non sarà più possibile assegnare la funzionalità Protezione esecuzione programmi alle cassette postali.

4. Contattare il supporto tecnico Microsoft e richiedere l'eDocument per l'eliminazione dei dati.

    Su richiesta dell'utente, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata nell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.

5. Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).

    Una volta ricevuto il documento legale, Microsoft esegue cmdlet per attivare l'eliminazione dei dati che prima elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva, quindi elimina la chiave di disponibilità. Una volta completato il processo di eliminazione dei dati, i dati sono stati eliminati, sono inaccessibili a Exchange Online e non sono recuperabili.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Revocare le chiavi dei clienti e la chiave di disponibilità per i file di SharePoint Online, OneDrive for Business e Teams

Per avviare il percorso di eliminazione dei dati per i file di SharePoint Online, OneDrive for Business e Teams, eseguire la procedura seguente:

1. Revocare l'accesso all'Insieme di credenziali delle chiavi di Azure. Tutti gli amministratori dell'insieme di credenziali delle chiavi devono accettare di revocare l'accesso.

   Non eliminare Azure Key Vault per SharePoint Online. Gli insiemi di credenziali delle chiavi possono essere condivisi tra diversi tenant e dep di SharePoint Online.

2. Contattare Microsoft per eliminare la chiave di disponibilità.

    Quando si contatta Microsoft per eliminare la chiave di disponibilità, verrà inviato un documento legale. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta FastTrack durante l'onboarding deve firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata nell'azienda che è legalmente autorizzata a firmare i documenti per conto dell'organizzazione.

3. Dopo che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (in genere tramite una firma eDoc).

   Una volta ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati che esegue l'eliminazione di crittografia della chiave del tenant, della chiave del sito e di tutte le singole chiavi per documento, interrompendo irrevocabilmente la gerarchia delle chiavi. Una volta completati i cmdlet di eliminazione dei dati, i dati sono stati eliminati.

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Configurare Customer Key](customer-key-set-up.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)
