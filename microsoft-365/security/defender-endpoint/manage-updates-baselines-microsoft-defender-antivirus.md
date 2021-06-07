---
title: Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base
description: Gestire il modo Antivirus Microsoft Defender ricevere aggiornamenti di prodotti e protezione.
keywords: aggiornamenti, linee di base della sicurezza, protezione, pianificazione degli aggiornamenti, forzare gli aggiornamenti, aggiornamenti mobili, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/03/2021
ms.openlocfilehash: e67f783552cca5cc36c1563f5e5557796028ea18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772018"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="abe05-104">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="abe05-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="abe05-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="abe05-105">**Applies to:**</span></span>

- [<span data-ttu-id="abe05-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="abe05-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="abe05-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="abe05-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="abe05-108">Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:</span><span class="sxs-lookup"><span data-stu-id="abe05-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="abe05-109">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="abe05-109">Security intelligence updates</span></span>
- <span data-ttu-id="abe05-110">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="abe05-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abe05-111">Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="abe05-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="abe05-112">Assicurarsi di aggiornare la protezione antivirus anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="abe05-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="abe05-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="abe05-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="abe05-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="abe05-114">Security intelligence updates</span></span>

<span data-ttu-id="abe05-115">Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="abe05-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="abe05-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="abe05-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="abe05-117">Antivirus Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="abe05-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="abe05-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="abe05-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="abe05-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="abe05-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="abe05-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="abe05-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="abe05-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="abe05-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="abe05-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="abe05-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="abe05-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="abe05-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="abe05-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="abe05-124">Product updates</span></span>

<span data-ttu-id="abe05-125">Antivirus Microsoft Defender aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della piattaforma *)* e riceveranno aggiornamenti delle funzionalità principali insieme Windows 10 versioni.</span><span class="sxs-lookup"><span data-stu-id="abe05-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="abe05-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="abe05-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="abe05-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="abe05-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="abe05-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="abe05-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="abe05-129">Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="abe05-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="abe05-130">Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="abe05-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="abe05-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="abe05-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="abe05-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="abe05-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="abe05-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="abe05-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="abe05-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="abe05-134">All our updates contain</span></span> 
- <span data-ttu-id="abe05-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="abe05-135">performance improvements;</span></span>
- <span data-ttu-id="abe05-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="abe05-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="abe05-137">miglioramenti all'integrazione (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="abe05-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="abe05-138">Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="abe05-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="abe05-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="abe05-140">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="abe05-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="abe05-141">&ensp;Piattaforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="abe05-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="abe05-142">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="abe05-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="abe05-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-144">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-144">What's new</span></span>
- <span data-ttu-id="abe05-145">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="abe05-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="abe05-146">Rilevamento dei keylogger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="abe05-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-147">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-147">Known Issues</span></span>
<span data-ttu-id="abe05-148">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-149">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="abe05-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="abe05-150">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="abe05-151">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="abe05-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="abe05-152">&ensp;Piattaforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="abe05-153">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="abe05-154">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="abe05-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-155">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-155">What's new</span></span>

- <span data-ttu-id="abe05-156">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="abe05-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="abe05-157">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="abe05-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="abe05-158">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="abe05-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-159">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-159">Known Issues</span></span>
<span data-ttu-id="abe05-160">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="abe05-161">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="abe05-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="abe05-162">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="abe05-163">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="abe05-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="abe05-164">&ensp;Piattaforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="abe05-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="abe05-165">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="abe05-166">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="abe05-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-167">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-167">What's new</span></span>

- <span data-ttu-id="abe05-168">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="abe05-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="abe05-169">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="abe05-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-170">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-170">Known Issues</span></span>
<span data-ttu-id="abe05-171">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="abe05-172">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="abe05-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="abe05-173">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="abe05-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="abe05-174">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="abe05-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="abe05-175">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="abe05-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="abe05-176">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="abe05-177">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="abe05-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="abe05-178">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="abe05-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="abe05-179">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="abe05-180">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-181">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-181">What's new</span></span>

