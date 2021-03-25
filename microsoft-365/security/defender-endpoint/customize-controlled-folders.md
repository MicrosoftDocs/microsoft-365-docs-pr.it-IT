---
title: Personalizzare l'accesso controllato alle cartelle
description: Aggiungi altre cartelle che devono essere protette dall'accesso controllato alle cartelle o consenti alle app che bloccano in modo errato le modifiche ai file importanti.
keywords: Accesso controllato alle cartelle, windows 10, windows defender, ransomware, proteggere, file, cartelle, personalizzare, aggiungere cartella, aggiungere app, consentire, aggiungere eseguibile
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163340"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="a6a48-104">Personalizzare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="a6a48-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a6a48-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a6a48-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6a48-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a6a48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6a48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6a48-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a6a48-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6a48-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a6a48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="a6a48-110">L'accesso controllato alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware.</span><span class="sxs-lookup"><span data-stu-id="a6a48-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="a6a48-111">L'accesso controllato alle cartelle è supportato nei client Windows Server 2019 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a6a48-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="a6a48-112">In questo articolo viene descritto come personalizzare le funzionalità di accesso controllato alle cartelle e sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6a48-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="a6a48-113">Proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="a6a48-114">Aggiungere app a cui dovrebbe essere consentito l'accesso alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="a6a48-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="a6a48-115">Consenti ai file eseguibili firmati di accedere alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="a6a48-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="a6a48-116">Personalizzare la notifica</span><span class="sxs-lookup"><span data-stu-id="a6a48-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="a6a48-117">L'accesso controllato alle cartelle monitora le app per le attività rilevate come dannose.</span><span class="sxs-lookup"><span data-stu-id="a6a48-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="a6a48-118">A volte, alle app legittime viene impedito di apportare modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="a6a48-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="a6a48-119">Se l'accesso controllato alle cartelle influisce sulla produttività dell'organizzazione, è consigliabile eseguire questa funzionalità [in](audit-windows-defender.md) modalità di controllo per valutarne completamente l'impatto.</span><span class="sxs-lookup"><span data-stu-id="a6a48-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="a6a48-120">Proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-120">Protect additional folders</span></span>

