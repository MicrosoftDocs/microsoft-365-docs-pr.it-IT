---
title: Configurare eDiscovery per Microsoft 365 Multi-Geo
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Informazioni su come utilizzare il parametro Region per configurare eDiscovery per l'utilizzo nelle posizioni satellite in Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923721"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="c9ede-103">Configurazione di eDiscovery per Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="c9ede-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="c9ede-104">[Advanced eDiscovery funzionalità consentono](../compliance/overview-ediscovery-20.md) a un amministratore di eDiscovery multi-geo di eseguire ricerche in tutte le aree geografiche senza dover utilizzare un filtro di sicurezza "Area geografica".</span><span class="sxs-lookup"><span data-stu-id="c9ede-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="c9ede-105">I dati vengono esportati nell'istanza di Azure della posizione centrale del tenant multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="c9ede-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="c9ede-106">Senza funzionalità avanzate di eDiscovery, un responsabile di eDiscovery o un amministratore di un tenant multi-geografico sarà in grado di eseguire eDiscovery solo nella posizione centrale di tale tenant.</span><span class="sxs-lookup"><span data-stu-id="c9ede-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="c9ede-107">Per supportare la possibilità di eseguire eDiscovery per le posizioni satellite, tramite PowerShell è disponibile un nuovo parametro del filtro di sicurezza di conformità denominato "Area geografica".</span><span class="sxs-lookup"><span data-stu-id="c9ede-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="c9ede-108">Questo parametro può essere utilizzato dai tenant la cui posizione centrale si trova in Nord America, Europa o Asia Pacifico.</span><span class="sxs-lookup"><span data-stu-id="c9ede-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="c9ede-109">Advanced eDiscovery è consigliabile per i tenant la cui posizione centrale non si trova in Nord America, Europa o Asia Pacifico e che devono eseguire eDiscovery in posizioni geografiche satellite.</span><span class="sxs-lookup"><span data-stu-id="c9ede-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="c9ede-110">L'amministratore globale di Microsoft 365 deve assegnare le autorizzazioni di manager di eDiscovery per consentire ad altri di eseguire eDiscovery e assegnare un parametro "Area" nel filtro di sicurezza e conformità applicabile per specificare l'area per l'esecuzione di eDiscovery come posizione satellite, in caso contrario nessuna istanza di eDiscovery verrà eseguita per la posizione geografica satellite.</span><span class="sxs-lookup"><span data-stu-id="c9ede-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="c9ede-p103">Quando è impostato il ruolo di manager o amministratore di eDiscovery per una posizione satellite specifica, sarà possibile eseguire operazioni di ricerca eDiscovery solo per i siti di SharePoint e OneDrive che si trovano in tale posizione satellite. Se un manager o amministratore di eDiscovery tenta di cercare siti di SharePoint o OneDrive all'esterno della posizione satellite specificata, non visualizzerà alcun risultato. Inoltre, quando il manager o amministratore di eDiscovery di una posizione satellite attiva un'esportazione, i dati vengono esportati nell'istanza di Azure di quest'area. Ciò consente alle organizzazioni di rimanere conformi, non permettendo di esportare contenuti oltre i confini controllati.</span><span class="sxs-lookup"><span data-stu-id="c9ede-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ede-115">Tuttavia, se dovesse essere necessario per un manager di eDiscovery effettuare una ricerca in più posizioni satellite di SharePoint, sarà necessario creare un altro account utente per il manager di eDiscovery, specificando la posizione satellite alternativa in cui si trovano i siti di OneDrive o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9ede-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="c9ede-116">Per impostare il filtro di sicurezza di conformità per un'area geografica:</span><span class="sxs-lookup"><span data-stu-id="c9ede-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="c9ede-117">Connettersi a PowerShell per Centro sicurezza e conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9ede-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="c9ede-118">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ede-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="c9ede-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9ede-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="c9ede-120">Vedere l’articolo [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) per ulteriori parametri e sintassi.</span><span class="sxs-lookup"><span data-stu-id="c9ede-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>