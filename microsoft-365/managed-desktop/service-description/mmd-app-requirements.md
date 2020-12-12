---
title: Requisiti per le app di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
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
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="89fef-103">Requisiti per le app di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="89fef-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="89fef-104">Microsoft Managed Desktop richiede che i dispositivi vengano gestiti utilizzando un approccio specifico per garantire le prestazioni, l'affidabilità e la facilità di utilizzo dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="89fef-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="89fef-105">Area di gestione</span><span class="sxs-lookup"><span data-stu-id="89fef-105">Management area</span></span>  |<span data-ttu-id="89fef-106">Approccio Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="89fef-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="89fef-107">Configurazione del dispositivo o gestione dei criteri</span><span class="sxs-lookup"><span data-stu-id="89fef-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="89fef-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="89fef-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="89fef-109">Gestione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="89fef-109">Application management</span></span>     | <span data-ttu-id="89fef-110">Microsoft Intune e portale aziendale</span><span class="sxs-lookup"><span data-stu-id="89fef-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="89fef-111">Distribuzione del driver</span><span class="sxs-lookup"><span data-stu-id="89fef-111">Driver deployment</span></span>     |  <span data-ttu-id="89fef-112">Driver inclusi nel dispositivo, Windows Update o Intune</span><span class="sxs-lookup"><span data-stu-id="89fef-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="89fef-113">Sicurezza del dispositivo</span><span class="sxs-lookup"><span data-stu-id="89fef-113">Device security</span></span>     | <span data-ttu-id="89fef-114">Vedere [sicurezza del dispositivo](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="89fef-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="89fef-115">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="89fef-115">Identity and access management</span></span>     | <span data-ttu-id="89fef-116">Vedere [gestione delle identità e degli accessi](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="89fef-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="89fef-117">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="89fef-117">Network security</span></span>     | <span data-ttu-id="89fef-118">Vedere [Network Security](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="89fef-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="89fef-119">Sicurezza delle informazioni</span><span class="sxs-lookup"><span data-stu-id="89fef-119">Information security</span></span>     |  <span data-ttu-id="89fef-120">Visualizzare la [sicurezza delle informazioni](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="89fef-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="89fef-121">Ripristino dei dati</span><span class="sxs-lookup"><span data-stu-id="89fef-121">Data recovery</span></span>     | <span data-ttu-id="89fef-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="89fef-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="89fef-123">Produttività di base</span><span class="sxs-lookup"><span data-stu-id="89fef-123">Core productivity</span></span>     | <span data-ttu-id="89fef-124">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="89fef-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="89fef-125">Browser</span><span class="sxs-lookup"><span data-stu-id="89fef-125">Browser</span></span>     | <span data-ttu-id="89fef-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89fef-126">Microsoft Edge</span></span>        |




<span data-ttu-id="89fef-127">Microsoft Managed Desktop potrebbe monitorare il software in esecuzione su dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="89fef-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="89fef-128">Se la gestione dei dispositivi, la sicurezza, le prestazioni o l'affidabilità del dispositivo incidono negativamente, potrebbe essere necessario richiedere un' [eccezione al piano di servizio](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="89fef-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
