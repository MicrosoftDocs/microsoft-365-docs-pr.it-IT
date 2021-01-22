---
title: Configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Informazioni su come configurare i dispositivi Windows che eseguono Windows 10 Pro per gli utenti di Microsoft 365 Business Premium, abilitando la gestione centralizzata e i controlli di sicurezza.
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928725"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="f80ba-103">Configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f80ba-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="f80ba-104">Prerequisiti per la configurazione dei dispositivi Windows per gli utenti di Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f80ba-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="f80ba-105">Prima di poter configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium, assicurati che tutti i dispositivi Windows esercitino Windows 10 Pro versione 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="f80ba-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="f80ba-106">Windows 10 Pro è un prerequisito per la distribuzione di Windows 10 Business, un set di servizi cloud e funzionalità di gestione dei dispositivi che integrano Windows 10 Pro e consentono i controlli di sicurezza e gestione centralizzata di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f80ba-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="f80ba-107">Se si dispone di dispositivi Windows che eseguono Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, l'abbonamento a Microsoft 365 Business Premium consente di eseguire un aggiornamento a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f80ba-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="f80ba-108">Per altre informazioni su come eseguire l'aggiornamento di dispositivi Windows Pro a Windows 10 Pro Creators Update, seguire i passaggi descritti in questo argomento: [Eseguire l'aggiornamento di dispositivi Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="f80ba-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="f80ba-109">Vedi [Verificare che il dispositivo sia connesso ad Azure AD](#verify-the-device-is-connected-to-azure-ad) per verificare di disporre dell'aggiornamento o per verificare che l'aggiornamento sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f80ba-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="f80ba-110">Guardare un breve video sulla connessione di Windows a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f80ba-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="f80ba-111">Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="f80ba-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="f80ba-112">Unire i dispositivi Windows 10 a Azure AD dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f80ba-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="f80ba-113">Quando tutti i dispositivi Windows nell'organizzazione sono stati aggiornati a Windows 10 Pro Creators Update o già eseguono Windows 10 Pro Creators Update, puoi aggiungere questi dispositivi ad Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f80ba-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="f80ba-114">Una volta aggiunti, i dispositivi verranno aggiornati automaticamente a Windows 10 Business, che fa parte dell'abbonamento a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f80ba-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="f80ba-115">Per un dispositivo Windows 10 Pro nuovo o appena aggiornato</span><span class="sxs-lookup"><span data-stu-id="f80ba-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="f80ba-116">Per un nuovo dispositivo che esegue Windows 10 Pro Creators Update oppure appena aggiornato a Windows 10 Pro Creators Update ma che non è ancora stato configurato con Windows 10, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f80ba-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="f80ba-117">Seguire la procedura di installazione di Windows 10 finché non viene visualizzata la pagina **Che configurazione vuoi eseguire?**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="f80ba-119">Qui, scegliere **Configura per un'organizzazione e** quindi immettere il nome utente e la password per Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f80ba-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="f80ba-120">Completare la configurazione del dispositivo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f80ba-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="f80ba-p103">Al termine, l'utente verrà connesso a Azure Active Directory dell'organizzazione. Per accertarsene, vedere [Verificare che il dispositivo sia connesso a Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="f80ba-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="f80ba-123">Per un dispositivo già configurato e che esegue Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="f80ba-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="f80ba-124">**Collegare gli utenti a Azure Active Directory:**</span><span class="sxs-lookup"><span data-stu-id="f80ba-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="f80ba-125">Nel PC Windows dell'utente, che esegue Windows 10 Pro, versione 1703 (Creators Update) (vedere i [prerequisiti](pre-requisites-for-data-protection.md)), fare clic sul logo Windows e quindi sull'icona Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f80ba-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="f80ba-127">In **Impostazioni** passare ad **Account**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="f80ba-129">Nella pagina **Le tue info** fare clic su **Accedi all'azienda o all'istituto di istruzione** \> **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="f80ba-131">Nella finestra di dialogo **Imposta un account aziendale o dell'istituto di istruzione**, in **Azioni alternative**, scegliere **Aggiungi il dispositivo ad Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="f80ba-133">Nella pagina **Esegui l'accesso** immettere l'account aziendale o dell'istituto di iscrizione \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="f80ba-134">Nella pagina **Immettere la password** immettere la password \> **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="f80ba-136">Nella pagina **Verificare che questa sia la pagina dell'organizzazione,** verificare che le informazioni siano corrette e scegliere **Partecipa.**</span><span class="sxs-lookup"><span data-stu-id="f80ba-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="f80ba-137">On the **You're all set!**</span><span class="sxs-lookup"><span data-stu-id="f80ba-137">On the **You're all set!**</span></span> <span data-ttu-id="f80ba-138">, chosse **Done.**</span><span class="sxs-lookup"><span data-stu-id="f80ba-138">page, chosse **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, choose Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="f80ba-140">Se sono stati caricati file in OneDrive for Business, sincronizzarli nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f80ba-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="f80ba-141">Se hai usato uno strumento di terze parti per eseguire la migrazione di profili e file, sincronizza anche questi con il nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="f80ba-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="f80ba-142">Verificare che il dispositivo sia connesso a Azure AD</span><span class="sxs-lookup"><span data-stu-id="f80ba-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="f80ba-143">Per verificare lo stato  della sincronizzazione, nella pagina  Accedi all'istituto di istruzione **o** all'istituto di istruzione in Impostazioni selezionare l'area Connesso a _ per esporre i pulsanti \<organization name\> **Informazioni** e **Disconnetti.**</span><span class="sxs-lookup"><span data-stu-id="f80ba-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="f80ba-144">Scegliere **Info per** ottenere lo stato di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="f80ba-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="f80ba-145">Nella pagina **Stato sincronizzazione** scegliere **Sincronizza** per ottenere i criteri di gestione dei dispositivi mobili più recenti nel PC.</span><span class="sxs-lookup"><span data-stu-id="f80ba-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="f80ba-146">Per iniziare a usare l'account Microsoft 365 Business Premium, passare al pulsante **Start** di Windows, fare clic con il pulsante destro del mouse sull'immagine dell'account corrente e quindi scegliere **Cambia account.**</span><span class="sxs-lookup"><span data-stu-id="f80ba-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="f80ba-147">Accedere usando l'indirizzo di posta elettronica e la password della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f80ba-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="f80ba-149">Verificare che il PC sia aggiornato a Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="f80ba-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="f80ba-150">Verificare che i dispositivi Windows 10 aggiunti ad Azure AD siano aggiornati a Windows 10 Business come parte dell'abbonamento a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f80ba-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="f80ba-151">Selezionare **Impostazioni** \> **Sistema** \> **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="f80ba-152">Verificare che in **Edizione** sia indicato **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="f80ba-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="f80ba-154">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f80ba-154">Next steps</span></span>

<span data-ttu-id="f80ba-155">Per configurare i dispositivi mobili, vedere Configurare i dispositivi mobili per gli utenti di [Microsoft 365 Business Premium,](set-up-mobile-devices.md)Per impostare i criteri di protezione dei dispositivi o delle app, vedere [Gestire Microsoft 365 per le aziende.](manage.md)</span><span class="sxs-lookup"><span data-stu-id="f80ba-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="f80ba-156">Per altre informazioni sulla configurazione e sull'uso di Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f80ba-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="f80ba-157">Video di formazione su Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="f80ba-157">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
