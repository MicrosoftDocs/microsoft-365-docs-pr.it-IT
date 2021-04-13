---
title: Microsoft Defender Antivirus in Windows Server
description: Scopri come abilitare e configurare Microsoft Defender Antivirus in Windows Server 2016 e Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3415d0caf0192b202cc4f471d5a9bf9051c3878d
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690397"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="21c4f-104">Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="21c4f-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21c4f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="21c4f-105">**Applies to:**</span></span>

- [<span data-ttu-id="21c4f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="21c4f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="21c4f-107">Microsoft Defender Antivirus è disponibile nelle seguenti edizioni/versioni di Windows Server:</span><span class="sxs-lookup"><span data-stu-id="21c4f-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="21c4f-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="21c4f-108">Windows Server 2019</span></span>
- <span data-ttu-id="21c4f-109">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="21c4f-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="21c4f-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="21c4f-110">Windows Server 2016.</span></span> 

<span data-ttu-id="21c4f-111">In alcuni casi, Microsoft Defender Antivirus viene definito *Endpoint Protection;* tuttavia, il motore di protezione è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="21c4f-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="21c4f-112">Sebbene le funzionalità, la configurazione e la gestione siano in gran parte le stesse per [Microsoft Defender Antivirus in Windows 10,](microsoft-defender-antivirus-in-windows-10.md)esistono alcune differenze chiave in Windows Server:</span><span class="sxs-lookup"><span data-stu-id="21c4f-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="21c4f-113">In Windows Server, [le esclusioni automatiche](configure-server-exclusions-microsoft-defender-antivirus.md) vengono applicate in base al ruolo del server definito.</span><span class="sxs-lookup"><span data-stu-id="21c4f-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="21c4f-114">In Windows Server, Microsoft Defender Antivirus non si disabilita automaticamente se si esegue un altro prodotto antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="21c4f-115">Il processo in breve</span><span class="sxs-lookup"><span data-stu-id="21c4f-115">The process at a glance</span></span>

<span data-ttu-id="21c4f-116">Il processo di configurazione ed esecuzione di Microsoft Defender Antivirus su una piattaforma server include diversi passaggi:</span><span class="sxs-lookup"><span data-stu-id="21c4f-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="21c4f-117">[Abilitare l'interfaccia](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="21c4f-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="21c4f-118">[Installare Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="21c4f-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="21c4f-119">[Verificare che Microsoft Defender Antivirus sia in esecuzione](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="21c4f-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="21c4f-120">[Aggiornare l'antimalware Security intelligence](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="21c4f-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="21c4f-121">(In base alle esigenze) [Inviare esempi](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="21c4f-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="21c4f-122">(In base alle esigenze) [Configurare le esclusioni automatiche](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="21c4f-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="21c4f-123">(Solo se necessario) [Imposta Microsoft Defender Antivirus sulla modalità passiva.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="21c4f-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="21c4f-124">Abilitare l'interfaccia utente in Windows Server</span><span class="sxs-lookup"><span data-stu-id="21c4f-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="21c4f-125">Per impostazione predefinita, Microsoft Defender Antivirus è installato e funzionante in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="21c4f-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="21c4f-126">L'interfaccia utente (GUI) è installata per impostazione predefinita in alcuni SKU, ma non è necessaria perché è possibile utilizzare PowerShell o altri metodi per gestire Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="21c4f-127">Se l'interfaccia utente grafica non è installata nel  server, è possibile aggiungerla utilizzando la procedura guidata Aggiungi ruoli e funzionalità o i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21c4f-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="21c4f-128">Attivare l'interfaccia utente grafica tramite l'Aggiunta guidata ruoli e funzionalità</span><span class="sxs-lookup"><span data-stu-id="21c4f-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="21c4f-129">Vedere [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use the Add Roles and Features **Wizard.**</span><span class="sxs-lookup"><span data-stu-id="21c4f-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="21c4f-130">Quando si arriva al passaggio **Funzionalità** della procedura guidata, in Windows Defender **funzionalità** selezionare l'opzione **GUI per Windows Defender** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="21c4f-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="21c4f-131">In Windows Server 2016, **l'Aggiunta guidata ruoli e funzionalità** è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Aggiunta guidata ruoli e funzionalità che mostra l'opzione GUI per Windows Defender funzionalità](images/server-add-gui.png)

   <span data-ttu-id="21c4f-133">In Windows Server 2019, **l'Aggiunta guidata ruoli e funzionalità** è simile.</span><span class="sxs-lookup"><span data-stu-id="21c4f-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="21c4f-134">Attivare l'interfaccia utente grafica con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21c4f-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="21c4f-135">Il cmdlet PowerShell seguente abiliterà l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="21c4f-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="21c4f-136">Installare Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="21c4f-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="21c4f-137">Puoi usare **l'Aggiunta guidata ruoli e funzionalità** o PowerShell per installare Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="21c4f-138">Utilizzo dell'Aggiunta guidata ruoli e funzionalità</span><span class="sxs-lookup"><span data-stu-id="21c4f-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="21c4f-139">Fare riferimento [a questo articolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e utilizzare l'Aggiunta guidata ruoli e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="21c4f-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="21c4f-140">Quando si arriva al passaggio **Funzionalità** della procedura guidata, selezionare l'opzione Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="21c4f-141">Selezionare anche **l'opzione GUI per Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="21c4f-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="21c4f-142">Usare PowerShell</span><span class="sxs-lookup"><span data-stu-id="21c4f-142">Use PowerShell</span></span>

<span data-ttu-id="21c4f-143">Per utilizzare PowerShell per installare Microsoft Defender Antivirus, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="21c4f-144">I messaggi di evento per il motore antimalware incluso in Microsoft Defender Antivirus sono disponibili in [Microsoft Defender AV Events.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="21c4f-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="21c4f-145">Verificare che Microsoft Defender Antivirus sia in esecuzione</span><span class="sxs-lookup"><span data-stu-id="21c4f-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="21c4f-146">Per verificare che Microsoft Defender Antivirus sia in esecuzione nel server, eseguire il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="21c4f-147">Per verificare che la protezione firewall sia attivata, eseguire il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="21c4f-148">In alternativa a PowerShell, è possibile utilizzare il prompt dei comandi per verificare che Microsoft Defender Antivirus sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21c4f-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="21c4f-149">A tale scopo, eseguire il comando seguente da un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="21c4f-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="21c4f-150">Il `sc query` comando restituisce informazioni sul servizio Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="21c4f-151">Quando Microsoft Defender Antivirus è in esecuzione, il `STATE` valore visualizza `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="21c4f-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="21c4f-152">Aggiornare antimalware Security intelligence</span><span class="sxs-lookup"><span data-stu-id="21c4f-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="21c4f-153">Per ottenere informazioni aggiornate sulla sicurezza antimalware, è necessario che il servizio Windows Update sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21c4f-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="21c4f-154">Se usi un servizio di gestione degli aggiornamenti, come Windows Server Update Services (WSUS), assicurati che gli aggiornamenti per Microsoft Defender Antivirus Security intelligence siano approvati per i computer gestiti.</span><span class="sxs-lookup"><span data-stu-id="21c4f-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="21c4f-155">Per impostazione predefinita, Windows Update non scarica e installa automaticamente gli aggiornamenti in Windows Server 2019 o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="21c4f-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="21c4f-156">È possibile modificare questa configurazione utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21c4f-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="21c4f-157">Metodo</span><span class="sxs-lookup"><span data-stu-id="21c4f-157">Method</span></span>  |<span data-ttu-id="21c4f-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21c4f-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="21c4f-159">**Windows Update** nel Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="21c4f-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="21c4f-160">- **L'installazione automatica** degli aggiornamenti comporta l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="21c4f-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="21c4f-161">- **Scaricare gli aggiornamenti ma consentirmi** di scegliere se installarli consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21c4f-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="21c4f-162">**Criteri di gruppo**</span><span class="sxs-lookup"><span data-stu-id="21c4f-162">**Group Policy**</span></span>     | <span data-ttu-id="21c4f-163">Puoi configurare e gestire Windows Update usando le impostazioni disponibili in Criteri di gruppo nel percorso seguente: **Modelli amministrativi\Componenti di Windows\Windows Update\Configura aggiornamenti automatici**</span><span class="sxs-lookup"><span data-stu-id="21c4f-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="21c4f-164">Chiave **del Registro di sistema AUOptions**</span><span class="sxs-lookup"><span data-stu-id="21c4f-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="21c4f-165">I due valori seguenti consentono a Windows Update di scaricare e installare automaticamente gli aggiornamenti di Security Intelligence:</span><span class="sxs-lookup"><span data-stu-id="21c4f-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="21c4f-166">- **4**  -  **Installare automaticamente gli aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="21c4f-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="21c4f-167">Questo valore determina l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="21c4f-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="21c4f-168">- **3**  -  **Scarica gli aggiornamenti ma consentimi di scegliere se installarli**.</span><span class="sxs-lookup"><span data-stu-id="21c4f-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="21c4f-169">Questo valore consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21c4f-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="21c4f-170">Per garantire che la protezione da malware sia mantenuta, è consigliabile abilitare i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21c4f-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="21c4f-171">Servizio Segnalazione errori Windows</span><span class="sxs-lookup"><span data-stu-id="21c4f-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="21c4f-172">Servizio Windows Update</span><span class="sxs-lookup"><span data-stu-id="21c4f-172">Windows Update service</span></span>

<span data-ttu-id="21c4f-173">Nella tabella seguente sono elencati i servizi per Microsoft Defender Antivirus e i servizi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="21c4f-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="21c4f-174">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="21c4f-174">Service Name</span></span>|<span data-ttu-id="21c4f-175">Percorso file</span><span class="sxs-lookup"><span data-stu-id="21c4f-175">File Location</span></span>|<span data-ttu-id="21c4f-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21c4f-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="21c4f-177">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="21c4f-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="21c4f-178">Questo è il principale servizio Microsoft Defender Antivirus che deve essere sempre in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21c4f-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="21c4f-179">Servizio Segnalazione errori Windows (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="21c4f-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="21c4f-180">Questo servizio invia le segnalazioni errori a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21c4f-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="21c4f-181">Windows Defender firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="21c4f-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="21c4f-182">È consigliabile lasciare abilitato il Windows Defender firewall.</span><span class="sxs-lookup"><span data-stu-id="21c4f-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="21c4f-183">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="21c4f-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="21c4f-184">Windows Update è necessario per ottenere gli aggiornamenti di Intelligence per la sicurezza e gli aggiornamenti del motore antimalware</span><span class="sxs-lookup"><span data-stu-id="21c4f-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="21c4f-185">Inviare esempi</span><span class="sxs-lookup"><span data-stu-id="21c4f-185">Submit samples</span></span>

<span data-ttu-id="21c4f-186">L'invio di esempio consente a Microsoft di raccogliere campioni di software potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="21c4f-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="21c4f-187">Per garantire una protezione continua e aggiornata, i ricercatori Microsoft usano questi esempi per analizzare le attività sospette e produrre informazioni aggiornate sulla sicurezza antimalware.</span><span class="sxs-lookup"><span data-stu-id="21c4f-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="21c4f-188">Vengono raccolti i file eseguibili del programma, ad esempio i file exe e dll.</span><span class="sxs-lookup"><span data-stu-id="21c4f-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="21c4f-189">Non vengono raccolti file contenenti dati personali, ad esempio documenti di Microsoft Word e file PDF.</span><span class="sxs-lookup"><span data-stu-id="21c4f-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="21c4f-190">Inviare un file</span><span class="sxs-lookup"><span data-stu-id="21c4f-190">Submit a file</span></span>

1. <span data-ttu-id="21c4f-191">Consultare la [guida all'invio](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="21c4f-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="21c4f-192">Visita il [portale di invio di esempio](https://www.microsoft.com/wdsi/filesubmission)e invia il file.</span><span class="sxs-lookup"><span data-stu-id="21c4f-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="21c4f-193">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="21c4f-193">Enable automatic sample submission</span></span>

<span data-ttu-id="21c4f-194">Per abilitare l'invio automatico di esempi, avviare una console di Windows PowerShell come amministratore e impostare i dati del valore **SubmitSamplesConsent** in base a una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="21c4f-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="21c4f-195">Impostazione</span><span class="sxs-lookup"><span data-stu-id="21c4f-195">Setting</span></span>  |<span data-ttu-id="21c4f-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21c4f-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="21c4f-197">**0**  -  **Chiedi sempre conferma**</span><span class="sxs-lookup"><span data-stu-id="21c4f-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="21c4f-198">Il servizio Microsoft Defender Antivirus richiede di confermare l'invio di tutti i file necessari.</span><span class="sxs-lookup"><span data-stu-id="21c4f-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="21c4f-199">Questa è l'impostazione predefinita per Microsoft Defender Antivirus, ma non è consigliata per le installazioni in Windows Server 2016 o 2019 senza gui.</span><span class="sxs-lookup"><span data-stu-id="21c4f-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="21c4f-200">**1**   -  **Inviare automaticamente campioni sicuri**</span><span class="sxs-lookup"><span data-stu-id="21c4f-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="21c4f-201">Il servizio Microsoft Defender Antivirus invia tutti i file contrassegnati come "sicuri" e richiede il resto dei file.</span><span class="sxs-lookup"><span data-stu-id="21c4f-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="21c4f-202">**2**  -  **Non inviare mai**</span><span class="sxs-lookup"><span data-stu-id="21c4f-202">**2** - **Never send**</span></span>      |<span data-ttu-id="21c4f-203">Il servizio Microsoft Defender Antivirus non richiede conferma e non invia alcun file.</span><span class="sxs-lookup"><span data-stu-id="21c4f-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="21c4f-204">**3**  -  **Inviare automaticamente tutti i campioni**</span><span class="sxs-lookup"><span data-stu-id="21c4f-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="21c4f-205">Il servizio Microsoft Defender Antivirus invia tutti i file senza una richiesta di conferma.</span><span class="sxs-lookup"><span data-stu-id="21c4f-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="21c4f-206">Configurare le esclusioni automatiche</span><span class="sxs-lookup"><span data-stu-id="21c4f-206">Configure automatic exclusions</span></span>

<span data-ttu-id="21c4f-207">Per garantire sicurezza e prestazioni, alcune esclusioni vengono aggiunte automaticamente in base ai ruoli e alle funzionalità installate quando si usa Microsoft Defender Antivirus in Windows Server 2016 o 2019.</span><span class="sxs-lookup"><span data-stu-id="21c4f-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="21c4f-208">Vedi [Configurare le esclusioni in Microsoft Defender Antivirus in Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="21c4f-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="21c4f-209">È necessario impostare Microsoft Defender Antivirus sulla modalità passiva?</span><span class="sxs-lookup"><span data-stu-id="21c4f-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="21c4f-210">Se si utilizza un prodotto antivirus non Microsoft come soluzione antivirus principale, impostare Microsoft Defender Antivirus sulla modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="21c4f-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="21c4f-211">Impostare Microsoft Defender Antivirus sulla modalità passiva usando una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="21c4f-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="21c4f-212">Se si usa Windows Server versione 1803 o Windows Server 2019, è possibile impostare Microsoft Defender Antivirus sulla modalità passiva impostando la chiave del Registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="21c4f-213">Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="21c4f-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="21c4f-214">Nome: `ForcePassiveMode`</span><span class="sxs-lookup"><span data-stu-id="21c4f-214">Name: `ForcePassiveMode`</span></span>
- <span data-ttu-id="21c4f-215">Digitare: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="21c4f-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="21c4f-216">Valore: `1`</span><span class="sxs-lookup"><span data-stu-id="21c4f-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="21c4f-217">Disabilitare Microsoft Defender Antivirus tramite la procedura guidata Rimuovi ruoli e funzionalità</span><span class="sxs-lookup"><span data-stu-id="21c4f-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="21c4f-218">Vedere [Installare o disinstallare ruoli, servizi ruolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)o funzionalità e utilizzare la Rimozione guidata ruoli e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="21c4f-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="21c4f-219">Quando si arriva al passaggio **Funzionalità** della procedura guidata, deselezionare l'opzione **Windows Defender funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="21c4f-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="21c4f-220">Se si deseleziona **Windows Defender** nella sezione Windows Defender **Features,** verrà richiesto di rimuovere l'opzione gui dell'interfaccia per **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="21c4f-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="21c4f-221">Microsoft Defender Antivirus verrà comunque eseguito normalmente senza l'interfaccia utente, ma l'interfaccia utente non può essere abilitata se disabiliti la **funzionalità** Windows Defender di base.</span><span class="sxs-lookup"><span data-stu-id="21c4f-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="21c4f-222">Disattivare l'interfaccia utente di Microsoft Defender Antivirus con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21c4f-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="21c4f-223">Per disattivare l'interfaccia grafica di Microsoft Defender Antivirus, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="21c4f-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="21c4f-224">Si usa Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="21c4f-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="21c4f-225">Se si utilizza Windows Server 2016 e un prodotto antimalware/antivirus di terze parti non offerto o sviluppato da Microsoft, è necessario disabilitare/disinstallare Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="21c4f-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="21c4f-226">Non puoi disinstallare l'app Sicurezza di Windows, ma puoi disabilitare l'interfaccia con queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="21c4f-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="21c4f-227">Il cmdlet PowerShell seguente disinstalla Microsoft Defender Antivirus in Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="21c4f-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="21c4f-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21c4f-228">See also</span></span>

- [<span data-ttu-id="21c4f-229">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="21c4f-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="21c4f-230">Compatibilità con Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="21c4f-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)