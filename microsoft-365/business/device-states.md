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
description: Informazioni sui vari stati dei dispositivi nell'elenco Azioni dispositivo nella home page dell'amministratore in Microsoft 365 per le aziende.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471180"
---
# <a name="device-states"></a><span data-ttu-id="c29a6-103">Stati dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c29a6-103">Device states</span></span>

<span data-ttu-id="c29a6-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c29a6-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c29a6-105">Ai dispositivi inclusi nell'elenco **Azioni dispositivo** (home page di amministrazione \> **Azioni dispositivo**) possono essere assegnati gli stati seguenti.</span><span class="sxs-lookup"><span data-stu-id="c29a6-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="c29a6-107">**Stato**</span><span class="sxs-lookup"><span data-stu-id="c29a6-107">**Status**</span></span>|<span data-ttu-id="c29a6-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c29a6-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c29a6-109">Gestito da Intune</span><span class="sxs-lookup"><span data-stu-id="c29a6-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="c29a6-110">Gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c29a6-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="c29a6-111">Disattivazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="c29a6-111">Retire pending</span></span>  <br/> |<span data-ttu-id="c29a6-112">Microsoft 365 Business Premium si prepara a rimuovere i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c29a6-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c29a6-113">Disattivazione in corso</span><span class="sxs-lookup"><span data-stu-id="c29a6-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="c29a6-114">Microsoft 365 Business Premium sta attualmente rimuovendo i dati aziendali dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c29a6-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c29a6-115">Disattivazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="c29a6-115">Retire failed</span></span>  <br/> | <span data-ttu-id="c29a6-116">L'azione di rimozione dei dati aziendali non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c29a6-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="c29a6-117">Ritiro annullato</span><span class="sxs-lookup"><span data-stu-id="c29a6-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="c29a6-118">L'azione di ritiro è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="c29a6-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="c29a6-119">Cancellazione dei dati in sospeso</span><span class="sxs-lookup"><span data-stu-id="c29a6-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="c29a6-120">In attesa dell'avvio del ripristino delle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="c29a6-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="c29a6-121">Cancellazione dei dati in corso</span><span class="sxs-lookup"><span data-stu-id="c29a6-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="c29a6-122">Il ripristino delle impostazioni predefinite è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="c29a6-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="c29a6-123">Cancellazione dei dati non riuscita</span><span class="sxs-lookup"><span data-stu-id="c29a6-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="c29a6-124">Impossibile eseguire il ripristino delle impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="c29a6-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="c29a6-125">Cancellazione annullata</span><span class="sxs-lookup"><span data-stu-id="c29a6-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="c29a6-126">Cancellazione in fabbrica annullata.</span><span class="sxs-lookup"><span data-stu-id="c29a6-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="c29a6-127">Non integro</span><span class="sxs-lookup"><span data-stu-id="c29a6-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="c29a6-128">Un'azione è in sospeso (o in corso), ma il dispositivo non è archiviato da oltre 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="c29a6-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="c29a6-129">Eliminazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="c29a6-129">Delete pending</span></span>  <br/> |<span data-ttu-id="c29a6-130">L'azione di eliminazione è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c29a6-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="c29a6-131">Rilevato</span><span class="sxs-lookup"><span data-stu-id="c29a6-131">Discovered</span></span>  <br/> |<span data-ttu-id="c29a6-132">Microsoft 365 Business Premium ha rilevato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c29a6-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
