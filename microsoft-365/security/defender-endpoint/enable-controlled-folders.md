---
title: Abilitare l’accesso controllato alle cartelle
keywords: Accesso controllato alle cartelle, Windows 10, windows defender, ransomware, proteggere, file, cartelle, abilitare, attivare, usare
description: Informazioni su come proteggere i file importanti abilitando l'accesso controllato alle cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924684"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="b7376-104">Abilitare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="b7376-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7376-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b7376-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7376-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b7376-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7376-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7376-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b7376-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b7376-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7376-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b7376-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b7376-110">[L'accesso controllato](controlled-folders.md) alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware.</span><span class="sxs-lookup"><span data-stu-id="b7376-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="b7376-111">L'accesso controllato alle cartelle è incluso Windows 10 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7376-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="b7376-112">È possibile abilitare l'accesso controllato alle cartelle utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7376-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="b7376-113">Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="b7376-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="b7376-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b7376-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="b7376-115">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="b7376-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="b7376-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b7376-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="b7376-117">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="b7376-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="b7376-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7376-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="b7376-119">[La modalità](evaluate-controlled-folder-access.md) di controllo consente di testare il funzionamento della funzionalità (e di esaminare gli eventi) senza influire sul normale utilizzo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7376-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="b7376-120">Le impostazioni di Criteri di gruppo che disabilitano l'unione degli elenchi di amministratori locali avranno la precedenza su impostazioni di accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="b7376-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="b7376-121">Ignorano anche le cartelle protette e le app consentite impostate dall'amministratore locale tramite l'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="b7376-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="b7376-122">Questi criteri includono:</span><span class="sxs-lookup"><span data-stu-id="b7376-122">These policies include:</span></span>

