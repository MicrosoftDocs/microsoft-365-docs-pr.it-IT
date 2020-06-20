---
title: Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Modificare il registro di sistema di Windows nel computer locale per disabilitare i report quando si esportano i risultati di una ricerca di contenuto dal centro sicurezza & conformità.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817855"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto

Quando si utilizza lo strumento di esportazione di eDiscovery per esportare i risultati di una ricerca di contenuto nel centro sicurezza & conformità, lo strumento crea e Esporta automaticamente due rapporti che contengono informazioni aggiuntive sul contenuto esportato. Questi rapporti sono il file Results.csv e il file Manifest.xml (vedere la sezione [domande frequenti su disabilitazione dei rapporti di esportazione](#frequently-asked-questions-about-disabling-export-reports) in questo argomento per una descrizione dettagliata di questi report). Poiché questi file possono essere di dimensioni molto grandi, è possibile velocizzare il tempo di download e salvare lo spazio su disco impedendo l'esportazione di tali file. A tale scopo, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Se si desidera includere i rapporti in un secondo momento, è possibile modificare l'impostazione del registro di sistema. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Creare le impostazioni del registro di sistema per disabilitare i report di esportazione

Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.
  
1. Chiudere lo strumento di esportazione di eDiscovery se è aperto.
    
2. Eseguire una o entrambe le operazioni seguenti, a seconda del rapporto di esportazione che si desidera disabilitare.
    
    - **Results.csv**
    
      Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, DisableResultsCsv. reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, DisableManifestXml. reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nei passaggi precedenti.
    
4. Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Modificare le impostazioni del registro di sistema per riattivare i report di esportazione

Se i rapporti Results.csv e Manifest.xml sono stati disabilitati creando i file con estensione reg nella procedura precedente, è possibile modificare tali file per riabilitare un report in modo che venga esportato con i risultati della ricerca. Eseguire di nuovo la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.
  
1. Chiudere lo strumento di esportazione di eDiscovery se è aperto.
    
2. Modificare uno o entrambi i file. reg Edit creati nella procedura precedente.
    
    - **Results.csv**
    
        Aprire il file DisableResultsCsv. reg in blocco note, modificare il valore `False` in `True` e quindi salvare il file. Ad esempio, dopo aver modificato il file, questo aspetto è simile al seguente:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Aprire il file DisableManifestXml. reg in blocco note, modificare il valore `False` in `True` e quindi salvare il file. Ad esempio, dopo aver modificato il file, questo aspetto è simile al seguente:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. In Esplora risorse fare clic o fare doppio clic su un file con estensione reg modificato nel passaggio precedente.
    
4. Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Domande frequenti sulla disabilitazione dei rapporti di esportazione

 **Quali sono i rapporti Results.csv e Manifest.xml?**
  
I file Results.csv e Manifest.xml contengono informazioni aggiuntive sul contenuto che è stato esportato.
  
- **Results.csv** Documento di Excel che contiene informazioni su ogni elemento che viene scaricato come risultato della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
  - Se il messaggio è un messaggio duplicato se è stata abilitata la deduplicazione quando si esportano i risultati della ricerca. I messaggi duplicati avranno un valore nella colonna **padre ItemId** che identifica il messaggio come duplicato. Il valore nella colonna **ItemId padre** è uguale al valore nella colonna **DocumentID elemento** del messaggio che è stato esportato. 
    
    Per i documenti dei siti di SharePoint e OneDrive for business, il log dei risultati contiene informazioni su ogni documento, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
- **Manifest.xml** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. Le informazioni contenute in questo report sono uguali a quelle del report Results.csv, ma sono nel formato specificato dal modello di riferimento per l'individuazione elettronica (EDRM). Per ulteriori informazioni su EDRM, accedere a [https://www.edrm.net](https://www.edrm.net) .
    
 **Quando è necessario disabilitare l'esportazione di questi rapporti?**
  
Dipende dalle esigenze specifiche. Molte organizzazioni non richiedono ulteriori informazioni sui risultati di ricerca e non hanno bisogno di questi rapporti.
  
 **Per quale computer è necessario eseguire questa operazione?**
  
 È necessario modificare l'impostazione del registro di sistema in un computer locale in cui viene eseguito lo strumento di esportazione di eDiscovery. 
  
 **Dopo aver modificato questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione di eDiscovery è in esecuzione, è necessario chiuderlo e riavviarlo dopo aver modificato l'impostazione del registro di sistema.
  
 **Una chiave del registro di sistema esistente viene modificata o viene creata una nuova chiave?**
  
La prima volta che si esegue il file con estensione reg creato nella procedura descritta in questo argomento viene creata una nuova chiave del registro di sistema. L'impostazione viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit.
