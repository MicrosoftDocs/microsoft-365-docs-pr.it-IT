---
title: Creare e modificare profili AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Scopri come creare un profilo AutoPilot e applicarlo a un dispositivo, nonché modificare o eliminare un profilo o rimuovere un profilo da un dispositivo.
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580255"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="7646c-103">Creare e modificare profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="7646c-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="7646c-104">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="7646c-104">Create a profile</span></span>

<span data-ttu-id="7646c-105">Un profilo si applica a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7646c-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="7646c-106">Nell'Microsoft 365 di amministrazione scegliere **Dispositivi** \> **AutoPilot.**</span><span class="sxs-lookup"><span data-stu-id="7646c-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="7646c-107">Nella pagina **AutoPilot** scegliere la **scheda Profili** \> **Crea profilo.**</span><span class="sxs-lookup"><span data-stu-id="7646c-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="7646c-108">Nella pagina **Crea profilo** immettere un nome per il profilo che consente di identificarlo, ad esempio Marketing.</span><span class="sxs-lookup"><span data-stu-id="7646c-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="7646c-109">Attivare l'impostazione desiderata e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7646c-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="7646c-110">Per ulteriori informazioni sulle impostazioni del profilo AutoPilot, vedere Informazioni sulle impostazioni del profilo [AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7646c-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="7646c-112">Assegnare il profilo a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7646c-112">Apply profile to a device</span></span>

<span data-ttu-id="7646c-113">Dopo aver creato un profilo, puoi applicarlo a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7646c-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="7646c-114">Puoi selezionare un profilo [](add-autopilot-devices-and-profile.md) esistente nella guida dettagliata e applicarlo a nuovi dispositivi o sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7646c-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="7646c-115">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="7646c-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="7646c-116">Seleziona la casella di controllo accanto al  nome di un dispositivo  e scegli un profilo nell'elenco a discesa Profilo assegnato Salva nel pannello \> **Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="7646c-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="7646c-118">Modificare, eliminare o rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="7646c-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="7646c-p103">Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo.</span><span class="sxs-lookup"><span data-stu-id="7646c-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="7646c-122">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="7646c-122">Edit a profile</span></span>

1. <span data-ttu-id="7646c-123">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="7646c-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="7646c-124">Seleziona la casella di controllo accanto al nome di un dispositivo e nel pannello **Profilo** aggiorna le impostazioni disponibili \> **Salva.**</span><span class="sxs-lookup"><span data-stu-id="7646c-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="7646c-125">Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7646c-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="7646c-126">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="7646c-126">Delete a profile</span></span>

1. <span data-ttu-id="7646c-127">Nella pagina **Prepara Windows** scegliere la scheda **Profili**.</span><span class="sxs-lookup"><span data-stu-id="7646c-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="7646c-128">Seleziona la casella di controllo accanto al nome di un dispositivo e nel pannello **Profilo** seleziona **Elimina profilo** \> **Salva.**</span><span class="sxs-lookup"><span data-stu-id="7646c-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="7646c-129">Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="7646c-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="7646c-130">Rimuovere un profilo</span><span class="sxs-lookup"><span data-stu-id="7646c-130">Remove a profile</span></span>

1. <span data-ttu-id="7646c-131">Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="7646c-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="7646c-132">Seleziona la casella di controllo accanto al  nome di un dispositivo  e nel pannello Dispositivo scegli **Nessuno** nell'elenco a discesa Profilo assegnato \> **Salva.**</span><span class="sxs-lookup"><span data-stu-id="7646c-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
