---
title: Dati analitici sulle batterie
description: Report che mostra i dati sulla durata stimata della batteria e sui principali consumatori di energia
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579711"
---
# <a name="battery-insights"></a>Dati analitici sulle batterie
Questa visualizzazione fornisce metriche di utilizzo di alimentazione, batteria e app per i dispositivi Microsoft Managed Desktop. Per questi scopi, un'app viene considerata "in uso" se è in esecuzione e a fuoco.

Per visualizzare i dati di utilizzo, selezionare la **scheda** Batteria.

![Riquadro batteria: durata stimata della batteria per modello di dispositivo in alto a sinistra, consumo di energia superiore (per app) in alto a destra, tabella insights nella parte inferiore. Collegamento documentazione in alto a destra](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Durata stimata della batteria

Nell'area **Durata prevista della** batteria vengono fornite previsioni per la durata prevista della batteria per i dispositivi, organizzati in base al modello di dispositivo.

> [!NOTE]
> Questi dati derivano dal campionamento dell'utilizzo di <em></em> energia, del tempo di utilizzo e della capacità della batteria da una selezione casuale dei dispositivi nella distribuzione di Microsoft Managed Desktop che segnalano anche i dati.

La tabella fornisce la durata stimata della batteria (in ore), la durata media della batteria per gli stessi modelli in altre distribuzioni di Microsoft Managed Desktop e il numero di dispositivi che segnalano questi dati nell'ambiente. Ordinare i dati selezionando le intestazioni di colonna.



## <a name="top-energy-consumers"></a>Principali consumatori di energia

Nell'area **Consumatori** di energia principali sono disponibili le app nell'ambiente che consumano più energia in milliWatt-hours (mWh). Le app visualizzate sono per dispositivo specifico, che è possibile selezionare nella **sezione Durata stimata** della batteria a sinistra. Ad esempio, per visualizzare il consumo per app per i dispositivi Microsoft Surface Book 2, seleziona la riga nell'area di durata della batteria. Se non si seleziona alcun modello, i dati di consumo delle app visualizzati sono per tutte le app per cui sono disponibili dati collettivamente.

 Per ogni app, i segmenti colorati mostrano la distribuzione dell'uso dell'energia dell'app tra queste categorie:

- CPU
- Visualizza
- Rete
- Altro

"Altro" potrebbe includere il consumo di energia da un'ampia gamma di fonti, come l'attività del disco, l'utilizzo della banda larga mobile e l'energia persa a causa della resistenza interna. 

Puoi filtrare questa visualizzazione per mostrare solo le app in primo piano, le app in background o entrambe usando il menu in alto a destra. Le app in primo piano sono quelle che hanno avuto interazione con l'utente negli ultimi 28 giorni, ad esempio la selezione di un elemento con il mouse.

## <a name="insights"></a>Dati analitici

**L'area Insights** mostra i primi tre consumatori di energia nelle categorie CPU e rete. Questi elementi consumano energia superiore alla media rispetto a tutte le distribuzioni di Microsoft Managed Desktop. La risorsa di visualizzazione non viene visualizzata perché dipende in larga parte dalle impostazioni di tempo di utilizzo del dispositivo e luminosità dello schermo. 

Per ulteriori informazioni, selezionare **le presentazioni** nella colonna Dettagli.

## <a name="battery-optimization"></a>Ottimizzazione della batteria

Windows 10 offre numerose impostazioni [del dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) per migliorare l'utilizzo dell'alimentazione e aumentare la durata della batteria dei dispositivi Microsoft Managed Desktop. Alcune di queste impostazioni possono ridurre altre funzionalità di Windows, quindi dovrai anche prendere in considerazione altri fattori, ad esempio il ruolo del dispositivo nell'organizzazione. Il supporto di Windows mantiene un elenco di questi suggerimenti [per il risparmio della batteria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Gli utenti possono modificare alcune impostazioni in modo personalizzato senza la necessità di elevazione o supporto dell'amministratore. Altre impostazioni richiedono il supporto dell'amministratore IT dell'organizzazione.
