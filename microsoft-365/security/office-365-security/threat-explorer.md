---
title: Threat Explorer e rilevamenti in tempo reale
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
description: Usa Esplora risorse e i rilevamenti in tempo reale nel Centro sicurezza e conformità per analizzare e rispondere alle minacce in &amp; modo efficiente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 810b5c99aa239f295fd930c1d13a6a817012b18b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245565"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer e rilevamenti in tempo reale

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se [l'organizzazione](#new-features-in-threat-explorer-and-real-time-detections)dispone di [Microsoft Defender per Office 365](defender-for-office-365.md)e si dispone delle autorizzazioni necessarie, si dispone dei rilevamenti di **Esplora** risorse o in tempo reale **(in** precedenza rapporti in tempo *reale,* vedere novità !). [](#required-licenses-and-permissions) Nel Centro sicurezza & conformità passare a **Gestione delle** minacce e quindi scegliere **Esplora risorse** _o_ **Rilevamenti in tempo reale.**

<br>

****

|Con Microsoft Defender per Office 365 Piano 2, viene visualizzato:|Con Microsoft Defender per Office 365 piano 1, viene visualizzato:|
|---|---|
|![Esplora minacce](../../media/threatmgmt-explorer.png)|![Rilevamenti in tempo reale](../../media/threatmgmt-realtimedetections.png)|
|

Explorer o rilevamenti in tempo reale consentono al team delle operazioni di sicurezza di analizzare e rispondere alle minacce in modo efficiente. Il report è simile all'immagine seguente:

![Vai a Esplora gestione \> delle minacce](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con questo report, è possibile:

- [Vedere malware rilevato dalle Microsoft 365 di sicurezza](#see-malware-detected-in-email-by-technology)
- [Visualizzare l'URL di phishing e fare clic su Dati verdetto](#view-phishing-url-and-click-verdict-data)
- [Avviare un processo di indagine e risposta](#start-automated-investigation-and-response) automatizzato da una visualizzazione in Esplora risorse (solo Defender per Office 365 Piano 2)
- [Analizzare la posta elettronica dannosa e altro ancora](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a>Miglioramenti all'esperienza di ricerca delle minacce

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a>Introduzione dell'ID avviso per gli avvisi MDO in Esplora risorse/Rilevamenti in tempo reale (anteprima)

Oggi, se si passa da un avviso a Esplora minacce, viene aperta una visualizzazione filtrata all'interno di Esplora risorse, con la visualizzazione filtrata in base all'ID dei criteri di avviso (l'ID criterio è un identificatore univoco per un criterio di avviso).
Stiamo rendendo questa integrazione più pertinente introducendo l'ID avviso (vedi un esempio di ID avviso di seguito) in Threat Explorer e rilevamenti in tempo reale in modo da visualizzare i messaggi pertinenti per l'avviso specifico, nonché un conteggio dei messaggi di posta elettronica. Sarà inoltre possibile vedere se un messaggio fa parte di un avviso e passare da tale messaggio all'avviso specifico.

L'ID avviso è disponibile all'interno dell'URL quando si visualizza un singolo avviso. un esempio è `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` .

> [!div class="mx-imgBorder"]
> ![Filtro per l'ID avviso](../../media/AlertID-Filter.png)

> [!div class="mx-imgBorder"]
> ![ID avviso nel riquadro a comparsa dettagli](../../media/AlertID-DetailsFlyout.png)

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a>Estensione del limite di conservazione e ricerca dei dati di Explorer (e rilevamento in tempo reale) per i tenant di prova da 7 a 30 giorni (Anteprima)

Come parte di questa modifica, sarà possibile cercare e filtrare i dati di posta elettronica in 30 giorni (un aumento rispetto ai 7 giorni precedenti) in Threat Explorer/Rilevamenti in tempo reale per Defender per tenant di prova Office P1 e P2.
Ciò non influisce sui tenant di produzione per i clienti P1 e P2/E5, che hanno già le funzionalità di conservazione e ricerca dei dati di 30 giorni.

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a>Limiti aggiornati per l'esportazione di record per Threat Explorer (anteprima)

Come parte di questo aggiornamento, il numero di righe per i record di posta elettronica che possono essere esportati da Esplora minacce è aumentato da 9990 a 200.000 record. Il set di colonne che è possibile esportare attualmente rimarrà invariato, ma il numero di righe aumenterà rispetto al limite corrente.

### <a name="tags-in-threat-explorer"></a>Tag in Threat Explorer

> [!NOTE]
> La funzionalità tag utente è disponibile in *Anteprima,* non è disponibile per tutti gli utenti ed è soggetta a modifiche. Per informazioni sulla pianificazione dei rilasci, vedere la guida di orientamento Microsoft 365 rilascio.

I tag utente identificano gruppi specifici di utenti in Microsoft Defender per Office 365. Per ulteriori informazioni sui tag, incluse le licenze e la configurazione, vedere [Tag utente](user-tags.md).

In Esplora minacce puoi visualizzare le informazioni sui tag utente nelle esperienze seguenti.

#### <a name="email-grid-view"></a>Visualizzazione griglia posta elettronica

La **colonna Tag** nella griglia della posta elettronica contiene tutti i tag applicati alle cassette postali del mittente o del destinatario. Per impostazione predefinita, i tag di sistema come gli account di priorità vengono visualizzati per primi.

> [!div class="mx-imgBorder"]
> ![Filtrare i tag nella visualizzazione griglia della posta elettronica](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtro

È possibile utilizzare i tag come filtro. Hunt solo attraverso gli account con priorità o specifici scenari di tag utente. È inoltre possibile escludere i risultati con determinati tag. Combina questa funzionalità con altri filtri per restringere l'ambito di indagine.

[![Tag di filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Tag non filtrati](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Riquadro a comparsa Dettagli posta elettronica

Per visualizzare i singoli tag per il mittente e il destinatario, selezionare l'oggetto per aprire il riquadro a comparsa dei dettagli del messaggio. Nella scheda **Riepilogo,** i tag mittente e destinatario vengono visualizzati separatamente, se sono presenti per un messaggio di posta elettronica.
Le informazioni sui singoli tag per mittente e destinatario si estendono anche ai dati CSV esportati, dove è possibile visualizzare questi dettagli in due colonne separate.

> [!div class="mx-imgBorder"]
> ![Tag Dettagli posta elettronica](../../media/tags-flyout.png)

Le informazioni sui tag vengono visualizzate anche nel riquadro a comparsa dei clic sull'URL. Per visualizzarla, passare alla visualizzazione Phish o All Email e quindi alla scheda URL **o** **CLIC** URL. Seleziona un singolo riquadro a comparsa URL per visualizzare ulteriori dettagli sui clic per tale URL, inclusi i tag associati a tale clic.

### <a name="updated-timeline-view"></a>Visualizzazione sequenza temporale aggiornata

> [!div class="mx-imgBorder"]
> ![Tag URL](../../media/tags-urls.png)
>
Scopri di più guardando [questo video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Miglioramenti all'esperienza di ricerca delle minacce (imminente)

### <a name="updated-threat-information-for-emails"></a>Informazioni aggiornate sulle minacce per i messaggi di posta elettronica

Ci siamo concentrati sui miglioramenti della piattaforma e della qualità dei dati per aumentare l'accuratezza e la coerenza dei dati per i record di posta elettronica. I miglioramenti includono il consolidamento delle informazioni di pre-recapito e post-recapito, ad esempio le azioni eseguite su un messaggio di posta elettronica come parte del processo ZAP, in un singolo record. Sono inclusi ulteriori dettagli come il verdetto di posta indesiderata, le minacce a livello di entità (ad esempio, l'URL dannoso) e le posizioni di recapito più recenti.

Dopo questi aggiornamenti, verrà visualizzata una singola voce per ogni messaggio, indipendentemente dal diverso evento di post-recapito che influisce sul messaggio. Le azioni possono includere ZAP, correzione manuale (che significa azione dell'amministratore), recapito dinamico e così via.

Oltre a mostrare minacce di malware e phishing, viene visualizzato il verdetto di posta indesiderata associato a un messaggio di posta elettronica. All'interno del messaggio di posta elettronica, vedere tutte le minacce associate al messaggio di posta elettronica insieme alle tecnologie di rilevamento corrispondenti. Un messaggio di posta elettronica può avere zero, una o più minacce. Vedrai le minacce correnti nella sezione **Dettagli** del riquadro a comparsa della posta elettronica. Per più minacce (ad esempio malware e phishing), il campo **tecnico rilevamento** mostra il mapping di rilevamento delle minacce, che è la tecnologia di rilevamento che ha identificato la minaccia.

Il set di tecnologie di rilevamento ora include nuovi metodi di rilevamento, nonché tecnologie di rilevamento della posta indesiderata. È possibile utilizzare lo stesso set di tecnologie di rilevamento per filtrare i risultati nelle diverse visualizzazioni della posta elettronica (Malware, Phish, All Email).

> [!NOTE]
> L'analisi del verdetto potrebbe non essere necessariamente legata a entità. Ad esempio, un messaggio di posta elettronica potrebbe essere classificato come phish o posta indesiderata, ma non ci sono URL contrassegnati con un verdetto phish/spam. Questo perché i filtri valutano anche il contenuto e altri dettagli per un messaggio di posta elettronica prima di assegnare un verdetto.

#### <a name="threats-in-urls"></a>Minacce negli URL

È ora possibile visualizzare la minaccia specifica per un URL nella scheda Dettagli riquadro **a comparsa della** posta elettronica. La minaccia può essere *malware,* *phish,* *spam* o *nessuno.)*

> [!div class="mx-imgBorder"]
> ![Minacce URL](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Visualizzazione sequenza temporale aggiornata (imminente)

> [!div class="mx-imgBorder"]
> ![Visualizzazione sequenza temporale aggiornata](../../media/Email_Timeline.png)

La visualizzazione Sequenza temporale identifica tutti gli eventi di recapito e post-recapito. Include informazioni sulla minaccia identificata in quel momento per un sottoinsieme di questi eventi. La visualizzazione Sequenza temporale fornisce inoltre informazioni su eventuali azioni aggiuntive intraprese (ad esempio zap o correzione manuale), insieme al risultato di tale azione. Le informazioni sulla visualizzazione sequenza temporale includono:

- **Origine:** Origine dell'evento. Può essere admin/system/user.
- **Evento:** Include eventi di primo livello come recapito originale, correzione manuale, ZAP, invii e recapito dinamico.
- **Azione:** L'azione specifica eseguita nell'ambito dell'azione ZAP o dell'amministratore (ad esempio, eliminazione recidiva).
- **Minacce:** Copre le minacce (malware, phish, spam) identificate in quel momento.
- **Risultato/Dettagli:** Ulteriori informazioni sul risultato dell'azione, ad esempio se è stata eseguita come parte dell'azione ZAP/amministratore.

### <a name="original-and-latest-delivery-location"></a>Posizione di recapito originale e più recente

Attualmente, viene visualizzata la posizione di recapito nella griglia della posta elettronica e nel riquadro a comparsa della posta elettronica. Il **campo Percorso di** recapito viene rinominato Posizione di recapito **_originale_*_. E stiamo introducendo un altro campo, _*_Posizione di recapito più recente._**

**Il percorso di recapito** originale fornisce ulteriori informazioni sulla posizione iniziale in cui è stato recapitato un messaggio di posta elettronica. **Il percorso di recapito più** recente consente di inviare un messaggio di posta elettronica dopo azioni di sistema come *ZAP* o azioni di amministrazione come *Sposta in elementi eliminati.* Il percorso di recapito più recente ha lo scopo di indicare agli amministratori l'ultima posizione nota del messaggio dopo il recapito o qualsiasi azione di sistema/amministratore. Non include azioni dell'utente finale nel messaggio di posta elettronica. Ad esempio, se un utente ha eliminato un messaggio o spostato il messaggio in archivio/pst, il percorso di "recapito" del messaggio non verrà aggiornato. Ma se un'azione di sistema ha aggiornato la posizione (ad esempio, ZAP causando lo spostamento di un messaggio di posta elettronica in quarantena), Il percorso di recapito **più recente** verrà visualizzato come "quarantena".

> [!div class="mx-imgBorder"]
> ![Percorsi di recapito aggiornati](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Esistono alcuni casi in cui la posizione **di recapito e** **l'azione di recapito** possono essere mostrate come "sconosciute":
>
> - È possibile  che la posizione di  recapito sia "recapitata" e la posizione di recapito come "sconosciuta" se il messaggio è stato recapitato, ma una regola di Posta in arrivo ha spostato il messaggio in una cartella predefinita ,ad esempio Bozza o Archivio, anziché nella cartella Posta in arrivo o Posta indesiderata.
>
> - **Il percorso di recapito più** recente può essere sconosciuto se è stata tentata un'azione di amministratore/sistema (ad esempio ZAP), ma il messaggio non è stato trovato. In genere, l'azione viene eseguita dopo che l'utente ha spostato o eliminato il messaggio. In questi casi, verificare la **colonna Result/Details** nella visualizzazione sequenza temporale. Cercare l'istruzione "Messaggio spostato o eliminato dall'utente".

> [!div class="mx-imgBorder"]
> ![Posizioni di recapito per la sequenza temporale](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Azioni aggiuntive

*Dopo il recapito* del messaggio di posta elettronica sono state applicate altre azioni. Possono includere *ZAP,* correzione manuale *(azione* eseguita da un amministratore, ad esempio eliminazione recidiva), recapito dinamico e rielaborazione *(per* un messaggio di posta elettronica che è stato rilevato retroattivamente come valido).

> [!NOTE]
> Come parte delle modifiche in sospeso, il valore "Rimosso da ZAP" attualmente evaso nel filtro Azione di recapito sta per andare via. Avrai un modo per cercare tutti i messaggi di posta elettronica con il tentativo ZAP tramite **Azioni aggiuntive.**

> [!div class="mx-imgBorder"]
> ![Azioni aggiuntive in Esplora risorse](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Sostituzioni di sistema

*Le sostituzioni* di sistema consentono di creare eccezioni al percorso di recapito previsto di un messaggio. La posizione di recapito fornita dal sistema viene sovrascritta in base alle minacce e ad altri rilevamenti identificati dallo stack di filtro. Le sostituzioni di sistema possono essere impostate tramite criteri tenant o utente per recapitare il messaggio come suggerito dal criterio. Le sostituzioni possono identificare il recapito involontario di messaggi dannosi a causa di lacune nelle configurazioni, ad esempio un criterio Mittente sicuro troppo ampio impostato da un utente. Questi valori di override possono essere:

- Consentito dai criteri utente: un utente crea criteri a livello di cassetta postale per consentire domini o mittenti.

- Bloccato dai criteri utente: un utente crea criteri a livello di casella di posta per bloccare domini o mittenti.

- Consentito dai criteri dell'organizzazione: i team di sicurezza dell'organizzazione impostano criteri o regole del flusso di posta Exchange (note anche come regole di trasporto) per consentire a mittenti e domini per gli utenti dell'organizzazione. Può essere per un set di utenti o per l'intera organizzazione.

- Bloccato dai criteri dell'organizzazione: i team di sicurezza dell'organizzazione impostano criteri o regole del flusso di posta per bloccare mittenti, domini, lingue dei messaggi o INDIRIZZI IP di origine per gli utenti dell'organizzazione. Può essere applicato a un set di utenti o all'intera organizzazione.

- Estensione di file bloccata dai criteri dell'organizzazione: il team di sicurezza di un'organizzazione blocca un'estensione di file tramite le impostazioni dei criteri antimalware. Questi valori verranno ora visualizzati nei dettagli della posta elettronica per facilitare le indagini. I team di Secops possono anche usare la funzionalità di filtro avanzato per filtrare le estensioni di file bloccate.

[![Sostituzioni di sistema in Esplora risorse](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Griglia sostituzioni di sistema in Esplora risorse](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Miglioramenti per l'esperienza di URL e clic

I miglioramenti includono:

- Mostra l'URL a cui è stato fatto clic completo  (inclusi eventuali parametri di query che fanno parte dell'URL) nella sezione Clic del riquadro a comparsa dell'URL. Attualmente, il dominio e il percorso dell'URL vengono visualizzati nella barra del titolo. Queste informazioni vengono estese per mostrare l'URL completo.

- Correzioni tra filtri URL (*DOMINIO URL* e dominio *URL* e percorso *URL*): gli aggiornamenti influiscono sulla ricerca dei messaggi che contengono un URL o un verdetto clic. È stato abilitato il supporto per le ricerche indipendenti dal protocollo, in modo da poter cercare un URL senza utilizzare `http` . Per impostazione predefinita, la ricerca URL viene mappata a http, a meno che non venga specificato in modo esplicito un altro valore. Ad esempio:
  - Eseguire una ricerca con e senza il prefisso nei campi di filtro `http://` **URL**, **Dominio URL** e Dominio **URL e** Percorso. Le ricerche dovrebbero mostrare gli stessi risultati.
  - Cercare il prefisso `https://` in **URL**. Quando non viene specificato alcun valore, viene `http://` utilizzato il prefisso.
  - `/` viene ignorato all'inizio e alla fine dei campi **percorso URL**, **DOMINIO URL**, dominio **URL e** percorso. `/` alla fine del campo **URL** viene ignorato.

### <a name="phish-confidence-level"></a>Livello di probabilità phish

Il livello di probabilità phish consente di identificare il grado di confidenza con cui un messaggio di posta elettronica è stato classificato come "phish". I due valori possibili sono *High* e *Normal.* Nelle fasi iniziali, questo filtro sarà disponibile solo nella visualizzazione Phish di Threat Explorer.

[![Livello di probabilità di phish in Esplora risorse](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Segnale URL ZAP

Il segnale DELL'URL ZAP viene in genere usato per gli scenari di avviso phish ZAP in cui un messaggio di posta elettronica è stato identificato come Phish e rimosso dopo il recapito. Questo segnale connette l'avviso con i risultati corrispondenti in Esplora risorse. Si tratta di una delle operazioni di I/O per l'avviso.

Per migliorare il processo di ricerca, abbiamo aggiornato Threat Explorer e i rilevamenti in tempo reale per rendere l'esperienza di ricerca più coerente. Le modifiche sono descritte qui:

- [Miglioramenti relativi al fuso orario](#timezone-improvements)
- [Aggiornamento nel processo di aggiornamento](#update-in-the-refresh-process)
- [Drill-down grafico da aggiungere ai filtri](#chart-drilldown-to-add-to-filters)
- [Aggiornamenti delle informazioni sui prodotti](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtro in base ai tag utente

È ora possibile ordinare e filtrare i tag utente personalizzati o di sistema per comprendere rapidamente l'ambito delle minacce. Per ulteriori informazioni, vedere [Tag utente.](user-tags.md)

> [!IMPORTANT]
> Il filtro e l'ordinamento in base ai tag utente sono attualmente in anteprima pubblica. Questa funzionalità può essere sostanzialmente modificata prima che venga rilasciata commercialmente. Microsoft non fa alcuna garanzia, espressa o implicita, rispetto alle informazioni fornite.

> [!div class="mx-imgBorder"]
> ![Colonna Tag in Esplora risorse](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Miglioramenti relativi al fuso orario

Verrà visualizzato il fuso orario per i record di posta elettronica nel portale e per i dati esportati. Sarà visibile tra esperienze come Griglia e-mail, Riquadro a comparsa Dettagli, Sequenza temporale e-mail e Messaggi di posta elettronica simili, quindi il fuso orario per il set di risultati è chiaro.

> [!div class="mx-imgBorder"]
> ![Visualizzare il fuso orario in Esplora risorse](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Aggiornamento nel processo di aggiornamento

Alcuni utenti hanno commentato la confusione con l'aggiornamento automatico (ad esempio, non appena si modifica la data, la pagina viene aggiornata) e l'aggiornamento manuale (per altri filtri). Analogamente, la rimozione dei filtri comporta l'aggiornamento automatico. La modifica dei filtri durante la modifica della query può causare esperienze di ricerca incoerenti. Per risolvere questi problemi, stiamo passando a un meccanismo di filtro manuale.

Dal punto di vista dell'esperienza, l'utente può applicare e rimuovere il diverso intervallo di filtri (dal set di filtri e dalla data) e selezionare il pulsante di aggiornamento per filtrare i risultati dopo aver definito la query. Anche il pulsante aggiorna viene sottolineato sullo schermo. Sono state inoltre aggiornate le descrizioni comandi correlate e la documentazione del prodotto.

> [!div class="mx-imgBorder"]
> ![Selezionare Aggiorna per filtrare i risultati](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Drill-down grafico da aggiungere ai filtri

È ora possibile creare un grafico dei valori della legenda per aggiungerli come filtri. Selezionare il **pulsante** Aggiorna per filtrare i risultati.

> [!div class="mx-imgBorder"]
> ![Eseguire il drill-down dei grafici per filtrare](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Aggiornamenti delle informazioni nel prodotto

Ulteriori dettagli sono ora disponibili all'interno del prodotto, ad esempio il numero totale di risultati della ricerca all'interno della griglia (vedere di seguito). Sono state migliorate le etichette, i messaggi di errore e le descrizioni comandi per fornire ulteriori informazioni sui filtri, sull'esperienza di ricerca e sul set di risultati.

> [!div class="mx-imgBorder"]
> ![Visualizzare le informazioni nel prodotto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Funzionalità estese in Threat Explorer

### <a name="top-targeted-users"></a>Utenti di destinazione principali

Oggi espongiamo l'elenco degli utenti di destinazione principali nella visualizzazione Malware per i messaggi di posta elettronica, nella **sezione Principali famiglie di malware.** Questa visualizzazione verrà estendeta anche nelle visualizzazioni Phish e All Email. Sarà possibile visualizzare i primi cinque utenti di destinazione, insieme al numero di tentativi per ogni utente per la visualizzazione corrispondente. Ad esempio, per phish view, vedrai il numero di tentativi phish.

Sarà possibile esportare l'elenco degli utenti di destinazione, fino a un limite di 3.000, insieme al numero di tentativi di analisi offline per ogni visualizzazione della posta elettronica. Inoltre, selezionando il numero di tentativi (ad esempio, 13 tentativi nell'immagine seguente) verrà aperta una visualizzazione filtrata in Esplora minacce, in modo da poter visualizzare ulteriori dettagli tra i messaggi di posta elettronica e le minacce per tale utente.

> [!div class="mx-imgBorder"]
> ![Utenti di destinazione principali](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange di trasporto

Come parte dell'arricchimento dei dati, sarà possibile visualizzare tutte le diverse regole di trasporto Exchange (ETR) applicate a un messaggio. Queste informazioni saranno disponibili nella visualizzazione Griglia posta elettronica. Per visualizzarla, selezionare **Opzioni colonna** nella griglia e quindi Exchange regola **di trasporto** dalle opzioni colonna. Sarà visibile anche nel riquadro **a** comparsa Dettagli nel messaggio di posta elettronica.

Sarà possibile visualizzare sia il GUID che il nome delle regole di trasporto applicate al messaggio. Sarà possibile cercare i messaggi utilizzando il nome della regola di trasporto. Si tratta di una ricerca "Contiene", il che significa che è possibile eseguire anche ricerche parziali.

> [!IMPORTANT]
> La ricerca ETR e la disponibilità del nome dipendono dal ruolo specifico assegnato all'utente. Per visualizzare i nomi ETR e la ricerca, è necessario disporre di uno dei ruoli/autorizzazioni seguenti. Se non è stato assegnato alcuno di questi ruoli, non è possibile visualizzare i nomi delle regole di trasporto o cercare i messaggi utilizzando i nomi ETR. Tuttavia, potresti visualizzare le informazioni sull'etichetta ETR e sul GUID nei Dettagli e-mail. Altre esperienze di visualizzazione dei record nelle griglie di posta elettronica, nei riquadri a comparsa di posta elettronica, nei filtri e nell'esportazione non sono interessate.
>
> - Solo EXO - Prevenzione della perdita di dati: Tutti
> - Solo EXO - O365SupportViewConfig: All
> - Microsoft Azure Active Directory o EXO - Amministratore sicurezza: Tutti
> - AAD o EXO - Security Reader: All
> - Solo EXO - Regole di trasporto: Tutte
> - Solo EXO - Configurazione View-Only: Tutti
>
> All'interno della griglia di posta elettronica, del riquadro a comparsa Dettagli e del file CSV esportato, gli ETF vengono presentati con un nome/GUID, come illustrato di seguito.
>
> > [!div class="mx-imgBorder"]
> > ![Exchange Regole di trasporto](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Connettori in ingresso

I connettori sono una raccolta di istruzioni che personalizzano il flusso della posta elettronica da e verso l'Microsoft 365 o Office 365'organizzazione. Consentono di applicare eventuali restrizioni o controlli di sicurezza. In Esplora minacce è ora possibile visualizzare i connettori correlati a un messaggio di posta elettronica e cercare i messaggi di posta elettronica utilizzando i nomi dei connettori.

La ricerca di connettori è di natura "contiene", il che significa che anche le ricerche parziali di parole chiave dovrebbero funzionare. All'interno della visualizzazione Griglia principale, del riquadro a comparsa Dettagli e del file CSV esportato, i connettori vengono visualizzati nel formato Nome/GUID, come illustrato di seguito:

> [!div class="mx-imgBorder"]
> ![Dettagli connettore](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuove funzionalità in Threat Explorer e rilevamenti in tempo reale

- [Visualizzare i messaggi di posta elettronica di phishing inviati a utenti e domini impersonati](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [Anteprima dell'intestazione della posta elettronica e download del corpo del messaggio di posta elettronica](#preview-email-header-and-download-email-body)
- [Sequenza temporale della posta elettronica](#email-timeline)
- [Esportare i dati di clic url](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a>Visualizzare i messaggi di posta elettronica di phishing inviati a utenti e domini impersonati

Per identificare i tentativi di phishing contro utenti e domini che sono utenti rappresentati devono essere aggiunti *all'elenco di utenti da proteggere*. Per i domini, gli amministratori devono abilitare *i domini dell'organizzazione* o aggiungere un nome di dominio a *Domini per proteggere*. I domini da proteggere sono disponibili nella pagina *Criteri anti-phishing* nella *sezione Rappresentazione.*

Per esaminare i messaggi di phish e cercare utenti o domini impersonati, usa la visualizzazione [Posta > Phish](threat-explorer-views.md) di Explorer.

In questo esempio viene utilizzato Threat Explorer.

1. Nel [Centro sicurezza & conformità](https://protection.office.com) ( , scegliere Gestione https://protection.office.com) delle minacce > Explorer (o rilevamenti in tempo reale).

2. Scegliere Posta elettronica dal menu Visualizza > Phish.

   Qui è possibile scegliere il **dominio rappresentato o** **l'utente rappresentato.**

3. **Selezionare** **Dominio rappresentato** e quindi digitare un dominio protetto nella casella di testo.

   Ad esempio, cercare nomi di dominio protetti come *contoso,* *contoso.com* o *contoso.com.au*.

4. Seleziona l'oggetto di qualsiasi messaggio nella scheda Posta > dettagli per visualizzare ulteriori informazioni sulla rappresentazione, ad esempio Dominio impersonato/Posizione rilevata.

    **OR**

    Selezionare **Utente rappresentato e** digitare l'indirizzo di posta elettronica di un utente protetto nella casella di testo.

    > [!TIP]
    > **Per ottenere risultati ottimali,** utilizzare *indirizzi di posta elettronica completi per* cercare utenti protetti. L'utente protetto verrà trovato più rapidamente e con maggiore successo se si cerca *firstname.lastname@contoso.com,* ad esempio quando si analizza la rappresentazione dell'utente. Quando si cerca un dominio protetto, la ricerca prenderà il dominio radice (ad esempio, contoso.com) e il nome di dominio (*contoso*). La ricerca del dominio *radice contoso.com* restituirà entrambe le *contoso.com* e il nome di dominio *contoso*.

5. Selezionare **l'oggetto** di qualsiasi messaggio nella scheda **E-mail** Scheda Dettagli per visualizzare ulteriori informazioni sulla rappresentazione dell'utente o del dominio e  >   la *posizione rilevata.*

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="Riquadro dei dettagli di Esplora minacce per un utente protetto che mostra la posizione di rilevamento e la minaccia rilevata (qui imitazione di un utente).":::

> [!NOTE]
> Nel passaggio 3 o 5, se si sceglie  Tecnologia di rilevamento e si seleziona rispettivamente Dominio di rappresentazione o Utente di rappresentazione, le informazioni nella scheda E-mail Dettagli sull'utente o sul dominio e la posizione rilevata verrà visualizzata solo sui messaggi correlati all'utente o al dominio elencati nella pagina Dei criteri    >   *anti-phishing.* 

### <a name="preview-email-header-and-download-email-body"></a>Anteprima dell'intestazione della posta elettronica e download del corpo del messaggio di posta elettronica

Ora puoi visualizzare in anteprima un'intestazione di posta elettronica e scaricare il corpo del messaggio in Threat Explorer. Gli amministratori possono analizzare le intestazioni e i messaggi di posta elettronica scaricati alla ricerca di minacce. Poiché il download dei messaggi di posta elettronica può rischiare l'esposizione delle informazioni, questo processo è controllato dal controllo di accesso basato sui ruoli (RBAC). Un nuovo ruolo, *Anteprima*, deve essere aggiunto a un altro gruppo di ruoli (ad esempio Operazioni di sicurezza o Amministratore sicurezza) per consentire il download dei messaggi di posta elettronica nella visualizzazione tutti i messaggi di posta elettronica. Tuttavia, la visualizzazione dell'intestazione del messaggio di posta elettronica non richiede alcun ruolo aggiuntivo (a parte quello necessario per visualizzare i messaggi in Threat Explorer).

Explorer e i rilevamenti in tempo reale otterranno anche nuovi campi che offrono un quadro più completo della posizione dei messaggi di posta elettronica. Queste modifiche semplificano la ricerca per Le operazioni di sicurezza. Ma il risultato principale è che puoi conoscere rapidamente la posizione dei messaggi di posta elettronica problematici.

Come viene eseguita questa operazione? Lo stato del recapito è ora suddiviso in due colonne:

- **Azione di recapito** - Stato del messaggio di posta elettronica.
- **Posizione di recapito** - Posizione in cui è stato instradato il messaggio di posta elettronica.

*L'azione* di recapito è l'azione eseguita su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le azioni possibili per un messaggio di posta elettronica:

<br>

****

|Recapitati|Posta indesiderata|Bloccato|Sostituito|
|---|---|---|---|
|La posta elettronica è stata recapitata nella posta in arrivo o nella cartella di un utente e l'utente può accedervi.|La posta elettronica è stata inviata alla cartella Posta indesiderata o Eliminata dell'utente e l'utente può accedervi.|Messaggi di posta elettronica messi in quarantena, non riusciti o eliminati. Questi messaggi non sono accessibili all'utente.|La posta elettronica aveva allegati dannosi sostituiti da .txt che indicavano che l'allegato era dannoso.|
|

Ecco cosa può e non può vedere l'utente:

<br>

****

|Accessibile agli utenti finali|Inaccessibile agli utenti finali|
|---|---|
|Recapitati|Bloccato|
|Posta indesiderata|Sostituito|
|

**Percorso di recapito** mostra i risultati dei criteri e dei rilevamenti eseguiti dopo il recapito. È collegato **_all'azione recapito_**. Questi sono i valori possibili:

- *Posta in arrivo o cartella*: il messaggio di posta elettronica si trova nella cartella Posta in arrivo o in una cartella (in base alle regole di posta elettronica).
- *Locale o esterno:* la cassetta postale non esiste nel cloud ma è locale.
- *Cartella posta indesiderata*: il messaggio di posta elettronica si trova nella cartella Posta indesiderata di un utente.
- *Cartella Posta eliminata*: Il messaggio di posta elettronica nella cartella Posta eliminata di un utente.
- *Quarantena*: il messaggio di posta elettronica è in quarantena e non nella cassetta postale di un utente.
- *Failed*: Il messaggio di posta elettronica non è riuscito a raggiungere la cassetta postale.
- *Dropped*: Il messaggio di posta elettronica si è perso da qualche parte nel flusso di posta.

### <a name="email-timeline"></a>Sequenza temporale della posta elettronica

La **sequenza temporale della** posta elettronica è una nuova funzionalità di Explorer che migliora l'esperienza di ricerca per gli amministratori. Riduce il tempo dedicato al controllo di posizioni diverse per cercare di comprendere l'evento. Quando si verificano più eventi in corrispondenza o vicino allo stesso momento dell'arrivo di un messaggio di posta elettronica, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito della posta elettronica vengono acquisiti nella **colonna Azione** speciale. Gli amministratori possono combinare le informazioni della sequenza temporale con l'azione speciale intrapresa sul post-recapito della posta per ottenere informazioni dettagliate sul funzionamento dei criteri, su dove è stata infine instradata la posta e, in alcuni casi, sulla valutazione finale.

Per ulteriori informazioni, vedere Analizzare e correggere i messaggi di posta elettronica dannosi [recapitati in Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Esportare i dati di clic url

È ora possibile esportare i report per i clic url Microsoft Excel per visualizzare **l'ID** messaggio di rete e fare clic su **verdetto**, che consente di spiegare da dove ha avuto origine il traffico di clic sull'URL. Ecco come funziona: in Threat Management sulla barra di Office 365 di avvio veloce, segui questa catena:

**Explorer** \> **Visualizza Phish** \> **Clic** \> **Gli URL principali o** **i clic principali dell'URL** \> selezionano qualsiasi record per aprire il riquadro a comparsa url.

Quando si seleziona un URL nell'elenco,  nel riquadro a comparsa viene visualizzato un nuovo pulsante Esporta. Utilizzare questo pulsante per spostare i dati in un foglio Excel per semplificare la creazione di report.

Seguire questo percorso per accedere alla stessa posizione nel report Rilevamenti in tempo reale:

**Explorer** \> **Rilevamenti in tempo reale** \> **Visualizza Phish** \> **URL** \> **URL principali o** **clic principali Selezionare** qualsiasi record per aprire il riquadro a comparsa URL passare alla \> \> **scheda** Clic.

> [!TIP]
> L'ID messaggio di rete mappa il clic a messaggi di posta elettronica specifici quando si esegue una ricerca sull'ID tramite Esplora risorse o strumenti di terze parti associati. Tali ricerche identificano il messaggio di posta elettronica associato al risultato di un clic. La presenza dell'ID messaggio di rete correlato consente un'analisi più rapida e potente.

> [!div class="mx-imgBorder"]
> ![Scheda Clic in Esplora risorse](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Vedere malware rilevato nella posta elettronica tramite tecnologia

Si supponga di voler visualizzare il malware rilevato nei messaggi di posta elettronica ordinati in base Microsoft 365 tecnologia. A tale scopo, usa la visualizzazione [Posta > malware](threat-explorer-views.md#email--malware) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **delle minacce** (o **Rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **Malware** tramite posta **elettronica** dal menu \> **Visualizza.**

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse](../../media/ExplorerViewEmailMalwareMenu.png)

3. Fare **clic su Mittente** e quindi scegliere **Tecnologia di** rilevamento di \> **base.**

   Le tecnologie di rilevamento sono ora disponibili come filtri per il report.

   > [!div class="mx-imgBorder"]
   > ![Tecnologie di rilevamento malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Scegliere un'opzione. Selezionare quindi il **pulsante** Aggiorna per applicare il filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnologia di rilevamento selezionata](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Il report viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione tecnologia selezionata. Da qui è possibile eseguire ulteriori analisi.

## <a name="view-phishing-url-and-click-verdict-data"></a>Visualizzare l'URL di phishing e fare clic su Dati verdetto

Si supponga di voler visualizzare i tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL consentiti, bloccati ed ignorati. Per identificare gli URL su cui è stato fatto clic, [è necessario](safe-links.md) configurare collegamenti sicuri. Assicurati di configurare i criteri [collegamenti](set-up-safe-links-policies.md) sicuri per la protezione del tempo di clic e la registrazione dei verdetti clic da collegamenti sicuri.

Per esaminare gli URL dei phish nei messaggi e fare clic sugli URL nei messaggi [   >  **phish,**](threat-explorer-views.md#email--phish) usa la visualizzazione Phish e-mail di Esplora risorse o rilevamenti in tempo reale.

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **delle minacce** (o **Rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **E-mail**  \> **phish dal** menu Visualizza.

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse nel contesto di phishing](../../media/ExplorerViewEmailPhishMenu.png)

3. Fare **clic su Mittente** e quindi scegliere **URL Fare** clic su \> **verdetto.**

4. Selezionare una o più opzioni, ad esempio **Blocca** e  Blocca ignorate, e quindi selezionare il pulsante Aggiorna sulla stessa riga delle opzioni per applicare il filtro. Non aggiornare la finestra del browser.

   > [!div class="mx-imgBorder"]
   > ![URL e clic su verdetti](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Il report viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del report:

   - **Gli URL principali sono** gli URL nei messaggi filtrati e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione Posta elettronica phish, questo elenco contiene in genere URL legittimi. Gli utenti malintenzionati includono una combinazione di URL buoni e non recapitati nei messaggi per tentare di ottenerli, ma rendono i collegamenti dannosi più interessanti. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica, ma questa colonna è nascosta per semplificare la visualizzazione.

   - **I clic principali** sono gli URL con ritorno a capo automatico dei collegamenti sicuri su cui è stato fatto clic, ordinati in base al numero totale di clic. Anche questa colonna non viene visualizzata per semplificare la visualizzazione. I conteggi totali per colonna indicano il numero di verdetti clic su Collegamenti sicuri per ogni URL su cui si è fatto clic. Nella visualizzazione Posta elettronica phish, questi url sono in genere sospetti o dannosi. Ma la visualizzazione potrebbe includere URL che non sono minacce ma sono in messaggi di phish. I clic url sui collegamenti senza ritorno a capo non vengono visualizzati qui.

   Le due tabelle URL mostrano gli URL principali nei messaggi di posta elettronica di phishing in base all'azione di recapito e alla posizione. Le tabelle mostrano i clic url bloccati o visitati nonostante un avviso, in modo da poter vedere quali potenziali collegamenti non riusciti sono stati presentati agli utenti e che l'utente ha fatto clic. Da qui è possibile eseguire ulteriori analisi. Ad esempio, sotto il grafico è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.

   > [!div class="mx-imgBorder"]
   > ![URL di Explorer bloccati](../../media/ExplorerPhishClickVerdictURLs.png)

   Selezionare un URL per visualizzare informazioni più dettagliate.

   > [!NOTE]
   > Nella finestra di dialogo riquadro a comparsa URL, il filtro sui messaggi di posta elettronica viene rimosso per mostrare la visualizzazione completa dell'esposizione dell'URL nell'ambiente. In questo modo è possibile filtrare i messaggi di posta elettronica di cui si è preoccupati in Esplora risorse, trovare URL specifici che sono potenziali minacce e quindi espandere la comprensione dell'esposizione degli URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL alla visualizzazione Esplora risorse stessa.

### <a name="interpretation-of-click-verdicts"></a>Interpretazione dei verdetti dei clic

All'interno dei riquadri a comparsa E-mail o URL, Dei clic principali e delle esperienze di filtro, vedrai diversi valori di verdetto clic:

- **Nessuno:** Impossibile acquisire il verdetto per l'URL. L'utente potrebbe aver fatto clic tramite l'URL.
- **Consentito:** All'utente è stato consentito passare all'URL.
- **Bloccato:** All'utente è stato impedito di passare all'URL.
- **Verdetto in sospeso:** All'utente è stata presentata la pagina detonazione in sospeso.
- **Bloccato ignorato:** All'utente è stato impedito di passare direttamente all'URL. Ma l'utente ha sovrascritto il blocco per passare all'URL.
- **Verdetto in sospeso ignorato:** All'utente è stata presentata la pagina di detonazione. Tuttavia, l'utente ha sovrascritto il messaggio per accedere all'URL.
- **Errore:** All'utente è stata presentata la pagina di errore oppure si è verificato un errore durante l'acquisizione del verdetto.
- **Errore:** Eccezione sconosciuta durante l'acquisizione del verdetto. L'utente potrebbe aver fatto clic tramite l'URL.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica segnalati dagli [](enable-the-report-message-add-in.md) utenti dell'organizzazione come Posta *indesiderata,* Non posta indesiderata o *Phishing* tramite il componente aggiuntivo Segnala messaggio o Segnala [phishing.](enable-the-report-phish-add-in.md) Per visualizzarli, usa la visualizzazione [   >  **Invii di posta**](threat-explorer-views.md#email--submissions) elettronica di Explorer (o rilevamenti in tempo reale).

1. Nel Centro sicurezza & conformità ( ), scegliere Esplora gestione <https://protection.office.com>  \> **delle minacce** (o **Rilevamenti in tempo reale).** In questo esempio viene utilizzato Explorer.

2. Scegliere **Invii** **di** posta elettronica dal menu \> **Visualizza.**

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse per i messaggi di posta elettronica](../../media/explorer-view-menu-email-user-reported.png)

3. Fare **clic su Mittente** e quindi scegliere **Tipo di** report di \> **base.**

4. Selezionare un'opzione, ad esempio **Phish,** e quindi fare clic **sul pulsante** Aggiorna.

   > [!div class="mx-imgBorder"]
   > ![Phish segnalato dall'utente](../../media/EmailUserReportedReportType.png)

Il report viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica segnalati da utenti dell'organizzazione come tentativi di phishing. È possibile utilizzare queste informazioni per eseguire ulteriori analisi e, se necessario, modificare i criteri [anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Avviare un'indagine e una risposta automatizzate

> [!NOTE]
> Le funzionalità di analisi e risposta automatizzate sono disponibili in Microsoft Defender per Office 365 *Piano 2* *e Office 365 E5.*

[L'indagine e la risposta automatizzate](automated-investigation-response-office.md) possono risparmiare tempo e impegno per le operazioni di sicurezza dedicato all'analisi e alla mitigazione dei cyberattacchi. Oltre a configurare avvisi che possono attivare un playbook di sicurezza, puoi avviare un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse. Per informazioni dettagliate, vedi Esempio: un amministratore [della sicurezza attiva un'indagine da Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Altri modi per usare Esplora risorse e rilevamenti in tempo reale

Oltre agli scenari descritti in questo articolo, sono disponibili molte più opzioni di creazione di report con Esplora risorse (o rilevamenti in tempo reale). Fare inoltre riferimento ai seguenti articoli:

- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](./mdo-for-spo-odb-and-teams.md)
- [Ottenere una panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)](threat-explorer-views.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Indagine e risposta automatizzate in Microsoft 365 Defender](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Devi disporre di [Microsoft Defender per Office 365](defender-for-office-365.md) usare Explorer o rilevamenti in tempo reale.

- Explorer è incluso in Defender per Office 365 Piano 2.
- Il report rilevamenti in tempo reale è incluso in Defender per Office 365 piano 1.
- Pianificare l'assegnazione delle licenze per tutti gli utenti che devono essere protetti da Defender per Office 365. Explorer e i rilevamenti in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.

Per visualizzare e usare Esplora risorse o rilevamenti in tempo reale, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza.

- Per il Centro sicurezza & conformità, è necessario disporre di uno dei ruoli seguenti:

  - Gestione dell'organizzazione
  - Amministratore della sicurezza (può essere assegnato nell'Azure Active Directory di amministrazione ( <https://aad.portal.azure.com> )
  - Ruolo con autorizzazioni di lettura per la sicurezza

- Per Exchange Online, è necessario disporre di uno dei ruoli seguenti assegnati nell'interfaccia di amministrazione di Exchange ( ) o <https://admin.protection.outlook.com/ecp/> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):

  - Gestione organizzazione
  - Gestione organizzazione sola visualizzazione
  - Destinatari solo visualizzazione
  - Gestione della conformità

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:

- [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)
- [Autorizzazioni funzionalità in Exchange Online](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Differenze tra Esplora minacce e rilevamenti in tempo reale

- Il *report Rilevamenti in tempo* reale è disponibile in Defender per Office 365 Piano 1. *Threat Explorer* è disponibile in Defender per Office 365 Piano 2.
- Il report Rilevamenti in tempo reale consente di visualizzare i rilevamenti in tempo reale. Threat Explorer esegue anche questa operazione, ma fornisce anche ulteriori dettagli per un determinato attacco.
- Una *visualizzazione Tutti i* messaggi di posta elettronica è disponibile in Esplora minacce, ma non nel report Rilevamenti in tempo reale.
- Altre funzionalità di filtro e azioni disponibili sono incluse in Threat Explorer. Per altre informazioni, vedi [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="other-articles"></a>Altri articoli

[Analizzare i messaggi di posta elettronica con la pagina Entità di posta elettronica](mdo-email-entity-page.md)
