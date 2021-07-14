---
title: Analizzare gli avvisi di rilevamento delle anomalie
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Analizzare gli avvisi di rilevamento delle anomalie.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420472"
---
# <a name="investigate-anomaly-detection-alerts"></a>Analizzare gli avvisi di rilevamento delle anomalie

 La governance delle app Microsoft fornisce rilevamenti di sicurezza e avvisi per attività dannose. Lo scopo di questa guida è fornire informazioni generali e pratiche su ciascun avviso, in modo da facilitare le attività di indagine e correzione. In questa guida sono incluse informazioni generali sulle condizioni per l'attivazione degli avvisi. Poiché i rilevamenti di anomalie non sono prevedibili per natura, vengono attivati solo quando c'è un comportamento che devia dalla norma. Infine, alcuni avvisi potrebbero essere in anteprima, quindi è consigliabile esaminare regolarmente la documentazione ufficiale per informazioni aggiornate sullo stato degli avvisi.

## <a name="mitre-attck"></a>MITRE ATT&CK

Per semplificare la mappatura della relazione tra gli avvisi di governance delle app Microsoft e la matrice familiare MITRE ATT&CK, gli avvisi sono stati classificati in base alla tattica MITRE ATT&CK corrispondente. Questo riferimento aggiuntivo semplifica la comprensione della tecnica di attacchi sospetti in uso, quando viene attivato l'avviso di sicurezza e governance delle applicazioni Microsoft.

Questa guida fornisce informazioni sull'analisi e sulla correzione degli avvisi di governance delle app Microsoft nelle categorie seguenti.

- Accesso iniziale
- Esecuzione
- Persistenza
- Escalation dei privilegi
- Evasione delle difese
- Accesso alle credenziali
- Raccolta
- Sottrazione di dati
- Impatto

## <a name="security-alert-classifications"></a>Classificazioni degli avvisi di sicurezza

Dopo un'adeguata indagine, tutti gli avvisi di governance delle app Microsoft possono essere classificati in base a uno dei seguenti tipi di attività:

- Vero positivo (TP): un avviso su un'attività dannosa confermata.
- Vero positivo non dannoso (B-TP): avviso su attività sospette ma non dannose, ad esempio un test di penetrazione o altre azioni sospette autorizzate.
- Falso positivo (FP): avviso su un'attività non dannosa.

## <a name="general-investigation-steps"></a>Passaggi generali dell'indagine

È consigliabile usare le seguenti linee guida generali durante l'analisi dei tipi di avviso per avere una maggiore comprensione della potenziale minaccia prima di applicare l'azione consigliata.

- Esaminare il livello di gravità dell'app e confrontarlo con il resto delle app nel tenant. Questa revisione consentirà di identificare quali app nel tenant rappresentano il rischio maggiore.
- Se viene identificato un TP, esaminare tutte le attività dell'app per comprendere l'impatto. Ad esempio, esaminare le informazioni seguenti sull'app:

  - Ambiti a cui è stato concesso l'accesso
  - Comportamento insolito  
  - Indirizzo IP e posizione

## <a name="initial-access-alerts"></a>Avvisi di accesso iniziale

Questa sezione descrive gli avvisi che indicano che un'app dannosa potrebbe tentare di mantenere il controllo nell'organizzazione.  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>Nome dell'app codificata con ambiti di consenso sospetti

**Gravità:** media

**Descrizione**: questo rilevamento identifica le app OAuth con caratteri, ad esempio caratteri Unicode o codificati, richiesti per gli ambiti di consenso sospetti e che hanno eseguito l'accesso alle cartelle di posta elettronica degli utenti tramite l'API Graph. Questo avviso può indicare un tentativo di mimetizzare un'app dannosa come app nota e attendibile, in modo che gli antagonisti possano indurre gli utenti a fornire il consenso all'app dannosa.

**TP o FP?**

- **TP**: se è possibile confermare che l'app OAuth ha codificato il nome visualizzato con gli ambiti sospetti recapitati da un'origine sconosciuta, viene indicato un vero positivo.  

  **Azione consigliata**: esaminare il livello di autorizzazione richiesto dall'app e quali utenti hanno concesso l'accesso. In base all'indagine, è possibile scegliere di escludere l'accesso a questa app.

  Per escludere l'accesso all'app, nella pagina delle app OAuth, nella riga in cui viene visualizzata l'app da escludere, selezionare l'icona di esclusione. È possibile scegliere di indicare agli utenti che l'app che hanno installato e autorizzato è stata esclusa. La notifica informa gli utenti che l'app verrà disabilitata e che non avranno accesso all'app connessa. Se non si vuole informare gli utenti, deselezionare "Invia una notifica agli utenti che hanno concesso l'accesso a questa app vietata" nella finestra di dialogo. È consigliabile informare gli utenti che l'app verrà presto bloccata e non sarà più possibile usarla.

- **FP**: se si vuole confermare che l'app ha un nome codificato ma ha un uso aziendale legittimo nell'organizzazione.

  **Azione consigliata**: ignorare l'avviso.

#### <a name="understand-the-scope-of-the-breach"></a>Comprendere l'ambito della violazione

Seguire l'esercitazione [Analizzare le app OAuth rischiose](/cloud-app-security/investigate-risky-oauth).

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>L'app OAuth con ambiti di lettura ha un URL di risposta sospetto

**Gravità**: media

**Descrizione**: questo rilevamento identifica un'app OAuth con solo ambiti di lettura, ad esempio User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared e reindirizza all'URL di risposta sospetto tramite l'API Graph. Questa attività tenta di indicare che l'app dannosa con autorizzazioni con privilegi inferiori (come gli ambiti di lettura) potrebbe essere sfruttata per condurre una ricognizione degli account utente.

