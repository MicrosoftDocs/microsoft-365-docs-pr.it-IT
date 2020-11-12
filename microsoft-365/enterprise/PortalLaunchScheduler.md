---
title: Avviare il portale utilizzando l'utilità di pianificazione del lancio del portale
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In questo articolo viene descritto come avviare il portale utilizzando l'utilità di pianificazione di avvio del portale
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999580"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="88d03-103">Avviare il portale utilizzando l'utilità di pianificazione del lancio del portale</span><span class="sxs-lookup"><span data-stu-id="88d03-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="88d03-104">È possibile avviare il portale utilizzando l'utilità di avvio del portale, convalidando la capacità dell'amministratore del tenant di impostare un'ondata per un nuovo portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="88d03-105">L'amministratore può quindi convalidare il reindirizzamento delle richieste, in base all'esistenza di un utente nelle onde attive.</span><span class="sxs-lookup"><span data-stu-id="88d03-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="88d03-106">Per ulteriori informazioni sull'avvio di un portale con esito positivo, seguire i principi di base, le procedure e i suggerimenti illustrati nell'ambiente di [creazione, avvio e gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="88d03-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="88d03-107">Configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="88d03-107">App setup</span></span>
1. <span data-ttu-id="88d03-108">Disinstalla se esiste una esistente `Microsoft.Online.SharePoint.PowerShell` dal computer tramite il pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="88d03-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="88d03-109">Sul passaggio di PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="88d03-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="88d03-110">Connessione a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="88d03-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="88d03-111">Aprire [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span><span class="sxs-lookup"><span data-stu-id="88d03-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="88d03-112">Connettersi al tenant come amministratore.</span><span class="sxs-lookup"><span data-stu-id="88d03-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="88d03-113">Fornire la password quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="88d03-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="88d03-114">Comando per ottenere un'installazione esistente</span><span class="sxs-lookup"><span data-stu-id="88d03-114">Command to get an existing setup</span></span>

<span data-ttu-id="88d03-115">Per visualizzare le configurazioni di avvio dei portale esistenti:</span><span class="sxs-lookup"><span data-stu-id="88d03-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="88d03-116">Passare `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="88d03-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="88d03-117">Passare il parametro addition `-DisplayFormat Raw` se si desidera visualizzare l'insieme Wave formattato come formato di input non elaborato.</span><span class="sxs-lookup"><span data-stu-id="88d03-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="88d03-118">Comandi per il reindirizzamento bi-direzionale</span><span class="sxs-lookup"><span data-stu-id="88d03-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="88d03-119">Per migrare gli utenti di siti precedenti al nuovo sito in modo a fasi:</span><span class="sxs-lookup"><span data-stu-id="88d03-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="88d03-120">Creare onde di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="88d03-121">Questa operazione è applicabile solo nella fase di test delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="88d03-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="88d03-122">Per testare immediatamente l'impatto della modifica, verificare che la prima ondata `LaunchDateUtc` sia impostata sulla data corrente.</span><span class="sxs-lookup"><span data-stu-id="88d03-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="88d03-123">Se non si specifica questo flag, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="88d03-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="88d03-124">Questo errore si verifica perché i lanci in produzione devono essere pianificati con almeno 7 giorni di anticipo.</span><span class="sxs-lookup"><span data-stu-id="88d03-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="88d03-125">Completamento della convalida.</span><span class="sxs-lookup"><span data-stu-id="88d03-125">Complete validation.</span></span>
  - <span data-ttu-id="88d03-126">Il reindirizzamento può richiedere fino a 5 minuti per completare la configurazione del servizio, quindi attendere prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="88d03-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="88d03-127">Se si effettua l'accesso con l'utente specificato come `WaveOverrideUsers` , quindi nulla cambia.</span><span class="sxs-lookup"><span data-stu-id="88d03-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="88d03-128">Si consiglia di soggiornare nel sito a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="88d03-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="88d03-129">Accedere con un utente che fa parte dei *visualizzatori SG1*.</span><span class="sxs-lookup"><span data-stu-id="88d03-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="88d03-130">Passare al sito precedente ed essere reindirizzato al nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="88d03-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="88d03-131">Passare al nuovo sito ed è necessario rimanere nel nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="88d03-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="88d03-132">Accedere con l'utente in *visualizzatori SG2* e passare al vecchio sito e rimanere nel sito precedente.</span><span class="sxs-lookup"><span data-stu-id="88d03-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="88d03-133">Passare al nuovo sito e procedere con il reindirizzamento al sito precedente.</span><span class="sxs-lookup"><span data-stu-id="88d03-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="88d03-134">Sospendere il lancio del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="88d03-135">Se è necessario sospendere le onde di lancio, è possibile sospenderle per il numero di giorni "x".</span><span class="sxs-lookup"><span data-stu-id="88d03-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="88d03-136">L'impostazione del `Status` flag su pause impedisce tutte le progressioni dell'onda imminenti.</span><span class="sxs-lookup"><span data-stu-id="88d03-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="88d03-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88d03-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88d03-138">Ciò consente di verificare che tutti gli utenti vengano reindirizzati al sito precedente.</span><span class="sxs-lookup"><span data-stu-id="88d03-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="88d03-139">Riavviare la progressione del lancio del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="88d03-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88d03-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88d03-141">Verificare che il reindirizzamento venga ripristinato.</span><span class="sxs-lookup"><span data-stu-id="88d03-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="88d03-142">Eliminare una configurazione di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="88d03-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88d03-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88d03-144">Verificare che non venga eseguito alcun reindirizzamento per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="88d03-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="88d03-145">Comandi per il reindirizzamento alla pagina temporanea</span><span class="sxs-lookup"><span data-stu-id="88d03-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="88d03-146">Seguire questa procedura se non si dispone di un sito precedente e si desidera omettere gli utenti non presenti nell'ondata dall'atterraggio nella nuova pagina del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="88d03-147">Per creare una pagina temporanea in uno dei siti seguenti:</span><span class="sxs-lookup"><span data-stu-id="88d03-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="88d03-148">Creare un'onda di avvio portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="88d03-149">Completamento della convalida.</span><span class="sxs-lookup"><span data-stu-id="88d03-149">Complete validation.</span></span>

  - <span data-ttu-id="88d03-150">Attendere cinque minuti prima di continuare, in quanto l'azione può richiedere fino a cinque minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="88d03-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="88d03-151">Accedere con l'utente che fa parte dei *visualizzatori SG1* e:</span><span class="sxs-lookup"><span data-stu-id="88d03-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="88d03-152">Passare al nuovo sito ed è necessario rimanere nel nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="88d03-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="88d03-153">Passare alla pagina Temp ed è necessario rimanere nella pagina Temp.</span><span class="sxs-lookup"><span data-stu-id="88d03-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="88d03-154">Accedere con l'utente che fa parte di *visualizzatori SG2* e:</span><span class="sxs-lookup"><span data-stu-id="88d03-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="88d03-155">Passare al nuovo sito ed essere reindirizzato alla pagina Temp.</span><span class="sxs-lookup"><span data-stu-id="88d03-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="88d03-156">Passare alla pagina Temp e mantenere la pagina temporanea.</span><span class="sxs-lookup"><span data-stu-id="88d03-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="88d03-157">Eliminare una configurazione di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="88d03-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="88d03-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88d03-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88d03-159">Verificare che non venga eseguito alcun reindirizzamento per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="88d03-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="88d03-160">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="88d03-160">Learn more</span></span>
[<span data-ttu-id="88d03-161">Pianificazione del piano di avvio del portale per il lancio in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="88d03-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)