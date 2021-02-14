---
title: Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca eDiscovery
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
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST scaricati nel computer quando si esportano i risultati della ricerca eDiscovery.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942919"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca eDiscovery

Quando si utilizza lo strumento di esportazione di eDiscovery per esportare i risultati della posta elettronica di una ricerca eDiscovery dai diversi strumenti di Microsoft eDiscovery, la dimensione predefinita di un file PST che può essere esportato è 10 GB. Se si desidera modificare questa dimensione predefinita, è possibile modificare il Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Uno dei motivi per eseguire questa operazione è che un file PST può adattarsi a supporti rimovibili, ad esempio un DVD, un compact disc o un'unità USB. 
  
> [!NOTE]
> Lo strumento di esportazione di eDiscovery viene utilizzato per esportare i risultati della ricerca quando si utilizza lo strumento Ricerca contenuto nel Centro sicurezza & conformità, In-Place eDiscovery in Exchange Online e centro eDiscovery in SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Creare un'impostazione del Registro di sistema per modificare le dimensioni dei file PST quando si esportano i risultati della ricerca eDiscovery

Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca eDiscovery.
  
1. Chiudere lo strumento di esportazione di eDiscovery, se aperto. 
    
2. Salvare il testo seguente in un file del Registro di sistema di Window utilizzando il suffisso del nome file reg. ad esempio PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Nell'esempio precedente il valore è impostato su  `PstSizeLimitInBytes` 1.073.741.824 byte o su circa 1 GB. Ecco alcuni altri valori di esempio per  `PstSizeLimitInBytes` l'impostazione. 
    
    |**Dimensioni in GB (circa)**|**Dimensioni in byte**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Modificare il valore sulla dimensione massima desiderata di un file PST quando si esportano i risultati della ricerca `PstSizeLimitInBytes` e quindi salvare il file. 
    
4. In Esplora risorse fare clic o fare doppio clic sul file reg creato nei passaggi precedenti.
    
5. Nella finestra Controllo di accesso utente fare clic su **Sì** per consentire all'Editor del Registro di sistema di apportare la modifica. 
    
6. Quando viene richiesto di continuare, fare clic su **Sì.**
    
    Nell'Editor del Registro di sistema viene visualizzato un messaggio che indica che l'impostazione è stata aggiunta correttamente al Registro di sistema.
    
7. È possibile ripetere i passaggi da 3 a 6 per modificare il valore dell'impostazione del Registro  `PstSizeLimitInBytes` di sistema. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Domande frequenti sulla modifica delle dimensioni predefinite dei file PST quando si esportano i risultati della ricerca eDiscovery

 **Perché la dimensione predefinita è 10 GB?**
  
Le dimensioni predefinite di 10 GB si basano sul feedback dei clienti; 10 GB è un buon equilibrio tra la quantità ottimale di contenuto in un singolo file PST e con una minima probabilità di danneggiamento dei file.
  
 **È consigliabile aumentare o ridurre le dimensioni predefinite dei file PST?**
  
I clienti tendono a ridurre il limite di dimensioni in modo che i risultati della ricerca si adattino ai supporti rimovibili che possono spedire fisicamente in altre posizioni dell'organizzazione. Non è consigliabile aumentare le dimensioni predefinite perché i file PST di dimensioni superiori a 10 GB potrebbero avere problemi di danneggiamento.
  
 **Su quale computer è necessario eseguire questa operazione?**
  
È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale in cui si esegue lo strumento di esportazione di eDiscovery.
  
 **Dopo aver modificato questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione di eDiscovery è in esecuzione, sarà necessario chiuderlo e riavviarlo dopo aver modificato questa impostazione.
  
 **Una chiave del Registro di sistema esistente viene modificata o viene creata una nuova chiave?**
  
Una nuova chiave del Registro di sistema viene creata alla prima esecuzione del file reg creato in questa procedura. L'impostazione viene quindi modificata ogni volta che si modifica ed esegue di nuovo il file reg edit.
