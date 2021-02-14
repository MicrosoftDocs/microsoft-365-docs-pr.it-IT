---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950343"
---
# <a name="reliability-insights"></a>Dati analitici sull'affidabilità

Questa visualizzazione fornisce un riepilogo dell'integrità dei dispositivi gestiti. Per visualizzare i dati di affidabilità, selezionare **la scheda Affidabilità.**


![Riquadro Affidabilità: affidabilità tra i dispositivi in alto a sinistra, affidabilità nel grafico del tempo in alto a destra, tabella dei problemi principali nella parte inferiore. Pulsanti guida e feedback in basso a destra.](../../media/insights_reliability.png)

La  sezione Affidabilità tra dispositivi offre un breve riepilogo dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integri" e il tempo medio osservato dopo l'ultimo errore segnalato. 

 
Il **grafico Affidabilità nel** tempo sulla destra segnala il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.

Nella **sezione Principali problemi** vengono fornite informazioni dettagliate sui problemi rilevati specifici che interessano almeno il 5% dei dispositivi gestiti. I dettagli segnalati includono:

- Tipo di problema
    - Arresti anomali dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto
    - L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input
    - Errori critici che si verificano quando Si verifica un problema in Windows da cui non è possibile eseguire il ripristino
- Il numero di dispositivi interessati dallo stesso problema
- Percentuale di dispositivi gestiti che il numero rappresenta
- Numero totale di occorrenze del problema specifico
- Il componente software che sembra essere l'origine del problema
- Categoria del problema rilevato:
    - Browser (Edge, Chrome, IE)
    - Sconosciuto (componenti non Microsoft)
    - Driver (audio, grafica o altri driver)
    - Produttività (Slack, G-Suite, Microsoft Office componenti aggiuntivi o estensioni, Teams)
    - App multimediali (app per immagini, musica o video
    - Sicurezza (componenti di sicurezza di Windows)
- Lo stato corrente di Microsoft Managed Desktop Operations analizza e corree il problema

