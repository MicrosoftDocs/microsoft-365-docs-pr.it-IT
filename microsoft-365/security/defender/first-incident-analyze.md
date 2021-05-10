---
title: Passaggio 1. Analizzare e analizzare il primo evento imprevisto
description: Come analizzare e iniziare l'analisi del primo incidente in Microsoft 365 Defender.
keywords: incidenti, avvisi, indagare, correlazione, attacco, computer, dispositivi, utenti, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta a eventi imprevisti, cyberattacco
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 83889123067897483478aec3d881a5a7b6ec14cc
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297225"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Passaggio 1. Analizzare e analizzare il primo evento imprevisto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Durante la definizione, l'implementazione e la gestione delle misure di sicurezza in base agli standard dell'organizzazione, è possibile configurare soluzioni di sicurezza che consentono di identificare rapidamente i rischi e le minacce per la sicurezza. Microsoft 365 Defender ti consente di rilevare, analizzare e analizzare gli eventi imprevisti tramite la sua esperienza con un singolo riquadro di vetro in cui puoi trovare le informazioni necessarie per prendere decisioni in tempo reale. 

Una volta rilevato un evento imprevisto di sicurezza, Microsoft 365 Defender presenta i dettagli necessari per definire la priorità di un incidente o di un evento imprevisto rispetto ad altri. Dopo aver determinato la definizione della priorità, gli analisti possono concentrare la propria energia sull'analisi dei casi loro assegnati.

## <a name="detection-by-microsoft-365-defender"></a>Rilevamento da parte di Microsoft 365 Defender

