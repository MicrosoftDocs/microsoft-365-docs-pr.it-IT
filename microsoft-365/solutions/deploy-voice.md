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
description: Informazioni su come scegliere e distribuire la soluzione Teams vocale giusta per l'organizzazione.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918383"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="8975b-103">Pianificare e distribuire una soluzione vocale di Teams</span><span class="sxs-lookup"><span data-stu-id="8975b-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="8975b-104">Una Teams vocale consente agli utenti dell'organizzazione di effettuare chiamate sia all'interno che all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8975b-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="8975b-105">Una soluzione vocale completa è costituita Teams, Telefono Microsoft System e una scelta di opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="8975b-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams panoramica delle soluzioni vocali](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="8975b-107">Sistema telefonico offre funzionalità PBX (Private Branch Exchange) complete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8975b-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="8975b-108">Le chiamate tra gli utenti dell'organizzazione, indipendentemente dalla loro posizione geografica, vengono gestite internamente all'interno di Sistema telefonico rimuovendo così i costi a lunga distanza per queste chiamate interne.</span><span class="sxs-lookup"><span data-stu-id="8975b-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="8975b-109">Connettendo Sistema telefonico alla rete PSTN (Public Switched Telephone Network), gli Teams utenti possono effettuare chiamate anche all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8975b-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="8975b-110">Questa guida alla soluzione consente di:</span><span class="sxs-lookup"><span data-stu-id="8975b-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="8975b-111">Scegliere la soluzione vocale più giusta per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8975b-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="8975b-112">Distribuire la soluzione vocale selezionata</span><span class="sxs-lookup"><span data-stu-id="8975b-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="8975b-113">Seguire questa procedura per scegliere, pianificare e configurare la soluzione vocale:</span><span class="sxs-lookup"><span data-stu-id="8975b-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Scegliere la soluzione vocale](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="8975b-115">Scegliere la soluzione vocale</span><span class="sxs-lookup"><span data-stu-id="8975b-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="8975b-116">Configurare Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="8975b-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="8975b-117">Configurare la connettività PSTN scegliendo una o una combinazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8975b-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="8975b-118">[Piano di chiamata](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Soluzione all-in-the-cloud di Microsoft con Microsoft come gestore PSTN</span><span class="sxs-lookup"><span data-stu-id="8975b-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="8975b-119">[Routing diretto](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Usare il routing diretto per connettere il proprio operatore PSTN a Teams</span><span class="sxs-lookup"><span data-stu-id="8975b-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="8975b-120">È inoltre consigliabile leggere come è stata eseguita la migrazione di una società multinazionale di grandi dimensioni a una soluzione Teams voice nel [case study di Contoso.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="8975b-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="8975b-121">Per informazioni sulle licenze necessarie, vedere:</span><span class="sxs-lookup"><span data-stu-id="8975b-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="8975b-122">Teams licenze dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="8975b-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="8975b-123">Requisiti di licenza per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="8975b-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)