---
title: Correzione degli errori durante l'elaborazione dei dati per un'indagine
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
description: Informazioni su come utilizzare la correzione degli errori per correggere i problemi relativi ai dati in indagini sui dati (Preview) che potrebbero impedire l'elaborazione corretta del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c833ce9ae93f5395e06ee3dbde54ff4a8d5d4a00
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035118"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>Correzione degli errori durante l'elaborazione dei dati per un'indagine

La correzione degli errori consente ai ricercatori la possibilità di correggere i problemi relativi ai dati che impediscono l'elaborazione corretta del contenuto da parte dell'analisi dei dati (Preview). Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati. Se si utilizza la correzione degli errori, gli investigatori possono scaricare i file con tale errore, rimuovere la protezione tramite password e caricare i file corretti.

Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi di analisi dei dati (Preview).

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creazione di una sessione di correzione degli errori per la correzione dei file con errore di elaborazione

>[!NOTE]
>Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni di errore** nel menu a discesa **Visualizza** .

1. Nella scheda **elaborazione** di un'analisi dei dati, selezionare **errori** dal menu a discesa **Visualizza** .

2. Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.  Nell'esempio seguente, viene rimediato un file protetto da password.

3. Fare clic su **+ nuova correzione degli errori**.

    ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    La sessione di correzione dei problemi inizia con una fase di preparazione in cui i file con errori vengono copiati in una posizione sicura di Azure in modo da poterli scaricare.

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Dopo aver completato la preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.

    ![Scaricare file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Per scaricare i file, specificare il **percorso di destinazione per il download**. Si tratta di un percorso del computer locale in cui deve essere scaricato il file.  Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso. Questo può essere modificato in base alle esigenze.

    >[!NOTE]
    >È consigliabile utilizzare un percorso di file locale anziché un percorso di rete remoto per ottenere prestazioni ottimali.

    > [!NOTE]
    > Se non è stato installato AzCopy, è possibile installarlo da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

6. Copiare il comando predefinito facendo clic su **copia negli Appunti**. Avviare un prompt dei comandi di Windows, incollare il comando e quindi premere **invio**.  

    I file verranno scaricati.

    ![Preparazione della correzione degli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > In caso di problemi con questo comando, vedere [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

7. Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato. Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare. Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.
    
   > [!NOTE]
    > È importante mantenere la struttura di directory e i nomi di file dei file corretti. I nomi di percorso dei file e delle cartelle scaricati consentono di associare i file corretti ai file originali.  Se la struttura di directory o i nomi di file vengono modificati, verrà visualizzato il seguente `Cannot apply Error Remediation to the current Evidenceset`messaggio di errore:.

8. A questo punto, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: carica file**.  In questo modo si passerà al passaggio successivo, in cui è ora possibile caricare i file.

    ![Caricare file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specificare il percorso dei file corretti nella casella di testo **percorso alla posizione dei file** e quindi fare clic su **copia negli Appunti**.

10. Incollare il comando in un prompt dei comandi di Windows e premere **invio** per caricare i file.

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Infine, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: elabora file**.

12. Quando l'elaborazione è completata.  È possibile tornare al working set e vedere il file correttivo.

## <a name="what-happens-when-files-are-remediated"></a>Cosa accade quando i file vengono corretti

Quando i file corretti vengono caricati, vengono conservati i metadati originali, ad eccezione dei campi seguenti: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Testo
- WordCount
- WorkingsetId

Per una definizione di tutti i campi dei metadati del documento in indagini sui dati (Preview), vedere [Document Metadata Fields](document-metadata-fields.md).
