---
title: Aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Informazioni su come configurare il registro di sistema di Windows per aumentare la velocità effettiva dei dati quando si scaricano i risultati della ricerca e i dati di ricerca dal centro sicurezza & compliance e Advanced eDiscovery in Office 365.
ms.openlocfilehash: f74d164250f9d5b9b8315fe2651d3374457451ed
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686558"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365

Quando si utilizza lo strumento di esportazione di eDiscovery di Office 365 per scaricare i risultati di una ricerca di contenuto nel centro sicurezza & conformità o scaricare i dati da Office 365 Advanced eDiscovery, lo strumento avvia un certo numero di operazioni di esportazione simultanee per scaricare i dati nel computer locale. Per impostazione predefinita, il numero di operazioni simultanee è impostato su 8 volte il numero di core nel computer che si sta utilizzando per scaricare i dati. Ad esempio, se si dispone di un computer dual core (che significa due unità di elaborazione centrale in un unico chip), il numero predefinito di operazioni di esportazione simultanee è 16. Per aumentare la velocità effettiva di trasferimento dei dati e velocizzare il processo di download, è possibile aumentare il numero di operazioni simultanee configurando un'impostazione del registro di sistema di Windows nel computer utilizzato per scaricare i risultati della ricerca. Per velocizzare il processo di download, è consigliabile iniziare con un'impostazione di 24 operazioni simultanee.
  
Se si scaricano i risultati della ricerca in una rete con larghezza di banda ridotta, l'aumento di questa impostazione può avere un impatto negativo. In alternativa, potrebbe essere possibile aumentare l'impostazione su più di 24 operazioni simultanee in una rete a larghezza di banda elevata (il numero massimo di operazioni simultanee è 48). Dopo aver configurato l'impostazione del registro di sistema, potrebbe essere necessario modificarla per individuare il numero ottimale di operazioni simultanee per l'ambiente.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Creare un'impostazione del registro di sistema per modificare il numero di operazioni simultanee durante l'esportazione dei dati

Eseguire la procedura seguente nel computer che verrà utilizzato per scaricare i risultati della ricerca dal centro sicurezza & conformità o i dati di Advanced eDiscovery.
  
1. Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto. 
    
2. Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, ConcurrentOperations. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Come spiegato in precedenza, si consiglia di iniziare con 24 operazioni simultanee e quindi modificare questa impostazione in base alle esigenze.
    
3. In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nel passaggio precedente.
    
4. Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.
    
6. È possibile ripetere i passaggi 2-5 per modificare il valore per `DownloadConcurrency` l'impostazione del registro di sistema. 
    
    > [!IMPORTANT]
    > Dopo aver creato o modificato l' `DownloadConcurrency` impostazione del registro di sistema, assicurarsi di creare un nuovo processo di esportazione o di riavviare un processo di esportazione esistente per i risultati di ricerca o i dati che si desidera scaricare. Per ulteriori dettagli, vedere la sezione [ulteriori informazioni](#more-information) . 
  
## <a name="more-information"></a>Altre informazioni

- La prima volta che si esegue il file con estensione reg creato in questa procedura viene creata una nuova chiave del registro di sistema. L' `DownloadConcurrency` impostazione del registro di sistema viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit. 
    
- Lo strumento di esportazione di eDiscovery di Office 365 utilizza l' [utilità AzCopy di Azure](https://go.microsoft.com/fwlink/?linkid=849949) per scaricare i dati di ricerca dal centro sicurezza & Compliance o da Advanced eDiscovery. La configurazione `DownloadConcurrency` dell'impostazione del registro di sistema è simile all'utilizzo del parametro **/NC** quando si esegue l'utilità AzCopy. In questo modo, l' `"DownloadConcurrency=24"` impostazione del registro di sistema avrebbe lo stesso effetto dell'utilizzo `/NC:24` del valore del parametro con l'utilità AzCopy. 
    
- Se si interrompe un download di esportazione che è attualmente in corso e quindi lo si riavvia (tentando di scaricare di nuovo i risultati della ricerca), lo strumento di esportazione di Office 365 eDiscovery tenterà di riprendere lo stesso download. Pertanto, se si avvia un download, lo si interrompe e quindi si modifica `DownloadConcurrency` l'impostazione del registro di sistema, il download probabilmente avrà esito negativo se lo si riavvia (facendo clic su **Scarica risultati esportati**). Ciò è dovuto al fatto che lo strumento di esportazione tenterà di riprendere il download precedente utilizzando le impostazioni non valide perché è stata modificata l'impostazione del registro di sistema.
    
    Pertanto, dopo aver modificato l' `DownloadConcurrency` impostazione del registro di sistema, assicurarsi di riavviare il processo di esportazione (facendo clic su **Riavvia esportazione**) nel centro sicurezza & conformità. È quindi possibile scaricare i risultati esportati. Per ulteriori informazioni sull'esportazione di dati e risultati della ricerca, vedere:
    
  - [Esportare i risultati della Ricerca contenuto](export-search-results.md)
    
  - [Esportare i risultati in Office 365 Advanced eDiscovery](export-results-in-advanced-ediscovery.md)
    
