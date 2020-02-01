---
title: Scaricare i processi di esportazione da un'indagine sui dati
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
description: Installare e utilizzare Esplora archivi di Azure per scaricare i documenti esportati da Evidence in un'indagine di dati.
ms.openlocfilehash: a0e93d392e12ba548c8360a618abf909c89f2036
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595161"
---
# <a name="download-export-jobs"></a>Scaricare processi di esportazione

Quando si esportano documenti da Evidence in un'analisi dei dati, i documenti vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft o in un percorso di archiviazione di Azure gestito dall'organizzazione. Il tipo di percorso di archiviazione di Azure utilizzato dipende dall'opzione selezionata quando i documenti sono stati esportati. 

In questo articolo vengono fornite le istruzioni per l'utilizzo di Microsoft Azure Storage Explorer per la connessione a un percorso di archiviazione di Azure per cercare e scaricare i documenti esportati. Per ulteriori informazioni su Esplora archivi di Azure, vedere [Guida introduttiva: utilizzare Esplora risorse di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="step-1-install-the-azure-storage-explorer"></a>Passaggio 1: installare l'archivio di archiviazione di Azure

Il primo passaggio consiste nel scaricare e installare Esplora archivi di Azure. Per istruzioni, vedere [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842). È possibile utilizzare questo strumento per connettersi e scaricare i documenti esportati nel passaggio 3.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Passaggio 2: ottenere l'URL SAS dal processo di esportazione

Il passaggio successivo consiste nell'ottenere l'URL della firma di accesso condiviso (SAS) che viene generato quando è stato creato il processo di esportazione per [esportare i documenti da un set di revisione](export-documents-from-review-set.md). È possibile copiare l'URL SAS per i documenti caricati in una posizione di archiviazione di Azure fornita da Microsoft o un percorso di archiviazione di Azure gestito dall'organizzazione. In entrambi i casi, è possibile utilizzare l'URL SAS per connettersi al percorso di archiviazione di Azure nel passaggio 3.

1. Nella pagina **indagini dati** passare all'analisi e quindi fare clic sulla scheda **esportazioni** .

2. Nella scheda **esportazioni** fare clic sul processo di esportazione che si desidera scaricare.

3. Nella pagina riquadro a comparsa, in **percorsi**, copiare l'URL SAS visualizzato. Se necessario, è possibile salvarlo in un file in modo che sia possibile accedervi nel passaggio 3.
 
   ![Copiare l'URL SAS visualizzato in percorsi](media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>Passaggio 3: connettersi al percorso di archiviazione di Azure

Il passaggio finale consiste nell'utilizzare l'esploratore di archiviazione di Azure e l'URL SAS per connettersi al percorso di archiviazione di Azure e scaricare i documenti esportati in un computer locale.

1.  Aprire l'esploratore di archiviazione di Azure installato nel passaggio 1.

2. Fare clic sull'icona **Aggiungi account** . In alternativa, è possibile fare clic con il pulsante destro del mouse su **account di archiviazione**.

   ![Fare clic sull'icona Aggiungi account](media/AzureStorageConnect.png)

3.  Nella pagina **connessione ad Azure Storage** fare clic su **utilizza un URI di firma di accesso condiviso** e quindi fare clic su **Avanti**.

    ![Fare clic su Usa un URI per la firma di accesso condiviso e quindi fare clic su Avanti.](media/AzureStorageConnect2.png)

4.  Nella pagina **Allega con URI SAS** fare clic nella casella URI e quindi incollare l'URL SAS ottenuto nel passaggio 2. 

    ![Incollare l'URL SAS nella casella URI](media/AzureStorageConnect3.png)

    Si noti che una parte dell'URL SAS viene visualizzata nella casella **nome visualizzato** . Verrà utilizzato come nome visualizzato del contenitore creato negli **account di archiviazione** dopo la connessione al percorso di archiviazione. Questo nome è costituito dall'ID dell'analisi dei dati e da un identificatore univoco. È possibile mantenere il nome visualizzato predefinito o modificarlo. Se viene modificato, il nome visualizzato deve essere univoco.

5.  Fare clic su **Avanti**.

    Viene visualizzata la pagina **Riepilogo connessione** .
   
    ![Fare clic su Connetti nella pagina Riepilogo connessione per connettersi al percorso di archiviazione di Azure](media/AzureStorageConnect4.png)

6. Nella pagina **Riepilogo connessione** esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**. 

    Viene aperto il nodo **contenitori BLOB** (in **account** > di archiviazione **(contenitori associati)** \> . 

    ![Esportare processi nel nodo contenitori BLOB](media/AzureStorageConnect5.png)

    Contiene un contenitore denominato con il nome visualizzato del passaggio 4. Questo contenitore contiene una cartella per ogni processo di esportazione creato. Queste cartelle sono denominate con un ID che corrisponde all'ID del processo di esportazione. È possibile trovare questi ID di esportazione (e il nome dell'esportazione) in **informazioni di supporto** nella pagina a comparsa per ogni processo di **preparazione dei dati per l'esportazione** elencato nella scheda **processi** .

7. Fare doppio clic sulla cartella Export Job per aprirla.

   Viene visualizzato un elenco di cartelle e di report di esportazione.
   
    ![La cartella Export contiene i file esportati e i report di esportazione](media/AzureStorageConnect6.png)

   La cartella dei processi di esportazione contiene gli elementi seguenti. Gli elementi effettivi nella cartella Export sono determinati dalle opzioni di esportazione configurate al momento della creazione del processo di esportazione. Per ulteriori informazioni, vedere [esportare documenti da un set di revisione](export-documents-from-review-set.md).

    - Export_load_file. csv: questo file CSV è un report di esportazione dettagliata che contiene informazioni su ogni documento esportato. Il file è costituito da una colonna per ogni proprietà dei metadati di un documento. Per un elenco e una descrizione dei metadati inclusi in questo report, vedere la colonna **nome campo esportato** nella tabella nei [campi dei metadati del documento in Advanced eDiscovery](document-metadata-fields.md).
    
    - Summary. txt: un file di testo contenente un riepilogo dell'esportazione, tra cui le statistiche di esportazione.
    
    - Extracted_text_files: questa cartella contiene una versione del file di testo di ogni documento esportato.
     
    - NativeFiles: questa cartella contiene una versione di file nativa di ogni documento esportato.
    
    - Error_files: questa cartella include gli elementi seguenti quando il processo di esportazione contiene eventuali file di errore: 
        
      - ExtractionError. csv: questo file CSV contiene i metadati disponibili per i file che non sono stati estratti correttamente dall'elemento padre.
        
      - ProcessingError: questa cartella contiene documenti con errori di elaborazione. Questo contenuto è a livello di elemento, il che significa che se un allegato ha un errore di elaborazione, il documento che contiene l'allegato verrà incluso anche in questa cartella.
 
8. Per esportare tutto il contenuto nell'esportazione, selezionare la cartella Export, quindi fare clic su **download**.

9. Specificare il percorso in cui si desidera scaricare i file esportati e quindi fare clic su **Seleziona cartella**.

    Esplora archivi di Azure consente di avviare il processo di esportazione. Lo stato del download degli elementi esportati viene visualizzato nel riquadro **attività** . Quando il download è stato completato, viene visualizzato un messaggio.

    ![Quando il download è stato completato, viene visualizzato un messaggio](media/AzureStorageConnect8.png)

> [!NOTE]
> Invece di scaricare l'intero processo di esportazione, è possibile selezionare elementi specifici da scaricare. Invece di scaricare gli elementi, è possibile fare doppio clic su un elemento per visualizzarlo.

