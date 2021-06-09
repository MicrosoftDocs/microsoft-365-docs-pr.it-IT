---
title: Analizzare i dati in un set di recensioni in Advanced eDiscovery
f1.keywords:
- NOCSH
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
description: Informazioni sugli strumenti disponibili per organizzare i set di documenti durante l'analisi di un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751371"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizzare i dati in un set di recensioni in Advanced eDiscovery

Quando il numero di documenti raccolti è elevato, può essere difficile esaminarli tutti. Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti per ridurre il volume di documenti da rivedere senza alcuna perdita di informazioni e per organizzare i documenti in modo coerente. Per ulteriori informazioni su queste funzionalità, vedere:

- [Rilevamento dei documenti simili](near-duplicate-detection-in-advanced-ediscovery.md)

- [Threading posta elettronica](email-threading-in-advanced-ediscovery.md)

- [Temi](themes-in-advanced-ediscovery.md)

Per analizzare i dati in un set di recensioni:

1. Configurare le impostazioni di analisi per il caso. Per ulteriori informazioni, vedere [Configure search and analytics settings.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)

2. Aprire il set di recensioni che si desidera analizzare.

3. Fare clic **su Gestisci set di revisioni.**

4. Fare **clic su Esegui analisi per il set di revisione.**

È possibile controllare lo stato di avanzamento dell'analisi nella **scheda Processi** del caso.

 Al termine dell'analisi, è possibile visualizzare il report di analisi, eseguire query all'interno del set di revisioni sugli output dell'analisi (vedere Query all'interno del [set](review-set-search.md)di revisioni ) e visualizzare i documenti correlati di un determinato documento (vedere Revisione dei dati nel set di [revisioni](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Report analitico

Per visualizzare un report di analisi per un set di recensioni:

1. Apri il set di recensioni.

2. Fare clic **su Gestisci set di revisioni.**

3. Fare **clic su Visualizza report.**

Il report include sette componenti dell'analisi:

- **Popolazione di destinazione:** Numero di messaggi di posta elettronica, allegati e documenti liberi trovati nel set di revisioni.

- **Documenti (allegati esclusi):** Il numero di documenti liberi che sono pivot, univoci quasi duplicati di un pivot o un duplicato esatto di un altro documento.

- **Messaggi di posta elettronica:** Numero di messaggi di posta elettronica inclusivi, copie incluse, meno inclusivi o nessuno dei precedenti.

- **Allegati:** Numero di allegati di posta elettronica univoci o duplicati di un altro allegato di posta elettronica nel set di revisioni.

- **Numero di file per tipo:** Numero di file, identificati dall'estensione di file.

- **Documenti per origine:** Riepilogo del contenuto in base all'origine dati originale.

- **Documenti aggregati per processo:** Riepilogo del contenuto in base ai processi del set di revisione. 
