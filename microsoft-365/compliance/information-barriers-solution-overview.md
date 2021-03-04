---
title: Barriere di informazioni in Microsoft 365
description: Informazioni su come configurare le barriere di informazioni in Microsoft 365.
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
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423597"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="dacdd-104">Barriere di informazioni in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dacdd-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="dacdd-105">Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni e supporta modi per limitare la comunicazione e la collaborazione tra gruppi specifici di utenti, se necessario.</span><span class="sxs-lookup"><span data-stu-id="dacdd-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="dacdd-106">Ciò può includere situazioni o scenari in cui si desidera limitare la comunicazione e la collaborazione tra due gruppi per evitare che si verifichi un conflitto di interesse nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dacdd-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="dacdd-107">Ciò può includere anche situazioni in cui è necessario limitare la comunicazione e la collaborazione tra alcune persone all'interno dell'organizzazione per proteggere le informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="dacdd-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="dacdd-108">Le barriere di informazioni sono supportate in Microsoft Teams, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="dacdd-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="dacdd-109">Un amministratore di conformità o un amministratore delle barriere di informazioni può definire criteri per consentire o impedire le comunicazioni tra gruppi di utenti in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dacdd-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="dacdd-110">I criteri delle barriere di informazioni possono essere usati in situazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="dacdd-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="dacdd-111">L'utente nel gruppo di distribuzione giornaliera non deve comunicare o condividere file con il team di marketing</span><span class="sxs-lookup"><span data-stu-id="dacdd-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="dacdd-112">Il personale finanziario che lavora su informazioni aziendali riservate non deve comunicare o condividere file con determinati gruppi all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dacdd-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="dacdd-113">Un team interno con materiale segreto commerciale non deve chiamare o chattare online con persone in determinati gruppi all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dacdd-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="dacdd-114">Un team di ricerca deve chiamare o chattare solo online con un team di sviluppo del prodotto</span><span class="sxs-lookup"><span data-stu-id="dacdd-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="dacdd-115">Configurare le barriere di informazioni per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dacdd-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="dacdd-116">Per configurare le barriere di informazioni per l'organizzazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dacdd-116">Use the following steps to configure information barriers for your organization:</span></span>

![Passaggi delle barriere di informazioni sulle soluzioni di rischio Insider](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="dacdd-118">Informazioni sulle [barriere di informazioni](information-barriers.md) in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dacdd-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="dacdd-119">Configurare [i prerequisiti e le autorizzazioni](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="dacdd-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="dacdd-120">Segmentare [gli utenti nell'organizzazione](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="dacdd-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="dacdd-121">Creare e configurare [i criteri delle barriere di informazioni](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="dacdd-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="dacdd-122">Applicare [i criteri delle barriere di informazioni](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="dacdd-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="dacdd-123">Ulteriori informazioni sulle barriere in fatto di informazioni</span><span class="sxs-lookup"><span data-stu-id="dacdd-123">More information about information barriers</span></span>

- [<span data-ttu-id="dacdd-124">Attributi per i criteri delle barriere informative</span><span class="sxs-lookup"><span data-stu-id="dacdd-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="dacdd-125">Modificare o rimuovere i criteri delle barriere di informazioni</span><span class="sxs-lookup"><span data-stu-id="dacdd-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)