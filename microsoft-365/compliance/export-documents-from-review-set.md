---
title: Esportare i documenti da un insieme da rivedere
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
description: Informazioni su come selezionare ed esportare il contenuto da un set di revisione per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285362"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Esportare documenti da un set di revisione in Advanced eDiscovery

Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download. Lo strumento di esportazione fornisce una pagina di configurazione con le seguenti impostazioni:

![Opzioni per l'esportazione di elementi da un set di Revisione](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Opzioni di esportazione

- Nome esportazione: nome del processo di esportazione.

- Descrizione: campo di testo libero che consente di aggiungere una descrizione.

- Esportare questi documenti:

  - Solo documenti selezionati: consente di esportare solo i documenti attualmente selezionati.
  
  - Tutti i documenti nel set di revisione-Esporta tutti i documenti nel set di Revisione

- Metadati
  
  - Load file: questo file contiene i metadati per ogni file. Per ulteriori informazioni sui campi inclusi, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) . Questo file può in genere essere ingerito da strumenti di eDiscovery di terze parti.
  
  - Tag: quando vengono selezionati, le informazioni di tagging verranno incluse nel file di caricamento.

- Contenuto
  
  - File nativi: selezionare questa casella di controllo per includere i file nativi.
  
  - Opzioni di conversazione
    
    - File di conversazione: esportare i messaggi di chat ricostruiti. Questo formato presenta conversazioni in un modulo simile a quello che gli utenti vedono nell'applicazione nativa.
    
    - Messaggi di chat individuali: esportare i file di conversazione originali come archiviati in Microsoft 365.

- Opzioni

  - File di testo-includere le versioni di testo estratte dei file nativi.
  
  - Sostituisci nativi ritirati con i file PDF convertiti-se durante la revisione sono stati generati i documenti di modifica, questi file sono disponibili per l'esportazione. È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le redazioni effettive.

- Opzioni di output (il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un account di archiviazione di Azure. Le prime due opzioni consentono il download diretto.
  
  - File allentati e PST (la posta elettronica viene aggiunta a PST quando possibile): i file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.  Per ulteriori informazioni, vedere la sezione [file Loose and PST Export Structure](#loose-files-and-pst-export-structure) .
  
  - Struttura di directory condensata-i file vengono esportati e inclusi nel download.
  
  - Struttura di directory ridotta esportata nell'account di archiviazione di Azure-i file vengono esportati nell'accouunt di archiviazione di Azure dell'organizzazione.

## <a name="loose-files-and-pst-export-structure"></a>File Loose e struttura di esportazione PST

Se si seleziona questa opzione di esportazione, il contenuto esportato è organizzato nella struttura seguente:

- Cartella radice – questa cartella denominata ExportName.zip
  
  - Export_load_file.csv-file di metadati.
  
  - Summary.csv-un file di riepilogo contenente anche le statistiche di esportazione.
  
  - Exchange: questa cartella contiene tutto il contenuto di Exchange nel formato di file nativo. Se è stata selezionata l'opzione **Sostituisci nativi con file PDF convertiti** , i file nativi vengono sostituiti con documenti PDF ritirati.
  
  - SharePoint = questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo. Se è stata selezionata l'opzione **Sostituisci nativi con file PDF convertiti** , i file nativi vengono sostituiti con documenti PDF ritirati.

## <a name="condensed-directory-structure"></a>Struttura di directory ridotta

- Cartella radice-questa cartella è denominata ExportName.zip
  
  - Export_load_file.csv-file di metadati.
  
  - Summary.txt-un file di riepilogo contenente anche le statistiche di esportazione.
  
  - Input_or_native_files: questa cartella contiene tutti i file nativi che sono stati esportati. Se si esportano file PDF redatti, non vengono inseriti nei file PST. Al contrario, vengono aggiunti a una cartella separata.
  
  - Error_files-questa cartella contiene i file di errore seguenti, se sono inclusi nell'esportazione:
    
    - ExtractionError. File CSV che contiene i metadati disponibili dei file che non sono stati estratti correttamente dai file padre.
    
    - ProcessingError – questo file contiene un elenco di documenti con errori di elaborazione. Questo contenuto è a livello di elemento, ovvero se un allegato ha generato un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato è incluso in questa cartella.
  
  - Extracted_text_files: questa cartella contiene tutti i file di testo estratti che sono stati generati durante l'elaborazione.

> [!NOTE]
> I processi di esportazione vengono mantenuti per tutta la durata del caso e possono essere scaricati purché il caso non venga eliminato.
