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
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400955"
---
# <a name="device-states"></a><span data-ttu-id="0a586-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="0a586-103">Device states</span></span>

<span data-ttu-id="0a586-104">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="0a586-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="0a586-106">**Stato**</span><span class="sxs-lookup"><span data-stu-id="0a586-106">**Status**</span></span>|<span data-ttu-id="0a586-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0a586-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a586-108">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="0a586-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="0a586-109">Gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0a586-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="0a586-110">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="0a586-110">Retire pending</span></span>  <br/> |<span data-ttu-id="0a586-111">Microsoft 365 Business Premium si prepara a rimuovere i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a586-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0a586-112">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="0a586-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="0a586-113">Microsoft 365 Business Premium è attualmente in fase di rimozione dei dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a586-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0a586-114">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a586-114">Retire failed</span></span>  <br/> | <span data-ttu-id="0a586-115">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0a586-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="0a586-116">Ritiro annullato</span><span class="sxs-lookup"><span data-stu-id="0a586-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="0a586-117">L'azione ritirata è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="0a586-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="0a586-118">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="0a586-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="0a586-119">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="0a586-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="0a586-120">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="0a586-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="0a586-121">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="0a586-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="0a586-122">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a586-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="0a586-123">Impossibile eseguire la reimpostazione di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="0a586-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="0a586-124">Cancellazione annullata</span><span class="sxs-lookup"><span data-stu-id="0a586-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="0a586-125">Il wipe di fabbrica è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="0a586-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="0a586-126">Non integro</span><span class="sxs-lookup"><span data-stu-id="0a586-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="0a586-127">Un'azione è in sospeso (o in corso), ma il dispositivo non è stato archiviato per 30 + giorni.</span><span class="sxs-lookup"><span data-stu-id="0a586-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="0a586-128">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="0a586-128">Delete pending</span></span>  <br/> |<span data-ttu-id="0a586-129">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="0a586-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="0a586-130">Rilevato</span><span class="sxs-lookup"><span data-stu-id="0a586-130">Discovered</span></span>  <br/> |<span data-ttu-id="0a586-131">Microsoft 365 Business Premium ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a586-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
