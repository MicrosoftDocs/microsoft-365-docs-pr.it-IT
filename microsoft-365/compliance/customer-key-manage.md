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
# <a name="manage-customer-key"></a>Gestione della chiave del cliente

Dopo aver configurato Customer Key per Office 365, è possibile gestire le chiavi come descritto in questo articolo. Per ulteriori informazioni, vedere Key Customer negli argomenti correlati.

## <a name="restore-azure-key-vault-keys"></a>Ripristinare le chiavi del Vault Key di Azure

Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite da soft delete. Tutte le chiavi utilizzate con la chiave Customer devono essere abilitate per l'eliminazione temporanea. Delete Soft agisce come un cestino e consente il ripristino per un massimo di 90 giorni senza che sia necessario ripristinarlo. Il ripristino deve essere necessario solo in caso di circostanze estreme o inusuali, ad esempio se la chiave o la chiave del Vault è persa. Se è necessario ripristinare una chiave da utilizzare con la chiave Customer, in Azure PowerShell, eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Ad esempio:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se il Vault della chiave contiene già un tasto con lo stesso nome, l'operazione di ripristino avrà esito negativo. Restore-AzKeyVaultKey Ripristina tutte le versioni principali e tutti i metadati per la chiave, incluso il nome della chiave.
  
## <a name="manage-key-vault-permissions"></a>Gestire le autorizzazioni del Vault Key

Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, di rimuovere le autorizzazioni chiave del Vault. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team. Per ognuna di queste attività, si utilizzerà Azure PowerShell. Per informazioni su Azure PowerShell, vedere [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).

Per visualizzare le autorizzazioni per il Vault chiave, eseguire il cmdlet Get-AzKeyVault.

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Gestire i criteri di crittografia dei dati con la chiave del cliente

La chiave Customer gestisce il DEPs in modo diverso tra i diversi servizi. Ad esempio, è possibile creare un numero diverso di DEPs per i diversi servizi.