* <span data-ttu-id="b7376-123">Antivirus Microsoft Defender comportamento **di unione dell'amministratore locale per gli elenchi**</span><span class="sxs-lookup"><span data-stu-id="b7376-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="b7376-124">System Center Endpoint Protection consentire **agli utenti di aggiungere esclusioni e sostituzioni**</span><span class="sxs-lookup"><span data-stu-id="b7376-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="b7376-125">Per ulteriori informazioni sulla disabilitazione dell'unione di elenchi locali, vedere Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri [di Microsoft Defender AV.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b7376-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="b7376-126">Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="b7376-126">Windows Security app</span></span>

1. <span data-ttu-id="b7376-127">Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7376-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="b7376-128">Puoi anche cercare Defender nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="b7376-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="b7376-129">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="b7376-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="b7376-130">Impostare l'opzione **Accesso controllato alle cartelle** su **Attiva.**</span><span class="sxs-lookup"><span data-stu-id="b7376-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="b7376-131">Se l'accesso controllato alle cartelle è configurato con Criteri di gruppo, PowerShell o CSP MDM, lo stato cambierà nell'app Sicurezza di Windows dopo un riavvio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7376-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="b7376-132">Se la funzionalità è impostata sulla **modalità** di controllo con uno di questi strumenti, l Sicurezza di Windows app mostrerà lo stato **come Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="b7376-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="b7376-133">Se si proteggono i dati del profilo utente, è consigliabile che il profilo utente si presenti nell'unità di Windows di installazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b7376-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="b7376-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b7376-134">Endpoint Manager</span></span>

1. <span data-ttu-id="b7376-135">Accedi al Endpoint Manager [e](https://endpoint.microsoft.com) apri **Endpoint Security.**</span><span class="sxs-lookup"><span data-stu-id="b7376-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="b7376-136">Vai a **Criteri di riduzione della superficie di**  >  **attacco.**</span><span class="sxs-lookup"><span data-stu-id="b7376-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="b7376-137">Seleziona **Piattaforma,** scegli Windows 10 **e versioni successive** e seleziona il profilo Regole di riduzione della superficie di **attacco**  >  **Crea.**</span><span class="sxs-lookup"><span data-stu-id="b7376-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="b7376-138">Assegnare un nome al criterio e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b7376-138">Name the policy and add a description.</span></span> <span data-ttu-id="b7376-139">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b7376-139">Select **Next**.</span></span>

5.  <span data-ttu-id="b7376-140">Scorrere verso il basso verso il basso, selezionare l'elenco a discesa **Abilita protezione** cartelle e scegliere **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="b7376-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="b7376-141">Selezionare **Elenco di cartelle aggiuntive che devono essere protette** e aggiungere le cartelle che devono essere protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="b7376-142">Seleziona **Elenco di app che hanno accesso alle cartelle protette** e aggiungi le app che hanno accesso alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="b7376-143">Seleziona **Escludi file e percorsi dalle regole di** riduzione della superficie di attacco e aggiungi i file e i percorsi che devono essere esclusi dalle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="b7376-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="b7376-144">Selezionare il profilo **Assegnazioni,** assegnare a **Tutti gli & tutti i** dispositivi e selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b7376-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="b7376-145">Selezionare **Avanti** per salvare ogni pannello aperto e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b7376-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7376-146">I caratteri jolly sono supportati per le applicazioni, ma non per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="b7376-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="b7376-147">Le sottocartelle non sono protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-147">Subfolders are not protected.</span></span> <span data-ttu-id="b7376-148">Le app consentite continueranno a attivare eventi finché non vengono riavviate.</span><span class="sxs-lookup"><span data-stu-id="b7376-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="b7376-149">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="b7376-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="b7376-150">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="b7376-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b7376-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="b7376-152">In Microsoft Endpoint Configuration Manager, andare a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="b7376-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="b7376-153">Selezionare **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="b7376-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="b7376-154">Immettere un nome e una descrizione, selezionare **Accesso controllato alle cartelle** e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b7376-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="b7376-155">Scegli se bloccare o controllare le modifiche, consentire altre app o aggiungere altre cartelle e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b7376-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b7376-156">Wilcard è supportato per le applicazioni, ma non per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="b7376-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="b7376-157">Le sottocartelle non sono protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-157">Subfolders are not protected.</span></span> <span data-ttu-id="b7376-158">Le app consentite continueranno a attivare eventi finché non vengono riavviate.</span><span class="sxs-lookup"><span data-stu-id="b7376-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="b7376-159">Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="b7376-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="b7376-160">Dopo la creazione del criterio, **chiudere**.</span><span class="sxs-lookup"><span data-stu-id="b7376-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="b7376-161">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="b7376-161">Group Policy</span></span>

1. <span data-ttu-id="b7376-162">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b7376-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="b7376-163">Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="b7376-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b7376-164">Espandi l'albero per **Windows componenti > Antivirus Microsoft Defender > Windows Defender Exploit Guard > accesso controllato alle cartelle**.</span><span class="sxs-lookup"><span data-stu-id="b7376-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="b7376-165">Fare doppio clic **sull'impostazione Configura accesso controllato alle** cartelle e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="b7376-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b7376-166">Nella sezione opzioni è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7376-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="b7376-167">**Abilita:** le app dannose e sospette non possono apportare modifiche ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="b7376-168">Una notifica verrà fornita nel registro Windows eventi.</span><span class="sxs-lookup"><span data-stu-id="b7376-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="b7376-169">**Disabilita (impostazione predefinita):** la funzionalità Accesso controllato alle cartelle non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="b7376-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="b7376-170">Tutte le app possono apportare modifiche ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="b7376-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="b7376-171">**Modalità di controllo:** le modifiche saranno consentite se un'app dannosa o sospetta tenta di apportare una modifica a un file in una cartella protetta.</span><span class="sxs-lookup"><span data-stu-id="b7376-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="b7376-172">Tuttavia, verrà registrato nel registro eventi di Windows in cui è possibile valutare l'impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b7376-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="b7376-173">**Blocca solo la modifica del disco:** i tentativi da parte di app non attendibili di scrivere nei settori del disco verranno registrati Windows registro eventi.</span><span class="sxs-lookup"><span data-stu-id="b7376-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="b7376-174">Questi registri sono disponibili in **Registri applicazioni** e servizi > Microsoft > Windows > Windows Defender > operativo > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="b7376-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="b7376-175">**Controlla** solo la modifica del disco: solo i tentativi di scrittura nei settori del disco protetti verranno registrati nel registro eventi di Windows (in Registri applicazioni e servizi Microsoft Windows Windows Defender ID operativo  >    >    >    >    >  **1124).**</span><span class="sxs-lookup"><span data-stu-id="b7376-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="b7376-176">I tentativi di modifica o eliminazione di file nelle cartelle protette non verranno registrati.</span><span class="sxs-lookup"><span data-stu-id="b7376-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Screenshot of the group policy option Enabled and Audit Mode selected in the drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="b7376-178">Per abilitare completamente l'accesso controllato alle cartelle, devi impostare l'opzione Criteri di gruppo su **Abilitato** e selezionare **Blocca** nel menu a discesa delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="b7376-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="b7376-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7376-179">PowerShell</span></span>

1. <span data-ttu-id="b7376-180">Digitare **powershell** nel menu Start, fare clic con il pulsante destro **del** mouse Windows PowerShell e scegliere Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="b7376-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="b7376-181">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="b7376-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="b7376-182">È possibile abilitare la funzionalità in modalità di controllo specificando `AuditMode` invece `Enabled` di .</span><span class="sxs-lookup"><span data-stu-id="b7376-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="b7376-183">Consente `Disabled` di disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b7376-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7376-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7376-184">See also</span></span>

* [<span data-ttu-id="b7376-185">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="b7376-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="b7376-186">Personalizzare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="b7376-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="b7376-187">Valutare Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b7376-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
