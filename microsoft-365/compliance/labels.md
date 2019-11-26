---
title: Panoramica delle etichette di conservazione
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Le etichette di conservazione in Office 365 aiutano a identificare le azioni corrette da eseguire per ogni contenuto. Con le etichette di conservazione è possibile classificare i dati all'interno dell'organizzazione a scopi di governance e applicare regole di conservazione in base alla classificazione. È possibile utilizzare le etichette di conservazione per implementare la gestione dei record in Office 365.
ms.openlocfilehash: 143d3fb97afca5b6a3b18e47b7be472f35a857ba
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "39266147"
---
# <a name="overview-of-retention-labels"></a>Panoramica delle etichette di conservazione

All'interno dell'organizzazione sono probabilmente presenti tipi di contenuto diversi, sui quali occorre eseguire azioni differenti per garantire la conformità alle normative di settore e ai criteri interni. Ad esempio, possono essere presenti:
  
- Moduli fiscali che devono essere **conservati** per un periodo di tempo minimo. 
    
- Materiali per la stampa che devono essere **eliminati definitivamente** dopo un determinato periodo di tempo. 
    
- Ricerche competitive che devono essere **conservate** e in seguito **eliminate definitivamente**. 
    
- Permessi di lavoro che devono essere **classificati come record** in modo che non sia possibile modificarli o eliminarli. 
    
In tutti questi casi, le etichette di conservazione in Office 365 aiutano a identificare le azioni corrette da eseguire per ogni contenuto. Con le etichette di conservazione è possibile classificare i dati all'interno dell'organizzazione a scopi di governance e applicare regole di conservazione in base alla classificazione.
  
Con le etichette di conservazione è possibile:
  
- **Permettere agli utenti dell'organizzazione di applicare manualmente un’etichetta di conservazione** a contenuti in Outlook sul web, Outlook 2010 e versioni successive, OneDrive, SharePoint e gruppi di Office 365. Spesso gli utenti sono quelli che conoscono meglio il tipo di contenuto che stanno usando, per cui sono in grado di classificarlo e applicare i criteri appropriati. 
    
- **Applicare automaticamente etichette di conservazione al contenuto** se soddisfa specifiche condizioni, ad esempio se include: 
    
  - Tipi specifici di informazioni riservate.
    
  - Parole chiave specifiche che corrispondono a una query creata.
    
  La possibilità di applicare automaticamente etichette di conservazione al contenuto è importante perché:
    
     - Non è necessario formare gli utenti su tutte le classificazioni.
    
     - Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.
    
   - Gli utenti non hanno più bisogno di conoscere i criteri di governance dai dati e possono concentrarsi sul loro lavoro.

  > [!NOTE]
  > La possibilità di applicare automaticamente etichette richiede una licenza di Office 365 Enterprise E5 per ogni utente che dispone delle autorizzazioni per modificare il contenuto a cui è stata assegnata automaticamente un’etichetta in un sito o in una cassetta postale. Per gli utenti che dispongono di accesso di sola lettura non è necessaria una licenza.
      
- **Implementare la gestione dei record in Office 365**, compresi posta elettronica e documenti. È possibile usare un'etichetta di conservazione per classificare il contenuto come record. In questo caso, non è possibile cambiare o rimuovere l'etichetta e il contenuto non può essere modificato o eliminato. 

- **Applicare un'etichetta di conservazione predefinita a una raccolta documenti, cartella o set di documenti** in SharePoint, così che i documenti in quella posizione ereditino l’etichetta di conservazione predefinita.  
    
Le etichette di conservazione vengono create nel Centro conformità Microsoft 365, nel Centro sicurezza Microsoft 365 o nel Centro sicurezza e conformità di Office 365. Nel riquadro di spostamento sinistro scegliere **Classificazione** > **Etichetta di conservazione** > **Crea un'etichetta**.

## <a name="how-retention-labels-work-with-retention-label-policies"></a>Funzionamento delle etichette di conservazione con i criteri di etichetta di conservazione

Rendere disponibili le etichette di conservazione agli utenti dell'organizzazione in modo che possano classificare il contenuto è un processo in due passaggi. Il primo consiste nel creare le etichette di conservazione, il secondo nel pubblicarle nelle posizioni scelte. Quando si pubblicano etichette di conservazione, vengono incluse in criteri di etichetta di conservazione.
  
