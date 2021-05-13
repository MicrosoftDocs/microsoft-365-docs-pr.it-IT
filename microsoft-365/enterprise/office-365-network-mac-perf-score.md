---
title: Microsoft 365 di rete
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
description: Microsoft 365 di rete
ms.openlocfilehash: c09e34b1bc3a8bf0f82a4a1e3c72e67f320abd43
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470475"
---
# <a name="microsoft-365-network-assessment"></a>Microsoft 365 di rete

Nella connettività Microsoft 365 di rete dell'interfaccia di **amministrazione,** le valutazioni di rete trasformano un aggregato di molte metriche delle prestazioni di rete in uno snapshot dell'integrità del perimetro della rete aziendale. Una valutazione di rete indica l'impatto della progettazione della rete responsabile del cliente Office 365'esperienza utente. Le valutazioni di rete hanno come ambito sia l'intero tenant che ogni posizione geografica da cui gli utenti si connettono al tenant. Le valutazioni offrono agli Microsoft 365 un modo semplice per ottenere immediatamente un'idea dell'integrità della rete aziendale ed eseguire rapidamente il drill-down in un report dettagliato per qualsiasi sede globale.

Il valore dei punti di valutazione della rete è compreso tra 0 e 100 ed è una media delle metriche relative alla latenza TCP, alla velocità di download e alla qualità della connessione UDP. Queste metriche vengono compilate una volta al giorno. Le metriche delle prestazioni per le reti di proprietà di Microsoft sono escluse da queste misurazioni per garantire che i risultati della valutazione siano univoci e specifici per la rete aziendale.

