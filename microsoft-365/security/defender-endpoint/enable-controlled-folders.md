---
title: Abilitare l'accesso controllato alle cartelle
keywords: Accesso controllato alle cartelle, Windows 10, windows defender, ransomware, proteggere, file, cartelle, abilitare, attivare, usare
description: Informazioni su come proteggere i file importanti abilitando l'accesso controllato alle cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218761"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="2b872-104">Abilitare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="2b872-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b872-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2b872-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b872-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2b872-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b872-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b872-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2b872-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2b872-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2b872-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2b872-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2b872-110">[L'accesso controllato](controlled-folders.md) alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware.</span><span class="sxs-lookup"><span data-stu-id="2b872-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="2b872-111">L'accesso controllato alle cartelle è incluso in Windows 10 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2b872-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="2b872-112">È possibile abilitare l'accesso controllato alle cartelle utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b872-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="2b872-113">App Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="2b872-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="2b872-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2b872-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="2b872-115">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="2b872-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="2b872-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b872-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="2b872-117">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2b872-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="2b872-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b872-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="2b872-119">[La modalità](evaluate-controlled-folder-access.md) di controllo consente di testare il funzionamento della funzionalità (e di esaminare gli eventi) senza influire sul normale utilizzo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b872-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="2b872-120">Le impostazioni di Criteri di gruppo che disabilitano l'unione degli elenchi di amministratori locali avranno la precedenza su impostazioni di accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="2b872-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="2b872-121">Ignorano anche le cartelle protette e le app consentite impostate dall'amministratore locale tramite l'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="2b872-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="2b872-122">Questi criteri includono:</span><span class="sxs-lookup"><span data-stu-id="2b872-122">These policies include:</span></span>

