---
title: Abilitazione di SharePoint Multi-Geo in una posizione geografica satellite
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: In questo articolo vengono fornite informazioni per gli amministratori globali o di SharePoint sull'abilitazione di SharePoint Multi-Geo nelle posizioni geografiche satellite.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691524"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="00fa3-103">Abilitazione di SharePoint Multi-Geo in una posizione geografica satellite</span><span class="sxs-lookup"><span data-stu-id="00fa3-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="00fa3-104">Questo articolo è diretto agli amministratori globali o di SharePoint che hanno creato una posizione satellite Multi-Geo **prima** che la funzionalità di SharePoint diventasse disponibile il 27 marzo 2019 e che non hanno abilitato SharePoint Multi-Geo nella posizione o nelle posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="00fa3-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="00fa3-105">Se è stata aggiunta una nuova posizione geografica **dopo il 27 marzo**, non è necessario seguire queste istruzioni, poiché la nuova posizione sarà stata già attivata per Multi-Geo di OneDrive e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="00fa3-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="00fa3-106">Queste istruzioni consentono di abilitare SharePoint nella posizione satellite, per consentire agli utenti di Multi-Geo di usufruire della funzionalità di OneDrive e SharePoint in O365.</span><span class="sxs-lookup"><span data-stu-id="00fa3-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="00fa3-107">Si tenga presente che si tratta di un processo non reversibile in modo autonomo.</span><span class="sxs-lookup"><span data-stu-id="00fa3-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="00fa3-108">Dopo aver impostato la modalità SPO, non sarà più possibile ripristinare il tenant in modalità Multi-Geo solo per OneDrive senza richiedere assistenza.</span><span class="sxs-lookup"><span data-stu-id="00fa3-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="00fa3-109">Impostare una posizione geografica in modalità SPO</span><span class="sxs-lookup"><span data-stu-id="00fa3-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="00fa3-110">Per impostare una posizione geografica in modalità SPO, connettersi alla posizione geografica scelta:</span><span class="sxs-lookup"><span data-stu-id="00fa3-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="00fa3-111">Aprire SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="00fa3-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="00fa3-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential</span><span class="sxs-lookup"><span data-stu-id="00fa3-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="00fa3-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="00fa3-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="00fa3-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="00fa3-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="00fa3-115">Questa operazione in genere richiede circa un'ora. Durante questo intervallo di tempo eseguiamo alcune operazioni in background nel servizio e nel tenant.</span><span class="sxs-lookup"><span data-stu-id="00fa3-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="00fa3-116">Dopo circa 1 ora, eseguire il comando Get-SPOMultiGeoExperience.</span><span class="sxs-lookup"><span data-stu-id="00fa3-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="00fa3-117">Servirà per visualizzare se la posizione geografica è in modalità di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="00fa3-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="00fa3-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="00fa3-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="00fa3-119">Alcune cache del servizio eseguono aggiornamenti ogni 24 ore, quindi è possibile durante questo periodo di 24 ore che la posizione geografica satellite occasionalmente si comporti come se fosse ancora in modalità ODB.</span><span class="sxs-lookup"><span data-stu-id="00fa3-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="00fa3-120">Questo non causa problemi tecnici.</span><span class="sxs-lookup"><span data-stu-id="00fa3-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="00fa3-121">Per ulteriori informazioni su SharePoint Multi-Geo visitare [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="00fa3-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


