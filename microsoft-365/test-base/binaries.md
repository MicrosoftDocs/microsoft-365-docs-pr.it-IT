---
title: Upload File binari dell'applicazione
description: Come iniziare a usare Test Base per M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323165"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Passaggio 3: Upload file binari, dipendenze e script

In questa scheda verrà caricato un singolo pacchetto zip contenente i file binari, le dipendenze e gli script utilizzati per eseguire il gruppo di test.

## <a name="upload-package-zip-file"></a>Upload zip del pacchetto

![Upload i file binari](Media/AddBinaries.png)

  - Le dipendenze caricate possono includere framework di test, motori di script o dati a cui sarà possibile accedere per eseguire l'applicazione o i test case. Ad esempio, puoi caricare Selenium e un programma di installazione di webdriver per eseguire test basati su browser.
  - È consigliabile assicurarsi che le attività di script siano mantenute modulari, ad esempio. 
    - Lo ```Install``` script esegue solo operazioni di installazione.
    - Lo ```Launch``` script avvia solo l'applicazione.
    - Lo ```Close``` script chiude solo l'applicazione.
    - Lo ```Uninstall``` script facoltativo disinstalla solo l'applicazione.

**Attualmente, il portale supporta solo script di PowerShell.**


## <a name="next-steps"></a>Passaggi successivi 

Passare all'articolo successivo per andare al Passaggio 4: **Impostare le attività di test.**
> [!div class="nextstepaction"]
> [Indietro](uploadApplication.md)
> [!div class="nextstepaction"]
> [Passaggio successivo](testtask.md)

