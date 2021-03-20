---
title: Configurare Messaggi secondari per l'organizzazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: "Informazioni su come abilitare o disabilitare la funzionalità Messaggi secondari per tutti gli utenti o specifici dell'organizzazione tramite PowerShell di Exchange. "
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915903"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="b86e9-103">Configurare Messaggi secondari per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b86e9-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="b86e9-104">[Posta in arrivo evidenziata](../setup/configure-focused-inbox.md) sostituirà Messaggi secondari.</span><span class="sxs-lookup"><span data-stu-id="b86e9-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="b86e9-105">Ulteriori informazioni: [Aggiornamento in Posta in arrivo mirata e piani per Messaggi secondari](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="b86e9-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="b86e9-106">In quanto amministratore, potrebbe essere necessario gestire la funzionalità Messaggi secondari in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b86e9-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="b86e9-107">Per attivare o disattivare questa funzionalità per gli utenti dell'organizzazione, è necessario usare Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b86e9-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="b86e9-108">Gli utenti possono attivarlo/disattivarlo usando queste istruzioni: [Disattivare/attivare Messaggi secondari in Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="b86e9-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="b86e9-109">Per informazioni sull'uso di Exchange PowerShell, vedere [Uso di PowerShell con Exchange Online](/powershell/exchange/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b86e9-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="b86e9-110">È necessario disporre di un account con almeno il ruolo di amministratore del servizio Exchange e la possibilità di connettersi a Exchange Online con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b86e9-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="b86e9-111">Attivare Messaggi secondari mediante Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b86e9-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="b86e9-p104">È possibile abilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter). Si possono anche visualizzare le impostazioni di Messaggi secondari per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="b86e9-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="b86e9-114">Attivare Messaggi secondari per un singolo utente di nome Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="b86e9-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="b86e9-115">Disattivare Messaggi secondari mediante Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b86e9-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="b86e9-p105">È possibile disabilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter). Si possono anche visualizzare le impostazioni di **Messaggi secondari** per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="b86e9-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="b86e9-118">Disattivare Messaggi secondari per un singolo utente di nome Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="b86e9-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="b86e9-119">Se si usa PowerShell per creare gli utenti in blocco, occorre eseguire [Set-Clutter](/powershell/module/exchange/set-clutter) su ogni cassetta postale degli utenti per gestire Messaggi secondari.</span><span class="sxs-lookup"><span data-stu-id="b86e9-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="b86e9-120">Quando viene visualizzato l'interruttore di attivazione/disattivazione di Messaggi secondari per gli utenti di Outlook sul Web?</span><span class="sxs-lookup"><span data-stu-id="b86e9-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="b86e9-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="b86e9-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="b86e9-122">In quanto amministratore, è possibile ri abilitare Messaggi secondari tramite PowerShell di Exchange.</span><span class="sxs-lookup"><span data-stu-id="b86e9-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="b86e9-123">Dopo averlo fatto, la funzionalità Posta in arrivo evidenziata verrà disattivata e verrà riattivato Messaggi secondari.</span><span class="sxs-lookup"><span data-stu-id="b86e9-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="b86e9-124">**Se si utilizza Outlook sul Web con un abbonamento a Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="b86e9-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="b86e9-125">Se l'utente ha abilitato Messaggi secondari:</span><span class="sxs-lookup"><span data-stu-id="b86e9-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-126">Vengono visualizzate le impostazioni di Messaggi secondari</span><span class="sxs-lookup"><span data-stu-id="b86e9-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="b86e9-127">Se l'utente ha abilitato Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="b86e9-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-128">Le impostazioni di Messaggi secondari non vengono visualizzate</span><span class="sxs-lookup"><span data-stu-id="b86e9-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="b86e9-129">Se non è abilitato né Messaggi secondari né Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="b86e9-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-130">Sia Messaggi secondari che Posta in arrivo evidenziata vengono visualizzati come opzioni nelle impostazioni di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="b86e9-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="b86e9-131">**Se si usa Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="b86e9-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="b86e9-132">Se l'utente ha abilitato Messaggi secondari:</span><span class="sxs-lookup"><span data-stu-id="b86e9-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-133">Vengono visualizzate le impostazioni di Messaggi secondari</span><span class="sxs-lookup"><span data-stu-id="b86e9-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="b86e9-134">Se l'utente ha abilitato Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="b86e9-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-135">Le impostazioni di Messaggi secondari non vengono visualizzate</span><span class="sxs-lookup"><span data-stu-id="b86e9-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="b86e9-136">Se non è abilitato né Messaggi secondari né Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="b86e9-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="b86e9-137">Sia Messaggi secondari che Posta in arrivo evidenziata vengono visualizzati come opzioni nelle impostazioni di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="b86e9-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="b86e9-138">Se in passato l'utente ha abilitato la Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="b86e9-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="b86e9-139">Le impostazioni di Messaggi secondari non verranno mai visualizzate</span><span class="sxs-lookup"><span data-stu-id="b86e9-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="b86e9-140">Altrimenti:</span><span class="sxs-lookup"><span data-stu-id="b86e9-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="b86e9-141">Vengono visualizzate le impostazioni di Messaggi secondari</span><span class="sxs-lookup"><span data-stu-id="b86e9-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="b86e9-142">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b86e9-142">Related articles</span></span>
<span data-ttu-id="b86e9-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="b86e9-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="b86e9-144">Usare la caratteristica Messaggi secondari per ordinare i messaggi con priorità bassa in Outlook</span><span class="sxs-lookup"><span data-stu-id="b86e9-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="b86e9-145">Utilizzare Messaggi secondari per ordinare i messaggi con priorità bassa OWA</span><span class="sxs-lookup"><span data-stu-id="b86e9-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="b86e9-146">Disattivare la caratteristica Messaggi secondari in Outlook</span><span class="sxs-lookup"><span data-stu-id="b86e9-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
