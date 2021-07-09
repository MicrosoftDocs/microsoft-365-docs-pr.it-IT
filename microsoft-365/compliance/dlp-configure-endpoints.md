---
title: Metodi e strumenti di onboarding per Windows 10 dispositivi
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
description: Onboard Windows 10 dispositivi in modo che possano inviare i dati del sensore alle soluzioni Microsoft 365 conformità
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341701"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="28ab1-103">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="28ab1-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="28ab1-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="28ab1-104">**Applies to:**</span></span>
- [<span data-ttu-id="28ab1-105">Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="28ab1-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="28ab1-106">I dispositivi nell'organizzazione devono essere configurati in modo che il Microsoft 365 endpoint di prevenzione della perdita dei dati possa ottenere i dati del sensore da essi.</span><span class="sxs-lookup"><span data-stu-id="28ab1-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="28ab1-107">Esistono diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="28ab1-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="28ab1-108">Sono supportati gli strumenti e i metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="28ab1-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="28ab1-109">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="28ab1-109">group policy</span></span>
- <span data-ttu-id="28ab1-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="28ab1-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="28ab1-111">Gestione dei dispositivi mobili (Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="28ab1-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="28ab1-112">script locale</span><span class="sxs-lookup"><span data-stu-id="28ab1-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="28ab1-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="28ab1-113">In this section</span></span>
<span data-ttu-id="28ab1-114">Argomento</span><span class="sxs-lookup"><span data-stu-id="28ab1-114">Topic</span></span> | <span data-ttu-id="28ab1-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28ab1-115">Description</span></span>
:---|:---
[<span data-ttu-id="28ab1-116">Onboardare Windows 10 dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="28ab1-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="28ab1-117">Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="28ab1-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="28ab1-118">Onboard Windows dispositivi con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="28ab1-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="28ab1-119">Puoi usare Microsoft Endpoint Configuration Manager (current branch) versione 1606 o Microsoft Endpoint Configuration Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="28ab1-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="28ab1-120">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="28ab1-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="28ab1-121">Usa gli strumenti di gestione dei dispositivi mobili Microsoft Intune distribuire il pacchetto di configurazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28ab1-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="28ab1-122">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="28ab1-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="28ab1-123">Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="28ab1-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="28ab1-124">Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="28ab1-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="28ab1-125">Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.</span><span class="sxs-lookup"><span data-stu-id="28ab1-125">Learn how to use the configuration package to configure VDI devices.</span></span>