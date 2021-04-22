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
description: Scopri come abilitare Microsoft 365 per proteggere i dispositivi Windows 10 aggiunti ad Active Directory locali in pochi passaggi.
ms.openlocfilehash: c9f5a21d993200abcf9ecf1fa236879245e1c153
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939503"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="be79e-103">Abilitare la gestione dei dispositivi Windows 10 aggiunti al dominio da Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="be79e-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="be79e-104">Se l'organizzazione usa Windows Server Active Directory in locale, puoi configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="be79e-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="be79e-105">Per configurare questa protezione, è possibile implementare dispositivi aggiunti **ad Azure AD ibridi.**</span><span class="sxs-lookup"><span data-stu-id="be79e-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="be79e-106">Questi dispositivi vengono aggiunti sia ad Active Directory locale che ad Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be79e-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="be79e-107">In questo video vengono descritti i passaggi per configurare questo scenario per lo scenario più comune, descritto anche nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="be79e-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="be79e-108">Prima di iniziare, assicurati di completare questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="be79e-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="be79e-109">Sincronizzare gli utenti con Azure AD con Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="be79e-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="be79e-110">Completare la sincronizzazione dell'unità organizzativa (OU) di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="be79e-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="be79e-111">Assicurati che tutti gli utenti di dominio sincronizzati siano licenze per Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be79e-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="be79e-112">Per [la procedura, vedere Sincronizzare gli utenti](manage-domain-users.md) di dominio con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="be79e-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="be79e-113">1. Verificare l'autorità MDM in Intune</span><span class="sxs-lookup"><span data-stu-id="be79e-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="be79e-114">Vai a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune seleziona **Registrazione** dispositivo , quindi nella pagina **Panoramica** assicurati che l'autorità **MDM** sia **Intune**.</span><span class="sxs-lookup"><span data-stu-id="be79e-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="be79e-115">Se **l'autorità MDM** **è None,** fai clic **sull'autorità MDM** per impostarla su **Intune.**</span><span class="sxs-lookup"><span data-stu-id="be79e-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="be79e-116">Se **l'autorità MDM** è **Microsoft Office 365,** vai a Dispositivi Registra dispositivi e usa la finestra di dialogo Aggiungi autorità MDM a destra per aggiungere l'autorità MDM di Intune (la finestra di dialogo Aggiungi autorità MDM è disponibile solo se l'autorità MDM è impostata su Microsoft Office  >   365).    </span><span class="sxs-lookup"><span data-stu-id="be79e-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="be79e-117">2. Verificare che Azure AD sia abilitato per l'aggiunta di computer</span><span class="sxs-lookup"><span data-stu-id="be79e-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="be79e-118">Passare all'interfaccia di amministrazione in e selezionare Azure Active Directory (selezionare Mostra tutto se <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Azure Active Directory non è visibile) nell'elenco Delle centri  **di** amministrazione.</span><span class="sxs-lookup"><span data-stu-id="be79e-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="be79e-119">**Nell'interfaccia di amministrazione di Azure Active Directory** passare ad Azure Active **Directory,** scegliere **Dispositivi** e quindi **Impostazioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="be79e-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="be79e-120">Verificare **che gli utenti possano aggiungere dispositivi ad Azure AD** sia abilitato</span><span class="sxs-lookup"><span data-stu-id="be79e-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="be79e-121">Per abilitare tutti gli utenti, impostare su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="be79e-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="be79e-122">Per abilitare utenti specifici, impostare su **Selezionato** per abilitare un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="be79e-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="be79e-123">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="be79e-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="be79e-124">Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be79e-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="be79e-125">3. Verificare che Azure AD sia abilitato per MDM</span><span class="sxs-lookup"><span data-stu-id="be79e-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="be79e-126">Accedere all'interfaccia di amministrazione in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  e selezionare Gestione **endpoint** t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)</span><span class="sxs-lookup"><span data-stu-id="be79e-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="be79e-127">**Nell'interfaccia di amministrazione di Microsoft Endpoint Manager,** vai a **Dispositivi**  >  **Registrazione automatica registrazione windows**  >    >  **di** Windows .</span><span class="sxs-lookup"><span data-stu-id="be79e-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="be79e-128">Verificare che l'ambito utente MDM sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="be79e-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="be79e-129">Per registrare tutti i computer, impostare su **Tutti** per registrare automaticamente tutti i computer utente aggiunti ad Azure AD e ai nuovi computer quando gli utenti aggiungono un account aziendale a Windows.</span><span class="sxs-lookup"><span data-stu-id="be79e-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="be79e-130">Impostare su **Some** per registrare i computer di un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="be79e-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="be79e-131">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="be79e-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="be79e-132">Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be79e-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="be79e-133">4. Creare le risorse necessarie</span><span class="sxs-lookup"><span data-stu-id="be79e-133">4. Create the required resources</span></span> 

