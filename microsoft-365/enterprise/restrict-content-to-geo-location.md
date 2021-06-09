---
title: Limitare il contenuto del sito di SharePoint a una posizione geografica
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In questo articolo viene illustrato come limitare SharePoint siti a una posizione geografica specificata in un ambiente multi-geografico.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927265"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="2fb18-103">Limitare il contenuto del sito di SharePoint a una posizione geografica</span><span class="sxs-lookup"><span data-stu-id="2fb18-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="2fb18-104">In alcuni casi è possibile applicare a un sito e il contenuto del file per mantenere la posizione geografica in cui è stato creato il sito, e non lo spostamento del sito o impedire la memorizzazione nella cache del contenuto del sito in un'altra posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="2fb18-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="2fb18-105">È possibile farlo usando il cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con il parametro **RestrictedToGeo**.</span><span class="sxs-lookup"><span data-stu-id="2fb18-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="2fb18-106">Questo parametro ha un valore predefinito NULL, ma è possibile sostituirlo con una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fb18-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="2fb18-107">Restrizione</span><span class="sxs-lookup"><span data-stu-id="2fb18-107">Restriction</span></span>|<span data-ttu-id="2fb18-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb18-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="2fb18-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="2fb18-109">NoRestriction</span></span>|<span data-ttu-id="2fb18-110">Il sito può essere spostato in un'altra posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="2fb18-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="2fb18-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="2fb18-111">BlockMoveOnly</span></span>|<span data-ttu-id="2fb18-112">I siti non possono essere spostati in un'altra posizione geografica, ma il contenuto dei siti può essere memorizzato nella cache in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="2fb18-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="2fb18-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="2fb18-113">BlockFull</span></span>|<span data-ttu-id="2fb18-114">I siti non possono essere spostati in un'altra posizione geografica e l’intero contenuto del file non viene memorizzato nella cache in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="2fb18-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="2fb18-115">Il titolo dei file (raccolto dal contenuto), il nome del file e altre sue proprietà possono comunque essere memorizzate nella cache in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="2fb18-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="2fb18-116">Il contenuto del sito prima che fosse configurato per BlockFull, potrebbe continuare a essere memorizzato nella cache in altre località geografiche.</span><span class="sxs-lookup"><span data-stu-id="2fb18-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="2fb18-117">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2fb18-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="2fb18-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2fb18-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`