---
title: Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Scopri come usare Windows AutoPilot per configurare nuovi dispositivi Windows 10 per la tua azienda in modo che siano pronti per l'uso da parte dei dipendenti.
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636107"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="8503b-103">Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot</span><span class="sxs-lookup"><span data-stu-id="8503b-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="8503b-104">Puoi usare Windows AutoPilot per configurare nuovi dispositivi **Windows 10** per la tua azienda in modo che siano pronti per l'uso quando li forni ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8503b-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="8503b-105">Requisiti dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="8503b-105">Device requirements</span></span>

<span data-ttu-id="8503b-106">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="8503b-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="8503b-107">Windows 10 versione 1703 o successiva</span><span class="sxs-lookup"><span data-stu-id="8503b-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="8503b-108">Nuovi dispositivi che non sono stati Windows'esperienza out-of-box</span><span class="sxs-lookup"><span data-stu-id="8503b-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="8503b-109">Creare dispositivi e profili con la guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="8503b-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="8503b-110">Se non hai ancora creato gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'usare la guida dettagliata.</span><span class="sxs-lookup"><span data-stu-id="8503b-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="8503b-111">Puoi anche aggiungere [dispositivi](create-and-edit-autopilot-devices.md) e [assegnare](create-and-edit-autopilot-profiles.md) profili senza usare la guida.</span><span class="sxs-lookup"><span data-stu-id="8503b-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="8503b-112">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="8503b-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="8503b-113">Nel riquadro di spostamento sinistro scegliere **Dispositivi** \> **AutoPilot.**</span><span class="sxs-lookup"><span data-stu-id="8503b-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Nell'interfaccia di amministrazione scegli i dispositivi e quindi AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="8503b-115">Nella pagina **AutoPilot** toccare o fare clic su **Guida iniziale.**</span><span class="sxs-lookup"><span data-stu-id="8503b-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="8503b-117">Nella pagina Upload .csv file con **l'elenco** dei dispositivi passare a un percorso in cui si dispone del file .CSV preparato, quindi **aprire** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8503b-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="8503b-118">Il file deve avere tre intestazioni:</span><span class="sxs-lookup"><span data-stu-id="8503b-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="8503b-119">Colonna A: numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8503b-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="8503b-120">Colonna B: ID prodotto Windows</span><span class="sxs-lookup"><span data-stu-id="8503b-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="8503b-121">Colonna C: hash dell'hardware</span><span class="sxs-lookup"><span data-stu-id="8503b-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="8503b-122">È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8503b-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="8503b-p103">Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](../admin/misc/device-list.md). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="8503b-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8503b-125">Questo script utilizza WMI per recuperare le proprietà necessarie a un cliente per registrare un dispositivo con Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8503b-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="8503b-126">Tenere presente che è normale che il file CSV risultante non raccogli un valore PKID (Product ID) di Windows poiché non è necessario registrare un dispositivo e il valore PKID null nel file CSV di output è completamente valido.</span><span class="sxs-lookup"><span data-stu-id="8503b-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="8503b-127">Verranno popolati solo il numero di serie e l'hash hardware.</span><span class="sxs-lookup"><span data-stu-id="8503b-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="8503b-128">Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="8503b-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="8503b-129">Se non ne hai ancora uno, ti verrà richiesto di crearne uno.</span><span class="sxs-lookup"><span data-stu-id="8503b-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="8503b-130">Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8503b-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="8503b-131">Le funzionalità predefinite sono obbligatorie e vengono impostate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8503b-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="8503b-132">Tali funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="8503b-132">The default features are:</span></span>
    
    - <span data-ttu-id="8503b-133">Ignora la registrazione di Cortana, OneDrive e OEM.</span><span class="sxs-lookup"><span data-stu-id="8503b-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="8503b-134">È necessario creare un'esperienza di accesso con il marchio della società.</span><span class="sxs-lookup"><span data-stu-id="8503b-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="8503b-135">Connessione i dispositivi per Azure Active Directory account e registrarli automaticamente per essere gestiti da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8503b-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="8503b-136">Per ulteriori informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8503b-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="8503b-137">Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**.</span><span class="sxs-lookup"><span data-stu-id="8503b-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="8503b-138">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8503b-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="8503b-139">Il termine indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creato caricando **l'elenco** dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8503b-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="8503b-140">Le impostazioni saranno effettive al successivo accesso degli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8503b-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="8503b-141">Scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8503b-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="8503b-142">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="8503b-142">Related content</span></span>

<span data-ttu-id="8503b-143">[Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8503b-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="8503b-144">[Opzioni per proteggere i dispositivi e i dati dell'app](../admin/devices/choose-device-security.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8503b-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
