---
title: Log di diagnostica
description: Log che potrebbero essere raccolti dai dispositivi durante la risoluzione dei problemi e come vengono archiviati
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272892"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="7c3cb-104">Log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7c3cb-104">Diagnostic logs</span></span>

<span data-ttu-id="7c3cb-105">Quando risolviamo un problema in un dispositivo gestito da Microsoft Managed Desktop, sia che ne sia stato segnalato uno o identificato dal servizio, potrebbe essere necessario raccogliere alcuni log di diagnostica dal dispositivo senza l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="7c3cb-106">Non vengono raccolti contenuti o informazioni generati dall'utente dalle directory degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="7c3cb-107">Raccogliamo solo i dati di diagnostica e di log che riguardano l'integrità e lo stato del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="7c3cb-108">I log raccolti vengono archiviati per 28 giorni e quindi eliminati.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="7c3cb-109">Microsoft elabora tutti i log raccolti da un dispositivo seguendo i nostri [standard di gestione dei dati.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="7c3cb-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="7c3cb-110">Dati raccolti</span><span class="sxs-lookup"><span data-stu-id="7c3cb-110">Data collected</span></span>

<span data-ttu-id="7c3cb-111">Questo elenco include tutte le cartelle, i registri eventi, i file eseguibili o i percorsi del Registro di Microsoft Managed Desktop da cui potrebbero essere raccolti i log di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="7c3cb-112">I dati effettivi raccolti saranno un sottoinsieme di questo elenco e dipendono dal problema identificato.</span><span class="sxs-lookup"><span data-stu-id="7c3cb-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="7c3cb-113">Chiavi del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="7c3cb-113">Registry keys</span></span>

- <span data-ttu-id="7c3cb-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="7c3cb-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="7c3cb-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="7c3cb-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="7c3cb-116">Criteri SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="7c3cb-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="7c3cb-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="7c3cb-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="7c3cb-118">Criteri software HKLM \\ \\ Microsoft \\ \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="7c3cb-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="7c3cb-119">HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="7c3cb-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="7c3cb-120">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="7c3cb-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="7c3cb-121">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="7c3cb-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="7c3cb-122">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="7c3cb-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="7c3cb-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="7c3cb-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="7c3cb-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="7c3cb-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="7c3cb-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="7c3cb-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="7c3cb-126">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="7c3cb-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="7c3cb-127">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="7c3cb-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="7c3cb-128">Installazione di HKLM \\ SYSTEM \\</span><span class="sxs-lookup"><span data-stu-id="7c3cb-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="7c3cb-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="7c3cb-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="7c3cb-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="7c3cb-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="7c3cb-131">HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="7c3cb-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="7c3cb-132">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Authentication \\ \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="7c3cb-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="7c3cb-133">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Impostazioni</span><span class="sxs-lookup"><span data-stu-id="7c3cb-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="7c3cb-134">HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="7c3cb-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="7c3cb-135">Criteri software HKLM \\ \\</span><span class="sxs-lookup"><span data-stu-id="7c3cb-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="7c3cb-136">Criteri SOFTWARE HKLM \\ \\ Microsoft \\ \\ Cryptography Configuration \\ \\ SSL</span><span class="sxs-lookup"><span data-stu-id="7c3cb-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="7c3cb-137">Criteri SOFTWARE HKLM \\ Microsoft Windows Advanced Threat \\ \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="7c3cb-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="7c3cb-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="7c3cb-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="7c3cb-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="7c3cb-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="7c3cb-140">Comandi</span><span class="sxs-lookup"><span data-stu-id="7c3cb-140">Commands</span></span>

- <span data-ttu-id="7c3cb-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="7c3cb-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="7c3cb-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="7c3cb-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="7c3cb-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="7c3cb-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="7c3cb-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="7c3cb-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="7c3cb-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="7c3cb-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="7c3cb-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="7c3cb-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="7c3cb-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="7c3cb-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="7c3cb-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="7c3cb-149">%windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="7c3cb-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="7c3cb-150">%windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="7c3cb-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="7c3cb-151">%windir% \\ system32 \\netsh.exe lan show profiles</span><span class="sxs-lookup"><span data-stu-id="7c3cb-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="7c3cb-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="7c3cb-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="7c3cb-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="7c3cb-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="7c3cb-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="7c3cb-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="7c3cb-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="7c3cb-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="7c3cb-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="7c3cb-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="7c3cb-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="7c3cb-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="7c3cb-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="7c3cb-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="7c3cb-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="7c3cb-159">fltMC.exe</span></span>
- <span data-ttu-id="7c3cb-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="7c3cb-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="7c3cb-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="7c3cb-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="7c3cb-162">Windows PowerShell comandi:</span><span class="sxs-lookup"><span data-stu-id="7c3cb-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="7c3cb-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="7c3cb-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="7c3cb-164">Bundle Get-appxpackage -packagetype</span><span class="sxs-lookup"><span data-stu-id="7c3cb-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="7c3cb-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="7c3cb-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="7c3cb-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="7c3cb-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="7c3cb-167">Get-WmiObject -Class win32 \_ product</span><span class="sxs-lookup"><span data-stu-id="7c3cb-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="7c3cb-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="7c3cb-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="7c3cb-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7c3cb-169">Get-Service</span></span>
    - <span data-ttu-id="7c3cb-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7c3cb-170">Get-Process</span></span>
    - <span data-ttu-id="7c3cb-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="7c3cb-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="7c3cb-172">Registri eventi</span><span class="sxs-lookup"><span data-stu-id="7c3cb-172">Event logs</span></span>

- <span data-ttu-id="7c3cb-173">Applicazione</span><span class="sxs-lookup"><span data-stu-id="7c3cb-173">Application</span></span>
- <span data-ttu-id="7c3cb-174">Microsoft-Windows-AppLocker/EXE e DLL</span><span class="sxs-lookup"><span data-stu-id="7c3cb-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="7c3cb-175">Microsoft-Windows-AppLocker/MSI e script</span><span class="sxs-lookup"><span data-stu-id="7c3cb-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="7c3cb-176">Microsoft-Windows-AppLocker/Distribuzione di app in pacchetto</span><span class="sxs-lookup"><span data-stu-id="7c3cb-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="7c3cb-177">Microsoft-Windows-AppLocker/Esecuzione di app in pacchetto</span><span class="sxs-lookup"><span data-stu-id="7c3cb-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="7c3cb-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span><span class="sxs-lookup"><span data-stu-id="7c3cb-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="7c3cb-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="7c3cb-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="7c3cb-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="7c3cb-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="7c3cb-181">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7c3cb-181">Setup</span></span>
- <span data-ttu-id="7c3cb-182">Sistema</span><span class="sxs-lookup"><span data-stu-id="7c3cb-182">System</span></span>

### <a name="files"></a><span data-ttu-id="7c3cb-183">File</span><span class="sxs-lookup"><span data-stu-id="7c3cb-183">Files</span></span>

- <span data-ttu-id="7c3cb-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="7c3cb-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="7c3cb-185">%ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="7c3cb-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="7c3cb-186">%ProgramData% \\ Supporto Windows Defender Microsoft \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="7c3cb-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="7c3cb-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="7c3cb-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="7c3cb-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="7c3cb-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="7c3cb-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="7c3cb-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="7c3cb-191">%windir% \\ logs \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="7c3cb-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="7c3cb-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="7c3cb-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="7c3cb-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="7c3cb-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="7c3cb-195">Sessioni di manutenzione %windir% \\ \\ \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="7c3cb-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="7c3cb-196">Sessioni di manutenzione %windir% \\ \\ \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="7c3cb-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="7c3cb-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="7c3cb-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="7c3cb-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="7c3cb-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="7c3cb-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="7c3cb-200">%SystemRoot% \\ System32 \\ Winevt \\ Logs</span><span class="sxs-lookup"><span data-stu-id="7c3cb-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="7c3cb-201">%appdata% \\ Microsoft \\ Teams \\ .blog dello stack \\ \* multimediale</span><span class="sxs-lookup"><span data-stu-id="7c3cb-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="7c3cb-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="7c3cb-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="7c3cb-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="7c3cb-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="7c3cb-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="7c3cb-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="7c3cb-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="7c3cb-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>