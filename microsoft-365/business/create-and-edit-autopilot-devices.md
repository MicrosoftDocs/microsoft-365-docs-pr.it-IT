---
title: Creare e modificare dispositivi AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informazioni su come caricare i dispositivi tramite il pilota automatico in Microsoft 365 business. È possibile assegnare un profilo a un dispositivo o a un gruppo di dispositivi.
ms.openlocfilehash: 6492f1469a1ac9ea67750e9ffa071d19c88c743f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660414"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="3fc94-104">Creare e modificare dispositivi AutoPilot</span><span class="sxs-lookup"><span data-stu-id="3fc94-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="3fc94-105">Caricare un elenco di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3fc94-105">Upload a list of devices</span></span>

<span data-ttu-id="3fc94-106">Per caricare i dispositivi, è possibile usare la [Guida dettagliata](add-autopilot-devices-and-profile.md) oppure usare la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="3fc94-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="3fc94-107">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="3fc94-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="3fc94-108">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3fc94-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="3fc94-109">Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.</span><span class="sxs-lookup"><span data-stu-id="3fc94-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="3fc94-110">Nell'interfaccia di amministrazione di Microsoft 365 business, \*\*\*\* \> scegliere Devices Autopilot. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3fc94-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="3fc94-111">Nella pagina **Autopilot** scegliere la \> scheda **dispositivi** **Aggiungi dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="3fc94-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="3fc94-113">Nel riquadro **Aggiungi dispositivi** , passare a un [file CSV elenco dispositivi](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) che è stato preparato \> **Salva** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3fc94-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="3fc94-114">È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="3fc94-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="3fc94-115">Assegnare un profilo a un dispositivo o a un gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3fc94-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="3fc94-116">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3fc94-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="3fc94-117">Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**.</span><span class="sxs-lookup"><span data-stu-id="3fc94-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="3fc94-118">Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3fc94-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
