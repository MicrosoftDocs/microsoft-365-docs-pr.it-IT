---
title: Microsoft Defender Antivirus su Windows Server
description: Scopri come abilitare e configurare Microsoft Defender Antivirus in Windows Server 2016 e Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269493"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="38c81-104">Microsoft Defender Antivirus su Windows Server</span><span class="sxs-lookup"><span data-stu-id="38c81-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38c81-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="38c81-105">**Applies to:**</span></span>

- [<span data-ttu-id="38c81-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="38c81-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="38c81-107">Microsoft Defender Antivirus è disponibile nelle seguenti edizioni/versioni di Windows Server:</span><span class="sxs-lookup"><span data-stu-id="38c81-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="38c81-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38c81-108">Windows Server 2019</span></span>
- <span data-ttu-id="38c81-109">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="38c81-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="38c81-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="38c81-110">Windows Server 2016.</span></span> 

<span data-ttu-id="38c81-111">In alcuni casi, Microsoft Defender Antivirus viene definito *Endpoint Protection;* tuttavia, il motore di protezione è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="38c81-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="38c81-112">Sebbene le funzionalità, la configurazione e la gestione siano in gran parte le stesse per [Microsoft Defender Antivirus in Windows 10,](microsoft-defender-antivirus-in-windows-10.md)esistono alcune differenze chiave in Windows Server:</span><span class="sxs-lookup"><span data-stu-id="38c81-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="38c81-113">In Windows Server, [le esclusioni automatiche](configure-server-exclusions-microsoft-defender-antivirus.md) vengono applicate in base al ruolo del server definito.</span><span class="sxs-lookup"><span data-stu-id="38c81-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="38c81-114">In Windows Server, se si esegue una soluzione antivirus/antimalware non Microsoft, Microsoft Defender Antivirus non passa automaticamente alla modalità passiva o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="38c81-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="38c81-115">Tuttavia, puoi impostare Microsoft Defender Antivirus in modalità passiva o disabilitata manualmente.</span><span class="sxs-lookup"><span data-stu-id="38c81-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="38c81-116">Configurazione di Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="38c81-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="38c81-117">Il processo di configurazione ed esecuzione di Microsoft Defender Antivirus su una piattaforma server include diversi passaggi:</span><span class="sxs-lookup"><span data-stu-id="38c81-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="38c81-118">[Abilitare l'interfaccia](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="38c81-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="38c81-119">[Installare Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="38c81-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="38c81-120">[Verificare che Microsoft Defender Antivirus sia in esecuzione](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="38c81-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="38c81-121">[Aggiornare l'antimalware Security intelligence](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="38c81-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="38c81-122">(In base alle esigenze) [Inviare esempi](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="38c81-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="38c81-123">(In base alle esigenze) [Configurare le esclusioni automatiche](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="38c81-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="38c81-124">(Solo se necessario) [Imposta Microsoft Defender Antivirus sulla modalità passiva.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="38c81-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="38c81-125">Abilitare l'interfaccia utente in Windows Server</span><span class="sxs-lookup"><span data-stu-id="38c81-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="38c81-126">Per impostazione predefinita, Microsoft Defender Antivirus è installato e funzionante in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="38c81-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="38c81-127">A volte, l'interfaccia utente (GUI) viene installata per impostazione predefinita, ma l'interfaccia utente grafica non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="38c81-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="38c81-128">Puoi usare PowerShell, Criteri di gruppo o altri metodi per gestire Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="38c81-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="38c81-129">Se l'interfaccia utente grafica non è installata nel server  e si desidera installarla, la procedura guidata Aggiungi ruoli e funzionalità o i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38c81-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="38c81-130">Attivare l'interfaccia utente grafica tramite l'Aggiunta guidata ruoli e funzionalità</span><span class="sxs-lookup"><span data-stu-id="38c81-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="38c81-131">Vedere [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use the Add Roles and Features **Wizard.**</span><span class="sxs-lookup"><span data-stu-id="38c81-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="38c81-132">Quando si arriva al passaggio **Funzionalità** della procedura guidata, in Windows Defender **funzionalità** selezionare l'opzione **GUI per Windows Defender** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="38c81-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="38c81-133">In Windows Server 2016, **l'Aggiunta guidata ruoli e funzionalità** è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Aggiunta guidata ruoli e funzionalità che mostra l'opzione GUI per Windows Defender funzionalità](images/server-add-gui.png)

   <span data-ttu-id="38c81-135">In Windows Server 2019, **l'Aggiunta guidata ruoli e funzionalità** è simile.</span><span class="sxs-lookup"><span data-stu-id="38c81-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="38c81-136">Attivare l'interfaccia utente grafica con PowerShell</span><span class="sxs-lookup"><span data-stu-id="38c81-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="38c81-137">Il cmdlet PowerShell seguente abiliterà l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="38c81-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="38c81-138">Installare Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="38c81-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="38c81-139">Se è necessario installare o reinstallare Microsoft Defender Antivirus in Windows Server, è possibile farlo utilizzando l'Aggiunta guidata ruoli **e** funzionalità o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38c81-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="38c81-140">Usare l'Aggiunta guidata ruoli e funzionalità per installare Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="38c81-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="38c81-141">Fare riferimento [a questo articolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e utilizzare l'Aggiunta guidata ruoli e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="38c81-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="38c81-142">Quando si arriva al passaggio **Funzionalità** della procedura guidata, selezionare l'opzione Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="38c81-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="38c81-143">Selezionare anche **l'opzione GUI per Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="38c81-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="38c81-144">Usare PowerShell per installare Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="38c81-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="38c81-145">Per utilizzare PowerShell per installare Microsoft Defender Antivirus, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="38c81-146">I messaggi di evento per il motore antimalware incluso in Microsoft Defender Antivirus sono disponibili in [Microsoft Defender AV Events.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="38c81-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="38c81-147">Verificare che Microsoft Defender Antivirus sia in esecuzione</span><span class="sxs-lookup"><span data-stu-id="38c81-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="38c81-148">Dopo aver installato Microsoft Defender Antivirus, il passaggio successivo consiste nel verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38c81-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="38c81-149">Nell'endpoint di Windows Server, eseguire il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="38c81-150">Per verificare che la protezione firewall sia attivata, eseguire il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="38c81-151">In alternativa a PowerShell, è possibile utilizzare il prompt dei comandi per verificare che Microsoft Defender Antivirus sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38c81-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="38c81-152">A tale scopo, eseguire il comando seguente da un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="38c81-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="38c81-153">Il `sc query` comando restituisce informazioni sul servizio Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="38c81-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="38c81-154">Quando Microsoft Defender Antivirus è in esecuzione, il `STATE` valore visualizza `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="38c81-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="38c81-155">Aggiornare antimalware Security intelligence</span><span class="sxs-lookup"><span data-stu-id="38c81-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="38c81-156">Per ottenere informazioni aggiornate sulla sicurezza antimalware, è necessario che il servizio Windows Update sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38c81-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="38c81-157">Se usi un servizio di gestione degli aggiornamenti, come Windows Server Update Services (WSUS), assicurati che gli aggiornamenti per Microsoft Defender Antivirus Security intelligence siano approvati per i computer gestiti.</span><span class="sxs-lookup"><span data-stu-id="38c81-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="38c81-158">Per impostazione predefinita, Windows Update non scarica e installa automaticamente gli aggiornamenti in Windows Server 2019 o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="38c81-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="38c81-159">È possibile modificare questa configurazione utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="38c81-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="38c81-160">Metodo</span><span class="sxs-lookup"><span data-stu-id="38c81-160">Method</span></span>  |<span data-ttu-id="38c81-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38c81-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="38c81-162">**Windows Update** nel Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="38c81-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="38c81-163">- **L'installazione automatica** degli aggiornamenti comporta l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="38c81-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="38c81-164">- **Scaricare gli aggiornamenti ma consentirmi** di scegliere se installarli consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38c81-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="38c81-165">**Criteri di gruppo**</span><span class="sxs-lookup"><span data-stu-id="38c81-165">**Group Policy**</span></span>     | <span data-ttu-id="38c81-166">Puoi configurare e gestire Windows Update usando le impostazioni disponibili in Criteri di gruppo nel percorso seguente: **Modelli amministrativi\Componenti di Windows\Windows Update\Configura aggiornamenti automatici**</span><span class="sxs-lookup"><span data-stu-id="38c81-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="38c81-167">Chiave **del Registro di sistema AUOptions**</span><span class="sxs-lookup"><span data-stu-id="38c81-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="38c81-168">I due valori seguenti consentono a Windows Update di scaricare e installare automaticamente gli aggiornamenti di Security Intelligence:</span><span class="sxs-lookup"><span data-stu-id="38c81-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="38c81-169">- **4**  -  **Installare automaticamente gli aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="38c81-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="38c81-170">Questo valore determina l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="38c81-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="38c81-171">- **3**  -  **Scarica gli aggiornamenti ma consentimi di scegliere se installarli**.</span><span class="sxs-lookup"><span data-stu-id="38c81-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="38c81-172">Questo valore consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38c81-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="38c81-173">Per garantire che la protezione da malware sia mantenuta, è consigliabile abilitare i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="38c81-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="38c81-174">Servizio Segnalazione errori Windows</span><span class="sxs-lookup"><span data-stu-id="38c81-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="38c81-175">Servizio Windows Update</span><span class="sxs-lookup"><span data-stu-id="38c81-175">Windows Update service</span></span>

<span data-ttu-id="38c81-176">Nella tabella seguente sono elencati i servizi per Microsoft Defender Antivirus e i servizi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="38c81-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="38c81-177">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="38c81-177">Service Name</span></span>|<span data-ttu-id="38c81-178">Percorso file</span><span class="sxs-lookup"><span data-stu-id="38c81-178">File Location</span></span>|<span data-ttu-id="38c81-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38c81-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="38c81-180">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="38c81-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="38c81-181">Questo è il principale servizio Microsoft Defender Antivirus che deve essere sempre in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38c81-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="38c81-182">Servizio Segnalazione errori Windows (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="38c81-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="38c81-183">Questo servizio invia le segnalazioni errori a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38c81-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="38c81-184">Windows Defender firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="38c81-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="38c81-185">È consigliabile lasciare abilitato il Windows Defender firewall.</span><span class="sxs-lookup"><span data-stu-id="38c81-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="38c81-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="38c81-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="38c81-187">Windows Update è necessario per ottenere gli aggiornamenti di Intelligence per la sicurezza e gli aggiornamenti del motore antimalware</span><span class="sxs-lookup"><span data-stu-id="38c81-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="38c81-188">Inviare esempi</span><span class="sxs-lookup"><span data-stu-id="38c81-188">Submit samples</span></span>

<span data-ttu-id="38c81-189">L'invio di esempio consente a Microsoft di raccogliere campioni di software potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="38c81-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="38c81-190">Per garantire una protezione continua e aggiornata, i ricercatori Microsoft usano questi esempi per analizzare le attività sospette e produrre informazioni aggiornate sulla sicurezza antimalware.</span><span class="sxs-lookup"><span data-stu-id="38c81-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="38c81-191">Raccogliamo file eseguibili di programma, ad esempio .exe file e .dll file.</span><span class="sxs-lookup"><span data-stu-id="38c81-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="38c81-192">Non vengono raccolti file contenenti dati personali, ad esempio documenti di Microsoft Word e file PDF.</span><span class="sxs-lookup"><span data-stu-id="38c81-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="38c81-193">Inviare un file</span><span class="sxs-lookup"><span data-stu-id="38c81-193">Submit a file</span></span>

1. <span data-ttu-id="38c81-194">Consultare la [guida all'invio](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="38c81-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="38c81-195">Visita il [portale di invio di esempio](https://www.microsoft.com/wdsi/filesubmission)e invia il file.</span><span class="sxs-lookup"><span data-stu-id="38c81-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="38c81-196">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="38c81-196">Enable automatic sample submission</span></span>

<span data-ttu-id="38c81-197">Per abilitare l'invio automatico di esempi, avviare una console di Windows PowerShell come amministratore e impostare i dati del valore **SubmitSamplesConsent** in base a una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38c81-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="38c81-198">Impostazione</span><span class="sxs-lookup"><span data-stu-id="38c81-198">Setting</span></span>  |<span data-ttu-id="38c81-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38c81-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="38c81-200">**0**  -  **Chiedi sempre conferma**</span><span class="sxs-lookup"><span data-stu-id="38c81-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="38c81-201">Il Antivirus Microsoft Defender richiede di confermare l'invio di tutti i file necessari.</span><span class="sxs-lookup"><span data-stu-id="38c81-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="38c81-202">Questa è l'impostazione predefinita per Antivirus Microsoft Defender, ma non è consigliata per le installazioni in Windows Server 2016 o 2019 senza gui.</span><span class="sxs-lookup"><span data-stu-id="38c81-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="38c81-203">**1**   -  **Inviare automaticamente campioni sicuri**</span><span class="sxs-lookup"><span data-stu-id="38c81-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="38c81-204">Il Antivirus Microsoft Defender invia tutti i file contrassegnati come "sicuri" e richiede il resto dei file.</span><span class="sxs-lookup"><span data-stu-id="38c81-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="38c81-205">**2**  -  **Non inviare mai**</span><span class="sxs-lookup"><span data-stu-id="38c81-205">**2** - **Never send**</span></span>      |<span data-ttu-id="38c81-206">Il Antivirus Microsoft Defender non richiede conferma e non invia alcun file.</span><span class="sxs-lookup"><span data-stu-id="38c81-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="38c81-207">**3**  -  **Inviare automaticamente tutti i campioni**</span><span class="sxs-lookup"><span data-stu-id="38c81-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="38c81-208">Il Antivirus Microsoft Defender invia tutti i file senza una richiesta di conferma.</span><span class="sxs-lookup"><span data-stu-id="38c81-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="38c81-209">Configurare le esclusioni automatiche</span><span class="sxs-lookup"><span data-stu-id="38c81-209">Configure automatic exclusions</span></span>

<span data-ttu-id="38c81-210">Per garantire sicurezza e prestazioni, alcune esclusioni vengono aggiunte automaticamente in base ai ruoli e alle funzionalità installate quando si usa Antivirus Microsoft Defender in Windows Server 2016 o 2019.</span><span class="sxs-lookup"><span data-stu-id="38c81-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="38c81-211">Vedere [Configure exclusions in Antivirus Microsoft Defender on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="38c81-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="38c81-212">È necessario impostare Antivirus Microsoft Defender modalità passiva?</span><span class="sxs-lookup"><span data-stu-id="38c81-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="38c81-213">Se si utilizza un prodotto antivirus non Microsoft come soluzione antivirus principale in Windows Server, è necessario impostare Antivirus Microsoft Defender modalità passiva o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="38c81-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="38c81-214">In Windows Server, versione 1803 o successiva o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="38c81-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="38c81-215">In Windows Server 2016, Antivirus Microsoft Defender non è supportato insieme a un prodotto antivirus/antimalware non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38c81-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="38c81-216">In questi casi, devi impostare Antivirus Microsoft Defender modalità disabilitata.</span><span class="sxs-lookup"><span data-stu-id="38c81-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="38c81-217">Impostare Antivirus Microsoft Defender modalità passiva tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="38c81-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="38c81-218">Se si utilizza Windows Server, versione 1803 o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender sulla modalità passiva utilizzando il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="38c81-219">Impostare Antivirus Microsoft Defender modalità passiva tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="38c81-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="38c81-220">PROCEDURA NECESSARIA</span><span class="sxs-lookup"><span data-stu-id="38c81-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="38c81-221">Impostare Antivirus Microsoft Defender modalità passiva usando una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="38c81-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="38c81-222">Se si utilizza Windows Server versione 1803 o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender sulla modalità passiva impostando la chiave del Registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="38c81-223">Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="38c81-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="38c81-224">Nome: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="38c81-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="38c81-225">Digitare: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="38c81-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="38c81-226">Valore: `1`</span><span class="sxs-lookup"><span data-stu-id="38c81-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="38c81-227">Disabilitare Antivirus Microsoft Defender tramite la procedura guidata Rimuovi ruoli e funzionalità</span><span class="sxs-lookup"><span data-stu-id="38c81-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="38c81-228">Vedere [Installare o disinstallare ruoli, servizi ruolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)o funzionalità e utilizzare la Rimozione guidata ruoli e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="38c81-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="38c81-229">Quando si arriva al passaggio **Funzionalità** della procedura guidata, deselezionare l'opzione **Windows Defender funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="38c81-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="38c81-230">Se si deseleziona **Windows Defender** nella sezione Funzionalità di **Windows Defender,** verrà richiesto di rimuovere l'opzione gui dell'interfaccia per **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="38c81-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="38c81-231">Antivirus Microsoft Defender verrà comunque eseguita normalmente senza l'interfaccia utente, ma l'interfaccia utente non può essere abilitata se si disabilita la funzionalità di Windows Defender **di** base.</span><span class="sxs-lookup"><span data-stu-id="38c81-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="38c81-232">Disattivare l'Antivirus Microsoft Defender utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="38c81-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="38c81-233">Per disattivare l'Antivirus Microsoft Defender gui, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="38c81-234">Si sta usando Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="38c81-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="38c81-235">Se si utilizza Windows Server 2016 e un prodotto antimalware/antivirus di terze parti non offerto o sviluppato da Microsoft, è necessario disabilitare/disinstallare Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="38c81-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="38c81-236">Non puoi disinstallare l'app Sicurezza di Windows, ma puoi disabilitare l'interfaccia con queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="38c81-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="38c81-237">Il cmdlet PowerShell seguente disinstalla Antivirus Microsoft Defender in Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="38c81-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="38c81-238">Per disabilitare Antivirus Microsoft Defender in Windows Server 2016, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="38c81-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="38c81-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38c81-239">See also</span></span>

- [<span data-ttu-id="38c81-240">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="38c81-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="38c81-241">Antivirus Microsoft Defender compatibilità</span><span class="sxs-lookup"><span data-stu-id="38c81-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
