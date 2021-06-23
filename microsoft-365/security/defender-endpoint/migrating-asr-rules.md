---
title: Migrazione da un gruppo HIPS di terze parti alle regole asr
description: Descrive come affrontare una migrazione da una soluzione HIPS (Host Intrusion Prevention System) di terze parti alle regole di ripristino dell'accesso alternativo.
keywords: Regole di riduzione della superficie di attacco, asr, regole asr, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: fd7c6a217c1bc1ce3b278afb911988b94a6951e0
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062161"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migrazione da un gruppo HIPS di terze parti alle regole asr

Questo articolo ti aiuta a mappare le regole comuni a Microsoft Defender per Endpoint.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Scenari durante la migrazione da un prodotto HIPS di terze parti alle regole di ripristino di emergenza

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Bloccare la creazione di file e chiavi del Registro di sistema specifici

- **Si applica a**- Tutti i processi
- **Operazione**- Creazione file
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Regole di riduzione della superficie** di attacco - Le regole asr bloccano le tecniche di attacco e non gli Indicatori di compromissione (IOC). Il blocco di un'estensione di file specifica non è sempre utile, perché non impedisce a un dispositivo di compromettere. Ostacola solo parzialmente un attacco finché gli utenti malintenzionati non creano un nuovo tipo di estensione per il payload.
- **Altre funzionalità consigliate:** è consigliabile che Microsoft Defender AV sia abilitato, insieme a Cloud Protection e Behavior Analysis. È consigliabile utilizzare altre misure di prevenzione, ad esempio la regola asr "Usare la protezione avanzata contro ransomware". In questo modo si garantisce un maggiore livello di protezione dagli attacchi ransomware. Inoltre, molte di queste chiavi del Registro di sistema vengono monitorate da Microsoft Defender per Endpoint, ad esempio le tecniche ASEP, che attiveranno avvisi specifici. Le chiavi del Registro di sistema utilizzate richiedono almeno privilegi di amministratore locale o di programma di installazione attendibile. È consigliabile utilizzare un ambiente bloccato, con almeno account amministrativi o diritti. È possibile abilitare altre configurazioni di sistema, tra cui "Disabilitare SeDebug per i ruoli non necessari" che fanno parte dei consigli di sicurezza più ampi.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Bloccare la creazione di file e chiavi del Registro di sistema specifici

- **Si applica a**- Tutti i processi
- **Processi**- N/D
- **Operation**- Registry Modifications
- **Esempi di file/cartelle, chiavi/valori del Registro di sistema, processi, servizi** -  \Software,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Regole di riduzione della superficie** di attacco - Le regole asr bloccano le tecniche di attacco e non gli Indicatori di compromissione (IOC). Il blocco di un'estensione di file specifica non è sempre utile, perché non impedisce la compromissione di un dispositivo. Ostacola solo parzialmente un attacco finché gli utenti malintenzionati non creano un nuovo tipo di estensione per il payload.
- **Altre funzionalità consigliate:** è consigliabile che Microsoft Defender AV sia abilitato, insieme a Cloud Protection e Behavior Analysis. Ti consigliamo di usare una prevenzione aggiuntiva, ad esempio la regola asr "Usare la protezione avanzata contro ransomware". In questo modo si garantisce un maggiore livello di protezione dagli attacchi ransomware. Inoltre, molte di queste chiavi del Registro di sistema vengono monitorate da Microsoft Defender per Endpoint, ad esempio le tecniche ASEP, che attiveranno avvisi specifici. Inoltre, le chiavi del Registro di sistema utilizzate richiedono almeno privilegi di amministratore locale o di programma di installazione attendibile. È consigliabile utilizzare un ambiente bloccato, con almeno account amministrativi o diritti. È possibile abilitare altre configurazioni di sistema, tra cui "Disabilitare SeDebug per i ruoli non necessari" che fanno parte dei consigli di sicurezza più ampi.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Impedire l'esecuzione di programmi non attendibili da unità rimovibili

- **Si applica a**- Programmi non attendibili da USB
- **Processi -***
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori del Registro di sistema, processi, servizi:-*
- Regole di riduzione della superficie di attacco **-** Le regole asr dispongono di una regola predefinita per impedire l'avvio di programmi non attendibili e non firmati da unità rimovibili: "Blocca processi non attendibili e non firmati eseguiti da USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Altre funzionalità consigliate-** Esplorare controlli aggiuntivi per i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint: Come controllare i dispositivi USB e altri supporti rimovibili con [Microsoft Defender for Endpoint.](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)

### <a name="block-mshta-from-launching-certain-child-processes"></a>Impedire a Mshta di avviare determinati processi figlio

- **Si applica a**- Mshta
- **Processi -** mshta.exe
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - powershell.exe, cmd.exe, regsvr32.exe
- **Regole di riduzione della superficie** di attacco- Le regole asr non contengono alcuna regola specifica per impedire ai processi figlio di "mshta.exe". Questo controllo rientra nell'ambito di Protezione da exploit o Windows Defender'applicazione.
- **Altre funzionalità consigliate:** abilita Windows Defender controllo dell'applicazione per impedire mshta.exe'esecuzione del tutto. Se l'organizzazione richiede "mshta.exe" per le app line-of-business, configurare una regola di protezione dagli exploit di Windows Defender specifica per impedire mshta.exe avviare processi figlio.

### <a name="block-outlook-from-launching-child-processes"></a>Impedire Outlook l'avvio di processi figlio

