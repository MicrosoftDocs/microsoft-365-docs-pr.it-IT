---
title: Eliminare gli elementi nella cartella Elementi ripristinabili dell'archiviazione della cassetta postale cloud
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
description: Informazioni su come gli amministratori possono eliminare gli elementi nella cartella Elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in conservazione a seguito di un blocco a tempo in sospeso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919956"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Eliminare gli elementi nella cartella Elementi recuperabili delle cassette postali basate su cloud con blocchi

La cartella Elementi ripristinabili per una cassetta postale di Exchange Online esiste per proteggere da eliminazioni accidentali o dannose. Viene inoltre utilizzato per archiviare gli elementi conservati e accessibili dalle funzionalità di conformità, ad esempio blocchi e ricerche eDiscovery. Tuttavia, in alcune situazioni le organizzazioni potrebbero disporre di dati che sono stati involontariamente conservati nella cartella Elementi ripristinabili che devono eliminare. Ad esempio, un utente potrebbe inconsapevolmente inviare o inoltrare un messaggio di posta elettronica contenente informazioni riservate o informazioni che potrebbero avere gravi conseguenze aziendali. Anche se il messaggio viene eliminato definitivamente, potrebbe essere conservato a tempo indeterminato perché è stata impostata una conservazione a livello legale nella cassetta postale. Questo scenario è noto come *perdita di* dati perché i dati sono stati accidentalmente *riversati* in Office 365. In queste situazioni, è possibile eliminare gli elementi nella cartella Elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale viene messa in attesa con una delle diverse funzionalità di blocco in Office 365. Questi tipi di blocchi includono blocchi per controversia legale, blocchi In-Place, blocchi eDiscovery e criteri di conservazione creati nel Centro sicurezza e conformità in Office 365 o Microsoft 365.
  
 In questo articolo viene illustrato come gli amministratori possono eliminare elementi dalla cartella Elementi ripristinabili per le cassette postali basate sul cloud in attesa. Questa procedura prevede la disabilitazione dell'accesso alla cassetta postale e la disabilitazione del ripristino di un singolo elemento, la disabilitazione dell'elaborazione della cassetta postale da parte dell'Assistente cartelle gestite, la rimozione temporanea del blocco, l'eliminazione degli elementi dalla cartella Elementi ripristinabili e il ripristino della configurazione precedente della cassetta postale. Ecco il processo:
  
