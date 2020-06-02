---
title: Proteggere i dispositivi Windows 10
f1.keywords:
- CSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Informazioni su come configurare le impostazioni del criterio di dispositivo predefinito che qualsiasi dispositivo Windows 10 riceverà al momento dell'accesso al proprio account aziendale o dell'Istituto di istruzione.
ms.openlocfilehash: 03ae86861ddb0cb83cd39b7834f19e01bf3e99e2
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470628"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="997a4-103">Proteggere i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="997a4-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="997a4-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="997a4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="997a4-105">Le impostazioni configurate qui fanno parte dei criteri predefiniti per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="997a4-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="997a4-106">Tutti gli utenti che si connettono a un dispositivo Windows 10, inclusi i dispositivi mobili e i PC, accedendo con il proprio account di lavoro riceveranno automaticamente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="997a4-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="997a4-107">È consigliabile accettare i criteri predefiniti durante l'installazione e aggiungere in un secondo momento i criteri relativi a gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="997a4-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="997a4-108">Impostazioni per la protezione di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="997a4-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="997a4-p102">Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="997a4-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="997a4-111">Impostazione</span><span class="sxs-lookup"><span data-stu-id="997a4-111">Setting</span></span>  <br/> |<span data-ttu-id="997a4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="997a4-112">Description</span></span>  <br/> |
|<span data-ttu-id="997a4-113">Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="997a4-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="997a4-114">Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="997a4-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="997a4-115">Protegge i PC dalle minacce del Web in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="997a4-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="997a4-116">Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.</span><span class="sxs-lookup"><span data-stu-id="997a4-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="997a4-117">Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="997a4-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="997a4-p103">Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.</span><span class="sxs-lookup"><span data-stu-id="997a4-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="997a4-121">Consenti agli utenti di scaricare app da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="997a4-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="997a4-p104">Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  </span><span class="sxs-lookup"><span data-stu-id="997a4-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="997a4-124">Consenti agli utenti di accedere a Cortana</span><span class="sxs-lookup"><span data-stu-id="997a4-124">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="997a4-125">Cortana può essere molto utile.</span><span class="sxs-lookup"><span data-stu-id="997a4-125">Cortana can be very helpful!</span></span> <span data-ttu-id="997a4-126">Cortana è in grado di abilitare o disabilitare le impostazioni per l'utente, fornire indicazioni e assicurarsi di essere puntuali per gli appuntamenti, in modo da mantenere **questa impostazione per** impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="997a4-126">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="997a4-127">Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows</span><span class="sxs-lookup"><span data-stu-id="997a4-127">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="997a4-128">I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="997a4-128">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="997a4-129">Mantieni automaticamente aggiornati i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="997a4-129">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="997a4-130">Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="997a4-130">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

