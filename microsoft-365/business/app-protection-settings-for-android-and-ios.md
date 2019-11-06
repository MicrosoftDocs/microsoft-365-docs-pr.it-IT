---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
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
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informazioni su come creare, modificare o eliminare un criterio di gestione delle app e proteggere i file di lavoro su dispositivi Android o iOS.
ms.openlocfilehash: 914e6848ac46eb334516aadff2827da2b83a38c4
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002086"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="51f60-103">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="51f60-103">Set app protection settings for Android or iOS devices</span></span>

![Banner che puntano https://aka.ms/aboutM365previewa.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="51f60-105">Creare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="51f60-105">Create an app management policy</span></span>

1. <span data-ttu-id="51f60-106">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="51f60-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="51f60-107">Nel NAV sinistro, scegliere **Devices** \> \*\*\*\* \> **Add**.</span><span class="sxs-lookup"><span data-stu-id="51f60-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="51f60-108">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="51f60-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="51f60-109">In **Tipo di criterio** scegliere **Gestione applicazioni per Android** o **Gestione applicazioni per iOS** a seconda del set di criteri che si vuole creare.</span><span class="sxs-lookup"><span data-stu-id="51f60-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="51f60-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="51f60-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="51f60-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="51f60-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="51f60-112">Per ulteriori informazioni, vedere [available Settings](#available-settings) .</span><span class="sxs-lookup"><span data-stu-id="51f60-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="51f60-113">È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51f60-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="51f60-p102">In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="51f60-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="51f60-117">Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="51f60-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="51f60-118">Modificare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="51f60-118">Edit an app management policy</span></span>

1. <span data-ttu-id="51f60-119">Nella scheda **criteri** scegliere **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="51f60-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="51f60-120">Nel riquadro **Modifica criterio** scegliere il criterio da modificare.</span><span class="sxs-lookup"><span data-stu-id="51f60-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="51f60-p103">Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio. Quando si modifica un valore, questo viene automaticamente salvato nel criterio.</span><span class="sxs-lookup"><span data-stu-id="51f60-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="51f60-123">Al termine, chiudere il riquadro **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="51f60-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="51f60-124">Eliminare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="51f60-124">Delete an app management policy</span></span>

1. <span data-ttu-id="51f60-125">Nella pagina **criteri** scegliere un criterio e quindi **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="51f60-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="51f60-126">Nel riquadro **Elimina criteri** scegliere **conferma** per eliminare i criteri o i criteri scelti.</span><span class="sxs-lookup"><span data-stu-id="51f60-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="51f60-127">Impostazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="51f60-127">Available settings</span></span>

<span data-ttu-id="51f60-128">Nelle tabelle seguenti vengono fornite informazioni dettagliate sulle impostazioni disponibili per proteggere i file di lavoro nei dispositivi e le impostazioni che controllano il modo in cui gli utenti accedono ai file di Office dai propri dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="51f60-128">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="51f60-129">Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="51f60-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="51f60-130">Impostazioni per la protezione dei file di lavoro</span><span class="sxs-lookup"><span data-stu-id="51f60-130">Settings that protect work files</span></span>

<span data-ttu-id="51f60-131">Le impostazioni seguenti sono disponibili per la protezione dei file di lavoro in caso di perdita o di furto del dispositivo di un utente:</span><span class="sxs-lookup"><span data-stu-id="51f60-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="51f60-132">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51f60-132">Setting</span></span>  <br/> |<span data-ttu-id="51f60-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51f60-133">Description</span></span>  <br/> |
|<span data-ttu-id="51f60-134">Elimina i file di lavoro dai dispositivi inattivi dopo questo numero di giorni</span><span class="sxs-lookup"><span data-stu-id="51f60-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="51f60-135">Se un dispositivo non viene usato per il numero di giorni specificato qui, eventuali file di lavoro archiviati nel dispositivo verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="51f60-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="51f60-136">Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="51f60-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="51f60-137">Se questa impostazione è **attivata**, l'unico percorso disponibile per il salvataggio dei file di lavoro sarà OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="51f60-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="51f60-138">Crittografa i file di lavoro</span><span class="sxs-lookup"><span data-stu-id="51f60-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="51f60-p104">Mantenere **attivata** questa impostazione in modo che i file di lavoro siano protetti dalla crittografia. Anche in caso di perdita o di furto del dispositivo, nessuno sarà in grado di leggere i dati aziendali.  </span><span class="sxs-lookup"><span data-stu-id="51f60-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="51f60-141">Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="51f60-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="51f60-142">Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:</span><span class="sxs-lookup"><span data-stu-id="51f60-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="51f60-143">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51f60-143">Setting</span></span>  <br/> |<span data-ttu-id="51f60-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51f60-144">Description</span></span>  <br/> |
|<span data-ttu-id="51f60-145">Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="51f60-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="51f60-146">Se questa impostazione è **attivata**, gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di potere usare le app di Office nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="51f60-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="51f60-147">Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente</span><span class="sxs-lookup"><span data-stu-id="51f60-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="51f60-148">Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.</span><span class="sxs-lookup"><span data-stu-id="51f60-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="51f60-149">Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per</span><span class="sxs-lookup"><span data-stu-id="51f60-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="51f60-150">Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesta la ripetizione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="51f60-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="51f60-151">Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted</span><span class="sxs-lookup"><span data-stu-id="51f60-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="51f60-p105">È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  </span><span class="sxs-lookup"><span data-stu-id="51f60-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="51f60-155">Consenti agli utenti di copiare contenuti dalle app di Office in quelle personali</span><span class="sxs-lookup"><span data-stu-id="51f60-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="51f60-156">Questa operazione è consentita per impostazione predefinita, ma se l'impostazione è **attivata** l'utente potrebbe copiare le informazioni di un file di lavoro in un file personale.</span><span class="sxs-lookup"><span data-stu-id="51f60-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="51f60-157">Se l'impostazione è **disattivata**, l'utente non potrà copiare informazioni da un account aziendale a un'app personale o un account personale.</span><span class="sxs-lookup"><span data-stu-id="51f60-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

