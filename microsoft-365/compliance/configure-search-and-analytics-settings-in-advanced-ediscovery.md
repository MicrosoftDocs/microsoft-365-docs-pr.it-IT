---
title: Configurare le impostazioni di ricerca e analisi - Advanced eDiscovery
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
ms.custom: seo-marvel-mar2020
description: Configurare Advanced eDiscovery che si applicano a tutti i set di revisione in un caso. Sono incluse le impostazioni per l'analisi e il riconoscimento ottico dei caratteri.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751303"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Configurare le impostazioni di ricerca e analisi in Advanced eDiscovery

È possibile configurare le impostazioni per ogni Advanced eDiscovery caso per controllare le funzionalità seguenti.

- Documenti simili e threading posta elettronica

- Temi

- Query dell'insieme da rivedere automatica

- Testo da ignorare

- Riconoscimento ottico dei caratteri

Per configurare le impostazioni di ricerca e analisi per un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso.

2. Nella scheda **Impostazioni** in **Ricerca e analisi**, fare clic su **Seleziona**.

   Viene visualizzata la pagina delle impostazioni del caso. Queste impostazioni vengono applicate a tutti i set di revisione in un caso.

   ![Configurare le impostazioni di analisi e ricerca per un Advanced eDiscovery caso](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Documenti simili e threading posta elettronica

In questa sezione è possibile impostare i parametri per il rilevamento duplicati, il rilevamento quasi duplicato e il threading della posta elettronica. Per ulteriori informazioni, vedere [Rilevamento quasi duplicato](near-duplicate-detection-in-advanced-ediscovery.md) e [Threading della posta elettronica.](email-threading-in-advanced-ediscovery.md)

- **Threading near duplicates/email:** Se attivato, il rilevamento duplicati, il rilevamento quasi duplicato e il threading della posta elettronica vengono inclusi come parte del flusso di lavoro quando si esegue l'analisi dei dati in un set di revisione.

- **Soglia di somiglianza tra documenti e messaggi di posta elettronica:** Se il livello di somiglianza per due documenti è superiore alla soglia, entrambi i documenti vengono inseriti nello stesso set di duplicati quasi duplicato.

- **Numero minimo/massimo di parole:** Queste impostazioni specificano che quasi i duplicati e l'analisi del threading della posta elettronica vengono eseguite solo su documenti con almeno il numero minimo di parole e al massimo il numero massimo di parole.

## <a name="themes"></a>Temi

In questa sezione è possibile impostare i parametri per i temi. Per ulteriori informazioni, vedere [Temi](themes-in-advanced-ediscovery.md).

- **Temi:** Se attivato, il clustering dei temi viene eseguito come parte del flusso di lavoro quando si esegue l'analisi dei dati in un set di revisione.

- **Numero massimo di temi:** Specifica il numero massimo di temi che possono essere generati quando si esegue l'analisi dei dati in un set di revisioni.

- **Includi numeri nei temi:** Quando è attivata, i numeri (che identificano un tema) vengono inclusi durante la generazione di temi. 

- **Regolare dinamicamente il numero massimo di temi:** In alcune situazioni, potrebbe non essere disponibile un numero sufficiente di documenti in un set di revisioni per produrre il numero desiderato di temi. Quando questa impostazione è abilitata, Advanced eDiscovery modifica il numero massimo di temi dinamicamente, invece di tentare di applicare il numero massimo di temi.

## <a name="review-set-query"></a>Query dell'insieme da rivedere

Se si seleziona la **casella** di controllo Crea automaticamente una ricerca salvata per revisione dopo l'analisi, Advanced eDiscovery automaticamente la query del set di revisione denominata **Per revisione.** 

![Query rigenerata automaticamente per la revisione](../media/AeDForReviewQuery.png)

Questa query filtra fondamentalmente gli elementi duplicati dal set di revisioni. In questo modo è possibile esaminare gli elementi univoci nel set di revisioni. Questa query viene creata solo quando si eseguono analisi per un insieme da rivedere nel caso. Per ulteriori informazioni sulle query di set di revisione, vedere [Query the data in a review set](review-set-search.md).

## <a name="ignore-text"></a>Testo da ignorare

Esistono situazioni in cui determinati testi diminuiscono la qualità dell'analisi, ad esempio dichiarazioni di non responsabilità lunghe che vengono aggiunte ai messaggi di posta elettronica indipendentemente dal contenuto del messaggio di posta elettronica. È possibile escludere la parte di testo da ignorare dall'analisi specificando la stringa di testo e la funzionalità di analisi (Documenti simili, Threading posta elettronica, Temi e Rilevanza) per cui escludere il testo. È inoltre supportato l'utilizzo di espressioni regolari (RegEx) come testo ignorato. 

## <a name="optical-character-recognition-ocr"></a>Riconoscimento ottico dei caratteri (OCR)

Quando questa impostazione è attivata, l'elaborazione OCR verrà eseguita sui file di immagine. L'elaborazione OCR viene eseguita nelle situazioni seguenti:

- Quando i custodi e le origini dati [non depositario](non-custodial-data-sources.md) vengono aggiunti a un caso. L'elaborazione OCR viene eseguita durante il processo di indicizzazione avanzata. Ciò significa che il testo nei file di immagine che corrisponde ai criteri di ricerca verrà restituito in una ricerca di raccolta.

- Quando il contenuto di altre origini dati (che non sono associate a un responsabile e che vengono aggiunti al caso in un'origine dati non depositale) viene aggiunto a un set di revisione.

Dopo l'aggiunta dei dati a un set di recensioni, il testo dell'immagine può essere esaminato, cercato, taggato e analizzato. È possibile visualizzare il testo estratto nel visualizzatore di testo del file di immagine selezionato nel set di revisioni. Per altre informazioni, vedere:

- [Indicizzazione avanzata dei dati dei responsabili](indexing-custodian-data.md)

- [Aggiungere i risultati della ricerca a un insieme da rivedere](add-data-to-review-set.md#optical-character-recognition)

- [Tipi di file di immagine supportati](supported-filetypes-ediscovery20.md#image)
