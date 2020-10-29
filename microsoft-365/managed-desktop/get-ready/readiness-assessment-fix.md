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
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795118"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="d1fb3-104">Risolvere i problemi rilevati dallo strumento di valutazione della conformità</span><span class="sxs-lookup"><span data-stu-id="d1fb3-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="d1fb3-105">Per ogni controllo, lo strumento riporterà uno dei quattro possibili risultati:</span><span class="sxs-lookup"><span data-stu-id="d1fb3-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="d1fb3-106">Risultato</span><span class="sxs-lookup"><span data-stu-id="d1fb3-106">Result</span></span>  |<span data-ttu-id="d1fb3-107">Significato</span><span class="sxs-lookup"><span data-stu-id="d1fb3-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="d1fb3-108">Pronto</span><span class="sxs-lookup"><span data-stu-id="d1fb3-108">Ready</span></span>     | <span data-ttu-id="d1fb3-109">Non è necessario eseguire alcuna operazione prima di completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="d1fb3-110">Consulenza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-110">Advisory</span></span>    | <span data-ttu-id="d1fb3-111">Seguire la procedura descritta nello strumento o in questo articolo per la migliore esperienza di registrazione e per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="d1fb3-112">È *possibile* completare la registrazione, ma è necessario correggere questi problemi prima di distribuire il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="d1fb3-113">Non pronto</span><span class="sxs-lookup"><span data-stu-id="d1fb3-113">Not ready</span></span> | <span data-ttu-id="d1fb3-114">*La registrazione avrà esito negativo se non si correggeranno questi problemi.*</span><span class="sxs-lookup"><span data-stu-id="d1fb3-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="d1fb3-115">Seguire la procedura descritta nello strumento o in questo articolo per risolverli.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="d1fb3-116">Error</span><span class="sxs-lookup"><span data-stu-id="d1fb3-116">Error</span></span> | <span data-ttu-id="d1fb3-117">Il ruolo di Azure Active Director (AD) utilizzato non dispone di autorizzazioni sufficienti per eseguire questo controllo.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="d1fb3-118">Impostazioni di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d1fb3-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="d1fb3-119">Profilo di distribuzione Autopilot</span><span class="sxs-lookup"><span data-stu-id="d1fb3-119">Autopilot deployment profile</span></span>

<span data-ttu-id="d1fb3-120">Non è necessario disporre di profili Autopilot esistenti per i gruppi assegnati o dinamici utilizzati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-121">Microsoft Managed Desktop utilizza il pilota automatico per eseguire il provisioning di nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="d1fb3-122">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-122">**Not ready**</span></span>

<span data-ttu-id="d1fb3-123">Si dispone di un profilo Autopilot assegnato a tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="d1fb3-124">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="d1fb3-125">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="d1fb3-126">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-126">**Advisory**</span></span>

<span data-ttu-id="d1fb3-127">Assicurarsi che i profili Autopilot siano destinati a un gruppo di Azure AD assegnato o dinamico che non includa i dispositivi desktop Microsoft gestiti che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="d1fb3-128">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="d1fb3-129">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="d1fb3-130">Connettori per i certificati</span><span class="sxs-lookup"><span data-stu-id="d1fb3-130">Certificate connectors</span></span>

<span data-ttu-id="d1fb3-131">Se si dispone di qualsiasi connettore di certificato utilizzato dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non possono avere errori.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="d1fb3-132">Solo uno dei seguenti consulenti si applicherà alla situazione, quindi controllali con attenzione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="d1fb3-133">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-133">**Advisory**</span></span>

<span data-ttu-id="d1fb3-134">Non sono presenti connettori di certificato.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-134">No certificate connectors are present.</span></span> <span data-ttu-id="d1fb3-135">È possibile che non siano necessari connettori, ma è necessario valutare se potrebbe essere necessario un po' di connettività di rete per i dispositivi desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-136">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="d1fb3-137">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-137">**Advisory**</span></span>

<span data-ttu-id="d1fb3-138">Almeno un connettore di certificato ha un errore.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="d1fb3-139">Se è necessario questo connettore per la connettività ai dispositivi Microsoft Managed Desktop, è necessario risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="d1fb3-140">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="d1fb3-141">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-141">**Advisory**</span></span>

