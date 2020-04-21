---
title: Microsoft Secure Score
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, in che modo vengono calcolati i dettagli e quali amministratori della sicurezza possono aspettarsi.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e7274ff196d5b822d146378752d66c9707fc9f19
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583382"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Dopo i consigli sui punteggi di sicurezza è possibile proteggere l'organizzazione dalle minacce. Da un Dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, dei dati, delle app, degli strumenti e dell'infrastruttura di Microsoft 365.

Secure Score aiuta le organizzazioni:

* Segnalare lo stato corrente della posizione di sicurezza dell'organizzazione.
* Migliorare la propria posizione di sicurezza fornendo individuabilità, visibilità, orientamento e controllo.  
* Confronta con benchmark e stabilisci indicatori di prestazioni chiave (KPI).

Le organizzazioni accedono alla visualizzazione robusta delle metriche e delle tendenze, all'integrazione con altri prodotti Microsoft, al confronto tra organizzazioni simili e molto altro ancora. Il Punteggio può anche riflettere quando le soluzioni di terze parti sono state indirizzate alle azioni consigliate.

Inoltre, è possibile accedere ai consigli e al Punteggio tramite l' [API di Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Informazioni sul [tipo di risorsa Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funzionamento

Si ricevono punti per la configurazione delle funzionalità di sicurezza consigliate, per l'esecuzione di attività relative alla sicurezza (come la visualizzazione di report) o per l'azione di miglioramento con un'applicazione o un software di terze parti. Alcune azioni di miglioramento offrono solo punti quando sono state completate e alcune forniscono punti parziali se sono state completate per alcuni dispositivi o utenti.

Viene mostrato il set completo di possibili miglioramenti, indipendentemente dalla licenza, in modo da poter comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La posizione di sicurezza assoluta è rappresentata da un punteggio sicuro, che rimane invariato indipendentemente dalle licenze di prodotto possedute dall'organizzazione. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente in uso.

Il Punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine di azione per la visualizzazione e il miglioramento. Secure Score sincronizza anche tutti i giorni per ricevere i dati di sistema relativi ai punti ottenuti per ogni azione.

### <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

La maggior parte sono segnati in modo binario, se si implementa l'azione di miglioramento, come creare un nuovo criterio o attivare un'impostazione specifica, si ottiene il 100% dei punti. Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale. Ad esempio, se gli Stati di azione di miglioramento si ottengono 30 punti proteggendo tutti gli utenti con autenticazione a più fattori e si dispone solo di 5 di 100 utenti totali protetti, si riceverebbe un punteggio parziale di circa 2 punti (5 protected/100 Total * 30 max pts = 2 PTS partial score).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi nel punteggio sicuro

Sono attualmente disponibili suggerimenti per Office 365 (tra cui SharePoint Online, Exchange Online, OneDrive for business, Microsoft Information Protection e altro ancora), Azure AD e cloud app Security. Sono disponibili suggerimenti per gli altri prodotti di sicurezza, come Azure ATP e Microsoft Defender ATP. Gli elementi consigliati non riguardano tutte le superfici di attacco associate a ciascun prodotto, ma sono una buona linea di base. È inoltre possibile contrassegnare le azioni di miglioramento riportate in base a una terza parte.

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

* SecurityEvents. Read. All (per il ruolo di sola lettura)
* SecurityEvents. ReadWrite. All (per il ruolo di lettura e scrittura)

## <a name="gain-visibility-into-your-security-posture"></a>Ottenere visibilità nella posizione di sicurezza

Per facilitare le informazioni necessarie più rapidamente, le azioni di miglioramento di Microsoft sono organizzate in gruppi:

* Identity (account di Azure AD & ruoli)
* Data (protezione delle informazioni di Microsoft)
* Dispositivo (nessuna azione di miglioramento per il momento)
* App (applicazioni di posta elettronica e cloud, tra cui Office 365 e Microsoft cloud app Security)
* Infrastructure (nessuna azione di miglioramento per il momento)

Nella pagina Panoramica di Microsoft Secure score, è possibile vedere come vengono divisi i punti tra questi gruppi e quali sono i punti disponibili. La pagina di panoramica è anche il luogo in cui ottenere una visualizzazione completa del punteggio totale, l'andamento storico del Punteggio sicuro con i confronti di benchmark e le azioni di miglioramento prioritarie che possono essere intraprese per migliorare il punteggio.

![Pagina iniziale](../../media/secure-score/homepage-original.png)
di Secure Score*Figura 1: pagina Panoramica del Punteggio di Microsoft Secure*

## <a name="take-action-to-improve-your-score"></a>Eseguire un'azione per migliorare il Punteggio

Nella scheda azioni di miglioramento sono elencati i suggerimenti per la sicurezza che consentono di risolvere possibili superfici di attacco, insieme al relativo stato (completato, non completato, risolto tramite terze parti e ignorati). È possibile eseguire la ricerca, il filtro e il raggruppamento di tutte le azioni di miglioramento.

### <a name="ranking"></a>Classificazione

