---
title: Valutazione della rete Microsoft 365 (Preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Valutazione della rete Microsoft 365 (Preview)
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696104"
---
# <a name="microsoft-365-network-assessment-preview"></a>Valutazione della rete Microsoft 365 (Preview)

Nella pagina connettività di Microsoft 365 Admin Center to Microsoft 365, le **valutazioni di rete** distillano un'aggregazione di molte metriche delle prestazioni di rete in un'istantanea dell'integrità della rete aziendale, rappresentata da un valore punti da 1-100. Le valutazioni di rete sono limitate all'intero tenant e per ogni posizione geografica da cui gli utenti si connettono al tenant, fornendo agli amministratori di Microsoft 365 un modo semplice per afferrare istantaneamente una Gestalt dell'integrità della rete dell'organizzazione e analizzarla rapidamente in una relazione dettagliata per qualsiasi posizione globale dell'ufficio.

Il valore dei punti di valutazione della rete è una media misura della latenza, della larghezza di banda, della velocità di download e delle metriche di qualità di connessione compilate dal vivo al momento della visualizzazione. Le metriche delle prestazioni per le reti di proprietà di Microsoft sono escluse da queste misure per garantire che i risultati della valutazione siano inequivocabili e specifici per la rete aziendale.

![Valore di valutazione della rete](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valore di valutazione della rete molto basso suggerisce che i client Microsoft 365 avranno problemi significativi per la connessione al tenant o per il mantenimento di un'esperienza utente reattiva, mentre un valore elevato indica una rete adeguatamente configurata con alcuni problemi di prestazioni in esecuzione. Un valore pari a 80% rappresenta una linea di base sana in cui non si dovrebbe pretendere di ricevere reclami da un utente regolare sulla connettività di Microsoft 365 o la risposta a causa delle prestazioni di rete. Quando vengono apportati miglioramenti della connettività di rete iterativa, questo valore aumenterà insieme all'esperienza utente.

>[!IMPORTANT]
>Insights di rete, raccomandazioni sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="network-assessment-panel"></a>Pannello di valutazione della rete

Ogni valutazione di rete, se ambito del tenant o di una specifica posizione di Office, Visualizza un riquadro con i dettagli relativi alla valutazione. In questo riquadro viene visualizzato un grafico a barre della valutazione, sia in percentuale che come punti totali per ogni carico di lavoro del componente, compresi solo i carichi di lavoro in cui sono stati ricevuti i dati di misurazione. Per una valutazione della rete delle posizioni di Office, viene mostrato anche un benchmark che è la mediana di tutti i client Microsoft 365 che hanno segnalato dati nella stessa città del percorso dell'ufficio.

![Valore di valutazione della rete di esempio](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

La **ripartizione di valutazione** nel pannello Visualizza la valutazione per ognuno dei carichi di lavoro del componente.

La **cronologia di valutazione** indica gli ultimi 30 giorni della valutazione e del benchmark.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Valutazioni della rete tenant e valutazioni della rete delle posizioni di Office

Una valutazione della rete misura la progettazione del perimetro di rete di una posizione di Office alla rete di Microsoft. I miglioramenti apportati al perimetro della rete sono migliori in ogni posizione di Office o in cui è possibile aggregare la connettività di rete possono essere presenti miglioramenti che influiscono su più percorsi.

Viene mostrato un valore di valutazione della rete per l'intero tenant Microsoft 365 nella pagina Panoramica delle prestazioni di rete e un valore specifico per ogni posizione di Office rilevata nella pagina di riepilogo di tale percorso.

## <a name="exchange-online"></a>Exchange Online

Per Exchange Online, viene misurata la latenza TCP dal computer client al front end server di Exchange. Questo può influire sulla distanza che la rete percorre nei clienti LAN e WAN. Può anche essere influenzato da dispositivi o servizi di intermediazione di rete che ritardano la connettività o causano il rimandato dei pacchetti.

## <a name="sharepoint-online"></a>SharePoint Online

Per SharePoint Online, la velocità di download disponibile per un utente per l'accesso a un documento viene misurata. Questo può essere influenzato dalla larghezza di banda disponibile nei circuiti di rete tra il computer client e la rete di Microsoft. È inoltre spesso influenzato dalla congestione della rete che esiste nei colli di bottiglia nei dispositivi di rete complessi o nelle aree Wi-Fi con una copertura scadente.

## <a name="microsoft-teams"></a>Microsoft Teams

Per Microsoft teams la qualità della rete viene misurata come latenza UDP, jitter UDP e perdita di pacchetti UDP. UDP viene utilizzato per la connettività multimediale di chiamata e di audioconferenza per Microsoft teams. Questo può influire sugli stessi fattori di latenza e velocità di download, oltre agli spazi di connettività nel supporto UDP di una rete, poiché UDP è configurato separatamente per il protocollo TCP più comune.

## <a name="related-topics"></a>Argomenti correlati

[Suggerimenti relativi alle prestazioni di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Test di connettività Microsoft 365 nell'interfaccia di amministrazione di M365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)](office-365-network-mac-location-services.md)
