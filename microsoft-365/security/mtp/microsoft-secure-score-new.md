---
title: Nuovo punteggio di Microsoft Secure
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, la modalità di calcolo dei dettagli e gli amministratori della sicurezza che possono aspettarsi di usarli.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbc8d1e8dae1845412b1fb3ad86b831b08a4a518
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327145"
---
# <a name="microsoft-secure-score-new"></a>Microsoft Secure Score (nuovo)

>[!IMPORTANT]
>Questa nuova iterazione del Punteggio di Microsoft Secure sta sostituendo l'iterazione precedente con nuovi elementi di progettazione e caratteristiche nei prossimi mesi
>
>Se non si vede una scheda **metriche & Trends** accanto alla cronologia, si è nell'iterazione precedente. [Passare a Microsoft Secure Score (iterazione precedente)](microsoft-secure-score.md)

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).

Dopo i consigli sui punteggi di sicurezza è possibile proteggere l'organizzazione dalle minacce. Da un Dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, dei dati, delle app, degli strumenti e dell'infrastruttura di Microsoft 365.

Secure Score aiuta le organizzazioni:  

* Segnalare lo stato corrente della posizione di sicurezza dell'organizzazione.
* Migliorare la propria posizione di sicurezza fornendo individuabilità, visibilità, orientamento e controllo.  
* Confronta con benchmark e stabilisci indicatori di prestazioni chiave (KPI).

Le organizzazioni accedono alla visualizzazione robusta delle metriche e delle tendenze, all'integrazione con altri prodotti Microsoft, al confronto tra organizzazioni simili e molto altro ancora. Il Punteggio può anche riflettere quando le soluzioni di terze parti sono state indirizzate alle azioni consigliate.

Inoltre, è possibile accedere ai consigli e al Punteggio tramite l' [API di Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Informazioni sul [tipo di risorsa Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funzionamento

Si ricevono punti per la configurazione delle funzionalità di sicurezza consigliate, per l'esecuzione di attività relative alla sicurezza o per l'azione di miglioramento con un'applicazione o un software di terze parti o con una attenuazione alternativa. Alcune azioni di miglioramento offrono solo punti quando sono state completate e alcune forniscono punti parziali se sono state completate per alcuni dispositivi o utenti. Se non è possibile o non si desidera applicare una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.

Viene mostrato il set completo di possibili miglioramenti, indipendentemente dalla licenza, in modo da poter comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La posizione di sicurezza assoluta è rappresentata da un punteggio sicuro, che rimane invariato indipendentemente dalle licenze di prodotto possedute dall'organizzazione. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente in uso.

Il Punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine di azione per la visualizzazione e il miglioramento. Secure Score sincronizza anche tutti i giorni per ricevere i dati di sistema relativi ai punti ottenuti per ogni azione.

### <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

Ogni azione di miglioramento vale 10 punti o meno. La maggior parte sono segnati in modo binario, se si implementa l'azione di miglioramento, come creare un nuovo criterio o attivare un'impostazione specifica, si ottiene il 100% dei punti. Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale. Ad esempio, se gli Stati di azione di miglioramento si ottengono 30 punti proteggendo tutti gli utenti con autenticazione a più fattori e si dispone solo di 5 di 100 utenti totali protetti, si riceverebbe un punteggio parziale di circa 2 punti (5 protected/100 Total * 30 max pts = 2 PTS partial score).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi nel punteggio sicuro

