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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083347"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizzare i dati in un set di revisione in Advanced eDiscovery

Quando il numero di documenti raccolti è di grandi dimensioni, può essere molto difficile rivederli tutti. Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti in modo da ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in maniera coerente. Per ulteriori informazioni su queste funzionalità, vedere:

- [Rilevamento dei documenti simili](near-duplicates.md)

- [Threading posta elettronica](email-threading.md)

- [Temi](themes.md)

Per analizzare i dati in un set di Revisione:

1. Configurare le impostazioni di analisi per il caso. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).

2. Aprire il set di revisione che si desidera analizzare.

3. Fare clic su **Gestisci Revisione set**.

4. Fare clic su **Esegui analisi per il set di revisione**.

È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** del caso.

 Dopo aver completato l'analisi, è possibile visualizzare il report di analisi, eseguire query all'interno del set di recensioni sugli output dell'analisi (vedere [query nel set di recensioni](review-set-search.md)) e vedere i documenti correlati di un documento specifico (vedere [revisione dei dati nel set](reviewing-data-in-review-set.md)di analisi).

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