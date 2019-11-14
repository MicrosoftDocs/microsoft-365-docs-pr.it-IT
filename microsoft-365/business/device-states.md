---
title: Stati dei dispositivi
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Informazioni sugli stati dei dispositivi in Microsoft 365 business.
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320209"
---
# <a name="device-states"></a><span data-ttu-id="84703-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="84703-103">Device states</span></span>

<span data-ttu-id="84703-104">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="84703-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="84703-106">**Stato**</span><span class="sxs-lookup"><span data-stu-id="84703-106">**Status**</span></span>|<span data-ttu-id="84703-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="84703-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84703-108">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="84703-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="84703-109">Gestito da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="84703-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="84703-110">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="84703-110">Retire pending</span></span>  <br/> |<span data-ttu-id="84703-111">Microsoft 365 Business sta predisponendo la rimozione dei dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84703-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="84703-112">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="84703-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="84703-113">Microsoft 365 Business sta attualmente rimuovendo i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84703-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="84703-114">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="84703-114">Retire failed</span></span>  <br/> | <span data-ttu-id="84703-115">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="84703-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="84703-116">Ritiro annullato</span><span class="sxs-lookup"><span data-stu-id="84703-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="84703-117">L'azione ritirata è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="84703-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="84703-118">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="84703-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="84703-119">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="84703-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="84703-120">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="84703-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="84703-121">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="84703-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="84703-122">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="84703-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="84703-123">Impossibile eseguire la reimpostazione di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="84703-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="84703-124">Cancellazione annullata</span><span class="sxs-lookup"><span data-stu-id="84703-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="84703-125">Il wipe di fabbrica è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="84703-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="84703-126">Non integro</span><span class="sxs-lookup"><span data-stu-id="84703-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="84703-127">Un'azione è in sospeso (o in corso), ma il dispositivo non è stato archiviato per 30 + giorni.</span><span class="sxs-lookup"><span data-stu-id="84703-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="84703-128">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="84703-128">Delete pending</span></span>  <br/> |<span data-ttu-id="84703-129">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="84703-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="84703-130">Rilevato</span><span class="sxs-lookup"><span data-stu-id="84703-130">Discovered</span></span>  <br/> |<span data-ttu-id="84703-131">Microsoft 365 Business ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84703-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
