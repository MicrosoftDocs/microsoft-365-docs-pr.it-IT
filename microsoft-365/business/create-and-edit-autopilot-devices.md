---
title: Creare e modificare dispositivi AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Informazioni su come caricare dispositivi tramite AutoPilot in Microsoft 365 Business. È possibile assegnare un profilo per un dispositivo o un gruppo di dispositivi.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868528"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="bd473-104">Creare e modificare dispositivi AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bd473-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="bd473-105">Caricare un elenco di dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd473-105">Upload a list of devices</span></span>

<span data-ttu-id="bd473-106">Per caricare i dispositivi, è possibile usare la [Guida dettagliata](add-autopilot-devices-and-profile.md) oppure usare la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="bd473-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="bd473-107">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="bd473-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="bd473-108">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bd473-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="bd473-109">Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.</span><span class="sxs-lookup"><span data-stu-id="bd473-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="bd473-110">Nell'interfaccia di amministrazione di Microsoft 365 Business scegliere **Distribuisci Windows con AutoPilot** nella scheda **Azioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="bd473-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="bd473-112">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi** \> **Aggiungi dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="bd473-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="bd473-114">Nel Pannello di **dispositivi Add** , passare a un [elenco dei dispositivi di file CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) preparato \> **salvare** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="bd473-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="bd473-115">È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV.</span><span class="sxs-lookup"><span data-stu-id="bd473-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="bd473-116">Assegnare un profilo a un dispositivo o a un gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd473-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="bd473-117">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bd473-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="bd473-118">Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**.</span><span class="sxs-lookup"><span data-stu-id="bd473-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="bd473-119">Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bd473-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