<span data-ttu-id="a6a48-121">L'accesso controllato alle cartelle si applica a molte cartelle di sistema e posizioni predefinite, incluse cartelle quali **Documenti,** **Immagini** e **Filmati.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="a6a48-122">È possibile aggiungere altre cartelle da proteggere, ma non rimuovere le cartelle predefinite nell'elenco predefinito.</span><span class="sxs-lookup"><span data-stu-id="a6a48-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="a6a48-123">L'aggiunta di altre cartelle all'accesso controllato alle cartelle può essere utile nei casi in cui non si archiviano file nelle raccolte di Windows predefinite o se è stato modificato il percorso predefinito delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a6a48-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="a6a48-124">È inoltre possibile specificare condivisioni di rete e unità mappate.</span><span class="sxs-lookup"><span data-stu-id="a6a48-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="a6a48-125">Sono supportati variabili di ambiente e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="a6a48-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="a6a48-126">Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="a6a48-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="a6a48-127">Puoi usare l'app Sicurezza di Windows, Criteri di gruppo, i cmdlet di PowerShell o i provider di servizi di configurazione per la gestione dei dispositivi mobili per aggiungere e rimuovere cartelle protette aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a6a48-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="a6a48-128">Usare l'app Sicurezza di Windows per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="a6a48-129">Apri l'app Sicurezza di Windows selezionando l'icona scudo nella barra delle applicazioni o cercando **sicurezza** nel menu Start.</span><span class="sxs-lookup"><span data-stu-id="a6a48-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="a6a48-130">Seleziona **Protezione da & virus** e quindi scorri verso il basso fino alla sezione Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="a6a48-131">Seleziona **Gestisci protezione ransomware** per aprire il riquadro Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="a6a48-132">Nella sezione **Accesso controllato alle cartelle** selezionare Cartelle **protette**.</span><span class="sxs-lookup"><span data-stu-id="a6a48-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="a6a48-133">Scegliere **Sì** nel prompt **Controllo di accesso utente.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="a6a48-134">Verrà **visualizzato il** riquadro Cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="a6a48-135">Selezionare **Aggiungi una cartella protetta** e seguire le istruzioni per aggiungere cartelle.</span><span class="sxs-lookup"><span data-stu-id="a6a48-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="a6a48-136">Usare Criteri di gruppo per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="a6a48-137">Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a6a48-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="a6a48-138">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="a6a48-139">Espandi l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Windows Defender accesso controllato alle cartelle di  >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="a6a48-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="a6a48-140">Fare doppio clic **su Cartelle protette configurate** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="a6a48-141">Selezionare **Mostra** e immettere ogni cartella.</span><span class="sxs-lookup"><span data-stu-id="a6a48-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="a6a48-142">Usare PowerShell per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="a6a48-143">Digitare **PowerShell** nel menu Start, fare clic con il pulsante destro **del** mouse Windows PowerShell e scegliere Esegui **come amministratore**</span><span class="sxs-lookup"><span data-stu-id="a6a48-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="a6a48-144">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a6a48-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="a6a48-145">Ripetere il passaggio 2 finché non sono state aggiunte tutte le cartelle che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="a6a48-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="a6a48-146">Le cartelle aggiunte sono visibili nell'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a48-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Screenshot of a PowerShell window with the cmdlet above entered](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="a6a48-148">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="a6a48-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="a6a48-149">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="a6a48-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="a6a48-150">Usare CSP MDM per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a6a48-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="a6a48-151">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="a6a48-152">Consenti ad app specifiche di apportare modifiche alle cartelle controllate</span><span class="sxs-lookup"><span data-stu-id="a6a48-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="a6a48-153">Puoi specificare se determinate app sono sempre considerate sicure e concedere l'accesso in scrittura ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="a6a48-154">Consentire le app può essere utile se una determinata app che conosci e considera attendibile viene bloccata dalla funzionalità di accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="a6a48-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6a48-155">Per impostazione predefinita, Windows aggiunge app considerate descrittive all'elenco di elementi consentiti.</span><span class="sxs-lookup"><span data-stu-id="a6a48-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="a6a48-156">Tali app aggiunte automaticamente non vengono registrate nell'elenco visualizzato nell'app Sicurezza di Windows o tramite i cmdlet di PowerShell associati.</span><span class="sxs-lookup"><span data-stu-id="a6a48-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="a6a48-157">Non è necessario aggiungere la maggior parte delle app.</span><span class="sxs-lookup"><span data-stu-id="a6a48-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="a6a48-158">Aggiungi app solo se vengono bloccate e puoi verificarne l'attendibilità.</span><span class="sxs-lookup"><span data-stu-id="a6a48-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="a6a48-159">Quando aggiungi un'app, devi specificare la posizione dell'app.</span><span class="sxs-lookup"><span data-stu-id="a6a48-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="a6a48-160">Solo l'app in tale percorso sarà autorizzata ad accedere alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="a6a48-161">Se l'app (con lo stesso nome) si trova in un percorso diverso, non verrà aggiunta all'elenco consenti e potrebbe essere bloccata dall'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="a6a48-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="a6a48-162">Un'applicazione o un servizio consentito ha accesso in scrittura a una cartella controllata solo dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="a6a48-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="a6a48-163">Ad esempio, un servizio di aggiornamento continuerà a attivare eventi dopo che è consentito fino a quando non viene arrestato e riavviato.</span><span class="sxs-lookup"><span data-stu-id="a6a48-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="a6a48-164">Usare l'app Windows Defender Sicurezza per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="a6a48-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="a6a48-165">Apri l'app Sicurezza di Windows cercando Sicurezza **nel** menu Start.</span><span class="sxs-lookup"><span data-stu-id="a6a48-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="a6a48-166">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Gestisci protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="a6a48-167">Nella sezione **Accesso controllato alle cartelle** seleziona Consenti **un'app tramite Accesso controllato alle cartelle**</span><span class="sxs-lookup"><span data-stu-id="a6a48-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="a6a48-168">Seleziona **Aggiungi un'app consentita** e segui le istruzioni per aggiungere app.</span><span class="sxs-lookup"><span data-stu-id="a6a48-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Screenshot di come aggiungere un pulsante dell'app consentito](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="a6a48-170">Usare Criteri di gruppo per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="a6a48-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="a6a48-171">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a6a48-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="a6a48-172">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="a6a48-173">Espandi l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Windows Defender accesso controllato alle cartelle di  >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="a6a48-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="a6a48-174">Fare doppio clic **sull'impostazione Configura applicazioni consentite** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="a6a48-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a6a48-175">Seleziona **Mostra** e immetti ogni app.</span><span class="sxs-lookup"><span data-stu-id="a6a48-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="a6a48-176">Usare PowerShell per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="a6a48-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="a6a48-177">Digitare **PowerShell** nel menu Start, fare clic con il pulsante destro **del** mouse Windows PowerShell e scegliere Esegui **come amministratore**</span><span class="sxs-lookup"><span data-stu-id="a6a48-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="a6a48-178">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a6a48-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="a6a48-179">Ad esempio, per aggiungere il *test.exe* eseguibile nella cartella *C:\apps,* il cmdlet sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="a6a48-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="a6a48-180">Continua a usare `Add-MpPreference -ControlledFolderAccessAllowedApplications` per aggiungere altre app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="a6a48-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="a6a48-181">Le app aggiunte con questo cmdlet verranno visualizzate nell'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a48-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Screenshot of a PowerShell window with the above cmdlet entered](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="a6a48-183">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="a6a48-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="a6a48-184">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="a6a48-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="a6a48-185">Usare CSP MDM per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="a6a48-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="a6a48-186">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="a6a48-187">Consenti ai file eseguibili firmati di accedere alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="a6a48-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="a6a48-188">Gli indicatori di file e certificati di Microsoft Defender for Endpoint possono consentire ai file eseguibili firmati di accedere alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="a6a48-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="a6a48-189">Per informazioni dettagliate sull'implementazione, vedere [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span><span class="sxs-lookup"><span data-stu-id="a6a48-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="a6a48-190">Ciò non si applica ai motori di script, incluso Powershell</span><span class="sxs-lookup"><span data-stu-id="a6a48-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="a6a48-191">Personalizzare la notifica</span><span class="sxs-lookup"><span data-stu-id="a6a48-191">Customize the notification</span></span>

<span data-ttu-id="a6a48-192">Per altre informazioni sulla personalizzazione della notifica quando viene attivata una regola e blocca un'app o un file, vedi Configurare le notifiche di [avviso in Microsoft Defender for Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)</span><span class="sxs-lookup"><span data-stu-id="a6a48-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6a48-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6a48-193">See also</span></span>

- [<span data-ttu-id="a6a48-194">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="a6a48-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="a6a48-195">Abilitare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="a6a48-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="a6a48-196">Valutare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="a6a48-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
