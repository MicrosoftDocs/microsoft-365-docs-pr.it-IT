---
title: Esplora minacce e rilevamenti in tempo reale
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Informazioni sull'utilizzo di Esplora risorse e sui rilevamenti in tempo reale nel centro sicurezza e &amp; conformità per esaminare e rispondere alle minacce in modo efficace ed efficiente.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 20b13e177a69d981a4c6793d4810256e33158a35
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414263"
---
# <a name="threat-explorer-and-real-time-detections"></a>Esplora minacce e rilevamenti in tempo reale

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se l'organizzazione dispone di [office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) ed è necessario disporre [delle autorizzazioni necessarie](#required-licenses-and-permissions), sono disponibili **esplorazioni** o **rilevamenti in tempo reale** (in precedenza i *report in tempo reale* , [vedere What ' s New](#new-features-in-threat-explorer-and-real-time-detections)!). Nel centro sicurezza & conformità, accedere a **gestione minacce**, quindi scegliere **Esplora risorse** _o_ **rilevamenti in tempo reale**.

|Con ATP piano 2, è possibile vedere:|Con ATP piano 1, è possibile visualizzare le informazioni seguenti:|
|---|---|
|![Esplora minacce](../../media/threatmgmt-explorer.png)|![Rilevamenti in tempo reale](../../media/threatmgmt-realtimedetections.png)|
|

Con Esplora risorse (o rilevamenti in tempo reale), si dispone di un report potente che consente al team di operazioni di sicurezza di analizzare e rispondere alle minacce in modo efficace ed efficiente. Il report è simile all'immagine seguente:

![Passare \> a gestione minacce](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con questo rapporto, è possibile:

- [Vedere malware detected by Microsoft 365 Security features](#see-malware-detected-in-email-by-technology)
- [Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto](#view-data-about-phishing-urls-and-click-verdict)
- [Avviare un processo di analisi e risposta automatizzato da una visualizzazione in Explorer](#start-automated-investigation-and-response) (solo ATP piano 2)
- ... [Esaminare messaggi di posta elettronica dannosi e altro ancora](#more-ways-to-use-explorer-or-real-time-detections)!

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Miglioramenti dell'esperienza in Esplora minacce e rilevamenti di Real-Time

Nell'ambito del miglioramento del processo di ricerca, sono stati apportati alcuni aggiornamenti a Threat Explorer e ai rilevamenti di Real-Time. Si tratta di miglioramenti ' Experience ', con l'obiettivo di rendere l'esperienza di caccia più coerente. Queste modifiche sono descritte di seguito:

- [Miglioramenti del fuso orario](#timezone-improvements)
- [Aggiornamento nel processo di aggiornamento](#update-in-the-refresh-process)
- [Drill-down del grafico da aggiungere ai filtri](#chart-drilldown-to-add-to-filters)
- [Negli aggiornamenti delle informazioni sui prodotti](#in-product-information-updates)

### <a name="timezone-improvements"></a>Miglioramenti del fuso orario

Verrà mostrato il fuso orario per i record di posta elettronica all'interno del portale, nonché per i dati esportati. Il fuso orario sarà visibile tra le esperienze come la griglia di posta elettronica, i dettagli a comparsa, la sequenza temporale e i messaggi di posta elettronica simili, in modo che il fuso orario del set di risultati sia chiaro per l'utente.

![Visualizzazione del fuso orario in Esplora risorse](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Aggiornamento nel processo di aggiornamento

Sono stati segnalati commenti e suggerimenti relativi alla confusione con l'aggiornamento automatico (ad esempio, per la data, non appena si modifica la data, la pagina viene aggiornata) e l'aggiornamento manuale (per altri filtri). Analogamente, la rimozione dei filtri porta all'aggiornamento automatico, in questo modo le situazioni in cui la modifica dei diversi filtri durante la modifica della query possono causare esperienze di ricerca incoerenti. Per risolvere questo passaggio, si passa a un meccanismo di filtraggio manuale.
Da un punto di vista dell'esperienza, l'utente può applicare e rimuovere i diversi filtri (dall'insieme di filtri e la data) e premere il pulsante Aggiorna per filtrare i risultati dopo aver terminato la query. Il pulsante Aggiorna è stato anche aggiornato per definirlo chiaramente sullo schermo. Sono state aggiornate anche le descrizioni comandi e la documentazione del prodotto in questa modifica.

![Fare clic su Aggiorna per filtrare i risultati](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Drill-down del grafico da aggiungere ai filtri

Sarà ora possibile fare clic sui valori della legenda del grafico per aggiungere il valore come filtro. Tenere presente che sarà comunque necessario fare clic sul pulsante Aggiorna per filtrare i risultati come parte della modifica descritta in alto.

![Drill-down tramite grafici da filtrare](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Negli aggiornamenti delle informazioni sui prodotti

È inoltre possibile visualizzare ulteriori dettagli all'interno del prodotto. Ad esempio, il numero totale di risultati della ricerca all'interno della griglia (vedere di seguito), nonché i miglioramenti relativi alle etichette, ai messaggi di errore e alle descrizioni comandi, per fornire ulteriori informazioni sui filtri, l'esperienza di ricerca e il set di risultati.

![Visualizzare le informazioni sul prodotto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Funzionalità estese in Esplora minacce

### <a name="top-targeted-users"></a>Utenti di destinazione principali

Oggi viene esposto l'elenco degli utenti di destinazione principali nella visualizzazione malware per i messaggi di posta elettronica (all'interno della sezione principali famiglie di malware). Si estenderà questa visualizzazione all'interno di phishing e tutte le visualizzazioni di posta elettronica, in cui sarà possibile visualizzare i primi cinque utenti mirati insieme al numero di tentativi per ogni utente per la visualizzazione corrispondente (ad esempio, per la visualizzazione di phishing, sarà possibile visualizzare il numero di tentativi di phishing).
È inoltre possibile esportare l'elenco di utenti di destinazione fino a un massimo di 3000, oltre al numero di tentativi di analisi offline per ogni visualizzazione di posta elettronica. Oltre a questo, selezionando No. di tentativi (ad esempio, 13 tentativi di seguito) aprirebbe una visualizzazione filtrata in Esplora minacce, in modo da poter guardare maggiori dettagli tra i messaggi di posta elettronica e le minacce per tale utente.

![Utenti di destinazione principali](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a>Regole di trasporto di Exchange
Nell'ambito dell'arricchimento dei dati, è inoltre necessario essere in grado di visualizzare tutte le diverse regole di trasporto applicate a un messaggio. Queste informazioni saranno presenti all'interno della visualizzazione griglia di posta elettronica (per visualizzare questa opzione, selezionare le opzioni di colonna nella griglia e aggiungere la regola di trasporto di Exchange dalle opzioni di colonna nella griglia), nonché il riquadro a comparsa dettagli nel messaggio di posta elettronica.
È possibile visualizzare sia il GUID che il nome delle regole di trasporto che sono state applicate al messaggio. Inoltre, è possibile cercare i messaggi utilizzando il nome della regola di trasporto. Si tratta di una ricerca "contiene" che indica che è possibile effettuare ricerche anche utilizzando ricerche parziali.

#### <a name="important-note"></a>Nota importante:
La disponibilità del nome e della ricerca di ETR dipenderà dal ruolo specifico che è stato assegnato all'utente. Per visualizzare i nomi e la ricerca di ETR, è necessario disporre di uno dei ruoli e delle autorizzazioni seguenti.  Se non si dispone di uno dei ruoli seguenti assegnati all'utente, non sarà possibile visualizzare i nomi delle regole di trasporto e cercare i messaggi utilizzando i nomi di ETR. Tuttavia, sarà possibile visualizzare l'etichetta di ETR e le informazioni sui GUID all'interno dei dettagli di posta elettronica. Le altre esperienze che riguardano la visualizzazione dei record nelle griglie di posta elettronica, l'comparsa della posta elettronica, i filtri e l'esportazione non sono interessati.

- EXO only-prevenzione della perdita di dati: All
- Solo EXO-O365SupportViewConfig: All
- AAD o EXO-Security admin: All
- AAD o EXO-Security Reader: tutti i
- Solo EXO-regole di trasporto: tutte
- Configurazione solo EXO-View-Only: All

All'interno della griglia di posta elettronica, del riquadro a comparsa dei dettagli e del CSV esportato, il ETRs viene presentato con un nome/GUID come illustrato di seguito.

![Regole di trasporto di Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Connettori in ingresso

I connettori sono una raccolta di istruzioni che personalizzano la modalità di flusso della posta elettronica da e verso l'organizzazione Microsoft 365 o Office 365, con la possibilità di applicare eventuali restrizioni o controlli di sicurezza. In Esplora minacce è ora possibile visualizzare i connettori correlati a un messaggio di posta elettronica e cercare i messaggi di posta elettronica utilizzando i nomi dei connettori.
La ricerca dei connettori è "contiene" in natura, il che significa che le ricerche di parole chiave parziali dovrebbero funzionare anche.
All'interno della visualizzazione griglia principale, del riquadro a comparsa dei dettagli e del CSV esportato, i connettori vengono visualizzati nel formato nome/GUID, come illustrato di seguito:

![Dettagli del connettore](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuove funzionalità in Esplora minacce e rilevamenti in tempo reale

Tre nuove funzionalità aggiunte in Esplora minacce e rilevamenti in tempo reale:

- [Anteprima della posta elettronica e scaricare il corpo della posta elettronica](#preview-email-header-and-download-email-body)
- [Sequenza temporale della posta elettronica](#email-timeline)
- [Esportare i dati di clic su URL](#export-url-click-data)

Queste nuove funzionalità sono descritte di seguito.

### <a name="preview-email-header-and-download-email-body"></a>Anteprima della posta elettronica e scaricare il corpo della posta elettronica

La possibilità di visualizzare in anteprima l'intestazione di un messaggio di posta elettronica e di scaricare il corpo della posta elettronica sono nuove funzionalità disponibili in Esplora minacce. Gli amministratori saranno in grado di analizzare le intestazioni o i messaggi di posta elettronica scaricati per individuare eventuali minacce. Poiché il download dei messaggi di posta elettronica può rischiare l'esposizione delle informazioni, questo processo è controllato dal controllo di accesso basato sui ruoli (RBAC). Un nuovo ruolo, l' *Anteprima*, deve essere aggiunto a un altro gruppo di ruoli, ad esempio operazioni di sicurezza o amministratore della sicurezza, per garantire la possibilità di scaricare i messaggi di posta elettronica e visualizzare le intestazioni di anteprima in tutte le visualizzazioni.

Ma Explorer (e rilevamenti in tempo reale) aggiunge anche nuovi campi creati per fornire un'immagine più completa della posizione in cui i messaggi di posta elettronica atterrano. Parte dell'obiettivo di questa modifica è facilitare la ricerca per gli addetti alle operazioni di sicurezza, ma il risultato della rete è la conoscenza del percorso dei messaggi di posta elettronica problematici.

Come è possibile eseguire questa operazione? Lo stato di recapito è ora suddiviso in due colonne:

- **Azione di recapito** -qual è lo stato di questo messaggio di posta elettronica?
- **Percorso di recapito** -dove è stato instradato il messaggio di posta elettronica come risultato?

Azione di recapito è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

|Consegnato|Junked|Bloccato|Sostituito|
|---|---|---|---|
|La posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.|La posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica in tali cartelle.|Tutti i messaggi di posta elettronica in quarantena, che non sono riusciti o sono stati eliminati. Questo è completamente inaccessibile dall'utente.|Qualsiasi messaggio di posta elettronica in cui gli allegati dannosi vengono sostituiti dai file. txt che lo stato dell'allegato è dannoso.|

|Consegnato|Junked|Bloccato|Sostituito|
|---|---|---|---|
|La posta elettronica è stata recapitata alla posta in arrivo dell'utente o a un'altra cartella e l'utente può accedervi direttamente.|La posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica in tali cartelle.|Tutti i messaggi di posta elettronica in quarantena, che non sono riusciti o sono stati eliminati e non sono accessibili dall'utente.|Tutti i messaggi di posta elettronica in cui gli allegati dannosi sono stati sostituiti da file txt che affermano che gli allegati sono pericolosi.|
|

Ecco cosa può essere visualizzato dall'utente e cosa non è possibile:

|Accessibile per gli utenti finali|Inaccessibile per gli utenti finali|
|---|---|
|Consegnato|Bloccato|
|Junked|Sostituito|

Il percorso di recapito consente di visualizzare i risultati dei criteri e i rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione intrapresa quando viene trovata una posta elettronica problematica. Di seguito sono riportati i possibili valori del percorso di recapito:

- **Posta in arrivo o cartella**: la posta elettronica è in posta in arrivo o in una cartella (in base alle regole di posta elettronica).
- **On-Prem o External**: la cassetta postale non esiste sul cloud ma è in locale.
- **Cartella posta indesiderata**: l'indirizzo di posta elettronica si trova nella cartella Junk di un utente.
- **Cartella Posta eliminata**: il messaggio nella cartella elementi eliminati di un utente.
- **Quarantine**: l'indirizzo di posta elettronica in quarantena e non è incluso nella cassetta postale di un utente.
- **Errore**: il messaggio di posta elettronica non è riuscito a raggiungere la cassetta postale.
- **Eliminato**: il messaggio di posta elettronica viene perso da qualche parte nel flusso di posta.

### <a name="email-timeline"></a>Sequenza temporale della posta elettronica

La **cronologia della posta elettronica** è un'altra funzionalità di Esplora risorse che consente di migliorare l'esperienza di ricerca per gli amministratori. La randomizzazione viene ridotta perché è necessario meno tempo per controllare posizioni diverse per cercare di comprendere l'evento. Quando più eventi si verificano in un messaggio di posta elettronica o vicino allo stesso tempo, gli eventi vengono visualizzati in una visualizzazione sequenza temporale. In effetti, alcuni eventi che si verificano dopo il recapito alla posta verranno acquisiti nella colonna ' Special Action '. La combinazione delle informazioni dalla sequenza temporale di quella posta con l'azione speciale intrapresa sul post-recapito della posta darà agli amministratori informazioni su come funzionano i propri criteri, in cui la posta è stata definitivamente instradata e, in alcuni casi, qual è stata la valutazione finale.

Per ulteriori informazioni sull'analisi dei messaggi di posta elettronica dannosi, vedere [indagare e correggere il messaggio di posta elettronica dannoso che è stato recapitato in Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Esportare i dati di clic su URL

Sarà inoltre possibile esportare i report per i clic URL in Microsoft Excel per visualizzare sia l'ID del messaggio di rete, sia il loro verdetto di clic, in cui è possibile capire dove è stato creato il traffico dell'URL. Ecco come funziona. A partire da Threat Management sulla barra di avvio veloce di Office 365, fare clic su questa catena:

**Gestione risorse** \> **Visualizzazione phishing** \> **Clic su** \> URL **principali o clic** \> principali per gli URL **Fare clic su qualsiasi record per aprire il riquadro a comparsa URL**

Quando si fa clic su un URL nell'elenco, verrà visualizzato un nuovo pulsante Esporta nel riquadro di volo. Utilizzare questo pulsante per spostare i dati in un foglio di calcolo di Excel per semplificare la creazione di report.

È possibile accedere allo stesso percorso nel rapporto rilevamenti in tempo reale, come indicato di seguito:

**Gestione risorse** \> Rilevamenti in tempo **reale** \> **Visualizzazione phishing** \> **URL** \> **URL principali o clic principali** \> **Fare clic su qualsiasi record per aprire il riquadro a comparsa URL** \> **Passare alla scheda clic.**

> [!TIP]
> ID messaggio di rete mappare il clic di nuovo su mail specifiche quando si esegue una ricerca tramite Explorer o gli strumenti di terze parti associati tramite ID messaggio di rete. La ricerca nell'ID messaggio di rete fornirà agli amministratori la posta elettronica specifica associata a un risultato di clic. In caso di esportazione, l'identificazione correlata dell'ID messaggio di rete rende l'analisi più rapida e potente.

![Scheda clic in Esplora risorse](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Vedere malware rilevato in posta elettronica dalla tecnologia

Si supponga di voler vedere malware rilevato nella posta elettronica, tramite la tecnologia Microsoft 365. A tale scopo, utilizzare la visualizzazione [posta elettronica > malware](threat-explorer-views.md#email--malware) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ), scegliere **gestione minacce**  >  **Explorer** (o **rilevamenti in tempo reale**). In questo esempio viene utilizzato Esplora.

2. Scegliere malware **tramite posta elettronica**dal menu **Visualizza**  >  **Malware**.

   ![Menu Visualizza per Esplora risorse](../../media/ExplorerViewEmailMalwareMenu.png)

3. Fare clic su **mittente**e quindi scegliere tecnologia di rilevamento di **base**  >  **Detection technology**.

   Le tecnologie di rilevamento sono ora disponibili come filtri per il report.

   ![Tecnologie di rilevamento di malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Selezionare un'opzione e quindi fare clic sul pulsante **Aggiorna** per applicare il filtro.

   ![Tecnologia di rilevamento selezionata](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Il rapporto viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione di tecnologia selezionata. Da qui, è possibile eseguire un'ulteriore analisi.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto

Si supponga di voler visualizzare i tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL consentiti, bloccati e ignorati. L'identificazione degli URL che sono stati cliccati richiede la configurazione di [collegamenti sicuri](atp-safe-links.md) . Assicurarsi di aver configurato i criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) per la protezione e la registrazione di un clic con i collegamenti sicuri per il tempo di clic.

Per esaminare gli URL di phishing nei messaggi e fare clic su URL nei messaggi di phishing, utilizzare la visualizzazione di [posta elettronica > phishing](threat-explorer-views.md#email--phish) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ), scegliere **gestione minacce**  >  **Explorer** (o **rilevamenti in tempo reale**). In questo esempio viene utilizzato Esplora.

2. Nel menu **Visualizza** scegliere **posta elettronica**  >  **phishing**.

   ![Menu Visualizza per Esplora risorse](../../media/ExplorerViewEmailPhishMenu.png)

3. Fare clic su **sender**e quindi scegliere **urls**  >  **Click verdict**.

4. Selezionare una o più opzioni, ad esempio **bloccate** e **bloccate**, e quindi fare clic sul pulsante **Aggiorna** che si trova nella stessa riga delle opzioni per applicare il filtro. (Non aggiornare la finestra del browser.)

   ![URL e fare clic su verdetti](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    Il rapporto viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del rapporto:

   - Gli URL **principali** sono gli URL contenuti nei messaggi che sono stati filtrati fino a e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione posta elettronica di phishing, in genere l'elenco conterrà URL legittimi. I pirati informatici includono una combinazione di URL buoni e cattivi nei messaggi per cercare di farli recapitare, ma renderà i collegamenti dannosi più interessanti per l'utente da fare clic su. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica (ma si noti che questa colonna è nascosta per semplificare la visualizzazione).

   - I **clic principali** sono gli URL con collegamenti sicuri che sono stati selezionati, ordinati in base al numero di clic totale (la colonna non viene visualizzata per semplificare la visualizzazione). Numeri totali per colonna indicano i collegamenti sicuri fare clic su conteggio verdetto per ogni URL selezionato. Nella visualizzazione posta elettronica di phishing, si tratta di URL più spesso sospetti o maligni, ma possono includere URL che non sono minacce, ma che sono presenti nei messaggi di phishing. Gli URL che fanno clic su collegamenti non spostati non verranno visualizzati qui.

   Le due tabelle degli URL visualizzano gli URL principali nei messaggi di posta elettronica di phishing tramite l'azione e la posizione di recapito e visualizzano gli URL che sono stati bloccati (o visitati nonostante un avviso), in modo da poter capire quali potenziali collegamenti non validi sono stati ricevuti dagli utenti e interagito con gli utenti. Da qui, è possibile eseguire un'ulteriore analisi. Ad esempio, al di sotto del grafico, è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.

   ![URL di Esplora risorse bloccati](../../media/ExplorerPhishClickVerdictURLs.png)

   Selezionare un URL per visualizzare informazioni più dettagliate.

   > [!NOTE]
   > Nella finestra di dialogo a comparsa URL, il filtro dei messaggi di posta elettronica viene rimosso per visualizzare la visualizzazione completa dell'esposizione dell'URL nell'ambiente in uso. In questo modo è possibile filtrare i messaggi di posta elettronica in Esplora per quelli che si sono preoccupati, individuare URL specifici che sono potenziali minacce e quindi espandere la propria comprensione dell'esposizione all'URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL alla visualizzazione Esplora risorse.

### <a name="interpretation-of-different-click-verdicts"></a>Interpretazione delle diverse sentenze di clic

All'interno di comparsa di posta elettronica o URL, clic principali e all'interno delle nostre esperienze di filtraggio, verranno visualizzati diversi valori di clic come parte dell'esperienza di caccia. Di seguito sono riportati i valori possibili di clic verdetti e la loro interpretazione:

- **None**: non è stato possibile acquisire il verdetto per l'URL. È possibile che l'utente abbia fatto clic su di esso tramite l'URL.
- **Consentito**: all'utente è stato consentito di passare all'URL.
- **Bloccato**: l'utente è stato bloccato dall'esplorazione all'URL.
- **Verdetto in sospeso**: l'utente è stato presentato con la pagina di detonazione in sospeso.
- **Bloccato sottoposto a override**: l'utente è stato bloccato dall'esplorazione all'URL. Tuttavia, l'utente ha scavalcato il blocco per passare all'URL.
- **Verdetto in sospeso bypassato**: l'utente è stato presentato con la pagina di detonazione; Tuttavia, l'utente ha ripercorso la pagina per passare all'URL.
- **Errore**: l'utente è stato presentato con la pagina di errore. Questo può anche significare che si è verificato un errore nell'acquisizione del verdetto.
- **Errore**: si è verificato l'eccezione sconosciuta durante l'acquisizione del verdetto. È possibile che l'utente abbia fatto clic su di esso tramite l'URL.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come posta indesiderata, non indesiderata o phishing tramite il [componente aggiuntivo per Outlook e Outlook sul Web](enable-the-report-message-add-in.md). A tale scopo, utilizzare la visualizzazione [> invii di posta elettronica](threat-explorer-views.md#email--submissions) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ), scegliere **gestione minacce**  >  **Explorer** (o **rilevamenti in tempo reale**). In questo esempio viene utilizzato Esplora.

2. Scegliere **invii di posta elettronica**dal menu **Visualizza**  >  **Submissions**.

   ![Menu Visualizza per Esplora risorse](../../media/explorer-view-menu-email-user-reported.png)

3. Fare clic su **mittente**e quindi scegliere tipo di report di **base**  >  **Report type**.

4. Selezionare un'opzione, ad esempio **phishing**, e quindi fare clic sul pulsante **Aggiorna** .

   ![Phishing segnalati dall'utente](../../media/EmailUserReportedReportType.png)

Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come tentativo di phishing. È possibile utilizzare queste informazioni per eseguire un'ulteriore analisi e, se necessario, regolare i [criteri di anti-phishing ATP](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Avviare l'analisi e la risposta automatizzata

> [!NOTE]
> Le funzionalità di ricerca e risposta automatizzate sono disponibili in **office 365 ATP piano 2** e **Office 365 E5**.

(Nuovo!) L' [analisi e la risposta automatizzate](automated-investigation-response-office.md) sono in grado di salvare il team delle operazioni di sicurezza molto tempo ed energie nell'analisi e nell'attenuazione di attacchi cibernetici. Oltre a configurare gli avvisi che possono attivare un PlayBook per la sicurezza, è possibile avviare un processo di analisi e risposta automatizzato da una visualizzazione di Esplora risorse.

Per ulteriori informazioni, vedere [esempio: un amministratore della sicurezza attiva un'analisi da Esplora risorse](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Altre modalità di utilizzo di Esplora risorse (o rilevamenti in tempo reale)

Oltre agli scenari descritti in questo articolo, sono disponibili molte altre opzioni per la creazione di report con Esplora risorse (o rilevamenti in tempo reale).

- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Ottenere una panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)](threat-explorer-views.md)
- [Indagine e reazione automatizzate in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

È necessario disporre di [Office 365 ATP](office-365-atp.md) per ottenere rilevamenti di Esplora risorse o in tempo reale.

- Explorer è incluso in Office 365 ATP piano 2.
- Il rapporto sui rilevamenti in tempo reale è incluso in Office 365 ATP Plan 1.
- Pianificare l'assegnazione delle licenze per tutti gli utenti che devono essere protetti da Office 365 ATP. (Esplora risorse o rilevamenti in tempo reale mostrano i dati di rilevamento per gli utenti con licenza).

Per visualizzare e utilizzare esplorazioni o rilevamenti in tempo reale, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza.

- Per il &amp; Centro sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:

  - Gestione organizzazione
  - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Ruolo con autorizzazioni di lettura per la sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Gestione organizzazione
  - Gestione organizzazione in sola visualizzazione
  - Ruolo Destinatari di sola lettura
  - Gestione della conformità

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:

- [Autorizzazioni nel centro sicurezza e &amp; conformità](permissions-in-the-security-and-compliance-center.md)
- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Alcune differenze tra Esplora minacce e rilevamenti in tempo reale

- Il rapporto sui **rilevamenti in tempo reale** è disponibile in Office 365 ATP Plan 1, mentre l' **esploratore di minacce** è disponibile in Office 365 ATP piano 2.
- Il rapporto sui **rilevamenti in tempo reale** consente di visualizzare i rilevamenti in tempo reale. **Threat Explorer** Anche questo consente di visualizzare ulteriori dettagli relativi a un determinato attacco.
- La visualizzazione di **tutti i messaggi di posta elettronica** è disponibile in **Esplora minacce** (e non è presente nel rapporto **rilevamenti in tempo reale** ).
- Altre funzionalità di filtro e le azioni disponibili sono incluse in **Esplora minacce**.

Per ulteriori informazioni, vedere [Descrizione del servizio ATP di Office 365: disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
