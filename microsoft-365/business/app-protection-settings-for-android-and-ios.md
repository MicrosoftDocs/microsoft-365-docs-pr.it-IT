---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
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
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informazioni su come creare, modificare o eliminare un criterio di gestione delle app e proteggere i file di lavoro su dispositivi Android o iOS.
ms.openlocfilehash: f4366230805c50fe82183431e3bd2bdfa9fddd68
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068649"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="0ec84-103">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="0ec84-103">Set app protection settings for Android or iOS devices</span></span>

![Banner che puntano https://aka.ms/aboutM365previewa.](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="0ec84-105">Creare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="0ec84-105">Create an app management policy</span></span>

1. <span data-ttu-id="0ec84-106">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0ec84-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="0ec84-107">Nel NAV sinistro, scegliere **Devices** \> \*\*\*\* \> **Add**.</span><span class="sxs-lookup"><span data-stu-id="0ec84-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="0ec84-108">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0ec84-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="0ec84-109">In **tipo di criterio**scegliere **Gestione applicazioni per Android** o **Gestione applicazioni per iOS**, a seconda del set di criteri che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="0ec84-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="0ec84-110">Espandere **Proteggi file di lavoro quando i dispositivi vengono persi o rubati** e **gestiscono come gli utenti accedono ai file di Office nei dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="0ec84-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="0ec84-111">Configurare le impostazioni come desiderate.</span><span class="sxs-lookup"><span data-stu-id="0ec84-111">Configure the settings how you would like.</span></span> <span data-ttu-id="0ec84-112">**Gestire il modo in cui gli utenti accedono ai file di Office nei dispositivi mobili** per impostazione predefinita, **ma è consigliabile** attivarlo **e accettare** i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0ec84-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="0ec84-113">Per ulteriori informazioni, vedere [available Settings](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="0ec84-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="0ec84-114">È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0ec84-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="0ec84-116">Successivamente decidere **chi otterrà queste impostazioni?**</span><span class="sxs-lookup"><span data-stu-id="0ec84-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="0ec84-117">Se non si desidera utilizzare il gruppo di sicurezza **tutti gli utenti** predefinito, scegliere **Cambia**, scegliere i gruppi di sicurezza in cui \> vengono **selezionate**le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0ec84-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="0ec84-118">Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0ec84-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="0ec84-119">Modificare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="0ec84-119">Edit an app management policy</span></span>

1. <span data-ttu-id="0ec84-120">Nella scheda **criteri** scegliere **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="0ec84-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="0ec84-121">Nel riquadro **Modifica criterio** scegliere il criterio da modificare.</span><span class="sxs-lookup"><span data-stu-id="0ec84-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="0ec84-122">Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="0ec84-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="0ec84-123">Quando si modifica un valore, il criterio viene salvato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0ec84-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="0ec84-124">Al termine, chiudere il riquadro **modifica criterio** .</span><span class="sxs-lookup"><span data-stu-id="0ec84-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="0ec84-125">Eliminare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="0ec84-125">Delete an app management policy</span></span>

1. <span data-ttu-id="0ec84-126">Nella pagina **criteri** scegliere un criterio e quindi **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0ec84-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="0ec84-127">Nel riquadro **Elimina criteri** scegliere **conferma** per eliminare i criteri o i criteri scelti.</span><span class="sxs-lookup"><span data-stu-id="0ec84-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="0ec84-128">Impostazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="0ec84-128">Available settings</span></span>

<span data-ttu-id="0ec84-129">Nelle tabelle seguenti vengono fornite informazioni dettagliate sulle impostazioni disponibili per proteggere i file di lavoro nei dispositivi e le impostazioni che controllano il modo in cui gli utenti accedono ai file di Office dai propri dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="0ec84-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="0ec84-130">Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0ec84-130">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="0ec84-131">Impostazioni per la protezione dei file di lavoro</span><span class="sxs-lookup"><span data-stu-id="0ec84-131">Settings that protect work files</span></span>

<span data-ttu-id="0ec84-132">Le impostazioni seguenti sono disponibili per la protezione dei file di lavoro in caso di perdita o di furto del dispositivo di un utente:</span><span class="sxs-lookup"><span data-stu-id="0ec84-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0ec84-133">Impostazione</span><span class="sxs-lookup"><span data-stu-id="0ec84-133">Setting</span></span>  <br/> |<span data-ttu-id="0ec84-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ec84-134">Description</span></span>  <br/> |
|<span data-ttu-id="0ec84-135">Elimina i file di lavoro dai dispositivi inattivi dopo questo numero di giorni</span><span class="sxs-lookup"><span data-stu-id="0ec84-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="0ec84-136">Se un dispositivo non viene utilizzato per il numero di giorni specificato, tutti i file di lavoro archiviati nel dispositivo verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0ec84-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="0ec84-137">Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="0ec84-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="0ec84-138">Se questa impostazione è **attiva**, l'unico percorso di salvataggio disponibile per i file di lavoro è OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="0ec84-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="0ec84-139">Crittografa i file di lavoro</span><span class="sxs-lookup"><span data-stu-id="0ec84-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="0ec84-140">Mantenere **attivata** questa impostazione in modo che i file di lavoro siano protetti dalla crittografia.</span><span class="sxs-lookup"><span data-stu-id="0ec84-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="0ec84-141">Anche se il dispositivo è perduto o rubato, nessuno può leggere i dati dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="0ec84-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="0ec84-142">Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="0ec84-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="0ec84-143">Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:</span><span class="sxs-lookup"><span data-stu-id="0ec84-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0ec84-144">Impostazione</span><span class="sxs-lookup"><span data-stu-id="0ec84-144">Setting</span></span>  <br/> |<span data-ttu-id="0ec84-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ec84-145">Description</span></span>  <br/> |
|<span data-ttu-id="0ec84-146">Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="0ec84-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="0ec84-147">Se questa impostazione è impostata **su** gli utenti devono fornire un'altra forma di autenticazione, oltre a nome utente e password, prima di poter utilizzare le app di Office nei propri dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="0ec84-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="0ec84-148">Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente</span><span class="sxs-lookup"><span data-stu-id="0ec84-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="0ec84-149">Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.</span><span class="sxs-lookup"><span data-stu-id="0ec84-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="0ec84-150">Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per</span><span class="sxs-lookup"><span data-stu-id="0ec84-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="0ec84-151">Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesto di eseguire nuovamente l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0ec84-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="0ec84-152">Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted</span><span class="sxs-lookup"><span data-stu-id="0ec84-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="0ec84-p105">È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  </span><span class="sxs-lookup"><span data-stu-id="0ec84-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="0ec84-156">Consenti agli utenti di copiare contenuti dalle app di Office in quelle personali</span><span class="sxs-lookup"><span data-stu-id="0ec84-156">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="0ec84-157">Questa operazione è consentita per impostazione predefinita, ma se l'impostazione è **attivata** l'utente potrebbe copiare le informazioni di un file di lavoro in un file personale.</span><span class="sxs-lookup"><span data-stu-id="0ec84-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="0ec84-158">Se l'impostazione è **disattivata**, l'utente non potrà copiare informazioni da un account aziendale a un'app personale o un account personale.</span><span class="sxs-lookup"><span data-stu-id="0ec84-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