- <span data-ttu-id="abe05-182">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="abe05-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="abe05-183">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="abe05-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="abe05-184">Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi</span><span class="sxs-lookup"><span data-stu-id="abe05-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="abe05-185">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="abe05-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="abe05-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="abe05-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-187">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-187">Known Issues</span></span>
<span data-ttu-id="abe05-188">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="abe05-189">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="abe05-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="abe05-190">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="abe05-191">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="abe05-192">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="abe05-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="abe05-193">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="abe05-194">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-195">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-195">What's new</span></span>

- <span data-ttu-id="abe05-196">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="abe05-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-197">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-197">Known Issues</span></span>
<span data-ttu-id="abe05-198">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="abe05-199">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="abe05-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="abe05-200">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="abe05-201">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="abe05-202">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="abe05-203">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="abe05-204">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-205">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-205">What's new</span></span>

- <span data-ttu-id="abe05-206">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="abe05-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="abe05-207">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="abe05-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="abe05-208">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="abe05-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="abe05-209">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="abe05-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-210">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-210">Known Issues</span></span>

<span data-ttu-id="abe05-211">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="abe05-212">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="abe05-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="abe05-213">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="abe05-214">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="abe05-215">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="abe05-216">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="abe05-217">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-218">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-218">What's new</span></span>

- <span data-ttu-id="abe05-219">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="abe05-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="abe05-220">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="abe05-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="abe05-221">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="abe05-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="abe05-222">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="abe05-222">New management interfaces for:</span></span>
   - <span data-ttu-id="abe05-223">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="abe05-223">UDP Inspection</span></span>
   - <span data-ttu-id="abe05-224">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="abe05-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="abe05-225">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="abe05-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="abe05-226">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="abe05-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="abe05-227">Analisi Office modulo VBA migliorata</span><span class="sxs-lookup"><span data-stu-id="abe05-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-228">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-228">Known Issues</span></span>

<span data-ttu-id="abe05-229">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="abe05-230">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="abe05-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="abe05-231">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="abe05-232">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="abe05-233">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="abe05-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="abe05-234">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="abe05-235">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="abe05-236">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-236">What's new</span></span>

- <span data-ttu-id="abe05-237">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="abe05-237">Add more telemetry events</span></span>
- <span data-ttu-id="abe05-238">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="abe05-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="abe05-239">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="abe05-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="abe05-240">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="abe05-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="abe05-241">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="abe05-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="abe05-242">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="abe05-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="abe05-243">Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="abe05-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="abe05-244">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-244">Known Issues</span></span>
<span data-ttu-id="abe05-245">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-246">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="abe05-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="abe05-247">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="abe05-248">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="abe05-249">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="abe05-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="abe05-250">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="abe05-251">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-252">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-252">What's new</span></span>

- <span data-ttu-id="abe05-253">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="abe05-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="abe05-254">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="abe05-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-255">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-255">Known Issues</span></span>
<span data-ttu-id="abe05-256">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-257">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="abe05-258">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="abe05-259">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="abe05-260">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="abe05-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="abe05-261">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="abe05-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="abe05-262">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-263">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-263">What's new</span></span>

- <span data-ttu-id="abe05-264">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="abe05-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="abe05-265">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="abe05-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="abe05-266">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="abe05-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="abe05-267">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="abe05-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="abe05-268">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="abe05-268">Fixed registry query</span></span> 
- <span data-ttu-id="abe05-269">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="abe05-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-270">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-270">Known Issues</span></span>
<span data-ttu-id="abe05-271">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-272">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="abe05-273">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="abe05-274">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="abe05-275">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="abe05-276">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="abe05-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="abe05-277">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-278">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-278">What's new</span></span>

