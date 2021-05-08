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
description: Informazioni su come selezionare ed esportare contenuto da un set Advanced eDiscovery per presentazioni o recensioni esterne.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244362"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Esportare documenti da un set di revisioni in Advanced eDiscovery

L'esportazione consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download quando si esporta un documento da un set di revisioni in Advanced eDiscovery.

Per esportare documenti da un set di revisioni:

1. Nel centro Microsoft 365 conformità aprire il caso Advanced eDiscovery, selezionare la scheda Review **sets** e quindi selezionare il set di recensioni che si desidera esportare.

2. Nel set di revisioni fare clic **su Azione**  >  **Esporta.**

   Lo strumento di esportazione visualizza la pagina a comparsa con le impostazioni per configurare l'esportazione. Alcune opzioni sono selezionate per impostazione predefinita, ma è possibile modificarle. Per le descrizioni delle opzioni di esportazione che è possibile configurare, vedere la sezione seguente.

   ![Opzioni di configurazione per l'esportazione di elementi da un set di revisione](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Dopo aver configurato l'esportazione, fare clic **su Esporta** per avviare il processo di esportazione. A seconda dell'opzione selezionata nella sezione **Opzioni** di output, è possibile accedere ai file di esportazione tramite download diretto o nell'account Archiviazione di Azure dell'organizzazione.

> [!NOTE]
> I processi di esportazione vengono conservati per tutta la durata del caso. Tuttavia, è necessario scaricare il contenuto da un processo di esportazione entro 30 giorni dal completamento del processo di esportazione.

## <a name="export-options"></a>Opzioni di esportazione

Utilizzare le opzioni seguenti per configurare l'esportazione. Non tutte le opzioni sono consentite per alcune opzioni di output, in particolare l'esportazione di file di testo e PDF redatti non sono consentite durante l'esportazione nel formato PST.

- **Nome esportazione**: Nome del processo di esportazione. Verrà usato per assegnare un nome ai file ZIP che verranno scaricati.

- **Descrizione**: campo a testo libero che consente di aggiungere una descrizione.

- **Esportare questi documenti**

  - Solo documenti selezionati: questa opzione esporta solo i documenti attualmente selezionati. Questa opzione è disponibile solo quando gli elementi sono selezionati in un set di revisioni.
  - Tutti i documenti filtrati: questa opzione consente di esportare i documenti in un filtro attivo. Questa opzione è disponibile solo quando viene applicato un filtro al set di revisioni.
  - Tutti i documenti nel set di revisioni: questa opzione consente di esportare tutti i documenti nel set di revisioni.

- **Opzioni di** output: il contenuto esportato è disponibile per il download direttamente tramite un Web browser o può essere inviato a un Archiviazione di Azure account. Le prime due opzioni consentono il download diretto.
  
  - Solo report: vengono creati solo il file di riepilogo e di caricamento.
  - File e file PST (la posta elettronica viene aggiunta ai file PST quando possibile): i file vengono esportati in un formato simile alla struttura di directory originale visualizzata dagli utenti nelle applicazioni native.  Per ulteriori informazioni, vedere la [sezione Loose files and PST export structure.](#loose-files-and-pst-export-structure)
  - Struttura di directory compressa: i file vengono esportati e inclusi nel download.
  - Struttura di directory compressa esportata nell'account Archiviazione di Azure: i file vengono esportati nell'account Archiviazione di Azure dell'organizzazione. Per questa opzione, devi fornire l'URL del contenitore nel tuo account Archiviazione di Azure in cui esportare i file. Devi anche fornire il token di firma di accesso condiviso (SAS) per il tuo account Archiviazione di Azure account. Per ulteriori informazioni, vedere [Export documents in a review set to an Archiviazione di Azure account](download-export-jobs.md).

- **Includi**
  - Tag: se selezionata, le informazioni di tagging vengono incluse nel file di caricamento.
  - File di testo: questa opzione include le versioni di testo estratte dei file nativi nell'esportazione.
  - Sostituire i nativi con PDF convertiti: se i file PDF redatti vengono generati durante la revisione, questi file sono disponibili per l'esportazione. È possibile scegliere di esportare solo i file nativi che sono stati redatti (non selezionando questa opzione) oppure è possibile selezionare questa opzione per esportare i file PDF che contengono le azioni effettive.

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a>Nelle sezioni seguenti viene descritta la struttura delle cartelle per i file con estensione loose e le opzioni della struttura di directory compressa

Le esportazioni vengono partizionate in file ZIP con una dimensione massima di contenuto non compresso di 75 GB. Se le dimensioni dell'esportazione sono inferiori a 75 GB, l'esportazione sarà costituita da un file di riepilogo e da un singolo file ZIP. Per le esportazioni che superano i 75 GB di dati non compressi, verranno creati più file ZIP. Una volta scaricati, i file ZIP possono essere decompressi in un'unica posizione per ricreare l'esportazione completa.

### <a name="loose-files-and-pst-export-structure"></a>File con estensione loose e struttura di esportazione PST

Se si seleziona questa opzione di esportazione, il contenuto esportato viene organizzato nella struttura seguente:

- Summary.csv: include un riepilogo del contenuto esportato dal set di recensioni
- Cartella radice: questa cartella denominata [Nome esportazione] x di z.zip e verrà ripetuta per ogni partizione del file ZIP.
  - Export_load_file_x di z.csv: il file di metadati.
  - Avvisi ed errori x di z.csv: questo file include informazioni sugli errori rilevati durante il tentativo di esportazione dal set di revisione.
  - Exchange: questa cartella contiene tutto il contenuto Exchange archiviati nei file PST. I file PDF redatti non possono essere inclusi con questa opzione. Se nel set di revisioni è selezionato un allegato, il messaggio di posta elettronica padre verrà esportato con l'allegato allegato.
  - SharePoint: questa cartella contiene tutto il contenuto nativo di SharePoint in un formato di file nativo. I file PDF redatti non possono essere inclusi con questa opzione.

### <a name="condensed-directory-structure"></a>Struttura di directory compressa

- Summary.csv: include un riepilogo del contenuto esportato dal set di recensioni
- Cartella radice: questa cartella denominata [Nome esportazione] x di z.zip e verrà ripetuta per ogni partizione del file ZIP.
  - Export_load_file_x di z.csv: il file di metadati e include anche il percorso di ogni file archiviato nel file ZIP.
  - Avvisi ed errori x di z.csv: questo file include informazioni sugli errori rilevati durante il tentativo di esportazione dal set di revisione.
  - NativeFiles: questa cartella contiene tutti i file nativi esportati. I file nativi vengono sostituiti con PDF redatti se è stata selezionata l'opzione Sostituisci i nativi con i *PDF convertiti.*
  - Error_files: questa cartella contiene file con errore di estrazione o di altro tipo. I file verranno inseriti in cartelle separate, ExtractionError o ProcessingError. Questi file sono elencati nel file di caricamento.
  - Extracted_text_files: questa cartella contiene tutti i file di testo estratti generati durante l'elaborazione.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Struttura di directory compressa esportata nell'Archiviazione di Azure account

Questa opzione utilizza la stessa struttura generale della struttura di *directory* condensata, tuttavia il contenuto non viene compresso e i dati vengono salvati nel Archiviazione di Azure account. Questa opzione viene in genere utilizzata quando si utilizza un provider di eDiscovery di terze parti. Per informazioni dettagliate su come utilizzare questa opzione, vedere [Export documents in a review set to an Archiviazione di Azure account](download-export-jobs.md).
