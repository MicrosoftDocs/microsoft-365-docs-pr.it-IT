---
title: Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base
description: Gestire il modo in cui Microsoft Defender Antivirus riceve la protezione e gli aggiornamenti dei prodotti.
keywords: aggiornamenti, linee di base della sicurezza, protezione, pianificazione degli aggiornamenti, forzare gli aggiornamenti, aggiornamenti mobili, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ae17aa6e2cb0cefd460ef0db0730570af8c84bb8
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995034"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="9ec8a-104">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="9ec8a-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="9ec8a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ec8a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9ec8a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="9ec8a-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9ec8a-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="9ec8a-108">Esistono due tipi di aggiornamenti correlati al mantenimento di Microsoft Defender Antivirus aggiornato:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="9ec8a-109">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ec8a-109">Security intelligence updates</span></span>
- <span data-ttu-id="9ec8a-110">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ec8a-111">Mantenere Microsoft Defender Antivirus aggiornato è fondamentale per garantire ai dispositivi la tecnologia e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="9ec8a-112">Assicurati di aggiornare la protezione antivirus anche se Microsoft Defender Antivirus è in esecuzione in [modalità passiva.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="9ec8a-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security [intelligence per Microsoft Defender Antivirus e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="9ec8a-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ec8a-114">Security intelligence updates</span></span>

<span data-ttu-id="9ec8a-115">Microsoft Defender Antivirus usa la protezione basata sul [cloud](cloud-protection-microsoft-defender-antivirus.md) (denominata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="9ec8a-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="9ec8a-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="9ec8a-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="9ec8a-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="9ec8a-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="9ec8a-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="9ec8a-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="9ec8a-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="9ec8a-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti delle informazioni di [sicurezza per Microsoft Defender Antivirus e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="9ec8a-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="9ec8a-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-124">Product updates</span></span>

<span data-ttu-id="9ec8a-125">Microsoft Defender Antivirus richiede aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della *piattaforma)* e riceverà aggiornamenti delle funzionalità principali insieme alle versioni di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="9ec8a-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="9ec8a-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="9ec8a-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9ec8a-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="9ec8a-129">Il metodo consueto che usi per distribuire gli aggiornamenti di Microsoft e Windows agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="9ec8a-130">Per ulteriori informazioni, vedere [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="9ec8a-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="9ec8a-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="9ec8a-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="9ec8a-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="9ec8a-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="9ec8a-134">All our updates contain</span></span> 
- <span data-ttu-id="9ec8a-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="9ec8a-135">performance improvements;</span></span>
- <span data-ttu-id="9ec8a-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="9ec8a-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="9ec8a-137">miglioramenti all'integrazione (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="9ec8a-138">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="9ec8a-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="9ec8a-140">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="9ec8a-141">&ensp;Piattaforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="9ec8a-142">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="9ec8a-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-144">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-144">What's new</span></span>

- <span data-ttu-id="9ec8a-145">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="9ec8a-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="9ec8a-146">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="9ec8a-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="9ec8a-147">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-148">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-148">Known Issues</span></span>
<span data-ttu-id="9ec8a-149">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="9ec8a-150">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="9ec8a-151">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="9ec8a-152">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="9ec8a-153">&ensp;Piattaforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="9ec8a-154">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="9ec8a-155">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-156">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-156">What's new</span></span>

- <span data-ttu-id="9ec8a-157">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="9ec8a-158">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-159">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-159">Known Issues</span></span>
<span data-ttu-id="9ec8a-160">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="9ec8a-161">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="9ec8a-162">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="9ec8a-163">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="9ec8a-164">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="9ec8a-165">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="9ec8a-166">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-167">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-167">What's new</span></span>

- <span data-ttu-id="9ec8a-168">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="9ec8a-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="9ec8a-169">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="9ec8a-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="9ec8a-170">Miglioramenti delle funzionalità di antitampering nei servizi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9ec8a-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="9ec8a-171">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="9ec8a-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="9ec8a-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="9ec8a-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-173">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-173">Known Issues</span></span>
<span data-ttu-id="9ec8a-174">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="9ec8a-175">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="9ec8a-176">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="9ec8a-177">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="9ec8a-178">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="9ec8a-179">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="9ec8a-180">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="9ec8a-181">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="9ec8a-182">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="9ec8a-183">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-183">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-184">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-184">What's new</span></span>

- <span data-ttu-id="9ec8a-185">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="9ec8a-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-186">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-186">Known Issues</span></span>
<span data-ttu-id="9ec8a-187">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="9ec8a-188">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="9ec8a-189">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="9ec8a-190">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="9ec8a-191">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="9ec8a-192">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="9ec8a-193">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-193">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-194">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-194">What's new</span></span>

- <span data-ttu-id="9ec8a-195">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="9ec8a-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="9ec8a-196">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="9ec8a-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="9ec8a-197">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="9ec8a-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="9ec8a-198">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="9ec8a-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-199">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-199">Known Issues</span></span>

<span data-ttu-id="9ec8a-200">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="9ec8a-201">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="9ec8a-202">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="9ec8a-203">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="9ec8a-204">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="9ec8a-205">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="9ec8a-206">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-207">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-207">What's new</span></span>

- <span data-ttu-id="9ec8a-208">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="9ec8a-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="9ec8a-209">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="9ec8a-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="9ec8a-210">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="9ec8a-211">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-211">New management interfaces for:</span></span>
   - <span data-ttu-id="9ec8a-212">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="9ec8a-212">UDP Inspection</span></span>
   - <span data-ttu-id="9ec8a-213">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="9ec8a-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="9ec8a-214">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="9ec8a-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="9ec8a-215">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="9ec8a-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="9ec8a-216">Analisi migliorata dei moduli VBA di Office</span><span class="sxs-lookup"><span data-stu-id="9ec8a-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-217">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-217">Known Issues</span></span>

<span data-ttu-id="9ec8a-218">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="9ec8a-219">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="9ec8a-220">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="9ec8a-221">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="9ec8a-222">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="9ec8a-223">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="9ec8a-224">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="9ec8a-225">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-225">What's new</span></span>

- <span data-ttu-id="9ec8a-226">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="9ec8a-226">Add more telemetry events</span></span>
- <span data-ttu-id="9ec8a-227">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="9ec8a-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="9ec8a-228">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="9ec8a-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="9ec8a-229">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="9ec8a-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="9ec8a-230">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ec8a-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="9ec8a-231">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="9ec8a-232">Microsoft Defender Antivirus si disattiva automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="9ec8a-233">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-233">Known Issues</span></span>
<span data-ttu-id="9ec8a-234">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-235">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="9ec8a-236">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="9ec8a-237">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="9ec8a-238">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="9ec8a-239">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="9ec8a-240">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-241">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-241">What's new</span></span>

- <span data-ttu-id="9ec8a-242">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="9ec8a-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="9ec8a-243">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="9ec8a-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-244">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-244">Known Issues</span></span>
<span data-ttu-id="9ec8a-245">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-246">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="9ec8a-247">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="9ec8a-248">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="9ec8a-249">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="9ec8a-250">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="9ec8a-251">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-252">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-252">What's new</span></span>

- <span data-ttu-id="9ec8a-253">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="9ec8a-254">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="9ec8a-255">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="9ec8a-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="9ec8a-256">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="9ec8a-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="9ec8a-257">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="9ec8a-257">Fixed registry query</span></span> 
- <span data-ttu-id="9ec8a-258">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="9ec8a-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-259">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-259">Known Issues</span></span>
<span data-ttu-id="9ec8a-260">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-261">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="9ec8a-262">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="9ec8a-263">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="9ec8a-264">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="9ec8a-265">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="9ec8a-266">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-267">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-267">What's new</span></span>

- <span data-ttu-id="9ec8a-268">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="9ec8a-268">Improved logging for scan events</span></span>
- <span data-ttu-id="9ec8a-269">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="9ec8a-270">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="9ec8a-271">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="9ec8a-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="9ec8a-272">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="9ec8a-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="9ec8a-273">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ec8a-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-274">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-274">Known Issues</span></span>
<span data-ttu-id="9ec8a-275">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-276">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="9ec8a-277">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="9ec8a-278">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="9ec8a-279">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="9ec8a-280">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="9ec8a-281">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-282">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-282">What's new</span></span>
- <span data-ttu-id="9ec8a-283">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="9ec8a-283">WDfilter improvements</span></span>
- <span data-ttu-id="9ec8a-284">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="9ec8a-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="9ec8a-285">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="9ec8a-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="9ec8a-286">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="9ec8a-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="9ec8a-287">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="9ec8a-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="9ec8a-288">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="9ec8a-288">UEFI scan capability</span></span>
- <span data-ttu-id="9ec8a-289">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="9ec8a-290">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-290">Known Issues</span></span>
<span data-ttu-id="9ec8a-291">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-292">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="9ec8a-293">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="9ec8a-294">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="9ec8a-295">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="9ec8a-296">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="9ec8a-297">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="9ec8a-298">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-298">What's new</span></span>

- <span data-ttu-id="9ec8a-299">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="9ec8a-300">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ec8a-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="9ec8a-301">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="9ec8a-302">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="9ec8a-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="9ec8a-303">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="9ec8a-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="9ec8a-304">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-304">Known Issues</span></span>
<span data-ttu-id="9ec8a-305">[**Risolto**] Microsoft Defender Antivirus ignora i file durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="9ec8a-306">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="9ec8a-307">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="9ec8a-308">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="9ec8a-309">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="9ec8a-310">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="9ec8a-311">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="9ec8a-312">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="9ec8a-313">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-313">Known Issues</span></span>
<span data-ttu-id="9ec8a-314">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-315">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="9ec8a-316">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="9ec8a-317">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="9ec8a-318">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="9ec8a-319">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="9ec8a-320">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="9ec8a-321">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-321">What's new</span></span>

- <span data-ttu-id="9ec8a-322">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="9ec8a-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="9ec8a-323">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="9ec8a-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="9ec8a-324">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="9ec8a-325">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="9ec8a-326">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="9ec8a-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="9ec8a-327">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-327">Known Issues</span></span>

<span data-ttu-id="9ec8a-328">[**Risolto**] i dispositivi che utilizzano la [modalità standby moderna](/windows-hardware/design/device-experiences/modern-standby) potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="9ec8a-329">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="9ec8a-330">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-330">This update is:</span></span>
> - <span data-ttu-id="9ec8a-331">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="9ec8a-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="9ec8a-332">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="9ec8a-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="9ec8a-333">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="9ec8a-334">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="9ec8a-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="9ec8a-335">è disponibile solo con [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="9ec8a-336">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="9ec8a-337">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="9ec8a-338">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="9ec8a-339">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="9ec8a-340">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="9ec8a-341">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="9ec8a-342">Novità</span><span class="sxs-lookup"><span data-stu-id="9ec8a-342">What's new</span></span>

- <span data-ttu-id="9ec8a-343">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="9ec8a-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="9ec8a-344">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="9ec8a-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="9ec8a-345">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="9ec8a-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="9ec8a-346">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="9ec8a-347">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="9ec8a-347">Known Issues</span></span>
<span data-ttu-id="9ec8a-348">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.10.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="9ec8a-349">Supporto della piattaforma Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9ec8a-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="9ec8a-350">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="9ec8a-351">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="9ec8a-352">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="9ec8a-353">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="9ec8a-354">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="9ec8a-355">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="9ec8a-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="9ec8a-356">\* Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione finale di Windows 10 (vedi Versione della piattaforma inclusa nelle versioni [di Windows 10)](#platform-version-included-with-windows-10-releases)alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="9ec8a-357">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="9ec8a-358">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="9ec8a-359">Versione della piattaforma inclusa nelle versioni di Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ec8a-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="9ec8a-360">La tabella seguente fornisce la piattaforma Microsoft Defender Antivirus e le versioni del motore fornite con le versioni più recenti di Windows 10:</span><span class="sxs-lookup"><span data-stu-id="9ec8a-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="9ec8a-361">Rilascio di Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ec8a-361">Windows 10 release</span></span>  |<span data-ttu-id="9ec8a-362">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="9ec8a-362">Platform version</span></span>  |<span data-ttu-id="9ec8a-363">Versione motore</span><span class="sxs-lookup"><span data-stu-id="9ec8a-363">Engine version</span></span> |<span data-ttu-id="9ec8a-364">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="9ec8a-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="9ec8a-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="9ec8a-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="9ec8a-366">4.18.1909.6</span></span> |<span data-ttu-id="9ec8a-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="9ec8a-367">1.1.17000.2</span></span> | <span data-ttu-id="9ec8a-368">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-369">1909  (19H2)</span></span> |<span data-ttu-id="9ec8a-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="9ec8a-370">4.18.1902.5</span></span> |<span data-ttu-id="9ec8a-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="9ec8a-371">1.1.16700.3</span></span> | <span data-ttu-id="9ec8a-372">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-373">1903  (19H1)</span></span> |<span data-ttu-id="9ec8a-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="9ec8a-374">4.18.1902.5</span></span> |<span data-ttu-id="9ec8a-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="9ec8a-375">1.1.15600.4</span></span> | <span data-ttu-id="9ec8a-376">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-377">1809  (RS5)</span></span> |<span data-ttu-id="9ec8a-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="9ec8a-378">4.18.1807.18075</span></span> |<span data-ttu-id="9ec8a-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="9ec8a-379">1.1.15000.2</span></span> | <span data-ttu-id="9ec8a-380">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-381">1803  (RS4)</span></span> |<span data-ttu-id="9ec8a-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="9ec8a-382">4.13.17134.1</span></span> |<span data-ttu-id="9ec8a-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="9ec8a-383">1.1.14600.4</span></span> | <span data-ttu-id="9ec8a-384">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-385">1709  (RS3)</span></span> |<span data-ttu-id="9ec8a-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="9ec8a-386">4.12.16299.15</span></span> |<span data-ttu-id="9ec8a-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="9ec8a-387">1.1.14104.0</span></span> | <span data-ttu-id="9ec8a-388">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-389">1703  (RS2)</span></span> |<span data-ttu-id="9ec8a-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="9ec8a-390">4.11.15603.2</span></span> |<span data-ttu-id="9ec8a-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="9ec8a-391">1.1.13504.0</span></span> | <span data-ttu-id="9ec8a-392">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="9ec8a-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-393">1607 (RS1)</span></span> |<span data-ttu-id="9ec8a-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="9ec8a-394">4.10.14393.3683</span></span> |<span data-ttu-id="9ec8a-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="9ec8a-395">1.1.12805.0</span></span> | <span data-ttu-id="9ec8a-396">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="9ec8a-397">Per informazioni sulla versione di Windows 10, vedi la scheda delle informazioni sul ciclo [di vita di Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="9ec8a-398">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="9ec8a-399">Ti consigliamo di aggiornare le immagini di installazione di Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 OS con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="9ec8a-400">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="9ec8a-401">Per ulteriori informazioni, vedere [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="9ec8a-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="9ec8a-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="9ec8a-403">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="9ec8a-404">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="9ec8a-405">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="9ec8a-406">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-407">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-407">Fixes</span></span>
- <span data-ttu-id="9ec8a-408">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-409">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-409">Additional information</span></span>
- <span data-ttu-id="9ec8a-410">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="9ec8a-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="9ec8a-412">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="9ec8a-413">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="9ec8a-414">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="9ec8a-415">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-416">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-416">Fixes</span></span>
- <span data-ttu-id="9ec8a-417">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-418">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-418">Additional information</span></span>
- <span data-ttu-id="9ec8a-419">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="9ec8a-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="9ec8a-421">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="9ec8a-422">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="9ec8a-423">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="9ec8a-424">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-425">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-425">Fixes</span></span>
- <span data-ttu-id="9ec8a-426">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-427">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-427">Additional information</span></span>
- <span data-ttu-id="9ec8a-428">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="9ec8a-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="9ec8a-430">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="9ec8a-431">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="9ec8a-432">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="9ec8a-433">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-434">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-434">Fixes</span></span>
- <span data-ttu-id="9ec8a-435">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-436">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-436">Additional information</span></span>
- <span data-ttu-id="9ec8a-437">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="9ec8a-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="9ec8a-439">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="9ec8a-440">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="9ec8a-441">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="9ec8a-442">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-443">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-443">Fixes</span></span>
- <span data-ttu-id="9ec8a-444">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-445">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-445">Additional information</span></span>
- <span data-ttu-id="9ec8a-446">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="9ec8a-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="9ec8a-448">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="9ec8a-449">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="9ec8a-450">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="9ec8a-451">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-452">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-452">Fixes</span></span>
- <span data-ttu-id="9ec8a-453">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-454">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-454">Additional information</span></span>
- <span data-ttu-id="9ec8a-455">Firme aggiornate di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9ec8a-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="9ec8a-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="9ec8a-457">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="9ec8a-458">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="9ec8a-459">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="9ec8a-460">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-461">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-461">Fixes</span></span>
- <span data-ttu-id="9ec8a-462">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-463">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-463">Additional information</span></span>
- <span data-ttu-id="9ec8a-464">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="9ec8a-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="9ec8a-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="9ec8a-466">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="9ec8a-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="9ec8a-467">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="9ec8a-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="9ec8a-468">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="9ec8a-469">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="9ec8a-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="9ec8a-470">Correzioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-470">Fixes</span></span>
- <span data-ttu-id="9ec8a-471">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9ec8a-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="9ec8a-472">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ec8a-472">Additional information</span></span>
- <span data-ttu-id="9ec8a-473">È stato aggiunto il supporto per le immagini di installazione del sistema operativo Windows 10 RS1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="9ec8a-474">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9ec8a-474">Additional resources</span></span>

| <span data-ttu-id="9ec8a-475">Articolo</span><span class="sxs-lookup"><span data-stu-id="9ec8a-475">Article</span></span> | <span data-ttu-id="9ec8a-476">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="9ec8a-477">Immagini di installazione dell'aggiornamento di Microsoft Defender per Windows</span><span class="sxs-lookup"><span data-stu-id="9ec8a-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="9ec8a-478">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="9ec8a-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="9ec8a-479">Ottenere gli aggiornamenti di Microsoft Defender Antivirus per Le immagini di installazione di Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="9ec8a-480">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="9ec8a-481">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="9ec8a-482">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="9ec8a-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="9ec8a-483">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="9ec8a-484">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="9ec8a-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="9ec8a-485">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="9ec8a-486">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="9ec8a-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="9ec8a-487">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="9ec8a-488">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="9ec8a-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="9ec8a-489">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="9ec8a-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
