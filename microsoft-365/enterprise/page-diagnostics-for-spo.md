---
title: Usare lo strumento Diagnostica pagine per SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Utilizzare lo strumento Diagnostica pagine per SharePoint per analizzare il portale moderno di SharePoint Online e le pagine di pubblicazione classiche in base a un set predefinito di criteri di prestazioni.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696101"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Usare lo strumento Diagnostica pagine per SharePoint

In questo articolo viene descritto come utilizzare lo strumento Diagnostica pagine per **SharePoint** per analizzare le pagine classiche e moderne del sito di SharePoint Online in base a un set predefinito di criteri di prestazioni.

Lo strumento Diagnostica pagine per SharePoint può essere installato per:

- **Microsoft Edge** [(estensione Edge)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(estensione Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>La **versione 2.0.0** e successive include il supporto per le pagine moderne oltre alle pagine classiche del sito. Se non sei sicuro della versione dello strumento in  uso, puoi selezionare il collegamento Informazioni su o i puntini di sospensione (...) per verificare la versione. **Aggiorna sempre all'ultima versione** quando utilizzi lo strumento.

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Questo strumento funziona solo per SharePoint Online e non può essere utilizzato in una pagina di sistema di SharePoint.

Lo strumento genera un report per ogni pagina analizzata che mostra le prestazioni della pagina rispetto a un set predefinito di regole e visualizza informazioni dettagliate quando i risultati di un test non rientrano nel valore di base. Gli amministratori e i progettisti di SharePoint Online possono utilizzare lo strumento per risolvere i problemi di prestazioni e garantire che le nuove pagine siano ottimizzate prima della pubblicazione.

Lo strumento Diagnostica pagine è progettato per analizzare solo le pagine del sito di SharePoint, non le pagine di sistema, ad esempio *allitems.aspx* *o sharepoint.aspx.* Se si tenta di eseguire lo strumento in una pagina di sistema o in qualsiasi altra pagina non del sito, verrà visualizzato un messaggio di errore che indica che non è possibile eseguire lo strumento per quel tipo di pagina.

![Deve essere eseguito in una pagina di SharePoint](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Non si tratta di un errore nello strumento, in quanto non vi è alcun valore nella valutazione delle raccolte o delle pagine di sistema. Passare a una pagina del sito di SharePoint per utilizzare lo strumento. Se questo errore si verifica in una pagina di SharePoint, controllare la pagina master per assicurarsi che i metatag di SharePoint non siano stati rimossi.

Per inviare commenti e suggerimenti sullo strumento, seleziona i puntini di sospensione nell'angolo in alto a destra dello strumento e quindi seleziona [Invia feedback.](https://go.microsoft.com/fwlink/?linkid=874109)

![Inviare commenti e suggerimenti](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Installare lo strumento Diagnostica pagine per SharePoint

La procedura di installazione descritta in questa sezione funziona sia per i browser Chrome che per i browser Microsoft Edge.

> [!IMPORTANT]
> Microsoft non legge i dati o il contenuto delle pagine analizzati dallo strumento Diagnostica pagine per SharePoint e non acquisisce informazioni personali, siti Web o informazioni di download. Le uniche informazioni identificabili registrate a Microsoft dallo strumento sono il nome del tenant, i conteggi delle regole non riuscite e la data e l'ora di esecuzione dello strumento. Queste informazioni vengono utilizzate da Microsoft per comprendere meglio le tendenze di utilizzo del portale e del sito di pubblicazione moderne e i problemi comuni relativi alle prestazioni.

1. Installare lo strumento Diagnostica pagine per SharePoint per Microsoft Edge [(estensione](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) **Edge)** o **Chrome** [(estensione Chrome).](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi) Leggi l'Informativa sulla privacy dell'utente fornita nella pagina di descrizione nello Store. Quando aggiungi lo strumento al browser, verrà visualizzato il seguente avviso sulle autorizzazioni.

    ![Autorizzazioni di estensione](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Questo avviso è presente perché una pagina può contenere contenuto da posizioni esterne a SharePoint a seconda delle web part e delle personalizzazioni nella pagina. Ciò significa che lo strumento leggerà le richieste e le risposte quando si fa clic sul pulsante Start e solo per la scheda di SharePoint attiva in cui lo strumento è in esecuzione. Queste informazioni vengono acquisite localmente dal Web browser ed è disponibile tramite il pulsante  Esporta in **JSON** o Esporta in **HAR** nella scheda Traccia di rete dello strumento. Le informazioni non vengono inviate o acquisite da **Microsoft.** Lo strumento rispetta l'informativa sulla privacy di Microsoft accessibile [qui.](https://go.microsoft.com/fwlink/p/?linkid=857875)

    _L'autorizzazione Gestione download_ illustra l'uso della funzionalità Di esportazione in **JSON** dello strumento. Segui le linee guida sulla privacy della tua azienda prima di condividere il file JSON all'esterno dell'organizzazione, perché i risultati contengono URL e possono essere classificati come informazioni personali (Informazioni personali).
1. Se vuoi usare lo strumento in modalità Incognito o InPrivate, segui la procedura per il browser:
    1. In Microsoft Edge passa a **Estensioni** o digita _edge://extensions_ nella barra dell'URL e seleziona **Dettagli** per l'estensione. Nelle impostazioni dell'estensione seleziona la casella di controllo **Consenti in InPrivate.**
    1. In Chrome, accedere a **Estensioni** o digitare _chrome://extensions_ nella barra dell'URL e selezionare **Dettagli** per l'estensione. Nelle impostazioni dell'estensione, seleziona il dispositivo di scorrimento **consenti in Incognito.**
1. Passare alla pagina del sito di SharePoint in SharePoint Online che si desidera esaminare. È stato consentito il "caricamento ritardato" degli elementi nelle pagine. Di conseguenza, lo strumento non si arresterà automaticamente (questo è da progettazione per supportare tutti gli scenari di caricamento delle pagine). Per interrompere la raccolta, selezionare **Interrompi.** Verificare che il caricamento della pagina sia stato completato prima di interrompere la raccolta dati oppure acquisire solo una traccia parziale.
1. Fare clic sul pulsante della barra degli strumenti dell'estensione ![Diagnostica pagine per il logo di SharePoint](../media/page-diagnostics-for-spo/pagediag-icon32.png) per caricare lo strumento e verrà visualizzata la finestra popup di estensione seguente:

    ![Popup dello strumento Diagnostica pagine](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Selezionare **Avvia per** iniziare la raccolta dei dati per l'analisi.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Cosa verrà visualizzato nello strumento Diagnostica pagine per SharePoint

1. Fare clic sui puntini di sospensione (...) nell'angolo superiore destro dello strumento per trovare i collegamenti seguenti:
   1. Il **collegamento Risorse** aggiuntive fornisce indicazioni generali e dettagli relativi a questo strumento, incluso un collegamento a questo articolo.
   1. Il **collegamento Inviare commenti** e suggerimenti fornisce un collegamento al sito Siti di _SharePoint e Collaboration User Voice._
   1. Il **collegamento** Informazioni include la versione attualmente installata dello strumento e un collegamento diretto all'avviso di terze parti dello strumento.  
1. **L'ID correlazione, SPRequestDuration, SPIISLatency,** **il** tempo di caricamento della pagina e i dettagli **dell'URL** sono in formato informativo e possono essere utilizzati per alcuni scopi.

    ![Dettagli di diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** è un elemento importante quando si lavora con il supporto tecnico Microsoft perché consente loro di raccogliere dati di diagnostica aggiuntivi per la pagina specifica.
   - **SPRequestDuration è** il tempo impiegato da SharePoint per elaborare la pagina. L'esplorazione strutturale, le immagini di grandi dimensioni e molte chiamate API potrebbero contribuire a durare più a lungo.
   - **SPIISLatency è il** tempo in millisecondi impiegato per sharePoint Online per iniziare a caricare la pagina. Questo valore non include il tempo impiegato per la risposta dell'applicazione Web.
   - **Il tempo di caricamento** della pagina è il tempo totale registrato dalla pagina dal momento della richiesta al momento in cui la risposta è stata ricevuta e sottoposta a rendering nel browser. Questo valore è influenzato da una serie di fattori, tra cui la latenza di rete, le prestazioni del computer e il tempo necessario al browser per caricare la pagina.
   - **L'URL** della pagina (Uniform Resource Locator) è l'indirizzo Web della pagina corrente.

1. Nella [**scheda Test di**](#how-to-use-the-diagnostic-tests-tab) diagnostica i risultati dell'analisi vengono visualizzati in tre categorie. **Non sono necessarie azioni,** **opportunità di miglioramento** e **attenzione.** Ogni risultato del test è rappresentato da un elemento in una di queste categorie, come descritto nella tabella seguente:

    |Categoria  |Colore  |Descrizione  |
    |---------|---------|---------|
    |**Attenzione necessaria** |Rosso |Il risultato del test non rientra nel valore di base e influisce sulle prestazioni della pagina. Seguire le indicazioni per la correzione.|
    |**Opportunità di miglioramento** |Giallo |Il risultato del test non rientra nel valore di base e potrebbe contribuire a problemi di prestazioni. Possono essere applicati criteri specifici del test.|
    |**Nessuna azione necessaria** |Verde |Il risultato del test rientra nel valore di base del test.|

    ![Diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Una [**scheda Traccia di**](#how-to-use-the-network-trace-tab) rete fornisce informazioni dettagliate sulle richieste di compilazione delle pagine e sulle risposte.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Come usare la scheda Test di diagnostica

Quando si analizza una pagina del portale moderno di SharePoint o una pagina del sito di pubblicazione classica con lo strumento Diagnostica  pagine per SharePoint, i risultati vengono analizzati utilizzando regole predefinite che confrontano i risultati con i valori di base e vengono visualizzati nella scheda Test di diagnostica. Le regole per determinati test possono utilizzare valori di base diversi per il portale moderno e i siti di pubblicazione classici, a seconda delle differenze tra le due caratteristiche di prestazioni specifiche.

I risultati dei  test visualizzati  nelle categorie Opportunità di miglioramento o Attenzione indicano le aree che devono essere esaminate rispetto alle procedure consigliate e possono essere selezionate per visualizzare informazioni aggiuntive sul risultato. I dettagli per ogni elemento _includono_ un collegamento Ulteriori informazioni che ti guiderà direttamente alle indicazioni appropriate relative al test. I risultati dei test visualizzati nella **categoria Nessuna** azione richiesta indicano la conformità alla regola pertinente e non visualizzano ulteriori dettagli quando sono selezionati.

Le informazioni nella scheda Test di diagnostica non spiegano come progettare le pagine, ma evidenziano i fattori che potrebbero influire sulle prestazioni delle pagine. Alcune funzionalità e personalizzazioni delle pagine hanno un impatto inevitabile sulle prestazioni della pagina e devono essere esaminate per la potenziale correzione o omissione dalla pagina se il loro impatto è sostanziale.

I risultati in rosso o in giallo possono anche indicare web part che aggiornano i dati con una frequenza troppo frequente. Ad esempio, le notizie aziendali non vengono aggiornate ogni secondo, ma le web part personalizzate vengono spesso create per recuperare le ultime notizie ogni secondo invece di implementare elementi di memorizzazione nella cache che potrebbero migliorare l'esperienza utente complessiva. Quando si includono web part in una pagina, tenere presente che spesso esistono modi semplici per ridurre l'impatto sulle prestazioni valutando il valore di ogni parametro disponibile per assicurarsi che sia impostato in modo appropriato per lo scopo previsto.

>[!NOTE]
>I siti del team classici in cui la caratteristica di pubblicazione non è abilitata non possono utilizzare reti CDN. Quando si esegue lo strumento in questi siti, è previsto che il test della rete CDN non riesca e possa essere ignorato, ma sono applicabili tutti i test rimanenti. Le funzionalità aggiuntive della caratteristica di pubblicazione di SharePoint possono aumentare i tempi di caricamento delle pagine, pertanto non è consigliabile attivarla solo per consentire la funzionalità della rete CDN.

>[!IMPORTANT]
>Le regole di test vengono aggiunte e aggiornate regolarmente, quindi fare riferimento alla versione più recente dello strumento per informazioni dettagliate sulle regole correnti e informazioni specifiche incluse nei risultati dei test. Puoi verificare la versione gestendo le estensioni e l'estensione ti consiglierà se è disponibile un aggiornamento.

## <a name="how-to-use-the-network-trace-tab"></a>Come usare la scheda Network Trace

La **scheda Network Trace** fornisce informazioni dettagliate su entrambe le richieste di creazione della pagina e sulle risposte ricevute da SharePoint.

1. **Cercare i tempi di caricamento degli elementi contrassegnati come rosso.** Ogni richiesta e risposta è codificata a colori per indicare l'impatto sulle prestazioni complessive della pagina usando le metriche di latenza seguenti:
    - Verde: \< 500 ms
    - Giallo: 500-1000 ms
    - Rosso: \> 1000 ms

    ![Traccia di rete](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    Nell'immagine mostrata sopra, l'elemento rosso riguarda la pagina predefinita. Verrà sempre visualizzato in rosso, a meno che la pagina non venga caricata in \< 1000 ms (meno di 1 secondo).

2. **Tempi di caricamento degli elementi di test.** In alcuni casi non ci sarà alcun indicatore di tempo o colore perché gli elementi sono già stati memorizzati nella cache dal browser. Per verificarlo correttamente, aprire la pagina, cancellare la cache del browser e quindi fare clic su **Start** per forzare un caricamento di pagina "a freddo" ed essere un vero riflesso del caricamento iniziale della pagina. Questo dovrebbe quindi essere confrontato con il carico di pagina "warm" perché consente anche di determinare quali elementi vengono memorizzati nella cache nella pagina.

3. **Condividere i dettagli rilevanti con altri utenti che possono aiutare ad analizzare i problemi.** Per condividere i dettagli o le informazioni forniti nello strumento con gli sviluppatori o un tecnico, fai clic su Esporta in **JSON** (come mostrato nell'immagine precedente). In questo modo potrai scaricare i risultati, visualizzabili con un visualizzatore di file JSON.

    Se hai scelto di usare la funzionalità di anteprima abilita l'esportazione in *HAR,* il tipo di esportazione verrà visualizzato come **Esporta in HAR.**

    ![Traccia di rete](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Questi risultati contengono URL che possono essere classificati come informazioni personali (Informazioni personali). Assicurarsi di seguire le linee guida dell'organizzazione prima di distribuire tali informazioni.

## <a name="engaging-with-microsoft-support"></a>Interagire con il supporto tecnico Microsoft

È stata inclusa **una funzionalità del livello di** supporto Microsoft che deve essere utilizzata solo quando si lavora direttamente a un caso di supporto. L'utilizzo di questa funzionalità non offre alcun vantaggio se usato senza l'impegno del team di supporto e può rallentare notevolmente le prestazioni della pagina. Non sono disponibili ulteriori informazioni quando si utilizza questa funzionalità nello strumento, poiché le informazioni aggiuntive vengono aggiunte alla registrazione nel servizio.

Non è visibile alcuna modifica, tranne per il fatto che si riceverà una notifica che indica che è stata abilitata e che le prestazioni della pagina verranno notevolmente ridotte di 2-3 volte le prestazioni durante l'attivazione. Sarà rilevante solo per la pagina specifica e la sessione attiva. Per questo motivo, questo deve essere usato con moderamento e solo quando attivamente coinvolto con il supporto.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Per abilitare la funzionalità del livello supporto tecnico Microsoft

1. Aprire lo strumento Diagnostica pagine per SharePoint.
2. Sulla tastiera premere **ALT+MAIUSC+L.** Verrà visualizzata la casella **di controllo Abilita registrazione** supporto.
3. Selezionare la casella di controllo e quindi fare clic su **Start** per ricaricare la pagina e generare la registrazione dettagliata.

    ![Opzione di supporto abilitata](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    È necessario prendere nota del CorrelationID (visualizzato nella parte superiore dello strumento) e fornirlo al rappresentante del supporto per consentire loro di raccogliere informazioni aggiuntive sulla sessione di diagnostica.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
