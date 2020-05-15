---
title: Eliminare gli elementi nella cassetta postale del cloud nella cartella elementi ripristinabili-Guida per gli amministratori
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Per gli amministratori: eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa legale. Si tratta di un modo efficace per eliminare i dati che sono stati inavvertitamente riversati in Microsoft 365.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223c589d191eef14662b7e19aa5ed113db9ff3b2
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232060"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa-Guida per l'amministratore

La cartella elementi ripristinabili per una cassetta postale di Exchange Online esiste per proteggere da eliminazioni accidentali o dannose. Viene inoltre utilizzato per archiviare gli elementi conservati e accessibili tramite le funzionalità di conformità, ad esempio i blocchi e le ricerche di eDiscovery. Tuttavia, in alcune situazioni le organizzazioni potrebbero avere dati che sono stati inavvertitamente conservati nella cartella elementi ripristinabili che devono essere eliminati. Ad esempio, un utente potrebbe inconsapevolmente inviare o inoltrare un messaggio di posta elettronica contenente informazioni riservate o informazioni che potrebbero avere gravi conseguenze per le aziende. Anche se il messaggio è stato eliminato definitivamente, potrebbe essere conservato per un periodo di tempo indefinito perché nella cassetta postale è stata inserita una conservazione legale. Questo scenario è noto come versamento dei dati poiché i dati sono stati inavvertitamente riversati in Office 365. In questi casi, è possibile eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa con una delle diverse funzionalità di archiviazione di Office 365. Questi tipi di esenzioni includono le esenzioni per controversia legale, le esenzioni sul posto, le esenzioni eDiscovery e i criteri di conservazione creati nel centro sicurezza e conformità di Office 365 o Microsoft 365.
  
 In questo articolo viene illustrato come eliminare gli elementi dalla cartella elementi ripristinabili per le cassette postali basate sul cloud che sono in attesa. Questa procedura comporta la disattivazione dell'accesso alla cassetta postale e la disabilitazione del ripristino di un singolo elemento, la disattivazione dell'Assistente cartelle gestite dall'elaborazione della cassetta postale, la rimozione temporanea del blocco, l'eliminazione degli elementi dalla cartella elementi ripristinabili e la restituzione della cassetta postale alla configurazione precedente. Ecco il processo: 
  
