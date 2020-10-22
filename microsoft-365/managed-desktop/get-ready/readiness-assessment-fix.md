---
title: Risolvere i problemi rilevati dallo strumento di valutazione della conformità
description: Azioni dettagliate da intraprendere per ogni problema rilevato dallo strumento
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656140"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="f16cb-104">Risolvere i problemi rilevati dallo strumento di valutazione della conformità</span><span class="sxs-lookup"><span data-stu-id="f16cb-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="f16cb-105">Per ogni controllo, lo strumento riporterà uno dei tre possibili risultati:</span><span class="sxs-lookup"><span data-stu-id="f16cb-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="f16cb-106">Risultato</span><span class="sxs-lookup"><span data-stu-id="f16cb-106">Result</span></span>  |<span data-ttu-id="f16cb-107">Significato</span><span class="sxs-lookup"><span data-stu-id="f16cb-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="f16cb-108">Pronto</span><span class="sxs-lookup"><span data-stu-id="f16cb-108">Ready</span></span>     | <span data-ttu-id="f16cb-109">Non è necessario eseguire alcuna operazione prima di completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="f16cb-110">Consulenza</span><span class="sxs-lookup"><span data-stu-id="f16cb-110">Advisory</span></span>    | <span data-ttu-id="f16cb-111">Seguire la procedura descritta nello strumento o in questo articolo per la migliore esperienza di registrazione e per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="f16cb-112">È *possibile* completare la registrazione, ma è necessario correggere questi problemi prima di distribuire il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f16cb-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="f16cb-113">Non pronto</span><span class="sxs-lookup"><span data-stu-id="f16cb-113">Not ready</span></span> | <span data-ttu-id="f16cb-114">*La registrazione avrà esito negativo se non si correggeranno questi problemi.*</span><span class="sxs-lookup"><span data-stu-id="f16cb-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="f16cb-115">Seguire la procedura descritta nello strumento o in questo articolo per risolverli.</span><span class="sxs-lookup"><span data-stu-id="f16cb-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="f16cb-116">Impostazioni di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f16cb-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="f16cb-117">Profilo di distribuzione Autopilot</span><span class="sxs-lookup"><span data-stu-id="f16cb-117">Autopilot deployment profile</span></span>

<span data-ttu-id="f16cb-118">Non è necessario disporre di profili Autopilot esistenti per i gruppi assegnati o dinamici utilizzati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-119">Microsoft Managed Desktop utilizza il pilota automatico per eseguire il provisioning di nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f16cb-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="f16cb-120">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-120">**Not ready**</span></span>

<span data-ttu-id="f16cb-121">Si dispone di un profilo Autopilot assegnato a tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f16cb-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="f16cb-122">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="f16cb-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f16cb-123">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="f16cb-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="f16cb-124">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-124">**Advisory**</span></span>

<span data-ttu-id="f16cb-125">Assicurarsi che i profili Autopilot siano destinati a un gruppo di Azure AD assegnato o dinamico che non includa i dispositivi desktop Microsoft gestiti che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="f16cb-126">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="f16cb-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f16cb-127">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="f16cb-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="f16cb-128">Connettori per i certificati</span><span class="sxs-lookup"><span data-stu-id="f16cb-128">Certificate connectors</span></span>

<span data-ttu-id="f16cb-129">Se si dispone di qualsiasi connettore di certificato utilizzato dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non possono avere errori.</span><span class="sxs-lookup"><span data-stu-id="f16cb-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="f16cb-130">Solo uno dei seguenti consulenti si applicherà alla situazione, quindi controllali con attenzione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="f16cb-131">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-131">**Advisory**</span></span>

<span data-ttu-id="f16cb-132">Non sono presenti connettori di certificato.</span><span class="sxs-lookup"><span data-stu-id="f16cb-132">No certificate connectors are present.</span></span> <span data-ttu-id="f16cb-133">È possibile che non siano necessari connettori, ma è necessario valutare se potrebbe essere necessario un po' di connettività di rete per i dispositivi desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-134">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="f16cb-135">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-135">**Advisory**</span></span>

<span data-ttu-id="f16cb-136">Almeno un connettore di certificato ha un errore.</span><span class="sxs-lookup"><span data-stu-id="f16cb-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="f16cb-137">Se è necessario questo connettore per la connettività ai dispositivi Microsoft Managed Desktop, è necessario risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="f16cb-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="f16cb-138">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="f16cb-139">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-139">**Advisory**</span></span>