- <span data-ttu-id="abe05-279">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="abe05-279">Improved logging for scan events</span></span>
- <span data-ttu-id="abe05-280">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="abe05-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="abe05-281">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="abe05-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="abe05-282">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="abe05-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="abe05-283">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="abe05-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="abe05-284">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="abe05-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-285">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-285">Known Issues</span></span>
<span data-ttu-id="abe05-286">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-287">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="abe05-288">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="abe05-289">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="abe05-290">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="abe05-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="abe05-291">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="abe05-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="abe05-292">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-293">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-293">What's new</span></span>
- <span data-ttu-id="abe05-294">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="abe05-294">WDfilter improvements</span></span>
- <span data-ttu-id="abe05-295">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="abe05-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="abe05-296">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="abe05-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="abe05-297">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="abe05-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="abe05-298">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="abe05-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="abe05-299">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="abe05-299">UEFI scan capability</span></span>
- <span data-ttu-id="abe05-300">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="abe05-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="abe05-301">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-301">Known Issues</span></span>
<span data-ttu-id="abe05-302">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-303">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="abe05-304">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="abe05-305">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="abe05-306">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="abe05-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="abe05-307">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="abe05-308">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="abe05-309">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-309">What's new</span></span>

- <span data-ttu-id="abe05-310">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="abe05-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="abe05-311">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="abe05-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="abe05-312">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="abe05-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="abe05-313">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="abe05-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="abe05-314">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="abe05-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="abe05-315">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-315">Known Issues</span></span>
<span data-ttu-id="abe05-316">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="abe05-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="abe05-317">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="abe05-318">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="abe05-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="abe05-319">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="abe05-320">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="abe05-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="abe05-321">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="abe05-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="abe05-322">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="abe05-323">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="abe05-324">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-324">Known Issues</span></span>
<span data-ttu-id="abe05-325">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="abe05-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-326">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="abe05-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="abe05-327">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="abe05-328">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="abe05-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="abe05-329">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="abe05-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="abe05-330">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="abe05-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="abe05-331">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="abe05-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="abe05-332">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-332">What's new</span></span>

- <span data-ttu-id="abe05-333">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="abe05-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="abe05-334">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="abe05-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="abe05-335">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="abe05-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="abe05-336">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="abe05-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="abe05-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="abe05-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="abe05-338">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-338">Known Issues</span></span>

<span data-ttu-id="abe05-339">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="abe05-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="abe05-340">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="abe05-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="abe05-341">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="abe05-341">This update is:</span></span>
> - <span data-ttu-id="abe05-342">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="abe05-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="abe05-343">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="abe05-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="abe05-344">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="abe05-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="abe05-345">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="abe05-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="abe05-346">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="abe05-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="abe05-347">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="abe05-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="abe05-348">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="abe05-349">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="abe05-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="abe05-350">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="abe05-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="abe05-351">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="abe05-352">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="abe05-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="abe05-353">Novità</span><span class="sxs-lookup"><span data-stu-id="abe05-353">What's new</span></span>

