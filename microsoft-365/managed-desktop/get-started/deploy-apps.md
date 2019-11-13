---
title: Distribuire le app ai dispositivi
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, app, app line-of-business, app LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a064a41fc7ab69e31d49553f600dfd6bb91ef7b0
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302913"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="5f16d-104">Distribuire le app ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="5f16d-104">Deploy apps to devices</span></span>
<span data-ttu-id="5f16d-105">Parte dell'onboarding di Microsoft Managed Desktop include l'aggiunta e la distribuzione di app ai dispositivi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5f16d-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="5f16d-106">Dopo aver utilizzato il portale Microsoft Managed Desktop, è possibile aggiungere e distribuire le app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="5f16d-107">Il processo globale è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5f16d-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="5f16d-108">[Aggiungere app a Microsoft Managed Desktop Portal](#1) -può essere costituita da app line-of-business (LOB) esistenti o app da Microsoft Store for business sincronizzate con Intune.</span><span class="sxs-lookup"><span data-stu-id="5f16d-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="5f16d-109">[Creare gruppi di Azure Active Directory (ad) per l'assegnazione delle app](#2) -si utilizzeranno questi gruppi per gestire l'assegnazione delle app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="5f16d-110">Assegnare le app agli utenti</span><span class="sxs-lookup"><span data-stu-id="5f16d-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="5f16d-111">Passaggio 1: aggiungere app al portale Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5f16d-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="5f16d-112">È possibile aggiungere le [app basate su Windows MSI o Win32](#lob-apps)o le [app Microsoft Store for business](#msfb-apps) a Microsoft Managed Desktop e quindi distribuirle in dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5f16d-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="5f16d-113">Applicazioni basate su Windows MSI o Win32 per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5f16d-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="5f16d-114">È possibile aggiungere le app line-of-business (LOB) al portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5f16d-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5f16d-115">Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedere [Microsoft Managed Desktop App requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="5f16d-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="5f16d-116">In questa procedura, è possibile selezionare il tipo di app che si desidera aggiungere e quindi configurare e caricare l'origine dell'app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="5f16d-117">**Per aggiungere l'app LOB o l'app Windows al portale Microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="5f16d-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="5f16d-118">È possibile accedere a Microsoft Managed Desktop Portal oppure accedere a Intune e quindi cercare Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5f16d-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="5f16d-119">Verrà visualizzato l'accesso a Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="5f16d-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="5f16d-120">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="5f16d-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="5f16d-121">In **inventario**, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="5f16d-122">Nel carico di lavoro delle app, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="5f16d-123">In **Aggiungi app**selezionare app **line-of-business** o **Windows app (Win32)**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="5f16d-124">Se è stata selezionata l' **applicazione line-of-business**, vedere [aggiungere un'app line-of-business di Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e sulla configurazione delle app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="5f16d-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="5f16d-125">Se è stata selezionata l'opzione **Windows app (Win32)**, vedere [gestione delle app Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni su come aggiungere e configurare le app di Windows.</span><span class="sxs-lookup"><span data-stu-id="5f16d-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="5f16d-126">App di Microsoft Store for business</span><span class="sxs-lookup"><span data-stu-id="5f16d-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="5f16d-127">Se non si è iscritti a Microsoft Store for business, è possibile iscriversi quando si effettua la ricerca per le app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="5f16d-128">Dopo aver eseguito le app, è possibile sincronizzarle con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5f16d-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="5f16d-129">**Per acquistare app da Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="5f16d-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="5f16d-130">Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="5f16d-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="5f16d-131">Selezionare **Shop per il gruppo personale**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="5f16d-132">Utilizza la ricerca per trovare l'app desiderata e seleziona l'app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="5f16d-133">Nei dettagli del prodotto, selezionare **Ottieni l'app**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="5f16d-134">Microsoft Store aggiunge l'app ai **prodotti & Services** per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f16d-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="5f16d-135">**Per forzare una sincronizzazione tra Intune e Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="5f16d-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="5f16d-136">Accedere al [portale di Azure](https://portal.azure.com/) come amministratore di Intune o amministratore globale per il tenant</span><span class="sxs-lookup"><span data-stu-id="5f16d-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="5f16d-137">Selezionare **tutti i servizi > Intune**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-137">Select **All services > Intune**.</span></span> <span data-ttu-id="5f16d-138">Intune si trova nella sezione Monitoring + Management.</span><span class="sxs-lookup"><span data-stu-id="5f16d-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="5f16d-139">Nel riquadro di Intune, selezionare **app client**, quindi selezionare **Microsoft Store for business**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="5f16d-140">Selezionare **Abilita** per sincronizzare le app di Microsoft Store for business con Intune.</span><span class="sxs-lookup"><span data-stu-id="5f16d-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="5f16d-141">Se non è già stato, iscriversi e associare l'account Microsoft Store for business a Intune</span><span class="sxs-lookup"><span data-stu-id="5f16d-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="5f16d-142">Selezionare la lingua in cui verranno visualizzate le app da Microsoft Store for business nella console di Intune</span><span class="sxs-lookup"><span data-stu-id="5f16d-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="5f16d-143">Selezionare **Sincronizza** per sincronizzare le app di Microsoft Store for business con Intune.</span><span class="sxs-lookup"><span data-stu-id="5f16d-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="5f16d-144">Verificare che la sincronizzazione tra Microsoft Store for business e Intune sia attiva (passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="5f16d-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="5f16d-145">**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="5f16d-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="5f16d-146">Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="5f16d-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="5f16d-147">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-147">Select **Manage**.</span></span>
3. <span data-ttu-id="5f16d-148">Selezionare **Impostazioni** e quindi **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="5f16d-149">In **strumenti di gestione**verificare che Intune sia elencato e che lo stato sia **attivo**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="5f16d-150">Passaggio 2: creare gruppi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="5f16d-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="5f16d-151">Creare tre gruppi di Azure AD per ogni app.</span><span class="sxs-lookup"><span data-stu-id="5f16d-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="5f16d-152">In questa tabella vengono illustrati i gruppi necessari (disponibili, necessari e disinstallati).</span><span class="sxs-lookup"><span data-stu-id="5f16d-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="5f16d-153">Tipo di assegnazione delle app</span><span class="sxs-lookup"><span data-stu-id="5f16d-153">App assignment type</span></span> |   <span data-ttu-id="5f16d-154">Utilizzo di gruppo</span><span class="sxs-lookup"><span data-stu-id="5f16d-154">Group use</span></span>   | <span data-ttu-id="5f16d-155">Nome di Azure AD di esempio</span><span class="sxs-lookup"><span data-stu-id="5f16d-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="5f16d-156">Disponibili</span><span class="sxs-lookup"><span data-stu-id="5f16d-156">Available</span></span> |  <span data-ttu-id="5f16d-157">L'app sarà disponibile nell'app o nel sito Web del portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="5f16d-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="5f16d-158">MMD – *nome applicazione* – disponibile</span><span class="sxs-lookup"><span data-stu-id="5f16d-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="5f16d-159">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="5f16d-159">Required</span></span> |  <span data-ttu-id="5f16d-160">L'app è installata nei dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="5f16d-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="5f16d-161">MMD – *nome dell'app* – obbligatorio</span><span class="sxs-lookup"><span data-stu-id="5f16d-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="5f16d-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="5f16d-162">Uninstall</span></span> |  <span data-ttu-id="5f16d-163">L'app viene disinstallata dai dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="5f16d-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="5f16d-164">MMD – *nome applicazione* – disinstallazione</span><span class="sxs-lookup"><span data-stu-id="5f16d-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="5f16d-165">Aggiungere gli utenti a questi gruppi per rendere l'app disponibili, installare l'app o rimuovere l'app dal proprio dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5f16d-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="5f16d-166">Passaggio 3: assegnare le app agli utenti</span><span class="sxs-lookup"><span data-stu-id="5f16d-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="5f16d-167">**Per assegnare l'app agli utenti**</span><span class="sxs-lookup"><span data-stu-id="5f16d-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="5f16d-168">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="5f16d-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="5f16d-169">Nel riquadro desktop gestito, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="5f16d-170">Nel carico di lavoro Apps selezionare l'app che si desidera assegnare agli utenti e selezionare **assegna gruppi di utenti**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="5f16d-171">Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Disinstalla) e assegnare il gruppo appropriato.</span><span class="sxs-lookup"><span data-stu-id="5f16d-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="5f16d-172">Nel riquadro assegna App, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f16d-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="5f16d-173">Passaggi per iniziare a utilizzare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5f16d-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="5f16d-174">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5f16d-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="5f16d-175">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="5f16d-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="5f16d-176">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="5f16d-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="5f16d-177">Distribuire il Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="5f16d-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="5f16d-178">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="5f16d-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="5f16d-179">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5f16d-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="5f16d-180">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5f16d-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="5f16d-181">Distribuire le app (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="5f16d-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