Sono attualmente disponibili suggerimenti per Microsoft 365 (incluso Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP e cloud app Security. Sono disponibili suggerimenti per gli altri prodotti di sicurezza. Gli elementi consigliati non riguardano tutte le superfici di attacco associate a ciascun prodotto, ma sono una buona linea di base. È inoltre possibile contrassegnare le azioni di miglioramento riportate da terze parti o da una attenuazione alternativa.

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per avere l'autorizzazione per accedere a Microsoft Secure score, è necessario essere assegnati a uno dei ruoli seguenti in Azure Active Directory.

### <a name="read-and-write-roles"></a>Ruoli di lettura e scrittura

Con l'accesso in lettura e in scrittura, è possibile apportare modifiche e interagire direttamente con il Punteggio sicuro. È inoltre possibile assegnare l'accesso in sola lettura ad altri utenti.

* Amministratore globale
* Amministratore della sicurezza
* Amministratore di Exchange
* Amministratore di SharePoint
* Amministratore account

### <a name="read-only-roles"></a>Ruoli di sola lettura

Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare le aree dei punteggi o modificare i confronti personalizzati.

* Amministratore del supporto tecnico
* Amministratore utenti
* Amministratore del servizio
* Ruolo con autorizzazioni di lettura per la sicurezza
* Operatore della sicurezza
* Ruolo con autorizzazioni di lettura globali

### <a name="graph-api"></a>API del grafico

Per accedere all'API del grafico, è necessario disporre di uno degli ambiti seguenti oltre a un ruolo:

* SecurityEvents. Read. All (per i ruoli di sola lettura)
* SecurityEvents. ReadWrite. All (per i ruoli di lettura e scrittura)

## <a name="gain-visibility-into-your-security-posture"></a>Ottenere visibilità nella posizione di sicurezza

Per facilitare le informazioni necessarie più rapidamente, le azioni di miglioramento di Microsoft sono organizzate in gruppi:

* Identity (account di Azure AD & ruoli)
* Data (protezione delle informazioni di Microsoft)
* Dispositivo (Microsoft Defender ATP)
* App (applicazioni di posta elettronica e cloud, tra cui Office 365 e Microsoft cloud app Security)
* Infrastructure (nessuna azione di miglioramento per il momento)

>[!NOTE]
>Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato che rendeva Microsoft Secure Score incompatibile temporaneamente con identità Secure score e l'API del grafico. [Visualizza dettagli](microsoft-secure-score-new.md#incompatibility-with-identity-secure-score-and-graph-api)

Nella pagina Panoramica di Microsoft Secure score, è possibile vedere come vengono divisi i punti tra questi gruppi e quali sono i punti disponibili. La pagina di panoramica è anche il luogo in cui ottenere una visualizzazione completa del punteggio totale, l'andamento storico del Punteggio sicuro con i confronti di benchmark e le azioni di miglioramento prioritarie che possono essere intraprese per migliorare il punteggio.

![Homepage del Punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)


## <a name="take-action-to-improve-your-score"></a>Eseguire un'azione per migliorare il Punteggio

Nella scheda **azioni di miglioramento** sono elencati i suggerimenti per la sicurezza che consentono di risolvere eventuali superfici di attacco, insieme al relativo stato (per indirizzare, pianificare, rischi accettati, risolti tramite terze parti, risolti tramite attenuazione alternativa e completati). È possibile eseguire la ricerca, il filtro e il raggruppamento di tutte le azioni di miglioramento.  

### <a name="ranking"></a>Classificazione

La classificazione si basa sul numero di punti rimanenti rimasti per raggiungere, sulla difficoltà di implementazione, sull'impatto dell'utente e sulla complessità. Le azioni di miglioramento più elevate hanno un numero elevato di punti rimanenti con difficoltà bassa, impatto dell'utente e complessità.

### <a name="view-improvement-action-details"></a>Visualizzare i dettagli dell'azione di miglioramento

Quando si seleziona un'azione di miglioramento specifica, viene visualizzato un riquadro a comparsa a pagina intera.  

![Esempio di riquadro a comparsa Azione miglioramento ](../../media/secure-score/secure-score-improvement-action-details.png)
 *Figura 2: esempio del riquadro a comparsa Azione miglioramento*

Per completare l'azione, sono disponibili alcune opzioni:

* Selezionare **Gestisci** per passare alla schermata di configurazione e apportare le modifiche. Si otterrà quindi i punti che il valore dell'azione vale, visibili nel volo. I punti generalmente richiedono circa 24 ore per l'aggiornamento.

* Selezionare **Condividi** per copiare il collegamento diretto all'azione di miglioramento oppure scegliere la piattaforma per la condivisione del collegamento, ad esempio posta elettronica, Microsoft teams, Microsoft Planner o ServiceNow. La selezione di ServiceNow consente di creare un ticket di modifica che sarà visibile in ServiceNow e nella Home page del Centro sicurezza Microsoft 365. Per ulteriori informazioni, vedere [Microsoft 365 Security Center e ServiceNow Integration](tickets.md).

### <a name="choose-an-improvement-action-status"></a>Scegliere uno stato di azione di miglioramento

Scegliere eventuali stati e note di record specifiche per l'azione di miglioramento. Le statue che è possibile selezionare sono le seguenti:

* **To address** : si riconosce che l'azione di miglioramento è necessaria e si prevede di affrontarla a un certo punto in futuro. Questo stato si applica anche alle azioni che vengono rilevate come parziali, ma non completamente completate.
* **Pianificato** : sono disponibili piani concreti per completare l'azione di miglioramento.
* **Rischi accettati** : la sicurezza deve essere sempre bilanciata con l'usabilità e non ogni raccomandazione funzionerà per l'ambiente in uso. In questo caso, è possibile scegliere di accettare il rischio o il rischio restante e non applicare l'azione di miglioramento. Non verranno assegnati punti, ma l'azione non sarà più visibile nell'elenco delle azioni di miglioramento. È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.
* **Risolti tramite terze parti** e **risolti tramite attenuazione alternativa** , l'azione di miglioramento è già stata indirizzata da un'applicazione o un software di terze parti o da uno strumento interno. Si ottengono i punti che l'azione vale, in modo che il Punteggio rispecchi meglio la posizione di sicurezza generale. Se uno strumento di terze parti o interno non è più in grado di coprire il controllo, è possibile scegliere un altro stato. Tenere presente che Microsoft non avrà visibilità sulla completezza dell'implementazione se l'azione di miglioramento è contrassegnata come uno di questi Stati.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Azioni di miglioramento della gestione della vulnerabilità & di minacce

Per le azioni di miglioramento nella categoria "dispositivo", non sarà possibile scegliere status. Al contrario, si verrà indirizzati all'indicazione di sicurezza per la [gestione della vulnerabilità del & di protezione (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) associata in [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) per eseguire l'azione. L'eccezione scelta e la giustificazione scritta saranno specifiche di quel portale e non saranno presenti nel portale Microsoft Secure score.

#### <a name="completed-improvement-actions"></a>Azioni di miglioramento completate

Le azioni di miglioramento hanno uno stato "completato" una volta che sono stati raggiunti tutti i punti possibili per l'azione di miglioramento. Le azioni di miglioramento completate sono state confermate se i dati di Microsoft e non saranno in grado di modificare lo stato.

### <a name="assess-information-and-review-user-impact"></a>Valutare le informazioni e esaminare l'impatto dell'utente

La sezione **a colpo d'occhio** vi dirà la categoria, gli attacchi che può proteggere e il prodotto.

L' **impatto dell'utente** indica ciò che gli utenti sperimenteranno se l'azione di miglioramento è stata emanata e **gli utenti interessati** visualizzano chi lo sperimenteranno.

### <a name="implement-the-improvement-action"></a>Implementazione dell'azione di miglioramento

La sezione **implementazione** Visualizza eventuali prerequisiti, passaggi successivi per completare l'azione di miglioramento, lo stato di implementazione corrente dell'azione di miglioramento e qualsiasi altro collegamento per ulteriori informazioni.

I prerequisiti saranno tutte le licenze che devono essere ottenute o le azioni che devono essere completate prima che venga affrontata l'azione di miglioramento. Assicurarsi di disporre di un numero sufficiente di posti nella licenza per completare l'azione di miglioramento e che tali licenze vengano applicate agli utenti necessari.  

## <a name="track-your-score-history-and-meet-goals"></a>Monitorare la cronologia dei punteggi e raggiungere gli obiettivi

È possibile visualizzare un grafico del punteggio dell'organizzazione nel tempo nella scheda **cronologia** . al di sotto del grafico è riportato un elenco di tutte le azioni eseguite nell'intervallo di tempo selezionato e i relativi attributi, ad esempio i punti e la categoria risultanti. È possibile personalizzare un intervallo di date e filtrare in base alla categoria.

Nella scheda **tendenze & metriche** sono disponibili diversi grafici e grafici che consentono di ottenere maggiori visibilità nelle tendenze e impostare gli obiettivi. È possibile impostare l'intervallo di date per l'intera pagina di visualizzazioni. Le visualizzazioni includono:

* **Area di valutazione sicura** , personalizzata in base agli obiettivi dell'organizzazione e alle definizioni di intervalli di risultati buoni, OK e non validi.
* **Tendenza di regressione** : una sequenza temporale di punti che sono stati regressione a causa di modifiche apportate alla configurazione, all'utente o al dispositivo.  
* **Trend di confronto** : la modalità di confronto tra il Punteggio sicuro dell'organizzazione e gli altri nel corso del tempo. Questa visualizzazione può includere linee che rappresentano la media del Punteggio di organizzazioni con conteggio dei sedili analogo e una visualizzazione di confronto personalizzata che è possibile impostare.
* **Tendenza all'accettazione del rischio** : cronologia delle azioni di miglioramento contrassegnate come "rischi accettati".
* **Modifiche al Punteggio** : il numero di punti ottenuti, i punti di regressione, insieme alla variazione del punteggio successivo, nell'intervallo di date specificato.

## <a name="risk-awareness"></a>Sensibilizzazione ai rischi

Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza. non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati. Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft, che possono contribuire a compensare il rischio di essere violati. Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.

## <a name="whats-new"></a>Novità 

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilità con il Punteggio identità sicuro e l'API del grafico

Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato. Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza. Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.

Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio. Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico. Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

### <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Aggiunta delle azioni di miglioramento di Azure Active Directory
- Aggiunta delle azioni di miglioramento di Azure Advanced Threat Protection
- Supporto per le indicazioni sulla sicurezza del trifosfato di adenosina di Microsoft Defender [& vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Tutti i consigli di sicurezza rilasciati forniti da TVM sono ora disponibili

### <a name="updated-interface-and-functionality"></a>Interfaccia e funzionalità aggiornate

* Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level
* Nuove modalità di monitoraggio e benchmark del Punteggio
* Migliorare il monitoraggio e la comprensione delle regressioni dei punteggi
* Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate
* E altro ancora!

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

In caso di problemi, fatecelo sapere inviando la [sicurezza, la Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Si sta monitorando la community e viene fornita assistenza.
