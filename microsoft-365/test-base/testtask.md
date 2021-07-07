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
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="786c7-103">Passaggio 4: scheda Attività</span><span class="sxs-lookup"><span data-stu-id="786c7-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="786c7-104">Nella scheda attività è previsto che si forniranno i percorsi degli script di test presenti nella cartella zip caricata nella scheda file binari.</span><span class="sxs-lookup"><span data-stu-id="786c7-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="786c7-105">**Script di test out-of-box:** Digitare i percorsi relativi agli script di installazione, avvio, chiusura e disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="786c7-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="786c7-106">È inoltre possibile selezionare impostazioni aggiuntive per lo script di installazione.</span><span class="sxs-lookup"><span data-stu-id="786c7-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="786c7-107">**Script di test funzionali:** Digitare il percorso relativo di ogni script di test funzionale caricato.</span><span class="sxs-lookup"><span data-stu-id="786c7-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="786c7-108">È possibile aggiungere ulteriori script di test funzionali utilizzando il ```Add Script``` pulsante.</span><span class="sxs-lookup"><span data-stu-id="786c7-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="786c7-109">È necessario un minimo di uno (1) script e può aggiungere fino a otto (8) script di test funzionali.</span><span class="sxs-lookup"><span data-stu-id="786c7-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="786c7-110">Gli script vengono eseguiti in sequenza di caricamento e un errore in uno script specifico interrompe l'esecuzione degli script successivi.</span><span class="sxs-lookup"><span data-stu-id="786c7-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="786c7-111">È inoltre possibile selezionare impostazioni aggiuntive per ogni script fornito.</span><span class="sxs-lookup"><span data-stu-id="786c7-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="786c7-112">Imposta percorso script</span><span class="sxs-lookup"><span data-stu-id="786c7-112">Set script path</span></span>

![Immagine dell'attività di test](Media/testtask.png)

<span data-ttu-id="786c7-114">Di seguito è riportato un esempio di come fornire il percorso relativo in una struttura di cartelle:</span><span class="sxs-lookup"><span data-stu-id="786c7-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="786c7-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="786c7-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="786c7-116">**ScriptX.ps1** avrebbe.</span><span class="sxs-lookup"><span data-stu-id="786c7-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="786c7-117">_ScriptX.ps1_ come percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="786c7-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="786c7-118">**Script.ps1** _cartella1/script.ps1_ come percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="786c7-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="786c7-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="786c7-119">Next steps</span></span>

<span data-ttu-id="786c7-120">Visualizzare i dettagli della scheda Opzioni di test nell'articolo successivo</span><span class="sxs-lookup"><span data-stu-id="786c7-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="786c7-121">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="786c7-121">Next step</span></span>](testoptions.md)
