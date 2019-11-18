---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di Office 365 ProPlus per Microsoft 365 Enterprise.
ms.openlocfilehash: a51a37a321b450d233d7f9fd6da28b5828514d13
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627450"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="8735e-103">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="8735e-103">Phase 4: Office 365 ProPlus</span></span>

![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="8735e-105">*Questo passaggio si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise e Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="8735e-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="8735e-106">Microsoft 365 Enterprise include Office 365 ProPlus, la versione in abbonamento di Office.</span><span class="sxs-lookup"><span data-stu-id="8735e-106">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office.</span></span> <span data-ttu-id="8735e-107">Come Office 2019, Office 365 ProPlus include tutte le applicazioni di Office, che vengono installate direttamente nei dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="8735e-107">Like Office 2019, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="8735e-108">A differenza di Office 2019, Office 365 ProPlus viene aggiornato regolarmente con nuove funzionalità e usa un modello di gestione delle licenze basato sugli utenti, che consente di installare Office in più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8735e-108">Unlike Office 2019, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="8735e-109">Per maggiori informazioni, vedere [Informazioni su Office 365 ProPlus nell'azienda](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="8735e-109">For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="8735e-p102">In questa fase, si distribuisce Office 365 ProPlus nei dispositivi client nell'ambito di Microsoft 365 Enterprise. Oltre a queste linee guida, consigliamo di usare [Microsoft Fastrack](https://fasttrack.microsoft.com/office) a supporto dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8735e-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="8735e-112">Se è stato già implementato Office 365 ProPlus, vedere i [criteri uscita](office365proplus-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni obbligatorie di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8735e-112">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="8735e-113">Per la distribuzione di Windows 10 Enterprise e Office 365 ProPlus insieme, vedere la [Centro di distribuzione desktop](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="8735e-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="8735e-114">Passaggio 1: valutazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="8735e-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="8735e-p103">Prima di distribuire Office 365 ProPlus, seguire le istruzioni in [Valutazione dell'ambiente e dei requisiti per la distribuzione di Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). La valutazione include informazioni sui requisiti, dettagli dei dispositivi client (come le architetture e lingue richieste), i requisiti di licenza, la funzionalità di rete e la compatibilità delle applicazioni. Completare la valutazione consente di prendere decisioni chiave durante la pianificazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8735e-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="8735e-118">Passaggio 2: pianificare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="8735e-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="8735e-p104">Dopo la valutazione dell'ambiente, seguire le istruzioni in [Pianificazione della distribuzione di Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) per creare un piano di distribuzione. Include le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8735e-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="8735e-121">Come distribuire Office, incluso lo strumento da usare (ad esempio, Microsoft Endpoint Configuration Manager o lo strumento di distribuzione di Office) e da dove installare Office</span><span class="sxs-lookup"><span data-stu-id="8735e-121">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="8735e-122">Come gestire gli aggiornamenti in Office</span><span class="sxs-lookup"><span data-stu-id="8735e-122">How to manage updates to Office</span></span>
- <span data-ttu-id="8735e-123">Quali canali di aggiornamento usare (i canali di aggiornamento di Office controllano la frequenza con cui gli utenti ricevono aggiornamenti delle funzionalità nelle proprie applicazioni Office)</span><span class="sxs-lookup"><span data-stu-id="8735e-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="8735e-124">I pacchetti di installazione di Office e i gruppi di distribuzione da usare, tra cui le applicazioni di Office e le lingue che devono essere installate per determinati utenti</span><span class="sxs-lookup"><span data-stu-id="8735e-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="8735e-125">L'[articolo sulla pianificazione](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) include le procedure consigliate per tutte queste opzioni, tra cui la gestione della distribuzione, degli aggiornamenti, la definizione dei pacchetti di installazione e la creazione dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8735e-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="8735e-126">Passaggio 3: distribuzione</span><span class="sxs-lookup"><span data-stu-id="8735e-126">Step 3: Deploy</span></span>

<span data-ttu-id="8735e-127">In base al piano di distribuzione, scegliere la modalità di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="8735e-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="8735e-128">**[Distribuire Office 365 ProPlus con Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** gestire la distribuzione con Configuration Manager e scaricare e distribuire Office dai punti di distribuzione sulla rete.</span><span class="sxs-lookup"><span data-stu-id="8735e-128">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="8735e-129">**[Distribuire Office 365 ProPlus con lo strumento ODT dal cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** gestire la distribuzione con lo strumento ODT e installare Office nei dispositivi client direttamente dalla rete CDN di Office</span><span class="sxs-lookup"><span data-stu-id="8735e-129">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="8735e-130">**[Installare autonomamente Office 365 Pro Plus dal portale Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** gestire la distribuzione dal portale Office e far installare agli utenti Office nei propri dispositivi client direttamente dal portale</span><span class="sxs-lookup"><span data-stu-id="8735e-130">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="8735e-p105">Molte organizzazioni usano una combinazione di queste opzioni per utenti diversi. Ad esempio, l'organizzazione potrebbe usare Configuration Manager per distribuire Office alla maggior parte dei propri utenti, ma consentire l'installazione autonoma a un piccolo gruppo di dipendenti che non si connettono spesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="8735e-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="8735e-p106">Se l'organizzazione usa Configuration Manager, consigliamo di effettuare l'aggiornamento a Current Branch e alla versione corrente. Per ulteriori dettagli, vedere [Scelta del ramo di Configuration Manager da usare?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="8735e-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="8735e-135">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8735e-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8735e-136">Informazioni sul modo in cui gli esperti di Microsoft [distribuiscono e gestiscono gli aggiornamenti per Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="8735e-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="8735e-137">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8735e-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8735e-138">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito Office 365 ProPlus](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="8735e-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="8735e-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8735e-140">Next step</span></span>

[<span data-ttu-id="8735e-141">Fase 365: criteri uscita dell'infrastruttura di rete di Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="8735e-141">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
