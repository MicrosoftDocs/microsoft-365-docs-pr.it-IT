---
title: Creare e modificare dispositivi AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informazioni su come caricare i dispositivi tramite il pilota automatico in Microsoft 365 Business Premium. È possibile assegnare un profilo a un dispositivo o a un gruppo di dispositivi.
ms.openlocfilehash: 83c027cfe019e037518c4ca13eb331e5300fc2c1
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165862"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="6bef6-104">Creare e modificare dispositivi AutoPilot</span><span class="sxs-lookup"><span data-stu-id="6bef6-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="6bef6-105">Caricare un elenco di dispositivi</span><span class="sxs-lookup"><span data-stu-id="6bef6-105">Upload a list of devices</span></span>

<span data-ttu-id="6bef6-106">È possibile utilizzare la [Guida dettagliata](add-autopilot-devices-and-profile.md) per caricare i dispositivi, ma è anche possibile caricare i dispositivi nella scheda **dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="6bef6-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="6bef6-107">I dispositivi devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bef6-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="6bef6-108">Windows 10, versione 1703 o successiva</span><span class="sxs-lookup"><span data-stu-id="6bef6-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="6bef6-109">Nuovi dispositivi che non sono stati eseguiti tramite Windows out-of-Box Experience</span><span class="sxs-lookup"><span data-stu-id="6bef6-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="6bef6-110">Nell'interfaccia di amministrazione di Microsoft 365, scegliere **Devices** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="6bef6-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="6bef6-111">Nella pagina **Autopilot** scegliere la scheda \> **dispositivi** **Aggiungi dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="6bef6-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="6bef6-113">Nel pannello **Aggiungi dispositivi** , passare a un [file CSV dell'elenco dei](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) dispositivi preparato \> **Salva** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6bef6-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="6bef6-114">È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="6bef6-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="6bef6-115">Assegnare un profilo a un dispositivo o a un gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="6bef6-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="6bef6-116">Nella pagina **prepara Windows** scegliere la scheda **dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6bef6-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="6bef6-117">Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**.</span><span class="sxs-lookup"><span data-stu-id="6bef6-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="6bef6-118">Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6bef6-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
