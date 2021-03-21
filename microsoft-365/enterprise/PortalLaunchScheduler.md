---
title: Avviare il portale usando l'Utilità di pianificazione di avvio portale
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
description: In questo articolo viene descritto come avviare il portale tramite l'Utilità di pianificazione di avvio portale
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926143"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="28872-103">Avviare il portale usando l'Utilità di pianificazione di avvio portale</span><span class="sxs-lookup"><span data-stu-id="28872-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="28872-104">Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto.</span><span class="sxs-lookup"><span data-stu-id="28872-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="28872-105">L'avvio del portale in modalità ondata è una parte importante per garantire agli utenti un'esperienza fluida ed performante per l'accesso a un nuovo portale di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="28872-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="28872-106">L'avvio in modalità ondata è un modo chiave per implementare il portale, come descritto in Pianificazione del piano di implementazione dell'avvio del portale [in SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="28872-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="28872-107">L'Utilità di pianificazione di avvio portale è progettata per consentire di seguire un approccio di implementazione graduale/ondata gestendo i reindirizzamenti per il nuovo portale.</span><span class="sxs-lookup"><span data-stu-id="28872-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="28872-108">Durante ognuna delle ondate, è possibile raccogliere il feedback degli utenti e monitorare le prestazioni durante ogni ondata di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="28872-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="28872-109">Questo ha il vantaggio di introdurre lentamente il portale, offrendoti la possibilità di sospendere e risolvere i problemi prima di procedere con l'onda successiva e di garantire un'esperienza positiva per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="28872-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="28872-110">Esistono due tipi di reindirizzamento:</span><span class="sxs-lookup"><span data-stu-id="28872-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="28872-111">bidirezionale: avviare un nuovo portale moderno di SharePoint Online per sostituire un portale classico o moderno di SharePoint esistente</span><span class="sxs-lookup"><span data-stu-id="28872-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="28872-112">reindirizzamento temporaneo delle pagine: avviare un nuovo portale di SharePoint Online moderno senza portale di SharePoint esistente</span><span class="sxs-lookup"><span data-stu-id="28872-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="28872-113">L'utilità di pianificazione di avvio del portale è disponibile solo per avviare portali di SharePoint Online moderni (ad esempio, siti di comunicazione).</span><span class="sxs-lookup"><span data-stu-id="28872-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="28872-114">Gli avvii devono essere pianificati con almeno 7 giorni di anticipo.</span><span class="sxs-lookup"><span data-stu-id="28872-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="28872-115">Il numero di onde richieste è determinato dal numero previsto di utenti.</span><span class="sxs-lookup"><span data-stu-id="28872-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="28872-116">Prima di pianificare l'avvio di un portale, è necessario eseguire lo strumento Diagnostica pagine per [SharePoint](./page-diagnostics-for-spo.md) per verificare che la home page del portale sia integra.</span><span class="sxs-lookup"><span data-stu-id="28872-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="28872-117">Al termine dell'avvio del portale, tutti gli utenti con autorizzazioni per il sito potranno accedere al nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="28872-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="28872-118">Per ulteriori informazioni sull'avvio di un portale corretto, seguire i principi di base, le procedure e i suggerimenti dettagliati in Creazione, avvio e [manutenzione di un portale integro.](/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="28872-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="28872-119">Questa funzionalità non è disponibile per i piani di Office 365 Germany, Office 365 gestito da 21Vianet (Cina) o Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="28872-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="28872-120">Configurazione dell'app e connessione a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="28872-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="28872-121">[Scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="28872-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="28872-p104">Se hai installato una versione precedente di SharePoint Online Management Shell, vai su Installazione applicazioni e disinstallare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28872-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="28872-123">Nella pagina Download Center selezionare la lingua e fare clic sul pulsante Scarica.</span><span class="sxs-lookup"><span data-stu-id="28872-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="28872-124">Ti verrà chiesto di scegliere tra il download di un file x64 e x86 con estensione msi.</span><span class="sxs-lookup"><span data-stu-id="28872-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="28872-125">Scaricare il file x64 se stai eseguendo la versione a 64 bit di Windows e il file x86 se stai eseguendo quella a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="28872-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="28872-126">Se non conosci quale versione stai eseguendo, vedere[Quale versione del sistema operativo Windows sto eseguendo?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="28872-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="28872-127">Dopo aver scaricato il file, eseguirlo e seguire i passaggi della configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="28872-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="28872-128">Connettiti a SharePoint come [amministratore globale o amministratore di SharePoint](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28872-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="28872-129">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="28872-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="28872-130">Visualizzare eventuali configurazioni di avvio del portale esistenti</span><span class="sxs-lookup"><span data-stu-id="28872-130">View any existing portal launch setups</span></span>

<span data-ttu-id="28872-131">Per verificare se sono presenti configurazioni di avvio del portale esistenti:</span><span class="sxs-lookup"><span data-stu-id="28872-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="28872-132">Pianificare un avvio del portale nel sito</span><span class="sxs-lookup"><span data-stu-id="28872-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="28872-133">Il numero di onde necessarie dipende dalle dimensioni di avvio previste.</span><span class="sxs-lookup"><span data-stu-id="28872-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="28872-134">Meno di 10.000 utenti: 1 onda</span><span class="sxs-lookup"><span data-stu-id="28872-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="28872-135">Da 10.000 a 30.000 utenti: 3 onde</span><span class="sxs-lookup"><span data-stu-id="28872-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="28872-136">Da 30.000 a 100.000 utenti: 5 onde</span><span class="sxs-lookup"><span data-stu-id="28872-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="28872-137">Più di 100.000 utenti: 5 onde e contattare il team dell'account Microsoft</span><span class="sxs-lookup"><span data-stu-id="28872-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="28872-138">Passaggi per il reindirizzamento bidirezionale</span><span class="sxs-lookup"><span data-stu-id="28872-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="28872-139">Il reindirizzamento bidirezionale prevede l'avvio di un nuovo portale di SharePoint Online moderno per sostituire un portale classico o moderno di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="28872-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="28872-140">Gli utenti in ondate attive verranno reindirizzati al nuovo sito indipendentemente dal fatto che si snavigare verso il sito vecchio o nuovo.</span><span class="sxs-lookup"><span data-stu-id="28872-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="28872-141">Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al sito precedente fino all'avvio dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="28872-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="28872-142">Supportiamo solo il reindirizzamento tra la home page predefinita nel vecchio sito e la home page predefinita nel nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="28872-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="28872-143">Se si dispone di amministratori o proprietari che devono accedere ai siti vecchi e nuovi senza essere reindirizzati, assicurarsi che siano elencati utilizzando il `WaveOverrideUsers` parametro .</span><span class="sxs-lookup"><span data-stu-id="28872-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="28872-144">Per eseguire la migrazione a fasi degli utenti da un sito di SharePoint esistente a un nuovo sito di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="28872-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="28872-145">Eseguire il comando seguente per designare le ondate di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="28872-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="28872-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="28872-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="28872-147">Completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="28872-147">Complete validation.</span></span> <span data-ttu-id="28872-148">Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="28872-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="28872-149">Passaggi per il reindirizzamento alla pagina temporanea</span><span class="sxs-lookup"><span data-stu-id="28872-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="28872-150">Il reindirizzamento temporaneo delle pagine deve essere utilizzato quando non esiste un portale di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="28872-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="28872-151">Gli utenti vengono indirizzati a un nuovo portale di SharePoint Online moderno in modo a fasi.</span><span class="sxs-lookup"><span data-stu-id="28872-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="28872-152">Se un utente è in un'ondata che non è stata avviata, verrà reindirizzato a una pagina temporanea (qualsiasi URL).</span><span class="sxs-lookup"><span data-stu-id="28872-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="28872-153">Eseguire il comando seguente per designare le ondate di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="28872-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="28872-154">Esempio:</span><span class="sxs-lookup"><span data-stu-id="28872-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="28872-155">Completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="28872-155">Complete validation.</span></span> <span data-ttu-id="28872-156">Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="28872-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="28872-157">Sospendere o riavviare l'avvio di un portale nel sito</span><span class="sxs-lookup"><span data-stu-id="28872-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="28872-158">Per sospendere l'avvio di un portale in corso e impedire temporaneamente che si verifichino imminenti progressioni delle onde, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="28872-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="28872-159">Verificare che tutti gli utenti siano reindirizzati al sito precedente.</span><span class="sxs-lookup"><span data-stu-id="28872-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="28872-160">Per riavviare un avvio del portale sospeso, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="28872-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="28872-161">Verificare che il reindirizzamento sia stato ripristinato.</span><span class="sxs-lookup"><span data-stu-id="28872-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="28872-162">Eliminare un avvio del portale nel sito</span><span class="sxs-lookup"><span data-stu-id="28872-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="28872-163">Eseguire il comando seguente per eliminare un avvio del portale pianificato o in corso per un sito.</span><span class="sxs-lookup"><span data-stu-id="28872-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="28872-164">Verificare che non si verifica alcun reindirizzamento per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="28872-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="28872-165">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="28872-165">Learn more</span></span>
[<span data-ttu-id="28872-166">Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="28872-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)