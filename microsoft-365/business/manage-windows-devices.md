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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564948"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="a4e90-103">Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="a4e90-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="a4e90-104">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="a4e90-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="a4e90-105">Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="a4e90-106">Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4e90-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="a4e90-107">In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="a4e90-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="a4e90-108">Prima di iniziare, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a4e90-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="a4e90-109">Sincronizzare gli utenti con Azure ad con Azure ad Connect.</span><span class="sxs-lookup"><span data-stu-id="a4e90-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="a4e90-110">Completare la sincronizzazione di Azure AD Connect unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="a4e90-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="a4e90-111">Assicurarsi che tutti gli utenti di dominio sincronizzati dispongano delle licenze per Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a4e90-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a4e90-112">Per la procedura, vedere [sincronizzare gli utenti di dominio a Microsoft](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="a4e90-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="a4e90-113">1. verificare l'autorità MDM in Intune</span><span class="sxs-lookup"><span data-stu-id="a4e90-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="a4e90-114">Andare a portal.azure.com e nella parte superiore della pagina di ricerca di Intune.</span><span class="sxs-lookup"><span data-stu-id="a4e90-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="a4e90-115">Nella pagina Microsoft Intune selezionare **registrazione dispositivo** e nella pagina **Panoramica** verificare che l' **autorità MDM** sia **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="a4e90-116">Se l' **autorità MDM** è **None**, fare clic sull' **autorità MDM** per impostarla su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="a4e90-117">Se l' **autorità MDM** è **Microsoft Office 365**, passare **a dispositivi di**  >  **registrazione** e utilizzare la finestra di dialogo **Aggiungi autorità MDM** sulla destra per aggiungere l'autorità di **MDM** (la finestra di dialogo **Aggiungi autorità MDM** è disponibile solo se l' **autorità MDM** è impostata su Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="a4e90-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="a4e90-118">2. Verificare che Azure AD sia abilitato per l'aggiunta di computer</span><span class="sxs-lookup"><span data-stu-id="a4e90-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="a4e90-119">Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare **Azure Active Directory** (selezionare Mostra tutto se Azure Active Directory non è visibile) nell'elenco **admin** Centers.</span><span class="sxs-lookup"><span data-stu-id="a4e90-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="a4e90-120">Nell'interfaccia di **amministrazione di Azure Active Directory**passare a **Azure Active Directory** , scegliere **dispositivi** e quindi **Impostazioni dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="a4e90-121">Verificare**che gli utenti possano aggiungere dispositivi ad Azure ad** sia abilitato</span><span class="sxs-lookup"><span data-stu-id="a4e90-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="a4e90-122">Per abilitare tutti gli utenti, impostare su **tutti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="a4e90-123">Per abilitare utenti specifici, impostare su **selezionato** per abilitare un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="a4e90-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="a4e90-124">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a4e90-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="a4e90-125">Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a4e90-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="a4e90-126">3. Verificare che Azure AD sia abilitato per MDM</span><span class="sxs-lookup"><span data-stu-id="a4e90-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="a4e90-127">Andare all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare Seleziona gli amministratori di **endpoint**t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)</span><span class="sxs-lookup"><span data-stu-id="a4e90-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="a4e90-128">Nell'interfaccia di **amministrazione di Microsoft Endpoint Manager**passare alla **Devices**  >  **Windows**  >  **Windows Enrollment**  >  **registrazione automatica**dei dispositivi Windows Windows.</span><span class="sxs-lookup"><span data-stu-id="a4e90-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="a4e90-129">Verificare che l'ambito dell'utente MDM sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="a4e90-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="a4e90-130">Per registrare tutti i computer, impostare su **tutti** per la registrazione automatica di tutti i computer degli utenti aggiunti a Azure ad e nuovi computer quando gli utenti aggiungono un account di lavoro a Windows.</span><span class="sxs-lookup"><span data-stu-id="a4e90-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="a4e90-131">Impostato su **alcuni** per registrare i computer di un gruppo specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="a4e90-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="a4e90-132">Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a4e90-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="a4e90-133">Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a4e90-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="a4e90-134">4. configurare il punto di connessione del servizio (SCP)</span><span class="sxs-lookup"><span data-stu-id="a4e90-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="a4e90-135">Questi passaggi sono semplificati da [Configure Hybrid Azure ad join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="a4e90-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="a4e90-136">Per completare la procedura, è necessario utilizzare Azure AD Connect e l'amministratore globale di Microsoft 365 Business Premium e le password di amministratore di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4e90-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="a4e90-137">Avviare Azure AD Connect e quindi selezionare **Configure**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="a4e90-138">Nella pagina **attività aggiuntive** selezionare **Configura opzioni dispositivo**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="a4e90-139">Nella pagina **Panoramica** selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="a4e90-140">Nella pagina **connessione ad Azure ad** , immettere le credenziali di un amministratore globale per Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a4e90-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="a4e90-141">Nella pagina **Opzioni dispositivo** , selezionare **Configura ibrido di Azure ad join**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="a4e90-142">Nella pagina **SCP** , per ogni foresta in cui si desidera connettersi ad Azure ad Connect per configurare l'SCP, completare i passaggi seguenti e quindi selezionare **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="a4e90-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="a4e90-143">Selezionare la casella accanto al nome della foresta.</span><span class="sxs-lookup"><span data-stu-id="a4e90-143">Check the box beside the forest name.</span></span> <span data-ttu-id="a4e90-144">La foresta dovrebbe essere il nome di dominio dell'annuncio.</span><span class="sxs-lookup"><span data-stu-id="a4e90-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="a4e90-145">Nella colonna **servizio di autenticazione** aprire l'elenco a discesa e selezionare nome di dominio corrispondente (è disponibile solo un'opzione solo).</span><span class="sxs-lookup"><span data-stu-id="a4e90-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="a4e90-146">Selezionare **Aggiungi** per immettere le credenziali di amministratore del dominio.</span><span class="sxs-lookup"><span data-stu-id="a4e90-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="a4e90-147">Nella pagina **sistemi operativi del dispositivo** selezionare solo i dispositivi collegati al dominio di Windows 10 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a4e90-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="a4e90-148">Nella pagina **pronto per la configurazione** , selezionare **Configure**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="a4e90-149">Nella pagina **Configurazione completata** selezionare **Esci**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="a4e90-150">5. creare un oggetto Criteri di gruppo per la registrazione di Intune-ADMX, metodo</span><span class="sxs-lookup"><span data-stu-id="a4e90-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="a4e90-151">Utilizzare. File modello ADMX.</span><span class="sxs-lookup"><span data-stu-id="a4e90-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="a4e90-152">Accedere a **Server Manager**  >  **Tools**  >  **Gestione criteri di gruppo**di Active Directory Server, ricerca e Apri Server Manager.</span><span class="sxs-lookup"><span data-stu-id="a4e90-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="a4e90-153">Selezionare il nome di dominio in **domini** e fare clic con il pulsante destro del mouse su **oggetti Criteri di gruppo** per selezionare **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="a4e90-154">Assegnare un nome al nuovo oggetto Criteri di gruppo, ad esempio "*Cloud_Enrollment*", quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="a4e90-155">Fare clic con il pulsante destro del mouse sul nuovo GPO in **oggetti Criteri di gruppo** e scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="a4e90-156">In **Editor gestione criteri di gruppo**, passare a criteri di **configurazione del computer**  >  **Policies**  >  **modelli amministrativi**dei  >  **componenti di Windows**  >  **MDM**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="a4e90-157">Fare clic con il pulsante destro del mouse su **Consenti registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite** e quindi selezionare **attivato**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="a4e90-158">Chiudere la finestra dell'editor.</span><span class="sxs-lookup"><span data-stu-id="a4e90-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e90-159">Se il criterio non viene abilitato per **abilitare la registrazione automatica del MDM utilizzando le credenziali di Azure ad predefinite**, vedere [Get the ultimo modelli amministrativi](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="a4e90-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="a4e90-160">6. distribuire i criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="a4e90-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="a4e90-161">In Server Manager, in **domini** > oggetti Criteri di gruppo, selezionare il GPO dal passaggio 3 sopra, ad esempio "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="a4e90-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="a4e90-162">Selezionare la scheda **ambito** per l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a4e90-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="a4e90-163">Nella scheda ambito dell'oggetto Criteri di gruppo fare clic con il pulsante destro del mouse sul collegamento al dominio in **collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="a4e90-164">Selezionare **enforced** per distribuire l'oggetto Criteri di gruppo e quindi fare clic su **OK** nella schermata di conferma.</span><span class="sxs-lookup"><span data-stu-id="a4e90-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="a4e90-165">Ottenere i modelli amministrativi più recenti</span><span class="sxs-lookup"><span data-stu-id="a4e90-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="a4e90-166">Se il criterio non viene visualizzato, **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite**, potrebbe essere perché non è installato ADMX per Windows 10, versione 1803, versione 1809 o versione 1903.</span><span class="sxs-lookup"><span data-stu-id="a4e90-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="a4e90-167">Per risolvere il problema, attenersi alla seguente procedura (Nota: l'ultima MDM. admx è compatibile con le versioni precedenti):</span><span class="sxs-lookup"><span data-stu-id="a4e90-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="a4e90-168">Download: [modelli amministrativi (con estensione ADMX) per l'aggiornamento a Windows 10 maggio 2019 (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="a4e90-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="a4e90-169">Installare il pacchetto nel controller di dominio primario (PDC).</span><span class="sxs-lookup"><span data-stu-id="a4e90-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="a4e90-170">Spostarsi, a seconda della versione della cartella: **c:\Programmi (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="a4e90-171">Rinominare la cartella delle **definizioni dei criteri** nel percorso precedente in **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="a4e90-172">Copiare la cartella **PolicyDefinitions** in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="a4e90-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="a4e90-173">Se si prevede di utilizzare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="a4e90-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="a4e90-174">Riavviare il controller di dominio principale affinché i criteri siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="a4e90-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="a4e90-175">Questa procedura funzionerà anche per qualsiasi versione futura.</span><span class="sxs-lookup"><span data-stu-id="a4e90-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="a4e90-176">A questo punto, è possibile visualizzare i criteri per **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad** disponibili.</span><span class="sxs-lookup"><span data-stu-id="a4e90-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

