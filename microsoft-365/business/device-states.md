---
title: Stati dei dispositivi
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Informazioni sui vari Stati del dispositivo nell'elenco delle azioni dei dispositivi in admin Home in Microsoft 365 for business.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471180"
---
# <a name="device-states"></a><span data-ttu-id="801f4-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="801f4-103">Device states</span></span>

<span data-ttu-id="801f4-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="801f4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="801f4-105">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="801f4-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="801f4-107">**Stato**</span><span class="sxs-lookup"><span data-stu-id="801f4-107">**Status**</span></span>|<span data-ttu-id="801f4-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="801f4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="801f4-109">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="801f4-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="801f4-110">Gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="801f4-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="801f4-111">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="801f4-111">Retire pending</span></span>  <br/> |<span data-ttu-id="801f4-112">Microsoft 365 Business Premium si prepara a rimuovere i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="801f4-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="801f4-113">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="801f4-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="801f4-114">Microsoft 365 Business Premium è attualmente in fase di rimozione dei dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="801f4-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="801f4-115">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="801f4-115">Retire failed</span></span>  <br/> | <span data-ttu-id="801f4-116">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="801f4-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="801f4-117">Ritiro annullato</span><span class="sxs-lookup"><span data-stu-id="801f4-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="801f4-118">L'azione ritirata è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="801f4-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="801f4-119">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="801f4-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="801f4-120">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="801f4-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="801f4-121">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="801f4-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="801f4-122">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="801f4-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="801f4-123">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="801f4-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="801f4-124">Impossibile eseguire la reimpostazione di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="801f4-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="801f4-125">Cancellazione annullata</span><span class="sxs-lookup"><span data-stu-id="801f4-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="801f4-126">Il wipe di fabbrica è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="801f4-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="801f4-127">Non integro</span><span class="sxs-lookup"><span data-stu-id="801f4-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="801f4-128">Un'azione è in sospeso (o in corso), ma il dispositivo non è stato archiviato per 30 + giorni.</span><span class="sxs-lookup"><span data-stu-id="801f4-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="801f4-129">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="801f4-129">Delete pending</span></span>  <br/> |<span data-ttu-id="801f4-130">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="801f4-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="801f4-131">Rilevato</span><span class="sxs-lookup"><span data-stu-id="801f4-131">Discovered</span></span>  <br/> |<span data-ttu-id="801f4-132">Microsoft 365 Business Premium ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="801f4-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
