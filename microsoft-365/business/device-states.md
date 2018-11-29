---
title: Stati dei dispositivi
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Informazioni relative agli stati di dispositivi in Microsoft 365 Business.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868507"
---
# <a name="device-states"></a><span data-ttu-id="004df-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="004df-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="004df-104">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="004df-104">Device states</span></span>

<span data-ttu-id="004df-105">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="004df-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="004df-107">**Stato**</span><span class="sxs-lookup"><span data-stu-id="004df-107">**Status**</span></span>|<span data-ttu-id="004df-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="004df-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="004df-109">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="004df-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="004df-110">Gestito da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="004df-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="004df-111">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="004df-111">Retire pending</span></span>  <br/> |<span data-ttu-id="004df-112">Microsoft 365 Business sta predisponendo la rimozione dei dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004df-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="004df-113">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="004df-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="004df-114">Microsoft 365 Business sta attualmente rimuovendo i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004df-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="004df-115">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="004df-115">Retire failed</span></span>  <br/> | <span data-ttu-id="004df-116">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="004df-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="004df-117">Disattivazione annullata</span><span class="sxs-lookup"><span data-stu-id="004df-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="004df-118">L'azione di disattivazione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="004df-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="004df-119">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="004df-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="004df-120">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="004df-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="004df-121">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="004df-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="004df-122">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="004df-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="004df-123">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="004df-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="004df-124">Non è stato possibile ripristinare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="004df-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="004df-125">Cancellazione dei dati annullata</span><span class="sxs-lookup"><span data-stu-id="004df-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="004df-126">La cancellazione dei dati di fabbrica è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="004df-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="004df-127">Non integro</span><span class="sxs-lookup"><span data-stu-id="004df-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="004df-128">Indica che un'azione è in sospeso o in corso, ma il dispositivo non è stato archiviato per più di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="004df-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="004df-129">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="004df-129">Delete pending</span></span>  <br/> |<span data-ttu-id="004df-130">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="004df-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="004df-131">Rilevato</span><span class="sxs-lookup"><span data-stu-id="004df-131">Discovered</span></span>  <br/> |<span data-ttu-id="004df-132">Microsoft 365 Business ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004df-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
