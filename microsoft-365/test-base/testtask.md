---
title: Impostare le attività di test
description: Impostare le attività di test
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322689"
---
# <a name="step-4-the-tasks-tab"></a>Passaggio 4: scheda Attività

Nella scheda attività è previsto che si forniranno i percorsi degli script di test presenti nella cartella zip caricata nella scheda file binari.

  - **Script di test out-of-box:** Digitare i percorsi relativi agli script di installazione, avvio, chiusura e disinstallazione. È inoltre possibile selezionare impostazioni aggiuntive per lo script di installazione.
  - **Script di test funzionali:** Digitare il percorso relativo di ogni script di test funzionale caricato. È possibile aggiungere ulteriori script di test funzionali utilizzando il ```Add Script``` pulsante. È necessario un minimo di uno (1) script e può aggiungere fino a otto (8) script di test funzionali. 
  
    Gli script vengono eseguiti in sequenza di caricamento e un errore in uno script specifico interrompe l'esecuzione degli script successivi.
    È inoltre possibile selezionare impostazioni aggiuntive per ogni script fornito.

## <a name="set-script-path"></a>Imposta percorso script

![Immagine dell'attività di test](Media/testtask.png)

Di seguito è riportato un esempio di come fornire il percorso relativo in una struttura di cartelle:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** avrebbe. _ScriptX.ps1_ come percorso relativo.
  - **Script.ps1** _cartella1/script.ps1_ come percorso relativo.


## <a name="next-steps"></a>Passaggi successivi

Visualizzare i dettagli della scheda Opzioni di test nell'articolo successivo 
> [!div class="nextstepaction"]
> [Passaggio successivo](testoptions.md)
