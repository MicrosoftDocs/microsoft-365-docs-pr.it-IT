---
title: Migrazione da un gruppo HIPS di terze parti alle regole asr
description: Descrive come affrontare una migrazione da una soluzione HIPS (Host Intrusion Prevention System) di terze parti alle regole di ripristino dell'accesso alternativo.
keywords: Regole di riduzione della superficie di attacco, asr, regole asr, hips, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, Microsoft Defender for Endpoint, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ced969fdd3e8b63136f8bd3f043272e76d99bc5e
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476520"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a><span data-ttu-id="087ad-104">Migrazione da un gruppo HIPS di terze parti alle regole asr</span><span class="sxs-lookup"><span data-stu-id="087ad-104">Migrating from a third-party HIPS to ASR rules</span></span>

<span data-ttu-id="087ad-105">Questo articolo ti aiuta a mappare le regole comuni a Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="087ad-105">This article helps you to map common rules to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="087ad-106">Nella tabella seguente vengono illustrate le domande e gli scenari comuni durante la migrazione da un prodotto HIPS di terze parti alle regole di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="087ad-106">The following table shows common questions and scenarios when migrating from a third-party HIPS product to ASR rules.</span></span>

|<span data-ttu-id="087ad-107">Ambito e azione</span><span class="sxs-lookup"><span data-stu-id="087ad-107">Scope and Action</span></span>|<span data-ttu-id="087ad-108">Processi</span><span class="sxs-lookup"><span data-stu-id="087ad-108">Processes</span></span>|<span data-ttu-id="087ad-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="087ad-109">Operation</span></span>|<span data-ttu-id="087ad-110">Esempi di file/cartelle, chiavi/valori del Registro di sistema, processi, servizi</span><span class="sxs-lookup"><span data-stu-id="087ad-110">Examples of Files/Folders, Registry Keys/Values, Processes, Services</span></span>|<span data-ttu-id="087ad-111">Regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="087ad-111">Attack Surface Reduction rules</span></span>|<span data-ttu-id="087ad-112">Altre funzionalità consigliate</span><span class="sxs-lookup"><span data-stu-id="087ad-112">Other recommended features</span></span>|
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="087ad-113">Tutti i processi: blocca la creazione di file e chiavi del Registro di sistema specifici</span><span class="sxs-lookup"><span data-stu-id="087ad-113">All Processes: Block creation of specific files and registry keys</span></span>||<span data-ttu-id="087ad-114">Creazione file</span><span class="sxs-lookup"><span data-stu-id="087ad-114">File Creation</span></span>|<span data-ttu-id="087ad-115">\*.zepto, \*.odin, \*.locky, \*.jaff, \*.lukitus, \*.wnry, \*.krab</span><span class="sxs-lookup"><span data-stu-id="087ad-115">\*.zepto, \*.odin, \*.locky, \*.jaff, \*.lukitus, \*.wnry, \*.krab</span></span>|<span data-ttu-id="087ad-116">Le regole asr bloccano le tecniche di attacco e non gli Indicatori di compromissione (IOC).</span><span class="sxs-lookup"><span data-stu-id="087ad-116">ASR rules block the attack techniques and not the Indicators of Compromise (IOC).</span></span> <span data-ttu-id="087ad-117">Bloccare un'estensione di file specifica non è sempre utile, perché non impedisce la compromissione di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="087ad-117">Blocking a specific file extension is not always useful, because it does not prevent a device from compromise.</span></span> <span data-ttu-id="087ad-118">Ostacola solo parzialmente un attacco finché gli utenti malintenzionati non creano un nuovo tipo di estensione per il payload.</span><span class="sxs-lookup"><span data-stu-id="087ad-118">It only partially thwarts an  attack until attackers create a new type of extension for the payload.</span></span>|<span data-ttu-id="087ad-119">È consigliabile avere Microsoft Defender AV abilitato, insieme a Cloud Protection e Behavior Analysis.</span><span class="sxs-lookup"><span data-stu-id="087ad-119">Having Microsoft Defender AV enabled, along with Cloud Protection and Behavior Analysis is highly recommended.</span></span> <span data-ttu-id="087ad-120">È consigliabile utilizzare altre misure di prevenzione, ad esempio la regola asr "Usare la protezione avanzata contro ransomware".</span><span class="sxs-lookup"><span data-stu-id="087ad-120">We recommended you use other prevention, such as the ASR rule "Use advanced protection against ransomware".</span></span> <span data-ttu-id="087ad-121">In questo modo si garantisce un maggiore livello di protezione dagli attacchi ransomware.</span><span class="sxs-lookup"><span data-stu-id="087ad-121">This provides a greater level of protection against ransomware attacks.</span></span> <span data-ttu-id="087ad-122">Inoltre, molte di queste chiavi del Registro di sistema vengono monitorate da Microsoft Defender per Endpoint, ad esempio le tecniche ASEP, che attiveranno avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="087ad-122">Furthermore, several of these registry keys are monitored by Microsoft Defender for Endpoint, such as ASEP techniques, which will trigger specific alerts.</span></span> <span data-ttu-id="087ad-123">Le chiavi del Registro di sistema utilizzate richiedono almeno privilegi di amministratore locale o di programma di installazione attendibile per poter essere modificate.</span><span class="sxs-lookup"><span data-stu-id="087ad-123">The registry keys used require a minimum of Local Admin or Trusted Installer privileges to be able to be modified.</span></span> <span data-ttu-id="087ad-124">È consigliabile utilizzare un ambiente bloccato, con almeno account amministrativi o diritti.</span><span class="sxs-lookup"><span data-stu-id="087ad-124">Using a locked down environment, with minimum administrative accounts or rights, is recommended.</span></span> <span data-ttu-id="087ad-125">È possibile abilitare altre configurazioni di sistema, tra cui "Disabilitare SeDebug per i ruoli non necessari" che fanno parte dei consigli di sicurezza più ampi.</span><span class="sxs-lookup"><span data-stu-id="087ad-125">Other system configurations can be enabled, including "Disable SeDebug for non-required roles" that are part of our wider security recommendations.</span></span>|
|<span data-ttu-id="087ad-126">Tutti i processi: blocca la creazione di file e chiavi del Registro di sistema specifici</span><span class="sxs-lookup"><span data-stu-id="087ad-126">All Processes: Block creation of specific files and registry keys</span></span>||<span data-ttu-id="087ad-127">Modifiche al Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="087ad-127">Registry Modifications</span></span>|<span data-ttu-id="087ad-128">\*\Software \* ,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs \* \StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options \* \Debugger,HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit \* \MonitorProcess</span><span class="sxs-lookup"><span data-stu-id="087ad-128">\*\Software\*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\*\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\*\Debugger,HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\*\MonitorProcess</span></span>|<span data-ttu-id="087ad-129">Le regole asr bloccano le tecniche di attacco e non gli Indicatori di compromissione (IOC).</span><span class="sxs-lookup"><span data-stu-id="087ad-129">ASR rules block the attack techniques and not the Indicators of Compromise (IOC).</span></span> <span data-ttu-id="087ad-130">Bloccare un'estensione di file specifica non è sempre utile, perché non impedisce la compromissione di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="087ad-130">Blocking a specific file extension is not always useful, because it does not prevent a device from compromise.</span></span> <span data-ttu-id="087ad-131">Ostacola solo parzialmente un attacco finché gli utenti malintenzionati non creano un nuovo tipo di estensione per il payload.</span><span class="sxs-lookup"><span data-stu-id="087ad-131">It only partially thwarts an  attack until attackers create a new type of extension for the payload.</span></span>|<span data-ttu-id="087ad-132">È consigliabile avere Microsoft Defender AV abilitato, insieme a Cloud Protection e Behavior Analysis.</span><span class="sxs-lookup"><span data-stu-id="087ad-132">Having Microsoft Defender AV enabled, along with Cloud Protection and Behavior Analysis is highly recommended.</span></span> <span data-ttu-id="087ad-133">È consigliabile utilizzare una prevenzione aggiuntiva, ad esempio la regola asr "Usare la protezione avanzata contro ransomware".</span><span class="sxs-lookup"><span data-stu-id="087ad-133">We recommended you use additional prevention, such as the ASR rule "Use advanced protection against ransomware".</span></span> <span data-ttu-id="087ad-134">In questo modo si garantisce un maggiore livello di protezione dagli attacchi ransomware.</span><span class="sxs-lookup"><span data-stu-id="087ad-134">This provides a greater level of protection against ransomware attacks.</span></span> <span data-ttu-id="087ad-135">Inoltre, molte di queste chiavi del Registro di sistema vengono monitorate da Microsoft Defender per Endpoint, ad esempio le tecniche ASEP, che attiveranno avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="087ad-135">Furthermore, several of these registry keys are monitored by Microsoft Defender for Endpoint, such as ASEP techniques, which will trigger specific alerts.</span></span> <span data-ttu-id="087ad-136">Inoltre, le chiavi del Registro di sistema utilizzate richiedono almeno privilegi di amministratore locale o di programma di installazione attendibile per poter essere modificate.</span><span class="sxs-lookup"><span data-stu-id="087ad-136">Plus, the registry keys used require a minimum of Local Admin or Trusted Installer privileges to be able to be modified.</span></span> <span data-ttu-id="087ad-137">È consigliabile utilizzare un ambiente bloccato, con almeno account amministrativi o diritti.</span><span class="sxs-lookup"><span data-stu-id="087ad-137">Using a locked down environment, with minimum administrative accounts or rights, is recommended.</span></span> <span data-ttu-id="087ad-138">È possibile abilitare altre configurazioni di sistema, tra cui "Disabilitare SeDebug per i ruoli non necessari" che fanno parte dei consigli di sicurezza più ampi.</span><span class="sxs-lookup"><span data-stu-id="087ad-138">Other system configurations can be enabled, including "Disable SeDebug for non-required roles" that are part of our wider security recommendations.</span></span>|
|<span data-ttu-id="087ad-139">Programmi non attendibili da USB: impedire l'esecuzione di programmi non attendibili da unità rimovibili</span><span class="sxs-lookup"><span data-stu-id="087ad-139">Untrusted Programs from USB: Block untrusted programs from running from removable drives</span></span>|*|<span data-ttu-id="087ad-140">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-140">Process Execution</span></span>|*|<span data-ttu-id="087ad-141">Le regole asr dispongono di una regola predefinita per impedire l'avvio di programmi non attendibili e non firmati da unità rimovibili: "Blocca processi non attendibili e non firmati eseguiti da USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".</span><span class="sxs-lookup"><span data-stu-id="087ad-141">ASR rules have a built-in rule to prevent the launch of untrusted and unsigned programs from removable drives:  "Block untrusted and unsigned processes that run from USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".</span></span>|<span data-ttu-id="087ad-142">Esplorare ulteriori controlli per i dispositivi USB e altri supporti rimovibili usando Microsoft Defender for Endpoint: Come controllare i dispositivi USB e altri supporti rimovibili [con Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)</span><span class="sxs-lookup"><span data-stu-id="087ad-142">Please explore additional controls for USB devices and other removable media using Microsoft Defender for Endpoint: [How to control USB devices and other removable media using Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune).</span></span> |
|<span data-ttu-id="087ad-143">Mshta: impedire a Mshta di avviare determinati processi figlio</span><span class="sxs-lookup"><span data-stu-id="087ad-143">Mshta: Block Mshta from launching certain child processes</span></span>|<span data-ttu-id="087ad-144">mshta.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-144">mshta.exe</span></span>|<span data-ttu-id="087ad-145">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-145">Process Execution</span></span>|<span data-ttu-id="087ad-146">powershell.exe, cmd.exe, regsvr32.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-146">powershell.exe, cmd.exe, regsvr32.exe</span></span>|<span data-ttu-id="087ad-147">Le regole asr non contengono alcuna regola specifica per impedire ai processi figlio di "mshta.exe".</span><span class="sxs-lookup"><span data-stu-id="087ad-147">ASR rules don't contain any specific rule to prevent child processes from "mshta.exe".</span></span> <span data-ttu-id="087ad-148">Questo controllo rientra nell'ambito di Protezione da exploit o Windows Defender'applicazione.</span><span class="sxs-lookup"><span data-stu-id="087ad-148">This control is within the remit of Exploit Protection or Windows Defender Application Control.</span></span>|<span data-ttu-id="087ad-149">Abilita Windows Defender controllo dell'applicazione per impedire mshta.exe'esecuzione del tutto.</span><span class="sxs-lookup"><span data-stu-id="087ad-149">Enable Windows Defender Application Control to prevent mshta.exe from being executed altogether.</span></span> <span data-ttu-id="087ad-150">Se l'organizzazione richiede "mshta.exe" per le app line-of-business, configura una regola di protezione dagli exploit di Windows Defender specifica per impedire mshta.exe avviare processi figlio.</span><span class="sxs-lookup"><span data-stu-id="087ad-150">If your organization requires "mshta.exe" for line of business apps,  configure a specific Windows Defender Exploit Protection rule, in order to prevent mshta.exe from launching child processes.</span></span>|
|<span data-ttu-id="087ad-151">Outlook: impedire a Outlook di avviare processi figlio</span><span class="sxs-lookup"><span data-stu-id="087ad-151">Outlook: Block Outlook from launching child processes</span></span>|<span data-ttu-id="087ad-152">outlook.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-152">outlook.exe</span></span>|<span data-ttu-id="087ad-153">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-153">Process Execution</span></span>|<span data-ttu-id="087ad-154">powershell.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-154">powershell.exe</span></span>|<span data-ttu-id="087ad-155">Le regole asr hanno una regola predefinita per impedire alle app di comunicazione di Office (Outlook, Skype e Teams) di avviare processi figlio: "Blocca l'applicazione di comunicazione di Office dalla creazione di processi figlio", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".</span><span class="sxs-lookup"><span data-stu-id="087ad-155">ASR rules have a built-in rule to prevent Office communication apps (Outlook, Skype and Teams) from launching child processes: "Block Office communication application from creating child processes", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".</span></span>|<span data-ttu-id="087ad-156">È consigliabile abilitare la modalità linguaggio vincolato di PowerShell per ridurre al minimo la superficie di attacco da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="087ad-156">We recommend enabling PowerShell constrained language mode, in order to minimize the attack surface from PowerShell.</span></span>|
|<span data-ttu-id="087ad-157">Office: impedire alle app di Office di avviare processi figlio e di creare contenuto eseguibile</span><span class="sxs-lookup"><span data-stu-id="087ad-157">Office: Block Office Apps from launching child processes and from creating executable content</span></span>|<span data-ttu-id="087ad-158">winword.exe, powerpnt.exe, excel.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-158">winword.exe, powerpnt.exe, excel.exe</span></span>|<span data-ttu-id="087ad-159">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-159">Process Execution</span></span>|<span data-ttu-id="087ad-160">powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-160">powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe</span></span>|<span data-ttu-id="087ad-161">Le regole asr hanno una regola predefinita per impedire alle app di Office di avviare processi figlio: "Blocca la creazione di processi figlio da parte di tutte le applicazioni di Office", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".</span><span class="sxs-lookup"><span data-stu-id="087ad-161">ASR rules have a built-in rule to prevent Office apps from launching child processes:  "Block all Office applications from creating child processes", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".</span></span>|<span data-ttu-id="087ad-162">N/D</span><span class="sxs-lookup"><span data-stu-id="087ad-162">N/A</span></span>|
|<span data-ttu-id="087ad-163">Office: impedire alle app di Office di avviare processi figlio e di creare contenuto eseguibile</span><span class="sxs-lookup"><span data-stu-id="087ad-163">Office: Block Office Apps from launching child processes and from creating executable content</span></span>|<span data-ttu-id="087ad-164">winword.exe, powerpnt.exe, excel.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-164">winword.exe, powerpnt.exe, excel.exe</span></span>|<span data-ttu-id="087ad-165">Creazione file</span><span class="sxs-lookup"><span data-stu-id="087ad-165">File Creation</span></span>|<span data-ttu-id="087ad-166">C:\Users \* \AppData \* *\* .exe, C:\ProgramData \** \* .exe, C:\ProgramData \* *\* .com, C:\Users \* \* AppData\Local\Temp* \* .com, C:\Users \* *\Downloads \** \* .exe, C:\Users \* \AppData \* *\* .scf, C:\ProgramData \** \* .scf, C:\Users\Public \* .exe, C:\Users \* \Desktop \* \* \* .exe</span><span class="sxs-lookup"><span data-stu-id="087ad-166">C:\Users\*\AppData\**\*.exe, C:\ProgramData\**\*.exe, C:\ProgramData\**\*.com, C:\Users\*AppData\Local\Temp\**\*.com, C:\Users\**\Downloads\**\*.exe, C:\Users\*\AppData\**\*.scf, C:\ProgramData\**\*.scf, C:\Users\Public\*.exe, C:\Users\*\Desktop\*\*\*.exe</span></span>|<span data-ttu-id="087ad-167">N/D</span><span class="sxs-lookup"><span data-stu-id="087ad-167">N/A</span></span>|
|<span data-ttu-id="087ad-168">Wscript: impedire a Wscript di leggere determinati tipi di file</span><span class="sxs-lookup"><span data-stu-id="087ad-168">Wscript: Block Wscript from reading certain types of files</span></span>|<span data-ttu-id="087ad-169">wscript.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-169">wscript.exe</span></span>|<span data-ttu-id="087ad-170">Lettura file</span><span class="sxs-lookup"><span data-stu-id="087ad-170">File Read</span></span>|<span data-ttu-id="087ad-171">C:\Users \* \AppData \* *\* .js*, C:\Users \* \Downloads \* *\* .js*</span><span class="sxs-lookup"><span data-stu-id="087ad-171">C:\Users\*\AppData\**\*.js*, C:\Users\*\Downloads\**\*.js*</span></span>|<span data-ttu-id="087ad-172">A causa di problemi di affidabilità e prestazioni, le regole asr non sono in grado di impedire a un processo specifico di leggere un determinato tipo di file di script.</span><span class="sxs-lookup"><span data-stu-id="087ad-172">Due to reliability and performance issues, ASR rules do not have the capability to prevent a specific process from reading a certain script file type.</span></span> <span data-ttu-id="087ad-173">Abbiamo una regola per impedire vettori di attacco che potrebbero provenire da questi scenari.</span><span class="sxs-lookup"><span data-stu-id="087ad-173">We do have a rule to prevent attack vectors that might originate from these scenarios.</span></span> <span data-ttu-id="087ad-174">Il nome della regola è "Blocca l'avvio del contenuto eseguibile scaricato da JavaScript o VBScript" (GUID "D3E037E1-3EB8-44C8-A917-57927947596 "Blocca l'esecuzione di script potenzialmente offuscati" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC")</span><span class="sxs-lookup"><span data-stu-id="087ad-174">The rule name is "Block JavaScript or VBScript from launching downloaded executable content" (GUID "D3E037E1-3EB8-44C8-A917-57927947596D") and the "Block execution of potentially obfuscated scripts" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC")</span></span>|<span data-ttu-id="087ad-175">Anche se esistono regole ASR specifiche che attenuano determinati vettori di attacco all'interno di questi scenari, è importante ricordare che AV è in grado per impostazione predefinita di esaminare gli script (PowerShell, Windows Script Host, JavaScript, VBScript e altro ancora) in tempo reale, tramite l'interfaccia AMSI (Antimalware Scan Interface).</span><span class="sxs-lookup"><span data-stu-id="087ad-175">Though there are specific ASR rules that mitigate certain attack vectors within these scenarios, it's important to mention that AV is able by default to inspect scripts (PowerShell, Windows Script Host, JavaScript, VBScript, and more) in real time, through the Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="087ad-176">Altre info sono disponibili qui: [Antimalware Scan Interface (AMSI)](https://docs.microsoft.com/windows/win32/amsi/antimalware-scan-interface-portal).</span><span class="sxs-lookup"><span data-stu-id="087ad-176">More info is available here: [Antimalware Scan Interface (AMSI)](https://docs.microsoft.com/windows/win32/amsi/antimalware-scan-interface-portal).</span></span> |
|<span data-ttu-id="087ad-177">Adobe Acrobat: bloccare l'avvio dei processi figlio</span><span class="sxs-lookup"><span data-stu-id="087ad-177">Adobe Acrobat: Block launch of child processes</span></span>|<span data-ttu-id="087ad-178">AcroRd32.exe, Acrobat.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-178">AcroRd32.exe, Acrobat.exe</span></span>|<span data-ttu-id="087ad-179">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-179">Process Execution</span></span>|<span data-ttu-id="087ad-180">cmd.exe, powershell.exe, wscript.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-180">cmd.exe, powershell.exe, wscript.exe</span></span>|<span data-ttu-id="087ad-181">Le regole asr consentono di bloccare l'avvio dei processi figlio da parte di Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="087ad-181">ASR rules allow blocking Adobe Reader from launching child processes.</span></span> <span data-ttu-id="087ad-182">Il nome della regola è "Block Adobe Reader from creating child processes", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".</span><span class="sxs-lookup"><span data-stu-id="087ad-182">The rule name is "Block Adobe Reader from creating child processes", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".</span></span>|<span data-ttu-id="087ad-183">N/D</span><span class="sxs-lookup"><span data-stu-id="087ad-183">N/A</span></span>|
|<span data-ttu-id="087ad-184">CertUtil: bloccare il download o la creazione di contenuto eseguibile</span><span class="sxs-lookup"><span data-stu-id="087ad-184">CertUtil: Block download or creation of executable content</span></span>|<span data-ttu-id="087ad-185">certutil.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-185">certutil.exe</span></span>|<span data-ttu-id="087ad-186">Creazione file</span><span class="sxs-lookup"><span data-stu-id="087ad-186">File Creation</span></span>|<span data-ttu-id="087ad-187">\*.exe</span><span class="sxs-lookup"><span data-stu-id="087ad-187">\*.exe</span></span>|<span data-ttu-id="087ad-188">Le regole asr non supportano questi scenari perché fanno parte della protezione di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="087ad-188">ASR rules don't support these scenarios because they're part of Microsoft Defender Antivirus protection.</span></span>|<span data-ttu-id="087ad-189">Microsoft Defender AV impedisce a CertUtil di creare o scaricare contenuto eseguibile.</span><span class="sxs-lookup"><span data-stu-id="087ad-189">Microsoft Defender AV prevents CertUtil from creating or downloading executable content.</span></span>|
|<span data-ttu-id="087ad-190">Tutti i processi: impedire ai processi di arrestare i componenti critici del sistema</span><span class="sxs-lookup"><span data-stu-id="087ad-190">All Processes: Block processes from stopping critical System components</span></span>|*|<span data-ttu-id="087ad-191">Terminazione processo</span><span class="sxs-lookup"><span data-stu-id="087ad-191">Process Termination</span></span>|<span data-ttu-id="087ad-192">MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe\*, services.exe, csrss.exe, smss.exe, wininit.exe e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="087ad-192">MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe\*, services.exe, csrss.exe, smss.exe, wininit.exe, and more.</span></span>|<span data-ttu-id="087ad-193">Le regole asr non supportano questi scenari perché sono protette con le protezioni di sicurezza predefinite di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="087ad-193">ASR rules don't support these scenarios because they're protected with Windows 10 built-in security protections.</span></span>|<span data-ttu-id="087ad-194">ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light e System Guard.</span><span class="sxs-lookup"><span data-stu-id="087ad-194">ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light, and System Guard.</span></span>|
|<span data-ttu-id="087ad-195">Processi specifici: blocca il tentativo di processo di avvio specifico</span><span class="sxs-lookup"><span data-stu-id="087ad-195">Specific Processes: Block specific launch Process Attempt</span></span>|<span data-ttu-id="087ad-196">"Assegnare un nome al processo"</span><span class="sxs-lookup"><span data-stu-id="087ad-196">"Name your Process"</span></span>|<span data-ttu-id="087ad-197">Esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="087ad-197">Process Execution</span></span>|<span data-ttu-id="087ad-198">tor.exe, bittorrent.exe, cmd.exe, powershell.exe e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="087ad-198">tor.exe, bittorrent.exe, cmd.exe, powershell.exe, and more.</span></span>|<span data-ttu-id="087ad-199">Nel complesso, le regole asr non sono progettate per funzionare come application manager.</span><span class="sxs-lookup"><span data-stu-id="087ad-199">Overall, ASR rules aren't designed to function as an Application manager.</span></span>|<span data-ttu-id="087ad-200">Per impedire agli utenti di avviare processi o programmi specifici, è consigliabile utilizzare Windows Defender Application Control.</span><span class="sxs-lookup"><span data-stu-id="087ad-200">To prevent users from launching specific processes or programs, the recommendation would be to use Windows Defender Application Control.</span></span> <span data-ttu-id="087ad-201">Microsoft Defender for Endpoint File and Cert indicators, può essere usato in uno scenario di risposta a eventi imprevisti (non deve essere visto come un meccanismo di controllo dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="087ad-201">Microsoft Defender for Endpoint File and Cert indicators, can be used in an Incident Response scenario (should not be seen as an application control mechanism).</span></span>|
|<span data-ttu-id="087ad-202">Tutti i processi: blocca le modifiche non autorizzate alle configurazioni av MDATP</span><span class="sxs-lookup"><span data-stu-id="087ad-202">All Processes: Block unauthorized changes to MDATP AV configurations</span></span>|*|<span data-ttu-id="087ad-203">Modifiche al Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="087ad-203">Registry Modifications</span></span>|<span data-ttu-id="087ad-204">HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring e così via.</span><span class="sxs-lookup"><span data-stu-id="087ad-204">HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring, etc.</span></span>|<span data-ttu-id="087ad-205">Le regole asr non coprono questi tipi di scenari perché fanno parte della protezione integrata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="087ad-205">ASR rules don't cover these kinds of scenarios because they are part of the Microsoft Defender for Endpoint built-in protection.</span></span>|<span data-ttu-id="087ad-206">Tamper Protection (consenso esplicito, gestito da Intune) impedisce modifiche non autorizzate alle chiavi del Registro di sistema DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring e DisableIOAVProtection (e altro ancora).</span><span class="sxs-lookup"><span data-stu-id="087ad-206">Tamper Protection (opt-in, managed from Intune) prevents unauthorized changes to DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring and DisableIOAVProtection registry keys (and more).</span></span> |



<span data-ttu-id="087ad-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="087ad-207">See also</span></span>

- [<span data-ttu-id="087ad-208">FAQ per la riduzione della superficie d'attacco</span><span class="sxs-lookup"><span data-stu-id="087ad-208">Attack surface reduction FAQ</span></span>](attack-surface-reduction-faq.md)
- [<span data-ttu-id="087ad-209">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="087ad-209">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="087ad-210">Rilevare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="087ad-210">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)