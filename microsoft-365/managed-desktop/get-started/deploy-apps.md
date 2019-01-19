---
title: Distribuzione di applicazioni per dispositivi Desktop gestiti Microsoft
description: Informazioni per l'aggiunta e la distribuzione di applicazioni per i dispositivi Desktop gestiti Microsoft.
keywords: Microsoft Desktop gestiti, Microsoft 365, servizio, la documentazione, App, applicazioni line-of-business, applicazioni LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341609"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="a37b2-104">Distribuire applicazioni per dispositivi Desktop gestiti Microsoft</span><span class="sxs-lookup"><span data-stu-id="a37b2-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="a37b2-p101">Parte di on-boarding desktop gestiti Microsoft include aggiunta e la distribuzione di applicazioni per i dispositivi dell'utente. Una volta che si sta utilizzando il portale Microsoft Desktop gestiti, è possibile aggiungere e distribuire le app.</span><span class="sxs-lookup"><span data-stu-id="a37b2-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="a37b2-107">Processo generale è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a37b2-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="a37b2-108">[Aggiungi App al portale dei Microsoft Desktop gestiti](#1) - questo può essere esistente applicazioni line-of-business (LOB) o App da Microsoft Store for Business che è stato sincronizzati con Intune.</span><span class="sxs-lookup"><span data-stu-id="a37b2-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="a37b2-109">[Gruppi di creazione di Azure Active Directory (AD) per l'assegnazione di app](#2) - si utilizzerà questi gruppi per gestire l'assegnazione di app.</span><span class="sxs-lookup"><span data-stu-id="a37b2-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="a37b2-110">Assegnare agli utenti applicazioni</span><span class="sxs-lookup"><span data-stu-id="a37b2-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="a37b2-111">Passaggio 1: Aggiungere applicazioni al portale dei Microsoft Desktop gestiti</span><span class="sxs-lookup"><span data-stu-id="a37b2-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="a37b2-112">È possibile aggiungere [Win32, applicazioni basate su MSI di Windows](#lob-apps)o [Archiviazione di Microsoft per le applicazioni di Business](#msfb-apps) desktop gestiti Microsoft e distribuirli nei dispositivi Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="a37b2-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="a37b2-113">Win32 o Windows App basato su MSI di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a37b2-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="a37b2-p102">È possibile aggiungere le applicazioni line-of-business (LOB) al portale dei Microsoft Desktop gestiti. Per informazioni sui requisiti per le applicazioni installate su dispositivi Desktop gestiti Microsoft, vedere [requisiti di app Desktop gestiti Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="a37b2-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="a37b2-116">In questa procedura è sarà selezionare il tipo di applicazione che si desidera aggiungere, configurare e caricare l'origine di app.</span><span class="sxs-lookup"><span data-stu-id="a37b2-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="a37b2-117">**Per aggiungere le applicazioni LOB o app di Windows al portale dei Microsoft Desktop gestiti**</span><span class="sxs-lookup"><span data-stu-id="a37b2-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="a37b2-p103">È possibile accedere al portale dei Microsoft Desktop gestiti o accedere a Intune e quindi cercare Microsoft Desktop gestiti. Verrà descritto in accesso al portale dei Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="a37b2-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="a37b2-120">Accedere al [portale di amministrazione di Desktop gestiti Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a37b2-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="a37b2-121">In **inventario**, selezionare **App**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="a37b2-122">Carico di lavoro App, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="a37b2-123">In **Aggiungi app**, selezionare **app del settore** o **visualizzare l'anteprima di app di Windows (Win32 -)**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="a37b2-124">Se si seleziona **del settore app**, vedere [aggiungere un'app del settore Windows Intune Microsoft](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e la configurazione di applicazioni line-of-business.</span><span class="sxs-lookup"><span data-stu-id="a37b2-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="a37b2-125">Se si sceglie di **visualizzare l'anteprima di app di Windows (Win32 -)**, vedere [gestione di applicazioni Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni sull'aggiunta e la configurazione di App di Windows.</span><span class="sxs-lookup"><span data-stu-id="a37b2-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="a37b2-126">Archivio di Microsoft per le applicazioni di Business</span><span class="sxs-lookup"><span data-stu-id="a37b2-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="a37b2-p104">Se non iscritti con Microsoft Store for Business, è possibile iscriversi quando si effettuano acquisti per le applicazioni. Dopo aver ottenuto le app, è possibile sincronizzare con Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="a37b2-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="a37b2-129">**Acquisto di App da Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="a37b2-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="a37b2-130">Accedere a [Microsoft Store for Business](https://businessstore.microsoft.com) con i Store Microsoft per l'account amministratore aziendale.</span><span class="sxs-lookup"><span data-stu-id="a37b2-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a37b2-131">Selezionare **reparto per il gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="a37b2-132">Utilizzare la ricerca per trovare che l'app desiderata e selezionare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a37b2-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="a37b2-p105">Scegliere i dettagli del prodotto, **ottenere l'App**. Microsoft Store aggiunge l'app **prodotti & servizi** per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a37b2-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="a37b2-135">**Per forzare la sincronizzazione tra Intune e Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="a37b2-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="a37b2-136">Accedere al [Portale di Azure](https://portal.azure.com/) come Intune Admin o amministratore globale per il tenant</span><span class="sxs-lookup"><span data-stu-id="a37b2-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="a37b2-p106">Selezionare **tutti i gt _ servizi Intune**. Intune è nel monitoraggio + gestione sezione.</span><span class="sxs-lookup"><span data-stu-id="a37b2-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="a37b2-139">Nel riquadro Intune selezionare **Applicazioni Client**e quindi selezionare **Microsoft Store for Business**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="a37b2-140">Selezionare **Abilita** per sincronizzare le Store Microsoft per le applicazioni Business con Intune.</span><span class="sxs-lookup"><span data-stu-id="a37b2-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="a37b2-141">Se non è ancora disponibile, accesso verso l'alto e associare i Microsoft archiviati per account Business con Intune</span><span class="sxs-lookup"><span data-stu-id="a37b2-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="a37b2-142">Selezionare la lingua in cui app da Microsoft Store for Business verrà visualizzato nella console Intune</span><span class="sxs-lookup"><span data-stu-id="a37b2-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="a37b2-143">Selezionare **sincronizzazione** per sincronizzare le Store Microsoft per le applicazioni Business con Intune.</span><span class="sxs-lookup"><span data-stu-id="a37b2-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="a37b2-144">Verificare che la sincronizzazione tra Microsoft Store for Business e Intune è attiva (passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="a37b2-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="a37b2-145">**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="a37b2-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="a37b2-146">Accedere a [Microsoft Store for Business](https://businessstore.microsoft.com) con i Store Microsoft per l'account amministratore aziendale.</span><span class="sxs-lookup"><span data-stu-id="a37b2-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a37b2-147">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-147">Select **Manage**.</span></span>
3. <span data-ttu-id="a37b2-148">Selezionare **Impostazioni** e quindi scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="a37b2-149">In **Strumenti di gestione**, verificare che sia elencata Intune e che lo stato è **attivo**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="a37b2-150">Passaggio 2: Creare gruppi di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a37b2-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="a37b2-p107">Creare tre gruppi di Azure Active Directory per ogni applicazione. In questa tabella vengono illustrati i gruppi necessari (disponibile, necessario e disinstallazione).</span><span class="sxs-lookup"><span data-stu-id="a37b2-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="a37b2-153">Tipo di assegnazione App</span><span class="sxs-lookup"><span data-stu-id="a37b2-153">App assignment type</span></span> |   <span data-ttu-id="a37b2-154">Utilizzo di gruppo</span><span class="sxs-lookup"><span data-stu-id="a37b2-154">Group use</span></span>   | <span data-ttu-id="a37b2-155">Nome di esempio Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a37b2-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="a37b2-156">Disponibile</span><span class="sxs-lookup"><span data-stu-id="a37b2-156">Available</span></span> |  <span data-ttu-id="a37b2-157">L'app sarà disponibile dal sito Web o applicazioni portale della società.</span><span class="sxs-lookup"><span data-stu-id="a37b2-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="a37b2-158">Directory di mapping principale – *nome di app* -disponibile</span><span class="sxs-lookup"><span data-stu-id="a37b2-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="a37b2-159">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="a37b2-159">Required</span></span> |  <span data-ttu-id="a37b2-160">L'app sia installato nei dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="a37b2-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="a37b2-161">Directory di mapping principale – *nome di app* -obbligatorio</span><span class="sxs-lookup"><span data-stu-id="a37b2-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="a37b2-162">Disinstalla</span><span class="sxs-lookup"><span data-stu-id="a37b2-162">Uninstall</span></span> |  <span data-ttu-id="a37b2-163">App TThe viene disinstallato dai dispositivi nei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="a37b2-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="a37b2-164">Directory di mapping principale – *nome di app* -disinstallazione</span><span class="sxs-lookup"><span data-stu-id="a37b2-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="a37b2-165">Aggiungere utenti a tali gruppi per rendere disponibili app, installare l'app o rimuovere l'applicazione dal proprio dispositivo Desktop gestiti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a37b2-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="a37b2-166">Passaggio 3: Assegnare apps agli utenti</span><span class="sxs-lookup"><span data-stu-id="a37b2-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="a37b2-167">**Per assegnare l'app per gli utenti**</span><span class="sxs-lookup"><span data-stu-id="a37b2-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="a37b2-168">Accedere al [portale di amministrazione di Desktop gestiti Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a37b2-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a37b2-169">Nel riquadro Desktop gestiti selezionare **App**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="a37b2-170">Carico di lavoro App, selezionare l'applicazione che si desidera assegnare agli utenti di e selezionare **assegnare gruppi di utenti**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="a37b2-171">Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Uninstall) e assegnare al gruppo appropriato.</span><span class="sxs-lookup"><span data-stu-id="a37b2-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="a37b2-172">Nel riquadro di assegnare App, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="a37b2-172">In the Assign Apps pane, select **OK**.</span></span>

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