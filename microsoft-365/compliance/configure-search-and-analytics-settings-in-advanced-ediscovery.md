---
title: Configurare le impostazioni di ricerca e analisi
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
description: Configurare le impostazioni avanzate di eDiscovery che si applicano a tutti i set di revisione in un caso. Sono incluse le impostazioni per l'analisi e l'OCR.
ms.openlocfilehash: 2def41ecc090b54cd3d6b789c2d9890392d1e0d3
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202197"
---
# <a name="configure-search-and-analytics-settings"></a>Configurare le impostazioni di ricerca e analisi

È possibile configurare le impostazioni per ogni caso eDiscovery avanzato per controllare la funzionalità seguente.

- Quasi duplicati e threading della posta elettronica

- Temi

- Query set di revisione generata automaticamente

- Ignora testo

- Riconoscimento ottico del carattere

Per configurare le impostazioni di ricerca e analisi per un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso.

2. Nella scheda **Impostazioni** , in **Search & Analytics**, fare clic su **Seleziona**.

   Viene visualizzata la pagina Impostazioni case. Queste impostazioni vengono applicate a tutti i set di revisione in un caso.

   ![Configurare le impostazioni di analisi e ricerca per un caso avanzato di eDiscovery](media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Quasi duplicati e threading della posta elettronica

In questa sezione, è possibile impostare parametri per il rilevamento duplicati, vicino al rilevamento duplicati e al threading tramite posta elettronica. Per ulteriori informazioni, vedere [near duplicate detection](near-duplicates.md) and [email Threading](email-threading.md).

- **Quasi duplicati/threading della posta elettronica:** Quando si esegue l'analisi dei dati in un set di revisione, quando si attiva il rilevamento duplicati, vicino al rilevamento duplicati e al threading della posta elettronica, vengono inclusi come parte del flusso di lavoro.

- **Soglia di somiglianza tra documenti e messaggi di posta elettronica:** Se il livello di somiglianza per due documenti è superiore alla soglia, entrambi i documenti vengono inseriti nello stesso set di duplicati vicino.

- **Numero minimo/massimo di parole:** Queste impostazioni specificano che l'analisi nei pressi dei duplicati e del threading della posta elettronica viene eseguita solo sui documenti che hanno almeno il numero minimo di parole e al massimo il numero di parole.

## <a name="themes"></a>Temi

In questa sezione, è possibile impostare parametri per i temi. Per ulteriori informazioni, vedere [Themes](themes-in-advanced-ediscovery.md).

- **Temi:** Quando si attiva l'operazione, il clustering dei temi viene eseguito come parte del flusso di lavoro quando si esegue l'analisi dei dati in un set di revisione.

- **Numero massimo di temi:** Specifica il numero massimo di temi che possono essere generati quando si esegue l'analisi dei dati in un set di revisione.

- **Includere numeri nei temi:** Quando si attivano i numeri (che identificano un tema) vengono inclusi durante la generazione di temi. 

- **Modificare dinamicamente il numero massimo di temi:** In determinate situazioni, potrebbe non essere disponibile un numero sufficiente di documenti in un set di riesame per ottenere i numeri di temi desiderati. Quando questa impostazione è abilitata, Advanced eDiscovery regola in modo dinamico il numero massimo di temi anziché tentare di applicare il numero massimo di temi.

## <a name="review-set-query"></a>Verifica set di query

Se si seleziona la casella **di controllo crea automaticamente una richiesta di ricerca salvata dopo l'analisi** , la query Advanced eDiscovery autogenerates Review set viene chiamata per la **revisione.** 

![La query per la revisione generata automaticamente](media/AeDForReviewQuery.png)

Questa query sostanzialmente filtra gli elementi duplicati dal set di revisione. In questo modo è possibile esaminare gli elementi univoci nel set di revisione. La query viene creata solo quando si esegue analisi per un set di revisione nel caso. Per ulteriori informazioni, vedere [query sui dati di un](review-set-search.md)set di revisione.

## <a name="ignore-text"></a>Ignora testo

Vi sono situazioni in cui un determinato testo diminuirà la qualità dell'analisi, ad esempio le dichiarazioni di non responsabilità lunghe che vengono aggiunte ai messaggi di posta elettronica indipendentemente dal contenuto del messaggio di posta elettronica. Se si conosce il testo che deve essere ignorato, è possibile escluderlo da analisi specificando la stringa di testo e la funzionalità di analisi (quasi duplicati, Threading di posta elettronica, temi e pertinenza) in base alla quale il testo dovrebbe essere escluso. Anche l'utilizzo di espressioni regolari (RegEx) come testo ignorato è supportato. 

## <a name="optical-character-recognition-ocr"></a>Riconoscimento ottico caratteri (OCR)

Quando questa impostazione è attivata, l'OCR verrà eseguito sui file di immagine aggiunti ai set di revisione in modo che il testo dell'immagine possa essere esaminato, cercato, taggato e analizzato. È possibile visualizzare il testo estratto nel Visualizzatore di testo del file di immagine selezionato nel set di revisione. Per ulteriori informazioni, vedere:

- [Aggiungere i risultati della ricerca a un insieme da rivedere](add-data-to-review-set.md#optical-character-recognition)

- [Tipi di file di immagine supportati](supported-filetypes-ediscovery20.md#image)
