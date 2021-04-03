---
title: Proteggere i dispositivi Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
description: Scopri come configurare le impostazioni del criterio dispositivo predefinito che qualsiasi dispositivo Windows 10 riceverà all'accesso al proprio account aziendale o dell'istituto di istruzione.
ms.openlocfilehash: 86db1c152f9f6ac1fe6093b4a55a74b69fbd8b0f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579975"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="eb77b-103">Proteggere i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="eb77b-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="eb77b-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="eb77b-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="eb77b-105">Le impostazioni configurate qui fanno parte dei criteri predefiniti per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eb77b-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="eb77b-106">Tutti gli utenti che connettono un dispositivo Windows 10, inclusi dispositivi mobili e PC, accedendo con il proprio account aziendale riceveranno automaticamente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="eb77b-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="eb77b-107">È consigliabile accettare i criteri predefiniti durante l'installazione e aggiungere in un secondo momento i criteri relativi a gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="eb77b-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="eb77b-108">Impostazioni per la protezione di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="eb77b-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="eb77b-p102">Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb77b-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eb77b-111">Impostazione</span><span class="sxs-lookup"><span data-stu-id="eb77b-111">Setting</span></span>  <br/> |<span data-ttu-id="eb77b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb77b-112">Description</span></span>  <br/> |
|<span data-ttu-id="eb77b-113">Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="eb77b-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="eb77b-114">Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="eb77b-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="eb77b-115">Protegge i PC dalle minacce del Web in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eb77b-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="eb77b-116">Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.</span><span class="sxs-lookup"><span data-stu-id="eb77b-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="eb77b-117">Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker</span><span class="sxs-lookup"><span data-stu-id="eb77b-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="eb77b-118">Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer.</span><span class="sxs-lookup"><span data-stu-id="eb77b-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="eb77b-119">Per altre informazioni, vedi Domande [frequenti su Bitlocker.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)</span><span class="sxs-lookup"><span data-stu-id="eb77b-119">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="eb77b-120">Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="eb77b-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="eb77b-p104">Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.</span><span class="sxs-lookup"><span data-stu-id="eb77b-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|