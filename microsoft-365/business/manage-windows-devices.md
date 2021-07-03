---
title: Abilitare i dispositivi Windows 10 aggiunti a un dominio per essere gestiti da Microsoft 365 per le aziende
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
description: Informazioni su come abilitare Microsoft 365 per proteggere i dispositivi Windows 10 aggiunti ad Active Directory in pochi passaggi.
ms.openlocfilehash: eb95c437030ae13a44f5e8043b3544d5846001c2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287696"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="d07a9-103">Abilitare i dispositivi Windows 10 aggiunti a un dominio per essere gestiti da Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d07a9-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="d07a9-104">Se l'organizzazione usa Windows Server Active Directory locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="d07a9-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="d07a9-105">Per configurare questa protezione, è possibile implementare dispositivi aggiunti **ad Azure AD ibridi.**</span><span class="sxs-lookup"><span data-stu-id="d07a9-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="d07a9-106">Questi dispositivi vengono aggiunti sia ad Active Directory locale che all'Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d07a9-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="d07a9-107">Watch: Configure Hybrid Azure Active Directory join</span><span class="sxs-lookup"><span data-stu-id="d07a9-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="d07a9-108">In questo video vengono descritti i passaggi per configurare questo scenario per lo scenario più comune, descritto anche nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d07a9-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="d07a9-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d07a9-109">Before you begin</span></span>

- <span data-ttu-id="d07a9-110">Sincronizzare gli utenti con Azure AD con Azure AD Connessione.</span><span class="sxs-lookup"><span data-stu-id="d07a9-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="d07a9-111">Completare la sincronizzazione Connessione unità organizzativa (OU) di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d07a9-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="d07a9-112">Assicurati che tutti gli utenti di dominio sincronizzati siano in grado di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d07a9-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d07a9-113">Per [la procedura, vedere Sincronizzare gli utenti](manage-domain-users.md) di dominio con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d07a9-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="d07a9-114">1. Verificare l'autorità MDM in Intune</span><span class="sxs-lookup"><span data-stu-id="d07a9-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="d07a9-115">Vai a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune, seleziona Registrazione dispositivo **,** quindi nella pagina Panoramica assicurati che l'autorità **MDM** sia  **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="d07a9-116">Se **l'autorità MDM** **è None,** fai clic **sull'autorità MDM** per impostarla su **Intune.**</span><span class="sxs-lookup"><span data-stu-id="d07a9-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="d07a9-117">Se **l'autorità MDM** è Microsoft Office 365 , vai **a** Dispositivi Registra dispositivi e usa la finestra di dialogo Aggiungi autorità MDM a destra per aggiungere l'autorità MDM di Intune (la finestra di dialogo Aggiungi autorità MDM è disponibile solo se l'autorità MDM è impostata su  >   Microsoft Office 365).    </span><span class="sxs-lookup"><span data-stu-id="d07a9-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="d07a9-118">2. Verificare che Azure AD sia abilitato per l'aggiunta di computer</span><span class="sxs-lookup"><span data-stu-id="d07a9-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="d07a9-119">Passare all'interfaccia di amministrazione in e selezionare Azure Active Directory (selezionare Mostra tutto se Azure Active Directory non <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> è visibile)  nell'elenco Delle admin **center.**</span><span class="sxs-lookup"><span data-stu-id="d07a9-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="d07a9-120">**Nell'Azure Active Directory di amministrazione,** vai a **Azure Active Directory** , scegli **Dispositivi** e quindi **Impostazioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="d07a9-121">Verificare **che gli utenti possano aggiungere dispositivi ad Azure AD** sia abilitato</span><span class="sxs-lookup"><span data-stu-id="d07a9-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="d07a9-122">Per abilitare tutti gli utenti, impostare su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="d07a9-123">Per abilitare utenti specifici, impostare su **Selezionato** per abilitare un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="d07a9-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="d07a9-124">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d07a9-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="d07a9-125">Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d07a9-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="d07a9-126">3. Verificare che Azure AD sia abilitato per MDM</span><span class="sxs-lookup"><span data-stu-id="d07a9-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="d07a9-127">Passare all'interfaccia di amministrazione in e selezionare Gestione endpoint t (selezionare Mostra tutto se Endpoint Manager <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> non è visibile)   </span><span class="sxs-lookup"><span data-stu-id="d07a9-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="d07a9-128">**Nell'Microsoft Endpoint Manager di amministrazione** passare a Dispositivi  >  **Windows**  >  **Windows registrazione**  >  **automatica**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="d07a9-129">Verificare che l'ambito utente MDM sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="d07a9-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="d07a9-130">Per registrare tutti i computer, impostare su **Tutti** per registrare automaticamente tutti i computer utente aggiunti ad Azure AD e ai nuovi computer quando gli utenti aggiungono un account aziendale a Windows.</span><span class="sxs-lookup"><span data-stu-id="d07a9-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="d07a9-131">Impostare su **Some** per registrare i computer di un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="d07a9-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="d07a9-132">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d07a9-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="d07a9-133">Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d07a9-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="d07a9-134">4. Creare le risorse necessarie</span><span class="sxs-lookup"><span data-stu-id="d07a9-134">4. Create the required resources</span></span> 

