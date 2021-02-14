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
description: Modificare il Registro di sistema di Windows nel computer locale per disabilitare i report quando si esportano i risultati di una ricerca di contenuto dal Centro sicurezza & conformità.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817855"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Disabilitare i rapporti quando si esportano i risultati di Ricerca contenuto

Quando si utilizza lo strumento di esportazione di eDiscovery per esportare i risultati di una ricerca di contenuto nel Centro sicurezza & conformità, lo strumento crea ed esporta automaticamente due report contenenti informazioni aggiuntive sul contenuto esportato. Questi report sono il file Results.csv e il file [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (vedere le domande frequenti sulla disabilitazione dei report di esportazione in questo argomento per descrizioni dettagliate di questi report). Poiché questi file possono essere molto grandi, è possibile velocizzare i tempi di download e risparmiare spazio su disco impedendo l'esportazione di tali file. A tale scopo, modificare il Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Se si desidera includere i report in un secondo momento, è possibile modificare l'impostazione del Registro di sistema. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Creare le impostazioni del Registro di sistema per disabilitare i report di esportazione

Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.
  
1. Chiudere lo strumento di esportazione di eDiscovery, se aperto.
    
2. Eseguire uno o entrambi i passaggi seguenti, a seconda del report di esportazione che si desidera disabilitare.
    
    - **Results.csv**
    
      Salvare il testo seguente in un file del Registro di sistema di Windows utilizzando il suffisso del nome file reg. ad esempio DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Salvare il testo seguente in un file del Registro di sistema di Windows utilizzando il suffisso del nome file reg. ad esempio DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. In Esplora risorse fare clic o fare doppio clic sul file reg creato nei passaggi precedenti.
    
4. Nella finestra Controllo di accesso utente fare clic su **Sì** per consentire all'Editor del Registro di sistema di apportare la modifica. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì.**
    
    Nell'Editor del Registro di sistema viene visualizzato un messaggio che indica che l'impostazione è stata aggiunta correttamente al Registro di sistema.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Modificare le impostazioni del Registro di sistema per abilitare di nuovo i report di esportazione

Se i report Results.csv e Manifest.xml sono stati disabilitati creando i file con estensione reg nella procedura precedente, è possibile modificare tali file per abilitare di nuovo un report in modo che sia esportato con i risultati della ricerca. Anche in questo caso, eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di contenuto.
  
1. Chiudere lo strumento di esportazione di eDiscovery, se aperto.
    
2. Modificare uno o entrambi i file di modifica con estensione reg creati nella procedura precedente.
    
    - **Results.csv**
    
        Aprire il file DisableResultsCsv.reg nel Blocco note, modificare il valore in  `False` e quindi salvare il  `True` file. Ad esempio, dopo aver modificato il file, l'aspetto sarà simile al seguente:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Aprire il file DisableManifestXml.reg nel Blocco note, modificare il valore in  `False` e quindi salvare il  `True` file. Ad esempio, dopo aver modificato il file, l'aspetto sarà simile al seguente:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. In Esplora risorse fare clic o fare doppio clic su un file reg modificato nel passaggio precedente.
    
4. Nella finestra Controllo di accesso utente fare clic su **Sì** per consentire all'Editor del Registro di sistema di apportare la modifica. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì.**
    
    Nell'Editor del Registro di sistema viene visualizzato un messaggio che indica che l'impostazione è stata aggiunta correttamente al Registro di sistema.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Domande frequenti sulla disabilitazione dei report di esportazione

 **Quali sono i Results.csv e Manifest.xml report?**
  
I Results.csv e Manifest.xml contengono informazioni aggiuntive sul contenuto esportato.
  
- **Results.csv** Documento di Excel che contiene informazioni su ogni elemento scaricato come risultato della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
  - Indica se il messaggio è duplicato se è stata abilitata la deduplicazione durante l'esportazione dei risultati della ricerca. I messaggi duplicati avranno un valore nella colonna **ItemId** padre che identifica il messaggio come duplicato. Il valore nella **colonna ItemId** padre corrisponde al valore nella colonna **DocumentId** dell'elemento del messaggio esportato. 
    
    Per i documenti dei siti di SharePoint e OneDrive for Business, il log dei risultati contiene informazioni su ogni documento, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
- **Manifest.xml** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. Le informazioni contenute in questo report sono le stesse del report Results.csv, ma sono nel formato specificato dal modello EDRM (Electronic Discovery Reference Model). Per ulteriori informazioni su EDRM, vedere [https://www.edrm.net](https://www.edrm.net) .
    
 **Quando è consigliabile disabilitare l'esportazione di questi report?**
  
Dipende dalle esigenze specifiche. Molte organizzazioni non richiedono informazioni aggiuntive sui risultati della ricerca e non necessitano di questi report.
  
 **Su quale computer è necessario eseguire questa operazione?**
  
 È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale in cui si esegue lo strumento di esportazione di eDiscovery. 
  
 **Dopo aver modificato questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione di eDiscovery è in esecuzione, è necessario chiuderlo e riavviarlo dopo aver modificato l'impostazione del Registro di sistema.
  
 **Una chiave del Registro di sistema esistente viene modificata o viene creata una nuova chiave?**
  
Una nuova chiave del Registro di sistema viene creata alla prima esecuzione del file reg creato nella procedura descritta in questo argomento. L'impostazione viene quindi modificata ogni volta che si modifica ed esegue di nuovo il file reg edit.
