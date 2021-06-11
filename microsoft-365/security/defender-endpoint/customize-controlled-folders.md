---
title: Personalizzare l’accesso controllato alle cartelle
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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326535"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="c65fb-104">Personalizzare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="c65fb-104">Customize controlled folder access</span></span>

<span data-ttu-id="c65fb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c65fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="c65fb-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c65fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c65fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c65fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="c65fb-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c65fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c65fb-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c65fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c65fb-110">L'accesso controllato alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware.</span><span class="sxs-lookup"><span data-stu-id="c65fb-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="c65fb-111">L'accesso controllato alle cartelle è supportato Windows Server 2019 e Windows 10 client.</span><span class="sxs-lookup"><span data-stu-id="c65fb-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="c65fb-112">In questo articolo viene descritto come personalizzare le funzionalità di accesso controllato alle cartelle e sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c65fb-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="c65fb-113">Proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="c65fb-114">Aggiungere app a cui dovrebbe essere consentito l'accesso alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="c65fb-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="c65fb-115">Consenti ai file eseguibili firmati di accedere alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="c65fb-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="c65fb-116">Personalizzare la notifica</span><span class="sxs-lookup"><span data-stu-id="c65fb-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="c65fb-117">L'accesso controllato alle cartelle monitora le app per le attività rilevate come dannose.</span><span class="sxs-lookup"><span data-stu-id="c65fb-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="c65fb-118">A volte, alle app legittime viene impedito di apportare modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="c65fb-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="c65fb-119">Se l'accesso controllato alle cartelle influisce sulla produttività dell'organizzazione, è consigliabile eseguire questa funzionalità [in](audit-windows-defender.md) modalità di controllo per valutarne completamente l'impatto.</span><span class="sxs-lookup"><span data-stu-id="c65fb-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="c65fb-120">Proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-120">Protect additional folders</span></span>

<span data-ttu-id="c65fb-121">L'accesso controllato alle cartelle si applica a molte cartelle di sistema e posizioni predefinite, incluse cartelle quali **Documenti,** **Immagini** e **Filmati.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="c65fb-122">È possibile aggiungere altre cartelle da proteggere, ma non è possibile rimuovere le cartelle predefinite nell'elenco predefinito.</span><span class="sxs-lookup"><span data-stu-id="c65fb-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="c65fb-123">L'aggiunta di altre cartelle all'accesso controllato alle cartelle può essere utile nei casi in cui non si archiviano file nelle raccolte Windows predefinite o se è stato modificato il percorso predefinito delle raccolte.</span><span class="sxs-lookup"><span data-stu-id="c65fb-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="c65fb-124">È inoltre possibile specificare condivisioni di rete e unità mappate.</span><span class="sxs-lookup"><span data-stu-id="c65fb-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="c65fb-125">Sono supportati variabili di ambiente e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="c65fb-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="c65fb-126">Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c65fb-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c65fb-127">Puoi usare l'app Sicurezza di Windows, Criteri di gruppo, cmdlet di PowerShell o provider di servizi di configurazione per la gestione dei dispositivi mobili per aggiungere e rimuovere cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="c65fb-128">Usare l'app Sicurezza di Windows per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="c65fb-129">Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni o cercando sicurezza *nel* menu Start.</span><span class="sxs-lookup"><span data-stu-id="c65fb-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="c65fb-130">Seleziona **Protezione da & virus** e quindi scorri verso il basso fino alla sezione Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="c65fb-131">Seleziona **Gestisci protezione ransomware** per aprire il riquadro Protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="c65fb-132">Nella sezione **Accesso controllato alle cartelle** selezionare Cartelle **protette**.</span><span class="sxs-lookup"><span data-stu-id="c65fb-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="c65fb-133">Scegliere **Sì** nel prompt **Controllo di accesso utente.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="c65fb-134">Verrà **visualizzato il** riquadro Cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="c65fb-135">Selezionare **Aggiungi una cartella protetta** e seguire le istruzioni per aggiungere cartelle.</span><span class="sxs-lookup"><span data-stu-id="c65fb-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="c65fb-136">Usare Criteri di gruppo per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="c65fb-137">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="c65fb-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="c65fb-138">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c65fb-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="c65fb-139">**Nell'Editor Gestione Criteri di gruppo** passare a Criteri di configurazione **computer**  >    >  **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="c65fb-140">Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Windows Defender accesso controllato alle cartelle di  >    >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="c65fb-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="c65fb-141">**NOTA:** nelle versioni precedenti di Windows, potrebbe essere visualizzato **Windows Defender Antivirus** invece **di Antivirus Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="c65fb-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="c65fb-142">Fare doppio clic **su Cartelle protette configurate** e quindi impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="c65fb-143">Selezionare **Mostra** e specificare ogni cartella che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="c65fb-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="c65fb-144">Distribuisci l'oggetto Criteri di gruppo come di solito.</span><span class="sxs-lookup"><span data-stu-id="c65fb-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="c65fb-145">Usare PowerShell per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="c65fb-146">Digita **PowerShell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**</span><span class="sxs-lookup"><span data-stu-id="c65fb-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="c65fb-147">Digitare il cmdlet PowerShell seguente, sostituendo con il percorso della `<the folder to be protected>` cartella (ad `"c:\apps\"` esempio):</span><span class="sxs-lookup"><span data-stu-id="c65fb-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="c65fb-148">Ripetere il passaggio 2 per ogni cartella che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="c65fb-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="c65fb-149">Le cartelle protette sono visibili nell Sicurezza di Windows app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Finestra di PowerShell con il cmdlet visualizzato":::

