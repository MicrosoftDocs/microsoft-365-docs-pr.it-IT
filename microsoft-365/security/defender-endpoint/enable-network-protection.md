---
title: Attivare la protezione di rete
description: Abilitare la protezione di rete con Criteri di gruppo, PowerShell o Gestione dispositivi mobili e Configuration Manager.
keywords: Protezione ANetwork, exploit, sito Web dannoso, ip, dominio, domini, abilitare, attivare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c7a2d943ec1813623065e70330b914a3911d1eb
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768999"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="970a7-104">Attivare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="970a7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="970a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="970a7-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="970a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="970a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="970a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="970a7-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="970a7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="970a7-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="970a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="970a7-110">[La protezione di](network-protection.md) rete consente di impedire ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet.</span><span class="sxs-lookup"><span data-stu-id="970a7-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="970a7-111">Puoi controllare [la protezione di rete](evaluate-network-protection.md) in un ambiente di testing per visualizzare quali app verrebbero bloccate prima di abilitarla.</span><span class="sxs-lookup"><span data-stu-id="970a7-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="970a7-112">Ulteriori informazioni sulle opzioni di configurazione del filtro di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="970a7-113">Verificare se la protezione di rete è abilitata</span><span class="sxs-lookup"><span data-stu-id="970a7-113">Check if network protection is enabled</span></span>

<span data-ttu-id="970a7-114">Controlla se la protezione di rete è stata abilitata in un dispositivo locale usando l'editor del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="970a7-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="970a7-115">Seleziona il **pulsante Start** nella barra delle applicazioni e digita **regedit** per aprire l'editor del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="970a7-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="970a7-116">Scegli **HKEY_LOCAL_MACHINE** dal menu laterale</span><span class="sxs-lookup"><span data-stu-id="970a7-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="970a7-117">Esplorare i menu annidati fino a **Criteri SOFTWARE**  >    >  **Microsoft**  >  **Windows Defender**  >  Windows Defender Protezione  >   di rete di Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="970a7-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="970a7-118">Seleziona **EnableNetworkProtection** per visualizzare lo stato corrente della protezione di rete nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="970a7-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="970a7-119">0 o **Disattivato**</span><span class="sxs-lookup"><span data-stu-id="970a7-119">0, or **Off**</span></span>
    * <span data-ttu-id="970a7-120">1 o **Su**</span><span class="sxs-lookup"><span data-stu-id="970a7-120">1, or **On**</span></span>
    * <span data-ttu-id="970a7-121">2 o **Modalità di** controllo</span><span class="sxs-lookup"><span data-stu-id="970a7-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="970a7-123">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-123">Enable network protection</span></span>

<span data-ttu-id="970a7-124">Abilitare la protezione di rete utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="970a7-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="970a7-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="970a7-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="970a7-126">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="970a7-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="970a7-127">Microsoft Endpoint Manager / Intune</span><span class="sxs-lookup"><span data-stu-id="970a7-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="970a7-128">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="970a7-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="970a7-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="970a7-129">PowerShell</span></span>

1. <span data-ttu-id="970a7-130">Digitare **powershell** nel menu Start, fare clic con il pulsante destro del mouse Windows PowerShell **e** selezionare Esegui come **amministratore**</span><span class="sxs-lookup"><span data-stu-id="970a7-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="970a7-131">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="970a7-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="970a7-132">Facoltativo: abilitare la funzionalità in modalità di controllo utilizzando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="970a7-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="970a7-133">Utilizzare `Disabled` invece di o per `AuditMode` `Enabled` disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="970a7-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="970a7-134">Gestione dei dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="970a7-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="970a7-135">Usa [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) per abilitare o disabilitare la protezione di rete o abilitare la modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="970a7-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="970a7-136">Microsoft Endpoint Manager (in precedenza Intune)</span><span class="sxs-lookup"><span data-stu-id="970a7-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="970a7-137">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="970a7-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="970a7-138">Creare o modificare un profilo di [configurazione di Endpoint Protection](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="970a7-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="970a7-139">In **Impostazioni di configurazione** nel flusso del profilo passare a Microsoft Defender Exploit **Guard** Filtro di rete  >    >  **Protezione di rete**  >  **Abilita** o **Controlla solo**</span><span class="sxs-lookup"><span data-stu-id="970a7-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="970a7-140">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="970a7-140">Group Policy</span></span>

<span data-ttu-id="970a7-141">Utilizzare la procedura seguente per abilitare la protezione di rete nei computer aggiunti a un dominio o in un computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="970a7-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="970a7-142">In un computer autonomo, andare a **Start** e quindi digitare e selezionare **Modifica Criteri di gruppo.**</span><span class="sxs-lookup"><span data-stu-id="970a7-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="970a7-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="970a7-143">*-Or-*</span></span>

    <span data-ttu-id="970a7-144">In un computer di gestione di Criteri di gruppo aggiunto al dominio, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="970a7-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="970a7-145">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="970a7-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="970a7-146">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Windows Defender Protezione  >  **di rete di Exploit**  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="970a7-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="970a7-147">Nelle versioni precedenti di Windows, il percorso dei Criteri di gruppo potrebbe essere "Windows Defender Antivirus" anziché "Microsoft Defender Antivirus".</span><span class="sxs-lookup"><span data-stu-id="970a7-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="970a7-148">Fai doppio clic **sull'impostazione Impedisci** a utenti e app di accedere a siti Web pericolosi e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="970a7-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="970a7-149">Nella sezione opzioni è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="970a7-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="970a7-150">**Blocca** - Gli utenti non possono accedere a indirizzi IP e domini dannosi</span><span class="sxs-lookup"><span data-stu-id="970a7-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="970a7-151">**Disabilita (impostazione predefinita):** la funzionalità Protezione di rete non funziona.</span><span class="sxs-lookup"><span data-stu-id="970a7-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="970a7-152">Agli utenti non verrà impedito di accedere a domini dannosi</span><span class="sxs-lookup"><span data-stu-id="970a7-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="970a7-153">**Modalità di** controllo- Se un utente visita un dominio o un indirizzo IP dannoso, un evento verrà registrato nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="970a7-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="970a7-154">Tuttavia, all'utente non verrà impedito di visitare l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="970a7-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="970a7-155">Per abilitare completamente la protezione di rete, devi impostare l'opzione Criteri di gruppo su **Abilitato** e anche selezionare **Blocca** nel menu a discesa delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="970a7-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="970a7-156">Verificare che la protezione di rete sia abilitata in un computer locale utilizzando l'editor del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="970a7-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="970a7-157">Selezionare **Start e** digitare **regedit** per aprire l'editor **del Registro di sistema.**</span><span class="sxs-lookup"><span data-stu-id="970a7-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="970a7-158">Passare a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="970a7-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="970a7-159">Selezionare **EnableNetworkProtection e** confermare il valore:</span><span class="sxs-lookup"><span data-stu-id="970a7-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="970a7-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="970a7-160">0=Off</span></span>
   * <span data-ttu-id="970a7-161">1=On</span><span class="sxs-lookup"><span data-stu-id="970a7-161">1=On</span></span>
   * <span data-ttu-id="970a7-162">2=Controllo</span><span class="sxs-lookup"><span data-stu-id="970a7-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="970a7-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970a7-163">See also</span></span>

* [<span data-ttu-id="970a7-164">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="970a7-165">Valutare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="970a7-166">Risolvere i problemi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="970a7-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
