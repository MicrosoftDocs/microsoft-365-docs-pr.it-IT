---
title: Stati dei dispositivi
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Informazioni sui vari stati dei dispositivi nell'elenco Azioni dispositivo nella home page dell'amministratore in Microsoft 365 per le aziende.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578468"
---
# <a name="device-states"></a><span data-ttu-id="a2d14-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a2d14-103">Device states</span></span>

<span data-ttu-id="a2d14-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a2d14-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a2d14-105">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="a2d14-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="a2d14-107">**Stato**</span><span class="sxs-lookup"><span data-stu-id="a2d14-107">**Status**</span></span>|<span data-ttu-id="a2d14-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a2d14-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2d14-109">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="a2d14-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="a2d14-110">Gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a2d14-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="a2d14-111">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="a2d14-111">Retire pending</span></span>  <br/> |<span data-ttu-id="a2d14-112">Microsoft 365 Business Premium si sta preparando per rimuovere i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2d14-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a2d14-113">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="a2d14-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="a2d14-114">Microsoft 365 Business Premium sta attualmente rimuovendo i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2d14-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a2d14-115">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="a2d14-115">Retire failed</span></span>  <br/> | <span data-ttu-id="a2d14-116">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a2d14-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="a2d14-117">Ritiro annullato</span><span class="sxs-lookup"><span data-stu-id="a2d14-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="a2d14-118">L'azione di ritiro è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="a2d14-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="a2d14-119">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="a2d14-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="a2d14-120">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="a2d14-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="a2d14-121">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="a2d14-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="a2d14-122">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="a2d14-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="a2d14-123">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="a2d14-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="a2d14-124">Impossibile eseguire la reimpostazione della factory.</span><span class="sxs-lookup"><span data-stu-id="a2d14-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="a2d14-125">Cancellazione annullata</span><span class="sxs-lookup"><span data-stu-id="a2d14-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="a2d14-126">Cancellazione in fabbrica annullata.</span><span class="sxs-lookup"><span data-stu-id="a2d14-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="a2d14-127">Non integro</span><span class="sxs-lookup"><span data-stu-id="a2d14-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="a2d14-128">Un'azione è in sospeso (o in corso), ma il dispositivo non è archiviato da più di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a2d14-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="a2d14-129">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="a2d14-129">Delete pending</span></span>  <br/> |<span data-ttu-id="a2d14-130">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="a2d14-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="a2d14-131">Rilevato</span><span class="sxs-lookup"><span data-stu-id="a2d14-131">Discovered</span></span>  <br/> |<span data-ttu-id="a2d14-132">Microsoft 365 Business Premium ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2d14-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
