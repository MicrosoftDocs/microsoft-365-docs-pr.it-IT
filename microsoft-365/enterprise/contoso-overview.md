---
title: Panoramica di Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sulla società Contoso Corporation e sulla struttura a livelli dei suoi uffici nel mondo.
ms.openlocfilehash: 856363881c749b06a530dc7cc4f0eb82dc155054
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068298"
---
# <a name="overview-of-the-contoso-corporation"></a><span data-ttu-id="ca544-103">Panoramica di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="ca544-103">Overview of the Contoso Corporation</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

<span data-ttu-id="ca544-p101">Contoso Corporation è un’organizzazione multinazionale con sede a Parigi, in Francia. È un’azienda conglomerata di produzione, vendita e supporto con oltre 100.000 prodotti.</span><span class="sxs-lookup"><span data-stu-id="ca544-p101">The Contoso Corporation is a multi-national business with headquarters in Paris, France. It is a conglomerate manufacturing, sales, and support organization with over 100,000 products.</span></span>

## <a name="contoso-around-the-world"></a><span data-ttu-id="ca544-107">Contoso nel mondo</span><span class="sxs-lookup"><span data-stu-id="ca544-107">Contoso around the world</span></span>

<span data-ttu-id="ca544-108">Nella figura 1 viene mostrata la sede di Parigi e gli uffici secondari e gli hub regionali nei vari continenti.</span><span class="sxs-lookup"><span data-stu-id="ca544-108">Figure 1 shows the headquarters office in Paris and regional hub and satellite offices in various continents.</span></span>

![Uffici di Contoso in tutto il mondo](../media/contoso-overview/contoso-overview-fig1.png)

<span data-ttu-id="ca544-110">**Figura 1: Uffici di Contoso in tutto il mondo**</span><span class="sxs-lookup"><span data-stu-id="ca544-110">**Figure 1: Contoso's offices around the world**</span></span>
 
<span data-ttu-id="ca544-111">Gli uffici di Contoso di tutto il mondo seguono una struttura a tre livelli.</span><span class="sxs-lookup"><span data-stu-id="ca544-111">Contoso's offices around the world follow a three-tier design.</span></span>

- <span data-ttu-id="ca544-112">Sede centrale</span><span class="sxs-lookup"><span data-stu-id="ca544-112">Headquarters</span></span>

  <span data-ttu-id="ca544-p102">La sede di Contoso Corporation è un grande campus aziendale alla periferia di Parigi con decine di edifici per le strutture di amministrazione, ingegneria e produzione. Tutti i datacenter di Contoso e la presenza Internet sono ospitati nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="ca544-p102">The Contoso Corporation headquarters is a large corporate campus on the outskirts of Paris with dozens of buildings for administrative, engineering, and manufacturing facilities. All of Contoso's datacenters and its Internet presence are housed in the Paris headquarters.</span></span>

  <span data-ttu-id="ca544-115">La sede ha 25.000 dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ca544-115">The headquarters has 25,000 workers.</span></span>

- <span data-ttu-id="ca544-116">Hub regionali</span><span class="sxs-lookup"><span data-stu-id="ca544-116">Regional hubs</span></span>

  <span data-ttu-id="ca544-p103">Gli hub regionali servono una specifica area geografica del mondo con il 60% delle vendite e staff di supporto. Ogni hub regionale è connesso alla sede centrale di Parigi con un collegamento WAN con larghezza di banda elevata.</span><span class="sxs-lookup"><span data-stu-id="ca544-p103">Regional hub offices serve a specific region of the world with 60% sales and support staff. Each regional hub is connected to the Paris headquarters with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="ca544-119">Ogni hub regionale ha una media di 2.000 dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ca544-119">Each regional hub has an average of 2,000 workers.</span></span>

- <span data-ttu-id="ca544-120">Filiali</span><span class="sxs-lookup"><span data-stu-id="ca544-120">Satellite offices</span></span>

  <span data-ttu-id="ca544-p104">Gli uffici secondari ospitano l’80% del personale addetto alle vendite e al supporto tecnico e forniscono una presenza sul posto per i clienti di Contoso nelle città principali o nelle aree geografiche secondarie. Ogni ufficio secondario è collegato a un hub regionale con un collegamento WAN ad elevata larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="ca544-p104">Satellite offices contain 80% sales and support staff and provide an on-site presence for Contoso customers in key cities or sub-regions. Each satellite office is connected to a regional hub with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="ca544-123">Ogni filiale ha una media di 250 dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ca544-123">Each satellite office has an average of 250 workers.</span></span>

