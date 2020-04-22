---
title: Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST scaricati nel computer quando si esportano i risultati della ricerca di eDiscovery.
ms.openlocfilehash: f5fde9bbb37f6e22c49049c892a1b69b07d15bef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636324"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery

Quando si utilizza lo strumento di esportazione di eDiscovery per esportare i risultati di una ricerca di eDiscovery dai diversi strumenti di eDiscovery di Microsoft, le dimensioni predefinite di un file PST che può essere esportato sono 10 GB. Se si desidera modificare queste dimensioni predefinite, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Un motivo per farlo è un file PST che può essere adattato ai supporti rimovibili, ad esempio un DVD, un disco compatto o un'unità USB. 
  
> [!NOTE]
> Lo strumento di esportazione di eDiscovery viene utilizzato per esportare i risultati della ricerca quando si utilizza lo strumento di ricerca contenuto nel centro sicurezza & Compliance, eDiscovery sul posto in Exchange Online e il centro eDiscovery in SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Creare un'impostazione del registro di sistema per modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery

Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di eDiscovery.
  
1. Chiudere lo strumento di esportazione di eDiscovery se è aperto. 
    
2. Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, PstExportSize. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Nell'esempio precedente, il `PstSizeLimitInBytes` valore è impostato su 1.073.741.824 byte o circa 1 GB. Di seguito sono riportati alcuni altri valori di `PstSizeLimitInBytes` esempio per l'impostazione. 
    
    |**Dimensioni in GB (circa)**|**Dimensioni in byte**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Quando si `PstSizeLimitInBytes` esportano i risultati della ricerca, modificare il valore con le dimensioni massime desiderate di un file PST e quindi salvare il file. 
    
4. In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nei passaggi precedenti.
    
5. Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche. 
    
6. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.
    
7. È possibile ripetere i passaggi 3-6 per modificare il valore per `PstSizeLimitInBytes` l'impostazione del registro di sistema. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Domande frequenti su come modificare le dimensioni predefinite dei file PST quando si esportano i risultati della ricerca di eDiscovery

 **Perché è la dimensione predefinita 10 GB?**
  
Le dimensioni predefinite di 10 GB si basano sul feedback dei clienti; 10 GB è un buon bilanciamento tra la quantità ottimale di contenuto in un singolo file PST e la possibilità minima di danneggiamento dei dati.
  
 **È consigliabile aumentare o diminuire la dimensione predefinita dei file PST?**
  
I clienti tendono a ridurre il limite di dimensione, in modo che i risultati della ricerca possano adattarsi a un supporto rimovibile che può essere importato fisicamente in altre posizioni all'interno della propria organizzazione. Non è consigliabile aumentare le dimensioni predefinite perché i file PST di dimensioni superiori a 10 GB potrebbero avere problemi di danneggiamento.
  
 **Per quale computer è necessario eseguire questa operazione?**
  
È necessario modificare l'impostazione del registro di sistema in un computer locale in cui viene eseguito lo strumento di esportazione di eDiscovery.
  
 **Dopo aver modificato questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione di eDiscovery è in esecuzione, sarà necessario chiuderlo e riavviarlo dopo la modifica di questa impostazione.
  
 **Una chiave del registro di sistema esistente viene modificata o viene creata una nuova chiave?**
  
La prima volta che si esegue il file con estensione reg creato in questa procedura viene creata una nuova chiave del registro di sistema. L'impostazione viene quindi modificata ogni volta che viene modificato ed eseguito il file. reg Edit.
