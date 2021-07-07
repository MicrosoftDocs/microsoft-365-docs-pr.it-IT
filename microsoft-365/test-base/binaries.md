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
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="2d096-103">Passaggio 3: Upload file binari, dipendenze e script</span><span class="sxs-lookup"><span data-stu-id="2d096-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="2d096-104">In questa scheda verrà caricato un singolo pacchetto zip contenente i file binari, le dipendenze e gli script utilizzati per eseguire il gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="2d096-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="2d096-105">Upload zip del pacchetto</span><span class="sxs-lookup"><span data-stu-id="2d096-105">Upload package zip file</span></span>

![Upload i file binari](Media/AddBinaries.png)

  - <span data-ttu-id="2d096-107">Le dipendenze caricate possono includere framework di test, motori di script o dati a cui sarà possibile accedere per eseguire l'applicazione o i test case.</span><span class="sxs-lookup"><span data-stu-id="2d096-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="2d096-108">Ad esempio, puoi caricare Selenium e un programma di installazione di webdriver per eseguire test basati su browser.</span><span class="sxs-lookup"><span data-stu-id="2d096-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="2d096-109">È consigliabile assicurarsi che le attività di script siano mantenute modulari, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="2d096-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="2d096-110">Lo ```Install``` script esegue solo operazioni di installazione.</span><span class="sxs-lookup"><span data-stu-id="2d096-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="2d096-111">Lo ```Launch``` script avvia solo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d096-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="2d096-112">Lo ```Close``` script chiude solo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d096-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="2d096-113">Lo ```Uninstall``` script facoltativo disinstalla solo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d096-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="2d096-114">**Attualmente, il portale supporta solo script di PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="2d096-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="2d096-115">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2d096-115">Next steps</span></span> 

<span data-ttu-id="2d096-116">Passare all'articolo successivo per andare al Passaggio 4: **Impostare le attività di test.**</span><span class="sxs-lookup"><span data-stu-id="2d096-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2d096-117">Indietro</span><span class="sxs-lookup"><span data-stu-id="2d096-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="2d096-118">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="2d096-118">Next step</span></span>](testtask.md)

