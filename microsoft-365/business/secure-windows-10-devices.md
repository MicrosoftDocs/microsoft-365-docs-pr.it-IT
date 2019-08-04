---
title: Proteggere i dispositivi Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: "Informazioni sull'impostazione predefinita e altre impostazioni per proteggere i dispositivi Windows 10. "
ms.openlocfilehash: b56aac0c760aa0e57d48683b5f1726c9add16d20
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074421"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="4077d-103">Proteggere i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="4077d-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="4077d-p101">Le impostazioni configurate qui fanno parte dei criteri predefiniti per i dispositivi Windows 10. Tutti gli utenti che si connettono a un dispositivo Windows 10, inclusi i dispositivi mobili e i PC, tramite il proprio account di lavoro riceveranno automaticamente queste impostazioni. È consigliabile accettare i criteri predefiniti durante l'installazione e aggiungere in un secondo momento i criteri relativi a gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4077d-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="4077d-107">Impostazioni per la protezione di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="4077d-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="4077d-p102">Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4077d-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4077d-110">Impostazione</span><span class="sxs-lookup"><span data-stu-id="4077d-110">Setting</span></span>  <br/> |<span data-ttu-id="4077d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4077d-111">Description</span></span>  <br/> |
|<span data-ttu-id="4077d-112">Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="4077d-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="4077d-113">Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="4077d-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="4077d-114">Protegge i PC dalle minacce del Web in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4077d-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="4077d-115">Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.</span><span class="sxs-lookup"><span data-stu-id="4077d-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="4077d-116">Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="4077d-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="4077d-p103">Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.</span><span class="sxs-lookup"><span data-stu-id="4077d-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="4077d-120">Consenti agli utenti di scaricare app da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4077d-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="4077d-p104">Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  </span><span class="sxs-lookup"><span data-stu-id="4077d-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="4077d-123">Consenti agli utenti di accedere a Cortana</span><span class="sxs-lookup"><span data-stu-id="4077d-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="4077d-p105">Cortana può risultare molto utile: è in grado di attivare o disattivare automaticamente le impostazioni, fornire indicazioni e assicurarsi che si sia puntuali agli appuntamenti, quindi questa impostazione è **attivata** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4077d-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="4077d-126">Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows</span><span class="sxs-lookup"><span data-stu-id="4077d-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="4077d-127">I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="4077d-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="4077d-128">Mantieni automaticamente aggiornati i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="4077d-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="4077d-129">Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="4077d-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

