---
title: Bloccare le applicazioni potenzialmente indesiderate con Antivirus Microsoft Defender
description: Abilitare la funzionalità antivirus delle applicazioni potenzialmente indesiderate (PUA) per bloccare il software indesiderato, ad esempio l'adware.
keywords: pua, abilitare, software indesiderato, app indesiderate, adware, barra degli strumenti del browser, rilevare, bloccare, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275241"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="330a9-104">Rilevare e bloccare applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="330a9-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="330a9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="330a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="330a9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="330a9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="330a9-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="330a9-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="330a9-108">Le applicazioni potenzialmente indesiderate (PUA) sono una categoria di software che può causare il rallentamento del computer, la visualizzazione di annunci non previsti o, nel peggiore dei casi, l'installazione di altro software che potrebbe risultare indesiderato o imprevisto.</span><span class="sxs-lookup"><span data-stu-id="330a9-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="330a9-109">Le applicazioni potenzialmente indesiderate non sono considerate virus, malware o minacce di altro tipo, ma potrebbero eseguire azioni che influiscono negativamente sulle prestazioni o sull'uso degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="330a9-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="330a9-110">Il termine *PUA* può anche fare riferimento a un'applicazione con una reputazione scadente, secondo la valutazione di Microsoft Defender per endpoint, a causa di alcuni tipi di comportamento indesiderato.</span><span class="sxs-lookup"><span data-stu-id="330a9-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="330a9-111">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="330a9-111">Here are some examples:</span></span>

