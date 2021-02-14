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
description: Informazioni su come selezionare ed esportare il contenuto da un insieme di recensioni per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285362"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Esportare documenti da un insieme da rivedere in Advanced eDiscovery

L'esportazione consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download. Lo strumento di esportazione fornisce una pagina di configurazione con le impostazioni seguenti:

![Opzioni per l'esportazione di elementi da un insieme da rivedere](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Opzioni di esportazione

- Nome esportazione: Nome del processo di esportazione.

- Descrizione: campo di testo libero per aggiungere una descrizione.

- Esportare questi documenti:

  - Solo documenti selezionati: esporta solo i documenti attualmente selezionati.
  
  - Tutti i documenti nell'insieme da rivedere - Esporta tutti i documenti nel set di revisioni

- Metadati
  
  - Carica file: questo file contiene i metadati per ogni file. Per ulteriori informazioni sui campi inclusi, vedere Campi dei metadati del documento [in Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md) Questo file può in genere essere ingerito da strumenti di eDiscovery di terze parti.
  
  - Tag: se selezionata, le informazioni di tagging verranno incluse nel file di caricamento.

- Contenuto
  
  - File nativi: selezionare questa casella di controllo per includere i file nativi.
  
  - Opzioni di conversazione
    
    - File di conversazione - Esportare i messaggi di chat ricostruiti. Questo formato presenta le conversazioni in un formato simile a quello visualizzato dagli utenti nell'applicazione nativa.
    
    - Singoli messaggi di chat: esportare i file di conversazione originali così come sono archiviati in Microsoft 365.

- Opzioni

  - File di testo: includi versioni di testo estratte di file nativi.
  
  - Sostituisci i file nativi con PDF convertiti: se i file PDF redatti vengono generati durante la revisione, questi file sono disponibili per l'esportazione. È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le azioni effettive.

- Opzioni di output (il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un account di archiviazione di Azure. Le prime due opzioni consentono il download diretto.
  
  - File e file PST (la posta elettronica viene aggiunta ai file PST quando possibile) - I file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.  Per ulteriori informazioni, vedere la sezione [Relativa ai file con estensione loose e alla struttura di esportazione PST.](#loose-files-and-pst-export-structure)
  
  - Struttura di directory ridotto: i file vengono esportati e inclusi nel download.
  
  - Struttura di directory ridotto esportata nell'account di archiviazione di Azure: i file vengono esportati nell'archivio di Azure dell'organizzazione.

## <a name="loose-files-and-pst-export-structure"></a>File con estensione loose e struttura di esportazione PST

Se si seleziona questa opzione di esportazione, il contenuto esportato viene organizzato nella struttura seguente:

- Cartella radice- Cartella denominata ExportName.zip
  
  - Export_load_file.csv - File di metadati.
  
  - Summary.csv - Un file di riepilogo che contiene anche le statistiche di esportazione.
  
  - Exchange: questa cartella contiene tutto il contenuto di Exchange in formato di file nativo. I file nativi vengono sostituiti con PDF redatti se hai selezionato l'opzione Sostituisci i file nativi con PDF **convertiti.**
  
  - SharePoint = Questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo. I file nativi vengono sostituiti con PDF redatti se hai selezionato l'opzione Sostituisci i file nativi con PDF **convertiti.**

## <a name="condensed-directory-structure"></a>Struttura di directory compressa

- Cartella radice - Questa cartella è denominata ExportName.zip
  
  - Export_load_file.csv - File di metadati.
  
  - Summary.txt - Un file di riepilogo che contiene anche le statistiche di esportazione.
  
  - Input_or_native_files- Questa cartella contiene tutti i file nativi esportati. Se si esportano file PDF redatti, questi non vengono inseriti nei file PST. Vengono invece aggiunti a una cartella separata.
  
  - Error_files- Questa cartella contiene i file di errore seguenti, se inclusi nell'esportazione:
    
    - ExtractionError. Un file CSV che contiene i metadati disponibili dei file che non sono stati estratti correttamente dai file padre.
    
    - ProcessingError: questo file contiene un elenco di documenti con errori di elaborazione. Questo contenuto è a livello di elemento, ovvero se un allegato ha generato un errore di elaborazione, il messaggio di posta elettronica contenente l'allegato viene incluso in questa cartella.
  
  - Extracted_text_files- Questa cartella contiene tutti i file di testo estratti che sono stati generati durante l'elaborazione.

> [!NOTE]
> I processi di esportazione vengono conservati per tutta la durata del caso e possono essere scaricati purché il caso non sia stato eliminato.
