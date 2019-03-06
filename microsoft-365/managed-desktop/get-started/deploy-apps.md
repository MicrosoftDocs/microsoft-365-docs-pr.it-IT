---
title: Distribuire le app per i dispositivi Microsoft Managed Desktop
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, app, app line-of-business, app LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: febb3198c434e638f83c412a3f8a3b688d9f5bd1
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414169"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="1d813-104">Distribuire le app ai dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1d813-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="1d813-105">Parte dell'onboarding di Microsoft Managed Desktop include l'aggiunta e la distribuzione di app ai dispositivi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1d813-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="1d813-106">Dopo aver utilizzato il portale Microsoft Managed Desktop, è possibile aggiungere e distribuire le app.</span><span class="sxs-lookup"><span data-stu-id="1d813-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="1d813-107">Il processo globale è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1d813-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="1d813-108">[Aggiungere app a Microsoft managEd desktop Portal](#1) -può essere costituita da app line-of-business (LOB) esistenti o app da Microsoft Store for business sincronizzate con Intune.</span><span class="sxs-lookup"><span data-stu-id="1d813-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="1d813-109">[Creare gruppi di Azure Active Directory (ad) per l'assegnazione delle app](#2) -si utilizzeranno questi gruppi per gestire l'assegnazione delle app.</span><span class="sxs-lookup"><span data-stu-id="1d813-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="1d813-110">Assegnare le app agli utenti</span><span class="sxs-lookup"><span data-stu-id="1d813-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="1d813-111">Passaggio 1: aggiungere app al portale Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1d813-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="1d813-112">È possibile aggiungere le [app basate su Windows MSI o Win32](#lob-apps)o le [app Microsoft Store for business](#msfb-apps) a Microsoft Managed Desktop e quindi distribuirle in dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d813-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="1d813-113">Applicazioni basate su Windows MSI o Win32 per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1d813-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="1d813-114">È possibile aggiungere le app line-of-business (LOB) al portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d813-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1d813-115">Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedere [Microsoft managEd desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="1d813-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="1d813-116">In questa procedura, è possibile selezionare il tipo di app che si desidera aggiungere e quindi configurare e caricare l'origine dell'app.</span><span class="sxs-lookup"><span data-stu-id="1d813-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="1d813-117">**Per aggiungere l'app LOB o l'app Windows al portale Microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="1d813-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="1d813-118">È possibile accedere a Microsoft Managed Desktop Portal oppure accedere a Intune e quindi cercare Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d813-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="1d813-119">Verrà visualizzato l'accesso a Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="1d813-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="1d813-120">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="1d813-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="1d813-121">In **inventario**, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="1d813-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="1d813-122">Nel carico di lavoro delle app, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1d813-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="1d813-123">In **Aggiungi app**selezionare app **line-of-business** o **Windows app (Win32)-Preview**.</span><span class="sxs-lookup"><span data-stu-id="1d813-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="1d813-124">Se è stata selezionata l' **applicazione line-of-business**, vedere [aggiungere un'app line-of-business di Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e sulla configurazione delle app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="1d813-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="1d813-125">Se è stata selezionata l'opzione **Windows app (Win32)-Preview**, vedere [gestione delle app Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni su come aggiungere e configurare le app di Windows.</span><span class="sxs-lookup"><span data-stu-id="1d813-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="1d813-126">App di Microsoft Store for business</span><span class="sxs-lookup"><span data-stu-id="1d813-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="1d813-127">Se non si è iscritti a Microsoft Store for business, è possibile iscriversi quando si effettua la ricerca per le app.</span><span class="sxs-lookup"><span data-stu-id="1d813-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="1d813-128">Dopo aver eseguito le app, è possibile sincronizzarle con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d813-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="1d813-129">**Per acquistare app da Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="1d813-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="1d813-130">Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="1d813-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="1d813-131">Selezionare **Shop per il gruppo personale**.</span><span class="sxs-lookup"><span data-stu-id="1d813-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="1d813-132">Utilizza la ricerca per trovare l'app desiderata e seleziona l'app.</span><span class="sxs-lookup"><span data-stu-id="1d813-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="1d813-133">Nei dettagli del prodotto, selezionare **Ottieni l'app**.</span><span class="sxs-lookup"><span data-stu-id="1d813-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="1d813-134">Microsoft Store aggiunge l'app ai **prodotti & Services** per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d813-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="1d813-135">**Per forzare una sincronizzazione tra Intune e Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="1d813-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="1d813-136">Accedere al [portale di Azure](https://portal.azure.com/) come amministratore di Intune o amministratore globale per il tenant</span><span class="sxs-lookup"><span data-stu-id="1d813-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="1d813-137">Selezionare **tutti i servizi _GT_ Intune**.</span><span class="sxs-lookup"><span data-stu-id="1d813-137">Select **All services > Intune**.</span></span> <span data-ttu-id="1d813-138">Intune si trova nella sezione Monitoring + Management.</span><span class="sxs-lookup"><span data-stu-id="1d813-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="1d813-139">Nel riquadro di Intune, selezionare **app client**, quindi selezionare **Microsoft Store for business**.</span><span class="sxs-lookup"><span data-stu-id="1d813-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="1d813-140">Selezionare **Abilita** per sincronizzare le app di Microsoft Store for business con Intune.</span><span class="sxs-lookup"><span data-stu-id="1d813-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="1d813-141">Se non è già stato, iscriversi e associare l'account Microsoft Store for business a Intune</span><span class="sxs-lookup"><span data-stu-id="1d813-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="1d813-142">Selezionare la lingua in cui verranno visualizzate le app da Microsoft Store for business nella console di Intune</span><span class="sxs-lookup"><span data-stu-id="1d813-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="1d813-143">Selezionare **Sincronizza** per sincronizzare le app di Microsoft Store for business con Intune.</span><span class="sxs-lookup"><span data-stu-id="1d813-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="1d813-144">Verificare che la sincronizzazione tra Microsoft Store for business e Intune sia attiva (passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="1d813-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="1d813-145">**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for business**</span><span class="sxs-lookup"><span data-stu-id="1d813-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="1d813-146">Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="1d813-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="1d813-147">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="1d813-147">Select **Manage**.</span></span>
3. <span data-ttu-id="1d813-148">Selezionare **Impostazioni** e quindi **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="1d813-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="1d813-149">In **strumenti di gestione**verificare che Intune sia elencato e che lo stato sia **attivo**.</span><span class="sxs-lookup"><span data-stu-id="1d813-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="1d813-150">Passaggio 2: creare gruppi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="1d813-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="1d813-151">Creare tre gruppi di Azure AD per ogni app.</span><span class="sxs-lookup"><span data-stu-id="1d813-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="1d813-152">In questa tabella vengono illustrati i gruppi necessari (disponibili, necessari e disInstallati).</span><span class="sxs-lookup"><span data-stu-id="1d813-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="1d813-153">Tipo di assegnazione delle app</span><span class="sxs-lookup"><span data-stu-id="1d813-153">App assignment type</span></span> |   <span data-ttu-id="1d813-154">Utilizzo di gruppo</span><span class="sxs-lookup"><span data-stu-id="1d813-154">Group use</span></span>   | <span data-ttu-id="1d813-155">Nome di Azure AD di esempio</span><span class="sxs-lookup"><span data-stu-id="1d813-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="1d813-156">Disponibili</span><span class="sxs-lookup"><span data-stu-id="1d813-156">Available</span></span> |  <span data-ttu-id="1d813-157">L'app sarà disponibile nell'app o nel sito Web del portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="1d813-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="1d813-158">MMD – *nome applicazione* – disponibile</span><span class="sxs-lookup"><span data-stu-id="1d813-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="1d813-159">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1d813-159">Required</span></span> |  <span data-ttu-id="1d813-160">L'app è installata nei dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="1d813-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="1d813-161">MMD – *nome dell'app* – obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1d813-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="1d813-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="1d813-162">Uninstall</span></span> |  <span data-ttu-id="1d813-163">L'app TThe viene disinstallata dai dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="1d813-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="1d813-164">MMD – *nome applicazione* – disinstallazione</span><span class="sxs-lookup"><span data-stu-id="1d813-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="1d813-165">Aggiungere gli utenti a questi gruppi per rendere l'app disponibili, installare l'app o rimuovere l'app dal proprio dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d813-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="1d813-166">Passaggio 3: assegnare le app agli utenti</span><span class="sxs-lookup"><span data-stu-id="1d813-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="1d813-167">**Per assegnare l'app agli utenti**</span><span class="sxs-lookup"><span data-stu-id="1d813-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="1d813-168">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="1d813-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="1d813-169">Nel riquadro desktop gestito, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="1d813-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="1d813-170">Nel carico di lavoro Apps selezionare l'app che si desidera assegnare agli utenti e selezionare **assegna gruppi di utenti**.</span><span class="sxs-lookup"><span data-stu-id="1d813-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="1d813-171">Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Disinstalla) e assegnare il gruppo appropriato.</span><span class="sxs-lookup"><span data-stu-id="1d813-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="1d813-172">Nel riquadro assegna App, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d813-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->