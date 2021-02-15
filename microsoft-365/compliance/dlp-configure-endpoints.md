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
description: Eseguire l'onboarded dei dispositivi Windows 10 in modo che possano inviare i dati dei sensori alle soluzioni di conformità di Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769643"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="a1a22-103">Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a1a22-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="a1a22-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a1a22-104">**Applies to:**</span></span>
- [<span data-ttu-id="a1a22-105">Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a1a22-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="a1a22-106">I dispositivi dell'organizzazione devono essere configurati in modo che il servizio di prevenzione della perdita dei dati degli endpoint di Microsoft 365 possa ottenere i dati dei sensori.</span><span class="sxs-lookup"><span data-stu-id="a1a22-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="a1a22-107">Esistono diversi metodi e strumenti di distribuzione che puoi usare per configurare i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1a22-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="a1a22-108">Sono supportati gli strumenti e i metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1a22-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="a1a22-109">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="a1a22-109">group policy</span></span>
- <span data-ttu-id="a1a22-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a1a22-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="a1a22-111">Gestione di dispositivi mobili (incluso Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="a1a22-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="a1a22-112">script locale</span><span class="sxs-lookup"><span data-stu-id="a1a22-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a1a22-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a1a22-113">In this section</span></span>
<span data-ttu-id="a1a22-114">Argomento</span><span class="sxs-lookup"><span data-stu-id="a1a22-114">Topic</span></span> | <span data-ttu-id="a1a22-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1a22-115">Description</span></span>
:---|:---
[<span data-ttu-id="a1a22-116">Onboard dei dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="a1a22-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="a1a22-117">Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a1a22-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a1a22-118">Onboard dei dispositivi Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a1a22-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="a1a22-119">Puoi usare Microsoft Endpoint Configuration Manager (current branch) versione 1606 o Microsoft Endpoint Configuration Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a1a22-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a1a22-120">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="a1a22-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="a1a22-121">Usa gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1a22-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="a1a22-122">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="a1a22-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="a1a22-123">Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a1a22-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="a1a22-124">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="a1a22-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="a1a22-125">Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.</span><span class="sxs-lookup"><span data-stu-id="a1a22-125">Learn how to use the configuration package to configure VDI devices.</span></span>
