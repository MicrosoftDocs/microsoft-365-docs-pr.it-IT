---
title: Risolvere problemi trovati dallo strumento di valutazione dell'idoneità
description: Azioni dettagliate da intraprendere per ogni problema rilevato dallo strumento
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b77313a18a5744549e492de991e282bc34dbb6da
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002418"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="1a3d5-104">Risolvere problemi trovati dallo strumento di valutazione dell'idoneità</span><span class="sxs-lookup"><span data-stu-id="1a3d5-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="1a3d5-105">Per ogni controllo, lo strumento riporterà uno dei quattro possibili risultati:</span><span class="sxs-lookup"><span data-stu-id="1a3d5-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="1a3d5-106">Risultato</span><span class="sxs-lookup"><span data-stu-id="1a3d5-106">Result</span></span>  |<span data-ttu-id="1a3d5-107">Significato</span><span class="sxs-lookup"><span data-stu-id="1a3d5-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="1a3d5-108">Pronto</span><span class="sxs-lookup"><span data-stu-id="1a3d5-108">Ready</span></span>     | <span data-ttu-id="1a3d5-109">Non è necessario eseguire alcuna operazione prima di completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="1a3d5-110">Consulenza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-110">Advisory</span></span>    | <span data-ttu-id="1a3d5-111">Seguire la procedura descritta nello strumento o in questo articolo per la migliore esperienza di registrazione e per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="1a3d5-112">È *possibile* completare la registrazione, ma è necessario correggere questi problemi prima di distribuire il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="1a3d5-113">Non pronto</span><span class="sxs-lookup"><span data-stu-id="1a3d5-113">Not ready</span></span> | <span data-ttu-id="1a3d5-114">*La registrazione avrà esito negativo se non si correggeranno questi problemi.*</span><span class="sxs-lookup"><span data-stu-id="1a3d5-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="1a3d5-115">Seguire la procedura descritta nello strumento o in questo articolo per risolverli.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="1a3d5-116">Error</span><span class="sxs-lookup"><span data-stu-id="1a3d5-116">Error</span></span> | <span data-ttu-id="1a3d5-117">Il ruolo di Azure Active Director (AD) utilizzato non dispone di autorizzazioni sufficienti per eseguire questo controllo.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="1a3d5-118">Impostazioni di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1a3d5-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="1a3d5-119">Profilo di distribuzione Autopilot</span><span class="sxs-lookup"><span data-stu-id="1a3d5-119">Autopilot deployment profile</span></span>

<span data-ttu-id="1a3d5-120">Non è necessario disporre di profili Autopilot esistenti per i gruppi assegnati o dinamici utilizzati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-121">Microsoft Managed Desktop utilizza il pilota automatico per eseguire il provisioning di nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="1a3d5-122">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-122">**Not ready**</span></span>

<span data-ttu-id="1a3d5-123">Si dispone di un profilo Autopilot assegnato a tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="1a3d5-124">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="1a3d5-125">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="1a3d5-126">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-126">**Advisory**</span></span>

<span data-ttu-id="1a3d5-127">Assicurarsi che i profili Autopilot siano destinati a un gruppo di Azure AD assegnato o dinamico che non includa i dispositivi desktop Microsoft gestiti che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="1a3d5-128">Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="1a3d5-129">Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="1a3d5-130">Connettori per i certificati</span><span class="sxs-lookup"><span data-stu-id="1a3d5-130">Certificate connectors</span></span>

<span data-ttu-id="1a3d5-131">Se si dispone di qualsiasi connettore di certificato utilizzato dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non possono avere errori.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="1a3d5-132">Solo uno dei seguenti consulenti si applicherà alla situazione, quindi controllali con attenzione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="1a3d5-133">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-133">**Advisory**</span></span>

<span data-ttu-id="1a3d5-134">Non sono presenti connettori di certificato.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-134">No certificate connectors are present.</span></span> <span data-ttu-id="1a3d5-135">È possibile che non siano necessari connettori, ma è necessario valutare se potrebbe essere necessario un po' di connettività di rete per i dispositivi desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-136">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="1a3d5-137">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-137">**Advisory**</span></span>

