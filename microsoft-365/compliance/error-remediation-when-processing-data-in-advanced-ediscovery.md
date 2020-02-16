---
title: Correzione degli errori durante l'elaborazione dei dati
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
ms.openlocfilehash: 5421ba811e401bdd191aee0ddbff21a1286dc9fe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074573"
---
# <a name="error-remediation-when-processing-data"></a>Correzione degli errori durante l'elaborazione dei dati

La correzione degli errori consente agli amministratori di eDiscovery di correggere i problemi relativi ai dati che impediscono al eDiscovery avanzato di elaborare correttamente il contenuto. Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati. Se si utilizza la correzione degli errori, gli amministratori di eDiscovery possono scaricare i file con tale errore, rimuovere la protezione tramite password e quindi caricare i file corretti.

Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi avanzati di eDiscovery.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creare una sessione di correzione degli errori per rimediare i file con errore di elaborazione

>[!NOTE]
>Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni** dal menu a discesa **Visualizza** .

1. Nella scheda **elaborazione** del caso Advanced eDiscovery, selezionare **errori** dal menu a discesa **Visualizza** , quindi selezionare un set di revisione o l'intero caso nel menu a discesa **ambito** . In questa sezione vengono visualizzati tutti gli errori provenienti dal caso o dall'errore di un set di revisione specifico.

   ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.  Nell'esempio seguente, viene rimediato un file protetto da password.

3. Fare clic su **nuova correzione degli errori**.

    Il flusso di lavoro di correzione dei problemi inizia con una fase di preparazione in cui i file con errori vengono copiati in una posizione di archiviazione di Azure fornita da Microsoft in modo da poterli scaricare nel computer locale per correggere i problemi.

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Al termine della preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.

    ![Scaricare file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Per scaricare i file, specificare il **percorso di destinazione per il download**. Si tratta di un percorso della cartella padre nel computer locale in cui verrà scaricato il file.  Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso. Se lo si desidera, è possibile modificare questo percorso. In caso contrario, si consiglia di utilizzare un percorso di file locale per ottenere prestazioni ottimali. Non utilizzare un percorso di rete remoto. Ad esempio, è possibile utilizzare il percorso **C:\Remediation**. 

   Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del parametro **/dest** ).

6. Copiare il comando predefinito facendo clic su **copia negli Appunti**. Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **invio**.  

    ![Preparare la correzione per gli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > È necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando disponibile nella pagina **Scarica file** . È inoltre necessario utilizzare AzCopy v 8.1 per caricare i file nel passaggio 10. Per installare questa versione di AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

    I file selezionati vengono scaricati nel percorso specificato nel passaggio 5. Nella cartella padre (ad esempio, **C:\Remediation**), viene creata automaticamente la struttura di sottocartelle seguente:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - La *sottocartella 1* è denominata con l'ID del caso o del set di revisione, a seconda dell'ambito selezionato nel passaggio 1.

    - La *sottocartella 2* è denominata con l'ID file del file scaricato

    - Il file scaricato si trova nella *sottocartella 2* e viene denominato anche con l'ID file.

    Di seguito è riportato un esempio del percorso della cartella e del nome del file di errore creato quando gli elementi vengono scaricati nella cartella padre di **C:\Remediation** :

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Se si scaricano più file, ognuno di essi viene scaricato in una sottocartella denominata con l'ID del file.

    > [!IMPORTANT]
    > Quando si caricano i file nel passaggio 9 e nel passaggio 10, i file corretti devono avere lo stesso nome di file e trovarsi nella stessa struttura di sottocartelle. La sottocartella e i nomi di file vengono utilizzati per associare il file di correzione al file di errore originale. Se la struttura di cartelle o i nomi di file vengono modificati, verrà visualizzato il seguente `Cannot apply Error Remediation to the current Workingset`messaggio di errore:. Per evitare problemi, è consigliabile mantenere i file corretti nella stessa cartella padre e sottocartella.

7. Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato. Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare. Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.

8. Tornare a Advanced eDiscovery e la procedura guidata per la correzione degli errori, quindi fare clic su **Avanti: carica file**.  Si passa alla pagina successiva in cui è ora possibile caricare i file.

    ![Caricare file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specificare la cartella padre in cui si trovano i file corretti nella casella di testo **percorso alla posizione dei file** . Anche in questo caso, la cartella padre deve avere la stessa struttura di sottocartelle creata quando sono stati scaricati i file.

    Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del parametro **/source** ).

10. Copiare il comando predefinito facendo clic su **copia negli Appunti**. Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **invio**. caricare i file.

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Dopo aver eseguito il comando AzCopy, fare clic su **Avanti: elabora file**.

    Al termine dell'elaborazione, è possibile passare a revisione set e visualizzare i file corretti. 

## <a name="remediating-errors-in-container-files"></a>Correzione degli errori nei file contenitore

Nei casi in cui il contenuto di un file contenitore (ad esempio un file con estensione zip) non può essere Estratto da Advanced eDiscovery, è possibile scaricare i contenitori e il contenuto viene espanso nella stessa cartella in cui risiede il contenitore originale. I file espansi verranno attribuiti al contenitore padre come se fosse stato originariamente espanso da Advanced eDiscovery. Il processo funziona come descritto sopra, tranne che per il caricamento di un singolo file come file di sostituzione.  Quando si caricano file corretti, non includere il file del contenitore originale.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Correzione degli errori mediante il caricamento del testo Estratto

A volte non è possibile correggere un file in un formato nativo che può essere interpretato da Advanced eDiscovery. Tuttavia, è possibile sostituire il file originale con un file di testo contenente il testo originale del file nativo (in un processo denominato *sovrapposizione di testo*). A tale scopo, seguire i passaggi descritti in questo articolo, ma anziché correggere il file originale nel formato nativo, è necessario creare un file di testo contenente il testo estratto dal file originale e quindi caricare il file di testo utilizzando il nome file originale. accodato con un suffisso. txt. Ad esempio, è possibile scaricare un file durante la correzione degli errori con il nome file 335850cc-6602-4af0-acfa-1d14d9128ca2. ABC. È possibile aprire il file nell'applicazione nativa, copiare il testo e incollarlo in un nuovo file denominato 335850cc-6602-4af0-acfa-1d14d9128ca2. ABC. txt. Quando si esegue questa operazione, assicurarsi di rimuovere il file originale nel formato nativo dal percorso dei file corretti nel computer locale prima di caricare il file di testo di cui è stata eseguita la correzione in Advanced eDiscovery.

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

Per una definizione di tutti i campi dei metadati in Advanced eDiscovery, vedere [Document Metadata Fields](document-metadata-fields.md).