<span data-ttu-id="be79e-134">L'esecuzione delle attività necessarie per configurare l'aggiunta ibrida [di Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) è stata semplificata tramite l'utilizzo del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) disponibile nel modulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be79e-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="be79e-135">Quando si richiama questo cmdlet, verrà creato e configurato il punto di connessione del servizio e i criteri di gruppo necessari.</span><span class="sxs-lookup"><span data-stu-id="be79e-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="be79e-136">È possibile installare questo modulo richiamando quanto segue da un'istanza di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be79e-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="be79e-137">È consigliabile installare questo modulo in Windows Server che esegue Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="be79e-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="be79e-138">Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="be79e-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="be79e-139">Per eseguire questa attività, saranno necessarie le credenziali di amministratore globale di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be79e-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="be79e-140">Quando si è pronti per creare le risorse, richiamare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="be79e-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="be79e-141">Il primo comando stabilisce una connessione con il cloud Microsoft e, quando richiesto, specifica le credenziali di amministratore globale di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be79e-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="be79e-142">5. Collegare Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="be79e-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="be79e-143">Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e scegliere Collega un oggetto Criteri di gruppo esistente *dal* menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="be79e-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="be79e-144">Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="be79e-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="be79e-145">Ottenere i modelli amministrativi più recenti</span><span class="sxs-lookup"><span data-stu-id="be79e-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="be79e-146">Se il criterio Abilita registrazione MDM automatica con le credenziali predefinite di **Azure AD** non è visualizzato, è possibile che l'ADMX non sia installato per Windows 10, versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="be79e-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="be79e-147">Per risolvere il problema, segui questi passaggi (Nota: l'ultimo file MDM.admx è compatibile con le versioni precedenti):</span><span class="sxs-lookup"><span data-stu-id="be79e-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="be79e-148">Download: [Modelli amministrativi (admx) per Windows 10 Ottobre 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="be79e-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="be79e-149">Installare il pacchetto in un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="be79e-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="be79e-150">Passare alla cartella **C:\Programmi (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)** a seconda della versione dei modelli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="be79e-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="be79e-151">Rinominare la **cartella Policy Definitions** nel percorso precedente in **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="be79e-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="be79e-152">Copiare **la cartella PolicyDefinitions** nella condivisione SYSVOL, per impostazione predefinita in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="be79e-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="be79e-153">Se si prevede di usare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="be79e-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="be79e-154">Nel caso in cui siano presenti più controller di dominio, attendere la replica di SYSVOL per la disponibilità dei criteri.</span><span class="sxs-lookup"><span data-stu-id="be79e-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="be79e-155">Questa procedura funzionerà anche per qualsiasi versione futura dei modelli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="be79e-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="be79e-156">A questo punto dovrebbe essere possibile visualizzare il criterio Abilita registrazione **AUTOMATICA MDM usando le credenziali predefinite di Azure AD** disponibili.</span><span class="sxs-lookup"><span data-stu-id="be79e-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="be79e-157">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="be79e-157">Related content</span></span>

<span data-ttu-id="be79e-158">Sincronizzare gli utenti di dominio con [Microsoft 365](manage-domain-users.md) (articolo) Creare un gruppo [nell'interfaccia](../admin/create-groups/create-groups.md) di amministrazione (articolo) [Esercitazione: Configurare](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) l'aggiunta ibrida di Azure Active Directory per i domini gestiti (articolo)</span><span class="sxs-lookup"><span data-stu-id="be79e-158">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article) [Create a group in the admin center](../admin/create-groups/create-groups.md) (article) [Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>