![Diagramma di ruoli e attività per le etichette](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
Le etichette di conservazione sono blocchi predefiniti indipendenti e riutilizzabili che vengono inclusi in uno o più criteri di etichetta di conservazione. Lo scopo principale di un criterio di etichetta di conservazione è raggruppare un set di tali etichette e specificare le posizioni in cui si vuole che vengano visualizzate.
  
![Diagramma di etichette, criteri per le etichette e posizioni](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. Quando si pubblicano etichette di conservazione, vengono incluse in criteri di etichetta di conservazione. Tenere presente che i nomi delle etichette di conservazione sono immutabili e non possono essere modificati una volta creati.


2. Una singola etichetta di conservazione può essere inclusa in molti criteri di etichetta di conservazione.

3. Una singola posizione può anche essere inclusa in molti criteri di etichetta di conservazione.    
    
3. I criteri di etichetta di conservazione specificano le posizioni di pubblicazione delle etichette di conservazione.
    
## <a name="only-one-retention-label-at-a-time"></a>Solo un'etichetta di conservazione alla volta

È importante tenere presente che a contenuti come un messaggio di posta elettronica o un documento è possibile assegnare una sola etichetta di conservazione alla volta:
  
- Per le etichette di conservazione assegnate manualmente dagli utenti finali, è possibile rimuovere o cambiare l'etichetta di conservazione assegnata.
    
- Se al contenuto è assegnata un'etichetta applicata automaticamente, questa può essere sostituita da un'etichetta di conservazione assegnata manualmente da un utente finale.
    
- Se al contenuto è assegnata un'etichetta di conservazione applicata manualmente da un utente finale, questa non può essere sostituita da un'etichetta di conservazione applicata automaticamente.
    
- Se sono presenti più regole che assegnano automaticamente un'etichetta e il contenuto soddisfa le condizioni di più regole, viene assegnata l'etichetta di conservazione della regola meno recente.
    
Le etichette assegnate manualmente vengono assegnate in modo esplicito, mentre le etichette applicate automaticamente vengono assegnate in modo implicito. Un'etichetta di conservazione esplicita ha la precedenza su un'etichetta implicita. Per altre informazioni, vedere la sezione [Principi di conservazione o criteri per determinare la precedenza](#the-principles-of-retention-or-what-takes-precedence), più avanti.

Le informazioni contenute in questa sezione si applicano solo alle etichette di conservazione. Si noti che, in aggiunta a un’etichetta di conservazione, è possibile applicare a un contenuto anche un’etichetta di riservatezza.
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Tempo necessario per l'applicazione delle etichette di conservazione

Quando si pubblicano o si applicano automaticamente le etichette di conservazione, queste non hanno effetto immediato:
  
1. Per prima cosa i criteri di etichetta devono essere sincronizzati dall'interfaccia di amministrazione alle posizioni indicate nei criteri.
    
2. Quindi, la posizione potrebbe richiedere del tempo per rendere disponibili le etichette di conservazione pubblicate agli utenti finali o per applicare automaticamente etichette al contenuto. Il tempo necessario dipende dalla posizione e dal tipo di etichetta di conservazione.
    
### <a name="published-retention-labels"></a>Etichette di conservazione pubblicate

Se si pubblicano etichette di conservazione in SharePoint o OneDrive, può essere necessario un giorno perché le etichette di conservazione siano visibili agli utenti finali. Se si pubblicano etichette di conservazione in Exchange, possono essere necessari 7 giorni perché le etichette di conservazione siano visibili agli utenti finali, inoltre la cassetta postale deve contenere almeno 10 MB di dati.
  
![Diagramma del momento in cui le etichette manuali hanno effetto](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>Applicare automaticamente etichette di conservazione

In caso di applicazione automatica di etichette di conservazione ai contenuti che soddisfano condizioni specifiche, possono essere necessari 7 giorni prima che le etichette di conservazione vengano applicate a tutto il contenuto esistente che soddisfa le condizioni.
  
![Diagramma di disponibilità delle etichette applicate automaticamente](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Come verificare lo stato delle etichette di conservazione pubblicate in Exchange

In Exchange Online le etichette di conservazione vengono rese disponibili agli utenti finali mediante un processo eseguito ogni sette giorni. Usando Powershell è possibile vedere quando è stato eseguito per l'ultima volta questo processo e quindi stabilire quando verrà eseguito nuovamente.
  
1. [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. Eseguire questi comandi.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

Nei risultati, la proprietà `ELCLastSuccessTimeStamp` (UTC) mostra quando il sistema ha elaborato la casetta postale per l'ultima volta. Se questa operazione non è stata eseguita da quando è stato creato il criterio, le etichette non verranno visualizzate. Per forzare l'elaborazione, eseguire `Start-ManagedFolderAssistant -Identity <user>`.
    
Se le etichette non compaiono in Outlook sul web e si ritiene che invece debbano comparire, svuotare la cache del browser (CTRL+F5).
    
## <a name="retention-label-policies-and-locations"></a>Criteri per le etichette di conservazione e posizioni

È possibile pubblicare tipi di etichette di conservazione differenti in posizioni diverse, a seconda dell'azione eseguita dall'etichetta di conservazione.
  
|**Se l'etichetta di conservazione è...**|**Il criterio di etichetta può essere applicato a…**|
|:-----|:-----|
|Pubblicata agli utenti finali  <br/> |Exchange, SharePoint, OneDrive, gruppi di Office 365  <br/> |
|Applicata automaticamente in base ai tipi di informazioni riservate  <br/> |Exchange (solo a tutte le cassette postali), SharePoint, OneDrive  <br/> |
|Applicata automaticamente in base a una query  <br/> |Exchange, SharePoint, OneDrive, gruppi di Office 365  <br/> |
   
Le etichette di conservazione applicate automaticamente in Exchange (sia per le query che per i tipi di informazioni riservate) vengono applicate solo ai messaggi appena inviati (dati in transito), non a tutti gli elementi attualmente nella cassetta postale (dati archiviati). Inoltre, le etichette di conservazione applicate automaticamente per i tipi di informazioni riservate possono essere applicate solo a tutte le cassette postali, non a cassette postali specifiche.
  
Le cartelle pubbliche di Exchange e Skype non supportano le etichette.
  
## <a name="how-retention-labels-enforce-retention"></a>In che modo le etichette di conservazione applicano i criteri di conservazione

Le etichette di conservazione possono applicare esattamente le stesse azioni di conservazione di un criterio di conservazione. Si possono usare le etichette di conservazione per implementare un piano contenuti (o un piano file) sofisticato. Per altre informazioni sul funzionamento della conservazione, vedere [Panoramica dei criteri di conservazione](retention-policies.md).
  
Inoltre, un'etichetta di conservazione ha due opzioni di conservazione che sono disponibili solo in un'etichetta di conservazione e non in un criterio di conservazione. Con un'etichetta di conservazione, è possibile:
  
- Attivare una revisione per l'eliminazione alla fine del periodo di conservazione, in modo che venga impostata una revisione obbligatoria dei documenti di SharePoint e OneDrive prima che vengano eliminati. Per altre informazioni, vedere [Panoramica delle revisioni per l'eliminazione](disposition-reviews.md).
    
- Iniziare il periodo di conservazione dal momento in cui il contenuto è stato etichettato invece che in base all'età o alla data dell'ultima modifica. Questa opzione si applica solo al contenuto di siti di SharePoint e account di OneDrive. Per la posta elettronica di Exchange il periodo di conservazione è sempre basato sulla data di invio o ricezione del messaggio, indipendentemente dall'opzione scelta.
    
![Impostazioni di conservazione con opzioni specifiche per le etichette](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a>Posizioni in cui è possibile visualizzare le etichette di conservazione pubblicate agli utenti finali

Se l'etichetta di conservazione verrà assegnata al contenuto dagli utenti finali, è possibile pubblicarla in:
  
- Outlook sul web
    
- Outlook 2010 e versioni successive
    
- OneDrive
    
- SharePoint
    
- Gruppi di Office 365 (sia nel sito del gruppo che nella cassetta postale del gruppo in Outlook sul web)
    
Le sezioni seguenti mostrano il modo in cui le etichette vengono visualizzate agli utenti dell'organizzazione in app diverse.
  
### <a name="outlook-on-the-web"></a>Outlook sul web

Per assegnare un'etichetta a un elemento in Outlook sul web, fare clic con il pulsante destro del mouse sull'elemento\> **Assegna criteri** \> scegliere l'etichetta di conservazione. 
  
![Menu Assegna criteri in Outlook sul web](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
Una volta applicata, l'etichetta di conservazione può essere visualizzata insieme all'azione che esegue nella parte superiore dell'elemento. Se un messaggio di posta elettronica viene classificato ed è associato a un periodo di conservazione, con una rapida occhiata se ne conoscerà la data di scadenza.
  
![Etichetta assegnata al messaggio di posta elettronica in Outlook sul web](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
È anche possibile applicare etichette di conservazione a cartelle. In questo caso:
  
- Tutti gli elementi nella cartella ricevono automaticamente la stessa etichetta di conservazione **tranne** gli elementi ai quali è stata applicata esplicitamente un'etichetta di conservazione. Gli elementi etichettati esplicitamente mantengono l'etichetta di conservazione esistente. Per altre informazioni, vedere la sezione sui principi di conservazione più avanti. 
    
- Se si modifica o si rimuove l'etichetta di conservazione predefinita per una cartella, l'etichetta viene modificata o rimossa anche da tutti gli elementi nella cartella **tranne** che dagli elementi con etichette di conservazione esplicite. 
    
- Se si sposta un elemento con un'etichetta di conservazione predefinita da una cartella a un'altra cartella con un'etichetta di conservazione predefinita diversa, l'elemento riceverà la nuova etichetta di conservazione predefinita.
    
- Se si sposta un elemento con un'etichetta di conservazione predefinita da una cartella a un'altra cartella senza alcuna etichetta di conservazione predefinita, l’etichetta di conservazione precedente è rimossa.
    
### <a name="outlook-2010-and-later"></a>Outlook 2010 e versioni successive

Per assegnare un'etichetta a un elemento nel client desktop di Outlook, selezionare l'elemento. Nella scheda **Home** della barra multifunzione fare clic su **Assegna criterio** e quindi scegliere l'etichetta di conservazione. 
  
![Pulsante Assegna criterio](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
È anche possibile fare clic con il pulsante destro del mouse su un elemento, scegliere **Assegna criterio** dal menu di scelta rapida e quindi scegliere l'etichetta di conservazione. 

Dopo l'applicazione dell'etichetta di conservazione, è possibile visualizzarla insieme all'azione che esegue nella parte superiore dell'elemento. Se a un messaggio di posta elettronica viene applicata un'etichetta di conservazione che ha un periodo di conservazione associato, con una rapida occhiata si conoscerà la data di scadenza del messaggio di posta elettronica.
  
È anche possibile applicare etichette di conservazione a cartelle. Questa operazione funziona allo stesso modo in Outlook 2010 e versioni successive e in Outlook sul Web. Per altre informazioni, vedere la sezione precedente.
  
### <a name="onedrive-and-sharepoint"></a>OneDrive e SharePoint

Per assegnare un'etichetta a un documento (inclusi i file di OneNote) in OneDrive o SharePoint, selezionare l'elemento \> nell'angolo in alto a destra, scegliere **Apri il riquadro dei dettagli**![Icona del riquadro informazioni](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Applica etichetta di conservazione** \>scegliere l'etichetta di conservazione. 
  
È possibile applicare un'etichetta di conservazione anche a un set di cartelle o di documenti e si può impostare un'etichetta di conservazione predefinita per una raccolta documenti. Per altre informazioni, vedere la sezione seguente.
  
![Applicazione di un elenco di etichette per un elemento in SharePoint](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
Dopo l'applicazione di un'etichetta di conservazione a un elemento, è possibile visualizzarla nel riquadro dei dettagli quando l'elemento viene selezionato.
  
![Etichetta applicata visibile nel riquadro dei dettagli](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
È anche possibile creare una visualizzazione della raccolta che contenga la colonna **Etichette** o la colonna **L'elemento è un record**, in modo da poter vedere a colpo d'occhio le etichette di conservazione assegnate a tutti gli elementi e quali elementi sono record. Tuttavia, non è possibile filtrare la visualizzazione per la colonna **L'elemento è un record**. 
  
![Colonna della raccolta per le etichette visibile nella visualizzazione personalizzata](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a>Gruppi di Office 365

Quando si pubblicano etichette di conservazione in un gruppo di Office 365, le etichette di conservazione vengono visualizzate sia nel sito del gruppo che nella cassetta postale del gruppo in Outlook sul web. L'esperienza di applicazione di un'etichetta di conservazione al contenuto è identica a quella illustrata in precedenza per posta elettronica e documenti.

Per conservare il contenuto di un gruppo di Office 365 è necessario usare la posizione dei gruppi di Office 365. Anche se un gruppo di Office 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso di Exchange non includerà il contenuto nelle cassette postali del gruppo di Office 365.

Inoltre, non è possibile usare il percorso di Exchange per includere o escludere una specifica cassetta postale del gruppo. Anche se il percorso di Exchange consente inizialmente di selezionare una cassetta postale del gruppo, provando a salvare il criterio di conservazione si riceverà un messaggio di errore che segnala che "RemoteGroupMailbox" non è una selezione valida per il percorso di Exchange.
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>Applicazione automatica di un'etichetta di conservazione in base alle condizioni

Una delle funzionalità più efficaci delle etichette di conservazione è la possibilità di applicarle automaticamente al contenuto che soddisfa determinate condizioni. In questo caso, gli utenti dell'organizzazione non dovranno applicare le etichette di conservazione. Office 365 lo farà automaticamente.
  
![Diagramma di ruoli e attività per le etichette applicate automaticamente](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
Le etichette di conservazione applicate automaticamente sono potenti perché:
  
- Non è necessario formare gli utenti su tutte le classificazioni.
    
- Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.
    
- Gli utenti non hanno più bisogno di conoscere i criteri di governance dai dati e possono concentrarsi sul loro lavoro.
    
È possibile scegliere di applicare automaticamente etichette di conservazione al contenuto quando questo contiene:
  
- Tipi specifici di informazioni riservate.
    
- Parole chiave specifiche che corrispondono a una query creata.
    
![Pagina riguardante la scelta delle condizioni per l'etichetta applicata automaticamente](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)


Per l'applicazione automatica delle etichette di conservazione è necessario un abbonamento a Office 365 Enterprise E5 e possono essere necessari fino a sette giorni per l'applicazione automatica delle etichette di conservazione a tutto il contenuto che soddisfa le condizioni, come illustrato in precedenza.
  
> [!TIP]
> Vedere [Gestire il ciclo di vita dei documenti di SharePoint con etichette di conservazione](auto-apply-retention-labels-scenario.md) per uno scenario dettagliato sull'uso delle proprietà gestite in SharePont per applicare automaticamente etichette di conservazione e implementare la conservazione basata su eventi.

### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a>Applicare automaticamente etichette di conservazione al contenuto con tipi specifici di informazioni riservate

Quando si creano etichette di conservazione ad applicazione automatica per le informazioni riservate, viene visualizzato lo stesso elenco di modelli di criteri mostrato quando si creano criteri di prevenzione della perdita dei dati (DLP). Ogni modello di criteri è preconfigurato in modo da cercare specifici tipi di informazioni riservate. Ad esempio, il modello illustrato di seguito cerca codici identificativi del singolo contribuente (ITIN), codici di previdenza sociale (SSN) e numeri di passaporto statunitensi. Per altre informazioni sui criteri DLP, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).
  
![Modelli di criteri con le tipologie di informazioni sensibili](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
Dopo aver selezionato un modello di criteri, è possibile aggiungere o rimuovere qualunque tipo di informazioni riservate e modificare il numero di istanze e l'accuratezza della corrispondenza. Nell'esempio mostrato di seguito, verrà applicata automaticamente un'etichetta di conservazione solo quando:
  
- Il contenuto include tra 1 e 9 istanze di qualsiasi di tipo di informazioni riservate. È possibile eliminare il valore **max** in modo che diventi **qualsiasi**.
    
- Il tipo di informazioni riservate rilevate ha un'accuratezza della corrispondenza (o livello di attendibilità) di almeno 75. Molti tipi di informazioni riservate sono definiti con più criteri. I criteri con un livello di accuratezza della corrispondenza superiore richiedono l'individuazione di ulteriori elementi di prova (ad esempio parole chiave, date o indirizzi), mentre i criteri con un livello di accuratezza della corrispondenza inferiore richiedono meno elementi di prova. In parole povere, più basso è il valore di accuratezza della corrispondenza **min**, più facile sarà che il contenuto soddisfi la condizione. 
    
Per altre informazioni su queste opzioni, vedere [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) (Ottimizzazione delle regole per rendere più facile o difficile la corrispondenza).
    
![Opzioni per l'identificazione dei tipi di informazioni riservate](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Applicare automaticamente etichette al contenuto con parole chiave o con proprietà disponibili per le ricerche

È possibile applicare automaticamente etichette al contenuto che soddisfa determinate condizioni. Le condizioni disponibili ora supportano l'applicazione di un'etichetta al contenuto che include parole, frasi, valori o proprietà disponibili per le ricerche specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT.

Per altre informazioni sulla sintassi della query, vedere:

- [Riferimenti per la sintassi di Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

Le etichette basate su query usano l’indice di ricerca per identificare il contenuto. Per altre informazioni sulle proprietà disponibili per la ricerca valide, vedere:

- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
- [Panoramica delle proprietà gestite e sottoposte a ricerca per indicizzazione in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

Esempi di query:

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint e OneDrive for Business
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![Editor di query](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint

Oltre a permettere agli utenti di applicare un'etichetta di conservazione a singoli documenti, è anche possibile applicare un'etichetta di conservazione predefinita a una raccolta, una cartella o un set di documenti di SharePoint, in modo che tutti i documenti in quella posizione ricevano l'etichetta di conservazione predefinita.
  
Per una raccolta documenti, questa operazione si esegue nella pagina **Impostazioni raccolta** corrispondente. Quando si sceglie l'etichetta di conservazione predefinita, è anche possibile scegliere di applicarla a elementi esistenti nella raccolta. 
  
Ad esempio, se si ha un tag per il materiale di marketing e si sa che una specifica raccolta documenti contiene solo quel tipo di contenuto, è possibile impostare il tag Materiali marketing come predefinito per tutti i documenti nella raccolta.
  
![Opzione Applica etichetta nella pagina Impostazioni della raccolta](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
Se si applica un'etichetta di conservazione predefinita agli elementi esistenti nella raccolta, nella cartella o nel set di documenti:
  
- Tutti gli elementi nella raccolta, nella cartella o nel set di documenti ricevono automaticamente la stessa etichetta di conservazione, **tranne** gli elementi ai quali è stata applicata esplicitamente un'etichetta di conservazione. Gli elementi etichettati esplicitamente mantengono l'etichetta esistente. Per altre informazioni, vedere la sezione [Precedenza nei principi di conservazione](#the-principles-of-retention-or-what-takes-precedence) più avanti.
    
- Se si modifica o si rimuove l'etichetta di conservazione predefinita per una raccolta, una cartella o un set di documenti, l'etichetta viene modificata o rimossa anche da tutti gli elementi nella raccolta, nella cartella o nel set di documenti **tranne** che dagli elementi con etichette di conservazione esplicite. 
    
- Se si sposta un elemento con un'etichetta di conservazione predefinita da una raccolta, una cartella o un set di documenti a un'altra raccolta, cartella o set di documenti, l'elemento mantiene l'etichetta di conservazione predefinita esistente anche se la nuova posizione ne ha una diversa.

- Se l'etichetta di conservazione predefinita per una raccolta, una cartella o un set di documenti dichiara il contenuto come record (si parla anche di *etichetta record*), sono applicabili le caratteristiche seguenti:

   - Se si modifica l'etichetta di conservazione predefinita in un'etichetta che non dichiara il contenuto come record, gli elementi mantengono l'etichetta record predefinita. La nuova etichetta di conservazione predefinita non viene applicata a tali elementi. Un amministratore della raccolta siti dovrà rimuovere o modificare esplicitamente l'etichetta di conservazione.

   - Se si rimuove l'etichetta di conservazione predefinita che dichiara il contenuto come record, l'etichetta record non viene rimossa dagli elementi della raccolta, della cartella o del set di documenti. Un amministratore della raccolta di siti dovrà rimuovere esplicitamente l'etichetta di conservazione.

   Per altre informazioni sulle etichette di conservazione che dichiarano il contenuto come record, vedere [Panoramica dei record](records.md).
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a>Applicazione di un'etichetta di conservazione alla posta elettronica mediante regole

In Outlook 2010 o versioni successive è possibile creare regole per applicare un'etichetta di conservazione o criteri di conservazione.
  
Ad esempio, si può creare una regola che applica un'etichetta di conservazione specifica a tutti i messaggi inviati a o da un particolare gruppo di distribuzione.
  
Per creare una regola, fare clic su un elemento\> **Regole** \> **Crea regola** \> **Opzioni avanzate** \> **Creazione guidata regole** \> **Applica i criteri di conservazione.**.
  
![Creazione guidata regole con opzione per applicare i criteri di conservazione](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>Classificazione del contenuto senza applicazione di azioni

Quando si crea un'etichetta di conservazione, è possibile farlo senza attivare criteri di conservazione o altre azioni, come illustrato di seguito. In questo caso, si può usare un'etichetta di conservazione semplicemente come etichetta di testo, senza applicare azioni.
  
Ad esempio, si può creare un'etichetta di conservazione denominata "Rivedere in un secondo momento" senza azioni e quindi applicarla automaticamente a contenuto con tipi di informazioni riservate o a contenuto in cui vengono eseguite query.
  
![Pagina Impostazioni etichetta con conservazione disattivata](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a>Uso di etichette di conservazione per la gestione dei record
    
È possibile usare le etichette di conservazione per dichiarare il contenuto come record. Questo permette di implementare un'unica strategia di gestione dei record coerente in Office 365. Per altre informazioni, vedere [Panoramica dei record](records.md).
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Uso di un'etichetta di conservazione come condizione nei criteri di prevenzione della perdita dei dati

Un'etichetta di conservazione può applicare azioni di conservazione sul contenuto. Inoltre, è possibile usare un'etichetta di conservazione come condizione in un criterio di prevenzione della perdita dei dati (DLP), e il criterio DLP può applicare altre azioni, come la limitazione dell'accesso, sui contenuti che includono un'etichetta di conservazione specifica. 
  
Per altre informazioni, vedere [Uso di un'etichetta come condizione nei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="monitor-retention-labels"></a>Monitorare le etichette di conservazione

Dopo aver pubblicato o applicato automaticamente le etichette di conservazione, è consigliabile verificare che vengano applicate al contenuto come previsto. Per monitorare le etichette di conservazione, si può usare:
  
- **Esplora attività con etichette**. Con Esplora attività con etichette (mostrato di seguito), è possibile cercare e visualizzare rapidamente le attività relative alle etichette di conservazione per tutto il contenuto di SharePoint e OneDrive for Business degli ultimi 30 giorni. Per altre informazioni, vedere [Visualizzare le attività con etichette per i documenti](view-label-activity-for-documents.md).

- Pagina di **analisi delle etichette**. Nel centro conformità Microsoft 365 e nel centro sicurezza Microsoft 365 è possibile visualizzare rapidamente le etichette principali e dove vengono applicate. È possibile anche visualizzare tutto il contenuto con una specifica etichetta. Per ulteriori informazioni vedere [Visualizzare l'uso delle etichette con Analisi delle etichette](label-analytics.md).
    
- **Report di Governance dei dati**. Con questi report, è possibile visualizzare rapidamente le tendenze delle etichette di conservazione e le attività per tutto il contenuto di Exchange, SharePoint e OneDrive for Business degli ultimi 90 giorni. Per altre informazioni, vedere [Visualizzare i report di Governance dei dati](view-the-data-governance-reports.md).
    
![Esplora attività con etichette](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>Uso di Ricerca contenuto per trovare tutto il contenuto a cui è applicata una specifica etichetta di conservazione

Dopo l'assegnazione automatica o manuale di etichette di conservazione al contenuto, è possibile usare Ricerca contenuto per trovare tutto il contenuto che ha una specifica etichetta di conservazione.
  
Quando si crea una ricerca di contenuto, scegliere la condizione **Tag di conformità**, quindi immettere il nome completo dell'etichetta o parte di esso e usare un carattere jolly. Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).
  
![Condizione tag di conformità](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Precedenza nei principi di conservazione

È possibile, o addirittura probabile, che al contenuto siano applicati più criteri di conservazione con azioni (conservare, eliminare o entrambi) e periodi di conservazione diversi. Quali sono i criteri che hanno la precedenza? Al livello più alto, un contenuto che viene conservato in base a un particolare criterio non può essere eliminato definitivamente da un altro criterio.
  
![Diagramma dei principi di conservazione](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Per comprendere in che modo le diverse etichette con azioni di conservazione vengono applicate al contenuto, tenere presente questi principi di conservazione:
  
1. **La conservazione prevale sull'eliminazione.** Si supponga di avere un criterio di conservazione che indica di eliminare la posta elettronica di Exchange dopo tre anni e un altro criterio di conservazione che indica di conservare la posta elettronica di Exchange per cinque anni e quindi eliminarla. Il contenuto che supera i tre anni verrà eliminato e nascosto agli utenti, ma comunque conservato nella cartella Elementi ripristinabili fino a raggiungere i cinque anni, quando verrà eliminato definitivamente. 
    
2. **Prevale il periodo di conservazione più lungo.** Se un contenuto è soggetto a più criteri di conservazione, verrà mantenuto fino al termine del periodo di conservazione più lungo. 
    
3. **L'inclusione esplicita prevale sull'inclusione implicita.** Questo significa che: 
    
    1. Se un utente assegna manualmente un'etichetta di conservazione con impostazioni di conservazione a un elemento, ad esempio un messaggio di posta elettronica di Exchange o un documento di OneDrive, l'etichetta di conservazione ha la precedenza sui criteri assegnati a livello di sito o di cassetta postale e su un'etichetta di conservazione predefinita assegnata tramite la raccolta documenti. Ad esempio, se l'etichetta di conservazione esplicita indica di conservare per dieci anni, ma i criteri di conservazione assegnati dal sito indicano di conservare solo per cinque anni, l'etichetta di conservazione ha la precedenza. Le etichette di conservazione applicate automaticamente sono considerate implicite e non esplicite, perché vengono applicate automaticamente da Office 365.
    
    2. Se un criterio di conservazione include una posizione specifica, ad esempio la cassetta postale o l'account di OneDrive for Business di un particolare utente, il criterio ha la precedenza su un altro criterio di conservazione applicato alle cassette postali o agli account di OneDrive for Business di tutti gli utenti, ma che non include specificamente la cassetta postale di quell'utente.
    
4. **Prevale il periodo di eliminazione più breve.** Analogamente, se un contenuto è soggetto a più criteri di eliminazione (senza conservazione), verrà eliminato alla fine del periodo di conservazione più breve. 
    
I principi di conservazione funzionano come un flusso di risoluzione di conflitti dall'alto verso il basso: se le regole applicate da tutti i criteri o le etichette sono le stesse in un determinato livello, il flusso si sposta verso il basso al livello successivo per determinare la priorità di applicazione di ogni regola.
  
Infine, un criterio o un'etichetta di conservazione non può eliminare definitivamente qualsiasi contenuto che si trovi in stato di blocco per eDiscovery. Quando il blocco viene rilasciato, il contenuto torna idoneo per il processo di pulizia descritto in precedenza.
  
## <a name="use-retention-labels-instead-of-these-features"></a>Usare le etichette di conservazione anziché queste funzionalità

Le etichette di conservazione possono facilmente essere rese disponibili per un'intera organizzazione e il relativo contenuto in Office 365, compresi Exchange, SharePoint, OneDrive e gruppi di Office 365. Se è necessario classificare il contenuto o gestire i record ovunque in Office 365, è consigliabile usare le etichette di conservazione.
  
Per classificare il contenuto o gestire i record in Office 365 esistono già altre funzionalità, elencate di seguito, che continueranno a funzionare insieme alle etichette di conservazione. Anche se ci sono istanze in cui l'implementazione delle etichette di conservazione è diversa rispetto alle funzionalità precedenti, l'evoluzione delle etichette di conservazione determinerà il futuro della gestione dei record in Office 365. In futuro, quindi, per la governance dei dati si consiglia di usare le etichette di conservazione invece di queste funzionalità.
  
### <a name="exchange-online"></a>Exchange Online

- [Tag di conservazione e criteri di conservazione](https://go.microsoft.com/fwlink/?linkid=846125), noti anche come [gestione record di messaggistica](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminazione) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

- [Configurazione di gestione dei record sul posto](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (conservazione) 
    
- [Introduzione al Centro record](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (conservazione) 
    
- [Criteri di gestione delle informazioni ](intro-to-info-mgmt-policies.md) (solo eliminazione) 
    
## <a name="permissions"></a>Autorizzazioni

Ai membri del team di conformità che creeranno etichette di conservazione è necessario assegnare autorizzazioni per il Centro sicurezza &amp; conformità. Per impostazione predefinita, l'amministratore del tenant ha accesso a questa posizione e può fornire ai responsabili della conformità e ad altre persone l'accesso al Centro sicurezza &amp; conformità, senza concedere tutte le autorizzazioni di un amministratore del tenant. A questo scopo, è consigliabile accedere alla pagina **Autorizzazioni** del Centro sicurezza &amp; conformità, modificare il gruppo di ruoli **Amministratore conformità** e aggiungere membri a tale gruppo di ruoli. 
  
Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie solo per creare e applicare etichette di conservazione e criteri di etichetta. L'applicazione dei criteri non richiede l'accesso al contenuto.  
## <a name="find-the-powershell-cmdlets-for-labels"></a>Trovare i cmdlet di PowerShell per le etichette

Per usare i cmdlet per le etichette è necessario:
  
1. [Connettersi a PowerShell in Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Usare questi cmdlet del Centro sicurezza e conformità di Office 365:

  - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
