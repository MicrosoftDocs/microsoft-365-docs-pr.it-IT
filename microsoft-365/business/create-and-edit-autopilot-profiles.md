---
title: Creare e modificare profili AutoPilot
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Informazioni su come creare un profilo pilota automatico e applicarlo a un dispositivo, nonché modificare o eliminare un profilo o rimuovere un profilo da un dispositivo.
ms.openlocfilehash: 6a8057969242d839ebbb4cbef8d26dd3f1858c59
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417337"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="66787-103">Creare e modificare profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="66787-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="66787-104">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="66787-104">Create a profile</span></span>

<span data-ttu-id="66787-105">Un profilo si applica a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="66787-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="66787-106">Nell'interfaccia di amministrazione di Microsoft 365 business, scegliere **Devices** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="66787-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="66787-107">Nella pagina **Autopilot** scegliere la scheda \> **profili** **creare profilo**.</span><span class="sxs-lookup"><span data-stu-id="66787-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="66787-108">Nella pagina **Crea profilo** , immettere un nome per il profilo che consenta di identificarlo, ad esempio marketing.</span><span class="sxs-lookup"><span data-stu-id="66787-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="66787-109">Attiva l'impostazione desiderata e quindi scegli **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66787-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="66787-110">Per ulteriori informazioni sulle impostazioni dei profili Autopilot, vedere [informazioni sulle impostazioni dei profili Autopilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="66787-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="66787-112">Assegnare il profilo a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="66787-112">Apply profile to a device</span></span>

<span data-ttu-id="66787-113">Dopo aver creato un profilo, è possibile applicarlo a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="66787-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="66787-114">È possibile selezionare un profilo esistente nella [Guida dettagliata](add-autopilot-devices-and-profile.md) e applicarlo ai nuovi dispositivi oppure sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="66787-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="66787-115">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="66787-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="66787-116">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **dispositivo** scegliere un profilo dall'elenco \> a discesa **profilo assegnato** **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66787-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="66787-118">Modificare, eliminare o rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="66787-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="66787-p103">Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo.</span><span class="sxs-lookup"><span data-stu-id="66787-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="66787-122">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="66787-122">Edit a profile</span></span>

1. <span data-ttu-id="66787-123">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="66787-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="66787-124">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **profilo** aggiornare le impostazioni \> disponibili per il **salvataggio**.</span><span class="sxs-lookup"><span data-stu-id="66787-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="66787-125">Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="66787-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="66787-126">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="66787-126">Delete a profile</span></span>

1. <span data-ttu-id="66787-127">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="66787-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="66787-128">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **profilo** selezionare **Delete profile** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="66787-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="66787-129">Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="66787-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="66787-130">Rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="66787-130">Remove a profile</span></span>

1. <span data-ttu-id="66787-131">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="66787-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="66787-132">Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **dispositivo** scegliere **nessuno** nell'elenco \> a discesa **profilo assegnato** **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66787-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
