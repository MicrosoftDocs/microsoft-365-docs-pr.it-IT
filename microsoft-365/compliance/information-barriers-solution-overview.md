---
title: Barriere informative in Microsoft 365
description: Informazioni su come configurare le barriere informative in Microsoft 365.
keywords: Microsoft 365, rischio Insider, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613844"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="ccfe8-104">Barriere informative in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ccfe8-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="ccfe8-105">Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni e supporta modi per limitare la comunicazione e la collaborazione tra gruppi di utenti specifici, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="ccfe8-106">Ciò può includere situazioni o scenari in cui si desidera limitare la comunicazione e la collaborazione tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="ccfe8-107">Ciò può includere anche situazioni in cui è necessario limitare la comunicazione e la collaborazione tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="ccfe8-108">Le barriere informative sono supportate in Microsoft teams, SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="ccfe8-109">Un amministratore di conformità o di barriere informative può definire criteri che consentano o impediscano le comunicazioni tra gruppi di utenti in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="ccfe8-110">I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="ccfe8-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="ccfe8-111">Gli utenti del gruppo Day Trader non devono comunicare o condividere file con il team di marketing</span><span class="sxs-lookup"><span data-stu-id="ccfe8-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="ccfe8-112">Il personale finanziario che lavora su informazioni aziendali riservate non deve comunicare o condividere file con determinati gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="ccfe8-113">Un team interno con materiale segreto commerciale non deve chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ccfe8-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="ccfe8-114">Un team di ricerca deve chiamare o chattare online solo con un team di sviluppo del prodotto</span><span class="sxs-lookup"><span data-stu-id="ccfe8-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="ccfe8-115">Configurare le barriere informative per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ccfe8-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="ccfe8-116">Utilizzare la procedura seguente per configurare le barriere informative per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="ccfe8-116">Use the following steps to configure information barriers for your organization:</span></span>

![Passaggi delle informazioni sulla soluzione dei rischi Insider](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="ccfe8-118">Informazioni sulle [barriere informative](information-barriers.md) in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ccfe8-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="ccfe8-119">Configurare i [prerequisiti e le autorizzazioni](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="ccfe8-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="ccfe8-120">Segmentare [gli utenti nell'organizzazione](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="ccfe8-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="ccfe8-121">Creare e configurare i [criteri di barriera delle informazioni](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="ccfe8-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="ccfe8-122">Applicare i [criteri di barriera delle informazioni](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="ccfe8-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="ccfe8-123">Altre informazioni sulle barriere informative</span><span class="sxs-lookup"><span data-stu-id="ccfe8-123">More information about information barriers</span></span>

- [<span data-ttu-id="ccfe8-124">Attributi per i criteri delle barriere informative</span><span class="sxs-lookup"><span data-stu-id="ccfe8-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="ccfe8-125">Modificare o rimuovere i criteri di barriera delle informazioni</span><span class="sxs-lookup"><span data-stu-id="ccfe8-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)