La classificazione si basa sul numero di punti rimanenti rimasti per raggiungere, sulla difficoltà di implementazione, sull'impatto dell'utente e sulla complessità. Le azioni di miglioramento più elevate hanno un numero elevato di punti rimanenti con difficoltà bassa, impatto dell'utente e complessità.

### <a name="actions"></a>Azioni

Le azioni contrassegnate come [non segnate] non vengono registrate da Microsoft Secure score. È comunque possibile eseguire un'azione, ma il loro completamento non influirà sul punteggio. Se un'azione viene registrata in futuro da Microsoft Secure score ed è già stata completata, il Punteggio sicuro rispecchierà automaticamente la modifica.

Quando si seleziona un'azione di miglioramento specifica, viene visualizzato un volo. Per completare l'azione, sono disponibili alcune opzioni:

1. Selezionare **Visualizza impostazioni** per passare alla schermata di configurazione e apportare le modifiche. È quindi possibile ottenere i punti che l'azione vale, visibili nella parte superiore del volo. I punti possono richiedere fino a 24 ore per l'aggiornamento.

2. Selezionare **Risolvi tramite terze parti** perché l'azione di miglioramento è già stata indirizzata da un'applicazione di terze parti o da un software. Si ottengono i punti che il valore dell'azione vale, in modo che il Punteggio sicuro rispecchi meglio la posizione di sicurezza complessiva. Se una terza parte non è più in grado di coprire il controllo, è possibile contrassegnare l'azione di miglioramento come non completata. Tenere presente che Microsoft non ha alcuna visibilità se i requisiti del punteggio sono stati soddisfatti se l'azione di miglioramento è stata contrassegnata come risolta tramite terze parti.

3. Selezionare **Ignora** perché si è deciso di accettare il rischio e non di applicare l'azione di miglioramento. Una volta ignorata un'azione di miglioramento, il numero totale di punti di Punteggio sicuro che è possibile ottenere è ridotto. È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.

4. Selezionare **Verifica** perché l'azione di miglioramento richiede la revisione periodica di una parte dell'ambiente per ottenere e mantenere i punti. Ad esempio, le regole di inoltro delle cassette postali devono essere riviste settimanalmente per assicurarsi che i dati non vengano exfiltrated dalla rete. Non è necessario apportare alcuna modifica, ma sarà necessario eseguire un'azione. Se si esaminano regolarmente le regole, verranno ricevuti i punti. In caso contrario, il punteggio viene ridotto.

![Esempio di azione di miglioramento sicuro del Punteggio](../../media/secure-score/secure-score1x450.png) ![Esempio di azione di miglioramento Secure Score Review](../../media/secure-score/secure-score2x450.png)

*Figure 2 & 3: azione di miglioramento comparsa*

## <a name="monitor-improvements-over-time"></a>Monitorare i miglioramenti nel tempo

È possibile visualizzare un grafico del punteggio dell'organizzazione nel tempo nella scheda **cronologia** . al di sotto del grafico è riportato un elenco di tutte le azioni eseguite nell'intervallo di tempo selezionato e i relativi attributi, ad esempio i punti e la categoria risultanti. È possibile personalizzare un intervallo di date e filtrare in base alla categoria.

## <a name="risk-awareness"></a>Sensibilizzazione ai rischi

Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza. non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati. Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft, che possono contribuire a compensare il rischio di essere violati. Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.

## <a name="whats-new"></a>Novità

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

### <a name="january---march-2020"></a>Gennaio-marzo 2020

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Supporto delle impostazioni predefinite per la sicurezza per le azioni di miglioramento di Azure AD

Microsoft Secure Score aggiornerà le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza di Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.

Influenzerà le operazioni di miglioramento seguenti:

- Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro
- Richiedere l'AMF per i ruoli amministrativi
- Abilitazione del criterio per bloccare l'autenticazione legacy

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Azioni di miglioramento rimosse che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza

Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.

- Archiviare i documenti degli utenti in OneDrive for business
- Impostare i criteri degli allegati sicuri di Office 365 ATP
- Configurare i collegamenti sicuri di Office 365 per verificare gli URL
- Non consentire la delega delle cassette postali
- Consenti collegamenti di condivisione guest anonimi per siti e documenti
- Abilitare la console di protezione delle app Cloud
- Configurare la data di scadenza per i collegamenti di condivisione esterna
- Abilitare la registrazione dei dati di controllo
- Individuare le applicazioni IT Shadow a rischio e non conformi
- Esaminare le autorizzazioni & bloccare le applicazioni OAuth rischiose connesse all'ambiente
- Configurare il controllo delle versioni nelle raccolte documenti di SharePoint Online
- Eliminare/bloccare gli account non utilizzati negli ultimi 30 giorni
- Designare meno di 5 amministratori globali

#### <a name="removed-not-scored-improvement-actions"></a>Azioni di miglioramento "non segnate" rimosse

Uno dei principi del Punteggio sicuro è che il punteggio dovrebbe essere standardizzato e facilmente correlabile. L'utilizzo di azioni di miglioramento non misurabili o utilizzabili ha provocato confusione. Microsoft Secure Score ha senso solo quando ogni suggerimento può avere un effetto chiaro sulla partitura. Le azioni di miglioramento non segnate non sono misurabili.  

