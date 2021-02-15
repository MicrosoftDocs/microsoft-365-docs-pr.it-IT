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
description: Informazioni su come utilizzare la correzione degli errori per correggere i problemi relativi ai dati in Advanced eDiscovery che potrebbero impedire una corretta elaborazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750799"
---
# <a name="error-remediation-when-processing-data"></a>Correzione degli errori durante l'elaborazione dei dati

La correzione degli errori consente agli amministratori di eDiscovery di rettificare i problemi relativi ai dati che impediscono ad Advanced eDiscovery di elaborare correttamente il contenuto. Ad esempio, i file protetti da password non possono essere elaborati perché i file sono bloccati o crittografati. Utilizzando la correzione degli errori, gli amministratori di eDiscovery possono scaricare file con tali errori, rimuovere la password di protezione e quindi caricare i file corretti.

Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi di Advanced eDiscovery.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creare una sessione di correzione degli errori per correggere i file con errori di elaborazione

>[!NOTE]
>Se la correzione guidata degli errori viene chiusa in qualsiasi momento durante la procedura seguente, è possibile  tornare alla sessione  di correzione degli errori dalla scheda Elaborazione selezionando Correzioni nel menu a discesa Visualizza. 

1. Nella scheda **Elaborazione** nel caso di Advanced eDiscovery, selezionare **Errori** nel menu a discesa Visualizza  e quindi selezionare un insieme di recensioni o l'intero caso nel menu a discesa Ambito.  In questa sezione vengono visualizzati tutti gli errori relativi al caso o all'errore di un insieme da rivedere specifico.

   ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.  Nell'esempio seguente viene corretti un file protetto da password.

3. Fare **clic su Nuova correzione degli errori.**

    Il flusso di lavoro di correzione degli errori inizia con una fase di preparazione in cui i file con errori vengono copiati in un percorso di Archiviazione di Azure fornito da Microsoft in modo da poterli scaricare nel computer locale per la correzione.

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Al termine della preparazione, fare clic su **Avanti: Scaricare i file** per procedere con il download.

    ![Scaricare i file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Per scaricare i file, specificare il **percorso di destinazione per il download.** Si tratta di un percorso della cartella padre nel computer locale in cui verrà scaricato il file.  Il percorso predefinito, %USERPROFILE%\Downloads\errors, punta alla cartella dei download dell'utente connesso. Se lo si desidera, è possibile modificare questo percorso. Se si modifica questa impostazione, è consigliabile utilizzare un percorso di file locale per ottenere prestazioni ottimali. Non usare un percorso di rete remoto. Ad esempio, è possibile utilizzare il percorso **C:\Remediation.** 

   Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del **parametro /Dest).**