- <span data-ttu-id="abe05-354">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="abe05-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="abe05-355">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="abe05-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="abe05-356">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="abe05-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="abe05-357">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="abe05-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="abe05-358">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="abe05-358">Known Issues</span></span>
<span data-ttu-id="abe05-359">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.10.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="abe05-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="abe05-360">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="abe05-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="abe05-361">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="abe05-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="abe05-362">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="abe05-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="abe05-363">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="abe05-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="abe05-364">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="abe05-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="abe05-365">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="abe05-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="abe05-366">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="abe05-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="abe05-367">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="abe05-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="abe05-368">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="abe05-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="abe05-369">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="abe05-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="abe05-370">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="abe05-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="abe05-371">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="abe05-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="abe05-372">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="abe05-372">Windows 10 release</span></span>  |<span data-ttu-id="abe05-373">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="abe05-373">Platform version</span></span>  |<span data-ttu-id="abe05-374">Versione motore</span><span class="sxs-lookup"><span data-stu-id="abe05-374">Engine version</span></span> |<span data-ttu-id="abe05-375">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="abe05-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="abe05-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="abe05-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="abe05-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="abe05-377">4.18.1909.6</span></span> |<span data-ttu-id="abe05-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="abe05-378">1.1.17000.2</span></span> | <span data-ttu-id="abe05-379">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="abe05-380">1909  (19H2)</span></span> |<span data-ttu-id="abe05-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="abe05-381">4.18.1902.5</span></span> |<span data-ttu-id="abe05-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="abe05-382">1.1.16700.3</span></span> | <span data-ttu-id="abe05-383">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="abe05-384">1903  (19H1)</span></span> |<span data-ttu-id="abe05-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="abe05-385">4.18.1902.5</span></span> |<span data-ttu-id="abe05-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="abe05-386">1.1.15600.4</span></span> | <span data-ttu-id="abe05-387">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="abe05-388">1809  (RS5)</span></span> |<span data-ttu-id="abe05-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="abe05-389">4.18.1807.18075</span></span> |<span data-ttu-id="abe05-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="abe05-390">1.1.15000.2</span></span> | <span data-ttu-id="abe05-391">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="abe05-392">1803  (RS4)</span></span> |<span data-ttu-id="abe05-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="abe05-393">4.13.17134.1</span></span> |<span data-ttu-id="abe05-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="abe05-394">1.1.14600.4</span></span> | <span data-ttu-id="abe05-395">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="abe05-396">1709  (RS3)</span></span> |<span data-ttu-id="abe05-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="abe05-397">4.12.16299.15</span></span> |<span data-ttu-id="abe05-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="abe05-398">1.1.14104.0</span></span> | <span data-ttu-id="abe05-399">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="abe05-400">1703  (RS2)</span></span> |<span data-ttu-id="abe05-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="abe05-401">4.11.15603.2</span></span> |<span data-ttu-id="abe05-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="abe05-402">1.1.13504.0</span></span> | <span data-ttu-id="abe05-403">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="abe05-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="abe05-404">1607 (RS1)</span></span> |<span data-ttu-id="abe05-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="abe05-405">4.10.14393.3683</span></span> |<span data-ttu-id="abe05-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="abe05-406">1.1.12805.0</span></span> | <span data-ttu-id="abe05-407">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="abe05-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="abe05-408">Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="abe05-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="abe05-409">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="abe05-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="abe05-410">È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="abe05-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="abe05-411">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="abe05-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="abe05-412">Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="abe05-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="abe05-413">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="abe05-413">1.1.2106.01</span></span></summary>

<span data-ttu-id="abe05-414">&ensp;Versione pacchetto: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-414">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="abe05-415">&ensp;Versione della piattaforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="abe05-415">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="abe05-416">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="abe05-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="abe05-417">&ensp;Versione firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-417">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-418">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-418">Fixes</span></span>
- <span data-ttu-id="abe05-419">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-420">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-420">Additional information</span></span>
- <span data-ttu-id="abe05-421">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-422">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="abe05-422">1.1.2105.01</span></span></summary>

<span data-ttu-id="abe05-423">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-423">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="abe05-424">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="abe05-424">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="abe05-425">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="abe05-425">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="abe05-426">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-426">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-427">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-427">Fixes</span></span>
- <span data-ttu-id="abe05-428">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-429">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-429">Additional information</span></span>
- <span data-ttu-id="abe05-430">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-431">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="abe05-431">1.1.2104.01</span></span></summary>

<span data-ttu-id="abe05-432">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-432">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="abe05-433">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="abe05-433">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="abe05-434">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-434">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="abe05-435">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-435">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-436">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-436">Fixes</span></span>
- <span data-ttu-id="abe05-437">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-438">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-438">Additional information</span></span>
- <span data-ttu-id="abe05-439">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-440">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="abe05-440">1.1.2103.01</span></span></summary>

