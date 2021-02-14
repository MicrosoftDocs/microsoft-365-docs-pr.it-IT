---
title: Valutazione della rete di Microsoft 365 (anteprima)
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
description: Valutazione della rete di Microsoft 365 (anteprima)
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200748"
---
# <a name="microsoft-365-network-assessment-preview"></a>Valutazione della rete di Microsoft 365 (anteprima)

Nella connettività di rete dell'interfaccia di  amministrazione di Microsoft 365, le valutazioni della rete trasformano un aggregato di molte metriche sulle prestazioni di rete in uno snapshot dell'integrità perimetrale della rete aziendale, rappresentata da un valore in punti compreso tra 0 e 100. Una valutazione di rete indica quanto la progettazione della rete responsabile del cliente influisce sull'esperienza utente di Office 365. Le valutazioni di rete hanno come ambito l'intero tenant e per ogni posizione geografica da cui gli utenti si connettono al tenant, fornendo agli amministratori di Microsoft 365 un modo semplice per comprendere immediatamente l'integrità della rete aziendale ed eseguire rapidamente il drill-down in un report dettagliato per qualsiasi sede globale.

Il valore dei punti di valutazione della rete è una media della latenza TCP, della velocità di download e delle metriche di qualità della connessione UDP compilate una volta al giorno. Le metriche delle prestazioni per le reti di proprietà di Microsoft sono escluse da queste misurazioni per garantire che i risultati della valutazione siano univoci e specifici della rete aziendale.

![Valore di valutazione della rete](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valore di valutazione della rete molto basso suggerisce che i client Microsoft 365 avranno problemi significativi di connessione al tenant o di gestione di un'esperienza utente reattiva, mentre un valore elevato indica una rete configurata correttamente con pochi problemi di prestazioni continui. Un valore pari all'80% rappresenta una linea di base integra in cui non è consigliabile ricevere reclami regolari degli utenti sulla connettività o sulla velocità di risposta di Microsoft 365 a causa delle prestazioni della rete. Con l'apportare miglioramenti alla connettività di rete iterativi, questo valore aumenta insieme all'esperienza utente.

| Valutazione della rete | Esperienza utente prevista |
| :----------------- | :----------------------- |
| 100                | Elevate                     |
| 80                 | Soddisfa i suggerimenti    |
| 60                 | Accettabile               |
| 40                 | È possibile che si verifichino problemi per gli utenti |
| 20                 | Gli utenti possono presentare reclamo       |
| 0                  | Problemi di rete un argomento di discussione comune |

>[!IMPORTANT]
>Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="network-assessment-panel"></a>Pannello di valutazione della rete

Ogni valutazione di rete, nell'ambito del tenant o di una posizione specifica dell'ufficio, mostra un pannello con informazioni dettagliate sulla valutazione. Questo pannello mostra un grafico a barre della valutazione sia come percentuale che come punti totali per ogni carico di lavoro dei componenti, inclusi solo i carichi di lavoro in cui sono stati ricevuti i dati di misurazione. Per una valutazione della rete di posizione dell'ufficio, viene inoltre illustrato un confronto con la percentuale di clienti di Microsoft 365 in ognuna delle cinque quintile che hanno segnalato i dati nella stessa città della sede dell'ufficio.

![Valore di valutazione di rete di esempio](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

La **suddivisione della** valutazione nel pannello mostra la valutazione per ognuno dei carichi di lavoro dei componenti.

La **cronologia della valutazione** mostra gli ultimi 30 giorni della valutazione e del benchmark. È inoltre possibile creare report sulla cronologia delle metriche per qualsiasi sede dell'ufficio per un massimo di due anni utilizzando la scheda Cronologia. La scheda cronologia consente di selezionare gli attributi su cui creare report e di scegliere un intervallo di tempo per i report, è possibile evidenziare l'impatto di un progetto di aggiornamento della rete e vedere il miglioramento della valutazione della rete.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Valutazioni della rete tenant e valutazioni della rete della posizione dell'ufficio

Una valutazione della rete misura la progettazione del perimetro di rete di una posizione di ufficio nella rete di Microsoft. I miglioramenti apportati al perimetro di rete sono ottimali in ogni posizione dell'ufficio.

Nella pagina di panoramica delle prestazioni di rete viene visualizzato un valore di valutazione della rete per l'intero tenant di Microsoft 365, che è una media ponderata delle valutazioni di rete per tutte le posizioni degli uffici. Esiste anche un valore specifico per la valutazione della rete per ogni posizione dell'ufficio rilevata nella pagina di riepilogo di tale posizione.

## <a name="exchange-online"></a>Exchange Online

Per Exchange Online viene misurata la latenza TCP dal computer client al front door del servizio Exchange. Ciò può essere influenzata dalla distanza che la rete viaggia tra la RETE LAN e la WAN dei clienti. Può anche essere influenzata da dispositivi o servizi di intermediazione di rete che ritardano la connettività o causano il resent dei pacchetti. Ed è influenzata dalla distanza dalla porta d'ingresso del servizio Exchange più vicina. La mediana (nota anche come 50° percentile o misura P50) viene misurata per tutte le misurazioni degli ultimi tre giorni.

La valutazione di Exchange Online viene effettuata utilizzando la tabella seguente. A qualsiasi numero di latenza TCP tra le soglie vengono assegnati punti linearmente all'interno della banda.

| Latenza TCP   | Punti |
| :------------ | :----- |
| 10 ms o meno  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms o più | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Per SharePoint Online viene misurata la velocità di download disponibile per un utente per accedere a un documento da SharePoint o OneDrive. Ciò può essere influenzata dalla larghezza di banda disponibile nei circuiti di rete tra il computer client e la rete di Microsoft. Inoltre, spesso è influenzata dalla congestione della rete presente in colli di bottiglia in dispositivi di rete complessi o in aree Wi-Fi scarsa. La velocità di download viene misurata in megabyte al secondo, ovvero circa un decimo di megabit valutati in circuiti al secondo. L'unità MegaByte al secondo è utile perché è possibile visualizzare direttamente le dimensioni del file che è possibile scaricare in 1 secondo. Il 25° percentile (noto anche come misura P25) viene effettuato per tutte le misurazioni degli ultimi tre giorni. Questo 25° percentile consente di ridurre l'impatto di una congestione variabile nel tempo.

La valutazione di SharePoint Online viene effettuata utilizzando la tabella seguente. A qualsiasi numero di velocità di download tra le soglie vengono assegnati punti linearmente all'interno della banda.

| Velocità di download | Punti |
| :------------- | :----- |
| 20MBps o più | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Per Microsoft Teams, la qualità della rete viene misurata come latenza UDP, instabilità UDP e perdita di pacchetti UDP. UDP viene usato per la connettività multimediale audio e video per chiamate e conferenze per Microsoft Teams. Ciò può essere influenzata dagli stessi fattori della latenza e della velocità di download oltre che dalle lacune di connettività nel supporto UDP di una rete, poiché UDP è configurato separatamente per il protocollo TCP più comune. La mediana (nota anche come 50° percentile o misura P50) viene misurata per tutte le misurazioni degli ultimi tre giorni. 

Calcoliamo un punteggio di opinione medio da queste misurazioni UDP per una scala da 1 a 5. Viene quindi mappato alla scala da 0 a 100 punti per la valutazione della rete di Microsoft Teams.  Complessivamente buona è oltre 87,5 punti e la parte negativa complessiva è inferiore a 50 punti.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni dettagliate sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Strumento di test della connettività di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Servizi percorso di connettività di rete di Microsoft 365 (anteprima)](office-365-network-mac-location-services.md)
