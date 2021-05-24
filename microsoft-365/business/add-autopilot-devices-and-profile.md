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
ms.openlocfilehash: cc5495f42214b222a70b281a713be782b1bf5c4f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623674"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="76a30-103">Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot</span><span class="sxs-lookup"><span data-stu-id="76a30-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="76a30-104">Puoi usare Windows AutoPilot per configurare nuovi dispositivi **Windows 10** per la tua azienda in modo che siano pronti per l'uso quando li forni ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="76a30-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="76a30-105">Requisiti dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="76a30-105">Device requirements</span></span>

<span data-ttu-id="76a30-106">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="76a30-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="76a30-107">Windows 10 versione 1703 o successiva</span><span class="sxs-lookup"><span data-stu-id="76a30-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="76a30-108">Nuovi dispositivi che non sono stati Windows'esperienza out-of-box</span><span class="sxs-lookup"><span data-stu-id="76a30-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="76a30-109">Creare dispositivi e profili con la guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="76a30-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="76a30-110">[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="76a30-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="76a30-111">Se non hai ancora creato gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'usare la guida dettagliata.</span><span class="sxs-lookup"><span data-stu-id="76a30-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="76a30-112">Puoi anche aggiungere [dispositivi](create-and-edit-autopilot-devices.md) e [assegnare](create-and-edit-autopilot-profiles.md) profili senza usare la guida.</span><span class="sxs-lookup"><span data-stu-id="76a30-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="76a30-113">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="76a30-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="76a30-114">Nel riquadro di spostamento sinistro scegliere **Dispositivi** \> **AutoPilot.**</span><span class="sxs-lookup"><span data-stu-id="76a30-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Nell'interfaccia di amministrazione scegli i dispositivi e quindi AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="76a30-116">Nella pagina **AutoPilot** toccare o fare clic su **Guida iniziale.**</span><span class="sxs-lookup"><span data-stu-id="76a30-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="76a30-118">Nella pagina Upload .csv file con **l'elenco** dei dispositivi passare a un percorso in cui si dispone del file .CSV preparato, quindi **aprire** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76a30-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="76a30-119">Il file deve avere tre intestazioni:</span><span class="sxs-lookup"><span data-stu-id="76a30-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="76a30-120">Colonna A: numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="76a30-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="76a30-121">Colonna B: ID prodotto Windows</span><span class="sxs-lookup"><span data-stu-id="76a30-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="76a30-122">Colonna C: hash dell'hardware</span><span class="sxs-lookup"><span data-stu-id="76a30-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="76a30-123">È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="76a30-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="76a30-p103">Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](../admin/misc/device-list.md). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="76a30-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="76a30-126">Questo script utilizza WMI per recuperare le proprietà necessarie a un cliente per registrare un dispositivo con Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="76a30-126">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="76a30-127">Tenere presente che è normale che il file CSV risultante non raccogli un valore PKID (Product ID) di Windows poiché non è necessario registrare un dispositivo e il valore PKID null nel file CSV di output è completamente valido.</span><span class="sxs-lookup"><span data-stu-id="76a30-127">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="76a30-128">Verranno popolati solo il numero di serie e l'hash hardware.</span><span class="sxs-lookup"><span data-stu-id="76a30-128">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="76a30-129">Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="76a30-129">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="76a30-130">Se non ne hai ancora uno, ti verrà richiesto di crearne uno.</span><span class="sxs-lookup"><span data-stu-id="76a30-130">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="76a30-131">Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="76a30-131">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="76a30-132">Le funzionalità predefinite sono obbligatorie e vengono impostate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="76a30-132">The default features are required and are set automatically.</span></span> <span data-ttu-id="76a30-133">Tali funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="76a30-133">The default features are:</span></span>
    
    - <span data-ttu-id="76a30-134">Ignora la registrazione di Cortana, OneDrive e OEM.</span><span class="sxs-lookup"><span data-stu-id="76a30-134">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="76a30-135">È necessario creare un'esperienza di accesso con il marchio della società.</span><span class="sxs-lookup"><span data-stu-id="76a30-135">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="76a30-136">Connessione i dispositivi per Azure Active Directory account e registrarli automaticamente per essere gestiti da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="76a30-136">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="76a30-137">Per ulteriori informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76a30-137">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="76a30-138">Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**.</span><span class="sxs-lookup"><span data-stu-id="76a30-138">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="76a30-139">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76a30-139">Choose **Next**.</span></span>
    
6. <span data-ttu-id="76a30-140">Il termine indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creato caricando **l'elenco** dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="76a30-140">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="76a30-141">Le impostazioni saranno effettive al successivo accesso degli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76a30-141">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="76a30-142">Scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="76a30-142">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="76a30-143">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="76a30-143">Related content</span></span>

<span data-ttu-id="76a30-144">[Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="76a30-144">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="76a30-145">[Opzioni per proteggere i dispositivi e i dati dell'app](../admin/devices/choose-device-security.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="76a30-145">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