<span data-ttu-id="ca544-p105">Il 25% dei dipendenti di Contoso è esclusivamente mobile, con una percentuale maggiore di dipendenti solo mobile negli hub regionali e negli uffici secondari. Fornire un supporto migliore ai dipendenti che operano solo da dispositivi mobili è un obiettivo aziendale importante per Contoso.</span><span class="sxs-lookup"><span data-stu-id="ca544-p105">25% of Contoso's workforce is mobile-only, with a higher percentage of mobile-only workers in the regional hubs and satellite offices. Providing better support for mobile-only workers is an important business goal for Contoso.</span></span>

## <a name="design-considerations-for-microsoft-365-enterprise"></a><span data-ttu-id="ca544-126">Considerazioni sulla progettazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ca544-126">Design considerations for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ca544-127">Gli architetti IT di Contoso hanno identificato i requisiti e le considerazioni di progettazione seguenti per la distribuzione di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="ca544-127">Contoso's IT architects identified the following design requirements and considerations when deploying Microsoft 365 Enterprise:</span></span> 

- <span data-ttu-id="ca544-128">Più aree geografiche con requisiti di conformità alle normative locali</span><span class="sxs-lookup"><span data-stu-id="ca544-128">Multiple geographic locations with local regulations and compliance requirements</span></span>
- <span data-ttu-id="ca544-129">Un datacenter intranet centrale nella sede centrale e server di applicazioni locali che ospitano applicazioni line of business interne</span><span class="sxs-lookup"><span data-stu-id="ca544-129">A central intranet datacenter in the headquarters office and regional application servers that host internal line of business applications</span></span>
- <span data-ttu-id="ca544-130">Un'infrastruttura di Microsoft Endpoint Configuration Manager esistente</span><span class="sxs-lookup"><span data-stu-id="ca544-130">An existing Microsoft Endpoint Configuration Manager infrastructure</span></span>
- <span data-ttu-id="ca544-131">Una combinazione di dispositivi informatici client, tra cui Windows, Mac e Linux</span><span class="sxs-lookup"><span data-stu-id="ca544-131">A mix of client computing devices, including Windows, Mac, and Linux</span></span>
- <span data-ttu-id="ca544-132">Una combinazione di dispositivi mobili personali e di proprietà dell’azienda, tra cui smartphone e tablet iOS (iPhone e iPad) e Android</span><span class="sxs-lookup"><span data-stu-id="ca544-132">A mix of personal and company-owned mobile devices, including iOS (iPhone and iPad) and Android smart phones and tablets</span></span>
- <span data-ttu-id="ca544-133">Molti dipendenti remoti e che operano da dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ca544-133">Many remote and mobile workers</span></span>
- <span data-ttu-id="ca544-134">Molti partner commerciali</span><span class="sxs-lookup"><span data-stu-id="ca544-134">Many business partners</span></span>
- <span data-ttu-id="ca544-135">Una grande quantità di informazioni personali e dei clienti</span><span class="sxs-lookup"><span data-stu-id="ca544-135">A large amount of customer and personally identifiable information</span></span>
- <span data-ttu-id="ca544-136">Una grande quantità di proprietà intellettuale di alto valore, sotto forma di specifiche di progettazione per i prodotti e di segreti commerciali</span><span class="sxs-lookup"><span data-stu-id="ca544-136">A large amount of high-value intellectual property in the form of design specifications for products and manufacturing trade secrets</span></span>

## <a name="next-step"></a><span data-ttu-id="ca544-137">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ca544-137">Next step</span></span>

<span data-ttu-id="ca544-138">[Informazioni](contoso-infra-needs.md) sull'infrastruttura IT locale di Contoso Corporation e su come sono state gestite le sue esigenze aziendali con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ca544-138">[Learn](contoso-infra-needs.md) about the Contoso Corporation’s on-premises IT infrastructure and how their business needs were addressed with Microsoft 365 Enterprise.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca544-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca544-139">See also</span></span>

[<span data-ttu-id="ca544-140">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="ca544-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ca544-141">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="ca544-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)