- **Si applica a**- Outlook
- **Processi -** outlook.exe
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori del Registro di sistema, processi, servizi**- powershell.exe
- Regole di riduzione della superficie di attacco **-** Le regole asr dispongono di una regola predefinita per impedire alle app di comunicazione Office (Outlook, Skype e Teams) di avviare processi figlio: "Bloccare l'applicazione di comunicazione Office dalla creazione di processi figlio", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Altre funzionalità consigliate:** è consigliabile abilitare la modalità linguaggio vincolato di PowerShell per ridurre al minimo la superficie di attacco da PowerShell.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blocca Office app dall'avvio di processi figlio e dalla creazione di contenuto eseguibile

- **Si applica a**- Office  
- **Processi -** winword.exe, powerpnt.exe, excel.exe
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- Regole di riduzione della superficie di attacco **:** le regole asr dispongono di una regola predefinita per impedire alle app di Office di avviare processi figlio: "Bloccare tutte le applicazioni Office dalla creazione di processi figlio", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Altre funzionalità consigliate**- N/D
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blocca Office app dall'avvio di processi figlio e dalla creazione di contenuto eseguibile

- **Si applica a**- Office
- **Processi -** winword.exe, powerpnt.exe, excel.exe
- **Operazione**- Creazione file
- **Esempi di file/cartelle, chiavi/valori del Registro di sistema, Processi,** servizi - C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop****.exe
- **Regole di riduzione della superficie di** attacco - N/D.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Impedire a Wscript di leggere determinati tipi di file

- **Si applica a**- Wscript
- **Processi -** wscript.exe
- **Operazione**- Lettura file
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Regole di riduzione della superficie** di attacco - A causa di problemi di affidabilità e prestazioni, le regole asr non sono in grado di impedire a un processo specifico di leggere un determinato tipo di file di script. Abbiamo una regola per impedire vettori di attacco che potrebbero provenire da questi scenari. Il nome della regola è "Blocca l'avvio del contenuto eseguibile scaricato da JavaScript o VBScript" (GUID "D3E037E1-3EB8-44C8-A917-57927947596 "Blocca l'esecuzione di script potenzialmente offuscati" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- Altre funzionalità **consigliate-** Anche se esistono regole ASR specifiche che attenuano determinati vettori di attacco all'interno di questi scenari, è importante ricordare che AV è in grado per impostazione predefinita di esaminare gli script (PowerShell, Windows Script Host, JavaScript, VBScript e altro ancora) in tempo reale, tramite Antimalware Scan Interface (AMSI). Altre info sono disponibili qui: [Antimalware Scan Interface (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Bloccare l'avvio dei processi figlio

- **Si applica a**- Adobe Acrobat
- **Processi**- AcroRd32.exe, Acrobat.exe
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - cmd.exe, powershell.exe, wscript.exe
- **Regole di riduzione della superficie di** attacco : le regole asr consentono di bloccare l'avvio di processi figlio da parte di Adobe Reader. Il nome della regola è "Block Adobe Reader from creating child processes", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Altre funzionalità consigliate**- N/D


### <a name="block-download-or-creation-of-executable-content"></a>Bloccare il download o la creazione di contenuto eseguibile

- **Si applica a**- CertUtil: bloccare il download o la creazione di file eseguibili 
- **Processi -** certutil.exe
- **Operazione**- Creazione file
- **Esempi di file/cartelle, chiavi/valori del Registro di sistema, processi, servizi**- *.exe
- **Regole di riduzione della superficie** di attacco: le regole asr non supportano questi scenari perché fanno parte della Antivirus Microsoft Defender protezione.
- **Altre funzionalità consigliate:** Microsoft Defender AV impedisce a CertUtil di creare o scaricare contenuto eseguibile.


### <a name="block-processes-from-stopping-critical-system-components"></a>Impedire ai processi di arrestare i componenti critici del sistema

- **Si applica a**- Tutti i processi
- **Processi -***
- **Operazione**- Terminazione processo
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe e altro ancora.
- **Regole di riduzione della** superficie di attacco: le regole asr non supportano questi scenari perché sono protette con Windows 10 di sicurezza predefinite.
- **Altre funzionalità consigliate:** ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light e System Guard.

### <a name="block-specific-launch-process-attempt"></a>Blocca tentativo di processo di avvio specifico

- **Si applica a**- Processi specifici
- **Processi**- "Assegnare un nome al processo"
- **Operation**- Process Execution
- **Esempi di file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - tor.exe, bittorrent.exe, cmd.exe, powershell.exe e altro ancora
- **Regole di riduzione della superficie di** attacco - Nel complesso, le regole asr non sono progettate per funzionare come application manager.
- **Altre funzionalità consigliate:** per impedire agli utenti di avviare processi o programmi specifici, è consigliabile utilizzare Windows Defender Controllo applicazioni. Microsoft Defender for Endpoint File and Cert indicators, può essere usato in uno scenario di risposta a eventi imprevisti (non deve essere visto come un meccanismo di controllo dell'applicazione).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Bloccare le modifiche non autorizzate alle configurazioni Antivirus Microsoft Defender non autorizzate

- **Si applica a**- Tutti i processi
- **Processi -***
- **Operation**- Registry Modifications
- Esempi di **file/cartelle, chiavi/valori** del Registro di sistema, processi, servizi - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring e così via.
- **Regole di riduzione della** superficie di attacco: le regole asr non coprono questi scenari perché fanno parte della protezione integrata di Microsoft Defender for Endpoint.
- Altre funzionalità **consigliate-** Tamper Protection (consenso esplicito, gestito da Intune) impedisce modifiche non autorizzate alle chiavi del Registro di sistema DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring e DisableIOAVProtection (e altro ancora).

Vedere anche

- [Domande frequenti per la riduzione della superficie di attacco](attack-surface-reduction-faq.yml)
- [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md)
- [Valutare le regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
