---
title: Eseguire analisi per velocizzare le indagini
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
description: ''
ms.openlocfilehash: c71f3a31c49c92a24d449fae151b858645ad2df6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081543"
---
# <a name="run-analytics-to-investigate-faster"></a>Eseguire analisi per velocizzare le indagini

Quando un insieme Evidence è di grandi dimensioni, può essere difficile rivederle tutte. Un insieme di evidenze spesso include più copie dello stesso tipo o di messaggi di posta elettronica o documenti simili. Indagini sui dati (Preview) fornisce una serie di strumenti di analisi che consentono di ridurre il volume dei documenti che devono essere esaminati senza perdita di informazioni. Per ulteriori informazioni su queste funzionalità, vedere:

- [Rilevamento dei documenti simili](near-duplicates.md)

- [Threading posta elettronica](email-threading.md)

- [Temi](themes.md)

Per analizzare i dati in un set di evidenze:

1. Configurare le impostazioni di analisi per l'indagine. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).

2. Aprire il set di prove.

3. Fare clic su **Gestisci evidenza**.

4. In **analisi**fare clic su **analizza**.

È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** dell'indagine. Il tipo di processo attivato è denominato **Running Analytics**.

 Al termine dell'analisi, è possibile visualizzare un elenco di duplicati esatti o quasi duplicati del documento che si sta esaminando nel riquadro a destra. Per selezionare tutti i duplicati del documento che si sta visualizzando, è possibile farlo facilmente usando questo pannello. Per ulteriori informazioni su altre caratteristiche di questo pannello, vedere [Review data in evidence](review-data-in-evidence.md). 

È inoltre possibile eseguire query aggiuntive all'interno dell'evidenza utilizzando gli output dell'analisi, ad esempio i temi. Per ulteriori informazioni, vedere [query the data in evidence](evidence-query.md).

## <a name="analytics-report"></a>Report di analisi

Per visualizzare un report di analisi per l'evidenza:

1. Aprire il set di prove.

2. Fare clic su **Gestisci evidenza**.

3. In **analisi**fare clic su **Visualizza report**.

Il report ha quattro componenti dall'analisi:

- **Breakdown** : il numero di messaggi di posta elettronica, allegati e documenti RAW trovati nel set di evidenze.

- **Email** : il numero di messaggi di eamil che sono inclusivi, meno inclusi, copie inclusive o nessuno dei precedenti.
   - Inclusive: l'ultimo messaggio nel thread di posta elettronica che contiene tutta la cronologia precedente e richiede la revisione.
   - Svantaggi inclusi: il messaggio nel thread che contiene uno o più allegati diversi che richiedono la revisione.
   - Copie Inclusive: il messaggio che rappresenta una copia di un altro messaggio con meno inclusivo o inclusivo (oggetto e corpo).

- **Allegati** : il numero di allegati di posta elettronica che sono univoci o duplicati di un allegato di posta elettronica diverso all'interno dello stesso elemento di prova stesso.

- **Documenti (esclusi gli allegati di posta elettronica)** -numero di documenti univoci che richiedono la revisione, ad esempio il documento più rappresentativo del set quasi duplicato o un duplicato esatto di un altro documento.