**Exchange Online e Skype for business:** È possibile creare fino a 50 DEPs. Per istruzioni, vedere [creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**File di SharePoint Online, OneDrive for business e teams:** Una DEP si applica ai dati in una posizione geografica, denominata anche _Geo_. Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo. Se non si utilizza multi-Geo, è possibile creare una DEP. In genere, si crea la funzionalità DEP quando si configura la chiave del cliente. Per istruzioni, vedere [creare un criterio di crittografia dei dati (DEP, Data Encryption Policy) per ogni server di SharePoint Online e OneDrive for business Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Visualizzare il DEPs creato per Exchange Online e Skype for business

Per visualizzare un elenco di tutti i DEPs creati per Exchange Online e Skype for business utilizzando il cmdlet Get-DataEncryptionPolicy di PowerShell, eseguire la procedura seguente.

1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Per restituire tutti i DEPs nell'organizzazione, eseguire il cmdlet Get-DataEncryptionPolicy senza parametri.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Per ulteriori informazioni sul cmdlet Get-DataEncryptionPolicy, vedere [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Assegnare una DEP prima di eseguire la migrazione di una cassetta postale nel cloud

Quando si assegna la funzionalità DEP, Microsoft 365 crittografa il contenuto della cassetta postale utilizzando la funzionalità DEP assegnata durante la migrazione. Questo processo è più efficiente della migrazione della cassetta postale, assegnando la funzionalità DEP e quindi in attesa che venga eseguita la crittografia, che può richiedere ore o eventualmente giorni.

Per assegnare una DEP a una cassetta postale prima di eseguirne la migrazione a Office 365, eseguire il cmdlet Set-MailUser in PowerShell di Exchange Online:

1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e *DATAENCRYPTIONPOLICYIDPARAMETER* è l'ID della funzionalità di protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinare la funzionalità DEP assegnata a una cassetta postale

Per determinare la funzionalità DEP assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce un identificatore univoco (GUID).
  
1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale e DataEncryptionPolicyID restituisce il GUID della funzionalità di protezione esecuzione programmi. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).
  
2. Eseguire il cmdlet Get-DataEncryptionPolicy per trovare il nome descrittivo della funzionalità DEP a cui è assegnata la cassetta postale.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificare che la chiave del cliente abbia completato la crittografia

Se è stata appena eseguita una chiave del cliente, è stata assegnata una nuova DEP o ha eseguito la migrazione di una cassetta postale, attenersi alla procedura descritta in questa sezione per assicurarsi che la crittografia venga completata.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Verifica del completamento della crittografia per Exchange Online e Skype for business

La crittografia di una cassetta postale può richiedere del tempo. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.

Il tempo necessario per completare gli spostamenti delle cassette postali dipende dalle dimensioni della cassetta postale. Se la chiave del cliente non ha crittografato completamente la cassetta postale dopo 72 ore dal momento in cui viene assegnata una nuova protezione esecuzione programmi, contattare il supporto tecnico Microsoft per assistenza. Il cmdlet New-MoveRequest non è più disponibile per gli spostamenti delle cassette postali locali. Per ulteriori informazioni, fare riferimento a [questo annuncio](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) .

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Verifica del completamento della crittografia per i file di SharePoint Online, OneDrive for business e teams

Controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

L'output di questo cmdlet include:
  
- URI della chiave primaria.

- URI del tasto secondario.

- Lo stato di crittografia per il Geo. Gli stati possibili includono:

  - Non **registrato:** La crittografia a chiave del cliente non è stata ancora applicata.

  - **Registrazione:** È stata applicata la crittografia a chiave del cliente e i file sono in fase di crittografazione. Se si sta registrando la chiave per il Geo, verranno visualizzate anche informazioni sulla percentuale di siti in Geo che sono stati completati in modo da poter monitorare lo stato della crittografia.

  - **Registrato:** È stata applicata la crittografia a chiave del cliente e tutti i file in tutti i siti sono stati crittografati.

  - **Rolling:** È in corso un roll Key. Se la chiave per il servizio Geo è in corso, verranno visualizzate anche informazioni su quale percentuale di siti è stata completata l'operazione di roll Key in modo da poter monitorare lo stato di avanzamento.

## <a name="unassign-a-dep-from-a-mailbox"></a>Annullamento dell'assegnazione di una funzionalità di protezione da una cassetta postale

Per annullare l'assegnazione di una funzionalità di protezione esecuzione programmi da una cassetta postale, utilizzare il cmdlet Set-Mailbox PowerShell e impostare `DataEncryptionPolicy` su `$NULL` . L'esecuzione di questo cmdlet Annulla l'assegnazione della funzionalità DEP correntemente assegnata e la riesegue la crittografia della cassetta postale utilizzando la funzionalità DEP associata alle chiavi gestite Microsoft predefinite. Non è possibile annullare l'assegnazione della funzionalità DEP utilizzata dalle chiavi gestite Microsoft. Se non si desidera utilizzare le chiavi gestite Microsoft, è possibile assegnare un altro DEP alla cassetta postale.

Per annullare l'assegnazione di DEP da una cassetta postale utilizzando il cmdlet Set-Mailbox PowerShell, eseguire la procedura seguente.

1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocare le chiavi e avviare il processo del percorso di eliminazione dei dati

È possibile controllare la revoca di tutte le chiavi radice incluso il tasto disponibilità. La chiave del cliente fornisce il controllo dell'aspetto di pianificazione dell'uscita dei requisiti normativi. Se si decide di revocare le chiavi per eliminare i dati e uscire dal servizio, il servizio eliminerà la chiave di disponibilità dopo il completamento del processo di eliminazione dei dati.

Microsoft 365 verifica e convalida il percorso di eliminazione dei dati. Per ulteriori informazioni, vedere il report SSAE 18 SOC 2 disponibile nel [Service Trust Portal](https://servicetrust.microsoft.com/). Microsoft consiglia inoltre i seguenti documenti:

- [Guida alla valutazione dei rischi e alla conformità per gli istituti finanziari nel cloud Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerazioni sulla pianificazione dell'uscita di O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Il percorso di eliminazione dei dati differisce leggermente tra i diversi servizi.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocare le chiavi dei clienti e la chiave di disponibilità per Exchange Online e Skype for business

Quando si avvia il percorso di eliminazione dei dati per Exchange Online e Skype for business, è possibile impostare una richiesta di eliminazione dei dati permanenti su una funzionalità di protezione esecuzione programmi. In questo modo vengono eliminati definitivamente i dati crittografati all'interno delle cassette postali a cui è assegnata la DEP.

Poiché è possibile eseguire solo il cmdlet di PowerShell su una DEP alla volta, valutare la possibilità di riassegnare una singola funzionalità DEP a tutte le cassette postali prima di avviare il percorso di eliminazione dei dati.

> [!WARNING]
> Non utilizzare il percorso di eliminazione dei dati per eliminare un sottoinsieme delle cassette postali. Questo processo è destinato solo ai clienti che sono in uscita dal servizio.

Per avviare il percorso di eliminazione dei dati, eseguire la procedura seguente:

1. Rimuovere le autorizzazioni wrap e unwrap per "O365 Exchange Online" dai Vault delle chiavi di Azure.

2. Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

3. Per ogni DEP che contiene le cassette postali che si desidera eliminare, eseguire il cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) come indicato di seguito.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se il comando ha esito negativo, verificare di aver rimosso le autorizzazioni di Exchange Online da entrambe le chiavi in Azure Key Vault come specificato in precedenza in questa attività.Dopo aver impostato l'opzione PermanentDataPurgeRequested utilizzando il cmdlet Set-DataEncryptionPolicy, non è più possibile assegnare questa funzionalità DEP alle cassette postali.

4. Contattare il supporto tecnico Microsoft e richiedere l'eliminazione dei dati eDocument.

    Su richiesta, Microsoft invia un documento legale per confermare e autorizzare l'eliminazione dei dati. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda legalmente autorizzata a firmare i documenti per conto dell'organizzazione.

5. Una volta che il rappresentante ha firmato il documento legale, restituirlo a Microsoft (di solito tramite una firma eDoc).

    Dopo che Microsoft ha ricevuto il documento legale, Microsoft esegue i cmdlet per attivare l'eliminazione dei dati, che prima Elimina il criterio, contrassegna le cassette postali per l'eliminazione definitiva e quindi Elimina il codice di disponibilità. Dopo il completamento del processo di eliminazione dei dati, i dati sono stati eliminati, sono inaccessibili per Exchange Online e non sono recuperabili.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Revocare le chiavi dei clienti e la chiave di disponibilità per i file di SharePoint Online, OneDrive for business e teams

Per avviare il percorso di eliminazione dei dati per i file di SharePoint Online, OneDrive for business e teams, eseguire la procedura seguente:

1. Revocare l'accesso all'archivio delle chiavi di Azure. Tutti gli amministratori di Key Vault devono accettare di revocare l'accesso.

   Non è possibile eliminare l'archiviazione delle chiavi di Azure per SharePoint Online. I Vault chiave possono essere condivisi tra più tenant e DEPs di SharePoint Online.

2. Per eliminare il codice di disponibilità, contattare Microsoft.

    Quando si contatta Microsoft per eliminare la chiave di disponibilità, è possibile inviare un documento legale. La persona dell'organizzazione che ha effettuato l'iscrizione come responsabile approvazione nell'offerta di FastTrack durante l'onboarding ha bisogno di firmare questo documento. In genere, si tratta di un dirigente o di un'altra persona designata nella propria azienda che è legalmente autorizzata a firmare la documentazione per conto dell'organizzazione.

3. Una volta che il rappresentante firmerà il documento legale, lo restituirà a Microsoft (di solito tramite una firma eDoc).

   Dopo la ricezione del documento legale da parte di Microsoft, vengono eseguiti i cmdlet per attivare l'eliminazione dei dati, che consente di eliminare la chiave tenant, la chiave del sito e tutti i singoli tasti per documento, infrangendo irrevocabilmente la gerarchia di chiavi. Dopo aver completato i cmdlet per l'eliminazione dei dati, i dati sono stati eliminati.

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con la chiave del cliente](customer-key-overview.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Configurare la chiave del cliente](customer-key-set-up.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)
