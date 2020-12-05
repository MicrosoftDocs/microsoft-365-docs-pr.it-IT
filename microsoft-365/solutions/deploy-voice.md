---
title: Distribuire la voce in Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Informazioni su come scegliere e distribuire la soluzione vocale Right teams per la propria organizzazione.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580900"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="eadac-103">Pianificare e distribuire una soluzione per la voce Teams</span><span class="sxs-lookup"><span data-stu-id="eadac-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="eadac-104">Una soluzione di teams Voice consente alle persone dell'organizzazione di effettuare chiamate sia all'interno che all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eadac-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="eadac-105">Una soluzione vocale completa è costituita da team, Microsoft Phone System e da una scelta di opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="eadac-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Panoramica di teams Voice Solutions](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="eadac-107">Il sistema telefonico fornisce funzionalità complete del PBX (Private Branch Exchange) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eadac-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="eadac-108">Le chiamate tra gli utenti dell'organizzazione--indipendentemente dalla loro posizione geografica--vengono gestite internamente all'interno del sistema telefonico, rimuovendo così i costi di lunga distanza su queste chiamate interne.</span><span class="sxs-lookup"><span data-stu-id="eadac-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="eadac-109">Collegando il sistema telefonico alla rete PSTN (Public Switched Telephone Network), gli utenti possono effettuare chiamate anche all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eadac-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="eadac-110">Questa guida della soluzione consente di:</span><span class="sxs-lookup"><span data-stu-id="eadac-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="eadac-111">Scegliere la soluzione vocale più adatta alla propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="eadac-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="eadac-112">Distribuire la soluzione vocale selezionata</span><span class="sxs-lookup"><span data-stu-id="eadac-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="eadac-113">Eseguire la procedura seguente per scegliere, pianificare e configurare la soluzione vocale:</span><span class="sxs-lookup"><span data-stu-id="eadac-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Scegliere la soluzione vocale](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="eadac-115">Scegliere la soluzione vocale</span><span class="sxs-lookup"><span data-stu-id="eadac-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="eadac-116">Configurare Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="eadac-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="eadac-117">Impostare la connettività PSTN scegliendo una o una combinazione di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="eadac-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="eadac-118">[Piano di chiamata](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -soluzione all-in-the-cloud di Microsoft con Microsoft come operatore PSTN</span><span class="sxs-lookup"><span data-stu-id="eadac-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="eadac-119">[Routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -utilizzare il routing diretto per connettere il proprio operatore PSTN ai team</span><span class="sxs-lookup"><span data-stu-id="eadac-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="eadac-120">È inoltre possibile leggere informazioni su come una società multinazionale di grandi dimensioni ha eseguito la migrazione a una soluzione vocale di Teams nel [caso di studio contoso](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="eadac-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="eadac-121">Per informazioni sulle licenze necessarie, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eadac-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="eadac-122">Licenze per i componenti aggiuntivi di Teams</span><span class="sxs-lookup"><span data-stu-id="eadac-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="eadac-123">Requisiti di licenza per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="eadac-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