> [!div class="mx-imgBorder"]
> ![Valore di valutazione della rete](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valore di valutazione di rete molto basso suggerisce che Microsoft 365 client avranno problemi significativi di connessione al tenant o di mantenere un'esperienza utente reattiva. Un valore elevato indica una rete configurata correttamente con pochi problemi di prestazioni in corso. Un valore pari all'80% rappresenta una linea di base integra, al di sopra della quale non dovresti aspettarti di ricevere reclami regolari da parte degli utenti sulla connettività Microsoft 365 o sulla velocità di risposta a causa delle prestazioni della rete. Con l'apportare miglioramenti alla connettività di rete iterativi, questo valore aumenterà insieme all'esperienza utente.

| Valutazione della rete | Esperienza utente prevista |
| :----------------- | :----------------------- |
| 100                | Elevate                     |
| 80                 | Soddisfa i suggerimenti    |
| 60                 | Accettabile               |
| 40                 | È possibile che si verifichino problemi per gli utenti |
| 20                 | Gli utenti possono lamentarsi       |
| 0                  | Problemi di rete un argomento comune di discussione |

>[!IMPORTANT]
>Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 registrati nel programma di anteprima delle funzionalità.

## <a name="network-assessment-panel"></a>Pannello di valutazione della rete

Ogni valutazione di rete, che si eserciti nel tenant o in una posizione specifica dell'ufficio, mostra un pannello con i dettagli sulla valutazione. Questo pannello mostra un grafico a barre della valutazione sia come percentuale che come punti totali per ogni carico di lavoro del componente, inclusi solo i carichi di lavoro in cui sono stati ricevuti i dati di misurazione. Per una valutazione della rete di posizione dell'ufficio, viene inoltre illustrato un confronto con la percentuale di clienti di Microsoft 365 in ognuno dei cinque quintili che hanno riportato i dati nella stessa città della sede dell'ufficio.

> [!div class="mx-imgBorder"]
> ![Valore di valutazione di rete di esempio](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

La **suddivisione della** valutazione nel pannello mostra la valutazione per ognuno dei carichi di lavoro dei componenti.

La **cronologia di valutazione** mostra gli ultimi 30 giorni della valutazione e del benchmark. È inoltre possibile creare report sulla cronologia delle metriche per qualsiasi sede dell'ufficio per un massimo di due anni utilizzando la scheda Cronologia. La scheda Cronologia consente di selezionare gli attributi per i report. Scegliendo un intervallo di tempo per i report, è possibile evidenziare l'impatto di un progetto di aggiornamento della rete e vedere il miglioramento della valutazione della rete.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Valutazioni della rete tenant e valutazioni della rete di posizione dell'ufficio

Una valutazione della rete misura la progettazione del perimetro di rete di una posizione dell'ufficio nella rete di Microsoft. I miglioramenti apportati al perimetro di rete sono ottimali in ogni posizione dell'ufficio.

Viene visualizzato un valore di valutazione della rete per l'Microsoft 365 tenant nella pagina panoramica delle prestazioni di rete. Questo valore è una media ponderata delle valutazioni di rete per tutte le posizioni dell'ufficio. Esiste anche un valore di valutazione della rete specifico per ogni posizione dell'ufficio rilevata nella pagina di riepilogo di tale posizione.

## <a name="exchange-online"></a>Exchange Online

Ad Exchange Online, viene misurata la latenza TCP dal computer client alla porta Exchange del servizio. Questa latenza può essere influenzata dalla distanza che la rete viaggia sulle reti LAN e WAN dei clienti. Può anche essere influenzata da dispositivi o servizi di intermediazione di rete, che ritardano la connettività o causano il risentimento dei pacchetti. Ed è influenzata dalla distanza dalla porta d'ingresso del Exchange più vicina. La mediana (nota anche come 50° percentile o misura P50) viene eseguita per tutte le misurazioni degli ultimi tre giorni.

La Exchange Online viene effettuata utilizzando la tabella seguente. A qualsiasi numero di latenza TCP tra le soglie vengono assegnati punti linearmente all'interno della banda.

| Latenza TCP   | Punti |
| :------------ | :----- |
| 10 ms o meno  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms o più | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Ad SharePoint Online viene misurata la velocità di download disponibile per un utente per accedere a un documento da SharePoint o OneDrive. Ciò può essere influenzata dalla larghezza di banda disponibile nei circuiti di rete tra il computer client e la rete di Microsoft. Inoltre, è spesso influenzata dalla congestione di rete presente in colli di bottiglia in dispositivi di rete complessi o in aree Wi-Fi scarsa copertura. La velocità di download è misurata in megabyte al secondo, ovvero circa un decimo di un circuito valutato megabit al secondo. L'unità MegaByte al secondo è utile perché è possibile visualizzare direttamente le dimensioni del file che è possibile scaricare in 1 secondo. Il 25° percentile (noto anche come misura P25) viene utilizzato per tutte le misurazioni degli ultimi tre giorni. Questo 25° percentile aiuta a ridurre l'impatto di una congestione variabile nel tempo.

La SharePoint online viene effettuata utilizzando la tabella seguente. A qualsiasi numero di velocità di download tra le soglie vengono assegnati punti linearmente all'interno della banda.

| Velocità di download | Punti |
| :------------- | :----- |
| 20 MBps o più | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2 MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Ad Microsoft Teams la qualità della rete viene misurata come latenza UDP, instabilità UDP e perdita di pacchetti UDP. UDP viene utilizzato per la connettività multimediale audio e video per chiamate e conferenze per Microsoft Teams. Questo può essere influenzato dagli stessi fattori della latenza e della velocità di download, oltre a lacune di connettività nel supporto UDP di una rete, poiché UDP è configurato separatamente per il protocollo TCP più comune. La mediana (nota anche come 50° percentile o misura P50) viene eseguita per tutte le misurazioni degli ultimi tre giorni. 

Calcoliamo un punteggio di opinione medio da queste misurazioni UDP per una scala da uno a cinque. Viene quindi mappato alla scala da 0 a 100 punti per la valutazione Microsoft Teams di rete.  Nel complesso, il valore è di oltre 87,5 punti e il male complessivo è inferiore a 50 punti.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'Microsoft 365 admin center (anteprima)](office-365-network-mac-perf-overview.md)

[Microsoft 365 informazioni dettagliate sulle prestazioni di rete (anteprima)](office-365-network-mac-perf-insights.md)

[Microsoft 365 di test della connettività di rete (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Servizi percorso di connettività di rete (anteprima)](office-365-network-mac-location-services.md)
