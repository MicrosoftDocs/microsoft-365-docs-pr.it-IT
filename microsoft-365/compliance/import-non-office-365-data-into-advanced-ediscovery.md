---
title: Importare contenuto non Microsoft 365 per l'analisi avanzata di eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Come eseguire la procedura per importare il contenuto non archiviato in Microsoft 365 in un BLOB di Azure in modo che possa essere analizzato con AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636953"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importare contenuto non Microsoft 365 per l'analisi di Advanced eDiscovery (Classic)

Non tutti i documenti che potrebbe essere necessario analizzare con Advanced eDiscovery vivranno in Microsoft 365. Con la caratteristica di importazione di contenuto non Microsoft 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Microsoft 365 (ad eccezione dei file PST) in un caso collegato, BLOB di archiviazione di Azure e analizzarli con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.
  
> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> È possibile acquistare un abbonamento aggiuntivo per l'archiviazione dei dati di eDiscovery per il contenuto non Microsoft 365. Questo è disponibile solo per il contenuto che deve essere analizzato con Advanced eDiscovery. Seguire la procedura in [acquistare o modificare un componente aggiuntivo per Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) e acquistare il componente aggiuntivo di archiviazione avanzata di eDiscovery. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Requisiti per caricare il contenuto non Office 365

Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:
  
- Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.
    
- Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.
    
- Un caso di eDiscovery esistente.
    
- Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato  *alias@domainname*  . I  *alias@domainname*  devono essere utenti di Office 365 alias e Domain. È possibile raccogliere tutte le cartelle di  *alias@domainname*  in una cartella radice. La cartella radice può contenere solo le cartelle  *alias@domainname*  , non devono essere presenti file liberi nella cartella radice.
    
- Un account che sia un amministratore di eDiscovery o eDiscovery.
    
- [Strumenti di archiviazione di Microsoft Azure](https://aka.ms/downloadazcopy) installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in Advanced eDiscovery


1. In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire **eDiscovery**e aprire il caso in cui verranno caricati i dati non di Office 365. Se è necessario creare un caso, vedere [gestire i casi di eDiscovery nel centro sicurezza e &amp; conformità](ediscovery-cases.md).
    
2. Fare clic su **passa a eDiscovery avanzato**.

3. Selezionare i **set di revisione** dal menu.

4. Selezionare un set di revisione esistente oppure scegliere **Aggiungi Revisione**.

5. Selezionare **Manage Review set**.

6. Nella scheda dati non Office 365, selezionare **Visualizza caricamento**.

7. Scegliere **Carica file** per avviare la procedura guidata per il caricamento dei file.

8. La prima scheda è **1. Prepara passaggio**. Selezionare **Avanti: carica file**.

9. Sul **2. Scheda carica file** verrà richiesto di scaricare AzCopy.exe se non è già stato fatto e quindi di specificare il percorso del file. Ad esempio, `C:\Upload`  vi darà il comando per l'esecuzione di AzCopy.exe. Usando `C:\Upload` , si vedrà:

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. Aprire una finestra del prompt dei comandi ed eseguire il comando AzCopy.exe per importare i dati in Azure. Dopo aver caricato tutti i dati, selezionare **Avanti: elabora file**.

11. La scheda successiva è **3. Elabora i file** in cui verranno visualizzati i depositari che dispongono di dati associati e mostrerà anche lo stato di avanzamento dei dati da importare.
        
    Per ulteriori informazioni sulla sintassi di Azcopy, vedere [Transfer Data with the Azcopy in Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy). 
    
    Per ulteriori informazioni sull'elaborazione avanzata di eDiscovery, vedere [Run the process Module and load data in Advanced eDiscovery (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md). 
    
    > [!IMPORTANT]
    > Deve essere presente una cartella radice per utente e il nome della cartella deve trovarsi nel formato <b>alias@domainname</b>  . 
   
    > [!IMPORTANT]
    > Dopo che il contenitore è stato elaborato correttamente in Advanced eDiscovery, non sarà più possibile aggiungere nuovo contenuto allo spazio di archiviazione SAS in Azure. Se si raccolgono contenuto aggiuntivo e si desidera aggiungerlo al caso per l'analisi avanzata di eDiscovery, è necessario creare un nuovo contenitore di **dati non Office 365** e ripetere questa procedura. 
  
    > [!NOTE]
    > Se il contenitore non  *elabora correttamente a causa di problemi di denominazione delle cartelle*  e quindi si corregge i problemi, sarà comunque necessario creare un nuovo contenitore e riconnetterlo e caricarlo nuovamente utilizzando le procedure illustrate in questo articolo.