* <span data-ttu-id="2b872-123">Microsoft Defender Antivirus **Configurare il comportamento di unione dell'amministratore locale per gli elenchi**</span><span class="sxs-lookup"><span data-stu-id="2b872-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="2b872-124">System Center Endpoint Protection **Consenti agli utenti di aggiungere esclusioni e sostituzioni**</span><span class="sxs-lookup"><span data-stu-id="2b872-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="2b872-125">Per ulteriori informazioni sulla disabilitazione dell'unione di elenchi locali, vedere Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri [di Microsoft Defender AV.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="2b872-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="2b872-126">App Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="2b872-126">Windows Security app</span></span>

1. <span data-ttu-id="2b872-127">Apri l'app Sicurezza di Windows selezionando l'icona scudo nella barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2b872-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="2b872-128">Puoi anche cercare Defender nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="2b872-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="2b872-129">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="2b872-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="2b872-130">Impostare l'opzione **Accesso controllato alle cartelle** su **Attiva.**</span><span class="sxs-lookup"><span data-stu-id="2b872-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="2b872-131">Se l'accesso controllato alle cartelle è configurato con Criteri di gruppo, PowerShell o CSP MDM, lo stato cambierà nell'app Sicurezza di Windows dopo un riavvio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b872-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="2b872-132">Se la funzionalità è impostata sulla **modalità** di controllo con uno di questi strumenti, l'app Sicurezza di Windows mostrerà lo stato come **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="2b872-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="2b872-133">Se stai proteggendo i dati del profilo utente, ti consigliamo di usare il profilo utente nell'unità di installazione predefinita di Windows.</span><span class="sxs-lookup"><span data-stu-id="2b872-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="2b872-134">Intune</span><span class="sxs-lookup"><span data-stu-id="2b872-134">Intune</span></span>

1. <span data-ttu-id="2b872-135">Accedi al portale [di Azure e](https://portal.azure.com) apri Intune.</span><span class="sxs-lookup"><span data-stu-id="2b872-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="2b872-136">Vai a **Profili di configurazione** dei  >  **dispositivi**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="2b872-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="2b872-137">Assegnare un nome al profilo, **scegliere Windows 10 e versioni successive** e Endpoint **protection.**</span><span class="sxs-lookup"><span data-stu-id="2b872-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="2b872-138">![Creare il profilo di endpoint protection](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="2b872-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="2b872-139">Vai a **Configura Windows Defender** accesso controllato alla cartella di  >  **Exploit Guard**  >    >  **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="2b872-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="2b872-140">Digitare il percorso di ogni applicazione che ha accesso alle cartelle protette e il percorso di qualsiasi cartella aggiuntiva che necessita di protezione.</span><span class="sxs-lookup"><span data-stu-id="2b872-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="2b872-141">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2b872-141">Select **Add**.</span></span><br/> <span data-ttu-id="2b872-142">![Abilitare l'accesso controllato alle cartelle in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="2b872-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="2b872-143">Wilcard è supportato per le applicazioni, ma non per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="2b872-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2b872-144">Le sottocartelle non sono protette.</span><span class="sxs-lookup"><span data-stu-id="2b872-144">Subfolders are not protected.</span></span> <span data-ttu-id="2b872-145">Le app consentite continueranno a attivare eventi finché non vengono riavviate.</span><span class="sxs-lookup"><span data-stu-id="2b872-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="2b872-146">Selezionare **OK** per salvare ogni pannello aperto e **Crea**.</span><span class="sxs-lookup"><span data-stu-id="2b872-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="2b872-147">Selezionare il profilo **Assegnazioni,** assegnare a **Tutti gli utenti & Tutti i dispositivi** e **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b872-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="2b872-148">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="2b872-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="2b872-149">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="2b872-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2b872-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2b872-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="2b872-151">In Microsoft Endpoint Configuration Manager, vai a **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="2b872-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="2b872-152">Selezionare **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="2b872-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="2b872-153">Immettere un nome e una descrizione, selezionare **Accesso controllato alle cartelle** e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="2b872-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="2b872-154">Scegli se bloccare o controllare le modifiche, consentire altre app o aggiungere altre cartelle e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="2b872-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2b872-155">Wilcard è supportato per le applicazioni, ma non per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="2b872-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2b872-156">Le sottocartelle non sono protette.</span><span class="sxs-lookup"><span data-stu-id="2b872-156">Subfolders are not protected.</span></span> <span data-ttu-id="2b872-157">Le app consentite continueranno a attivare eventi finché non vengono riavviate.</span><span class="sxs-lookup"><span data-stu-id="2b872-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="2b872-158">Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2b872-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="2b872-159">Dopo la creazione del criterio, **chiudere**.</span><span class="sxs-lookup"><span data-stu-id="2b872-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="2b872-160">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2b872-160">Group Policy</span></span>

1. <span data-ttu-id="2b872-161">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2b872-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="2b872-162">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="2b872-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="2b872-163">Espandi l'albero fino ai componenti **di Windows > Microsoft Defender Antivirus > Windows Defender Exploit Guard > accesso controllato alle cartelle.**</span><span class="sxs-lookup"><span data-stu-id="2b872-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="2b872-164">Fare doppio clic **sull'impostazione Configura accesso controllato alle** cartelle e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="2b872-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2b872-165">Nella sezione opzioni è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b872-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="2b872-166">**Abilita:** le app dannose e sospette non possono apportare modifiche ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="2b872-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="2b872-167">Nel registro eventi di Windows verrà fornita una notifica.</span><span class="sxs-lookup"><span data-stu-id="2b872-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="2b872-168">**Disabilita (impostazione predefinita):** la funzionalità Accesso controllato alle cartelle non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="2b872-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="2b872-169">Tutte le app possono apportare modifiche ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="2b872-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="2b872-170">**Modalità di controllo:** le modifiche saranno consentite se un'app dannosa o sospetta tenta di apportare una modifica a un file in una cartella protetta.</span><span class="sxs-lookup"><span data-stu-id="2b872-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="2b872-171">Tuttavia, verrà registrato nel registro eventi di Windows in cui è possibile valutare l'impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b872-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="2b872-172">**Blocca solo la modifica del disco:** i tentativi da parte di app non attendibili di scrivere nei settori del disco verranno registrati nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="2b872-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="2b872-173">Questi registri sono disponibili in **Registri** applicazioni e servizi > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="2b872-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="2b872-174">**Controlla solo** la modifica del disco: solo i tentativi di scrittura nei settori del disco protetti verranno registrati nel registro eventi di Windows (in Registri applicazioni e servizi Microsoft Windows Windows Defender ID operativo  >    >    >    >    >  **1124**).</span><span class="sxs-lookup"><span data-stu-id="2b872-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="2b872-175">I tentativi di modifica o eliminazione di file nelle cartelle protette non verranno registrati.</span><span class="sxs-lookup"><span data-stu-id="2b872-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Screenshot of the group policy option Enabled and Audit Mode selected in the drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="2b872-177">Per abilitare completamente l'accesso controllato alle cartelle, devi impostare l'opzione Criteri di gruppo su **Abilitato** e selezionare **Blocca** nel menu a discesa delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="2b872-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="2b872-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b872-178">PowerShell</span></span>

1. <span data-ttu-id="2b872-179">Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="2b872-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2b872-180">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2b872-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="2b872-181">È possibile abilitare la funzionalità in modalità di controllo specificando `AuditMode` invece `Enabled` di .</span><span class="sxs-lookup"><span data-stu-id="2b872-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="2b872-182">Consente `Disabled` di disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2b872-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b872-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b872-183">See also</span></span>

* [<span data-ttu-id="2b872-184">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="2b872-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="2b872-185">Personalizzare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="2b872-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="2b872-186">Valutare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="2b872-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