<span data-ttu-id="f16cb-140">Si dispone di almeno un connettore di certificato e non vengono segnalati errori.</span><span class="sxs-lookup"><span data-stu-id="f16cb-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="f16cb-141">Tuttavia, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-142">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="f16cb-143">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="f16cb-143">Conditional access policies</span></span>

<span data-ttu-id="f16cb-144">I criteri di accesso condizionale nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="f16cb-145">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-145">**Not ready**</span></span>

<span data-ttu-id="f16cb-146">Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="f16cb-147">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa il gruppo di Azure AD degli account di servizio di Microsoft Managed Desktop che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="f16cb-148">Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="f16cb-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="f16cb-149">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-149">**Advisory**</span></span>

<span data-ttu-id="f16cb-150">Verificare che tutti i criteri di accesso condizionale siano esclusi dal gruppo di Azure AD degli **account di servizio sul posto di lavoro moderno** .</span><span class="sxs-lookup"><span data-stu-id="f16cb-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="f16cb-151">Per i passaggi, vedere [regolare l'accesso condizionale](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="f16cb-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="f16cb-152">Il gruppo di Azure AD dei **servizi di ambiente di lavoro moderno** è un gruppo dinamico creato per il servizio quando si esegue la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="f16cb-153">Sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="f16cb-154">Per ulteriori informazioni su questi account di servizio, vedere [standard operative Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="f16cb-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="f16cb-155">Criteri di conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f16cb-155">Device Compliance policies</span></span>

<span data-ttu-id="f16cb-156">I criteri di conformità dei dispositivi di Intune nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="f16cb-157">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-157">**Not ready**</span></span>

<span data-ttu-id="f16cb-158">Si dispone di almeno un criterio di conformità che è destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="f16cb-159">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f16cb-160">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="f16cb-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="f16cb-161">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-161">**Advisory**</span></span>

<span data-ttu-id="f16cb-162">Verificare che i criteri di conformità non includano gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f16cb-163">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="f16cb-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="f16cb-164">Criteri di configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f16cb-164">Device Configuration policies</span></span>

<span data-ttu-id="f16cb-165">I criteri di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere destinati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="f16cb-166">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-166">**Not ready**</span></span>

<span data-ttu-id="f16cb-167">Si dispone di almeno un criterio di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="f16cb-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="f16cb-168">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="f16cb-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-169">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="f16cb-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="f16cb-170">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-170">**Advisory**</span></span>

<span data-ttu-id="f16cb-171">Verificare che i criteri di conformità non includano dispositivi o utenti desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="f16cb-172">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="f16cb-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="f16cb-173">Restrizioni per il tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="f16cb-173">Device type restrictions</span></span>

<span data-ttu-id="f16cb-174">I dispositivi Microsoft Managed Desktop devono essere autorizzati a eseguire la registrazione in Intune.</span><span class="sxs-lookup"><span data-stu-id="f16cb-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="f16cb-175">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-175">**Not ready**</span></span>

<span data-ttu-id="f16cb-176">Seguire la procedura descritta in [set Restriction](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) **consentitions**to change the setting to allow.</span><span class="sxs-lookup"><span data-stu-id="f16cb-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="f16cb-177">Pagina stato registrazione</span><span class="sxs-lookup"><span data-stu-id="f16cb-177">Enrollment Status Page</span></span>

<span data-ttu-id="f16cb-178">La pagina stato di registrazione (ESP) è attualmente abilitata.</span><span class="sxs-lookup"><span data-stu-id="f16cb-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="f16cb-179">Se si partecipa all'anteprima pubblica di questa funzionalità, è possibile ignorare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="f16cb-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="f16cb-180">Per ulteriori informazioni, vedere [First-Run experience with Autopilot e la pagina status di registrazione](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="f16cb-181">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-181">**Not ready**</span></span>

<span data-ttu-id="f16cb-182">Si dispone del set di profili ESP predefinito per **visualizzare lo stato di avanzamento della configurazione dei profili e delle app**.</span><span class="sxs-lookup"><span data-stu-id="f16cb-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="f16cb-183">Disabilitare questa impostazione attenendosi alla procedura descritta in [impostare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="f16cb-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="f16cb-184">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-184">**Advisory**</span></span>

<span data-ttu-id="f16cb-185">Verificare che i profili con l'impostazione **Mostra avanzamento configurazione app e profilo** non siano assegnati a nessun gruppo di Azure ad che includa i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-186">Per ulteriori informazioni, vedere [configurare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="f16cb-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="f16cb-187">Registrazione di Intune</span><span class="sxs-lookup"><span data-stu-id="f16cb-187">Intune enrollment</span></span>

<span data-ttu-id="f16cb-188">I dispositivi Windows 10 nell'organizzazione di Azure AD devono essere registrati automaticamente in Intune.</span><span class="sxs-lookup"><span data-stu-id="f16cb-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="f16cb-189">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-189">**Not ready**</span></span>

<span data-ttu-id="f16cb-190">Gli utenti dell'organizzazione di Azure AD non vengono automaticamente registrati in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="f16cb-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="f16cb-191">Impostare l'ambito dell'utente MDM su **alcuni** o su **tutti**.</span><span class="sxs-lookup"><span data-stu-id="f16cb-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="f16cb-192">Se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="f16cb-192">If you choose.</span></span> <span data-ttu-id="f16cb-193">Alcuni \* \*, ritornati dopo la registrazione e seleziona la pagina di **lavoro moderna-tutto** il gruppo di Azure ad per i **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f16cb-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="f16cb-194">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="f16cb-194">Microsoft Store for Business</span></span>

<span data-ttu-id="f16cb-195">Microsoft Store for business viene utilizzato in modo da poter scaricare il portale aziendale per distribuire alcune app, ad esempio Microsoft Project e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="f16cb-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="f16cb-196">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-196">**Not ready**</span></span>

<span data-ttu-id="f16cb-197">Microsoft Store for business non è abilitato o non è sincronizzato con Intune.</span><span class="sxs-lookup"><span data-stu-id="f16cb-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="f16cb-198">Per ulteriori informazioni, vedere [How to Manage volume purchased Apps from the Microsoft Store for business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="f16cb-199">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f16cb-199">Multi-factor authentication</span></span>

<span data-ttu-id="f16cb-200">Per l'autenticazione a più fattori non è necessario applicare accidentalmente gli account di servizio di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="f16cb-201">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-201">**Not ready**</span></span>

<span data-ttu-id="f16cb-202">Si dispone di alcuni criteri di autenticazione a più fattori (AMF) impostati come "necessari" per i criteri di accesso condizionale assegnati a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="f16cb-203">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="f16cb-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-204">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="f16cb-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="f16cb-205">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-205">**Advisory**</span></span>

<span data-ttu-id="f16cb-206">Verificare che tutti i criteri di accesso condizionale che richiedono l'AMF escludano la **moderna area di lavoro-tutti i** gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="f16cb-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="f16cb-207">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="f16cb-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="f16cb-208">La **moderna area di lavoro-tutti i** gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="f16cb-209">Script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f16cb-209">PowerShell scripts</span></span>

<span data-ttu-id="f16cb-210">Gli script di Windows PowerShell non possono essere assegnati in modo da indirizzare i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="f16cb-211">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-211">**Advisory**</span></span>

<span data-ttu-id="f16cb-212">Assicurarsi che gli script di Windows PowerShell nell'organizzazione Azure AD non vengano indirizzati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="f16cb-213">Per ulteriori informazioni, vedere [utilizzare gli script di PowerShell nei dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="f16cb-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="f16cb-214">Area geografica</span><span class="sxs-lookup"><span data-stu-id="f16cb-214">Region</span></span>

<span data-ttu-id="f16cb-215">La propria area geografica deve essere supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f16cb-216">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-216">**Not ready**</span></span>

<span data-ttu-id="f16cb-217">L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-218">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="f16cb-219">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-219">**Advisory**</span></span>

<span data-ttu-id="f16cb-220">Uno o più dei paesi in cui si trova l'organizzazione Azure AD non è supportato da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-221">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="f16cb-222">Linee di base per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-222">Security baselines</span></span>

<span data-ttu-id="f16cb-223">I criteri di base di sicurezza non devono essere destinati ai dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f16cb-224">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-224">**Not ready**</span></span>

<span data-ttu-id="f16cb-225">Si dispone di un profilo di base di sicurezza che è destinato a tutti gli utenti, tutti i dispositivi o entrambi.</span><span class="sxs-lookup"><span data-stu-id="f16cb-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="f16cb-226">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="f16cb-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-227">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="f16cb-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="f16cb-228">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-228">**Advisory**</span></span>

<span data-ttu-id="f16cb-229">Assicurarsi che tutti i criteri di base di sicurezza che è possibile escludere i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-230">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="f16cb-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="f16cb-231">I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="f16cb-232">App di Windows</span><span class="sxs-lookup"><span data-stu-id="f16cb-232">Windows apps</span></span>

<span data-ttu-id="f16cb-233">Esaminare le app desiderate dagli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="f16cb-234">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-234">**Advisory**</span></span>

<span data-ttu-id="f16cb-235">È consigliabile preparare un inventario delle app che si desidera vengano convogliate dagli utenti di Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="f16cb-236">Verificare che le app possano essere distribuite da Intune.</span><span class="sxs-lookup"><span data-stu-id="f16cb-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="f16cb-237">Per ulteriori informazioni, vedere [app in Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="f16cb-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="f16cb-238">È possibile richiedere al rappresentante dell'account Microsoft una query in Microsoft endpoint Configuration Manager per identificare le applicazioni che sono pronte per la migrazione a Intune o che devono essere rettificate.</span><span class="sxs-lookup"><span data-stu-id="f16cb-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="f16cb-239">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="f16cb-239">Windows Hello for Business</span></span>

<span data-ttu-id="f16cb-240">Microsoft Managed Desktop richiede l'abilitazione di Windows Hello for business.</span><span class="sxs-lookup"><span data-stu-id="f16cb-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="f16cb-241">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-241">**Not ready**</span></span>

<span data-ttu-id="f16cb-242">Windows Hello for business è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f16cb-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="f16cb-243">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="f16cb-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="f16cb-244">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-244">**Advisory**</span></span>

<span data-ttu-id="f16cb-245">Windows Hello for business non è configurato.</span><span class="sxs-lookup"><span data-stu-id="f16cb-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="f16cb-246">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="f16cb-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="f16cb-247">Anelli di aggiornamento di Windows 10</span><span class="sxs-lookup"><span data-stu-id="f16cb-247">Windows 10 update rings</span></span>

<span data-ttu-id="f16cb-248">Il criterio "Windows 10 Update Ring" in Intune non deve essere indirizzato a qualsiasi dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f16cb-249">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-249">**Not ready**</span></span>

<span data-ttu-id="f16cb-250">Si dispone di un criterio "anello di aggiornamento" che consente di indirizzare tutti i dispositivi, tutti gli utenti o entrambi.</span><span class="sxs-lookup"><span data-stu-id="f16cb-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="f16cb-251">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="f16cb-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f16cb-252">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="f16cb-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="f16cb-253">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-253">**Advisory**</span></span>

<span data-ttu-id="f16cb-254">Assicurarsi che tutti i criteri anello di aggiornamento che è possibile escludere il **luogo di lavoro moderno-tutti i gruppi di** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="f16cb-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="f16cb-255">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="f16cb-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="f16cb-256">I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="f16cb-257">Impostazioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f16cb-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="f16cb-258">Abbonamenti ad hoc</span><span class="sxs-lookup"><span data-stu-id="f16cb-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="f16cb-259">Si consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento del roaming dello stato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="f16cb-260">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-260">**Advisory**</span></span>

<span data-ttu-id="f16cb-261">Verificare che **AllowAdHocSubscriptions** sia impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="f16cb-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="f16cb-262">In caso contrario, il roaming dello stato dell'organizzazione potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="f16cb-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="f16cb-263">Per ulteriori informazioni, vedere [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="f16cb-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="f16cb-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="f16cb-264">Enterprise State Roaming</span></span>

<span data-ttu-id="f16cb-265">Il roaming dello stato dell'organizzazione deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="f16cb-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="f16cb-266">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-266">**Advisory**</span></span>

<span data-ttu-id="f16cb-267">Verificare che il roaming dello stato dell'organizzazione sia abilitato per tutti o per **i** gruppi **selezionati** .</span><span class="sxs-lookup"><span data-stu-id="f16cb-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="f16cb-268">Per ulteriori informazioni, vedere [Enable Enterprise state roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="f16cb-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="f16cb-269">Licenze</span><span class="sxs-lookup"><span data-stu-id="f16cb-269">Licenses</span></span>

<span data-ttu-id="f16cb-270">Per utilizzare Microsoft Managed Desktop è necessario disporre di un numero di licenze.</span><span class="sxs-lookup"><span data-stu-id="f16cb-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f16cb-271">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-271">**Not Ready**</span></span>

<span data-ttu-id="f16cb-272">Non si dispone di tutte le licenze necessarie per l'utilizzo di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-273">Per ulteriori informazioni, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md) e [altro sulle licenze](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="f16cb-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="f16cb-274">Nomi degli account di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-274">Security account names</span></span>

<span data-ttu-id="f16cb-275">Alcuni nomi degli account di sicurezza potrebbero essere in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f16cb-276">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-276">**Not ready**</span></span>

<span data-ttu-id="f16cb-277">Si dispone di almeno un nome di account che sarà in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-278">Collaborare con il rappresentante dell'account Microsoft per escludere i nomi degli account.</span><span class="sxs-lookup"><span data-stu-id="f16cb-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="f16cb-279">Ruoli di amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-279">Security administrator roles</span></span>

<span data-ttu-id="f16cb-280">Gli utenti con determinati ruoli di sicurezza devono avere quelli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f16cb-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="f16cb-281">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-281">**Advisory**</span></span>

<span data-ttu-id="f16cb-282">Se si dispone di uno di questi ruoli assegnati nell'organizzazione di Azure AD, assicurarsi che dispongano anche di questi ruoli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f16cb-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f16cb-283">In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="f16cb-284">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-284">Security Reader</span></span>
- <span data-ttu-id="f16cb-285">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-285">Security Operator</span></span>
- <span data-ttu-id="f16cb-286">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="f16cb-286">Global Reader</span></span>

<span data-ttu-id="f16cb-287">Per ulteriori informazioni, vedere [creare e gestire i ruoli per il controllo di accesso basato sui ruoli](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="f16cb-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="f16cb-288">Impostazione predefinita per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f16cb-288">Security default</span></span>

<span data-ttu-id="f16cb-289">Le impostazioni predefinite per la sicurezza in Azure Active Directory impediscono la gestione dei dispositivi da parte di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="f16cb-290">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-290">**Not ready**</span></span>

<span data-ttu-id="f16cb-291">Sono state attivate le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f16cb-291">You have Security defaults turned on.</span></span> <span data-ttu-id="f16cb-292">Disattivare le impostazioni predefinite per la sicurezza e configurare i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="f16cb-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="f16cb-293">Per ulteriori informazioni, vedere [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="f16cb-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="f16cb-294">Reimpostazione della password in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="f16cb-294">Self-service Password Reset</span></span>

<span data-ttu-id="f16cb-295">È necessario abilitare la reimpostazione della password in modalità self-service (SSPR).</span><span class="sxs-lookup"><span data-stu-id="f16cb-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="f16cb-296">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="f16cb-296">**Not ready**</span></span>

<span data-ttu-id="f16cb-297">SSPR deve essere abilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16cb-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="f16cb-298">In caso contrario, gli account di servizio di Microsoft Managed Desktop non possono funzionare.</span><span class="sxs-lookup"><span data-stu-id="f16cb-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="f16cb-299">Per ulteriori informazioni, vedere [esercitazione: consentire agli utenti di sbloccare l'account o reimpostare le password tramite la reimpostazione della password self-service di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="f16cb-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="f16cb-300">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-300">**Advisory**</span></span>

<span data-ttu-id="f16cb-301">Verificare che l'impostazione SSPR **Selected** includa dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="f16cb-302">Ruolo utente standard</span><span class="sxs-lookup"><span data-stu-id="f16cb-302">Standard user role</span></span>

<span data-ttu-id="f16cb-303">Gli utenti di Microsoft Managed Desktop devono essere utenti standard senza privilegi di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="f16cb-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="f16cb-304">Al momento dell'avvio del dispositivo Microsoft Managed Desktop verrà assegnato un ruolo utente standard.</span><span class="sxs-lookup"><span data-stu-id="f16cb-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="f16cb-305">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-305">**Advisory**</span></span>

<span data-ttu-id="f16cb-306">Gli utenti di Microsoft Managed Desktop non devono avere privilegi di amministratore locale prima di effettuare l'iscrizione.</span><span class="sxs-lookup"><span data-stu-id="f16cb-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f16cb-307">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="f16cb-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="f16cb-308">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f16cb-308">OneDrive for Business</span></span>

<span data-ttu-id="f16cb-309">L'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** sarà in conflitto con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f16cb-310">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="f16cb-310">**Advisory**</span></span>

<span data-ttu-id="f16cb-311">Si sta utilizzando l'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** .</span><span class="sxs-lookup"><span data-stu-id="f16cb-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="f16cb-312">Questa impostazione non funzionerà con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f16cb-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f16cb-313">Disabilitare questa impostazione e configurare OneDrive for business per l'utilizzo di un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="f16cb-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="f16cb-314">Per informazioni, vedere [pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="f16cb-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