<span data-ttu-id="1a3d5-138">Almeno un connettore di certificato ha un errore.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="1a3d5-139">Se è necessario questo connettore per la connettività ai dispositivi Microsoft Managed Desktop, è necessario risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="1a3d5-140">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="1a3d5-141">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-141">**Advisory**</span></span>

<span data-ttu-id="1a3d5-142">Si dispone di almeno un connettore di certificato e non vengono segnalati errori.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="1a3d5-143">Tuttavia, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-144">Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="1a3d5-145">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="1a3d5-145">Conditional access policies</span></span>

<span data-ttu-id="1a3d5-146">I criteri di accesso condizionale nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="1a3d5-147">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-147">**Not ready**</span></span>

<span data-ttu-id="1a3d5-148">Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="1a3d5-149">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa il gruppo di Azure AD degli account di servizio di Microsoft Managed Desktop che verranno creati in fase di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="1a3d5-150">Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="1a3d5-151">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-151">**Advisory**</span></span>

<span data-ttu-id="1a3d5-152">Verificare che tutti i criteri di accesso condizionale siano esclusi dal gruppo di Azure AD degli **account di servizio sul posto di lavoro moderno** .</span><span class="sxs-lookup"><span data-stu-id="1a3d5-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="1a3d5-153">Per i passaggi, vedere [regolare l'accesso condizionale](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="1a3d5-154">Il gruppo di Azure AD dei **servizi di ambiente di lavoro moderno** è un gruppo dinamico creato per il servizio quando si esegue la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="1a3d5-155">Sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="1a3d5-156">Per ulteriori informazioni su questi account di servizio, vedere [standard operative Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="1a3d5-157">**Errore**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-157">**Error**</span></span>

<span data-ttu-id="1a3d5-158">Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="1a3d5-159">Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:</span><span class="sxs-lookup"><span data-stu-id="1a3d5-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="1a3d5-160">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-160">Security Reader</span></span>
- <span data-ttu-id="1a3d5-161">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-161">Security Administrator</span></span>
- <span data-ttu-id="1a3d5-162">Amministratore dell'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="1a3d5-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="1a3d5-163">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="1a3d5-163">Global Reader</span></span>
- <span data-ttu-id="1a3d5-164">Amministratore di dispositivi</span><span class="sxs-lookup"><span data-stu-id="1a3d5-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="1a3d5-165">Criteri di conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1a3d5-165">Device Compliance policies</span></span>

<span data-ttu-id="1a3d5-166">I criteri di conformità dei dispositivi di Intune nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="1a3d5-167">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-167">**Not ready**</span></span>

<span data-ttu-id="1a3d5-168">Si dispone di almeno un criterio di conformità che è destinato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="1a3d5-169">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="1a3d5-170">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="1a3d5-171">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-171">**Advisory**</span></span>

<span data-ttu-id="1a3d5-172">Verificare che i criteri di conformità non includano gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="1a3d5-173">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="1a3d5-174">Criteri di configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1a3d5-174">Device Configuration policies</span></span>

<span data-ttu-id="1a3d5-175">I criteri di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere destinati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="1a3d5-176">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-176">**Not ready**</span></span>

<span data-ttu-id="1a3d5-177">Si dispone di almeno un criterio di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="1a3d5-178">Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-179">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="1a3d5-180">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-180">**Advisory**</span></span>

<span data-ttu-id="1a3d5-181">Verificare che i criteri di conformità non includano dispositivi o utenti desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="1a3d5-182">Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="1a3d5-183">Restrizioni per il tipo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="1a3d5-183">Device type restrictions</span></span>

<span data-ttu-id="1a3d5-184">I dispositivi Microsoft Managed Desktop devono essere autorizzati a eseguire la registrazione in Intune.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="1a3d5-185">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-185">**Not ready**</span></span>