[Passaggio 1: raccogliere informazioni sulla cassetta postale](#step-1-collect-information-about-the-mailbox)

[Passaggio 2: preparare la cassetta postale](#step-2-prepare-the-mailbox)

[Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale](#step-3-remove-all-holds-from-the-mailbox)

[Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale](#step-4-remove-the-delay-hold-from-the-mailbox)

[Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili](#step-5-delete-items-in-the-recoverable-items-folder)

[Passaggio 6: ripristinare lo stato precedente della cassetta postale](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Le procedure descritte in questo articolo determinano l'eliminazione definitiva (eliminata) dei dati da una cassetta postale di Exchange Online. Questo significa che i messaggi eliminati dalla cartella elementi ripristinabili non possono essere recuperati e non saranno disponibili per la ricerca legale o per altri scopi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che è stata messa in attesa nell'ambito di un blocco per controversia legale, archiviazione sul posto, blocco di eDiscovery o criterio di conservazione creato nel centro sicurezza e conformità, consultare la gestione dei record o i servizi legali prima di rimuovere il blocco. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un evento di perdita dei dati ha la priorità. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per creare ed eseguire una ricerca di contenuto, è necessario essere un membro del gruppo di ruoli di gestione di eDiscovery o disporre del ruolo di gestione della ricerca di conformità. Per eliminare i messaggi, è necessario essere un membro del gruppo di ruoli Gestione organizzazione o disporre del ruolo di gestione di ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Ciò è dovuto al fatto che non è possibile riapplicare un blocco o un criterio di conservazione a una cassetta postale inattiva dopo averlo rimosso. Quando si rimuove un'esenzione da una cassetta postale inattiva, viene modificata in una normale cassetta postale eliminata temporaneamente e viene eliminata definitivamente dall'organizzazione dopo che è stata elaborata dall'Assistente cartelle gestite.

- Non è possibile eseguire questa procedura per una cassetta postale che è stata assegnata a un criterio di conservazione bloccato con un blocco di conservazione. Ciò è dovuto al fatto che un blocco di conservazione impedisce di rimuovere o escludere la cassetta postale dal criterio di conservazione e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sul blocco dei criteri di conservazione, vedere [use Preservation Lock to conforme ai requisiti normativi](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).

- Se non si dispone di una cassetta postale in attesa (o se non è stato abilitato il ripristino di un singolo elemento), è possibile eliminare gli elementi dalla cartella elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Passaggio 1: raccogliere informazioni sulla cassetta postale

Questo primo passaggio consiste nel raccogliere le proprietà selezionate dalla cassetta postale di destinazione che influenzerà questa procedura. Assicurarsi di annotare queste impostazioni o salvarle in un file di testo, perché si modificheranno alcune di queste proprietà e quindi si tornerà ai valori originali del passaggio 6, dopo aver eliminato gli elementi dalla cartella elementi ripristinabili. Ecco un elenco delle proprietà della cassetta postale che è necessario raccogliere.
  
- *SingleItemRecoveryEnabled* e *RetainDeletedItemsFor*. Se necessario, è possibile disabilitare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3. 

- *LitigationHoldEnabled* e *InPlaceHolds*. È necessario identificare tutti gli appigli posizionati nella cassetta postale in modo da poterli rimuovere temporaneamente nel passaggio 3. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale. 

Inoltre, è necessario ottenere le impostazioni di accesso client delle cassette postali in modo da poterle disabilitare temporaneamente in modo che il proprietario (o altri utenti) non riesca ad accedere alla cassetta postale durante questa procedura. Infine, è possibile ottenere la dimensione corrente e il numero di elementi nella cartella elementi ripristinabili. Dopo aver eliminato gli elementi nella cartella elementi ripristinabili nel passaggio 5, è possibile utilizzare queste informazioni per verificare che gli elementi siano stati rimossi.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e una password per un account amministratore a cui sono stati assegnati i ruoli di gestione idonei in Exchange Online. 
    
2. Eseguire il seguente comando per ottenere informazioni sul ripristino di un singolo elemento e sul periodo di conservazione degli elementi eliminati.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se il ripristino di un singolo elemento è abilitato, è necessario disattivarlo nel passaggio 2. Se il periodo di conservazione degli elementi eliminati non è impostato per 30 giorni (il valore massimo in Exchange Online), è possibile aumentarlo nel passaggio 2. 
    
3. Eseguire il seguente comando per ottenere le impostazioni di accesso alle cassette postali per la cassetta postale. 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Nel passaggio 2 vengono disattivati tutti questi metodi di accesso.
    
4. Eseguire il seguente comando per ottenere informazioni sulle esenzioni e sui criteri di conservazione applicati alla cassetta postale.
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta. 
  
5. Eseguire il seguente comando per ottenere informazioni su tutti i criteri di conservazione a livello dell'organizzazione. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   Se l'organizzazione dispone di criteri di conservazione a livello di organizzazione, sarà necessario escludere la cassetta postale da questi criteri nel passaggio 3.

   > [!TIP]
    > Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta. 
  
6. Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se la cassetta postale di archiviazione dell'utente è abilitata, eseguire il comando riportato di seguito per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Quando si eliminano gli elementi nel passaggio 5, è possibile scegliere di eliminare o non eliminare gli elementi nella cartella elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente. Se per la cassetta postale è abilitata l'archiviazione con espansione automatica, gli elementi in una cassetta postale di archiviazione ausiliaria non verranno eliminati.
  
## <a name="step-2-prepare-the-mailbox"></a>Passaggio 2: preparare la cassetta postale

Dopo aver raccolto e salvato le informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le attività seguenti: 
  
- **Disabilitare l'accesso client alla cassetta postale** , in modo che il proprietario della cassetta postale non possa accedere alla propria cassetta postale e apportare le modifiche ai dati della cassetta postale durante questa procedura. 
    
- **Aumentare il periodo di conservazione degli elementi eliminati** fino a 30 giorni (il valore massimo in Exchange Online), in modo che gli elementi non vengano eliminati dalla cartella elemento ripristinabile prima di poterli eliminare nel passaggio 5. 
    
- **Disabilitare il ripristino di un singolo elemento** in modo che gli elementi non vengano conservati (per la durata del periodo di conservazione degli elementi eliminati) dopo averli eliminati dalla cartella elementi ripristinabili nel passaggio 5. 
    
- **Disabilitare l'Assistente cartelle gestite** in modo che non elabori la cassetta postale e mantenga gli elementi eliminati nel passaggio 5. 
    
Eseguire le operazioni seguenti in PowerShell di Exchange Online.
  
1. Eseguire il seguente comando per disabilitare tutti gli accessi client alla cassetta postale. La sintassi del comando presuppone che tutti i metodi di accesso client siano stati abilitati nella cassetta postale.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Per disabilitare tutti i metodi di accesso client alla cassetta postale, potrebbero essere necessari fino a 60 minuti. Si noti che la disabilitazione di questi metodi di accesso non disconnetterà il proprietario della cassetta postale a cui è attualmente connesso. Se il proprietario non ha eseguito l'accesso, non sarà in grado di accedere alla propria cassetta postale dopo che questi metodi di accesso sono stati disabilitati. 
  
2. Eseguire il seguente comando per aumentare il periodo di conservazione degli elementi eliminati per un massimo di 30 giorni. Si presuppone che l'impostazione corrente sia inferiore a 30 giorni. 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Per disabilitare il ripristino di un singolo elemento, eseguire il comando riportato di seguito.
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Per disabilitare il ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti. Non eliminare gli elementi nella cartella elementi ripristinabili fino a quando non è trascorso questo periodo. 
  
4. Eseguire il seguente comando per evitare che l'Assistente cartelle gestite esegua l'elaborazione della cassetta postale. Come spiegato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se un criterio di conservazione con un blocco di conservazione non viene applicato alla cassetta postale. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale

L'ultimo passaggio prima di poter eliminare gli elementi dalla cartella elementi ripristinabili consiste nel rimuovere tutte le esenzioni (identificate nel passaggio 1) inserite nella cassetta postale. Tutte le esenzioni devono essere rimosse in modo che gli elementi non vengano conservati dopo averli eliminati dalla cartella elementi ripristinabili. Nelle sezioni seguenti sono contenute informazioni sulla rimozione di diversi tipi di esenzioni su una cassetta postale. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale. Per ulteriori informazioni, vedere [come identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Come indicato in precedenza, consultare la gestione dei record o i reparti giuridici prima di rimuovere un'esenzione da una cassetta postale. 
  
 ### <a name="litigation-hold"></a>Conservazione in caso di dispute
  
Eseguire il seguente comando in Exchange Online PowerShell per rimuovere un blocco per controversia legale dalla cassetta postale.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Analogamente alla disattivazione dei metodi di accesso client e del ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti per rimuovere il blocco per controversia legale. Non eliminare gli elementi dalla cartella elementi ripristinabili fino a quando non è trascorso questo periodo. 
  
 ### <a name="in-place-hold"></a>Blocco sul posto
  
Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco sul posto applicato alla cassetta postale. Utilizzare il GUID per il blocco sul posto identificato nel passaggio 1. 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Dopo aver identificato il blocco sul posto, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [Creare o rimuovere un'archiviazione sul posto](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>Criteri di conservazione applicati a cassette postali specifiche
  
Per identificare il criterio di conservazione applicato alla cassetta postale, eseguire il comando riportato di seguito in [sicurezza & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) . Utilizzare il GUID (escluso il `mbx` `skp` prefisso o) per i criteri di conservazione identificati nel passaggio 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Dopo aver identificato il criterio di conservazione, passare alla **Information governance** \> pagina **conservazione** delle informazioni sulla sicurezza nel centro protezione & conformità, modificare i criteri di conservazione identificati nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di conservazione. 
  
 ### <a name="organization-wide-retention-policies"></a>Criteri di conservazione a livello dell'organizzazione
  
I criteri di conservazione a livello di organizzazione e di Exchange vengono applicati a tutte le cassette postali dell'organizzazione. Vengono applicati a livello di organizzazione (non a livello di cassetta postale) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Per identificare i criteri di conservazione a livello di organizzazione, eseguire il comando riportato di seguito in [PowerShell per Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=627084) . Utilizzare il GUID (escluso il `mbx` prefisso) per i criteri di conservazione a livello dell'organizzazione identificati nel passaggio 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Dopo aver identificato i criteri di conservazione a livello dell'organizzazione, passare alla pagina conservazione delle **informazioni** sulla \> **Retention** sicurezza nel centro protezione & conformità, modificare ogni criterio di conservazione a livello di organizzazione identificato nel passaggio precedente e aggiungere la cassetta postale all'elenco dei destinatari esclusi. In questo modo, la cassetta postale dell'utente verrà rimossa dal criterio di conservazione. 

### <a name="retention-labels"></a>Etichette di conservazione

Ogni volta che un utente applica un'etichetta configurata per mantenere il contenuto o mantenere e quindi eliminare il contenuto in una cartella o un elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* viene impostata su **true**. In questo caso, la cassetta postale viene considerata attiva, come se fosse stata messa in blocco per controversia legale o assegnata a un criterio di conservazione.

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il comando seguente in PowerShell di Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Dopo aver identificato che una cassetta postale è in attesa perché viene applicata un'etichetta di conservazione a una cartella o a un elemento, è possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare gli elementi contrassegnati utilizzando la condizione di ricerca di ComplianceTag. Per ulteriori informazioni, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Per ulteriori informazioni sulle etichette, vedere [Panoramica delle etichette](labels.md).

 ### <a name="ediscovery-holds"></a>eDiscovery contiene
  
Per identificare il blocco associato a un caso di eDiscovery (denominato *eDiscovery*holds) applicato alla cassetta postale, eseguire i comandi seguenti in [PowerShell Center Security & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) . Utilizzare il GUID (escluso il `UniH` prefisso) per il blocco eDiscovery identificato nel passaggio 1. Nel secondo comando viene visualizzato il nome del caso di eDiscovery a cui è associato il blocco. il terzo comando Visualizza il nome dell'esenzione. 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Dopo aver identificato il nome del caso di eDiscovery e il blocco, passare alla pagina **eDiscovery** \> **eDiscovery** nel centro conformità, aprire il caso e rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni sull'identificazione di eDiscovery holds, vedere la sezione "eDiscovery holds" in [How to identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* o *DelayReleaseHoldApplied* è impostato su **true**. Questo problema si verifica quando l'Assistente cartelle gestite elabora la cassetta postale e rileva che è stata rimossa un'esenzione. Si tratta di un *blocco di ritardo* che indica che la rimozione effettiva del blocco viene posticipata di 30 giorni per evitare che i dati vengano eliminati definitivamente dalla cassetta postale. Lo scopo di un blocco di ritardo consiste nell'assegnare agli amministratori la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un'esenzione.  Quando viene immessa una conservazione per la cassetta postale, la cassetta postale è ancora considerata attiva per una durata illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, scade il ritardo e Microsoft 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* su **false**) in modo che il blocco venga rimosso. Per ulteriori informazioni su un blocco di ritardo, vedere la sezione "gestione delle cassette postali per il ritardo" in [come identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Prima di poter eliminare gli elementi nel passaggio 5, è necessario rimuovere un blocco di ritardo dalla cassetta postale. Per prima cosa, determinare se il blocco di ritardo viene applicato alla cassetta postale eseguendo il comando seguente in PowerShell di Exchange Online:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Se il valore della proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* è impostato su **false**, nella cassetta postale non è stato applicato un blocco di ritardo. È possibile passare al passaggio 5 ed eliminare gli elementi nella cartella elementi ripristinabili.

Se il valore della proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* è impostato su **true**, eseguire uno dei comandi seguenti per rimuovere il blocco di ritardo:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oppure

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Per utilizzare il parametro *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied* , è necessario che sia assegnato il ruolo di blocco legale in Exchange Online.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili

A questo punto si è pronti per eliminare gli elementi nella cartella elementi ripristinabili utilizzando i cmdlet [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch) e [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) nel centro sicurezza & Compliance. 

Per eseguire questa operazione, vedere [cercare ed eliminare i messaggi di posta elettronica](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

### <a name="verify-that-items-were-deleted"></a>Verificare che gli elementi siano stati eliminati

Per verificare la corretta eliminazione degli elementi dalla cartella elementi ripristinabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** in PowerShell di Exchange Online per controllare la dimensione e il numero di elementi nella cartella elementi ripristinabili. È possibile confrontare queste statistiche con quelle raccolte nel passaggio 1. 
  
Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente. 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Eseguire il seguente comando per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente. 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Passaggio 6: ripristinare lo stato precedente della cassetta postale

Il passaggio finale consiste nel ripristinare la configurazione precedente della cassetta postale. Questo significa reimpostare le proprietà modificate nel passaggio 2 e riapplicare le esenzioni rimosse al passaggio 3. Ciò include:
  
- Modifica del periodo di conservazione degli elementi eliminati sul valore precedente. In alternativa, è possibile lasciare questo set a 30 giorni, ovvero il valore massimo in Exchange Online.
    
- Riattivazione del ripristino di un singolo elemento.
    
- Riattivare i metodi di accesso client in modo che il proprietario possa accedere alla propria cassetta postale.
    
- Riapplicare le esenzioni e i criteri di conservazione rimossi.
    
- Riattivare l'Assistente cartelle gestite per elaborare la cassetta postale.
    
> [!IMPORTANT]
> È consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione (e verificare che sia sul posto) prima di riabilitare l'Assistente cartelle gestite per elaborare la cassetta postale. 
  
Eseguire i passaggi seguenti (nella sequenza specificata) in PowerShell di Exchange Online.
  
1. Eseguire il seguente comando per ripristinare il valore originale del periodo di conservazione degli elementi eliminati. Si presuppone che l'impostazione precedente sia inferiore a 30 giorni. ad esempio, 14 giorni. 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Eseguire il seguente comando per riattivare il ripristino di un singolo elemento.
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Eseguire il seguente comando per riabilitare tutti i metodi di accesso client alla cassetta postale.
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Riapplicare le esenzioni rimosse nel passaggio 3. A seconda del tipo di blocco, utilizzare una delle procedure seguenti.
    
    **Conservazione per controversia legale**
    
    Eseguire il seguente comando per riattivare un blocco per controversia legale per la cassetta postale.
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    Utilizzare EAC (o Exchange Online PowerShell) per aggiungere di nuovo la cassetta postale all'archiviazione sul posto. 
    
    **Criteri di conservazione applicati a cassette postali specifiche**
    
    Utilizzare il Centro sicurezza & conformità per aggiungere di nuovo la cassetta postale al criterio di conservazione. Passare alla pagina conservazione della **governance delle informazioni** \> **Retention** nel centro sicurezza & conformità, modificare il criterio di conservazione e aggiungere di nuovo la cassetta postale all'elenco dei destinatari a cui è applicato il criterio di conservazione. 
    
    **Criteri di conservazione a livello dell'organizzazione**
    
    Se è stato rimosso un criterio di conservazione a livello di organizzazione o a livello di Exchange, escluderlo dal criterio, utilizzare il Centro sicurezza & conformità per rimuovere la cassetta postale dall'elenco degli utenti esclusi. Passare alla pagina conservazione delle **informazioni di gestione** \> **Retention** nel centro sicurezza & conformità, modificare il criterio di conservazione a livello dell'organizzazione e rimuovere la cassetta postale dall'elenco dei destinatari esclusi. In questo modo verrà riapplicato il criterio di conservazione alla cassetta postale dell'utente. 
    
    **blocco del caso di eDiscovery**
    
    Utilizzare il Centro sicurezza & conformità per aggiungere la cassetta postale che è associata a un caso di eDiscovery. Passare alla pagina **eDiscovery** \> **eDiscovery** , aprire il caso e aggiungere di nuovo la cassetta postale all'esenzione. 
    
5. Eseguire il seguente comando per consentire all'Assistente cartelle gestite di elaborare di nuovo la cassetta postale. Come indicato in precedenza, è consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione e verificare che sia sul posto, prima di abilitare di nuovo l'Assistente cartelle gestite. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Per verificare che la cassetta postale sia stata ripristinata alla configurazione precedente, è possibile eseguire i comandi seguenti e quindi confrontare le impostazioni con quelle raccolte nel passaggio 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Ulteriori informazioni

Di seguito viene riportata una tabella in cui viene descritto come identificare diversi tipi di esenzioni in base ai valori della proprietà *InPlaceHolds* quando si eseguono i cmdlet **Get-Mailbox** o **Get-OrganizationConfig** . Per informazioni più dettagliate, vedere [How to identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Come spiegato in precedenza, è necessario rimuovere tutte le esenzioni e i criteri di conservazione da una cassetta postale prima di poter eliminare correttamente gli elementi nella cartella elementi ripristinabili. 
  
|**Tipo di blocco**|**Valore di esempio**|**Come identificare il blocco**|
|:-----|:-----|:-----|
|Blocco per controversia legale  <br/> | `True` <br/> |La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.  <br/> |
|Blocco sul posto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La proprietà *InPlaceHolds* contiene il GUID del blocco sul posto applicato alla cassetta postale. È possibile indicare che si tratta di un blocco sul posto poiché il GUID non inizia con un prefisso.  <br/> È possibile utilizzare il `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando in PowerShell di Exchange Online per ottenere informazioni sul blocco sul posto sulla cassetta postale.  <br/> |
| Criteri di conservazione nel centro sicurezza & Compliance applicato a cassette postali specifiche  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oppure  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Quando si esegue il cmdlet **Get-Mailbox** , la proprietà *InPlaceHolds* contiene anche i GUID dei criteri di conservazione applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia con il `mbx` prefisso. Se il GUID del criterio di conservazione inizia con il `skp` prefisso, indica che il criterio di conservazione viene applicato alle conversazioni di Skype for business.  <br/> Per identificare i criteri di conservazione applicati alla cassetta postale, eseguire il comando seguente in PowerShell per il Centro sicurezza & Compliance: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Assicurarsi di rimuovere il prefisso  `mbx` o  `skp` quando si esegue questo comando.  <br/> |
|Criteri di conservazione a livello di organizzazione nel centro sicurezza & Compliance  <br/> |Nessun valore  <br/> oppure  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica che la cassetta postale è esclusa da un criterio a livello di organizzazione)  <br/> |Anche se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è possibile che siano presenti almeno uno o più criteri di conservazione a livello di organizzazione applicati alla cassetta postale.  <br/> Per verificarlo, è possibile eseguire il `Get-OrganizationConfig | FL InPlaceHolds` comando in Exchange Online PowerShell per ottenere un elenco dei GUID per i criteri di conservazione a livello dell'organizzazione. Il GUID per i criteri di conservazione a livello dell'organizzazione applicati alle cassette postali di Exchange inizia con il `mbx` prefisso, ad esempio `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Per identificare i criteri di conservazione a livello dell'organizzazione applicati alla cassetta postale, eseguire il comando seguente in PowerShell per il Centro sicurezza & Compliance: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Se una cassetta postale è esclusa da un criterio di conservazione a livello dell'organizzazione, il GUID del criterio di conservazione viene visualizzato nella proprietà *InPlaceHolds* della cassetta postale dell'utente quando si esegue il cmdlet **Get-Mailbox** . viene identificato dal prefisso, `-mbx` ad esempio`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|blocco del caso di eDiscovery nel centro sicurezza & Compliance  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La proprietà *InPlaceHolds* contiene inoltre il GUID di qualsiasi blocco associato a un caso di eDiscovery nel centro sicurezza & Compliance che potrebbe essere posizionato sulla cassetta postale. È possibile stabilire che si tratta di un blocco caso eDiscovery perché il GUID inizia con il prefisso  `UniH`.  <br/> È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in PowerShell per la sicurezza & Compliance Center per ottenere informazioni sul caso di eDiscovery a cui è associato il blocco sulla cassetta postale. Ad esempio, è possibile eseguire il comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` per visualizzare il nome del blocco del caso che si trova nella cassetta postale. Be sure to remove the  `UniH` quando si esegue questo comando.  <br/><br/> Per identificare il caso di eDiscovery a cui è associato il blocco della cassetta postale, eseguire i comandi seguenti:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


