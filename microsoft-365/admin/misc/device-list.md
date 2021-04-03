---
title: File CSV elenco dispositivi
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Informazioni su come creare un file CSV per AutoPilot in Microsoft 365 per le aziende.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579219"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="d4a47-103">File CSV elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="d4a47-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="d4a47-104">Formato di file CSV dell'elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="d4a47-104">Device list .csv file format</span></span>

<span data-ttu-id="d4a47-105">Per gestire e distribuire i dispositivi tramite Windows Autopilot, è necessario un file CSV contenente informazioni specifiche sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d4a47-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="d4a47-106">Le colonne nel file elenco dispositivi devono avere le intestazioni seguenti nell'ordine specificato:</span><span class="sxs-lookup"><span data-stu-id="d4a47-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="d4a47-107">Colonna A: numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d4a47-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="d4a47-108">Colonna B: lasciare vuoto</span><span class="sxs-lookup"><span data-stu-id="d4a47-108">Column B: leave blank</span></span>

- <span data-ttu-id="d4a47-109">Colonna C: hash dell'hardware</span><span class="sxs-lookup"><span data-stu-id="d4a47-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="d4a47-110">È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d4a47-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="d4a47-111">Quando aggiungi dispositivi, devi anche aggiungerli a un profilo.</span><span class="sxs-lookup"><span data-stu-id="d4a47-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="d4a47-112">Un profilo viene usato per applicare profili di distribuzione AutoPilot a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d4a47-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d4a47-113">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="d4a47-113">Related articles</span></span>

[<span data-ttu-id="d4a47-114">Documentazione e risorse di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="d4a47-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="d4a47-115">Introduzione a Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="d4a47-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="d4a47-116">Gestire Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="d4a47-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
