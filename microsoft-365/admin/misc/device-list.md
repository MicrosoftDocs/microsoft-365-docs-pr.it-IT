---
title: Elenco dispositivi CSV-file
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Informazioni su come creare un file CSV per AutoPilo Tin Microsoft 365 business.
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361357"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="93933-103">Elenco dispositivi CSV-file</span><span class="sxs-lookup"><span data-stu-id="93933-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="93933-104">Formato del file CSV elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="93933-104">Device list .csv file format</span></span>

<span data-ttu-id="93933-105">Per gestire e distribuire i dispositivi tramite Windows Autopilot, è necessario un file. csv contenente informazioni specifiche sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="93933-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="93933-106">Le colonne nel file dell'elenco dei dispositivi devono avere le seguenti intestazioni nell'ordine specificato:</span><span class="sxs-lookup"><span data-stu-id="93933-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="93933-107">Colonna A: numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="93933-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="93933-108">Colonna B: lasciare vuoto</span><span class="sxs-lookup"><span data-stu-id="93933-108">Column B: leave blank</span></span>

- <span data-ttu-id="93933-109">Colonna C: hash dell'hardware</span><span class="sxs-lookup"><span data-stu-id="93933-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="93933-110">È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="93933-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="93933-111">Quando si aggiungono dispositivi, è inoltre necessario aggiungerli a un profilo.</span><span class="sxs-lookup"><span data-stu-id="93933-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="93933-112">Un profilo viene utilizzato per applicare i profili di distribuzione dei piloti automatici a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="93933-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="93933-113">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="93933-113">Related articles</span></span>

[<span data-ttu-id="93933-114">Documentazione e risorse su Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="93933-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="93933-115">Introduzione a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="93933-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="93933-116">Gestire Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="93933-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
