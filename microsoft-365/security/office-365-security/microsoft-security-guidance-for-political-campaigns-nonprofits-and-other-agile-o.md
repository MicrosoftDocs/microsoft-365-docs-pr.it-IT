---
title: Guida sulla sicurezza Microsoft per campagne politiche e organizzazioni no profit
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: "Riepilogo: indicazioni relative alla pianificazione e all'implementazione per organizzazioni dinamiche con un profilo maggiormente a rischio."
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 76680ef5b21ae80525a7158ca0473cf82bd154d7
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406329"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="7bb8f-103">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile</span><span class="sxs-lookup"><span data-stu-id="7bb8f-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7bb8f-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="7bb8f-104">**Applies to**</span></span>
- [<span data-ttu-id="7bb8f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7bb8f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7bb8f-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="7bb8f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="7bb8f-107">**Riepilogo:** indicazioni relative alla pianificazione e all'implementazione per organizzazioni dinamiche con un profilo maggiormente a rischio.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="7bb8f-p101">Questa guida è utile se la propria organizzazione è agile, si dispone di un piccolo team IT e il proprio profilo è più a rischio rispetto alla media. Questa soluzione mostra come creare rapidamente un ambiente con i servizi cloud essenziali che includono controlli della sicurezza. Questa guida comprende suggerimenti sulla sicurezza per proteggere i dati, le identità, i messaggi di posta elettronica e l'accesso dai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="7bb8f-111">Guida alla soluzione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7bb8f-111">Security solution guidance</span></span>

<span data-ttu-id="7bb8f-p102">Questa guida descrive come implementare un ambiente cloud protetto. Può essere usata da qualsiasi organizzazione. Include informazioni aggiuntive per le organizzazioni Agile con accesso BYOD e account guest. È possibile usare questa guida come un punto di partenza per la progettazione del proprio ambiente. I commenti e suggerimenti degli utenti sono molto apprezzati e possono essere inviati all'indirizzo [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7bb8f-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="7bb8f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7bb8f-117">Item</span></span>|<span data-ttu-id="7bb8f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bb8f-118">Description</span></span>|
|---|---|
|<span data-ttu-id="7bb8f-119">**Guida alla sicurezza Microsoft per le campagne politiche**</span><span class="sxs-lookup"><span data-stu-id="7bb8f-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="7bb8f-120">[![Anteprima per il set di poster ridotto.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="7bb8f-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="7bb8f-p103">La seguente guida utilizza un esempio di organizzazione della campagna politica. Utilizzare questa guida come punto di partenza per qualsiasi ambiente.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="7bb8f-124">**Guida alla sicurezza Microsoft per le organizzazioni no profit**</span><span class="sxs-lookup"><span data-stu-id="7bb8f-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="7bb8f-125">[![Immagine di anteprima per file scaricabile](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="7bb8f-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7bb8f-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="7bb8f-p104">Questa guida è stata leggermente modificata per le organizzazioni no profit. Ad esempio, fa riferimento ai piani di Office 365 Nonprofit. Le indicazioni tecniche sono identiche a quelle fornite nella guida alle soluzioni per le campagne politiche.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="7bb8f-130">Guide all'ambiente di test</span><span class="sxs-lookup"><span data-stu-id="7bb8f-130">Test Lab Guides</span></span>

<span data-ttu-id="7bb8f-131">Per creare un ambiente di sviluppo/test per questa soluzione, utilizzare le guide di lab di test seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bb8f-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="7bb8f-132">Configurare gruppi e utenti per un ambiente di sviluppo/test per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="7bb8f-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="7bb8f-133">Creare sottoscrizioni di prova per Office 365 ed EMS, quindi creare gruppi e utenti per una campagna politica rappresentativa.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="7bb8f-134">Creare siti del team in un ambiente di sviluppo/test per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="7bb8f-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="7bb8f-135">Creare quattro siti del team SharePoint Online con livelli di sicurezza Dati interni, Dati privati, Dati riservati e Dati estremamente riservati.</span><span class="sxs-lookup"><span data-stu-id="7bb8f-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="7bb8f-136">Per ulteriori informazioni sulle funzionalità di protezione per una dimostrazione o modello di verifica, vedere [Guida al lab test per Office 365](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span><span class="sxs-lookup"><span data-stu-id="7bb8f-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7bb8f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bb8f-137">See Also</span></span>

[<span data-ttu-id="7bb8f-138">Risorse sull'architettura IT del cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bb8f-138">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
