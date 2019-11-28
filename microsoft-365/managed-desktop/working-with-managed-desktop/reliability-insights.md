---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634033"
---
# <a name="reliability-insights"></a>Dati analitici sull'affidabilità

Questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti. Per visualizzare i dati di attendibilità, selezionare la scheda **affidabilità** .


![Riquadro affidabilità](images/insights_reliability.png)

La sezione **affidabilità tra i dispositivi** offre un riepilogo rapido dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integro" e il tempo medio osservato dopo l'ultimo errore segnalato. 

 
Il grafico sull' **affidabilità nel tempo** sulla destra riporta il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.

La sezione **problemi principali** specifica i problemi rilevati specifici che incidono almeno sul 5% dei dispositivi gestiti. I dettagli riportati includono:

- Il tipo di problema
    - Crash dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto
    - L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input
    - Errori critici, che si verificano quando Windows ha riscontrato un problema di cui non è possibile eseguire il ripristino
- Il numero di dispositivi coinvolti nello stesso problema
- La percentuale di dispositivi gestiti che il numero rappresenta
- Il numero totale di occorrenze del problema specifico
- Il componente software che sembra essere l'origine del problema
- La categoria del problema rilevato:
    - Browser (Edge, Chrome, IE)
    - Unknown (componenti non Microsoft)
    - Driver (audio, grafica o altri driver)
    - Produttività (Slack, G-Suites, Microsoft Office e relativi componenti aggiuntivi o estensioni, Teams)
    - Contenuto multimediale (app di immagini, musica o video
    - Sicurezza (componenti di sicurezza di Windows)
- Lo stato corrente delle operazioni di Microsoft Managed Desktop indaga e rimedia il problema

