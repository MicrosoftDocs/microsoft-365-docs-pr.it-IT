---
title: Intuizioni della batteria
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 056685cbd49e6fb247a92357b3483b479d705c90
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085731"
---
# <a name="battery-insights"></a>Intuizioni della batteria
Questa visualizzazione fornisce metriche per l'utilizzo di energia, batteria e app per i dispositivi Microsoft Managed Desktop. A tal fine, un'app viene considerata "in uso" se è in esecuzione e in stato di inattività.

Per visualizzare i dati di utilizzo, selezionare la scheda **batteria** .

![Riquadro della batteria: durata stimata della batteria per modello di dispositivo in alto a sinistra, consumer energetici superiori (per app) in alto a destra, tabella Insights nella parte inferiore. Collegamento alla documentazione in alto a destra.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Durata prevista della batteria

Nell'area di **durata della batteria** prevista, vengono fornite previsioni per la durata prevista della batteria per i dispositivi, organizzati per modello di dispositivo.

> [!NOTE]
> Questi dati sono derivati dal campionamento dell'utilizzo di energia, dal tempo di utilizzo e dalla capacità della batteria da una <em>selezione</em> casuale dei dispositivi nella distribuzione di Microsoft Managed Desktop che sono anche i dati di report.

La tabella fornisce la durata prevista della batteria (in ore), la durata media della batteria per gli stessi modelli in altre distribuzioni di Microsoft Managed Desktop e il numero di dispositivi che segnalano tali dati nell'ambiente. Ordinare i dati selezionando le intestazioni di colonna.



## <a name="top-energy-consumers"></a>Top Energy consumer

Nell'area **Top Energy consumer** sono disponibili le app nel proprio ambiente che consumano il maggior numero di energia in milliwatt-hours (MWh). Le app mostrate sono per dispositivo specifico, che si seleziona nella sezione **durata prevista della batteria** a sinistra. Ad esempio, per visualizzare i consumi per app per i dispositivi di Microsoft Surface Book 2, selezionare tale riga nell'area Durata batteria. Se non si seleziona un modello, i dati di consumo delle app sono visualizzati per tutte le app che sono disponibili per i dati collettivi.

 Per ogni app, i segmenti colorati mostrano la distribuzione dell'utilizzo di energia dell'app tra queste categorie:

- CPU
- Schermo
- Rete
- Altro

"Altro" potrebbe includere il consumo di energia da diverse fonti, come l'attività su disco, l'utilizzo della banda larga mobile e l'energia persa per la resistenza interna. 

È possibile filtrare questa visualizzazione in modo da visualizzare solo le app in primo piano, le app in background o entrambe utilizzando il menu in alto a destra. Le app in primo piano sono quelle che hanno avuto l'interazione degli utenti negli ultimi 28 giorni, ad esempio la selezione di un elemento con un mouse.

## <a name="insights"></a>Approfondimenti

Nell'area **Insights** sono elencati i primi tre consumer energetici nelle categorie CPU e rete. Questi elementi consumano energia superiore alla media rispetto a tutte le distribuzioni desktop Microsoft gestite. Non viene visualizzata la risorsa di visualizzazione perché dipende fortemente dalle impostazioni di tempo di utilizzo del dispositivo e della luminosità dello schermo. 

Per ulteriori informazioni, selezionare gli elenchi nella colonna **Details** .

## <a name="battery-optimization"></a>Ottimizzazione della batteria

Windows 10 offre numerose [impostazioni del dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) per migliorare l'utilizzo dell'alimentazione e aumentare la durata della batteria dei dispositivi Microsoft Managed Desktop. Alcune di queste impostazioni possono ridurre le altre funzionalità di Windows, pertanto è necessario prendere in considerazione anche altri fattori, ad esempio il ruolo del dispositivo nell'organizzazione. Il supporto di Windows gestisce un elenco di questi suggerimenti per il [salvataggio della batteria](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Gli utenti possono modificare le impostazioni in base alle proprie esigenze, senza necessità di supporto o elevazione di amministratore. Altre impostazioni richiedono supporto dall'amministratore IT dell'organizzazione.