**TP o FP?**

- **TP**: se è possibile confermare che l'app OAuth con ambito di lettura viene recapitata da un'origine sconosciuta e reindirizza a un URL sospetto, viene indicato un vero positivo.

  **Azione consigliata**: esaminare l'URL di risposta e gli ambiti richiesti dall'app. In base all'indagine, è possibile scegliere di escludere l'accesso a questa app. Esaminare il livello di autorizzazione richiesto dall'app e quali utenti hanno concesso l'accesso.

  Per escludere l'accesso all'app, nella pagina delle app OAuth, nella riga in cui viene visualizzata l'app da escludere, selezionare l'icona di esclusione. È possibile scegliere di indicare agli utenti che l'app che hanno installato e autorizzato è stata esclusa. La notifica informa gli utenti che l'app verrà disabilitata e che non avranno accesso all'app connessa. Se non si vuole informare gli utenti, deselezionare "Invia una notifica agli utenti che hanno concesso l'accesso a questa app vietata" nella finestra di dialogo. È consigliabile informare gli utenti che l'app verrà presto bloccata e non sarà più possibile usarla.

- **B-TP**: se dopo un'indagine, è possibile verificare che l'app abbia un uso aziendale legittimo nell'organizzazione.

  **Azione consigliata**: ignorare l'avviso.

#### <a name="understand-the-scope-of-the-breach"></a>Comprendere l'ambito della violazione 

1. Esaminare tutte le attività eseguite dall'app.
1. Se si hanno dubbi che un'app sia sospetta, è consigliabile analizzare il nome e l'URL di risposta dell'app in diversi app store. Quando si controllano gli app store, concentrarsi sui tipi di app seguenti:
   - App create di recente.
   - App con un URL di risposta sospetto
   - App che non sono state aggiornate di recente. La mancanza di aggiornamenti potrebbe indicare che l'app non è più supportata.
1. Se si hanno dubbi che un'app sia sospetta, è possibile cercare il nome dell'app, il nome dell'editore e l'URL di risposta online  

## <a name="persistence-alerts"></a>Avvisi di persistenza

Questa sezione descrive gli avvisi che indicano che un antagonista potrebbe tentare di mantenere il controllo nell'organizzazione.

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>L'app con ambito OAuth sospetto crea una regola Posta in arrivo  

**Gravità**: media

**ID MITRE**: T1137.005, T1114  

Questo rilevamento identifica un'app OAuth che ha acconsentito a ambiti sospetti, crea una regola Posta in arrivo sospetta e accede alle cartelle di posta e ai messaggi degli utenti tramite l'API Graph. Le regole Posta in arrivo, ad esempio l'inoltro di tutte o specifiche e-mail a un altro account di posta elettronica, e le chiamate Graph per accedere alle e-mail e inviarle a un altro account di posta elettronica, possono essere un tentativo di esfiltrare le informazioni dall'organizzazione.  

**TP o FP?**

- **TP**: se è possibile confermare che la regola Posta in arrivo è stata creata da un'app di terze parti OAuth con ambiti sospetti recapitati da un'origine sconosciuta, viene indicato un vero positivo.

  **Azione consigliata**: disabilitare e rimuovere l'app, reimpostare la password e rimuovere la regola Posta in arrivo.

  Seguire l'esercitazione su come reimpostare una password usando Azure Active Directory e l'esercitazione su come rimuovere la regola Posta in arrivo.

- **FP**: se è possibile confermare che l'app ha creato una regola di posta in arrivo per un account di posta elettronica esterno nuovo o personale per motivi legittimi.

  **Azione consigliata**: ignorare l'avviso.

#### <a name="understand-the-scope-of-the-breach"></a>Comprendere l'ambito della violazione

1. Esaminare tutte le attività eseguite dall'app.
1. Esaminare gli ambiti concessi dall'app.
1. Esaminare l'azione e la condizione della regola Posta in arrivo creata dall'app.

## <a name="collection-alerts"></a>Avvisi di raccolta

Questa sezione descrive gli avvisi che indicano che un antagonista potrebbe tentare di raccogliere dati di interesse dall'organizzazione per i propri obiettivi.

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>L'app ha effettuato chiamate anomale a Graph per leggere le e-mail.

**Gravità**: media

**ID MITRE**: T1114

Questo rilevamento identifica quando l'app OAuth Line of Business (LOB) accede a un volume insolito e elevato di cartelle ed e-mail dell'utente tramite l'API Graph, che può indicare un tentativo di violazione dell'organizzazione.

**TP o FP?**

- **TP**: se è possibile confermare che l'attività insolita del grafico è stata eseguita dall'app OAuth Line of Business (LOB), viene indicato un vero positivo.

  **Azioni consigliate**: disabilitare temporaneamente l'app, reimpostare la password e riabilitare l'app.

  Seguire l'esercitazione su come reimpostare una password usando Azure Active Directory.

- **FP**: se è possibile confermare che l'app ha lo scopo di eseguire un volume elevato di chiamate Graph.

  **Azione consigliata**: ignorare l'avviso.

#### <a name="understand-the-scope-of-the-breach"></a>Comprendere l'ambito della violazione

1. Esaminare il log attività per gli eventi eseguiti da questa app in modo comprendere meglio le altre attività di Graph per leggere le e-mail e tentare di raccogliere informazioni riservate sugli utenti.
1. Monitorare l'aggiunta di credenziali impreviste all'app.