> [!IMPORTANT]
> <span data-ttu-id="c65fb-151">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco e non `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="c65fb-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="c65fb-152">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="c65fb-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="c65fb-153">Usare CSP MDM per proteggere cartelle aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c65fb-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="c65fb-154">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="c65fb-155">Consenti ad app specifiche di apportare modifiche alle cartelle controllate</span><span class="sxs-lookup"><span data-stu-id="c65fb-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="c65fb-156">Puoi specificare se determinate app sono sempre considerate sicure e concedere l'accesso in scrittura ai file nelle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="c65fb-157">Consentire le app può essere utile se una determinata app che conosci e considera attendibile viene bloccata dalla funzionalità di accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="c65fb-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c65fb-158">Per impostazione predefinita, Windows app considerate descrittive all'elenco di elementi consentiti.</span><span class="sxs-lookup"><span data-stu-id="c65fb-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="c65fb-159">Tali app aggiunte automaticamente non vengono registrate nell'elenco visualizzato nell'app Sicurezza di Windows o tramite i cmdlet di PowerShell associati.</span><span class="sxs-lookup"><span data-stu-id="c65fb-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="c65fb-160">Non è necessario aggiungere la maggior parte delle app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="c65fb-161">Aggiungi app solo se vengono bloccate e puoi verificarne l'attendibilità.</span><span class="sxs-lookup"><span data-stu-id="c65fb-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="c65fb-162">Quando aggiungi un'app, devi specificare la posizione dell'app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="c65fb-163">Solo l'app in tale percorso sarà autorizzata ad accedere alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="c65fb-164">Se l'app (con lo stesso nome) si trova in un percorso diverso, non verrà aggiunta all'elenco degli elementi consentiti e potrebbe essere bloccata dall'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="c65fb-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="c65fb-165">Un'applicazione o un servizio consentito ha accesso in scrittura a una cartella controllata solo dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="c65fb-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="c65fb-166">Ad esempio, un servizio di aggiornamento continuerà a attivare eventi dopo che è consentito fino a quando non viene arrestato e riavviato.</span><span class="sxs-lookup"><span data-stu-id="c65fb-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="c65fb-167">Usare l'app Windows Defender Sicurezza per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="c65fb-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="c65fb-168">Apri l Sicurezza di Windows app cercando Sicurezza **nel** menu Start.</span><span class="sxs-lookup"><span data-stu-id="c65fb-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c65fb-169">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Gestisci protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="c65fb-170">Nella sezione **Accesso controllato alle cartelle** seleziona Consenti **un'app tramite Accesso controllato alle cartelle**</span><span class="sxs-lookup"><span data-stu-id="c65fb-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="c65fb-171">Seleziona **Aggiungi un'app consentita** e segui le istruzioni per aggiungere app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Pulsante Aggiungi un'app consentita":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="c65fb-173">Usare Criteri di gruppo per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="c65fb-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="c65fb-174">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c65fb-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c65fb-175">Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="c65fb-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c65fb-176">Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Windows Defender accesso controllato alle cartelle di  >    >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="c65fb-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="c65fb-177">Fare doppio clic **sull'impostazione Configura applicazioni consentite** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c65fb-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c65fb-178">Seleziona **Mostra** e immetti ogni app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="c65fb-179">Usare PowerShell per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="c65fb-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="c65fb-180">Digita **PowerShell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**</span><span class="sxs-lookup"><span data-stu-id="c65fb-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c65fb-181">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c65fb-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="c65fb-182">Ad esempio, per aggiungere il *test.exe* eseguibile nella cartella *C:\apps,* il cmdlet sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="c65fb-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="c65fb-183">Continua a usare `Add-MpPreference -ControlledFolderAccessAllowedApplications` per aggiungere altre app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="c65fb-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="c65fb-184">Le app aggiunte utilizzando questo cmdlet verranno visualizzate nell'app Sicurezza di Windows app.</span><span class="sxs-lookup"><span data-stu-id="c65fb-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet di PowerShell per consentire un'app":::

> [!IMPORTANT]
> <span data-ttu-id="c65fb-186">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="c65fb-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c65fb-187">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="c65fb-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="c65fb-188">Usare CSP MDM per consentire app specifiche</span><span class="sxs-lookup"><span data-stu-id="c65fb-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="c65fb-189">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) per consentire alle app di apportare modifiche alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="c65fb-190">Consenti ai file eseguibili firmati di accedere alle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="c65fb-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="c65fb-191">Gli indicatori di file e certificati di Microsoft Defender for Endpoint possono consentire ai file eseguibili firmati di accedere alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="c65fb-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="c65fb-192">Per informazioni dettagliate sull'implementazione, vedere [Create indicators based on certificates](indicator-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c65fb-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="c65fb-193">Ciò non si applica ai motori di script, incluso Powershell</span><span class="sxs-lookup"><span data-stu-id="c65fb-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="c65fb-194">Personalizzare la notifica</span><span class="sxs-lookup"><span data-stu-id="c65fb-194">Customize the notification</span></span>

<span data-ttu-id="c65fb-195">Per altre informazioni sulla personalizzazione della notifica quando viene attivata una regola e blocca un'app o un file, vedi Configurare le notifiche di [avviso in Microsoft Defender for Endpoint.](configure-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="c65fb-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c65fb-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c65fb-196">See also</span></span>

- [<span data-ttu-id="c65fb-197">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="c65fb-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="c65fb-198">Abilitare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="c65fb-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="c65fb-199">Valutare le regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="c65fb-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