- <span data-ttu-id="330a9-112">**Software pubblicitario** che mostra annunci pubblicitari o promozioni, incluso il software che inserisce annunci pubblicitari nelle pagine Web.</span><span class="sxs-lookup"><span data-stu-id="330a9-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="330a9-113">**Software bundler** che offre l'installazione di altro software non firmato digitalmente dalla stessa entità</span><span class="sxs-lookup"><span data-stu-id="330a9-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="330a9-114">oppure classificato come PUA.</span><span class="sxs-lookup"><span data-stu-id="330a9-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="330a9-115">**Software di evasione**, che tenta attivamente di evadere il rilevamento da parte dei prodotti per la sicurezza, incluso il software che si comporta in modo diverso in presenza di prodotti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="330a9-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="330a9-116">Per altri esempi e una descrizione dei criteri che usiamo per etichettare le applicazioni per una particolare attenzione da parte delle funzionalità di sicurezza, vedere [Come Microsoft identifica malware e applicazioni potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="330a9-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="330a9-117">Queste applicazioni possono aumentare il rischio di infezione della rete da parte di malware, possono rendere più difficile l'identificazione di infezioni malware e possono sprecare risorse IT per la pulizia delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="330a9-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="330a9-118">La protezione da applicazioni potenzialmente indesiderate è supportata in Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="330a9-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="330a9-119">In Windows 10 (versione 2004 e successive), Antivirus Microsoft Defender blocca le app considerate PUA per i dispositivi Enterprise (E5) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="330a9-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="330a9-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="330a9-120">Microsoft Edge</span></span>

<span data-ttu-id="330a9-121">Il [nuovo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), basato su Chromium, blocca i download di applicazioni potenzialmente indesiderate e gli URL di risorse associati.</span><span class="sxs-lookup"><span data-stu-id="330a9-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="330a9-122">Questa funzionalità viene fornita tramite [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="330a9-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="330a9-123">Abilitare la protezione da applicazioni potenzialmente indesiderate in Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="330a9-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="330a9-124">Anche se la protezione da applicazioni potenzialmente indesiderate in Microsoft Edge (basato su Chromium, versione 80.0.361.50) è disattivata per impostazione predefinita, può essere attivata facilmente dall'interno del browser.</span><span class="sxs-lookup"><span data-stu-id="330a9-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="330a9-125">Nel browser Microsoft Edge selezionare i puntini di sospensione e quindi **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="330a9-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="330a9-126">Selezionare **Privacy, ricerca e servizi**.</span><span class="sxs-lookup"><span data-stu-id="330a9-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="330a9-127">Nella sezione **Sicurezza** attivare **Blocca app potenzialmente indesiderate**.</span><span class="sxs-lookup"><span data-stu-id="330a9-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="330a9-128">Se si usa Microsoft Edge (basato su Chromium), si può esplorare in sicurezza la funzionalità di blocco degli URL della protezione PUA, testandola in una delle [pagine demo di Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="330a9-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="330a9-129">Bloccare gli URL con Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="330a9-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="330a9-130">In Microsoft Edge basato su Chromium con protezione PUA attivata, Microsoft Defender SmartScreen protegge dagli URL associati alle applicazioni potenzialmente indesiderate.</span><span class="sxs-lookup"><span data-stu-id="330a9-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="330a9-131">Gli amministratori della sicurezza possono [configurare](/DeployEdge/configure-microsoft-edge) il modo in cui Microsoft Edge e Microsoft Defender SmartScreen interagiscono per proteggere gruppi di utenti dagli URL associati alle applicazioni potenzialmente indesiderate.</span><span class="sxs-lookup"><span data-stu-id="330a9-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="330a9-132">Sono disponibili diverse [impostazioni di Criteri di gruppo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) esplicitamente destinate a Microsoft Defender SmartScreen, tra cui [una per bloccare le PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="330a9-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="330a9-133">Gli amministratori possono inoltre [configurare Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) nel suo insieme, usando le impostazioni di Criteri di gruppo per attivare o disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="330a9-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="330a9-134">Anche se Microsoft Defender per endpoint ha un proprio elenco di blocco basato su un set di dati gestito da Microsoft, è possibile personalizzare questo elenco in base alla propria intelligence per le minacce.</span><span class="sxs-lookup"><span data-stu-id="330a9-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="330a9-135">Se si [creano e gestiscono indicatori](manage-indicators.md) nel portale di Microsoft Defender per endpoint, Microsoft Defender SmartScreen rispetta le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="330a9-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="330a9-136">Antivirus Microsoft Defender e protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="330a9-137">La funzionalità di protezione PUA in Antivirus Microsoft Defender può rilevare e bloccare le applicazioni potenzialmente indesiderate negli endpoint della rete.</span><span class="sxs-lookup"><span data-stu-id="330a9-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="330a9-138">Questa funzionalità è disponibile in Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="330a9-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="330a9-139">Antivirus Microsoft Defender blocca i file di PUA rilevati e gli eventuali tentativi di scaricarli, spostarli, eseguirli o installarli.</span><span class="sxs-lookup"><span data-stu-id="330a9-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="330a9-140">I file di PUA bloccati vengono quindi spostati in quarantena.</span><span class="sxs-lookup"><span data-stu-id="330a9-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="330a9-141">Quando viene rilevato un file PUA in un endpoint, Antivirus Microsoft Defender invia una notifica all'utente ([a meno che le notifiche non siano state disabilitate](configure-notifications-microsoft-defender-antivirus.md)) nello stesso formato degli altri rilevamenti delle minacce.</span><span class="sxs-lookup"><span data-stu-id="330a9-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="330a9-142">La notifica è preceduta da `PUA:` per indicarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="330a9-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="330a9-143">La notifica viene visualizzata nel normale [elenco di quarantena nell'app Sicurezza di Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="330a9-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="330a9-144">Configurare la protezione PUA in Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="330a9-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="330a9-145">È possibile abilitare la protezione da applicazioni potenzialmente indesiderate con [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Criteri di gruppo](/azure/active-directory-domain-services/manage-group-policy) o tramite [cmdlet di PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="330a9-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="330a9-146">SI può anche usare la protezione PUA in modalità di controllo per rilevare le applicazioni potenzialmente indesiderate senza bloccarle.</span><span class="sxs-lookup"><span data-stu-id="330a9-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="330a9-147">I rilevamenti vengono acquisiti nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="330a9-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="330a9-148">Visitare il sito Web con le demo di Microsoft Defender per endpoint all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) per verificare se la funzionalità è operativa e vederla in azione.</span><span class="sxs-lookup"><span data-stu-id="330a9-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="330a9-149">La protezione PUA in modalità di controllo è utile se l'azienda sta esegue un controllo di conformità interno sulla sicurezza del software e si desidera evitare falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="330a9-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="330a9-150">Usare Intune per configurare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="330a9-151">Per altre informazioni, vedere [Configurare le impostazioni relative alle restrizioni dei dispositivi in Microsoft Intune](/intune/device-restrictions-configure) e [Impostazioni relative alle restrizioni dei dispositivi di Antivirus Microsoft Defender per Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="330a9-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="330a9-152">Usare Configuration Manager per configurare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="330a9-153">La protezione PUA è abilitata per impostazione predefinita in Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="330a9-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="330a9-154">Vedere la [sezione Impostazioni per le analisi pianificate in Come creare e distribuire criteri antimalware](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="330a9-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="330a9-155">Per System Center Configuration Manager 2012, vedere [Come distribuire criteri di protezione delle applicazioni potenzialmente indesiderate per Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="330a9-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="330a9-156">Gli eventi PUA bloccati da Antivirus Microsoft Defender vengono segnalati nel Visualizzatore eventi di Windows e non in Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="330a9-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="330a9-157">Usare Criteri di gruppo per configurare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="330a9-158">Scaricare e installare i [modelli amministrativi (.admx) per Windows 10 aggiornamento dell'ottobre 2020 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="330a9-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="330a9-159">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="330a9-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="330a9-160">Selezionare l'oggetto Criteri di gruppo da configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="330a9-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="330a9-161">Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="330a9-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="330a9-162">Espandere l'albero fino a **Componenti di Windows** > **Antivirus Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="330a9-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="330a9-163">Fare doppio clic su **Configura il rilevamento di applicazioni potenzialmente indesiderate**.</span><span class="sxs-lookup"><span data-stu-id="330a9-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="330a9-164">Selezionare **Abilitata** per abilitare la protezione PUA.</span><span class="sxs-lookup"><span data-stu-id="330a9-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="330a9-165">In **Opzioni** selezionare **Blocca** per bloccare le applicazioni potenzialmente indesiderate oppure selezionare **Modalità di controllo** per testare il funzionamento dell'impostazione nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="330a9-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="330a9-166">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="330a9-166">Select **OK**.</span></span>

9. <span data-ttu-id="330a9-167">Distribuire l'oggetto Criteri di gruppo come di consueto.</span><span class="sxs-lookup"><span data-stu-id="330a9-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="330a9-168">Usare i cmdlet di PowerShell per configurare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="330a9-169">Per abilitare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="330a9-170">Impostando il valore di questo cmdlet su `Enabled` è possibile attivare la funzionalità, se è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="330a9-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="330a9-171">Per impostare la protezione PUA sulla modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="330a9-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="330a9-172">L'impostazione `AuditMode` consente di rilevare le applicazioni potenzialmente indesiderate senza bloccarle.</span><span class="sxs-lookup"><span data-stu-id="330a9-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="330a9-173">Per disabilitare la protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-173">To disable PUA protection</span></span>

<span data-ttu-id="330a9-174">È consigliabile mantenere la protezione PUA attivata.</span><span class="sxs-lookup"><span data-stu-id="330a9-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="330a9-175">Tuttavia, è possibile disattivarla usando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="330a9-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="330a9-176">Impostando il valore di questo cmdlet su `Disabled` è possibile disattivare la funzionalità, se è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="330a9-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="330a9-177">Per altre informazioni, vedere [Usare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Cmdlet di Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="330a9-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="330a9-178">Visualizzare gli eventi PUA con PowerShell</span><span class="sxs-lookup"><span data-stu-id="330a9-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="330a9-179">Gli eventi PUA vengono segnalati nel Visualizzatore eventi di Windows, ma non in Microsoft Endpoint Manager o in Intune.</span><span class="sxs-lookup"><span data-stu-id="330a9-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="330a9-180">È anche possibile usare il cmdlet `Get-MpThreat` per visualizzare le minacce gestite da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="330a9-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="330a9-181">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="330a9-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="330a9-182">Ricevere notifiche tramite posta elettronica sui rilevamenti di applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="330a9-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="330a9-183">È possibile attivare le notifiche tramite posta elettronica per ricevere messaggi relativi al rilevamento di PUA.</span><span class="sxs-lookup"><span data-stu-id="330a9-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="330a9-184">Vedere l'articolo su come [risolvere i problemi relativi agli ID evento](troubleshoot-microsoft-defender-antivirus.md) per informazioni dettagliate sulla visualizzazione degli eventi di Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="330a9-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="330a9-185">Gli eventi PUA vengono registrati con l'ID evento **1160**.</span><span class="sxs-lookup"><span data-stu-id="330a9-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="330a9-186">Visualizzare gli eventi PUA con la rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="330a9-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="330a9-187">Se si usa [Microsoft Defender per endpoint](microsoft-defender-endpoint.md), è possibile usare una query di rilevazione avanzata per visualizzare gli eventi PUA.</span><span class="sxs-lookup"><span data-stu-id="330a9-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="330a9-188">Ecco una query di esempio:</span><span class="sxs-lookup"><span data-stu-id="330a9-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="330a9-189">Per altre informazioni sulla rilevazione avanzata, vedere [Rilevare in modo proattivo le minacce con la rilevazione avanzata](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="330a9-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="330a9-190">Escludere file dalla protezione PUA</span><span class="sxs-lookup"><span data-stu-id="330a9-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="330a9-191">A volte un file viene erroneamente bloccato dalla protezione PUA oppure per completare un'attività è necessaria una funzionalità di un'applicazione potenzialmente indesiderata.</span><span class="sxs-lookup"><span data-stu-id="330a9-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="330a9-192">In questi casi, è possibile aggiungere un file a un elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="330a9-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="330a9-193">Per altre informazioni, vedere [Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="330a9-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="330a9-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="330a9-194">See also</span></span>

- [<span data-ttu-id="330a9-195">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="330a9-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="330a9-196">Configurare la protezione comportamentale, euristica e in tempo reale</span><span class="sxs-lookup"><span data-stu-id="330a9-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)