<span data-ttu-id="d07a9-135">L'esecuzione delle attività necessarie per configurare l'aggiunta ibrida [di Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) è stata semplificata tramite l'utilizzo del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) disponibile nel modulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07a9-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="d07a9-136">Quando si richiama questo cmdlet, verrà creato e configurato il punto di connessione del servizio e i criteri di gruppo necessari.</span><span class="sxs-lookup"><span data-stu-id="d07a9-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="d07a9-137">È possibile installare questo modulo richiamando quanto segue da un'istanza di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d07a9-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="d07a9-138">È consigliabile installare questo modulo nel Windows Server che esegue Azure AD Connessione.</span><span class="sxs-lookup"><span data-stu-id="d07a9-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="d07a9-139">Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="d07a9-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="d07a9-140">Per eseguire questa attività, Microsoft 365 Business Premium le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d07a9-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="d07a9-141">Quando si è pronti per creare le risorse, richiamare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d07a9-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="d07a9-142">Il primo comando stabilisce una connessione con il cloud Microsoft e, quando richiesto, specifica le credenziali Microsoft 365 Business Premium amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d07a9-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="d07a9-143">5. Collegare Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="d07a9-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="d07a9-144">Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e scegliere Collega un oggetto Criteri di gruppo esistente *dal* menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d07a9-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="d07a9-145">Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d07a9-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="d07a9-146">Ottenere i modelli amministrativi più recenti</span><span class="sxs-lookup"><span data-stu-id="d07a9-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="d07a9-147">Se il criterio Abilita registrazione MDM automatica con le credenziali predefinite di **Azure AD** non è visualizzato, è possibile che l'ADMX non sia installato per Windows 10, versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d07a9-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="d07a9-148">Per risolvere il problema, segui questi passaggi (Nota: l'ultimo file MDM.admx è compatibile con le versioni precedenti):</span><span class="sxs-lookup"><span data-stu-id="d07a9-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1. <span data-ttu-id="d07a9-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="d07a9-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2. <span data-ttu-id="d07a9-150">Installare il pacchetto in un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="d07a9-150">Install the package on a Domain Controller.</span></span>
3. <span data-ttu-id="d07a9-151">Passare alla cartella **C:\Programmi (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2) a** seconda della versione dei modelli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="d07a9-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4. <span data-ttu-id="d07a9-152">Rinominare la **cartella Policy Definitions** nel percorso precedente in **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5. <span data-ttu-id="d07a9-153">Copiare **la cartella PolicyDefinitions** nella condivisione SYSVOL, per impostazione predefinita in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="d07a9-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span>
   - <span data-ttu-id="d07a9-154">Se si prevede di usare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="d07a9-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6. <span data-ttu-id="d07a9-155">Nel caso in cui siano presenti più controller di dominio, attendere la replica di SYSVOL per la disponibilità dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d07a9-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="d07a9-156">Questa procedura funzionerà anche per qualsiasi versione futura dei modelli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="d07a9-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="d07a9-157">A questo punto dovrebbe essere possibile visualizzare il criterio Abilita registrazione **AUTOMATICA MDM usando le credenziali predefinite di Azure AD** disponibili.</span><span class="sxs-lookup"><span data-stu-id="d07a9-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="d07a9-158">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d07a9-158">Related content</span></span>

<span data-ttu-id="d07a9-159">[Sincronizzare gli utenti di dominio Microsoft 365](manage-domain-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d07a9-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="d07a9-160">[Creare un gruppo nell'interfaccia di amministrazione](../admin/create-groups/create-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d07a9-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="d07a9-161">[Esercitazione: Configurare l'Azure Active Directory ibrida per i domini gestiti](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d07a9-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>