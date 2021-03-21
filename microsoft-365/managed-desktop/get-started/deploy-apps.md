---
title: Distribuire le app sui dispositivi
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922027"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="bc0a6-104">Distribuire le app sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="bc0a6-104">Deploy apps to devices</span></span>
<span data-ttu-id="bc0a6-105">Parte dell'onboarding in Microsoft Managed Desktop include l'aggiunta e la distribuzione di app nei dispositivi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="bc0a6-106">Dopo aver utilizzato il portale Microsoft Managed Desktop, puoi aggiungere e distribuire le tue app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="bc0a6-107">Il processo complessivo è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bc0a6-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="bc0a6-108">[Aggiungere app al portale Microsoft Managed Desktop:](#1) possono trattarsi di app line-of-business (LOB) esistenti o app di Microsoft Store per le aziende sincronizzate con Intune.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="bc0a6-109">[Creare gruppi di Azure Active Directory (AD) per l'assegnazione delle app:](#2) questi gruppi verranno utilizzati per gestire l'assegnazione delle app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="bc0a6-110">Assegnare app agli utenti</span><span class="sxs-lookup"><span data-stu-id="bc0a6-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="bc0a6-111">Passaggio 1: Aggiungere app al portale Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="bc0a6-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="bc0a6-112">Puoi aggiungere [app win32 o](#lob-apps)basate su MSI di Windows o app di Microsoft Store per [le](#msfb-apps) aziende a Microsoft Managed Desktop e quindi distribuirle nei dispositivi Desktop gestito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="bc0a6-113">App basate su Win32 o Windows MSI per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="bc0a6-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="bc0a6-114">È possibile aggiungere le app line-of-business (LOB) al portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="bc0a6-115">Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedi [Requisiti per le app desktop](../service-description/mmd-app-requirements.md)gestite Microsoft .</span><span class="sxs-lookup"><span data-stu-id="bc0a6-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="bc0a6-116">In questa procedura selezionerai il tipo di app che vuoi aggiungere e quindi configurerai e carichi l'origine dell'app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="bc0a6-117">**Per aggiungere l'app LOB o l'app Di Windows al portale Microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="bc0a6-118">È possibile accedere al portale Microsoft Managed Desktop oppure accedere a Intune e quindi cercare Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="bc0a6-119">Verrà visualizzato l'accesso al portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="bc0a6-120">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="bc0a6-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="bc0a6-121">In **Inventario** seleziona **App.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="bc0a6-122">Nel carico di lavoro App selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="bc0a6-123">In **Aggiungi app** seleziona App **line-of-business** o **App di Windows (Win32).**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="bc0a6-124">Se è stata selezionata **l'opzione App line-of-business,** vedere Aggiungere un'app [line-of-business di Windows a Microsoft Intune](/intune/lob-apps-windows) per istruzioni sull'aggiunta e la configurazione di app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="bc0a6-125">Se hai selezionato **App di Windows (Win32),** vedi Gestione app [Win32](/intune/apps-win32-app-management) per istruzioni sull'aggiunta e la configurazione delle app di Windows.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="bc0a6-126">App di Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="bc0a6-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="bc0a6-127">Se non hai effettuato l'iscrizione a Microsoft Store per le aziende, puoi iscriverti quando acquisti le app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="bc0a6-128">Dopo aver creato le app, puoi sincronizzarle con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="bc0a6-129">**Per acquistare app da Microsoft Store per le aziende**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="bc0a6-130">Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account amministratore di Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="bc0a6-131">Seleziona **Acquista per il mio gruppo.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="bc0a6-132">Usa Cerca per trovare l'app desiderata e seleziona l'app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="bc0a6-133">Nei dettagli del prodotto seleziona **Scarica l'app.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="bc0a6-134">Microsoft Store aggiunge l'app ai **tuoi prodotti** per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="bc0a6-135">**Per forzare una sincronizzazione tra Intune e Microsoft Store per le aziende**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="bc0a6-136">Accedere [all'interfaccia di amministrazione di Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="bc0a6-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="bc0a6-137">Selezionare **Tenant administration**  >  **Connectors and tokens** Microsoft Store for  >  **Business**.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="bc0a6-138">Seleziona **Sincronizza** per ottenere le app acquistate da Microsoft Store in Intune.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="bc0a6-139">**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store per le aziende**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="bc0a6-140">Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account amministratore di Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="bc0a6-141">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-141">Select **Manage**.</span></span>
3. <span data-ttu-id="bc0a6-142">Selezionare **Impostazioni** e quindi **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="bc0a6-143">In **Strumenti di gestione** verificare che Intune sia elencato e che lo stato sia **Attivo.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="bc0a6-144">Passaggio 2: Creare gruppi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="bc0a6-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="bc0a6-145">Crea tre gruppi di Azure AD per ogni app.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="bc0a6-146">Questa tabella descrive i gruppi necessari (Disponibile, Obbligatorio e Disinstalla).</span><span class="sxs-lookup"><span data-stu-id="bc0a6-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="bc0a6-147">Tipo di assegnazione app</span><span class="sxs-lookup"><span data-stu-id="bc0a6-147">App assignment type</span></span> |    <span data-ttu-id="bc0a6-148">Utilizzo del gruppo</span><span class="sxs-lookup"><span data-stu-id="bc0a6-148">Group use</span></span>    | <span data-ttu-id="bc0a6-149">Esempio di nome Azure AD</span><span class="sxs-lookup"><span data-stu-id="bc0a6-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="bc0a6-150">Disponibile</span><span class="sxs-lookup"><span data-stu-id="bc0a6-150">Available</span></span> |  <span data-ttu-id="bc0a6-151">L'app sarà disponibile dall'app Portale aziendale o dal sito Web.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="bc0a6-152">MMD - *nome dell'app* - Disponibile</span><span class="sxs-lookup"><span data-stu-id="bc0a6-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="bc0a6-153">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="bc0a6-153">Required</span></span> |  <span data-ttu-id="bc0a6-154">L'app viene installata nei dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="bc0a6-155">MMD - *nome dell'app* - Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="bc0a6-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="bc0a6-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="bc0a6-156">Uninstall</span></span> |  <span data-ttu-id="bc0a6-157">L'app viene disinstallata dai dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="bc0a6-158">MMD - *nome dell'app* - Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="bc0a6-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="bc0a6-159">Aggiungi gli utenti a questi gruppi per rendere disponibile l'app, installare l'app o rimuovere l'app dal dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="bc0a6-160">Passaggio 3: Assegnare app agli utenti</span><span class="sxs-lookup"><span data-stu-id="bc0a6-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="bc0a6-161">**Per assegnare l'app agli utenti**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="bc0a6-162">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="bc0a6-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="bc0a6-163">Nel riquadro Desktop gestito seleziona **App.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="bc0a6-164">Nel carico di lavoro App seleziona l'app a cui vuoi assegnare gli utenti e seleziona **Assegna gruppi di utenti.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="bc0a6-165">Per l'app specifica, seleziona un tipo di assegnazione (Disponibile, Obbligatorio, Disinstalla) e assegna il gruppo appropriato.</span><span class="sxs-lookup"><span data-stu-id="bc0a6-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="bc0a6-166">Nel riquadro Assegna app selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="bc0a6-167">Passaggi per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="bc0a6-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="bc0a6-168">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="bc0a6-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="bc0a6-169">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="bc0a6-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="bc0a6-170">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="bc0a6-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="bc0a6-171">Distribuire il Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="bc0a6-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="bc0a6-172">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="bc0a6-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="bc0a6-173">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="bc0a6-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="bc0a6-174">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="bc0a6-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="bc0a6-175">Distribuire app (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="bc0a6-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->