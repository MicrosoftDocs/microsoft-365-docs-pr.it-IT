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
# <a name="diagnostic-logs"></a>Log di diagnostica

Quando risolviamo un problema in un dispositivo gestito da Microsoft Managed Desktop, sia che ne sia stato segnalato uno o identificato dal servizio, potrebbe essere necessario raccogliere alcuni log di diagnostica dal dispositivo senza l'intervento dell'utente. Non vengono raccolti contenuti o informazioni generati dall'utente dalle directory degli utenti. Raccogliamo solo i dati di diagnostica e di log che riguardano l'integrità e lo stato del dispositivo.

I log raccolti vengono archiviati per 28 giorni e quindi eliminati. Microsoft elabora tutti i log raccolti da un dispositivo seguendo i nostri [standard di gestione dei dati.](privacy-personal-data.md)

## <a name="data-collected"></a>Dati raccolti

Questo elenco include tutte le cartelle, i registri eventi, i file eseguibili o i percorsi del Registro di Microsoft Managed Desktop da cui potrebbero essere raccolti i log di diagnostica. I dati effettivi raccolti saranno un sottoinsieme di questo elenco e dipendono dal problema identificato.

### <a name="registry-keys"></a>Chiavi del Registro di sistema

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- Criteri SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- Criteri software HKLM \\ \\ Microsoft \\ \\ WindowsStore
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch
- Installazione di HKLM \\ SYSTEM \\
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Authentication \\ \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Impostazioni
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall
- Criteri software HKLM \\ \\
- Criteri SOFTWARE HKLM \\ \\ Microsoft \\ \\ Cryptography Configuration \\ \\ SSL
- Criteri SOFTWARE HKLM \\ Microsoft Windows Advanced Threat \\ \\ \\ Protection
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Comandi

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall show allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall show global
- %windir% \\ system32 \\netsh.exe lan show profiles
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan show profiles
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell comandi:
    - Get-appxpackage -allusers
    - Bundle Get-appxpackage -packagetype
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ product
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Registri eventi

- Applicazione
- Microsoft-Windows-AppLocker/EXE e DLL
- Microsoft-Windows-AppLocker/MSI e script
- Microsoft-Windows-AppLocker/Distribuzione di app in pacchetto
- Microsoft-Windows-AppLocker/Esecuzione di app in pacchetto
- Microsoft-Windows-Bitlocker/Bitlocker Management
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Configurazione
- Sistema

### <a name="files"></a>File

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*
- %ProgramData% \\ Supporto Windows Defender Microsoft \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- Sessioni di manutenzione %windir% \\ \\ \\ActionList.xml
- Sessioni di manutenzione %windir% \\ \\ \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ Logs\\
- %appdata% \\ Microsoft \\ Teams \\ .blog dello stack \\ \* multimediale
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*