Per questi motivi, tutte le azioni di miglioramento non segnate sono state rimosse. Non è necessaria alcuna azione da parte vostra.

#### <a name="removed-device-improvement-actions"></a>Azioni di miglioramento del dispositivo rimosse

Dopo aver valutato la categoria del dispositivo Microsoft Secure score per le azioni di miglioramento, è stato stabilito che tali azioni valutano attualmente lo stato del criterio e non lo stato di configurazione dei dispositivi. Poiché la configurazione è direttamente legata alla postura di sicurezza, le azioni del dispositivo esistenti sono state determinate per non rappresentare completamente la postura organizzativa.  Verranno eliminate le azioni correnti nella categoria dispositivo durante la lavorazione per fornire una serie di raccomandazioni che utilizzano direttamente i dati di diagnostica per rappresentare in modo più completo la posizione di sicurezza dei dispositivi.

Sono state rimosse le operazioni di miglioramento seguenti:

- Abilitare la gestione dei dispositivi mobili di Microsoft Intune
- Creare un criterio di conformità di Microsoft Intune per Android
- Creare un criterio di conformità di Microsoft Intune per Android per il lavoro
- Creare un criterio di protezione delle app di Microsoft Intune per Android
- Creare un criterio di protezione delle app di Microsoft Intune per iOS
- Contrassegnare i dispositivi senza criteri di conformità di Microsoft Intune assegnati come non conformi
- Creare un criterio di conformità di Microsoft Intune per iOS
- Creare un criterio di conformità di Microsoft Intune per macOS
- Creare un criterio di conformità di Microsoft Intune per Windows
- Creare un profilo di configurazione di Microsoft Intune per Android
- Creare un profilo di configurazione di Microsoft Intune per Android per il lavoro
- Creare un profilo di configurazione di Microsoft Intune per macOS
- Creare un profilo di configurazione di Microsoft Intune per iOS
- Creare un profilo di configurazione di Microsoft Intune per Windows
- Abilitare il rilevamento migliorato del jailbreak in Microsoft Intune
- Richiedere la correzione di tutti i dispositivi, disporre di antivirus e firewall abilitati
- Abilitare l'integrazione di Windows Defender ATP in Microsoft Intune
- Creare un criterio di protezione delle informazioni di Windows per Microsoft Intune
- Richiedere che tutti i dispositivi dispongano di configurazioni di sicurezza avanzate
- Rivedere i dispositivi bloccati segnala settimanalmente

#### <a name="mfa-improvement-action-updates"></a>Aggiornamenti dell'azione per il miglioramento dell'AMF

Per riflettere la necessità per le aziende di garantire la massima sicurezza durante l'applicazione di criteri che funzionano con le loro attività, Microsoft Secure Score ha rimosso tre azioni di miglioramento incentrate sull'autenticazione a più fattori e ha aggiunto due.

Azioni di miglioramento rimosse:

- Registrare tutti gli utenti per l'autenticazione a più fattori
- Richiedi l'AMF per tutti gli utenti
- Richiedere l'autenticazione master per i ruoli con privilegi di Azure AD

Operazioni di miglioramento aggiunte:

- Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro
- Richiedere l'AMF per i ruoli amministrativi

 Queste nuove azioni di miglioramento richiedono la registrazione di utenti o amministratori per l'autenticazione a più fattori (AMF) all'interno della directory e la definizione del set di criteri appropriato che soddisfano le esigenze dell'organizzazione. L'obiettivo principale è la flessibilità garantendo che tutti gli utenti e gli amministratori siano in grado di eseguire l'autenticazione con più fattori o richieste di verifica dell'identità basata sui rischi. Che può assumere la forma di avere più criteri che applicano decisioni con ambito o impostazione dei valori predefiniti per la sicurezza (a partire dal 16 marzo) che consentono a Microsoft di decidere quando sfidare gli utenti per l'AMF.

#### <a name="removed-review-improvement-actions"></a>Azioni di miglioramento "revisione" rimosse

Uno dei principi del Punteggio sicuro è che il punteggio dovrebbe essere standardizzato e facilmente correlabile. L'utilizzo di azioni di miglioramento non misurabili o utilizzabili ha provocato confusione. Un punteggio sicuro di Microsoft ha senso solo quando ogni suggerimento può avere un effetto chiaro sulla partitura. Esaminare le azioni di miglioramento non vengono misurate allo stesso livello di altre azioni di miglioramento.  

Per questi motivi, tutte le azioni di miglioramento che richiedono una cadenza di revisione sono state temporaneamente rimosse. Non è necessaria alcuna azione da parte vostra.

### <a name="preview-features"></a>Funzionalità di anteprima

Nella [versione di anteprima](microsoft-secure-score-preview.md)verranno incluse le funzionalità seguenti:

* Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level
* Nuove modalità di monitoraggio e benchmark del Punteggio
* Migliorare la tracciabilità e il monitoraggio delle regressioni dei punteggi
* Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate
* Semplificazione del sistema di punti
* E altro ancora!

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

In caso di problemi, fatecelo sapere inviando la [sicurezza, la Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Si sta monitorando la community e viene fornita assistenza.
