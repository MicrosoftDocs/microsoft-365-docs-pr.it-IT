---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739784"
---
# <a name="reliability-insights"></a>Dati analitici sull'affidabilità

Questa visualizzazione fornisce un riepilogo dell'integrità dei dispositivi gestiti. Per visualizzare i dati di affidabilità, selezionare la **scheda Affidabilità.**


![Riquadro Affidabilità: affidabilità tra i dispositivi in alto a sinistra, grafico dell'affidabilità nel tempo in alto a destra, tabella dei problemi principali nella parte inferiore. Pulsanti guida e feedback in basso a destra.](../../media/insights_reliability.png)

La  sezione Affidabilità tra dispositivi offre un breve riepilogo dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integri" e il tempo medio osservato dopo l'ultimo errore segnalato. 

 
Il **grafico Affidabilità nel** tempo a destra segnala il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.

La **sezione Problemi principali** contiene informazioni dettagliate sui problemi rilevati specifici che interessano almeno il 5% dei dispositivi gestiti. I dettagli segnalati includono:

- Tipo di problema
    - Arresto anomalo dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto
    - L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input
    - Errori critici che si verificano Windows si è verificato un problema da cui non è possibile eseguire il ripristino
- Il numero di dispositivi interessati dallo stesso problema
- Percentuale di dispositivi gestiti che il numero rappresenta
- Conteggio totale delle occorrenze del problema specifico
- Il componente software che sembra essere l'origine del problema
- Categoria del problema rilevato:
    - Browser (Edge, Chrome, IE)
    - Sconosciuto (componenti non Microsoft)
    - Driver (audio, grafica o altri driver)
    - Produttività (Slack, G-Suites, Microsoft Office e relativi componenti aggiuntivi o estensioni, Teams)
    - App multimediali (immagini, musica o video
    - Sicurezza (Windows componenti di sicurezza)
- Lo stato corrente di Microsoft Managed Desktop operations analizza e correggere il problema

