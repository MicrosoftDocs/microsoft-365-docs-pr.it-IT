---
title: Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informazioni su come usare Windows Autopilot per configurare nuovi dispositivi Windows 10 per la propria azienda.
ms.openlocfilehash: 8c4a14b4b9dcbf7a30c1e6e0bdd53418a1ab8a03
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660677"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="701d2-103">Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot</span><span class="sxs-lookup"><span data-stu-id="701d2-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="701d2-104">È possibile usare Windows Autopilot per configurare **nuovi** dispositivi Windows 10 per la propria azienda in modo che siano pronti per l'utilizzo produttivo non appena vengono conferiti ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="701d2-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="701d2-105">Requisiti dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="701d2-105">Device requirements</span></span>

<span data-ttu-id="701d2-106">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="701d2-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="701d2-107">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="701d2-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="701d2-108">Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.</span><span class="sxs-lookup"><span data-stu-id="701d2-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="701d2-109">Creare dispositivi e profili con la guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="701d2-109">Use the setup guide to create devices and profiles</span></span>

![Banner che puntano https://aka.ms/aboutM365previewa.](media/m365admincenterchanging.png)

<span data-ttu-id="701d2-111">Se non sono stati ancora creati gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'eseguire la guida dettagliata. È anche possibile [aggiungere dispositivi](create-and-edit-autopilot-devices.md) e [assegnare profili](create-and-edit-autopilot-profiles.md) senza usare la guida.</span><span class="sxs-lookup"><span data-stu-id="701d2-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="701d2-112">Accedere all'interfaccia di amministrazione all' <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>indirizzo.</span><span class="sxs-lookup"><span data-stu-id="701d2-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="701d2-113">Nella barra di spostamento a sinistra scegliere **dispositivi** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="701d2-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![Nell'interfaccia di amministrazione scegliere dispositivi e quindi Autopilot.](media/AutoPilot.png)
  
2. <span data-ttu-id="701d2-115">Nella pagina **Autopilot** fare clic o toccare **Guida introduttiva**.</span><span class="sxs-lookup"><span data-stu-id="701d2-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="701d2-p101">Nella pagina **Carica file CSV con l'elenco dei dispositivi** passare a un percorso in cui è presente il file CSV preparato e quindi fare clic su **Apri** \> **Avanti**. Il file deve contenere tre intestazioni:</span><span class="sxs-lookup"><span data-stu-id="701d2-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="701d2-119">Colonna A: numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="701d2-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="701d2-120">Colonna B: ID prodotto Windows</span><span class="sxs-lookup"><span data-stu-id="701d2-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="701d2-121">Colonna C: hash dell'hardware</span><span class="sxs-lookup"><span data-stu-id="701d2-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="701d2-122">È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="701d2-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="701d2-p102">Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="701d2-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="701d2-p103">Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo. Se non esiste alcun profilo, verrà chiesto di crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="701d2-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="701d2-127">Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="701d2-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="701d2-p104">Le funzionalità predefinite sono obbligatorie e verranno configurate automaticamente. Tali funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="701d2-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="701d2-130">La registrazione di Cortana, OneDrive e OEM viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="701d2-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="701d2-131">È necessario creare un'esperienza di accesso con il marchio della società.</span><span class="sxs-lookup"><span data-stu-id="701d2-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="701d2-132">I dispositivi verranno connessi ad account Azure Active Directory e registrati automaticamente in modo da essere gestiti da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="701d2-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="701d2-133">Per altre informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="701d2-133">For more information, see</span></span>
    
    <span data-ttu-id="701d2-134">[Informazioni sulle impostazioni dei profili AutoPilot](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="701d2-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="701d2-135">Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**.</span><span class="sxs-lookup"><span data-stu-id="701d2-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="701d2-136">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="701d2-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="701d2-p105">La pagina **Fine** indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creati caricando l'elenco di dispositivi. Queste impostazioni diventeranno effettive al successivo accesso degli utenti del dispositivo. Scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="701d2-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    