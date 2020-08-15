---
title: Utilizzare lo strumento di diagnostica delle pagine per SharePoint Online
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
description: Utilizzare lo strumento page Diagnostics for SharePoint per analizzare i moderni portale e le pagine di pubblicazione classiche di SharePoint online in base a un set predefinito di criteri di prestazioni.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696101"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Utilizzare lo strumento page Diagnostics for SharePoint

In questo articolo viene descritto come utilizzare lo **strumento page Diagnostics for SharePoint** per analizzare pagine del sito moderne e classiche di SharePoint online in base a un set predefinito di criteri di prestazioni.

È possibile installare lo strumento page Diagnostics for SharePoint per:

- **Microsoft Edge** [(estensione perimetrale)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(estensione Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>La versione **2.0.0** e versioni successive include il supporto per le pagine moderne oltre alle pagine del sito classiche. Se non si è certi di quale versione dello strumento si sta utilizzando, è possibile selezionare il collegamento **About** o i puntini di controllo (...) per verificare la versione. **Aggiornare sempre la versione più recente quando si** utilizza lo strumento.

Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni. Questo strumento funziona solo per SharePoint Online e non può essere utilizzato in una pagina di sistema di SharePoint.

Lo strumento genera un rapporto per ogni pagina analizzata che mostra la modalità di esecuzione della pagina in base a un set di regole predefinito e visualizza informazioni dettagliate quando i risultati di un test non rientrano nel valore previsto. Gli amministratori e i progettisti di SharePoint Online possono utilizzare lo strumento per la risoluzione dei problemi relativi alle prestazioni e per garantire che le nuove pagine vengano ottimizzate prima della pubblicazione.

Lo strumento page Diagnostics è stato creato per analizzare solo le pagine del sito di SharePoint e non le pagine di sistema, ad esempio *AllItems. aspx* o *SharePoint. aspx*. Se si tenta di eseguire lo strumento in una pagina di sistema o in qualsiasi altra pagina non del sito, verrà visualizzato un messaggio di errore che indica che non è possibile eseguire lo strumento per il tipo di pagina.

![Deve essere eseguito in una pagina di SharePoint](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Non si tratta di un errore nello strumento poiché non è presente alcun valore per la valutazione di raccolte o pagine di sistema. Passare a una pagina del sito di SharePoint per utilizzare lo strumento. Se si verifica questo errore in una pagina di SharePoint, controllare la pagina master per assicurarsi che i metatag di SharePoint non siano stati rimossi.

Per fornire commenti e suggerimenti sullo strumento, selezionare i puntini di sospensione nell'angolo in alto a destra dello strumento e quindi fare clic su [Invia commenti e suggerimenti](https://go.microsoft.com/fwlink/?linkid=874109).

![Inviare commenti e suggerimenti](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Installare lo strumento page Diagnostics for SharePoint

La procedura di installazione in questa sezione funzionerà per i browser Chrome e Microsoft Edge.

> [!IMPORTANT]
> Microsoft non legge i dati o il contenuto della pagina analizzati dallo strumento page Diagnostics for SharePoint e non acquisisce informazioni personali, siti Web o informazioni di download. Le uniche informazioni identificabili registrate in Microsoft dallo strumento sono il nome del tenant, i conteggi delle regole che hanno avuto esito negativo e la data e l'ora in cui è stato eseguito lo strumento. Queste informazioni vengono utilizzate da Microsoft per comprendere meglio i moderni trend di utilizzo dei siti e del portale di pubblicazione e i problemi di prestazioni comuni.

1. Installare lo strumento page Diagnostics for SharePoint per **Microsoft Edge** [(Edge Extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) o **Chrome** [(Chrome Extension)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi). Leggere i criteri di privacy degli utenti disponibili nella pagina di descrizione dell'archivio. Quando si aggiunge lo strumento al browser, verrà visualizzato il seguente avviso di autorizzazione.

    ![Autorizzazioni di estensione](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Questo avviso è sul posto perché una pagina può contenere contenuto proveniente da percorsi esterni a SharePoint a seconda delle web part e delle personalizzazioni della pagina. Questo significa che nello strumento verranno lette le richieste e le risposte quando si fa clic sul pulsante Start e solo per la scheda attiva di SharePoint in cui è in esecuzione lo strumento. Queste informazioni vengono acquisite localmente dal Web browser ed è disponibile per l'utente tramite il pulsante **Esporta in JSON** o **Esporta in har** nella scheda traccia di _rete_ dello strumento. **le informazioni non vengono inviate o acquisite da Microsoft.** (Lo strumento rispetta l'informativa sulla privacy di Microsoft accessibile [qui](https://go.microsoft.com/fwlink/p/?linkid=857875)).

    L'autorizzazione _Gestisci i download_ copre l'utilizzo della funzionalità di **esportazione in JSON** dello strumento. Seguire le linee guida sulla privacy della propria azienda prima di condividere il file JSON all'esterno dell'organizzazione, in quanto i risultati contengono URL e possono essere classificati come PII (informazioni di identificazione personale).
1. Se si desidera utilizzare lo strumento in modalità incognito o InPrivate, seguire la procedura per il browser:
    1. In Microsoft Edge, passare a **Extensions** o digitare _Edge://Extensions_ nella barra degli URL e selezionare **Dettagli** per l'estensione. Nelle impostazioni di estensione, selezionare la casella di controllo **Consenti in InPrivate**.
    1. In Chrome, passare a **Extensions** o digitare _Chrome://Extensions_ nella barra degli URL e selezionare **Dettagli** per l'estensione. Nelle impostazioni di estensione, selezionare il dispositivo di scorrimento per **Consenti in incognito**.
1. Passare alla pagina del sito di SharePoint in SharePoint Online che si desidera esaminare. È stato consentito il "caricamento ritardato" degli elementi nelle pagine; di conseguenza, lo strumento non si arresterà automaticamente (in base alla progettazione per contenere tutti gli scenari di caricamento delle pagine). Per interrompere l'insieme, selezionare **Interrompi**. Verificare che il caricamento della pagina sia stato completato prima di interrompere la raccolta dei dati oppure acquisire solo una traccia parziale.
1. Fare clic sul pulsante della barra degli strumenti dell'estensione ![Diagnostica pagina per il logo di SharePoint](../media/page-diagnostics-for-spo/pagediag-icon32.png) per caricare lo strumento e viene visualizzata la finestra popup di estensione seguente:

    ![Popup dello strumento di diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Selezionare **inizia** per iniziare la raccolta dei dati per l'analisi.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Cosa verrà visualizzato nello strumento page Diagnostics for SharePoint

1. Fare clic sui puntini di ellisse (...) nell'angolo superiore destro dello strumento per trovare i collegamenti seguenti:
   1. Il collegamento **risorse aggiuntive** fornisce indicazioni generali e dettagli relativi allo strumento, tra cui un collegamento a questo articolo.
   1. Il collegamento **Invia commenti e suggerimenti** fornisce un collegamento ai _siti di SharePoint e al sito vocale dell'utente di collaborazione_ .
   1. Il collegamento **About** include la versione correntemente installata dello strumento e un collegamento diretto all'avviso di terze parti dello strumento.  
1. L' **ID correlazione, SPRequestDuration, SPIISLatency**, il **tempo di caricamento delle pagine**e i dettagli **URL** sono informativi e possono essere utilizzati per alcuni scopi.

    ![Dettagli sulla diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationId** è un elemento importante quando si utilizza il supporto tecnico Microsoft in quanto consente di raccogliere ulteriori dati di diagnostica per la pagina specifica.
   - **SPRequestDuration** è il tempo necessario per l'elaborazione della pagina da parte di SharePoint. La struttura di spostamento strutturale, le immagini di grandi dimensioni, numerose chiamate API potrebbero contribuire a una durata più lunga.
   - **SPIISLatency** è il tempo in millisecondi per cui è stato effettuato il caricamento della pagina di SharePoint Online. Questo valore non include il tempo necessario per l'applicazione Web per rispondere.
   - **Tempo di caricamento della pagina** indica il tempo totale registrato dalla pagina dal momento della richiesta al momento in cui la risposta è stata ricevuta e sottoposta a rendering nel browser. Questo valore è influenzato da una serie di fattori, tra cui la latenza della rete, le prestazioni del computer e il tempo necessario per il caricamento della pagina da parte del browser.
   - L' **URL della pagina** (Uniform Resource Locator) è l'indirizzo Web della pagina corrente.

1. Nella scheda [**test diagnostici**](#how-to-use-the-diagnostic-tests-tab) vengono visualizzati i risultati dell'analisi in tre categorie. **Nessuna azione necessaria**, **possibilità di miglioramento** e **attenzione richieste**. Ogni risultato del test è rappresentato da un elemento in una di queste categorie, come descritto nella tabella seguente:

    |Category  |Colore  |Descrizione  |
    |---------|---------|---------|
    |**Attenzione necessaria** |Rosso |I risultati del test non rientrano nel valore previsto e incidono sulle prestazioni della pagina. Seguire le istruzioni per la correzione.|
    |**Opportunità di miglioramento** |Giallo |Il risultato del test non rientra nel valore previsto e potrebbe contribuire ai problemi di prestazioni. È possibile applicare criteri specifici del test.|
    |**Nessuna azione necessaria** |Verde |Il risultato del test rientra nel valore di base del test.|

    ![Diagnostica pagina](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Una scheda di [**traccia di rete**](#how-to-use-the-network-trace-tab) fornisce informazioni dettagliate sulle richieste e le risposte di compilazione della pagina.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Come utilizzare la scheda test di diagnostica

Quando si analizza una pagina di SharePoint moderna o un sito di pubblicazione classico con lo strumento page Diagnostics for SharePoint, i risultati vengono analizzati utilizzando regole predefinite che consentono di confrontare i risultati con i valori della linea di base e visualizzati nella scheda **test diagnostici** . le regole per alcuni test possono utilizzare valori di base diversi per i siti di pubblicazione classico e portale moderni a seconda del modo in cui le caratteristiche

I risultati dei test visualizzati nelle categorie di **miglioramento** o di **attenzione richieste** indicano le aree che devono essere esaminate in base alle procedure consigliate e possono essere selezionate per visualizzare informazioni aggiuntive sul risultato. I dettagli per ogni elemento includono un collegamento per ulteriori _informazioni_ , che consentirà di eseguire direttamente le indicazioni appropriate relative al test. I risultati dei test visualizzati nella categoria **Nessuna azione obbligatoria** indicano la conformità con la regola pertinente e non visualizzano ulteriori dettagli quando vengono selezionati.

Le informazioni nella scheda test di diagnostica non indicano come progettare le pagine, ma evidenziano fattori che potrebbero influire sulle prestazioni della pagina. Alcune funzionalità e personalizzazioni delle pagine hanno un impatto inevitabile sulle prestazioni delle pagine e devono essere esaminate per una possibile correzione o omissione dalla pagina se il loro impatto è sostanziale.

I risultati di colore rosso o giallo possono inoltre indicare le web part che aggiornano i dati con troppa frequenza. Ad esempio, le notizie aziendali non vengono aggiornate ogni secondo, ma le web part personalizzate vengono spesso create per recuperare le ultime notizie ogni secondo anziché implementare elementi di memorizzazione nella cache che potrebbero migliorare l'esperienza utente complessiva. Tenere presente quando si includono le web part in una pagina che spesso sono semplici modi per ridurre l'impatto delle prestazioni valutando il valore di ogni parametro disponibile per garantire che sia impostato in modo appropriato per lo scopo previsto.

>[!NOTE]
>Non è possibile utilizzare reti CDN per i siti del team classico che non dispongono della caratteristica di pubblicazione abilitata. Quando si esegue lo strumento in questi siti, il test della rete CDN dovrebbe avere esito negativo e può essere ignorato, ma tutti i test restanti sono applicabili. La funzionalità aggiuntiva della caratteristica di pubblicazione di SharePoint può aumentare i tempi di caricamento delle pagine, quindi non dovrebbe essere abilitata solo per consentire la funzionalità CDN.

>[!IMPORTANT]
>Le regole di test vengono aggiunte e aggiornate regolarmente, quindi fare riferimento alla versione più recente dello strumento per informazioni dettagliate sulle regole correnti e sulle informazioni specifiche incluse nei risultati dei test. È possibile verificare la versione gestendo le estensioni e l'estensione consiglierà se è disponibile un aggiornamento.

## <a name="how-to-use-the-network-trace-tab"></a>Come usare la scheda traccia di rete

La scheda **traccia di rete** fornisce informazioni dettagliate su entrambe le richieste di creazione della pagina e sulle risposte ricevute da SharePoint.

1. **Cercare i tempi di caricamento degli elementi contrassegnati come rossi**. Ogni richiesta e risposta è codificata a colori per indicare il relativo impatto sulle prestazioni complessive della pagina utilizzando le metriche di latenza seguenti:
    - Verde: \< 500ms
    - Giallo: 500-1000ms
    - Rosso: \> 1000ms

    ![Traccia di rete](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    Nell'immagine sopra riportata, l'elemento rosso appartiene alla pagina predefinita. La visualizzazione sarà sempre rossa, a meno che la pagina non venga caricata in \< 1000ms (meno di 1 secondo).

2. **Tempi di caricamento degli elementi di prova**. In alcuni casi non vi sarà alcun indicatore di tempo o colore perché gli elementi sono già stati memorizzati nella cache dal browser. Per eseguire il testing in modo corretto, aprire la pagina, cancellare la cache del browser e quindi fare clic su **Avvia** come che forza il caricamento di una pagina "fredda" ed essere una vera riflessione del caricamento della pagina iniziale. Questo dovrebbe essere quindi confrontato con il caricamento della pagina "calda", che consentirà anche di determinare quali elementi vengono memorizzati nella cache della pagina.

3. **Condividere i dettagli rilevanti con altri utenti che possono contribuire all'analisi dei problemi**. Per condividere i dettagli o le informazioni fornite nello strumento con gli sviluppatori o con una persona del supporto tecnico, fare clic su **Esporta in JSON** (come mostrato nell'immagine precedente). Che consentirà di scaricare i risultati, visualizzabili con un visualizzatore di file JSON.

    Se si è scelto di utilizzare la funzionalità di anteprima per *abilitare l'esportazione a Har* , il tipo di esportazione verrà visualizzato come **Export to har**.

    ![Traccia di rete](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Questi risultati contengono URL e possono essere classificati come PII (informazioni di identificazione personale). Assicurarsi di seguire le linee guida dell'organizzazione prima di distribuire tali informazioni.

## <a name="engaging-with-microsoft-support"></a>Interazione con il supporto tecnico Microsoft

È stata inclusa una **funzionalità di Microsoft Support Level** che dovrebbe essere utilizzata solo quando si lavora direttamente su un caso di supporto. L'utilizzo di questa funzionalità non offrirà alcun vantaggio quando viene utilizzato senza l'impegno del team di supporto e può rendere l'esecuzione della pagina significativamente più lenta. Quando si utilizza questa funzionalità nello strumento non sono disponibili ulteriori informazioni, in quanto le informazioni aggiuntive vengono aggiunte alla registrazione nel servizio.

Nessuna modifica è visibile, tranne per il fatto che si riceverà una notifica che è stata abilitata e che le prestazioni della pagina saranno significativamente diminuite di 2-3 volte le prestazioni più lente quando sono abilitate. Sarà pertinente solo per la pagina specifica e per la sessione attiva. Per questo motivo, questo dovrebbe essere usato con parsimonia e solo quando attivamente impegnato con il supporto.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Per abilitare la caratteristica livello di supporto Microsoft

1. Aprire lo strumento page Diagnostics for SharePoint.
2. Sulla tastiera, premere **ALT-MAIUSC-L**. Verrà visualizzata la casella di controllo **Abilita registrazione del supporto** .
3. Selezionare la casella di controllo e quindi fare clic su **Avvia** per ricaricare la pagina e generare la registrazione dettagliata.

    ![Opzione di supporto attivata](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    È necessario tenere presente il parametro CorrelationID (visualizzato nella parte superiore dello strumento) e inviarlo al rappresentante del supporto tecnico per consentire loro di raccogliere ulteriori informazioni sulla sessione di diagnostica.

## <a name="related-topics"></a>Argomenti correlati

[Ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)

[Prestazioni nell'esperienza moderna di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
