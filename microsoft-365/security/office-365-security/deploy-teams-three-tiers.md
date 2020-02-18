---
title: Distribuire team per tre livelli di protezione dei file
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Creare e configurare team con Microsoft Teams per diversi livelli di protezione delle informazioni per i file.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083339"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="ce6e0-103">Distribuire team per tre livelli di protezione dei file</span><span class="sxs-lookup"><span data-stu-id="ce6e0-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="ce6e0-104">Usare i passaggi descritti in questo articolo per progettare e implementare team di base, sensibili ed estremamente riservati.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="ce6e0-105">Per ulteriori informazioni su questi tre livelli di protezione, vedere [Proteggere i file in Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e0-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="ce6e0-106">Team di base</span><span class="sxs-lookup"><span data-stu-id="ce6e0-106">Baseline teams</span></span>

<span data-ttu-id="ce6e0-107">La protezione di base include team pubblici e privati.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="ce6e0-108">I team pubblici possono essere individuati e usati da chiunque nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="ce6e0-109">I siti privati possono essere individuati e sono accessibili solo dai membri del gruppo Office 365 associato al team.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="ce6e0-110">Entrambi questi tipi di team consentono ai membri di condividere il sito con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="ce6e0-111">Pubblico</span><span class="sxs-lookup"><span data-stu-id="ce6e0-111">Public</span></span>

<span data-ttu-id="ce6e0-112">Seguire le istruzioni disponibili in [questo articolo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) per creare un Team di base con autorizzazioni e accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="ce6e0-113">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-113">Here is your resulting configuration.</span></span>

![Protezione di base per un team pubblico.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="ce6e0-115">Privato</span><span class="sxs-lookup"><span data-stu-id="ce6e0-115">Private</span></span>

<span data-ttu-id="ce6e0-116">Seguire le istruzioni disponibili in [questo articolo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) per creare un Team di base con autorizzazioni e accesso privato.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="ce6e0-117">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-117">Here is your resulting configuration.</span></span>

![Protezione di base per un team privato.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="ce6e0-119">Team sensibili</span><span class="sxs-lookup"><span data-stu-id="ce6e0-119">Sensitive teams</span></span>

<span data-ttu-id="ce6e0-120">Per un team sensibile, è possibile iniziare [creando un team privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="ce6e0-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="ce6e0-121">Successivamente, si configura il sito di SharePoint sottostante per impedire la condivisione ai membri del team.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="ce6e0-122">Nella barra degli strumenti per il team fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="ce6e0-123">Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="ce6e0-124">Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="ce6e0-125">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="ce6e0-126">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="ce6e0-127">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-127">Here is your resulting configuration.</span></span>

![Protezione dati sensibili per un team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="ce6e0-129">Team estremamente riservati</span><span class="sxs-lookup"><span data-stu-id="ce6e0-129">Highly confidential teams</span></span>

<span data-ttu-id="ce6e0-130">Con un team estremamente riservato, si inizia [creando un team privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="ce6e0-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="ce6e0-131">Successivamente, si configura il sito di SharePoint sottostante per impedire la condivisione ai membri del team e la richiesta di accesso per i non membri del team.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="ce6e0-132">Nella barra degli strumenti per il team fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="ce6e0-133">Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="ce6e0-134">Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="ce6e0-135">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="ce6e0-136">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="ce6e0-137">Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="ce6e0-138">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="ce6e0-138">Here is your resulting configuration.</span></span>

![Protezione dati estremamente riservati per un team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="ce6e0-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ce6e0-140">Next step</span></span>

[<span data-ttu-id="ce6e0-141">Proteggere i file nei team con etichette di conservazione e prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="ce6e0-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="ce6e0-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce6e0-142">See also</span></span>

[<span data-ttu-id="ce6e0-143">Proteggere i file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce6e0-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="ce6e0-144">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="ce6e0-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
