---
title: Esplora minacce e rilevamenti in tempo reale
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Usare Esplora risorse e i rilevamenti in tempo reale nel Centro sicurezza e conformità per analizzare &amp; e rispondere in modo efficiente alle minacce.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5cbb8bd57a2e9bde8d19c960a71066d3ea5531c1
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233643"
---
# <a name="threat-explorer-and-real-time-detections"></a>Esplora minacce e rilevamenti in tempo reale


**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se [l'organizzazione](#new-features-in-threat-explorer-and-real-time-detections)dispone di Microsoft Defender per [Office 365](office-365-atp.md)e si dispone delle autorizzazioni [necessarie,](#required-licenses-and-permissions)si dispone di rilevamenti di **Esplora** risorse o in tempo reale **(in** precedenza report in tempo *reale,* vedere le novità!). Nel Centro sicurezza & conformità passare a **Gestione** minacce e quindi scegliere **Esplora risorse** _o_ **rilevamenti in tempo reale.**


|Con Microsoft Defender per Office 365 Piano 2, viene visualizzato:|Con Microsoft Defender per Office 365 Piano 1, viene visualizzato:|
|---|---|
|![Esplora minacce](../../media/threatmgmt-explorer.png)|![Rilevamenti in tempo reale](../../media/threatmgmt-realtimedetections.png)|
|

Esplora risorse o rilevamenti in tempo reale consentono al team delle operazioni di sicurezza di analizzare e rispondere alle minacce in modo efficiente. Il report è simile all'immagine seguente:

![Passare a Esplora gestione \> minacce](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con questo report, è possibile:

- [Visualizzare il malware rilevato dalle funzionalità di sicurezza di Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Visualizzare l'URL di phishing e fare clic sui dati del verdetto](#view-phishing-url-and-click-verdict-data)
- [Avviare un processo di analisi e risposta](#start-automated-investigation-and-response) automatizzato da una visualizzazione in Esplora risorse (solo Defender per Office 365 Piano 2)
- [Analizzare la posta elettronica dannosa e altro ancora](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Miglioramenti a Esplora minacce e rilevamenti in tempo reale

### <a name="tags-in-threat-explorer"></a>Tag in Esplora minacce

> [!NOTE]
> La funzionalità tag utente è disponibile in *Anteprima,* non è disponibile per tutti gli utenti ed è soggetta a modifiche. Per informazioni sulla pianificazione dei rilasci, consultare la roadmap di Microsoft 365.

I tag utente identificano gruppi specifici di utenti in Microsoft Defender per Office 365. Per ulteriori informazioni sui tag, incluse le licenze e la configurazione, vedere [Tag utente.](user-tags.md)

In Esplora minacce puoi visualizzare informazioni sui tag utente nelle esperienze seguenti.

#### <a name="email-grid-view"></a>Visualizzazione griglia della posta elettronica

La **colonna Tag** nella griglia della posta elettronica contiene tutti i tag applicati alle cassette postali del mittente o del destinatario. Per impostazione predefinita, i tag di sistema come gli account di priorità vengono visualizzati per primi.

> [!div class="mx-imgBorder"]
> ![Filtrare i tag nella visualizzazione griglia della posta elettronica](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtro

È possibile utilizzare i tag come filtro. Cerca solo in scenari con account con priorità o tag utente specifici. È inoltre possibile escludere i risultati con determinati tag. Combina questa funzionalità con altri filtri per restringere l'ambito dell'indagine.

[![Tag di filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Tag non filtrati](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Riquadro a comparsa Dettagli messaggio di posta elettronica
Per visualizzare i singoli tag per il mittente e il destinatario, selezionare l'oggetto per aprire il riquadro a comparsa dei dettagli del messaggio. Nella scheda **Riepilogo,** i tag mittente e destinatario vengono visualizzati separatamente, se sono presenti per un messaggio di posta elettronica.
Le informazioni sui singoli tag per mittente e destinatario si estendono anche ai dati CSV esportati, dove è possibile visualizzare questi dettagli in due colonne separate.

> [!div class="mx-imgBorder"]
> ![Tag dettagli posta elettronica](../../media/tags-flyout.png)

Le informazioni sui tag vengono visualizzate anche nel riquadro a comparsa dei clic sull'URL. To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Seleziona un singolo riquadro a comparsa URL per visualizzare ulteriori dettagli sui clic per tale URL, inclusi i tag associati a tale clic.

> [!div class="mx-imgBorder"]
> ![Tag URL](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Miglioramenti all'esperienza di ricerca delle minacce (imminente)

### <a name="updated-threat-information-for-emails"></a>Informazioni aggiornate sulle minacce per i messaggi di posta elettronica

Ci siamo concentrati sui miglioramenti della piattaforma e della qualità dei dati per aumentare l'accuratezza e la coerenza dei dati per i record di posta elettronica. I miglioramenti includono il consolidamento delle informazioni di pre-recapito e post-recapito, ad esempio le azioni eseguite su un messaggio di posta elettronica come parte del processo ZAP, in un unico record. Sono inclusi ulteriori dettagli come verdetto di posta indesiderata, minacce a livello di entità (ad esempio, quale URL era dannoso) e posizioni di recapito più recenti.

Dopo questi aggiornamenti, verrà visualizzata una singola voce per ogni messaggio, indipendentemente dal diverso evento di post-recapito che influisce sul messaggio. Le azioni possono includere ZAP, correzione manuale (che significa azione dell'amministratore), recapito dinamico e così via.

Oltre a mostrare minacce malware e phishing, viene visualizzato il verdetto di posta indesiderata associato a un messaggio di posta elettronica. All'interno del messaggio di posta elettronica, vedere tutte le minacce associate al messaggio di posta elettronica insieme alle tecnologie di rilevamento corrispondenti. Un messaggio di posta elettronica può avere zero, una o più minacce. You'll see the current threats in the **Details** section of the email flyout. Per più minacce (ad esempio malware e phishing), il campo **tecnico** di rilevamento mostra il mapping di rilevamento delle minacce, che è la tecnologia di rilevamento che ha identificato la minaccia.

L'insieme di tecnologie di rilevamento ora include nuovi metodi di rilevamento, nonché tecnologie di rilevamento della posta indesiderata. È possibile utilizzare lo stesso set di tecnologie di rilevamento per filtrare i risultati nelle diverse visualizzazioni della posta elettronica (Malware, Phish, All Email).

> [!NOTE]
> L'analisi dei verdetti potrebbe non essere necessariamente collegata a entità. Ad esempio, un messaggio di posta elettronica potrebbe essere classificato come posta indesiderata o di phish, ma non vi sono URL contrassegnati con un verdetto di phish/spam. Questo perché i filtri valutano anche il contenuto e altri dettagli per un messaggio di posta elettronica prima di assegnare un verdetto.

#### <a name="threats-in-urls"></a>Minacce negli URL

È ora possibile visualizzare la minaccia specifica per un URL nella scheda Dettagli riquadro **a comparsa della posta** elettronica. La minaccia può essere *malware,* *phish,* *posta* indesiderata o *nessuno.)*

> [!div class="mx-imgBorder"]
> ![Minacce URL](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Visualizzazione cronologia aggiornata (imminente)

> [!div class="mx-imgBorder"]
> ![Visualizzazione Sequenza temporale aggiornata](../../media/Email_Timeline.png)

La visualizzazione Sequenza temporale identifica tutti gli eventi di recapito e post-recapito. Include informazioni sulla minaccia identificata in quel momento per un sottoinsieme di questi eventi. La visualizzazione Sequenza temporale fornisce inoltre informazioni su qualsiasi azione aggiuntiva eseguita (ad esempio ZAP o correzione manuale), insieme al risultato di tale azione. Le informazioni sulla visualizzazione sequenza temporale includono:

- **Origine:** Origine dell'evento. Può essere admin/system/user.
- **Evento:** Include eventi di primo livello come il recapito originale, la correzione manuale, ZAP, gli invii e il recapito dinamico.
- **Azione:** L'azione specifica eseguita nell'ambito dell'azione ZAP o dell'amministratore (ad esempio, eliminazione rescisa).
- **Minacce:** Copre le minacce (malware, phish, posta indesiderata) identificate in quel momento.
- **Risultato/Dettagli:** Ulteriori informazioni sul risultato dell'azione, ad esempio se è stata eseguita come parte dell'azione ZAP/amministratore.

### <a name="original-and-latest-delivery-location"></a>Percorso di recapito originale e più recente

Attualmente, la posizione di recapito viene visualizzata nella griglia della posta elettronica e nel riquadro a comparsa della posta elettronica. Il **campo Percorso di** recapito viene rinominato Percorso di **_recapito_ originale *_. Stiamo introducendo un altro campo, _*_Posizione di recapito più recente._**

**Il percorso di recapito** originale fornisce ulteriori informazioni sulla posizione iniziale in cui è stato recapitato un messaggio di posta elettronica. **Il percorso di recapito più** recente consente di inviare un messaggio di posta elettronica dopo azioni di sistema come *ZAP* o azioni di amministratore come *Sposta in elementi eliminati.* Il percorso di recapito più recente ha lo scopo di indicare agli amministratori l'ultima posizione nota del messaggio dopo il recapito o qualsiasi azione di sistema/amministratore. Non include azioni dell'utente finale nel messaggio di posta elettronica. Ad esempio, se un utente ha eliminato un messaggio o spostato il messaggio in archivio/pst, il percorso di "recapito" del messaggio non verrà aggiornato. Tuttavia, se un'azione del sistema ha aggiornato la posizione (ad esempio, ZAP causando lo spostamento di un messaggio di posta elettronica in quarantena), **il** percorso di recapito più recente viene visualizzato come "quarantena".

> [!div class="mx-imgBorder"]
> ![Posizioni di recapito aggiornate](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Esistono alcuni casi in cui la posizione **di recapito e** **l'azione di recapito** possono essere mostrate come "sconosciute":
>
> - La posizione  di recapito potrebbe essere  "recapitata" e la posizione di recapito come "sconosciuta" se il messaggio è stato recapitato, ma una regola di Posta in arrivo ha spostato il messaggio in una cartella predefinita (ad esempio Bozza o Archivio) anziché nella cartella Posta in arrivo o Posta indesiderata.
>
> - **Il percorso di recapito** più recente può essere sconosciuto se è stata tentata un'azione di amministratore/sistema (ad esempio ZAP), ma il messaggio non è stato trovato. In genere, l'azione viene eseguita dopo che l'utente ha spostato o eliminato il messaggio. In questi casi, verificare la colonna **Risultato/Dettagli** nella visualizzazione Sequenza temporale. Cercare l'istruzione "Messaggio spostato o eliminato dall'utente".

> [!div class="mx-imgBorder"]
> ![Percorsi di recapito per la sequenza temporale](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Azioni aggiuntive

*Sono state applicate ulteriori* azioni dopo il recapito del messaggio di posta elettronica. Possono includere *ZAP,* correzione manuale *(azione* eseguita da un amministratore come eliminazione rescisa), recapito dinamico e rielaborazione *(per* un messaggio di posta elettronica che è stato rilevato come valido in modo retroattivo).

> [!NOTE]
> - Come parte delle modifiche in sospeso, il valore "Rimosso da ZAP" attualmente indicato nel filtro Azione di recapito sta per andare via. You'll have a way to search for all email with the ZAP attempt through **Additional actions.**
>
> - Saranno disponibili nuovi campi e valori per le **tecnologie di rilevamento e** azioni **aggiuntive** (in particolare per gli scenari ZAP). Sarà necessario valutare le query salvate e le query monitorate esistenti per verificare che funzionino con i nuovi valori.

> [!div class="mx-imgBorder"]

> ![Azioni aggiuntive in Esplora risorse](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Sostituzioni del sistema

*Le sostituzioni* di sistema consentono di creare eccezioni al percorso di recapito previsto di un messaggio. La posizione di recapito fornita dal sistema viene sovrascritta in base alle minacce e ad altri rilevamenti identificati dallo stack di filtro. Le sostituzioni del sistema possono essere impostate tramite criteri tenant o utente per recapitare il messaggio come suggerito dal criterio. Le sostituzioni possono identificare il recapito involontario di messaggi dannosi a causa di lacune di configurazione, ad esempio un criterio Mittente sicuro troppo ampio impostato da un utente. Questi valori di override possono essere:

- Consentito dai criteri utente: un utente crea criteri a livello di cassetta postale per consentire domini o mittenti.
- Bloccato dai criteri utente: un utente crea criteri a livello di casella di posta per bloccare domini o mittenti.
- Consentito dai criteri dell'organizzazione: i team di sicurezza dell'organizzazione impostano criteri o regole del flusso di posta di Exchange (note anche come regole di trasporto) per consentire mittenti e domini per gli utenti dell'organizzazione. Può essere per un set di utenti o per l'intera organizzazione.
- Bloccato dai criteri dell'organizzazione: i team di sicurezza dell'organizzazione impostano criteri o regole del flusso di posta per bloccare mittenti, domini, lingue dei messaggi o INDIRIZZI IP di origine per gli utenti dell'organizzazione. Può essere applicato a un insieme di utenti o all'intera organizzazione.
- Estensione di file bloccata dai criteri dell'organizzazione: il team di sicurezza di un'organizzazione blocca un'estensione di file tramite le impostazioni dei criteri antimalware. Questi valori verranno ora visualizzati nei dettagli dei messaggi di posta elettronica per facilitare le indagini. I team di Secops possono anche usare la funzionalità di filtro avanzato per filtrare le estensioni di file bloccate.

[![Sostituzioni di sistema in Esplora risorse](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![La griglia viene sovrascritta dal sistema in Esplora risorse](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Miglioramenti per l'esperienza di URL e clic

I miglioramenti includono:

- Mostra l'URL su cui è stato fatto clic completo  (inclusi eventuali parametri di query che fanno parte dell'URL) nella sezione Clic del riquadro a comparsa dell'URL. Attualmente, il dominio e il percorso dell'URL vengono visualizzati nella barra del titolo. Queste informazioni vengono estese per visualizzare l'URL completo.

- Correzioni tra filtri URL *(URL* e dominio *URL* e dominio *URL* e percorso): gli aggiornamenti influiscono sulla ricerca dei messaggi che contengono un verdetto URL/clic. È stato abilitato il supporto per le ricerche indipendenti dal protocollo, in modo da poter cercare un URL senza utilizzare `http` . Per impostazione predefinita, la ricerca URL è mappata a http, a meno che non venga specificato in modo esplicito un altro valore. Ad esempio:

   -  Eseguire la ricerca con e senza il prefisso nei campi di filtro `http://` **URL,** **URL Domain** e **URL Domain and Path.** Le ricerche dovrebbero mostrare gli stessi risultati.

   -  Cercare il prefisso `https://` **nell'URL.** Se non viene specificato alcun valore, viene `http://` utilizzato il prefisso.

   - `/` viene ignorato all'inizio e alla fine dei campi percorso **URL,** **DOMINIO URL,** **dominio URL e** percorso. `/` alla fine del campo **URL** viene ignorato.

### <a name="phish-confidence-level"></a>Livello di probabilità di phish

Il livello di probabilità di phish aiuta a identificare il grado di sicurezza con cui un messaggio di posta elettronica è stato classificato come "phish". I due valori possibili sono *High* e *Normal.* Nelle fasi iniziali, questo filtro sarà disponibile solo nella visualizzazione Phish di Esplora minacce.

[![Livello di probabilità di phish in Esplora risorse](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Segnale URL ZAP

Il segnale DELL'URL ZAP viene in genere usato per gli scenari di avviso zap phish in cui un messaggio di posta elettronica è stato identificato come phish e rimosso dopo il recapito. Questo segnale connette l'avviso con i risultati corrispondenti in Esplora risorse. Si tratta di una delle operazioni di I/O per l'avviso.

Per migliorare il processo di ricerca, abbiamo aggiornato Esplora minacce e i rilevamenti in tempo reale per rendere l'esperienza di ricerca più coerente. Le modifiche sono descritte di seguito:

- [Miglioramenti del fuso orario](#timezone-improvements)
- [Aggiornamento nel processo di aggiornamento](#update-in-the-refresh-process)
- [Drill-down grafico da aggiungere ai filtri](#chart-drilldown-to-add-to-filters)
- [Negli aggiornamenti delle informazioni sui prodotti](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrare in base ai tag utente

È ora possibile ordinare e filtrare in base ai tag utente di sistema o personalizzati per comprendere rapidamente l'ambito delle minacce. Per ulteriori informazioni, vedere [Tag utente.](user-tags.md)

> [!IMPORTANT]
> Il filtro e l'ordinamento in base ai tag utente sono attualmente in anteprima pubblica. Questa funzionalità potrebbe essere sostanzialmente modificata prima del rilascio sul mercato. Microsoft non garantisce alcuna garanzia, espressa o implicita, in relazione alle informazioni fornite.

![Colonna Tag in Esplora risorse](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Miglioramenti del fuso orario

Verrà visualizzato il fuso orario per i record di posta elettronica nel portale e per i dati esportati. Sarà visibile tra esperienze come griglia di posta elettronica, riquadro a comparsa Dettagli, Sequenza temporale della posta elettronica e messaggi di posta elettronica simili, quindi il fuso orario per il set di risultati è chiaro.

> [!div class="mx-imgBorder"]
> ![Visualizzare il fuso orario in Esplora risorse](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Aggiornamento nel processo di aggiornamento

Alcuni utenti hanno commentato la confusione con l'aggiornamento automatico (ad esempio, non appena si modifica la data, la pagina viene aggiornata) e l'aggiornamento manuale (per altri filtri). Analogamente, la rimozione dei filtri comporta l'aggiornamento automatico. La modifica dei filtri durante la modifica della query può causare esperienze di ricerca incoerenti. Per risolvere questi problemi, stiamo passando a un meccanismo di filtro manuale.

Dal punto di vista dell'esperienza, l'utente può applicare e rimuovere il diverso intervallo di filtri (dal set di filtri e dalla data) e selezionare il pulsante di aggiornamento per filtrare i risultati dopo aver definito la query. Anche il pulsante aggiorna viene sottolineato sullo schermo. Abbiamo anche aggiornato le descrizioni comandi correlate e la documentazione nel prodotto.

> [!div class="mx-imgBorder"]
> ![Selezionare Aggiorna per filtrare i risultati](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Drill-down grafico da aggiungere ai filtri

È ora possibile creare un grafico dei valori della legenda per aggiungerli come filtri. Selezionare il **pulsante Aggiorna** per filtrare i risultati.

> [!div class="mx-imgBorder"]
> ![Eseguire il drill-down dei grafici per filtrare](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Aggiornamenti delle informazioni nel prodotto

Sono ora disponibili ulteriori dettagli all'interno del prodotto, ad esempio il numero totale di risultati della ricerca all'interno della griglia (vedere di seguito). Abbiamo migliorato le etichette, i messaggi di errore e le descrizioni comandi per fornire ulteriori informazioni sui filtri, sull'esperienza di ricerca e sul set di risultati.

> [!div class="mx-imgBorder"]
> ![Visualizzare le informazioni nel prodotto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Funzionalità estese in Esplora minacce

### <a name="top-targeted-users"></a>Utenti di destinazione principali

Oggi esporremo l'elenco dei principali utenti di destinazione nella visualizzazione Malware per i messaggi di posta elettronica, nella **sezione Principali famiglie di malware.** Questa visualizzazione verrà estendeta anche nelle visualizzazioni Phish e All Email. Potrai vedere i primi cinque utenti di destinazione, insieme al numero di tentativi per ogni utente per la visualizzazione corrispondente. Ad esempio, per phish view, vedrai il numero di tentativi di phishing.

You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view. Inoltre, selezionando il numero di tentativi (ad esempio, 13 tentativi nell'immagine seguente) si aprirà una visualizzazione filtrata in Esplora minacce, in modo da visualizzare ulteriori dettagli tra i messaggi di posta elettronica e le minacce per l'utente.

> [!div class="mx-imgBorder"]
> ![Utenti di destinazione principali](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Regole di trasporto di Exchange

Come parte dell'arricchimento dei dati, sarà possibile visualizzare tutte le diverse regole di trasporto di Exchange applicate a un messaggio. Queste informazioni saranno disponibili nella visualizzazione griglia della posta elettronica. Per visualizzarla, selezionare **Opzioni colonna** nella griglia e quindi Aggiungere la regola di trasporto **di Exchange** dalle opzioni di colonna. Sarà visibile anche nel riquadro **a** comparsa Dettagli nel messaggio di posta elettronica.

Sarà possibile visualizzare sia il GUID che il nome delle regole di trasporto applicate al messaggio. Sarà possibile cercare i messaggi utilizzando il nome della regola di trasporto. Si tratta di una ricerca "Contiene", che significa che è possibile eseguire anche ricerche parziali.

#### <a name="important-note"></a>Nota importante:

La ricerca ETR e la disponibilità del nome dipendono dal ruolo specifico assegnato all'utente. Per visualizzare i nomi ETR e la ricerca, è necessario disporre di uno dei ruoli/autorizzazioni seguenti. Se non è stato assegnato alcuno di questi ruoli, non è possibile visualizzare i nomi delle regole di trasporto o cercare i messaggi utilizzando i nomi ETR. Tuttavia, è possibile visualizzare le informazioni sull'etichetta ETR e sul GUID nei dettagli del messaggio di posta elettronica. Altre esperienze di visualizzazione dei record nelle griglie di posta elettronica, nei riquadri a comparsa dei messaggi di posta elettronica, nei filtri e nell'esportazione non sono interessate.

- Solo EXO - Prevenzione della perdita dei dati: tutti
- Solo EXO - O365SupportViewConfig: All
- Microsoft Azure Active Directory o EXO - Amministratore della sicurezza: Tutti
- AAD o EXO - Security Reader: All
- Solo EXO - Regole di trasporto: Tutte
- Solo EXO - View-Only configurazione: Tutti

All'interno della griglia di posta elettronica, del riquadro a comparsa Dettagli e del file CSV esportato, gli etR vengono presentati con un nome/GUID, come illustrato di seguito.

> [!div class="mx-imgBorder"]
> ![Regole di trasporto di Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Connettori in ingresso

I connettori sono una raccolta di istruzioni che personalizzano il flusso della posta elettronica da e verso l'organizzazione di Microsoft 365 o Office 365. Consentono di applicare eventuali restrizioni o controlli di sicurezza. In Esplora minacce è ora possibile visualizzare i connettori correlati a un messaggio di posta elettronica e cercare i messaggi di posta elettronica utilizzando i nomi dei connettori.

La ricerca dei connettori è di natura "contiene", il che significa che anche le ricerche parziali delle parole chiave dovrebbero funzionare. All'interno della visualizzazione griglia principale, del riquadro a comparsa Dettagli e del file CSV esportato, i connettori vengono visualizzati nel formato Nome/GUID, come illustrato di seguito:

> [!div class="mx-imgBorder"]
> ![Dettagli del connettore](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuove funzionalità in Esplora minacce e rilevamenti in tempo reale

In Esplora minacce e nei rilevamenti in tempo reale sono disponibili tre nuove funzionalità:

- [Visualizzare in anteprima l'intestazione e scaricare il corpo del messaggio di posta elettronica](#preview-email-header-and-download-email-body)
- [Sequenza temporale della posta elettronica](#email-timeline)
- [Esportare i dati di clic url](#export-url-click-data)

Queste nuove funzionalità sono descritte di seguito.

### <a name="preview-email-header-and-download-email-body"></a>Visualizzare in anteprima l'intestazione e scaricare il corpo del messaggio di posta elettronica

È ora possibile visualizzare in anteprima un'intestazione di posta elettronica e scaricare il corpo del messaggio in Threat Explorer Gli amministratori possono analizzare le intestazioni e i messaggi di posta elettronica scaricati per le minacce. Poiché il download dei messaggi di posta elettronica può rischiare l'esposizione delle informazioni, questo processo è controllato dal controllo dell'accesso basato sui ruoli (RBAC). Un nuovo ruolo, *Anteprima,* deve essere aggiunto a un altro gruppo di ruoli (ad esempio Operazioni di sicurezza o Amministratore sicurezza) per consentire il download dei messaggi di posta elettronica nella visualizzazione tutti i messaggi di posta elettronica. Tuttavia, la visualizzazione dell'intestazione del messaggio di posta elettronica non richiede alcun ruolo aggiuntivo (diverso da quello necessario per visualizzare i messaggi in Esplora minacce).

Explorer e i rilevamenti in tempo reale otterranno anche nuovi campi che forniscono un quadro più completo della posizione dei messaggi di posta elettronica. Queste modifiche semplificano la ricerca delle operazioni di sicurezza. Tuttavia, il risultato principale è che è possibile conoscere rapidamente la posizione dei messaggi di posta elettronica problematici.

Come viene eseguita questa operazione? Lo stato del recapito è ora suddiviso in due colonne:

- **Azione di recapito** - Stato del messaggio di posta elettronica.
- **Posizione di recapito-** Posizione in cui è stato instradato il messaggio di posta elettronica.

*L'azione* di recapito è l'azione eseguita su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le azioni possibili per un messaggio di posta elettronica:

|Recapitato|Posta indesiderata|Bloccato|Sostituito|
|---|---|---|---|
|La posta elettronica è stata recapitata nella posta in arrivo o nella cartella di un utente e l'utente può accedervi.|La posta elettronica è stata inviata alla cartella Posta indesiderata o Eliminata dell'utente e l'utente può accedervi.|Messaggi di posta elettronica messi in quarantena, non riusciti o eliminati. Questi messaggi di posta elettronica non sono accessibili all'utente.|La posta elettronica aveva allegati dannosi sostituiti da file txt che indicavano che l'allegato era dannoso.|

Ecco cosa può e non può vedere l'utente:

|Accessibile agli utenti finali|Inaccessibile agli utenti finali|
|---|---|
|Recapitato|Bloccato|
|Posta indesiderata|Sostituito|

**Il percorso di** recapito mostra i risultati dei criteri e dei rilevamenti eseguiti dopo il recapito. È collegato **_all'azione recapito._** Questi sono i valori possibili:

- *Posta in arrivo o cartella:* il messaggio di posta elettronica si trova nella cartella Posta in arrivo o in una cartella (in base alle regole di posta elettronica).
- *Locale o esterno:* la cassetta postale non esiste nel cloud ma è locale.
- *Cartella Posta indesiderata:* la posta elettronica si trova nella cartella Posta indesiderata di un utente.
- *Cartella Posta eliminata:* il messaggio di posta elettronica nella cartella Posta eliminata di un utente.
- *Quarantena:* il messaggio di posta elettronica è in quarantena e non nella cassetta postale di un utente.
- *Failed:* il messaggio di posta elettronica non è riuscito a raggiungere la cassetta postale.
- *Eliminato:* il messaggio di posta elettronica si è perso da qualche parte nel flusso di posta.

### <a name="email-timeline"></a>Sequenza temporale della posta elettronica

La **sequenza temporale della** posta elettronica è una nuova funzionalità di Explorer che migliora l'esperienza di ricerca per gli amministratori. Riduce il tempo impiegato per controllare posizioni diverse per provare a comprendere l'evento. Quando si verificano più eventi contemporaneamente all'arrivo di un messaggio di posta elettronica, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito della posta elettronica vengono acquisiti nella **colonna Azione** speciale. Gli amministratori possono combinare le informazioni della sequenza temporale con l'azione speciale eseguita sul post-recapito della posta per ottenere informazioni dettagliate sul funzionamento dei loro criteri, su dove è stata infine instradata la posta e, in alcuni casi, sulla valutazione finale.

Per ulteriori informazioni, vedere Analizzare e correggere i messaggi di posta elettronica dannosi [recapitati in Office 365.](investigate-malicious-email-that-was-delivered.md)

### <a name="export-url-click-data"></a>Esportare i dati di clic url

È ora possibile esportare i report per i clic su URL in Microsoft Excel per visualizzare **l'ID** messaggio di rete e fare clic sul verdetto, in modo da spiegare dove ha avuto origine il traffico di clic dell'URL. Ecco come funziona: in Gestione minacce sulla barra di avvio veloce di Office 365, seguire questa catena:

**Explorer** \> **View Phish** \> **Clic** \> **Gli URL principali o** i **clic principali degli URL** \> selezionano qualsiasi record per aprire il riquadro a comparsa url.

Quando si seleziona un URL nell'elenco, nel riquadro a comparsa viene visualizzato un nuovo pulsante **Esporta.** Utilizzare questo pulsante per spostare i dati in un foglio di calcolo di Excel per semplificare la creazione di report.

Seguire questo percorso per accedere alla stessa posizione nel report rilevamenti in tempo reale:

**Explorer** \> **Rilevamenti in tempo reale** \> **View Phish** \> **URL** \> **URL principali o** **clic principali Selezionare** qualsiasi record per aprire il riquadro a comparsa URL passare alla \> \> **scheda** Clic.

> [!TIP]
> L'ID messaggio di rete associa il clic a messaggi di posta elettronica specifici quando si esegue una ricerca sull'ID tramite Esplora risorse o strumenti di terze parti associati. Tali ricerche identificano il messaggio di posta elettronica associato a un risultato del clic. La presenza dell'ID messaggio di rete correlato consente un'analisi più rapida e potente.

> [!div class="mx-imgBorder"]
> ![Scheda Clic in Esplora risorse](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Visualizzare il malware rilevato nella posta elettronica tramite tecnologia

Si supponga di voler visualizzare il malware rilevato nei messaggi di posta elettronica ordinati in base alla tecnologia Microsoft 365. A tale scopo, utilizzare la visualizzazione [Posta > malware](threat-explorer-views.md#email--malware) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **minacce** (o **rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **Malware** di posta **elettronica** dal menu \> **Visualizza.**

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse](../../media/ExplorerViewEmailMalwareMenu.png)

3. Fare **clic su Mittente** e quindi scegliere **Tecnologia di** rilevamento di \> **base.**

   Le tecnologie di rilevamento sono ora disponibili come filtri per il report.

   > [!div class="mx-imgBorder"]
   > ![Tecnologie di rilevamento malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Scegliere un'opzione. Selezionare quindi il **pulsante Aggiorna** per applicare il filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnologia di rilevamento selezionata](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Il report viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione tecnologia selezionata. Da qui è possibile eseguire ulteriori analisi.

## <a name="view-phishing-url-and-click-verdict-data"></a>Visualizzare l'URL di phishing e fare clic sui dati del verdetto

Si supponga di voler visualizzare i tentativi di phishing tramite URL nei messaggi di posta elettronica, incluso un elenco di URL consentiti, bloccati e ignorati. Per identificare gli URL su cui è stato fatto clic, [è necessario](atp-safe-links.md) configurare collegamenti sicuri. Assicurarsi di configurare i criteri [collegamenti](set-up-atp-safe-links-policies.md) sicuri per la protezione del momento del clic e la registrazione dei verdetti clic per collegamenti sicuri.

Per esaminare gli URL dei phish nei messaggi e fare clic sugli URL nei messaggi di [   >  **phish,**](threat-explorer-views.md#email--phish) usa la visualizzazione E-mail phish di Explorer o rilevamenti in tempo reale.

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **minacce** (o **rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **E-mail**  phish dal menu \> **Visualizza.**

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse nel contesto di phishing](../../media/ExplorerViewEmailPhishMenu.png)

3. Fare **clic su Mittente** e quindi scegliere **URL Fare** clic su \> **verdetto.**

4. Selezionare una o più  opzioni, ad esempio Blocca e  Blocca ignorate, e quindi selezionare il pulsante Aggiorna sulla stessa riga delle opzioni per applicare il filtro. Non aggiornare la finestra del browser.

   > [!div class="mx-imgBorder"]
   > ![URL e clic sui verdetti](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Il report viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del report:

   - **Gli URL principali sono** gli URL nei messaggi filtrati e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione e-mail di Phish, questo elenco contiene in genere URL legittimi. Gli utenti malintenzionati includono nei messaggi una combinazione di URL buoni e non erri per tentare di ottenerli, ma rendono i collegamenti dannosi più interessanti. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica, ma questa colonna è nascosta per semplificare la visualizzazione.

   - **I clic principali** sono gli URL con collegamenti sicuri su cui è stato fatto clic, ordinati in base al numero totale di clic. Anche questa colonna non viene visualizzata, per semplificare la visualizzazione. Il conteggio totale per colonna indica il numero di verdetti clic su Collegamenti sicuri per ogni URL su cui è stato fatto clic. Nella visualizzazione posta elettronica di Phish, questi sono in genere URL sospetti o dannosi. Ma la visualizzazione potrebbe includere URL che non sono minacce ma sono nei messaggi di phish. I clic url sui collegamenti senza ritorno a capo non vengono visualizzati qui.

   Le due tabelle URL mostrano gli URL principali nei messaggi di posta elettronica di phishing in base all'azione di recapito e al percorso. Le tabelle mostrano i clic url bloccati o visitati nonostante un avviso, in modo da poter vedere quali potenziali collegamenti non riusciti sono stati presentati agli utenti e che l'utente ha fatto clic. Da qui è possibile eseguire ulteriori analisi. Ad esempio, sotto il grafico è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.

   > [!div class="mx-imgBorder"]
   > ![URL di Explorer bloccati](../../media/ExplorerPhishClickVerdictURLs.png)

   Selezionare un URL per visualizzare informazioni più dettagliate.

   > [!NOTE]
   > Nella finestra di dialogo del riquadro a comparsa dell'URL, il filtro dei messaggi di posta elettronica viene rimosso per mostrare la visualizzazione completa dell'esposizione dell'URL nell'ambiente. In questo modo è possibile filtrare i messaggi di posta elettronica di cui si è preoccupati in Esplora risorse, trovare URL specifici che sono potenziali minacce e quindi espandere la comprensione dell'esposizione degli URL nell'ambiente (tramite la finestra di dialogo dei dettagli dell'URL) senza dover aggiungere filtri URL alla visualizzazione Esplora risorse stessa.

### <a name="interpretation-of-click-verdicts"></a>Interpretazione dei verdetti clic

All'interno dei riquadri a comparsa e-mail o URL, dei clic principali e delle esperienze di filtro, vedrai diversi valori di verdetto clic:

- **Nessuno:** Impossibile acquisire il verdetto per l'URL. L'utente potrebbe aver fatto clic sull'URL.
- **Consentito:** All'utente è stato consentito passare all'URL.
- **Bloccato:** All'utente è stato impedito di passare all'URL.
- **Verdetto in sospeso:** All'utente è stata presentata la pagina detonazione in sospeso.
- **Bloccato ignorato:** All'utente è stato impedito di passare direttamente all'URL. Tuttavia, l'utente ha sovrascritto il blocco per passare all'URL.
- **Verdetto in sospeso ignorato:** All'utente è stata presentata la pagina di detonazione. Tuttavia, l'utente ha sovrascritto il messaggio per accedere all'URL.
- **Errore:** All'utente è stata visualizzata la pagina di errore o si è verificato un errore durante l'acquisizione del verdetto.
- **Errore:** Si è verificata un'eccezione sconosciuta durante l'acquisizione del verdetto. L'utente potrebbe aver fatto clic sull'URL.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica segnalati dagli [](enable-the-report-message-add-in.md) utenti dell'organizzazione come posta *indesiderata,* non indesiderata o *phishing* tramite il componente aggiuntivo Segnala messaggio o Segnala [phishing.](enable-the-report-phish-add-in.md) Per visualizzarli, usa la visualizzazione [   >  **Invii di posta**](threat-explorer-views.md#email--submissions) elettronica di Esplora risorse (o rilevamenti in tempo reale).

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **minacce** (o **rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **Invii** **di** posta elettronica dal menu \> **Visualizza.**

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse per i messaggi di posta elettronica](../../media/explorer-view-menu-email-user-reported.png)

3. Fare **clic su Mittente** e quindi scegliere **Tipo di** rapporto di \> **base.**

4. Selezionare un'opzione, ad esempio **Phish,** e quindi fare clic **sul pulsante** Aggiorna.

   > [!div class="mx-imgBorder"]
   > ![Phish segnalato dall'utente](../../media/EmailUserReportedReportType.png)

Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica segnalati da utenti dell'organizzazione come tentativi di phishing. È possibile utilizzare queste informazioni per eseguire ulteriori analisi e, se necessario, modificare i criteri [anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="start-automated-investigation-and-response"></a>Avviare un'indagine e una risposta automatizzate

> [!NOTE]
> Le funzionalità di analisi e risposta automatizzate sono disponibili in *Microsoft Defender per Office 365 Piano 2* e Office *365 E5.*

[L'analisi e la risposta automatizzate](automated-investigation-response-office.md) possono risparmiare tempo e impegno del team delle operazioni di sicurezza dedicato all'analisi e alla mitigazione degli attacchi informatici. Oltre a configurare avvisi che possono attivare un playbook sulla sicurezza, puoi avviare un processo di analisi e risposta automatizzato da una visualizzazione in Esplora risorse. Per informazioni dettagliate, vedere Esempio: un amministratore [della sicurezza attiva un'indagine da Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Altri modi per usare Esplora risorse e i rilevamenti in tempo reale

Oltre agli scenari descritti in questo articolo, sono disponibili molte più opzioni di creazione di report con Esplora risorse (o rilevamenti in tempo reale). Fare inoltre riferimento ai seguenti articoli:

- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)](threat-explorer-views.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Indagine e reazione automatizzate in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

È necessario disporre di [Microsoft Defender per Office 365](office-365-atp.md) per usare Esplora risorse o rilevamenti in tempo reale.

- Explorer è incluso in Defender per Office 365 Piano 2.
- Il report rilevamenti in tempo reale è incluso in Defender per Office 365 Piano 1.
- Pianificare l'assegnazione di licenze per tutti gli utenti che devono essere protetti da Defender per Office 365. Explorer e i rilevamenti in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.

Per visualizzare e usare Esplora risorse o rilevamenti in tempo reale, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza.

- Per il Centro sicurezza & conformità, è necessario disporre di uno dei ruoli seguenti:

  - Gestione organizzazione
  - Amministratore della sicurezza (può essere assegnato nell'interfaccia di amministrazione di Azure Active Directory ( <https://aad.portal.azure.com> )
  - Ruolo con autorizzazioni di lettura per la sicurezza

- Per Exchange Online, è necessario disporre di uno dei ruoli seguenti assegnati nell'interfaccia di amministrazione di Exchange ( ) o <https://admin.protection.outlook.com/ecp/> [in PowerShell di Exchange Online:](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Gestione organizzazione
  - Gestione organizzazione sola visualizzazione
  - Destinatari solo visualizzazione
  - Gestione della conformità

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:

- [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)
- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Differenze tra Esplora minacce e rilevamenti in tempo reale

- Il *report rilevamenti in tempo* reale è disponibile in Defender per Office 365 Piano 1. *Esplora minacce* è disponibile in Defender per Office 365 Piano 2.
- Il report rilevamenti in tempo reale consente di visualizzare i rilevamenti in tempo reale. Esplora minacce esegue anche questa operazione, ma fornisce anche ulteriori dettagli per un determinato attacco.
- Una *visualizzazione Tutti i* messaggi di posta elettronica è disponibile in Esplora minacce, ma non nel report rilevamenti in tempo reale.
- Altre funzionalità di filtro e azioni disponibili sono incluse in Esplora minacce. Per altre informazioni, vedere [Microsoft Defender per Office 365 Service Description: Feature availability across Defender for Office 365 plans.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