Microsoft 365 Defender riceve avvisi ed eventi da più piattaforme di sicurezza Microsoft come origini di rilevamento per creare un quadro olistico e un contesto di attività dannose. Queste sono le possibili origini di rilevamento:

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) è una soluzione di rilevamento e risposta degli endpoint (EDR) che usa l'antivirus di Microsoft Defender e una protezione avanzata dalle minacce abilitata per il cloud con Microsoft Security Graph. Defender for Endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. Protegge gli endpoint dalle minacce informatiche, rileva attacchi avanzati e violazioni dei dati, automatizza gli incidenti di sicurezza e migliora la sicurezza. 
- [Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) è una soluzione di sicurezza basata sul cloud che utilizza i segnali di Servizi di dominio Active Directory (AD DS) locali per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione. 
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) funge da gatekeeper per mediare l'accesso in tempo reale tra gli utenti aziendali e le risorse cloud che usano, ovunque gli utenti si trovino e indipendentemente dal dispositivo in uso. 
- [Microsoft Defender per Office 365](../office-365-security/overview.md) protegge l'organizzazione da minacce dannose nei messaggi di posta elettronica, nei collegamenti (URL) e negli strumenti di collaborazione. 
- [Il Centro](https://docs.microsoft.com/azure/security-center/security-center-introduction) sicurezza di Azure è un sistema di gestione della sicurezza dell'infrastruttura unificato che rafforza la sicurezza dei data center e fornisce una protezione avanzata dalle minacce nei carichi di lavoro ibridi nel cloud e in locale. 

In Microsoft 365 Defender, [gli eventi imprevisti](incidents-overview.md) vengono identificati correlando gli avvisi provenienti da queste diverse origini di rilevamento. Invece di spendere risorse per stringere o distinguere più avvisi nei rispettivi eventi imprevisti, puoi iniziare subito con la coda degli eventi imprevisti in Microsoft 365 Defender. In questo modo è possibile eseguire il triage degli incidenti in modo efficiente tra endpoint, identità, posta elettronica e applicazioni e ridurre i danni causati da un attacco.

## <a name="triage-your-incidents"></a>Triage your incidents

La risposta agli eventi imprevisti in Microsoft 365 Defender inizia dopo aver valutato l'elenco degli eventi imprevisti usando il metodo consigliato di definizione delle priorità dell'organizzazione. Per triage si intende assegnare un livello di importanza o di urgenza agli incidenti, che determina quindi l'ordine in cui verranno esaminati. 

Una guida di esempio utile per determinare quale evento imprevisto assegnare la priorità in Microsoft 365 Defender può essere riepilogato con la formula: *Gravità + Impatto = Priorità.* 

- **La gravità** è il livello designato da Microsoft 365 Defender e dai relativi componenti di sicurezza integrati. 
- **L'impatto** è determinato dall'organizzazione e in genere include, ma non solo, un numero di soglia di utenti, dispositivi, servizi interessati (o una combinazione di questi) e anche il tipo di avviso. 

Gli analisti avviano quindi indagini in base ai **criteri di** priorità impostati dall'organizzazione.

La priorità degli eventi imprevisti può variare a seconda dell'organizzazione. NIST consiglia anche di considerare l'impatto funzionale e informativo dell'incidente e la recuperabilità.  

Di seguito è riportato un solo approccio alla triage: 

1. Vai alla pagina [degli eventi](incidents-overview.md) imprevisti per avviare la triage. Qui è possibile visualizzare un elenco di eventi imprevisti che interessano l'organizzazione. Per impostazione predefinita, vengono disposti dall'evento imprevisto più recente a quello meno recente. Da qui, è anche possibile visualizzare colonne diverse per ogni evento imprevisto che mostrano la gravità, la categoria, il numero di avvisi attivi e le entità influenzate, tra gli altri. È possibile personalizzare il set di colonne e ordinare la coda degli eventi imprevisti in base ad alcune di queste colonne selezionando il nome della colonna. È inoltre possibile filtrare la coda degli eventi imprevisti in base alle proprie esigenze. Per un elenco completo dei filtri disponibili, vedere [Prioritize incidents.](incident-queue.md#available-filters)
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Esempio di coda degli eventi imprevisti"::: 

    Un esempio di come è possibile eseguire la triage per questo set di eventi imprevisti è quello di assegnare priorità agli eventi imprevisti che hanno interessato più utenti e dispositivi. In questo esempio, è possibile assegnare la priorità all'ID evento imprevisto 6769 perché ha interessato il maggior numero di entità: 7 dispositivi, 6 utenti e 2 cassette postali. Inoltre, l'evento imprevisto sembra contenere avvisi da Microsoft Defender per l'identità che indicano un avviso basato sull'identità e un possibile furto di credenziali.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Esempio di incidente ad alto impatto":::
 
2. Selezionare il cerchio accanto al nome dell'evento imprevisto per esaminare i dettagli. Sul lato destro verrà visualizzato un riquadro laterale che contiene informazioni aggiuntive che possono aiutare ulteriormente la tua ricerca. 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Esempio di riquadro laterale di un evento imprevisto"::: 

   Ad esempio, osservando le tattiche [miTRE ATT&CK](https://attack.mitre.org/) usate dall'utente malintenzionato in base alle categorie dell'incidente, è possibile definire la priorità di questo evento perché l'autore dell'attacco ha usato credenziali rubate, stabilito il comando e il controllo, eseguito il movimento laterale ed esfiltrato alcuni dati. Ciò suggerisce che l'autore dell'attacco sia già andato in profondità nella rete e che probabilmente abbia rubato informazioni riservate.

   Inoltre, se l'organizzazione ha implementato il framework Zero Trust, è consigliabile considerare l'accesso alle credenziali come una violazione di sicurezza importante che vale la pena assegnare priorità.
 
   Scorrendo verso il basso il riquadro laterale, verranno visualizzate le entità specifiche influenzate, ad esempio utenti, dispositivi e cassette postali. È possibile controllare il livello di esposizione di ogni dispositivo e i proprietari delle cassette postali interessate.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Esempio di dettagli del riquadro laterale di un evento imprevisto"::: 
 
3. Più in basso nel riquadro laterale, è possibile trovare gli avvisi associati. Microsoft 365 Defender ha già eseguito la correlazione di questi avvisi in un singolo evento imprevisto, risparmiando tempo e risorse più utili per correggere l'attacco. Gli avvisi sono eventi di sistema sospetti e quindi potenzialmente dannosi che indicano la presenza di un utente malintenzionato in una rete. 

   In questo esempio, 87 singoli avvisi sono stati determinati come parte di un evento imprevisto di sicurezza. È possibile visualizzare tutti gli avvisi per ottenere una rapida visualizzazione della modalità di attacco.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Esempio di avvisi in un riquadro laterale degli eventi imprevisti"::: 
 
## <a name="analyze-your-first-incident"></a>Analizzare il primo evento imprevisto

La comprensione del contesto che circonda gli avvisi è altrettanto importante. Spesso un avviso non è un singolo evento indipendente. Esiste una catena di processi creati, comandi e azioni che potrebbero non essere stati evasi contemporaneamente. Pertanto, un analista deve cercare la prima e l'ultima attività dell'entità sospetta nelle sequenze temporali del dispositivo per comprendere il contesto degli avvisi.

Esistono diversi modi per leggere e analizzare i dati con Microsoft 365 Defender, ma l'obiettivo finale per gli analisti è quello di rispondere agli incidenti il più rapidamente possibile. Sebbene Microsoft 365 Defender possa ridurre in modo significativo il tempo medio per la [](m365d-autoir.md) correzione [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) tramite la funzionalità di analisi e risposta automatizzata leader del settore, esistono sempre casi che richiedono un'analisi manuale. 

Ecco un esempio:

1. Dopo aver determinato la priorità di analisi, un analista inizia un'analisi approfondita selezionando il nome dell'evento imprevisto. In questa pagina viene visualizzato il **riepilogo degli** eventi imprevisti in cui i dati vengono visualizzati nelle schede per facilitare l'analisi. Nella scheda **Avvisi** viene visualizzato il tipo di avvisi. Gli analisti possono fare clic su ogni avviso per eseguire il drill-down nella rispettiva origine di rilevamento. 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Esempio della scheda Riepilogo di un evento imprevisto"::: 
 
    Per una guida rapida sul dominio illustrato da ogni origine di rilevamento, vedere la [sezione Rilevare](#detection-by-microsoft-365-defender) di questo articolo.

2.  Dalla scheda **Avvisi,** un analista può eseguire il pivot nell'origine di rilevamento per eseguire un'analisi e un'analisi più approfondite. Ad esempio, selezionando Rilevamento malware con Microsoft Cloud App Security come origine di rilevamento, l'analista viene visualizzato nella pagina di avviso corrispondente.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Esempio di selezione di un avviso di un evento imprevisto"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Esempio di pagina corrispondente in Microsoft Cloud App Security"::: 
  
3.  Per analizzare ulteriormente l'esempio, scorrere fino alla parte inferiore della pagina per visualizzare **gli utenti interessati.** Per visualizzare l'attività e il contesto che circondano il rilevamento di malware, selezionare Pagina utente di Annette Hill. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Esempio di pagina utente":::
  
4.  Nella pagina dell'utente è riportato un elenco cronologico degli eventi che iniziano con un accesso rischioso da un avviso indirizzo IP di rete *TOR.* Anche se la sospettosità di un'attività dipende dalla natura del modo in cui un'organizzazione svolge la propria attività, nella maggior parte dei casi l'uso di The Onion Router (TOR), una rete che consente agli utenti di esplorare il Web in modo anonimo, in un ambiente aziendale potrebbe essere considerato altamente improbabile e superfluo per le normali operazioni online.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Esempio di elenco cronologico di eventi per un utente":::
  
5.  Ogni avviso può essere selezionato per ottenere ulteriori informazioni sull'attività. Ad esempio, se si **seleziona Attività da un avviso indirizzo IP Tor,** si apre la pagina dell'avviso. Annette è un amministratore di Office 365, il che significa che ha privilegi elevati e che l'evento imprevisto di origine potrebbe aver causato l'accesso a informazioni riservate. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Esempio di dettagli degli avvisi per Microsoft Cloud App Security"::: 
 
6.  Selezionando altri avvisi, un analista può ottenere un quadro completo dell'attacco.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 2: informazioni su come correggere gli eventi imprevisti](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Informazioni su [come correggere gli eventi imprevisti.](first-incident-remediate.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
