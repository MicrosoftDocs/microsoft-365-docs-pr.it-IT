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
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898069"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="865c5-103">Proteggere i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="865c5-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="865c5-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="865c5-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="865c5-105">Le impostazioni configurate qui fanno parte dei criteri predefiniti per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="865c5-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="865c5-106">Tutti gli utenti che si connettono a un dispositivo Windows 10, inclusi i dispositivi mobili e i PC, accedendo con il proprio account di lavoro riceveranno automaticamente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="865c5-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="865c5-107">È consigliabile accettare i criteri predefiniti durante l'installazione e aggiungere in un secondo momento i criteri relativi a gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="865c5-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="865c5-108">Impostazioni per la protezione di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="865c5-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="865c5-p102">Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="865c5-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="865c5-111">Impostazione</span><span class="sxs-lookup"><span data-stu-id="865c5-111">Setting</span></span>  <br/> |<span data-ttu-id="865c5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="865c5-112">Description</span></span>  <br/> |
|<span data-ttu-id="865c5-113">Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="865c5-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="865c5-114">Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="865c5-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="865c5-115">Protegge i PC dalle minacce del Web in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="865c5-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="865c5-116">Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.</span><span class="sxs-lookup"><span data-stu-id="865c5-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="865c5-117">Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="865c5-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="865c5-p103">Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.</span><span class="sxs-lookup"><span data-stu-id="865c5-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="865c5-121">Consenti agli utenti di scaricare app da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="865c5-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="865c5-p104">Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  </span><span class="sxs-lookup"><span data-stu-id="865c5-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|