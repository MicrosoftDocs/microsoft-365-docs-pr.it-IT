---
title: Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Dispositivi di bordo di Windows 10 in modo che possano inviare i dati del sensore alle soluzioni di conformità di Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769643"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="42ce3-103">Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="42ce3-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="42ce3-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="42ce3-104">**Applies to:**</span></span>
- [<span data-ttu-id="42ce3-105">Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="42ce3-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="42ce3-106">I dispositivi nell'organizzazione devono essere configurati in modo che il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint possa ottenere i dati dei sensori.</span><span class="sxs-lookup"><span data-stu-id="42ce3-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="42ce3-107">Sono disponibili diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="42ce3-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="42ce3-108">Sono supportati gli strumenti e i metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="42ce3-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="42ce3-109">criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="42ce3-109">group policy</span></span>
- <span data-ttu-id="42ce3-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42ce3-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="42ce3-111">Gestione dei dispositivi mobili (tra cui Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="42ce3-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="42ce3-112">script locale</span><span class="sxs-lookup"><span data-stu-id="42ce3-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="42ce3-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="42ce3-113">In this section</span></span>
<span data-ttu-id="42ce3-114">Argomento</span><span class="sxs-lookup"><span data-stu-id="42ce3-114">Topic</span></span> | <span data-ttu-id="42ce3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42ce3-115">Description</span></span>
:---|:---
[<span data-ttu-id="42ce3-116">Dispositivi di bordo di Windows 10 con criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="42ce3-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="42ce3-117">Utilizzare criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="42ce3-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="42ce3-118">Dispositivi di bordo di Windows con Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42ce3-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="42ce3-119">È possibile utilizzare Microsoft endpoint Configuration Manager (Current Branch) versione 1606 o Microsoft endpoint Configuration Manager (Current Branch) versione 1602 o versioni precedenti per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="42ce3-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="42ce3-120">Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="42ce3-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="42ce3-121">Utilizzare gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42ce3-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="42ce3-122">Dispositivi di bordo di Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="42ce3-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="42ce3-123">Informazioni su come utilizzare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="42ce3-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="42ce3-124">Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo</span><span class="sxs-lookup"><span data-stu-id="42ce3-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="42ce3-125">Informazioni su come utilizzare il pacchetto di configurazione per configurare i dispositivi VDI.</span><span class="sxs-lookup"><span data-stu-id="42ce3-125">Learn how to use the configuration package to configure VDI devices.</span></span>
