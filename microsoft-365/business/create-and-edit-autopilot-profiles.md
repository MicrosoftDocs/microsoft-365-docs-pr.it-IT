---
title: Creare e modificare profili AutoPilot
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informazioni su come creare, modificare, eliminare o rimuovere profili Autopilot. '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073491"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="c352b-103">Creare e modificare profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c352b-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="c352b-104">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="c352b-104">Create a profile</span></span>

<span data-ttu-id="c352b-105">Un profilo si applica a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c352b-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="c352b-106">Nell'interfaccia di amministrazione di Microsoft 365 business, \*\*\*\* \> scegliere Devices Autopilot. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c352b-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="c352b-107">Nella pagina **Autopilot** scegliere la \> scheda **profili** **creare profilo**.</span><span class="sxs-lookup"><span data-stu-id="c352b-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="c352b-108">Nella pagina **Crea profilo** immettere un nome per il profilo che ne faciliti l'identificazione, ad esempio Marketing, quindi attivare l'impostazione desiderata (per altre informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md)) e infine scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c352b-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="c352b-110">Assegnare il profilo a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="c352b-110">Apply profile to a device</span></span>

<span data-ttu-id="c352b-p101">Dopo aver creato un profilo, è possibile applicarlo a un dispositivo o a un gruppo di dispositivi. È possibile selezionare un profilo esistente nella [guida dettagliata](add-autopilot-devices-and-profile.md), applicarlo a nuovi dispositivi oppure sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c352b-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="c352b-113">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="c352b-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="c352b-114">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere un profilo nell'elenco a discesa **Profilo assegnato** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c352b-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="c352b-116">Modificare, eliminare o rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="c352b-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="c352b-p102">Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo.</span><span class="sxs-lookup"><span data-stu-id="c352b-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="c352b-120">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="c352b-120">Edit a profile</span></span>

1. <span data-ttu-id="c352b-121">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="c352b-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="c352b-122">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** aggiornare una qualsiasi delle impostazioni disponibili \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c352b-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="c352b-123">Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c352b-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="c352b-124">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="c352b-124">Delete a profile</span></span>

1. <span data-ttu-id="c352b-125">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="c352b-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="c352b-126">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** fare clic su **Elimina profilo** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c352b-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="c352b-127">Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="c352b-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="c352b-128">Rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="c352b-128">Remove a profile</span></span>

1. <span data-ttu-id="c352b-129">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="c352b-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="c352b-130">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere **Nessuno** nell'elenco a discesa **Profilo assegnato** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c352b-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
