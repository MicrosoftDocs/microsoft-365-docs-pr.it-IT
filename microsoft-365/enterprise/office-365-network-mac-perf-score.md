---
title: Valutazione della rete Microsoft 365 (Preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
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
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200748"
---
# <a name="microsoft-365-network-assessment-preview"></a>Valutazione della rete Microsoft 365 (Preview)

Nella connettività di rete dell'interfaccia di amministrazione di Microsoft 365, le **valutazioni di rete** distillano un'aggregazione di molte metriche delle prestazioni di rete in un'istantanea dell'integrità del perimetro della rete aziendale, rappresentata da un valore a punti compreso tra 0-100. Una valutazione della rete indica quanto la progettazione della rete responsabile del cliente ha un impatto sull'esperienza utente di Office 365. Le valutazioni di rete sono limitate all'intero tenant e per ogni posizione geografica da cui gli utenti si connettono al tenant, fornendo agli amministratori di Microsoft 365 un modo semplice per afferrare istantaneamente una Gestalt dell'integrità della rete dell'organizzazione e analizzarla rapidamente in una relazione dettagliata per qualsiasi posizione globale dell'ufficio.

Il valore dei punti di valutazione della rete è una media della latenza TCP, della velocità di download e delle metriche di qualità della connessione UDP compilate una volta al giorno. Le metriche delle prestazioni per le reti di proprietà di Microsoft sono escluse da queste misure per garantire che i risultati della valutazione siano inequivocabili e specifici per la rete aziendale.

![Valore di valutazione della rete](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valore di valutazione della rete molto basso suggerisce che i client Microsoft 365 avranno problemi significativi per la connessione al tenant o per il mantenimento di un'esperienza utente reattiva, mentre un valore elevato indica una rete adeguatamente configurata con alcuni problemi di prestazioni in esecuzione. Un valore pari a 80% rappresenta una linea di base sana in cui non si dovrebbe pretendere di ricevere reclami da un utente regolare sulla connettività di Microsoft 365 o la risposta a causa delle prestazioni di rete. Quando vengono apportati miglioramenti della connettività di rete iterativa, questo valore aumenterà insieme all'esperienza utente.

| Valutazione della rete | Esperienza utente prevista |
| :----------------- | :----------------------- |
| 100                | Elevate                     |
| 80                 | Soddisfa le raccomandazioni    |
| 60                 | Accettabile               |
| 40                 | Gli utenti possono riscontrare problemi |
| 20                 | Gli utenti possono lamentarsi       |
| 0                  | Problemi di rete un argomento comune di discussione |

>[!IMPORTANT]
>Insights di rete, raccomandazioni sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="network-assessment-panel"></a>Pannello di valutazione della rete

Ogni valutazione di rete, se ambito del tenant o di una specifica posizione di Office, Visualizza un riquadro con i dettagli relativi alla valutazione. In questo riquadro viene visualizzato un grafico a barre della valutazione, sia in percentuale che come punti totali per ogni carico di lavoro del componente, compresi solo i carichi di lavoro in cui sono stati ricevuti i dati di misurazione. Per una valutazione della rete delle posizioni di Office, viene mostrato anche un confronto con la percentuale di clienti di Microsoft 365 in ognuno dei cinque quintiles che hanno riportato dati nella stessa città del percorso di Office.

![Valore di valutazione della rete di esempio](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

La **ripartizione di valutazione** nel pannello Visualizza la valutazione per ognuno dei carichi di lavoro del componente.

La **cronologia di valutazione** indica gli ultimi 30 giorni della valutazione e del benchmark. È inoltre possibile segnalare la cronologia delle metriche per qualsiasi percorso di Office per un massimo di due anni utilizzando la scheda cronologia. La scheda cronologia consente di selezionare gli attributi da segnalare e scegliendo un intervallo di tempo dei rapporti è possibile evidenziare l'impatto di un progetto di aggiornamento della rete e vedere il miglioramento della valutazione della rete.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Valutazioni della rete tenant e valutazioni della rete delle posizioni di Office

Una valutazione della rete misura la progettazione del perimetro di rete di una posizione di Office alla rete di Microsoft. I miglioramenti apportati al perimetro della rete sono migliori in ogni posizione dell'ufficio.

Viene mostrato un valore di valutazione della rete per l'intero tenant Microsoft 365 nella pagina Panoramica delle prestazioni di rete, che corrisponde a una media ponderata delle valutazioni di rete per tutte le posizioni di Office. È inoltre disponibile un valore di valutazione della rete specifico per ogni posizione di Office rilevata nella pagina di riepilogo di tale percorso.

## <a name="exchange-online"></a>Exchange Online

Per Exchange Online, la latenza TCP dal computer client al servizio Exchange porta anteriore viene misurata. Questo può influire sulla distanza che la rete percorre nei clienti LAN e WAN. Può anche essere influenzato da dispositivi o servizi di intermediazione di rete che ritardano la connettività o causano il rimandato dei pacchetti. Ed è influenzato da quanto è lontana la porta principale del servizio Exchange più vicino. La mediana (nota anche come misura cinquantesimo percentile o P50) viene rilevata per tutte le misurazioni negli ultimi tre giorni.

La valutazione di Exchange Online viene effettuata utilizzando la tabella seguente. Qualsiasi numero di latenza TCP tra le soglie sono assegnati punti linearmente all'interno della banda.

| Latenza TCP   | Punti |
| :------------ | :----- |
| 10ms o meno  | 100    |
| 25ms          | 80     |
| 100 ms         | 60     |
| 200ms         | 40     |
| 300ms         | 20     |
| 350ms o più | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Per SharePoint Online, la velocità di download disponibile per un utente per l'accesso a un documento da SharePoint o OneDrive viene misurata. Questo può essere influenzato dalla larghezza di banda disponibile nei circuiti di rete tra il computer client e la rete di Microsoft. È inoltre spesso influenzato dalla congestione della rete che esiste nei colli di bottiglia nei dispositivi di rete complessi o nelle aree Wi-Fi con una copertura scadente. La velocità di download viene misurata in megabyte al secondo, che corrisponde a circa un decimo dei circuiti con valori di megabit al secondo. L'unità MegaByte al secondo è utile perché è possibile vedere direttamente il file di dimensioni che è possibile scaricare in 1 secondo. Il venticinquesimo percentile (noto anche come misura P25) viene eseguito per tutte le misurazioni nei tre giorni precedenti. Questo venticinquesimo percentile aiuta a ridurre l'impatto del variare della congestione nel tempo.

La valutazione di SharePoint Online viene effettuata utilizzando la tabella seguente. Qualsiasi numero di velocità di download tra le soglie sono assegnati punti linearmente all'interno della banda.

| Velocità di download | Punti |
| :------------- | :----- |
| 20MBps o più | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Per Microsoft teams la qualità della rete viene misurata come latenza UDP, jitter UDP e perdita di pacchetti UDP. UDP viene utilizzato per la connettività multimediale di chiamata e di audioconferenza per Microsoft teams. Questo può influire sugli stessi fattori di latenza e velocità di download, oltre agli spazi di connettività nel supporto UDP di una rete, poiché UDP è configurato separatamente per il protocollo TCP più comune. La mediana (nota anche come misura cinquantesimo percentile o P50) viene rilevata per tutte le misurazioni negli ultimi tre giorni. 

Si calcola un punteggio di opinione medio da queste misure UDP per una scala da 1 a 5. Viene quindi mappato alla scala di 0-100 punti per la valutazione della rete Microsoft teams.  Overall good è oltre 87,5 punti e complessivamente Bad è inferiore a 50 punti.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Strumento di test della connettività di rete Microsoft 365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)](office-365-network-mac-location-services.md)
