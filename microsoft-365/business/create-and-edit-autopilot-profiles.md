---
title: Creare e modificare profili AutoPilot
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informazioni su come creare, modificare, eliminare o rimuovere i profili AutoPilot. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868583"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="a6287-103">Creare e modificare profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a6287-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="a6287-104">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="a6287-104">Create a profile</span></span>

<span data-ttu-id="a6287-105">Un profilo si applica a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a6287-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="a6287-106">Nell'interfaccia di amministrazione di Microsoft 365 Business scegliere **Distribuisci Windows con AutoPilot** nella scheda **Azioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a6287-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="a6287-108">Nella pagina **Prepara Windows** scegliere la scheda **Profili** \> **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="a6287-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="a6287-109">Nella pagina **Crea profilo** immettere un nome per il profilo che ne faciliti l'identificazione, ad esempio Marketing, quindi attivare l'impostazione desiderata (per altre informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md)) e infine scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a6287-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="a6287-111">Assegnare il profilo a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="a6287-111">Apply profile to a device</span></span>

<span data-ttu-id="a6287-p101">Dopo aver creato un profilo, è possibile applicarlo a un dispositivo o a un gruppo di dispositivi. È possibile selezionare un profilo esistente nella [guida dettagliata](add-autopilot-devices-and-profile.md), applicarlo a nuovi dispositivi oppure sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a6287-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="a6287-114">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="a6287-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="a6287-115">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere un profilo nell'elenco a discesa **Profilo assegnato** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a6287-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="a6287-117">Modificare, eliminare o rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="a6287-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="a6287-p102">Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo.</span><span class="sxs-lookup"><span data-stu-id="a6287-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="a6287-121">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="a6287-121">Edit a profile</span></span>

1. <span data-ttu-id="a6287-122">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="a6287-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="a6287-123">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** aggiornare una qualsiasi delle impostazioni disponibili \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a6287-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="a6287-124">Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a6287-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="a6287-125">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="a6287-125">Delete a profile</span></span>

1. <span data-ttu-id="a6287-126">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="a6287-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="a6287-127">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** fare clic su **Elimina profilo** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a6287-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="a6287-128">Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="a6287-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="a6287-129">Rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="a6287-129">Remove a profile</span></span>

1. <span data-ttu-id="a6287-130">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="a6287-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="a6287-131">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere **Nessuno** nell'elenco a discesa **Profilo assegnato** \> **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a6287-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
