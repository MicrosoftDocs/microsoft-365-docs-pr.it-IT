---
title: Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 for business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come consentire a Microsoft 365 di proteggere i dispositivi Windows 10 locali con l'aggiunta di Active Directory in pochi passaggi.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560844"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="68640-103">Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="68640-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="68640-104">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="68640-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="68640-105">Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**.</span><span class="sxs-lookup"><span data-stu-id="68640-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="68640-106">Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68640-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="68640-107">In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="68640-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="68640-108">Prima di iniziare, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="68640-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="68640-109">Sincronizzare gli utenti con Azure ad con Azure ad Connect.</span><span class="sxs-lookup"><span data-stu-id="68640-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="68640-110">Completare la sincronizzazione di Azure AD Connect unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="68640-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="68640-111">Assicurarsi che tutti gli utenti di dominio sincronizzati dispongano delle licenze per Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="68640-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="68640-112">Per la procedura, vedere [sincronizzare gli utenti di dominio a Microsoft](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="68640-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="68640-113">1. verificare l'autorità MDM in Intune</span><span class="sxs-lookup"><span data-stu-id="68640-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="68640-114">Andare a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune, selezionare **registrazione dispositivo**, quindi nella pagina **Panoramica** verificare che l' **autorità MDM** sia **Intune**.</span><span class="sxs-lookup"><span data-stu-id="68640-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="68640-115">Se l' **autorità MDM** è **None**, fare clic sull' **autorità MDM** per impostarla su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="68640-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="68640-116">Se l' **autorità MDM** è **Microsoft Office 365**, passare **a dispositivi di**  >  **registrazione** e utilizzare la finestra di dialogo **Aggiungi autorità MDM** sulla destra per aggiungere l'autorità di **MDM** (la finestra di dialogo **Aggiungi autorità MDM** è disponibile solo se l' **autorità MDM** è impostata su Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="68640-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="68640-117">2. Verificare che Azure AD sia abilitato per l'aggiunta di computer</span><span class="sxs-lookup"><span data-stu-id="68640-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="68640-118">Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare **Azure Active Directory** (selezionare Mostra tutto se Azure Active Directory non è visibile) nell'elenco **admin** Centers.</span><span class="sxs-lookup"><span data-stu-id="68640-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="68640-119">Nell'interfaccia di **amministrazione di Azure Active Directory**passare a **Azure Active Directory** , scegliere **dispositivi** e quindi **Impostazioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="68640-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="68640-120">Verificare**che gli utenti possano aggiungere dispositivi ad Azure ad** sia abilitato</span><span class="sxs-lookup"><span data-stu-id="68640-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="68640-121">Per abilitare tutti gli utenti, impostare su **tutti**.</span><span class="sxs-lookup"><span data-stu-id="68640-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="68640-122">Per abilitare utenti specifici, impostare su **selezionato** per abilitare un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="68640-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="68640-123">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="68640-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="68640-124">Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68640-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="68640-125">3. Verificare che Azure AD sia abilitato per MDM</span><span class="sxs-lookup"><span data-stu-id="68640-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="68640-126">Andare all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare Seleziona gli amministratori di **endpoint**t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)</span><span class="sxs-lookup"><span data-stu-id="68640-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="68640-127">Nell'interfaccia di **amministrazione di Microsoft Endpoint Manager**passare alla **Devices**  >  **Windows**  >  **Windows Enrollment**  >  **registrazione automatica**dei dispositivi Windows Windows.</span><span class="sxs-lookup"><span data-stu-id="68640-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="68640-128">Verificare che l'ambito dell'utente MDM sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="68640-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="68640-129">Per registrare tutti i computer, impostare su **tutti** per la registrazione automatica di tutti i computer degli utenti aggiunti a Azure ad e nuovi computer quando gli utenti aggiungono un account di lavoro a Windows.</span><span class="sxs-lookup"><span data-stu-id="68640-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="68640-130">Impostato su **alcuni** per registrare i computer di un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="68640-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="68640-131">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="68640-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="68640-132">Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68640-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="68640-133">4. creare le risorse necessarie</span><span class="sxs-lookup"><span data-stu-id="68640-133">4. Create the required resources</span></span> 

<span data-ttu-id="68640-134">L'esecuzione delle attività necessarie per la [configurazione di Azure ad join ibrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) è stata semplificata mediante l'utilizzo del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) trovato nel modulo di [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68640-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="68640-135">Quando si richiama questo cmdlet, vengono creati e configurati il punto di connessione del servizio e i criteri di gruppo necessari.</span><span class="sxs-lookup"><span data-stu-id="68640-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="68640-136">È possibile installare questo modulo richiamando quanto segue da un'istanza di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68640-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="68640-137">È consigliabile installare questo modulo nel Windows Server che esegue Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="68640-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="68640-138">Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) .</span><span class="sxs-lookup"><span data-stu-id="68640-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="68640-139">Durante l'esecuzione di questa attività, sono necessarie le credenziali di amministratore globale di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="68640-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="68640-140">Quando si è pronti per creare le risorse, richiamare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68640-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="68640-141">Il primo comando consentirà di stabilire una connessione con il cloud Microsoft e, quando richiesto, specificare le credenziali di amministratore globale di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="68640-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="68640-142">5. Collegare i criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="68640-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="68640-143">Nella console Gestione criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e selezionare *collega un oggetto Criteri* di controllo esistente dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="68640-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="68640-144">Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68640-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="68640-145">Ottenere i modelli amministrativi più recenti</span><span class="sxs-lookup"><span data-stu-id="68640-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="68640-146">Se il criterio non viene visualizzato, **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite**, potrebbe essere perché non è installato ADMX per Windows 10, versione 1803, versione 1809 o versione 1903.</span><span class="sxs-lookup"><span data-stu-id="68640-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="68640-147">Per risolvere il problema, attenersi alla seguente procedura (Nota: l'ultima MDM. admx è compatibile con le versioni precedenti):</span><span class="sxs-lookup"><span data-stu-id="68640-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="68640-148">Download: [modelli amministrativi (con estensione ADMX) per l'aggiornamento a Windows 10 maggio 2019 (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="68640-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="68640-149">Installare il pacchetto nel controller di dominio primario (PDC).</span><span class="sxs-lookup"><span data-stu-id="68640-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="68640-150">Spostarsi, a seconda della versione della cartella: **c:\Programmi (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="68640-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="68640-151">Rinominare la cartella delle **definizioni dei criteri** nel percorso precedente in **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="68640-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="68640-152">Copiare la cartella **PolicyDefinitions** in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="68640-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="68640-153">Se si prevede di utilizzare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="68640-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="68640-154">Riavviare il controller di dominio principale affinché i criteri siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="68640-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="68640-155">Questa procedura funzionerà anche per qualsiasi versione futura.</span><span class="sxs-lookup"><span data-stu-id="68640-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="68640-156">A questo punto, è possibile visualizzare i criteri per **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad** disponibili.</span><span class="sxs-lookup"><span data-stu-id="68640-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