<span data-ttu-id="d1fb3-142">Si dispone di almeno un connettore di certificato e non vengono segnalati errori.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="d1fb3-143">Tuttavia, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-144">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="d1fb3-145">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d1fb3-145">Conditional access policies</span></span>

<span data-ttu-id="d1fb3-146">I criteri di accesso condizionale nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="d1fb3-147">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-147">**Not ready**</span></span>

<span data-ttu-id="d1fb3-148">Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="d1fb3-149">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa il gruppo di Azure AD degli account di servizio di Microsoft Managed Desktop che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="d1fb3-150">Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="d1fb3-151">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-151">**Advisory**</span></span>

<span data-ttu-id="d1fb3-152">Verificare che tutti i criteri di accesso condizionale siano esclusi dal gruppo di Azure AD degli **account di servizio sul posto di lavoro moderno** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="d1fb3-153">Per i passaggi, vedere [regolare l'accesso condizionale](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="d1fb3-154">Il gruppo di Azure AD dei **servizi di ambiente di lavoro moderno** è un gruppo dinamico creato per il servizio quando si esegue la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="d1fb3-155">Sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="d1fb3-156">Per ulteriori informazioni su questi account di servizio, vedere [standard operative Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="d1fb3-157">**Errore**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-157">**Error**</span></span>

<span data-ttu-id="d1fb3-158">Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="d1fb3-159">Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:</span><span class="sxs-lookup"><span data-stu-id="d1fb3-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="d1fb3-160">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-160">Security Reader</span></span>
- <span data-ttu-id="d1fb3-161">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-161">Security Administrator</span></span>
- <span data-ttu-id="d1fb3-162">Amministratore dell'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d1fb3-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="d1fb3-163">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d1fb3-163">Global Reader</span></span>
- <span data-ttu-id="d1fb3-164">Amministratore di dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1fb3-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="d1fb3-165">Criteri di conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d1fb3-165">Device Compliance policies</span></span>

<span data-ttu-id="d1fb3-166">I criteri di conformità dei dispositivi di Intune nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="d1fb3-167">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-167">**Not ready**</span></span>

<span data-ttu-id="d1fb3-168">Si dispone di almeno un criterio di conformità che è destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="d1fb3-169">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d1fb3-170">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="d1fb3-171">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-171">**Advisory**</span></span>

<span data-ttu-id="d1fb3-172">Verificare che i criteri di conformità non includano gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d1fb3-173">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="d1fb3-174">Criteri di configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d1fb3-174">Device Configuration policies</span></span>

<span data-ttu-id="d1fb3-175">I criteri di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere destinati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="d1fb3-176">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-176">**Not ready**</span></span>

<span data-ttu-id="d1fb3-177">Si dispone di almeno un criterio di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="d1fb3-178">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-179">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="d1fb3-180">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-180">**Advisory**</span></span>

<span data-ttu-id="d1fb3-181">Verificare che i criteri di conformità non includano dispositivi o utenti desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="d1fb3-182">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="d1fb3-183">Restrizioni per il tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="d1fb3-183">Device type restrictions</span></span>

<span data-ttu-id="d1fb3-184">I dispositivi Microsoft Managed Desktop devono essere autorizzati a eseguire la registrazione in Intune.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="d1fb3-185">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-185">**Not ready**</span></span>

<span data-ttu-id="d1fb3-186">Seguire la procedura descritta in [set Restriction](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) **consentitions** to change the setting to allow.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="d1fb3-187">Pagina stato registrazione</span><span class="sxs-lookup"><span data-stu-id="d1fb3-187">Enrollment Status Page</span></span>

<span data-ttu-id="d1fb3-188">La pagina stato di registrazione (ESP) è attualmente abilitata.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="d1fb3-189">Se si partecipa all'anteprima pubblica di questa funzionalità, è possibile ignorare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="d1fb3-190">Per ulteriori informazioni, vedere [First-Run experience with Autopilot e la pagina status di registrazione](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="d1fb3-191">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-191">**Not ready**</span></span>

<span data-ttu-id="d1fb3-192">Si dispone del set di profili ESP predefinito per **visualizzare lo stato di avanzamento della configurazione dei profili e delle app** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="d1fb3-193">Disabilitare questa impostazione attenendosi alla procedura descritta in [impostare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="d1fb3-194">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-194">**Advisory**</span></span>

<span data-ttu-id="d1fb3-195">Verificare che i profili con l'impostazione **Mostra avanzamento configurazione app e profilo** non siano assegnati a nessun gruppo di Azure ad che includa i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-196">Per ulteriori informazioni, vedere [configurare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="d1fb3-197">Registrazione di Intune</span><span class="sxs-lookup"><span data-stu-id="d1fb3-197">Intune enrollment</span></span>

<span data-ttu-id="d1fb3-198">I dispositivi Windows 10 nell'organizzazione di Azure AD devono essere registrati automaticamente in Intune.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="d1fb3-199">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-199">**Not ready**</span></span>

<span data-ttu-id="d1fb3-200">Gli utenti dell'organizzazione di Azure AD non vengono automaticamente registrati in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="d1fb3-201">Impostare l'ambito dell'utente MDM su **alcuni** o su **tutti** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="d1fb3-202">Se si sceglie **alcuni** , tornare dopo la registrazione e selezionare la **moderna area di lavoro-tutto** il gruppo di Azure ad per i **gruppi** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="d1fb3-203">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="d1fb3-203">Microsoft Store for Business</span></span>

<span data-ttu-id="d1fb3-204">Microsoft Store for business viene utilizzato in modo da poter scaricare il portale aziendale per distribuire alcune app, ad esempio Microsoft Project e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="d1fb3-205">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-205">**Not ready**</span></span>

<span data-ttu-id="d1fb3-206">Microsoft Store for business non è abilitato o non è sincronizzato con Intune.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="d1fb3-207">Per ulteriori informazioni, vedere [How to Manage volume purchased Apps from the Microsoft Store for business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="d1fb3-208">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="d1fb3-208">Multi-factor authentication</span></span>

<span data-ttu-id="d1fb3-209">Per l'autenticazione a più fattori non è necessario applicare accidentalmente gli account di servizio di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="d1fb3-210">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-210">**Not ready**</span></span>

<span data-ttu-id="d1fb3-211">Si dispone di alcuni criteri di autenticazione a più fattori (AMF) impostati come "necessari" per i criteri di accesso condizionale assegnati a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="d1fb3-212">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-213">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="d1fb3-214">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-214">**Advisory**</span></span>

<span data-ttu-id="d1fb3-215">Verificare che tutti i criteri di accesso condizionale che richiedono l'AMF escludano la **moderna area di lavoro-tutti i** gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="d1fb3-216">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="d1fb3-217">La **moderna area di lavoro-tutti i** gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="d1fb3-218">**Errore**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-218">**Error**</span></span>

<span data-ttu-id="d1fb3-219">Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="d1fb3-220">Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:</span><span class="sxs-lookup"><span data-stu-id="d1fb3-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="d1fb3-221">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-221">Security Reader</span></span>
- <span data-ttu-id="d1fb3-222">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-222">Security Administrator</span></span>
- <span data-ttu-id="d1fb3-223">Amministratore dell'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d1fb3-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="d1fb3-224">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d1fb3-224">Global Reader</span></span>
- <span data-ttu-id="d1fb3-225">Amministratore di dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1fb3-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="d1fb3-226">Script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1fb3-226">PowerShell scripts</span></span>

<span data-ttu-id="d1fb3-227">Gli script di Windows PowerShell non possono essere assegnati in modo da indirizzare i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="d1fb3-228">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-228">**Advisory**</span></span>

<span data-ttu-id="d1fb3-229">Assicurarsi che gli script di Windows PowerShell nell'organizzazione Azure AD non vengano indirizzati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="d1fb3-230">Per ulteriori informazioni, vedere [utilizzare gli script di PowerShell nei dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="d1fb3-231">Area geografica</span><span class="sxs-lookup"><span data-stu-id="d1fb3-231">Region</span></span>

<span data-ttu-id="d1fb3-232">La propria area geografica deve essere supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d1fb3-233">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-233">**Not ready**</span></span>

<span data-ttu-id="d1fb3-234">L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-235">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="d1fb3-236">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-236">**Advisory**</span></span>

<span data-ttu-id="d1fb3-237">Uno o più dei paesi in cui si trova l'organizzazione Azure AD non è supportato da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-238">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="d1fb3-239">Linee di base per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-239">Security baselines</span></span>

<span data-ttu-id="d1fb3-240">I criteri di base di sicurezza non devono essere destinati ai dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d1fb3-241">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-241">**Not ready**</span></span>

<span data-ttu-id="d1fb3-242">Si dispone di un profilo di base di sicurezza che è destinato a tutti gli utenti, tutti i dispositivi o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="d1fb3-243">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-244">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="d1fb3-245">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-245">**Advisory**</span></span>

<span data-ttu-id="d1fb3-246">Assicurarsi che tutti i criteri di base di sicurezza che è possibile escludere i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-247">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="d1fb3-248">I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="d1fb3-249">App di Windows</span><span class="sxs-lookup"><span data-stu-id="d1fb3-249">Windows apps</span></span>

<span data-ttu-id="d1fb3-250">Esaminare le app desiderate dagli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="d1fb3-251">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-251">**Advisory**</span></span>

<span data-ttu-id="d1fb3-252">È consigliabile preparare un inventario delle app che si desidera vengano convogliate dagli utenti di Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="d1fb3-253">Verificare che le app possano essere distribuite da Intune.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="d1fb3-254">Per ulteriori informazioni, vedere [app in Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="d1fb3-255">È possibile richiedere al rappresentante dell'account Microsoft una query in Microsoft endpoint Configuration Manager per identificare le applicazioni che sono pronte per la migrazione a Intune o che devono essere rettificate.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="d1fb3-256">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="d1fb3-256">Windows Hello for Business</span></span>

<span data-ttu-id="d1fb3-257">Microsoft Managed Desktop richiede l'abilitazione di Windows Hello for business.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="d1fb3-258">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-258">**Not ready**</span></span>

<span data-ttu-id="d1fb3-259">Windows Hello for business è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="d1fb3-260">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="d1fb3-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="d1fb3-261">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-261">**Advisory**</span></span>

<span data-ttu-id="d1fb3-262">Windows Hello for business non è configurato.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="d1fb3-263">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="d1fb3-264">Anelli di aggiornamento di Windows 10</span><span class="sxs-lookup"><span data-stu-id="d1fb3-264">Windows 10 update rings</span></span>

<span data-ttu-id="d1fb3-265">Il criterio "Windows 10 Update Ring" in Intune non deve essere indirizzato a qualsiasi dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d1fb3-266">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-266">**Not ready**</span></span>

<span data-ttu-id="d1fb3-267">Si dispone di un criterio "anello di aggiornamento" che consente di indirizzare tutti i dispositivi, tutti gli utenti o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="d1fb3-268">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d1fb3-269">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="d1fb3-270">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-270">**Advisory**</span></span>

<span data-ttu-id="d1fb3-271">Assicurarsi che tutti i criteri anello di aggiornamento che è possibile escludere il **luogo di lavoro moderno-tutti i gruppi di** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="d1fb3-272">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="d1fb3-273">I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="d1fb3-274">Impostazioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1fb3-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="d1fb3-275">Abbonamenti ad hoc</span><span class="sxs-lookup"><span data-stu-id="d1fb3-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="d1fb3-276">Si consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento del roaming dello stato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="d1fb3-277">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-277">**Advisory**</span></span>

<span data-ttu-id="d1fb3-278">Verificare che **AllowAdHocSubscriptions** sia impostato su **true** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="d1fb3-279">In caso contrario, il roaming dello stato dell'organizzazione potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="d1fb3-280">Per ulteriori informazioni, vedere [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="d1fb3-281">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="d1fb3-281">Enterprise State Roaming</span></span>

<span data-ttu-id="d1fb3-282">Il roaming dello stato dell'organizzazione deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="d1fb3-283">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-283">**Advisory**</span></span>

<span data-ttu-id="d1fb3-284">Verificare che il roaming dello stato dell'organizzazione sia abilitato per tutti o per **i** gruppi **selezionati** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="d1fb3-285">Per ulteriori informazioni, vedere [Enable Enterprise state roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="d1fb3-286">Licenze</span><span class="sxs-lookup"><span data-stu-id="d1fb3-286">Licenses</span></span>

<span data-ttu-id="d1fb3-287">Per utilizzare Microsoft Managed Desktop è necessario disporre di un numero di licenze.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d1fb3-288">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-288">**Not Ready**</span></span>

<span data-ttu-id="d1fb3-289">Non si dispone di tutte le licenze necessarie per l'utilizzo di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-290">Per ulteriori informazioni, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md) e [altro sulle licenze](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="d1fb3-291">Nomi degli account di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-291">Security account names</span></span>

<span data-ttu-id="d1fb3-292">Alcuni nomi degli account di sicurezza potrebbero essere in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d1fb3-293">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-293">**Not ready**</span></span>

<span data-ttu-id="d1fb3-294">Si dispone di almeno un nome di account che sarà in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-295">Collaborare con il rappresentante dell'account Microsoft per escludere i nomi degli account.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="d1fb3-296">Ruoli di amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-296">Security administrator roles</span></span>

<span data-ttu-id="d1fb3-297">Gli utenti con determinati ruoli di sicurezza devono avere quelli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d1fb3-298">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-298">**Advisory**</span></span>

<span data-ttu-id="d1fb3-299">Se si dispone di uno di questi ruoli assegnati nell'organizzazione di Azure AD, assicurarsi che dispongano anche di questi ruoli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d1fb3-300">In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="d1fb3-301">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-301">Security Reader</span></span>
- <span data-ttu-id="d1fb3-302">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-302">Security Operator</span></span>
- <span data-ttu-id="d1fb3-303">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d1fb3-303">Global Reader</span></span>

<span data-ttu-id="d1fb3-304">Per ulteriori informazioni, vedere [creare e gestire i ruoli per il controllo di accesso basato sui ruoli](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="d1fb3-305">Impostazione predefinita per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1fb3-305">Security default</span></span>

<span data-ttu-id="d1fb3-306">Le impostazioni predefinite per la sicurezza in Azure Active Directory impediscono la gestione dei dispositivi da parte di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="d1fb3-307">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-307">**Not ready**</span></span>

<span data-ttu-id="d1fb3-308">Sono state attivate le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-308">You have Security defaults turned on.</span></span> <span data-ttu-id="d1fb3-309">Disattivare le impostazioni predefinite per la sicurezza e configurare i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="d1fb3-310">Per ulteriori informazioni, vedere [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="d1fb3-311">Reimpostazione della password in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="d1fb3-311">Self-service Password Reset</span></span>

<span data-ttu-id="d1fb3-312">È necessario abilitare la reimpostazione della password in modalità self-service (SSPR).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="d1fb3-313">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-313">**Not ready**</span></span>

<span data-ttu-id="d1fb3-314">SSPR deve essere abilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="d1fb3-315">In caso contrario, gli account di servizio di Microsoft Managed Desktop non possono funzionare.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="d1fb3-316">Per ulteriori informazioni, vedere [esercitazione: consentire agli utenti di sbloccare l'account o reimpostare le password tramite la reimpostazione della password self-service di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="d1fb3-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="d1fb3-317">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-317">**Advisory**</span></span>

<span data-ttu-id="d1fb3-318">Verificare che l'impostazione SSPR **Selected** includa dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d1fb3-319">**Errore**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-319">**Error**</span></span>

<span data-ttu-id="d1fb3-320">Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="d1fb3-321">Per eseguire il controllo, è necessario anche il ruolo di Azure AD di Reader di report assegnato.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="d1fb3-322">Ruolo utente standard</span><span class="sxs-lookup"><span data-stu-id="d1fb3-322">Standard user role</span></span>

<span data-ttu-id="d1fb3-323">Gli utenti di Microsoft Managed Desktop devono essere utenti standard senza privilegi di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="d1fb3-324">Al momento dell'avvio del dispositivo Microsoft Managed Desktop verrà assegnato un ruolo utente standard.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="d1fb3-325">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-325">**Advisory**</span></span>

<span data-ttu-id="d1fb3-326">Gli utenti di Microsoft Managed Desktop non devono avere privilegi di amministratore locale prima di effettuare l'iscrizione.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d1fb3-327">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="d1fb3-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="d1fb3-328">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d1fb3-328">OneDrive for Business</span></span>

<span data-ttu-id="d1fb3-329">L'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** sarà in conflitto con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d1fb3-330">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="d1fb3-330">**Advisory**</span></span>

<span data-ttu-id="d1fb3-331">Si sta utilizzando l'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="d1fb3-332">Questa impostazione non funzionerà con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1fb3-333">Disabilitare questa impostazione e configurare OneDrive for business per l'utilizzo di un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="d1fb3-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="d1fb3-334">Per informazioni, vedere [pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="d1fb3-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