[Passaggio 1: Raccogliere informazioni sulla cassetta postale](#step-1-collect-information-about-the-mailbox)

[Passaggio 2: Preparare la cassetta postale](#step-2-prepare-the-mailbox)

[Passaggio 3: Rimuovere tutti i blocchi dalla cassetta postale](#step-3-remove-all-holds-from-the-mailbox)

[Passaggio 4: Rimuovere il blocco di ritardo dalla cassetta postale](#step-4-remove-the-delay-hold-from-the-mailbox)

[Passaggio 5: Eliminare gli elementi nella cartella Elementi ripristinabili](#step-5-delete-items-in-the-recoverable-items-folder)

[Passaggio 6: Ripristinare lo stato precedente della cassetta postale](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Le procedure descritte in questo articolo comportano l'eliminazione definitiva (eliminazione) dei dati da una cassetta postale di Exchange Online. Ciò significa che i messaggi eliminati dalla cartella Elementi ripristinabili non possono essere recuperati e non saranno disponibili per l'individuazione a fini giudiziari o per altri scopi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che viene messa in attesa come parte di un blocco per controversia legale, un blocco di In-Place, un blocco eDiscovery o un criterio di conservazione creato nel Centro sicurezza e conformità, rivolgersi alla gestione dei record o ai reparti legali prima di rimuovere il blocco. L'organizzazione potrebbe avere un criterio che definisce se una cassetta postale in attesa o un evento imprevisto di perdita di dati ha la priorità.
  
## <a name="before-you-delete-items"></a>Prima di eliminare gli elementi

- Per creare ed eseguire una ricerca di contenuto, è necessario essere un membro del gruppo di ruoli di gestione di eDiscovery o disporre del ruolo di gestione della ricerca di conformità. Per eliminare i messaggi, è necessario essere un membro del gruppo di ruoli Gestione organizzazione o disporre del ruolo di gestione di ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Questo perché non è possibile riapplicare un blocco (o criteri di conservazione) a una cassetta postale inattiva dopo la rimozione. Quando si rimuove un blocco da una cassetta postale inattiva, viene modificata in una normale cassetta postale eliminata temporaneamente e verrà eliminata definitivamente dall'organizzazione dopo essere stata elaborata dall'Assistente cartelle gestite.

- Non è possibile eseguire questa procedura per una cassetta postale a cui sono state assegnate impostazioni di conservazione con un criterio bloccato utilizzando la protezione dell'archiviazione. Questo perché questo blocco impedisce di rimuovere o escludere la cassetta postale dal criterio e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sui criteri di blocco per la conservazione, vedere [Use Preservation Lock to restrict changes to retention policies and retention label policies.](retention-preservation-lock.md)

- Se una cassetta postale non viene messa in attesa (o non dispone del ripristino di un singolo elemento abilitato), è possibile eliminare gli elementi dalla cartella Elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere Cercare ed eliminare i messaggi [di posta elettronica nell'organizzazione.](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Passaggio 1: Raccogliere informazioni sulla cassetta postale

Questo primo passaggio consiste nel raccogliere le proprietà selezionate dalla cassetta postale di destinazione che influiranno su questa procedura. Assicurarsi di annotarle o salvarle in un file di testo perché alcune di queste proprietà verranno modificate e quindi ripristinate ai valori originali nel passaggio 6, dopo aver eliminato gli elementi dalla cartella Elementi ripristinabili. Ecco un elenco delle proprietà della cassetta postale che è necessario raccogliere.
  
- *SingleItemRecoveryEnabled* e *RetainDeletedItemsFor.* Se necessario, disabilitare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3.

- *LitigationHoldEnabled* e *InPlaceHolds.* È necessario identificare tutti i blocchi effettuati sulla cassetta postale in modo da poterli rimuovere temporaneamente nel passaggio 3. Vedere la [sezione Ulteriori informazioni](#more-information) per suggerimenti su come identificare il tipo di blocco che potrebbe essere effettuato su una cassetta postale.

Inoltre, è necessario ottenere le impostazioni di accesso client delle cassette postali in modo da poterle disabilitare temporaneamente in modo che il proprietario (o altri utenti) non possa accedere alla cassetta postale durante questa procedura. Infine, è possibile ottenere la dimensione corrente e il numero di elementi nella cartella Elementi ripristinabili. Dopo aver eliminato gli elementi nella cartella Elementi ripristinabili nel passaggio 5, è possibile utilizzare queste informazioni per verificare che gli elementi siano stati rimossi.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e una password per un account amministratore a cui sono stati assegnati i ruoli di gestione appropriati in Exchange Online.

2. Eseguire il comando seguente per ottenere informazioni sul ripristino di un singolo elemento e sul periodo di conservazione degli elementi eliminati.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se il ripristino di un singolo elemento è abilitato, sarà necessario disabilitarlo nel passaggio 2. Se il periodo di conservazione degli elementi eliminati non è impostato per 30 giorni (il valore massimo in Exchange Online), è possibile aumentarlo nel passaggio 2.

3. Eseguire il seguente comando per ottenere le impostazioni di accesso alla cassetta postale per la cassetta postale.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Tutti questi metodi di accesso verranno disabilitati nel passaggio 2.

4. Eseguire il seguente comando per ottenere informazioni sui blocchi e sui criteri di conservazione applicati alla cassetta postale.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > Se nella proprietà  *InPlaceHolds*  sono presenti troppi valori e non vengono visualizzati tutti, è possibile eseguire il comando per visualizzare ogni valore su  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una riga separata.
  
5. Eseguire il comando seguente per ottenere informazioni sui criteri di conservazione a livello di organizzazione. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Se l'organizzazione dispone di criteri di conservazione a livello di organizzazione, sarà necessario escludere la cassetta postale da questi criteri nel passaggio 3.

   > [!TIP]
    > Se nella proprietà  *InPlaceHolds*  sono presenti troppi valori e non vengono visualizzati tutti, è possibile eseguire il comando per visualizzare ogni valore su  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una riga separata. 
  
6. Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle nella cartella Elementi ripristinabili nella cassetta postale principale dell'utente.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se la cassetta postale di archiviazione dell'utente è abilitata, eseguire il seguente comando per ottenere la dimensione e il numero totale di elementi nelle cartelle e nelle sottocartelle nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Quando si eliminano elementi nel passaggio 5, è possibile scegliere se eliminare o meno gli elementi nella cartella Elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente. Se l'archiviazione con espansione automatica è abilitata per la cassetta postale, gli elementi in una cassetta postale di archiviazione ausiliaria non verranno eliminati.
  
## <a name="step-2-prepare-the-mailbox"></a>Passaggio 2: Preparare la cassetta postale

Dopo aver raccolto e salvato le informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le attività seguenti:
  
- **Disabilitare l'accesso** client alla cassetta postale in modo che il proprietario della cassetta postale non possa accedere alla propria cassetta postale e apportare modifiche ai dati della cassetta postale durante questa procedura.

- **Aumentare** il periodo di conservazione degli elementi eliminati a 30 giorni (il valore massimo in Exchange Online) in modo che gli elementi non siano eliminati dalla cartella Elementi ripristinabili prima di poterli eliminare nel passaggio 5.

- **Disabilitare** il ripristino di un singolo elemento in modo che gli elementi non siano conservati (per la durata del periodo di conservazione degli elementi eliminati) dopo averli eliminati dalla cartella Elementi ripristinabili nel passaggio 5.

- **Disabilitare l'Assistente** cartelle gestite in modo che non elava la cassetta postale e manteni gli elementi eliminati nel passaggio 5.

Eseguire la procedura seguente in PowerShell di Exchange Online.
  
1. Eseguire il seguente comando per disabilitare tutti gli accessi client alla cassetta postale. La sintassi del comando presuppone che tutti i metodi di accesso client siano stati abilitati nella cassetta postale.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > La disabilitazione di tutti i metodi di accesso client alla cassetta postale potrebbe richiedere fino a 60 minuti. Si noti che la disabilitazione di questi metodi di accesso non disconnetterà il proprietario della cassetta postale attualmente connesso. Se il proprietario non ha effettuato l'accesso, non sarà in grado di accedere alla propria cassetta postale dopo aver disabilitato questi metodi di accesso.
  
2. Eseguire il comando seguente per aumentare il periodo di conservazione degli elementi eliminati per un massimo di 30 giorni. Si presuppone che l'impostazione corrente sia inferiore a 30 giorni.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Eseguire il comando seguente per disabilitare il ripristino di un singolo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > La disabilitazione del ripristino di un singolo elemento potrebbe richiedere fino a 60 minuti. Non eliminare gli elementi nella cartella Elementi ripristinabili fino al termine di questo periodo. 
  
4. Eseguire il seguente comando per impedire all'Assistente cartelle gestite di elaborare la cassetta postale. Come spiegato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se alla cassetta postale non viene applicato un criterio di conservazione con protezione dell'archiviazione. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Passaggio 3: Rimuovere tutti i blocchi dalla cassetta postale

L'ultimo passaggio prima di eliminare gli elementi dalla cartella Elementi ripristinabili consiste nel rimuovere tutti i blocchi (identificati nel passaggio 1) inseriti nella cassetta postale. Tutte le esenzioni devono essere rimosse in modo che gli elementi non siano conservati dopo averli eliminati dalla cartella Elementi ripristinabili. Nelle sezioni seguenti sono contenute informazioni sulla rimozione di diversi tipi di blocchi in una cassetta postale. Vedere la [sezione Ulteriori informazioni](#more-information) per suggerimenti su come identificare il tipo di blocco che potrebbe essere effettuato su una cassetta postale. Per ulteriori informazioni, vedere Come identificare il tipo di blocco effettuato su una cassetta postale [di Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> Come indicato in precedenza, rivolgersi alla gestione dei record o ai reparti legali prima di rimuovere un'esenzione da una cassetta postale. 
  
### <a name="litigation-hold"></a>Conservazione in caso di dispute
  
Eseguire il seguente comando in PowerShell di Exchange Online per rimuovere un blocco per controversia legale dalla cassetta postale.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> Analogamente alla disabilitazione dei metodi di accesso client e al ripristino di un singolo elemento, la rimozione del blocco per controversia legale potrebbe richiedere fino a 60 minuti. Non eliminare elementi dalla cartella Elementi ripristinabili fino al termine di questo periodo. 
  
### <a name="in-place-hold"></a>Blocco sul posto
  
Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco In-Place cassetta postale. Utilizzare il GUID per il In-Place blocco sul posto identificato nel passaggio 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Dopo aver identificato il blocco In-Place, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell di Exchange Online per rimuovere la cassetta postale dal blocco. Per ulteriori informazioni, vedere [Creare o rimuovere un'archiviazione sul posto](https://go.microsoft.com/fwlink/?linkid=852668).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Criteri di conservazione applicati a cassette postali specifiche
  
Eseguire il comando seguente in [PowerShell & Centro](https://go.microsoft.com/fwlink/?linkid=627084) sicurezza e conformità per identificare il criterio di conservazione applicato alla cassetta postale. Questo comando restituirà anche tutti i criteri di conservazione delle conversazioni di Teams applicati a una cassetta postale. Utilizzare il GUID (senza includere il prefisso o il prefisso) per il criterio `mbx` di conservazione identificato nel passaggio `skp` 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Dopo aver identificato il criterio di conservazione, passare alla pagina Conservazione della **governance** delle informazioni nel Centro sicurezza & e conformità, modificare il criterio di conservazione identificato nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di  >   conservazione.
  
### <a name="organization-wide-retention-policies"></a>Criteri di conservazione a livello di organizzazione
  
I criteri di conservazione a livello di organizzazione, di Exchange e di Teams vengono applicati a tutte le cassette postali dell'organizzazione. Vengono applicati a livello di organizzazione (non a livello di cassetta postale) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Eseguire il comando seguente in [PowerShell & Centro](https://go.microsoft.com/fwlink/?linkid=627084) sicurezza e conformità per identificare i criteri di conservazione a livello di organizzazione. Utilizzare il GUID (senza includere il prefisso) per i criteri di conservazione a livello di organizzazione identificati  `mbx` nel passaggio 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Dopo aver identificato i criteri di conservazione a livello di organizzazione, passare alla pagina Conservazione governance delle informazioni nel Centro sicurezza & conformità, modificare ogni criterio di conservazione a livello di organizzazione identificato nel passaggio precedente e aggiungere la cassetta postale all'elenco dei destinatari  >   esclusi. In questo modo la cassetta postale dell'utente verrà eliminata dal criterio di conservazione.

### <a name="retention-labels"></a>Etichette di conservazione

Ogni volta che un utente applica un'etichetta configurata per conservare il contenuto o conservare ed eliminare il contenuto in qualsiasi cartella o elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* è impostata su **True.** In questo caso, la cassetta postale viene considerata in attesa, come se fosse stata messa in conservazione per controversia legale o assegnata a un criterio di conservazione.

Per visualizzare il valore della *proprietà ComplianceTagHoldApplied,* eseguire il comando seguente in PowerShell di Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Dopo aver identificato che una cassetta postale è in attesa perché un'etichetta di conservazione viene applicata a una cartella o a un elemento, è possibile utilizzare lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare gli elementi etichettati utilizzando la condizione di ricerca ComplianceTag. Per ulteriori informazioni, vedere la sezione "Condizioni di ricerca" in Query con parole chiave [e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

Per ulteriori informazioni sulle etichette, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)

### <a name="ediscovery-holds"></a>Blocchi di eDiscovery
  
Eseguire i seguenti comandi in [& PowerShell per Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità per identificare il blocco associato a un caso di eDiscovery (detti blocchi di *eDiscovery)* applicato alla cassetta postale. Utilizzare il GUID (senza includere il prefisso) per il blocco di eDiscovery identificato  `UniH` nel passaggio 1. Il secondo comando visualizza il nome del caso di eDiscovery a cui è associato il blocco; Il terzo comando visualizza il nome dell'esenzione.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Dopo aver identificato il nome del caso di eDiscovery  e il blocco, passare alla pagina \> **eDiscovery di eDiscovery** nel Centro conformità, aprire il caso e rimuovere la cassetta postale dal blocco. Per ulteriori informazioni sull'identificazione dei blocchi di eDiscovery, vedere la sezione "Blocchi di eDiscovery" in Come identificare il tipo di blocco effettuato su una cassetta postale [di Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Passaggio 4: Rimuovere il blocco di ritardo dalla cassetta postale

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, il valore della proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* della cassetta postale viene impostato su **True.** Ciò si verifica la volta successiva in cui l'Assistente cartelle gestite elabora la cassetta postale e rileva che un blocco è stato rimosso. Si tratta  di un blocco di ritardo e significa che la rimozione effettiva del blocco viene ritardata per 30 giorni per evitare che i dati vengano eliminati definitivamente dalla cassetta postale. Lo scopo di un blocco ritardato è quello di offrire agli amministratori la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un blocco.  Quando viene effettuato un blocco di ritardo sulla cassetta postale, la cassetta postale viene ancora considerata in attesa per una durata illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, il blocco di ritardo scade e Microsoft 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* su **False)** in modo che il blocco venga rimosso. Per ulteriori informazioni su un blocco di ritardo, vedere la sezione "Gestione delle cassette postali in attesa di ritardo" in Come identificare il tipo di blocco effettuato su una cassetta postale [di Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)

Prima di eliminare gli elementi nel passaggio 5, è necessario rimuovere un blocco di ritardo dalla cassetta postale. Prima di tutto, determinare se il blocco di ritardo viene applicato alla cassetta postale eseguendo il comando seguente in PowerShell di Exchange Online:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Se il valore della proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* è impostato su **False,** non è stato effettuato un blocco di ritardo nella cassetta postale. È possibile andare al passaggio 5 ed eliminare gli elementi nella cartella Elementi ripristinabili.

Se il valore della proprietà *DelayHoldApplied* o *DelayReleaseHoldApplied* è impostato su **True,** eseguire uno dei comandi seguenti per rimuovere il blocco di ritardo:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oppure

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Per utilizzare il parametro *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied,* è necessario disporre del ruolo di blocco legale in Exchange Online.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Passaggio 5: Eliminare gli elementi nella cartella Elementi ripristinabili

Ora è possibile eliminare effettivamente gli elementi nella cartella Elementi ripristinabili utilizzando i cmdlet [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) e [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) in PowerShell per Centro sicurezza & conformità.

Per cercare gli elementi che si trovano nella cartella Elementi ripristinabili, è consigliabile eseguire una *raccolta di destinazione.* Ciò significa che si restringe l'ambito della ricerca solo agli elementi che si trovano nella cartella Elementi ripristinabili. A tale scopo, eseguire lo script nell'articolo [Use Content Search for targeted collections.](use-content-search-for-targeted-collections.md) Questo script restituisce il valore della proprietà ID cartella per tutte le sottocartelle nella cartella Elementi ripristinabili di destinazione. Utilizzare quindi l'ID cartella in una query di ricerca per restituire gli elementi che si trovano in tale cartella.

Ecco una panoramica del processo di ricerca ed eliminazione di elementi nella cartella Elementi ripristinabili di un utente:

1. Eseguire lo script di raccolta di destinazione che restituisce gli ID cartella per tutte le cartelle nella cassetta postale dell'utente di destinazione. Lo script si connette a PowerShell e Sicurezza di Exchange Online & PowerShell di conformità nella stessa sessione di PowerShell. Per ulteriori informazioni, vedere [Eseguire lo script per ottenere un elenco delle cartelle per una cassetta postale.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Copiare gli ID cartella per tutte le sottocartelle nella cartella Elementi ripristinabili. In alternativa, è possibile reindirizzare l'output dello script a un file di testo.

   Ecco un elenco e una descrizione delle sottocartelle nella cartella Elementi ripristinabili da cui è possibile cercare ed eliminare elementi:

   - **Eliminazioni:** contiene gli elementi eliminati in modo reciso il cui periodo di conservazione non è scaduto. Gli utenti possono recuperare gli elementi eliminati in modo reverso da questa sottocartella utilizzando lo strumento Recupera elementi eliminati in Outlook.

   - **Ripuliture:** contiene gli elementi eliminati definitivamente il cui periodo di conservazione degli elementi eliminati è scaduto. Gli utenti possono anche eliminare definitivamente gli elementi cancellando gli elementi dalla cartella Elementi ripristinabili. Se la cassetta postale è in attesa, gli elementi eliminati definitivamente vengono mantenuti. Questa sottocartella non è visibile agli utenti finali.

   - **DiscoveryHolds:** contiene gli elementi eliminati definitivamente che sono stati conservati da un blocco di eDiscovery o da un criterio di conservazione. Questa sottocartella non è visibile agli utenti finali.

   - **SubstrateHolds:** contiene gli elementi eliminati definitivamente da Teams e altre app basate su cloud che sono state conservate da un criterio di conservazione o da un altro tipo di blocco. Questa sottocartella non è visibile agli utenti finali.

3. Utilizzare il cmdlet **New-ComplianceSearch** (in PowerShell per Centro sicurezza & conformità) o lo strumento Ricerca contenuto nel Centro conformità per creare una ricerca di contenuto che restituisca gli elementi dalla cartella Elementi ripristinabili dell'utente di destinazione. A tale scopo, includere FolderId nella query di ricerca per tutte le sottocartelle in cui si desidera eseguire la ricerca. Ad esempio, la query seguente restituisce tutti i messaggi nelle sottocartelle Purges ed eDiscoveryHolds:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Per ulteriori informazioni ed esempi sull'esecuzione di ricerche di contenuto che utilizzano la proprietà ID cartella, vedere Utilizzare un ID cartella o [per eseguire una raccolta di destinazione.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > Se si utilizza il cmdlet **New-ComplianceSearch** per eseguire ricerche nella cartella Elementi ripristinabili, assicurarsi di utilizzare il cmdlet **Start-ComplianceSearch** per eseguire la ricerca.

4. Dopo aver creato una ricerca di contenuto e verificato che restituisca gli elementi che si desidera eliminare, utilizzare il comando (in PowerShell per Centro sicurezza & conformità) per eliminare definitivamente gli elementi restituiti dalla ricerca di contenuto creata nel passaggio `New-ComplianceSearchAction -Purge -PurgeType HardDelete` precedente. Ad esempio, è possibile eseguire un comando simile al seguente:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Un massimo di 10 elementi per cassetta postale vengono eliminati quando si esegue il comando precedente. Ciò significa che potrebbe essere necessario eseguire il comando più volte per eliminare tutti gli elementi che si desidera eliminare `New-ComplianceSearchAction -Purge` nella cartella Elementi ripristinabili. Per eliminare altri elementi, è innanzitutto necessario rimuovere l'azione di eliminazione della ricerca di conformità precedente. A tale scopo, eseguire il `Remove-ComplianceSearchAction` cmdlet. Ad esempio, per eliminare l'azione di eliminazione eseguita nel passaggio precedente, eseguire il comando seguente:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Una volta eseguita questa operazione, è possibile creare una nuova azione di eliminazione della ricerca di conformità per eliminare altri elementi. Dovrai eliminare ogni azione di eliminazione prima di crearne una nuova.

   Per ottenere un elenco delle azioni di ricerca di conformità, è possibile eseguire il `Get-ComplianceSearchAction` cmdlet. Le azioni di eliminazione vengono identificate `_Purge` aggiungendo il nome della ricerca.

### <a name="verify-that-items-were-deleted"></a>Verificare che gli elementi siano stati eliminati

Per verificare che gli elementi siano stati eliminati correttamente dalla cartella Elementi ripristinabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** in PowerShell di Exchange Online per controllare le dimensioni e il numero di elementi nella cartella Elementi ripristinabili. È possibile confrontare queste statistiche con quelle raccolte nel passaggio 1.
  
Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle nella cartella Elementi ripristinabili nella cassetta postale principale dell'utente.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Eseguire il seguente comando per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle nella cartella Elementi ripristinabili nella cassetta postale di archiviazione dell'utente.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Passaggio 6: Ripristinare lo stato precedente della cassetta postale

Il passaggio finale consiste nel ripristinare la configurazione precedente della cassetta postale. Ciò significa reimpostare le proprietà modificate nel passaggio 2 e riapplicare i blocchi rimossi nel passaggio 3. Ciò include:
  
- Modifica del periodo di conservazione degli elementi eliminati al valore precedente. In alternativa, è possibile lasciare questo valore impostato su 30 giorni, il valore massimo in Exchange Online.

- Ri-abilitazione del ripristino di un singolo elemento.

- Ri-abilitando i metodi di accesso client in modo che il proprietario possa accedere alla propria cassetta postale.

- Riapplicare i blocchi e i criteri di conservazione rimossi.

- Ri-abilitando l'Assistente cartelle gestite per elaborare la cassetta postale.

> [!IMPORTANT]
> È consigliabile attendere 24 ore dopo aver ri-applicato un blocco o un criterio di conservazione (e verificare che sia presente) prima di ri abilitare l'Assistente cartelle gestite per elaborare la cassetta postale.
  
Eseguire i passaggi seguenti (nella sequenza specificata) in PowerShell di Exchange Online.
  
1. Eseguire il comando seguente per tornare al valore originale del periodo di conservazione degli elementi eliminati. Si presuppone che l'impostazione precedente sia inferiore a 30 giorni. ad esempio 14 giorni.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Eseguire il comando seguente per abilitare nuovamente il ripristino di un singolo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Eseguire il seguente comando per abilitare nuovamente tutti i metodi di accesso client alla cassetta postale.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Riapplicare i blocchi rimossi nel passaggio 3. A seconda del tipo di blocco, utilizzare una delle procedure seguenti.

    **Conservazione per controversia legale**

    Eseguire il seguente comando per abilitare nuovamente un blocco per controversia legale per la cassetta postale.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    Utilizzare l'interfaccia di amministrazione di Exchange (o PowerShell di Exchange Online) per aggiungere di nuovo la cassetta postale al blocco In-Place locale.

    **Criteri di conservazione applicati a cassette postali specifiche**

    Utilizzare il Centro sicurezza & conformità per aggiungere di nuovo la cassetta postale al criterio di conservazione. Passare alla pagina Conservazione della **governance** delle informazioni nel Centro sicurezza & conformità, modificare i criteri di conservazione e aggiungere di nuovo la cassetta postale all'elenco dei destinatari a cui viene applicato il criterio  >   di conservazione.

    **Criteri di conservazione a livello di organizzazione**

    Se è stato rimosso un criterio di conservazione a livello di organizzazione o di Exchange escludendolo dal criterio, utilizzare il Centro sicurezza & conformità per rimuovere la cassetta postale dall'elenco degli utenti esclusi. Passare alla pagina **Conservazione governance** delle informazioni nel Centro sicurezza & conformità, modificare i criteri di conservazione a livello di organizzazione e rimuovere la cassetta postale dall'elenco dei  >   destinatari esclusi. In questo modo il criterio di conservazione verrà riapplicato alla cassetta postale dell'utente.

    **Blocchi dei casi di eDiscovery**

    Utilizzare il Centro sicurezza & conformità per aggiungere la cassetta postale all'esenzione associata a un caso di eDiscovery. Passare alla pagina **eDiscovery** di  >  **eDiscovery,** aprire il caso e aggiungere di nuovo la cassetta postale al blocco. 

5. Eseguire il seguente comando per consentire all'Assistente cartelle gestite di elaborare di nuovo la cassetta postale. Come indicato in precedenza, è consigliabile attendere 24 ore dopo aver riapplicato un blocco o un criterio di conservazione (e verificare che sia presente) prima di ri abilitare l'Assistente cartelle gestite.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Per verificare che la cassetta postale sia stata ripristinata alla configurazione precedente, è possibile eseguire i seguenti comandi e quindi confrontare le impostazioni con quelle raccolte nel passaggio 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Altre informazioni

Ecco una tabella che descrive come identificare diversi tipi di blocchi in base ai valori nella proprietà *InPlaceHolds* quando si eseguono i cmdlet **Get-Mailbox** o **Get-OrganizationConfig.** Per informazioni più dettagliate, vedere Come identificare il tipo di blocco effettuato su una cassetta postale [di Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md)

Come spiegato in precedenza, è necessario rimuovere tutti i blocchi e i criteri di conservazione da una cassetta postale prima di eliminare correttamente gli elementi nella cartella Elementi ripristinabili.
  
| Tipo di blocco | Valore di esempio | Come identificare l'esenzione |
|:-----|:-----|:-----|
|Blocco per controversia legale  <br/> | `True` <br/> |La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.  <br/> |
|Blocco sul posto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La  *proprietà InPlaceHolds*  contiene il GUID del blocco In-Place cassetta postale. È possibile indicare che si tratta di un In-Place blocco perché il GUID non inizia con un prefisso.  <br/> È possibile utilizzare il comando in PowerShell di Exchange Online per ottenere informazioni sull'In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` sulla cassetta postale.  <br/> |
| Criteri di conservazione nel Centro sicurezza & conformità applicato a cassette postali specifiche  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oppure  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Quando si esegue il cmdlet **Get-Mailbox,** la proprietà  *InPlaceHolds*  contiene anche i GUID dei criteri di conservazione applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia con il  `mbx` prefisso. Se il GUID del criterio di conservazione inizia con il prefisso, indica che il criterio di conservazione viene  `skp` applicato alle conversazioni di Skype for Business.  <br/> Per identità dei criteri di conservazione applicati alla cassetta postale, eseguire il comando seguente in PowerShell per Centro sicurezza & conformità: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Assicurarsi di rimuovere il prefisso  `mbx` o  `skp` quando si esegue questo comando.  <br/> |
|Criteri di conservazione a livello di organizzazione nel Centro sicurezza & conformità  <br/> |Nessun valore  <br/> oppure  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indica che la cassetta postale è esclusa da un criterio a livello di organizzazione)  <br/> |Anche se la  *proprietà InPlaceHolds*  è vuota quando si esegue il cmdlet **Get-Mailbox,** alla cassetta postale potrebbero essere applicati uno o più criteri di conservazione a livello di organizzazione.  <br/> Per verificare questo problema, è possibile eseguire il comando in PowerShell di Exchange Online per ottenere un elenco dei GUID per i criteri di  `Get-OrganizationConfig | FL InPlaceHolds` conservazione a livello di organizzazione. Il GUID dei criteri di conservazione applicati alle cassette postali di Exchange inizia con il  `mbx` prefisso, ad esempio  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Per identità dei criteri di conservazione applicati alla cassetta postale a livello di organizzazione, eseguire il comando seguente in PowerShell per Centro sicurezza & conformità: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Se una cassetta postale viene esclusa da un criterio di conservazione a livello di organizzazione, il GUID per il criterio di conservazione viene visualizzato nella proprietà  *InPlaceHolds*  della cassetta postale dell'utente quando si esegue il cmdlet **Get-Mailbox;** è identificato dal  `-mbx` prefisso; ad esempio,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|Blocco del caso di eDiscovery nel Centro sicurezza & conformità  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La  *proprietà InPlaceHolds*  contiene anche il GUID di qualsiasi blocco associato a un caso di eDiscovery nel Centro sicurezza & conformità che potrebbe essere posizionato nella cassetta postale. È possibile stabilire che si tratta di un blocco caso eDiscovery perché il GUID inizia con il prefisso  `UniH`.  <br/> È possibile utilizzare il cmdlet in PowerShell & Centro sicurezza e conformità per ottenere informazioni sul caso di eDiscovery a cui è associato il blocco sulla cassetta  `Get-CaseHoldPolicy` postale. Ad esempio, è possibile eseguire il comando per visualizzare il nome del blocco caso nella  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` cassetta postale. Be sure to remove the  `UniH` quando si esegue questo comando.  <br/><br/> Per identità del caso di eDiscovery a cui è associato il blocco sulla cassetta postale, eseguire i comandi seguenti:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
