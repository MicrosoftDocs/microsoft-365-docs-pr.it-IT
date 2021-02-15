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
description: Configurare le impostazioni di Advanced eDiscovery che si applicano a tutte le recensioni impostate in un caso. Sono incluse le impostazioni per l'analisi e il riconoscimento ottico dei caratteri.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751303"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Configurare le impostazioni di ricerca e analisi in Advanced eDiscovery

È possibile configurare le impostazioni per ogni caso di Advanced eDiscovery per controllare le funzionalità seguenti.

- Quasi duplicati e threading della posta elettronica

- Temi

- Query del set di revisione rigenerata automaticamente

- Ignora testo

- Riconoscimento ottico dei caratteri

Per configurare le impostazioni di ricerca e analisi per un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso.

2. Nella scheda **Impostazioni,** in Analisi & **ricerca,** fare clic su **Seleziona.**

   Viene visualizzata la pagina delle impostazioni del caso. Queste impostazioni vengono applicate a tutti i set di recensioni in un caso.

   ![Configurare le impostazioni di analisi e ricerca per un caso di Advanced eDiscovery](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Quasi duplicati e threading della posta elettronica

In questa sezione è possibile impostare i parametri per il rilevamento dei duplicati, il rilevamento quasi duplicato e il threading della posta elettronica. Per ulteriori informazioni, vedere [Rilevamento quasi duplicati e](near-duplicate-detection-in-advanced-ediscovery.md) Threading della posta [elettronica.](email-threading-in-advanced-ediscovery.md)

- **Threading near duplicates/email:** Se attivato, il rilevamento dei duplicati, il rilevamento quasi duplicato e il threading della posta elettronica vengono inclusi come parte del flusso di lavoro quando si esegue l'analisi dei dati in un insieme da rivedere.

- **Soglia di similarità di documenti e messaggi di posta elettronica:** Se il livello di similarità per due documenti è superiore alla soglia, entrambi i documenti vengono inseriti nello stesso set di duplicati quasi duplicati.

- **Numero minimo/massimo di parole:** Queste impostazioni specificano che quasi i duplicati e l'analisi del threading della posta elettronica vengono eseguite solo su documenti con almeno il numero minimo di parole e al massimo il numero massimo di parole.

## <a name="themes"></a>Temi

In questa sezione è possibile impostare i parametri per i temi. Per ulteriori informazioni, vedere [Temi.](themes-in-advanced-ediscovery.md)

- **Temi:** Se attivato, il clustering dei temi viene eseguito come parte del flusso di lavoro quando si esegue l'analisi dei dati in un insieme da rivedere.

- **Numero massimo di temi:** Specifica il numero massimo di temi che possono essere generati quando si esegue l'analisi dei dati in un insieme da rivedere.

- **Includi numeri nei temi:** Quando è attivata, i numeri (che identificano un tema) vengono inclusi durante la generazione dei temi. 

- **Regolare il numero massimo di temi in modo dinamico:** In alcune situazioni potrebbe non essere disponibile un numero sufficiente di documenti in un insieme da rivedere per produrre il numero desiderato di temi. Quando questa impostazione è abilitata, Advanced eDiscovery regola il numero massimo di temi in modo dinamico anziché tentare di applicare il numero massimo di temi.

## <a name="review-set-query"></a>Esaminare la query impostata

Se si seleziona la **casella** di controllo Crea automaticamente una ricerca salvata per revisione dopo l'analisi, Advanced eDiscovery genera automaticamente la query del set di revisione denominata **Per revisione.** 

![Query rigenerata automaticamente per la revisione](../media/AeDForReviewQuery.png)

Questa query filtra fondamentalmente gli elementi duplicati dal set di recensioni. In questo modo è possibile esaminare gli elementi univoci nel set di recensioni. Questa query viene creata solo quando si esegue l'analisi per un insieme di recensioni nel caso. Per ulteriori informazioni sulla revisione delle query impostate, vedere [Eseguire query sui dati in un insieme da rivedere.](review-set-search.md)

## <a name="ignore-text"></a>Ignora testo

Ci sono situazioni in cui un determinato testo riduce la qualità dell'analisi, ad esempio lunghe dichiarazioni di non responsabilità che vengono aggiunte ai messaggi di posta elettronica indipendentemente dal contenuto del messaggio di posta elettronica. Se si conosce il testo che deve essere ignorato, è possibile escluderlo dall'analisi specificando la stringa di testo e la funzionalità di analisi (near-duplicates, Email threading, Themes e Relevance) per cui deve essere escluso il testo. È inoltre supportato l'utilizzo di espressioni regolari (RegEx) come testo ignorato. 

## <a name="optical-character-recognition-ocr"></a>Riconoscimento ottico dei caratteri (OCR)

Quando questa impostazione è attivata, l'elaborazione OCR verrà eseguita sui file di immagine. L'elaborazione OCR viene eseguita nelle situazioni seguenti:

- Quando i responsabile e [le origini dati non](non-custodial-data-sources.md) dei depositario vengono aggiunti a un caso. L'elaborazione OCR viene eseguita durante il processo di indicizzazione avanzata. Ciò significa che il testo nei file di immagine che corrisponde ai criteri di ricerca verrà restituito in una ricerca di raccolta.

- Quando il contenuto di altre origini dati (che non sono associate a un responsabile e aggiunto al caso in un'origine dati non responsabile) viene aggiunto a un insieme da rivedere.

Dopo l'aggiunta dei dati a un insieme di recensioni, il testo dell'immagine può essere esaminato, cercato, contrassegnato e analizzato. Puoi visualizzare il testo estratto nel visualizzatore di testo del file di immagine selezionato nel set di recensioni. Per altre informazioni, vedere:

- [Indicizzazione avanzata dei dati dei responsabili](indexing-custodian-data.md)

- [Aggiungere i risultati della ricerca a un insieme da rivedere](add-data-to-review-set.md#optical-character-recognition)

- [Tipi di file di immagine supportati](supported-filetypes-ediscovery20.md#image)