6. Copiare il comando predefinito facendo clic **su Copia negli Appunti.** Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **INVIO.**  

    ![Preparare la correzione degli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > È necessario utilizzare AzCopy v8.1 per utilizzare correttamente il comando fornito nella pagina **Download dei** file. È inoltre necessario utilizzare AzCopy v8.1 per caricare i file nel passaggio 10. Per installare questa versione di AzCopy, vedere Trasferire dati [con AzCopy v8.1 in Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) Se il comando AzCopy fornito non riesce, vedere [Risoluzione dei problemi di AzCopy in Advanced eDiscovery.](troubleshooting-azcopy.md)

    I file selezionati vengono scaricati nel percorso specificato nel passaggio 5. Nella cartella padre ,ad esempio **C:\Correzione,** viene creata automaticamente la struttura della sottocartella seguente:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *La sottocartella 1* viene denominata con l'ID del caso o del set di revisioni, a seconda dell'ambito selezionato nel passaggio 1.

    - *La sottocartella 2* è denominata con l'ID file del file scaricato

    - Il file scaricato si trova nella *sottocartella 2* ed è anche denominato con l'ID file.

    Ecco un esempio del percorso della cartella e del nome del file di errore creato quando gli elementi vengono scaricati nella cartella **padre C:\Remediation:**

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Se vengono scaricati più file, ognuno di essi viene scaricato in una sottocartella denominata con l'ID file.

    > [!IMPORTANT]
    > Quando si caricano file nei passaggi 9 e 10, i file corretti devono avere lo stesso nome file e trovarsi nella stessa struttura di sottocartelle. La sottocartella e i nomi dei file vengono utilizzati per associare il file correttivo al file di errore originale. Se la struttura della cartella o i nomi dei file vengono modificati, verrà visualizzato l'errore seguente: `Cannot apply Error Remediation to the current Workingset` . Per evitare problemi, è consigliabile mantenere i file corretti nella stessa cartella padre e nella stessa struttura di sottocartelle.

7. Dopo aver scaricato i file, puoi correggere i file con uno strumento appropriato. Per i file protetti da password, sono disponibili diversi strumenti per la discrizione delle password. Se si conoscono le password per i file, è possibile aprirli e rimuovere la password di protezione.

8. Tornare ad Advanced eDiscovery e alla procedura guidata di correzione degli errori, quindi fare clic su **Avanti: Caricare i file.**  Verrà visualizzata la pagina successiva in cui è ora possibile caricare i file.

    ![Carica file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specificare la cartella padre in cui si trovano i file corretti nella casella di testo Percorso **del percorso** dei file. Anche in questo caso, la cartella padre deve avere la stessa struttura di sottocartella creata al momento del download dei file.

    Il percorso della cartella padre viene aggiunto automaticamente al comando AzCopy (come valore del **parametro /Source).**

10. Copiare il comando predefinito facendo clic **su Copia negli Appunti.** Aprire un prompt dei comandi di Windows, incollare il comando AzCopy e quindi premere **INVIO.** caricare i file.

    ![Risultati del caricamento corretto dei file corretti in Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Dopo aver eseguito il comando AzCopy, fare clic su **Avanti: Elabora file.**

    Al termine dell'elaborazione, è possibile passare al set di revisioni e visualizzare i file corretti. 

## <a name="remediating-errors-in-container-files"></a>Correzione degli errori nei file contenitore

In situazioni in cui il contenuto di un file contenitore (ad esempio un file ZIP) non può essere estratto da Advanced eDiscovery, i contenitori possono essere scaricati e il contenuto espanso nella stessa cartella in cui si trova il contenitore originale. I file espansi verranno attribuiti al contenitore padre come se fosse stato originariamente espanso da Advanced eDiscovery. Il processo funziona come descritto in precedenza, ad eccezione del caricamento di un singolo file come file sostitutivo.  Quando carichi file corretti, non includere il file contenitore originale.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Correzione degli errori caricando il testo estratto

A volte non è possibile correggere un file nel formato nativo che Advanced eDiscovery è in grado di interpretare. Tuttavia, puoi sostituire il file originale con un file di testo contenente il testo originale del file nativo (in un processo denominato *sovrimpressione del testo).* A tale scopo, seguire i passaggi descritti in questo articolo, ma invece di correggere il file originale nel formato nativo, è necessario creare un file di testo contenente il testo estratto dal file originale e quindi caricare il file di testo utilizzando il nome file originale aggiunto con un suffisso txt. Ad esempio, si scarica un file durante la correzione degli errori con il nome file 335850cc-6602-4af0-acfa-1d14d9128ca2.abc. Aprire il file nell'applicazione nativa, copiare il testo e incollarlo in un nuovo file denominato 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. Quando si esegue questa operazione, assicurarsi di rimuovere il file originale nel formato nativo dal percorso del file corretto nel computer locale prima di caricare il file di testo corretto in Advanced eDiscovery.

## <a name="what-happens-when-files-are-remediated"></a>Cosa succede quando i file vengono corretti

Quando i file corretti vengono caricati, i metadati originali vengono mantenuti ad eccezione dei campi seguenti: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Testo
- WordCount
- WorkingsetId

Per una definizione di tutti i campi dei metadati in Advanced eDiscovery, vedere [Campi dei metadati del documento.](document-metadata-fields-in-advanced-ediscovery.md)
