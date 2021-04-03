---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Scopri come creare, modificare o eliminare un criterio di gestione delle app e proteggere i file di lavoro nei dispositivi Android o iOS.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580295"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="b1a31-103">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="b1a31-103">Set app protection settings for Android or iOS devices</span></span>

<span data-ttu-id="b1a31-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b1a31-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="b1a31-105">Creare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="b1a31-105">Create an app management policy</span></span>

1. <span data-ttu-id="b1a31-106">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b1a31-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="b1a31-107">Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi** \> **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b1a31-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="b1a31-108">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b1a31-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="b1a31-109">In **Tipo di criterio** scegliere Gestione applicazioni per **Android** o Gestione applicazioni **per iOS,** a seconda del set di criteri che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="b1a31-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="b1a31-110">Espandi **Proteggi i file di lavoro quando i dispositivi vengono persi o rubati** e Gestisci il modo in cui gli utenti accedono ai **file di Office nei dispositivi mobili.**</span><span class="sxs-lookup"><span data-stu-id="b1a31-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="b1a31-111">Configurare le impostazioni come si desidera.</span><span class="sxs-lookup"><span data-stu-id="b1a31-111">Configure the settings how you would like.</span></span> <span data-ttu-id="b1a31-112">**La modalità di accesso degli utenti ai** file di Office nei  dispositivi mobili è disattivata per impostazione predefinita, ma è consigliabile attivarla e accettare i valori predefiniti. </span><span class="sxs-lookup"><span data-stu-id="b1a31-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="b1a31-113">Per ulteriori informazioni, vedere [Impostazioni disponibili.](#available-settings)</span><span class="sxs-lookup"><span data-stu-id="b1a31-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="b1a31-114">È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b1a31-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="b1a31-116">Decidere quindi **chi otterrà queste impostazioni?**</span><span class="sxs-lookup"><span data-stu-id="b1a31-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="b1a31-117">Se non si desidera utilizzare il gruppo di sicurezza **Predefinito** Tutti gli utenti, scegliere **Cambia**, scegliere i gruppi di sicurezza che ottengono queste \> **impostazioni Selezionare**.</span><span class="sxs-lookup"><span data-stu-id="b1a31-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="b1a31-118">Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b1a31-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="b1a31-119">Modificare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="b1a31-119">Edit an app management policy</span></span>

1. <span data-ttu-id="b1a31-120">Nella scheda **Criteri** scegliere **Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="b1a31-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="b1a31-121">Nel riquadro **Modifica criterio** scegliere il criterio da modificare.</span><span class="sxs-lookup"><span data-stu-id="b1a31-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="b1a31-122">Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="b1a31-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="b1a31-123">Quando si modifica un valore, questo viene salvato automaticamente nel criterio.</span><span class="sxs-lookup"><span data-stu-id="b1a31-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="b1a31-124">Al termine, chiudere il riquadro **Modifica** criterio.</span><span class="sxs-lookup"><span data-stu-id="b1a31-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="b1a31-125">Eliminare un criterio di gestione delle app</span><span class="sxs-lookup"><span data-stu-id="b1a31-125">Delete an app management policy</span></span>

1. <span data-ttu-id="b1a31-126">Nella pagina **Criteri** scegliere un criterio e quindi **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b1a31-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="b1a31-127">Nel riquadro **Elimina criterio** scegliere **Conferma** per eliminare i criteri scelti.</span><span class="sxs-lookup"><span data-stu-id="b1a31-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="b1a31-128">Impostazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="b1a31-128">Available settings</span></span>

<span data-ttu-id="b1a31-129">Nelle tabelle seguenti vengono fornite informazioni dettagliate sulle impostazioni disponibili per proteggere i file di lavoro nei dispositivi e sulle impostazioni che controllano il modo in cui gli utenti accedono ai file di Office dai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="b1a31-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="b1a31-130">Per ulteriori informazioni, vedere Come eseguire il mapping delle funzionalità di [protezione in Microsoft 365 Business Premium alle impostazioni di Intune.](map-protection-features-to-intune-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1a31-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="b1a31-131">Impostazioni per la protezione dei file di lavoro</span><span class="sxs-lookup"><span data-stu-id="b1a31-131">Settings that protect work files</span></span>

<span data-ttu-id="b1a31-132">Le impostazioni seguenti sono disponibili per la protezione dei file di lavoro in caso di perdita o di furto del dispositivo di un utente:</span><span class="sxs-lookup"><span data-stu-id="b1a31-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b1a31-133">Impostazione</span><span class="sxs-lookup"><span data-stu-id="b1a31-133">Setting</span></span>  <br/> |<span data-ttu-id="b1a31-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1a31-134">Description</span></span>  <br/> |
|<span data-ttu-id="b1a31-135">Elimina i file di lavoro dai dispositivi inattivi dopo questo numero di giorni</span><span class="sxs-lookup"><span data-stu-id="b1a31-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="b1a31-136">Se un dispositivo non viene utilizzato per il numero di giorni specificato qui, tutti i file di lavoro archiviati nel dispositivo verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1a31-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="b1a31-137">Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b1a31-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="b1a31-138">Se questa impostazione è **attivata,** l'unico percorso di salvataggio disponibile per i file di lavoro è OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="b1a31-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="b1a31-139">Crittografa i file di lavoro</span><span class="sxs-lookup"><span data-stu-id="b1a31-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="b1a31-140">Mantenere **attivata** questa impostazione in modo che i file di lavoro siano protetti dalla crittografia.</span><span class="sxs-lookup"><span data-stu-id="b1a31-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="b1a31-141">Anche se il dispositivo viene perso o rubato, nessuno può leggere i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="b1a31-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="b1a31-142">Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="b1a31-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="b1a31-143">Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:</span><span class="sxs-lookup"><span data-stu-id="b1a31-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b1a31-144">Impostazione</span><span class="sxs-lookup"><span data-stu-id="b1a31-144">Setting</span></span>  <br/> |<span data-ttu-id="b1a31-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1a31-145">Description</span></span>  <br/> |
|<span data-ttu-id="b1a31-146">Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="b1a31-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="b1a31-147">Se questa impostazione è **Attivata,** gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di poter usare le app di Office nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="b1a31-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="b1a31-148">Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente</span><span class="sxs-lookup"><span data-stu-id="b1a31-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="b1a31-149">Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.</span><span class="sxs-lookup"><span data-stu-id="b1a31-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="b1a31-150">Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per</span><span class="sxs-lookup"><span data-stu-id="b1a31-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="b1a31-151">Questa impostazione determina per quanto tempo un utente può essere inattivo prima che venga richiesto di eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b1a31-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="b1a31-152">Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted</span><span class="sxs-lookup"><span data-stu-id="b1a31-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="b1a31-p105">È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  </span><span class="sxs-lookup"><span data-stu-id="b1a31-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="b1a31-156">Non consentire agli utenti di copiare il contenuto dalle app di Office alle app personali</span><span class="sxs-lookup"><span data-stu-id="b1a31-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="b1a31-157">Questa operazione è consentita per impostazione predefinita, ma se l'impostazione è **attivata** l'utente potrebbe copiare le informazioni di un file di lavoro in un file personale.</span><span class="sxs-lookup"><span data-stu-id="b1a31-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="b1a31-158">Se l'impostazione è **disattivata**, l'utente non potrà copiare informazioni da un account aziendale a un'app personale o un account personale.</span><span class="sxs-lookup"><span data-stu-id="b1a31-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