<span data-ttu-id="abe05-441">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-441">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="abe05-442">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="abe05-442">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="abe05-443">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="abe05-444">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-444">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-445">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-445">Fixes</span></span>
- <span data-ttu-id="abe05-446">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-447">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-447">Additional information</span></span>
- <span data-ttu-id="abe05-448">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-449">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="abe05-449">1.1.2102.03</span></span></summary>

<span data-ttu-id="abe05-450">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="abe05-450">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="abe05-451">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="abe05-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="abe05-452">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-452">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="abe05-453">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-453">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-454">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-454">Fixes</span></span>
- <span data-ttu-id="abe05-455">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-456">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-456">Additional information</span></span>
- <span data-ttu-id="abe05-457">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-458">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="abe05-458">1.1.2101.02</span></span></summary>

<span data-ttu-id="abe05-459">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="abe05-459">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="abe05-460">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="abe05-460">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="abe05-461">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="abe05-461">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="abe05-462">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-462">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-463">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-463">Fixes</span></span>
- <span data-ttu-id="abe05-464">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-465">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-465">Additional information</span></span>
- <span data-ttu-id="abe05-466">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-467">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="abe05-467">1.1.2012.01</span></span></summary>

<span data-ttu-id="abe05-468">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-468">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="abe05-469">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="abe05-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="abe05-470">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="abe05-471">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-471">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-472">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-472">Fixes</span></span>
- <span data-ttu-id="abe05-473">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-474">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-474">Additional information</span></span>
- <span data-ttu-id="abe05-475">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-476">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="abe05-476">1.1.2011.02</span></span></summary>

<span data-ttu-id="abe05-477">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="abe05-477">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="abe05-478">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="abe05-478">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="abe05-479">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="abe05-480">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-480">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-481">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-481">Fixes</span></span>
- <span data-ttu-id="abe05-482">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-483">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-483">Additional information</span></span>
- <span data-ttu-id="abe05-484">Firme Antivirus Microsoft Defender aggiornate</span><span class="sxs-lookup"><span data-stu-id="abe05-484">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-485">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="abe05-485">1.1.2011.01</span></span></summary>

<span data-ttu-id="abe05-486">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="abe05-487">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="abe05-487">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="abe05-488">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-488">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="abe05-489">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-489">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-490">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-490">Fixes</span></span>
- <span data-ttu-id="abe05-491">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-492">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-492">Additional information</span></span>
- <span data-ttu-id="abe05-493">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-493">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="abe05-494">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="abe05-494">1.1.2009.10</span></span></summary>

<span data-ttu-id="abe05-495">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="abe05-495">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="abe05-496">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="abe05-496">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="abe05-497">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="abe05-497">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="abe05-498">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="abe05-498">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="abe05-499">Correzioni</span><span class="sxs-lookup"><span data-stu-id="abe05-499">Fixes</span></span>
- <span data-ttu-id="abe05-500">Nessuno</span><span class="sxs-lookup"><span data-stu-id="abe05-500">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="abe05-501">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-501">Additional information</span></span>
- <span data-ttu-id="abe05-502">È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="abe05-502">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="abe05-503">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="abe05-503">Additional resources</span></span>

| <span data-ttu-id="abe05-504">Articolo</span><span class="sxs-lookup"><span data-stu-id="abe05-504">Article</span></span> | <span data-ttu-id="abe05-505">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abe05-505">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="abe05-506">Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="abe05-506">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="abe05-507">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="abe05-507">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="abe05-508">Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.</span><span class="sxs-lookup"><span data-stu-id="abe05-508">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="abe05-509">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="abe05-509">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="abe05-510">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="abe05-510">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="abe05-511">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="abe05-511">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="abe05-512">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="abe05-512">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="abe05-513">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="abe05-513">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="abe05-514">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="abe05-514">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="abe05-515">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="abe05-515">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="abe05-516">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="abe05-516">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="abe05-517">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="abe05-517">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="abe05-518">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="abe05-518">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
