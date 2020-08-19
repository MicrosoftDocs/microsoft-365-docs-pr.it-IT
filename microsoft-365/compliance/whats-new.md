---
title: Novità della conformità a Microsoft 365
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: L'aggiunta di nuove nuove soluzioni al centro conformità, l'aggiornamento delle funzionalità esistenti in base ai commenti o la documentazione aggiornata e rinnovata, Microsoft 365 consente di rimanere al di sopra del panorama di conformità in continua evoluzione. Scoprire cosa è stato fino a questo mese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9bccaab4c1dd1ac8b4676939d848c0f1a599d86b
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798174"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novità della conformità a Microsoft 365

L'aggiunta di nuove nuove soluzioni al [centro conformità di Microsoft 365](microsoft-365-compliance-center.md), l'aggiornamento delle funzionalità esistenti in base ai commenti e la documentazione aggiornata, Microsoft 365 consente di rimanere al di sopra del panorama di conformità sempre mutevole. Per informazioni sulle novità della conformità di Microsoft 365, vedere oggi stesso. 

> [!NOTE]
> Alcune funzionalità di conformità vengono distribuite a velocità diverse rispetto ai clienti. Se non si vede ancora una funzionalità, provare ad aggiungersi alla [versione mirata](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).


> [!TIP]
> Interessato a cosa succede in altri centri di amministrazione? Consultare questi articoli:<br>[Novità dell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[Novità dell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novità di Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Per informazioni sulle funzionalità di Microsoft 365 che sono state avviate, sono in sviluppo, sono state annullate o sono state rilasciate in precedenza. [365](https://www.microsoft.com/en-us/microsoft-365/roadmap)

## <a name="june-2020"></a>Giugno 2020

### <a name="spotlight-new-data-connectors-hit-preview"></a>Spotlight: i nuovi connettori di dati hanno colpito l'anteprima

Basandosi sulla promessa che consente di importare i dati da origini di terze parti in Microsoft 365, è lieta di annunciare la versione di anteprima di altri due connettori di dati:

- [Messaggio Bloomberg](archive-bloomberg-message-data.md). Importare e archiviare i dati della posta elettronica dei servizi finanziari dallo strumento di collaborazione del messaggio Bloomberg. Dopo che i dati sono stati archiviati nelle cassette postali, è possibile accedere ai dati e utilizzarli in funzionalità di conformità, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo, conformità alla comunicazione e criteri di ritenzione.
- [Chat su ghiaccio](archive-icechat-data.md). Importare e archiviare i dati di chat dei servizi finanziari dallo strumento di collaborazione di ICE chat. Dopo che i dati sono stati archiviati nelle cassette postali, è possibile accedere ai dati e utilizzarli in funzionalità di conformità, ad esempio conservazione per controversia legale, eDiscovery, archiviazione, controllo, conformità alla comunicazione e criteri per il mantenimento.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>Punteggio di conformità & Compliance Manager: i risultati continuano a venire

Gli aggiornamenti di giugno includono una nuova visualizzazione drill-down di valutazione nel [Punteggio di conformità](compliance-score.md). Monitorare lo stato di avanzamento del controllo, aggiungere, eliminare valutazioni direttamente dal punteggio di conformità e altro ancora.

Vuoi rimanere al di sopra degli aggiornamenti per la conformità score e Compliance Manager? Contrassegnare le [Note di rilascio del Punteggio di conformità](compliance-score-release-notes.md) e controllare spesso.

## <a name="may-2020"></a>Maggio 2020

### <a name="spotlight-data-classification-is-officially-released"></a>Spotlight: la classificazione dei dati è stata rilasciata ufficialmente

Classificazione dei dati, aka '[know your data](data-classification-overview.md)', features (Analytics, Content Explorer e Esplora attività) sono state graduate dalla fase di anteprima e sono disponibili per tutte le organizzazioni. Potenti approfondimenti e strumenti consentono di individuare e valutare la modalità di utilizzo di informazioni e etichette sensibili (conservazione e sensibilità) nei contenuti all'interno dell'organizzazione. Esaminare il contenuto che contiene informazioni riservate o se sono state applicate etichette, esplorare l'attività delle etichette tra le posizioni di Microsoft 365, creare tipi di informazioni riservate personalizzate e altro ancora.

Fare un video tour...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Classificatori addestrabili: una correzione e una funzionalità

Potrebbe portare maggiori miglioramenti ai classificatori addestrabili:

- Una correzione basata sui commenti e suggerimenti: quando si esegue il seeding e si addestra un classificatore personalizzato, non è più necessario immettere manualmente gli URL del sito di SharePoint e i percorsi delle cartelle. È ora possibile scegliere da un elenco di siti e cartelle prepopolare.
- Nuova caratteristica: quando si crea un'etichetta di riservatezza e si configurano le impostazioni di etichettatura automatica per le app di Office, è ora possibile applicare automaticamente (o consigliare agli utenti di applicare) l'etichetta al contenuto che corrisponde ai classificatori addestrabili. [Altre informazioni](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>Conformità alla comunicazione: il supporto di Yammer è qui

I messaggi privati e le conversazioni della community pubblica in Yammer sono supportati nei criteri di conformità della comunicazione. Yammer è un canale facoltativo e deve essere in [modalità nativa](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) per supportare l'analisi dei messaggi e degli allegati.

### <a name="data-loss-prevention-new-sharing-restriction"></a>Prevenzione della perdita di dati: nuova restrizione di condivisione

Quando si configura un criterio DLP per proteggere il contenuto in SharePoint o OneDrive, è ora possibile configurare l'azione "limitare l'accesso al contenuto" per bloccare le persone a cui è stato concesso l'accesso al contenuto tramite l'opzione "[chiunque abbia il collegamento](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)".

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Gestione dei rischi Insider: adattare il volume degli avvisi

Le attività degli utenti rilevate dai criteri di rischio Insider sono assegnate a un punteggio di rischio specifico, che a sua data determina la gravità degli avvisi (basso, medio, alto). Per impostazione predefinita, Microsoft 365 genera una determinata quantità di avvisi di gravità bassa, media e alta, ma con la nuova [impostazione volume di avviso](insider-risk-management-settings.md#alert-volume)è possibile aumentare o diminuire il volume in base alle proprie esigenze.

### <a name="pst-import-new-region-supported"></a>Importazione PST: supporto per nuove aree geografiche

Il caricamento di rete è ora disponibile in Emirati Arabi Uniti.

### <a name="sensitivity-labels-new-privacy-option"></a>Etichette di riservatezza: nuova opzione privacy

Quando si configurano le [impostazioni del sito e del gruppo](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings) per un'etichetta, è ora possibile impostare l'opzione privacy su **None-Consenti agli utenti di scegliere gli utenti autorizzati a accedere al sito**. Questa opzione è utile quando si desidera proteggere il contenuto del contenitore utilizzando un'etichetta di riservatezza, ma è comunque possibile che gli utenti configurino l'impostazione di privacy.

## <a name="april-2020"></a>Aprile 2020

### <a name="records-management-overhauland-a-new-addition"></a>Gestione dei record: Revision... e una nuova aggiunta

April include un paio di aggiornamenti chiave per la soluzione di gestione dei record:

- La sezione ' Records Management ' è ora completamente disponibile nel centro conformità. Utilizzare le interfacce utente e le funzionalità aggiornate per il piano di file, le etichette di conservazione e i criteri di etichetta, gli eventi e la disposizione.
- A proposito di disposizione, è stato anche implementato il [certificato di disponibilità](disposition.md#disposition-of-records) dei record in SharePoint e OneDrive. È ora possibile visualizzare un elenco di elementi in quelle posizioni che sono state eliminate automaticamente o dopo una revisione della disposizione.

:::image type="content" source="../media/mcc-records-management-page.png" alt-text="Sezione Gestione record in Microsoft 365 Compliance Center":::

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>Etichette di riservatezza: anteprima di criteri di etichettatura automatica

Con i criteri di etichettatura automatica, è ora possibile applicare automaticamente le etichette di riservatezza ai documenti di SharePoint e OneDrive che sono già stati salvati (aka ' data at rest) e messaggi di posta elettronica che sono già stati inviati o ricevuti (aka ' e-mail in transito '). Poiché questa etichettatura viene applicata dai servizi anziché dalle app, non è necessario preoccuparsi di cosa hanno gli utenti delle app e di quale versione.

Questa funzionalità consente di estendere l'etichettatura sul retro del client già inclusa nelle impostazioni di "etichettatura automatica per le app di Office" quando si crea un'etichetta di riservatezza. Per velocizzare le differenze e i vantaggi delle opzioni di etichettatura automatica, vedere l' [articolo aggiornato](apply-sensitivity-label-automatically.md).

## <a name="march-2020"></a>Marzo 2020

### <a name="introducing-advanced-audit"></a>Introduzione al controllo avanzato

[Advanced audit in Microsoft 365](advanced-audit.md) introduce nuove funzionalità di controllo che consentono all'organizzazione di svolgere indagini forensi e di conformità. Gli Highlight includono la conservazione a lungo termine dei log di controllo, i criteri di conservazione del registro di controllo personalizzato, la nuova azione di controllo delle cassette postali di *MailItemsAccessed* e l'introduzione di un nuovo limite di limitazione a livello di tenant, che fornisce all'organizzazione una quota di larghezza di banda completamente allocata per accedere ai dati di controllo.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>Score Compliance & Compliance Manager: anteprima dei miglioramenti più recenti

Gli aggiornamenti principali per questa versione di anteprima includono:

- Processo semplificato per la creazione e la modifica dei modelli
- Avviso per il controllo delle versioni e per i modelli e le azioni
- Sincronizzazione di azioni comuni tra gruppi
- Supporto per le lingue ora esteso a cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo

Per ulteriori informazioni, vedere [Compliance Score](compliance-score.md) and [Compliance Manager](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>Etichette di riservatezza: supporto per l'etichettatura dei file di Office in SharePoint e OneDrive (anteprima)

L'abilitazione dell'anteprima consente agli utenti di applicare etichette di riservatezza in Office sul Web. Saranno in grado di visualizzare il pulsante **sensitivity** sulla barra multifunzione e il nome dell'etichetta applicata sulla barra di stato. Inoltre, se utilizzano le app desktop per etichettare e quindi salvare i file in SharePoint o OneDrive, Microsoft 365 sarà ora in grado di elaborare il contenuto di questi file se l'etichetta dispone di impostazioni di crittografia applicate. La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca e altre funzionalità di collaborazione saranno supportate anche in queste circostanze.

[Informazioni su come abilitare l'anteprima](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>Febbraio 2020

### <a name="insider-risk-management-is-officially-released"></a>Gestione dei rischi Insider rilasciata ufficialmente

Rullo di tamburi, per favore...<br>La gestione dei rischi Insider è ora disponibile per le organizzazioni con gli abbonamenti seguenti:

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (a pagamento o a prova)
- Sottoscrizione Microsoft 365 Enterprise E3 con il [componente aggiuntivo Microsoft E5 Compliance](https://go.microsoft.com/fwlink/?linkid=2120432)

Heads up che sono stati apportati alcuni miglioramenti dopo la versione di anteprima, inclusi i [nuovi gruppi di ruoli](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) e [le impostazioni a livello di soluzione](insider-risk-management-configure.md#step-4-configure-insider-risk-settings).

Come sempre, si prega di lasciare commenti e suggerimenti quando si utilizza la soluzione in modo da poter continuare a migliorare.

### <a name="records-management"></a>Gestione dei record

Questa nuova soluzione apporta tutte le funzionalità di gestione dei record in un unico ombrello. Tra i punti salienti sono inclusi l'introduzione del controllo delle versioni dei record per SharePoint e OneDrive e la prova dello smaltimento dei record.

![Pagina Gestione record in Microsoft 365 Compliance Center](../media/mcc-records-management-page.png)

[Ulteriori informazioni sulla gestione dei record](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>Spotlight della soluzione: connettori di dati per Facebook e Twitter

Connettori di dati [rilasciati il mese scorso](#just-launched) e stiamo cercando il vostro aiuto per testare i connettori seguenti.

- [Pagine business di Facebook](archive-facebook-data-with-sample-connector.md). Importa e archivia i dati dalle pagine di business di Facebook a Microsoft 365. Vantaggi per le soluzioni di conformità, ad esempio la gestione dei record e eDiscovery.
- [Twitter](archive-twitter-data-with-sample-connector.md). Importa e archivia i dati da Twitter a Microsoft 365. Vantaggi per le soluzioni di conformità, ad esempio la gestione dei record e eDiscovery.

Man mano che si configurano e convalidano questi connettori, si prega di lasciare commenti e suggerimenti su cosa è successo, cosa non è stato e cosa è possibile fare per migliorare l'esperienza.

## <a name="january-2020"></a>Gennaio 2020

L'attesa è terminata. Siamo lieti di annunciare che Microsoft 365 Compliance Center è disponibile per tutti i clienti con i piani di Microsoft 365, Office 365, Enterprise Mobility + Security (EMS) e Windows 10 Enterprise. Tutti i dati o i criteri che sono stati gestiti nel centro sicurezza & conformità sono disponibili nel centro conformità, quindi non è necessario saltare avanti e indietro.

> [!TIP]
> Leggere di nuovo l'aggiornamento del mese scorso per una panoramica su alcune delle [nuove soluzioni](#new-compliance-solutions) presentate di recente, oltre a una [Roadmap](#updated-compliance-solutions) in cui sono riportate le caratteristiche di conformità dal centro sicurezza & conformità ora in Microsoft 365.

Segnalibro e Head Over Now to [https://compliance.microsoft.com](https://compliance.microsoft.com) to tour Your One-Stop-Shop per la gestione della conformità in tutto il tuo org... oppure [leggere questo articolo](microsoft-365-compliance-center.md) per approfondire un po' di più.

![Home page del centro conformità Microsoft 365](../media/mcc-home-ga.png)

Questo mese sono state rilasciate anche soluzioni nuove e aggiornate. Ecco una breve panoramica dei punti salienti.

### <a name="now-in-preview"></a>Ora in anteprima

**Gestione dei rischi Insider (Preview)**

Siamo lieti di annunciare che la nostra soluzione di gestione dei rischi Insider è ora in anteprima pubblica. In poche parole, la gestione dei rischi Insider aiuta l'organizzazione a identificare intelligentemente e ad intervenire sui rischi di informazioni privilegiate fornendo:

- Controlli anonimi per garantire la privacy degli utenti.
- Modelli di criteri intelligenti con indicatori nativi e di terze parti che identificano le minacce privilegiate, ad esempio le perdite di dati.
- Flussi di lavoro di analisi end-to-end integrati che interessano, team HR e Legal.

Ci piacerebbe sapere cosa ne pensi. Quando si utilizza la soluzione, è possibile lasciarci commenti e suggerimenti per essere certi di soddisfare le proprie esigenze quando ci dirigiamo verso la disponibilità generale.

[Ulteriori informazioni sulla gestione dei rischi Insider](insider-risk-management.md)

### <a name="just-launched"></a>Appena avviato

**Conformità delle comunicazioni**

La graduazione dalla fase di anteprima alla disponibilità completa, la conformità alla comunicazione è un componente chiave del nuovo set di soluzioni di rischio Insider. Questa soluzione robusta consente di ridurre al minimo i rischi di comunicazione utilizzando flussi di lavoro per il rilevamento, l'analisi e l'adozione di azioni correttive per i messaggi che non soddisfano gli standard dell'organizzazione.

I commenti dei clienti durante l'anteprima sono stati fantastici. Sono stati apportati numerosi miglioramenti, tra cui un'esperienza di prima esecuzione per iniziare, miglioramenti alle azioni di ricerca e correzione e altro ancora.

[Ulteriori informazioni sulla conformità alla comunicazione](communication-compliance.md)

![Pagina conformità comunicazione nel centro conformità Microsoft 365 che mostra la prima scheda dell'esperienza di benvenuto](../media/mcc-communication-compliance-page-with-fre.png)

**Connettori dati**

Precedentemente, lo spazio di condivisione con altre caratteristiche ' Import ' nel centro sicurezza & conformità di Office 365, i connettori di dati ora hanno la propria abitazione nel centro conformità di Microsoft 365. Utilizzare la nuova pagina ' data connectors ' per importare e archiviare i dati dai file delle risorse umane (HR) dell'organizzazione e da varie piattaforme di terze parti (come Facebook, LinkedIn, Twitter e Instant Bloomberg) alle cassette postali dell'organizzazione Microsoft 365. Una volta importati, i dati possono essere gestiti in diverse soluzioni di conformità, tra cui eDiscovery, gestione dei rischi Insider, conformità alla comunicazione, controllo, criteri di conservazione e altro ancora.

[Altre informazioni sui connettori di dati](archiving-third-party-data.md)

![Pagina connettori dati nel centro conformità di Microsoft 365](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>Aggiornamenti rilevanti

**Nuovi modelli di valutazione per il Punteggio di conformità (anteprima)**

Lavorando sempre duramente per ottenere un vantaggio rispetto al panorama di conformità sempre in evoluzione, il team di conformità Score ha inviato una nuova serie di modelli per valutare la conformità dell'organizzazione rispetto alle normative recenti e ottenere indicazioni su come implementare controlli più efficaci. Verranno visualizzati nuovi modelli per:

- ISO/IEC 27701:2019
- California Consumer Privacy Act (CCPA)
- Brasile-legge generale sulla protezione dei dati (lei Geral de proteção de dados-LGPD)
- SOC 1 tipo 2 e SOC 2 di tipo 2

[Altre informazioni sui modelli di Punteggio di conformità](compliance-score.md#templates)

## <a name="november--december-2019"></a>Novembre & dicembre 2019

Durante le festività, è stata avviata l'implementazione di tutte le soluzioni di conformità che sono state dimostrate in Ignite. La maggior parte è in uno stato di anteprima, quindi testarli e assicurarsi di farci sapere cosa pensi aprendo la scheda di feedback in basso a destra del centro conformità.

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>Conoscere il nuovo quartiere

Il nuovo centro conformità di Microsoft 365 include nuove soluzioni e le funzionalità di conformità che si conoscono e si amano dal centro sicurezza & conformità di Office 365. Let ' s dig in un po' di più...

#### <a name="new-compliance-solutions"></a>Nuove soluzioni di conformità

Potrebbe essere utile sapere cos'è una *soluzione* . Per quanto il cloud abbia rivoluzionato la modalità di gestione delle attività, ha anche aperto la porta a nuovi metodi per il furto e la frode dei dati e ha reso necessarie nuove normative. Le soluzioni di conformità sono raccolte di funzionalità integrate che consentono di gestire i requisiti di conformità in evoluzione. Le funzionalità di una soluzione possono includere una combinazione di criteri, avvisi, report e altro ancora.

Di seguito è illustrato un riepilogo delle nuove soluzioni disponibili. Tieni d'occhio gli altri utenti che verranno presto.

> [!NOTE]
> Queste soluzioni sono situate solo nel centro conformità Microsoft 365. Non possono essere gestiti nel centro sicurezza & conformità di Office 365.
<br/>

|**Nuova soluzione**|**Descrizione**|**Altre informazioni**|
|:-----|:-----|:-----|
|Punteggio di conformità Microsoft (anteprima) <br/>|Creato da [Compliance Manager](compliance-manager-overview.md), il Punteggio di conformità è una funzionalità autonoma con una progettazione più semplice e più facile da usare che consente di comprendere e migliorare la posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi. <br/>|[Panoramica del Punteggio di conformità Microsoft (anteprima)](compliance-score.md)|
|Catalogo delle soluzioni (anteprima) <br/>|Il catalogo della soluzione è il One-Stop-Shop per scoprire, conoscere e iniziare rapidamente con le nostre soluzioni di gestione dei rischi e conformità. Il catalogo è suddiviso in tre categorie di conformità, ognuna delle quali contiene informazioni dettagliate sulle soluzioni che compongono tale categoria. Le categorie includono la protezione delle informazioni & governance, gestione dei rischi Insider e individuazione & risposta <br/>|[Panoramica del catalogo delle soluzioni (anteprima)](microsoft-365-solution-catalog.md)|
|Conformità alla comunicazione (anteprima) <br/>|La conformità alla comunicazione è parte integrante della nuova categoria di gestione dei rischi Insider che consente di ridurre al minimo i rischi di comunicazione contribuendo a rilevare, acquisire e intraprendere azioni correttive per i messaggi inopportuni nell'organizzazione. La soluzione consente di estendere le funzionalità dei criteri di supervisione in Office 365 introducendo diversi nuovi miglioramenti, ad esempio modelli intelligenti, flussi di lavoro di correzione flessibili e approfondimenti che consentono di eseguire le operazioni di monitoraggio. <br/>|[Conformità della comunicazione in Microsoft 365 (anteprima)](communication-compliance.md)|
|Classificazione dei dati (anteprima) <br/>|La nuova pagina di classificazione dei dati contiene potenti strumenti e intuizioni utili per individuare e valutare la modalità di utilizzo di informazioni e etichette sensibili (conservazione e sensibilità) nei contenuti all'interno dell'organizzazione. Esaminare il contenuto che contiene informazioni riservate o applicare etichette, esplorare l'attività delle etichette tra le posizioni di Microsoft 365, creare tipi di informazioni riservate personalizzate e molto altro ancora.<br/>|[Panoramica della classificazione dei dati (anteprima)](data-classification-overview.md)|
|Classificatori addestrabili (anteprima) <br/>|Questo nuovo potente strumento utilizza il motore di apprendimento automatico per identificare le categorie di contenuto dell'organizzazione, ad esempio i documenti di regolamentazione o i contratti con i dipendenti. Una volta creato, i classificatori possono essere utilizzati in diverse soluzioni di conformità per individuare il contenuto correlato e classificarlo, proteggerlo, conservarlo e altro ancora.<br/>|[Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md)|

#### <a name="updated-compliance-solutions"></a>Soluzioni di conformità aggiornate

Se è stato utilizzato il Centro sicurezza & conformità di Office 365 per soddisfare i requisiti di conformità, potrebbe essere utile sapere dove sono presenti alcune funzionalità nel nuovo centro conformità di Microsoft 365. Ecco una guida di orientamento rapida per trovare le loro nuove case.

> [!NOTE]
> Alcune funzionalità sono ancora disponibili solo nel centro sicurezza & conformità di Office 365: queste sono note di seguito. Ma stiamo lavorando duramente per visualizzare in anteprima questi nel centro conformità Microsoft 365, quindi resta sintonizzato per gli aggiornamenti. 
<br/>

|**Caratteristica**|**Centro sicurezza e conformità di Office 365**|**Centro conformità Microsoft 365**|**Altre informazioni**|
|:-----|:-----|:-----|:-----|
|Advanced eDiscovery|eDiscovery > Advanced eDiscovery <br/> https://protection.office.com/advancedediscoverycases |eDiscovery > Advanced <br/> https://compliance.microsoft.com/advancedediscovery | [Panoramica della soluzione avanzata di eDiscovery in Microsoft 365](overview-ediscovery-20.md) |
|Criteri di avviso|Avvisi > criteri di avviso <br/> https://protection.office.com/alertpolicies |In questo momento, i criteri di avviso sono gestiti solo nel centro conformità & sicurezza di Office 365. |[Criteri di avviso nel Centro sicurezza e conformità](alert-policies.md) |
|Avvisi|Avvisi > visualizzare gli avvisi <br/> https://protection.office.com/viewalerts |Avvisi <br/> https://compliance.microsoft.com/compliancealerts |[Visualizzazione degli avvisi](alert-policies.md#viewing-alerts)|
|Archivio|Archivio > di governance delle informazioni <br/> https://protection.office.com/archiving |Scheda Archivio informazioni > di governance <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[Abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md)|
|Ricerca dei log di controllo|Ricerca > log di controllo <br/> https://protection.office.com/unifiedauditlog |Audit <br/> https://compliance.microsoft.com/auditlogsearch | [Eseguire una ricerca nel log di controllo nel centro sicurezza & Compliance](search-the-audit-log-in-security-and-compliance.md)|
|Ricerca contenuto|Ricerca di contenuti > di ricerca <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | Ricerca contenuto <br/> https://compliance.microsoft.com/contentsearch |[Ricerca di contenuto in Office 365](search-for-content.md) |
|Connettori dati|Information Governance > archiviazione dei dati di terze parti <br/> https://protection.office.com/nativeconnector | Connettori dati <br/> https://compliance.microsoft.com/connectorlanding |[Archiviare i dati di terze parti](archiving-third-party-data.md)|
|Prevenzione della perdita di dati|Prevenzione della perdita di dati <br/> https://protection.office.com/datalossprevention |Prevenzione della perdita di dati <br/> https://compliance.microsoft.com/datalossprevention |[Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)|
|Richieste del soggetto dei dati |Privacy dei dati > richieste del soggetto dei dati <br/> https://protection.office.com/dsrcases |Richieste del soggetto dei dati <br/> https://compliance.microsoft.com/datasubjectrequest |[Gestire le richieste del soggetto dei dati di GDPR con lo strumento di gestione dei casi DSR](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|eDiscovery|eDiscovery > eDiscovery <br/> https://protection.office.com/ediscoveryv1 |eDiscovery > Core <br/> https://compliance.microsoft.com/classicediscovery |[Gestire casi di eDiscovery](ediscovery-cases.md) |
|Events|Eventi > di gestione dei record <br/> https://protection.office.com/events |Scheda eventi > di gestione dei record <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[Avviare la conservazione al verificarsi di un evento](event-driven-retention.md)|
|Piano di archiviazione|Gestione dei record > piano file <br/> https://protection.office.com/fileplan |Scheda Gestione record > piano file <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[Usare il piano di archiviazione per gestire le etichette di conservazione](file-plan-manager.md)|
|Importare i file PST|Information Governance > importazione di file PST <br/> https://protection.office.com/importV2 |Scheda Importazione > di governance delle informazioni <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[Panoramica dell'importazione di file PST dell'organizzazione](importing-pst-files-to-office-365.md)|
|Esplora attività etichette|Gestione delle informazioni > label Activity Explorer <br/> https://protection.office.com/labelexplorer |Classificazione dei dati > scheda Esplora attività <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[Visualizzare le attività sul contenuto etichettato (anteprima)](data-classification-activity-explorer.md)|
|Etichette di conservazione e criteri di etichetta |Schede di classificazione > etichette di conservazione > etichette e criteri etichetta <br/> https://protection.office.com/retentionlabels |Schede per la governance delle informazioni > etichette e criteri etichetta <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | [Panoramica delle etichette di conservazione](retention.md)|
|Criteri di conservazione|Gestione delle informazioni > conservazione <br/> https://protection.office.com/retention |Scheda conservazione > di gestione delle informazioni <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[Informazioni sui criteri e sulle etichette di conservazione](retention.md)|
|Tipi di informazioni riservate|Classificazione > tipi di informazioni riservate <br/> https://protection.office.com/sensitivetypes |Classificazione dei dati > scheda tipi di informazioni riservate <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)|
|Etichette di riservatezza e criteri di etichetta|Classificazione > etichette di riservatezza > etichette e schede criteri etichetta <br/> https://protection.office.com/sensitivity |Schede per la protezione delle informazioni > etichette e criteri etichette <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[Informazioni sulle etichette di riservatezza](sensitivity-labels.md) |
|Garanzia del servizio|Garanzia del servizio <br/> https://protection.office.com/serviceassurance/dashboard |A questo punto, è possibile accedere alle risorse di Service Assurance solo nel centro sicurezza & conformità di Office 365. |[Garanzia del servizio nel Centro sicurezza e conformità](service-assurance.md)|
|Supervisione|Supervisione <br/> https://protection.office.com/supervisoryreviewv2 |Conformità delle comunicazioni <br/> https://compliance.microsoft.com/supervisoryreview |[Conformità della comunicazione in Microsoft 365 (anteprima)](communication-compliance.md) |

## <a name="september-2019"></a>Settembre 2019

Si sta chiedendo perché è tranquillo sul fronte del rilascio di questo mese? Siamo responsabili della creazione di nuove soluzioni di conformità innovative che verranno svelate a [Microsoft Ignite](https://www.microsoft.com/ignite) nel novembre. Restate sintonizzati!

### <a name="new-encryption-options-for-sensitivity-labels"></a>Nuove opzioni di crittografia per le etichette di riservatezza 

Quando si configura la crittografia per un'etichetta di riservatezza, sono ora disponibili due opzioni che consentono agli utenti di assegnare le autorizzazioni quando applicano manualmente l'etichetta alla posta elettronica e ai documenti:<br>
- Quando si applica l'etichetta al **messaggio di posta elettronica di Outlook**, gli utenti possono applicare restrizioni equivalenti all'opzione non inoltrare. I destinatari saranno in grado di leggere il messaggio, ma non di inoltrarlo, stamparlo o copiarlo.
- Quando si applica l'etichetta ai **file Word, PowerPoint ed Excel**, agli utenti verrà richiesto di assegnare le autorizzazioni di accesso a utenti e gruppi specifici.

Andare a [limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](encryption-sensitivity-labels.md#let-users-assign-permissions) per ulteriori informazioni.

## <a name="august-2019"></a>Agosto 2019

### <a name="update-to-data-investigations"></a>Aggiornamento alle indagini sui dati

Quando si esegue un'analisi dei dati, è ora possibile eliminare gli elementi dai percorsi originali. Questo significa che è possibile eliminare gli elementi da cassette postali di Exchange, siti di SharePoint e account di OneDrive nell'organizzazione. Dal momento che gli elementi sono stati raccolti come prova, è possibile che vengano conservate copie del gruppo di prove, in modo da poter indagare ulteriormente o conservare come riferimento. [Altre informazioni](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) Quando si esegue un'analisi dei dati, è ora possibile eliminare gli elementi dai percorsi originali. Questo significa che è possibile eliminare gli elementi da cassette postali di Exchange, siti di SharePoint e account di OneDrive nell'organizzazione. Dal momento che gli elementi sono stati raccolti come prova, è possibile che vengano conservate copie del gruppo di prove, in modo da poter indagare ulteriormente o conservare come riferimento. Per ulteriori informazioni, vedere [gestire un problema di fuoriuscita dei dati in Microsoft 365](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) . 

## <a name="july-2019"></a>Luglio 2019

### <a name="new-admin-roles"></a>Nuovi ruoli di amministratore

Sono stati rilasciati due nuovi ruoli di amministratore che consentono di gestire la sicurezza e la conformità nell'org. Dillo a tutti i tuoi amici.

- **Amministratore dei dati di conformità**. Gli utenti che dispongono di questo ruolo dispongono delle autorizzazioni per proteggere e monitorare i dati nel centro conformità di Microsoft 365, nell'interfaccia di amministrazione di Microsoft 365 e in Azure. Possono anche gestire tutto l'interfaccia di amministrazione di Exchange, Compliance Manager, teams & interfaccia di amministrazione di Skype for business e creare ticket di supporto per Azure e Microsoft 365.
- **Operatore di sicurezza**. Gli utenti che dispongono di questo ruolo possono gestire gli avvisi e disporre dell'accesso globale in sola lettura alle funzionalità correlate alla sicurezza, inclusi tutti gli elementi presenti in Microsoft 365 Security Center, Azure Active Directory, Identity Protection, Privileged Identity Management e Office 365 Security & Compliance Center.

[Ulteriori informazioni su questi ruoli](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>Ricerca e filtro per i report

Non è più possibile scorrere un mare di report per trovare quelli desiderati. È ora possibile cercare i report (basati sui rispettivi titoli) e filtrare su categorie quali "label" e "Compliance" e fonti quali "Office 365" e "Microsoft cloud app Security".

![Acquisizione dello schermo dei pulsanti di ricerca e del filtro per i report con un filtro applicato](../media/mcc_report_filtering.png)
