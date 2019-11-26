---
title: Analizzare i dati in un set di revisione in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 60436db997d75d92e7d17fc27f66eb3944b419d8
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256903"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizzare i dati in un set di revisione in Advanced eDiscovery

Quando il numero di documenti raccolti è di grandi dimensioni, può essere difficile rivederli tutti. Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti in modo da ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in maniera coerente. Per ulteriori informazioni su queste funzionalità, vedere:

- [Rilevamento dei documenti simili](near-duplicates.md)

- [Threading posta elettronica](email-threading.md)

- [Temi](themes.md)

Per analizzare i dati in un set di Revisione:

1. Configurare le impostazioni di analisi per il caso. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).

2. Aprire il set di revisione che si desidera analizzare.

3. Fare clic su **Gestisci Revisione set**.

4. Fare clic su **Esegui analisi per il set di revisione**.

È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** del caso.

 Dopo aver completato l'analisi, è possibile visualizzare il rapporto analitico, eseguire query all'interno del set di recensioni sugli output dell'analisi (vedere [query nel set di recensioni](review-set-search.md)) e vedere i documenti correlati di un documento specifico (vedere [reviewing data in Review set](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Report di analisi

Per visualizzare un report di analisi per un set di Revisione:

1. Aprire il set di revisione.

2. Fare clic su **Gestisci Revisione set**.

3. Fare clic su **Visualizza report**.

Il report ha quattro componenti dall'analisi:

- **Breakdown** : il numero di messaggi di posta elettronica, allegati e documenti sciolti è stato trovato nel set di revisione.

- **Documenti (esclusi gli allegati)** -quanti documenti sfusi sono stati pivot, unici in prossimità di duplicati di un pivot o duplicati esatti di un altro documento.

- **Messaggi di posta elettronica-il** numero di email sono stati inclusivi, copie inclusive, svantaggi inclusi o nessuno di questi.

- **Allegati** -quanti allegati di posta elettronica sono stati univoci o duplicati di un altro allegato di posta elettronica nel set di revisione.