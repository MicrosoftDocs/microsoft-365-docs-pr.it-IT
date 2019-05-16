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
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072721"
---
# <a name="device-states"></a><span data-ttu-id="2835f-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="2835f-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="2835f-104">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="2835f-104">Device states</span></span>

<span data-ttu-id="2835f-105">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="2835f-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="2835f-107">**Stato**</span><span class="sxs-lookup"><span data-stu-id="2835f-107">**Status**</span></span>|<span data-ttu-id="2835f-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2835f-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2835f-109">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="2835f-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="2835f-110">Gestito da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="2835f-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="2835f-111">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="2835f-111">Retire pending</span></span>  <br/> |<span data-ttu-id="2835f-112">Microsoft 365 Business sta predisponendo la rimozione dei dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2835f-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2835f-113">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="2835f-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="2835f-114">Microsoft 365 Business sta attualmente rimuovendo i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2835f-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2835f-115">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="2835f-115">Retire failed</span></span>  <br/> | <span data-ttu-id="2835f-116">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2835f-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="2835f-117">Disattivazione annullata</span><span class="sxs-lookup"><span data-stu-id="2835f-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="2835f-118">L'azione di disattivazione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="2835f-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="2835f-119">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="2835f-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="2835f-120">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="2835f-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="2835f-121">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="2835f-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="2835f-122">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="2835f-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="2835f-123">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="2835f-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="2835f-124">Non è stato possibile ripristinare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="2835f-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="2835f-125">Cancellazione dei dati annullata</span><span class="sxs-lookup"><span data-stu-id="2835f-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="2835f-126">La cancellazione dei dati di fabbrica è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="2835f-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="2835f-127">Non integro</span><span class="sxs-lookup"><span data-stu-id="2835f-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="2835f-128">Indica che un'azione è in sospeso o in corso, ma il dispositivo non è stato archiviato per più di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="2835f-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="2835f-129">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="2835f-129">Delete pending</span></span>  <br/> |<span data-ttu-id="2835f-130">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="2835f-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="2835f-131">Rilevato</span><span class="sxs-lookup"><span data-stu-id="2835f-131">Discovered</span></span>  <br/> |<span data-ttu-id="2835f-132">Microsoft 365 Business ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2835f-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