<span data-ttu-id="1a3d5-186">Seguire la procedura descritta in [set Restriction](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) **consentitions** to change the setting to allow.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="1a3d5-187">Pagina stato registrazione</span><span class="sxs-lookup"><span data-stu-id="1a3d5-187">Enrollment Status Page</span></span>

<span data-ttu-id="1a3d5-188">La pagina stato di registrazione (ESP) è attualmente abilitata.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="1a3d5-189">Se si partecipa all'anteprima pubblica di questa funzionalità, è possibile ignorare questo elemento.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="1a3d5-190">Per ulteriori informazioni, vedere [First-Run experience with Autopilot e la pagina status di registrazione](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="1a3d5-191">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-191">**Not ready**</span></span>

<span data-ttu-id="1a3d5-192">Si dispone del set di profili ESP predefinito per **visualizzare lo stato di avanzamento della configurazione dei profili e delle app**.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="1a3d5-193">Disabilitare questa impostazione o verificare che le assegnazioni a un gruppo di Azure AD non includano i dispositivi Microsoft Managed Desktop attenendosi alla procedura descritta in [set up the registration status page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="1a3d5-194">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-194">**Advisory**</span></span>

<span data-ttu-id="1a3d5-195">Verificare che i profili con l'impostazione **Mostra avanzamento configurazione app e profilo** non siano assegnati a nessun gruppo di Azure ad che includa i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-196">Per ulteriori informazioni, vedere [configurare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="1a3d5-197">Registrazione di Intune</span><span class="sxs-lookup"><span data-stu-id="1a3d5-197">Intune enrollment</span></span>

<span data-ttu-id="1a3d5-198">I dispositivi Windows 10 nell'organizzazione di Azure AD devono essere registrati automaticamente in Intune.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="1a3d5-199">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-199">**Advisory**</span></span>

<span data-ttu-id="1a3d5-200">Verificare che l'ambito dell'utente MDM sia impostato su **alcuni** o su **tutti** , non su **None**.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="1a3d5-201">Se si sceglie **alcuni** , tornare dopo la registrazione e selezionare la **moderna area di lavoro-tutto** il gruppo di Azure ad per i **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="1a3d5-202">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="1a3d5-202">Microsoft Store for Business</span></span>

<span data-ttu-id="1a3d5-203">Microsoft Store for business viene utilizzato in modo da poter scaricare il portale aziendale per distribuire alcune app, ad esempio Microsoft Project e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="1a3d5-204">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-204">**Not ready**</span></span>

<span data-ttu-id="1a3d5-205">Microsoft Store for business non è abilitato o non è sincronizzato con Intune.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="1a3d5-206">Per ulteriori informazioni, vedere [How to Manage volume purchased Apps from the Microsoft Store for business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="1a3d5-207">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="1a3d5-207">Multi-factor authentication</span></span>

<span data-ttu-id="1a3d5-208">Per l'autenticazione a più fattori non è necessario applicare accidentalmente gli account di servizio di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="1a3d5-209">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-209">**Not ready**</span></span>

<span data-ttu-id="1a3d5-210">Si dispone di alcuni criteri di autenticazione a più fattori (AMF) impostati come "necessari" per i criteri di accesso condizionale assegnati a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="1a3d5-211">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-212">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="1a3d5-213">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-213">**Advisory**</span></span>

<span data-ttu-id="1a3d5-214">Verificare che tutti i criteri di accesso condizionale che richiedono l'AMF escludano la **moderna area di lavoro-tutti i** gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="1a3d5-215">Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="1a3d5-216">La **moderna area di lavoro-tutti i** gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="1a3d5-217">**Errore**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-217">**Error**</span></span>

<span data-ttu-id="1a3d5-218">Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="1a3d5-219">Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:</span><span class="sxs-lookup"><span data-stu-id="1a3d5-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="1a3d5-220">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-220">Security Reader</span></span>
- <span data-ttu-id="1a3d5-221">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-221">Security Administrator</span></span>
- <span data-ttu-id="1a3d5-222">Amministratore dell'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="1a3d5-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="1a3d5-223">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="1a3d5-223">Global Reader</span></span>
- <span data-ttu-id="1a3d5-224">Amministratore di dispositivi</span><span class="sxs-lookup"><span data-stu-id="1a3d5-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="1a3d5-225">Script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a3d5-225">PowerShell scripts</span></span>

<span data-ttu-id="1a3d5-226">Gli script di Windows PowerShell non possono essere assegnati in modo da indirizzare i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="1a3d5-227">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-227">**Advisory**</span></span>

<span data-ttu-id="1a3d5-228">Assicurarsi che gli script di Windows PowerShell nell'organizzazione Azure AD non vengano indirizzati a qualsiasi dispositivo o utente di Microsoft Manage desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="1a3d5-229">Non assegnare uno script di PowerShell per indirizzare tutti gli utenti, tutti i dispositivi o entrambi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="1a3d5-230">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-231">Per ulteriori informazioni, vedere [utilizzare gli script di PowerShell nei dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="1a3d5-232">Area geografica</span><span class="sxs-lookup"><span data-stu-id="1a3d5-232">Region</span></span>

<span data-ttu-id="1a3d5-233">La propria area geografica deve essere supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="1a3d5-234">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-234">**Not ready**</span></span>

<span data-ttu-id="1a3d5-235">L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-236">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="1a3d5-237">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-237">**Advisory**</span></span>

<span data-ttu-id="1a3d5-238">Uno o più dei paesi in cui si trova l'organizzazione Azure AD non è supportato da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-239">Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="1a3d5-240">Linee di base per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-240">Security baselines</span></span>

<span data-ttu-id="1a3d5-241">I criteri di base di sicurezza non devono essere destinati ai dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="1a3d5-242">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-242">**Not ready**</span></span>

<span data-ttu-id="1a3d5-243">Si dispone di un profilo di base di sicurezza che è destinato a tutti gli utenti, tutti i dispositivi o entrambi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="1a3d5-244">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-245">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="1a3d5-246">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-246">**Advisory**</span></span>

<span data-ttu-id="1a3d5-247">Assicurarsi che tutti i criteri di base di sicurezza che è possibile escludere i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-248">Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="1a3d5-249">I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="1a3d5-250">App di Windows</span><span class="sxs-lookup"><span data-stu-id="1a3d5-250">Windows apps</span></span>

<span data-ttu-id="1a3d5-251">Esaminare le app desiderate dagli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="1a3d5-252">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-252">**Advisory**</span></span>

<span data-ttu-id="1a3d5-253">È consigliabile preparare un inventario delle app che si desidera vengano convogliate dagli utenti di Microsoft Desktop gestiti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="1a3d5-254">Poiché queste app devono essere distribuite da Intune, valutare il riutilizzo delle app di Intune esistenti.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-254">Since these these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="1a3d5-255">È consigliabile utilizzare il portale aziendale (vedere [Install Intune Company Portal on Devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Registration status page (ESP) to distribute Apps to your users.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-255">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="1a3d5-256">Per ulteriori informazioni, vedere [app in Microsoft Managed Desktop](apps.md) and [First-Run experience with Autopilot e la pagina status di registrazione](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-256">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="1a3d5-257">È possibile richiedere al rappresentante dell'account Microsoft una query in Microsoft endpoint Configuration Manager per identificare le applicazioni che sono pronte per la migrazione a Intune o che devono essere rettificate.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-257">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="1a3d5-258">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="1a3d5-258">Windows Hello for Business</span></span>

<span data-ttu-id="1a3d5-259">Microsoft Managed Desktop richiede l'abilitazione di Windows Hello for business.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-259">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="1a3d5-260">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-260">**Not ready**</span></span>

<span data-ttu-id="1a3d5-261">Windows Hello for business è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-261">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="1a3d5-262">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="1a3d5-262">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="1a3d5-263">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-263">**Advisory**</span></span>

<span data-ttu-id="1a3d5-264">Windows Hello for business non è configurato.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-264">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="1a3d5-265">Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-265">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="1a3d5-266">Anelli di aggiornamento di Windows 10</span><span class="sxs-lookup"><span data-stu-id="1a3d5-266">Windows 10 update rings</span></span>

<span data-ttu-id="1a3d5-267">Il criterio "Windows 10 Update Ring" in Intune non deve essere indirizzato a qualsiasi dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-267">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="1a3d5-268">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-268">**Not ready**</span></span>

<span data-ttu-id="1a3d5-269">Si dispone di un criterio "anello di aggiornamento" che consente di indirizzare tutti i dispositivi, tutti gli utenti o entrambi.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-269">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="1a3d5-270">Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-270">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1a3d5-271">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-271">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="1a3d5-272">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-272">**Advisory**</span></span>

<span data-ttu-id="1a3d5-273">Verificare che tutti i criteri anello di aggiornamento siano esclusi dai **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-273">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="1a3d5-274">Se è stato assegnato un gruppo di utenti di Azure AD a questi criteri, verificare che i criteri di aggiornamento siano stati esclusi anche dalla **moderna area di lavoro: tutti** i gruppi di Azure ad che includono gli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-274">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="1a3d5-275">Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="1a3d5-276">Sia i **dispositivi di lavoro moderni-tutti** che quelli **moderni-tutti** i gruppi di Azure ad sono assegnati ai gruppi creati quando si effettua la registrazione in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-276">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="1a3d5-277">Impostazioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1a3d5-277">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="1a3d5-278">Abbonamenti ad hoc</span><span class="sxs-lookup"><span data-stu-id="1a3d5-278">Ad hoc subscriptions</span></span>

<span data-ttu-id="1a3d5-279">Si consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento del roaming dello stato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-279">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="1a3d5-280">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-280">**Advisory**</span></span>

<span data-ttu-id="1a3d5-281">Verificare che **AllowAdHocSubscriptions** sia impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-281">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="1a3d5-282">In caso contrario, il roaming dello stato dell'organizzazione potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-282">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="1a3d5-283">Per ulteriori informazioni, vedere [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-283">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="1a3d5-284">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="1a3d5-284">Enterprise State Roaming</span></span>

<span data-ttu-id="1a3d5-285">Il roaming dello stato dell'organizzazione deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-285">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="1a3d5-286">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-286">**Advisory**</span></span>

<span data-ttu-id="1a3d5-287">Verificare che il roaming dello stato dell'organizzazione sia abilitato per tutti o per **i** gruppi **selezionati** .</span><span class="sxs-lookup"><span data-stu-id="1a3d5-287">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="1a3d5-288">Per ulteriori informazioni, vedere [Enable Enterprise state roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-288">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="1a3d5-289">Licenze</span><span class="sxs-lookup"><span data-stu-id="1a3d5-289">Licenses</span></span>

<span data-ttu-id="1a3d5-290">Per utilizzare Microsoft Managed Desktop è necessario disporre di un numero di licenze.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-290">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="1a3d5-291">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-291">**Not Ready**</span></span>

<span data-ttu-id="1a3d5-292">Non si dispone di tutte le licenze necessarie per l'utilizzo di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-292">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-293">Per ulteriori informazioni, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md) e [altro sulle licenze](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-293">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="1a3d5-294">Nomi degli account di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-294">Security account names</span></span>

<span data-ttu-id="1a3d5-295">Alcuni nomi degli account di sicurezza potrebbero essere in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-295">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="1a3d5-296">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-296">**Not ready**</span></span>

<span data-ttu-id="1a3d5-297">Si dispone di almeno un nome di account che sarà in conflitto con quelli creati da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-297">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-298">Collaborare con il rappresentante dell'account Microsoft per escludere i nomi degli account.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-298">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="1a3d5-299">Ruoli di amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-299">Security administrator roles</span></span>

<span data-ttu-id="1a3d5-300">Gli utenti con determinati ruoli di sicurezza devono avere quelli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-300">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="1a3d5-301">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-301">**Advisory**</span></span>

<span data-ttu-id="1a3d5-302">Se gli utenti sono assegnati a uno di questi ruoli nell'organizzazione di Azure AD, assicurarsi che dispongano anche di questi ruoli assegnati in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-302">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1a3d5-303">In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-303">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="1a3d5-304">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-304">Security Operator</span></span>
- <span data-ttu-id="1a3d5-305">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="1a3d5-305">Global Reader</span></span>

<span data-ttu-id="1a3d5-306">Per ulteriori informazioni, vedere [creare e gestire i ruoli per il controllo di accesso basato sui ruoli](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-306">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="1a3d5-307">Impostazione predefinita per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a3d5-307">Security default</span></span>

<span data-ttu-id="1a3d5-308">Le impostazioni predefinite per la sicurezza in Azure Active Directory impediscono la gestione dei dispositivi da parte di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-308">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="1a3d5-309">**Non pronto**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-309">**Not ready**</span></span>

<span data-ttu-id="1a3d5-310">Sono state attivate le impostazioni predefinite per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-310">You have Security defaults turned on.</span></span> <span data-ttu-id="1a3d5-311">Disattivare le impostazioni predefinite per la sicurezza e configurare i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-311">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="1a3d5-312">Per ulteriori informazioni, vedere [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-312">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="1a3d5-313">Reimpostazione della password in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="1a3d5-313">Self-service Password Reset</span></span>

<span data-ttu-id="1a3d5-314">La reimpostazione della password self-service (SSPR) deve essere abilitata per tutti gli utenti di Microsoft Managed Desktop esclusi gli account di servizio Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-314">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="1a3d5-315">Per ulteriori informazioni, vedere [esercitazione: consentire agli utenti di sbloccare l'account o reimpostare le password tramite la reimpostazione della password self-service di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="1a3d5-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="1a3d5-316">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-316">**Advisory**</span></span>

<span data-ttu-id="1a3d5-317">Verificare che l'impostazione SSPR **Selected** includa i dispositivi Microsoft Managed Desktop ma escluda gli account di servizio di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="1a3d5-318">Gli account di servizio di Microsoft Managed Desktop non possono funzionare come previsto quando SSPR è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-318">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="1a3d5-319">Ruolo utente standard</span><span class="sxs-lookup"><span data-stu-id="1a3d5-319">Standard user role</span></span>

<span data-ttu-id="1a3d5-320">A parte gli utenti a cui sono stati assegnati i ruoli di Azure AD di amministratore globale e amministratore di dispositivi, gli utenti di Microsoft Managed Desktop saranno utenti standard senza privilegi di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-320">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="1a3d5-321">A tutti gli altri utenti verrà assegnato un ruolo utente standard quando avviano il dispositivo Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-321">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="1a3d5-322">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-322">**Advisory**</span></span>

<span data-ttu-id="1a3d5-323">Gli utenti di Microsoft Managed Desktop non disporranno dei privilegi di amministratore locale nei dispositivi desktop Microsoft gestiti dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-323">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="1a3d5-324">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="1a3d5-324">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="1a3d5-325">OneDrive</span><span class="sxs-lookup"><span data-stu-id="1a3d5-325">OneDrive</span></span>

<span data-ttu-id="1a3d5-326">L'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** sarà in conflitto con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-326">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="1a3d5-327">**Consulenza**</span><span class="sxs-lookup"><span data-stu-id="1a3d5-327">**Advisory**</span></span>

<span data-ttu-id="1a3d5-328">Si sta utilizzando l'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** .</span><span class="sxs-lookup"><span data-stu-id="1a3d5-328">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="1a3d5-329">Questa impostazione non funzionerà con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-329">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a3d5-330">Disabilitare questa impostazione e configurare OneDrive per l'utilizzo di un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="1a3d5-330">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="1a3d5-331">Per informazioni, vedere [pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="1a3d5-331">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

