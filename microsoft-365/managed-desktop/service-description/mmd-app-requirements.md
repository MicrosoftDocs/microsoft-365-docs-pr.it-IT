---
title: Microsoft Managed Desktop'app
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659715"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="a8b26-103">Microsoft Managed Desktop'app</span><span class="sxs-lookup"><span data-stu-id="a8b26-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="a8b26-104">Microsoft Managed Desktop è necessario gestire i dispositivi con un approccio specifico per garantire le prestazioni, l'affidabilità e la gestibilità dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a8b26-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="a8b26-105">Area di gestione</span><span class="sxs-lookup"><span data-stu-id="a8b26-105">Management area</span></span>  |<span data-ttu-id="a8b26-106">Microsoft Managed Desktop approccio</span><span class="sxs-lookup"><span data-stu-id="a8b26-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="a8b26-107">Configurazione dei dispositivi o gestione dei criteri</span><span class="sxs-lookup"><span data-stu-id="a8b26-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="a8b26-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a8b26-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="a8b26-109">Gestione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a8b26-109">Application management</span></span>     | <span data-ttu-id="a8b26-110">Microsoft Intune e Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="a8b26-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="a8b26-111">Distribuzione driver</span><span class="sxs-lookup"><span data-stu-id="a8b26-111">Driver deployment</span></span>     |  <span data-ttu-id="a8b26-112">Driver inclusi nel dispositivo, Windows Update o Intune</span><span class="sxs-lookup"><span data-stu-id="a8b26-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="a8b26-113">Sicurezza dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a8b26-113">Device security</span></span>     | <span data-ttu-id="a8b26-114">Vedi [Sicurezza del dispositivo](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="a8b26-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="a8b26-115">Gestione delle identità e degli accessi</span><span class="sxs-lookup"><span data-stu-id="a8b26-115">Identity and access management</span></span>     | <span data-ttu-id="a8b26-116">Vedere [Gestione di identità e accessi](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="a8b26-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="a8b26-117">Sicurezza della rete</span><span class="sxs-lookup"><span data-stu-id="a8b26-117">Network security</span></span>     | <span data-ttu-id="a8b26-118">Vedere [Sicurezza di rete](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="a8b26-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="a8b26-119">Sicurezza delle informazioni</span><span class="sxs-lookup"><span data-stu-id="a8b26-119">Information security</span></span>     |  <span data-ttu-id="a8b26-120">Vedere [Sicurezza delle informazioni](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="a8b26-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="a8b26-121">Ripristino dei dati</span><span class="sxs-lookup"><span data-stu-id="a8b26-121">Data recovery</span></span>     | <span data-ttu-id="a8b26-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a8b26-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="a8b26-123">Produttività di base</span><span class="sxs-lookup"><span data-stu-id="a8b26-123">Core productivity</span></span>     | <span data-ttu-id="a8b26-124">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b26-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="a8b26-125">Browser</span><span class="sxs-lookup"><span data-stu-id="a8b26-125">Browser</span></span>     | <span data-ttu-id="a8b26-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a8b26-126">Microsoft Edge</span></span>        |




<span data-ttu-id="a8b26-127">Microsoft Managed Desktop altro software in esecuzione nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="a8b26-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="a8b26-128">Se influisce negativamente sulla gestione dei dispositivi, sulla sicurezza, sulle prestazioni o sull'affidabilità dei dispositivi, potrebbe essere necessario richiedere [un'eccezione al piano di servizio.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="a8b26-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
