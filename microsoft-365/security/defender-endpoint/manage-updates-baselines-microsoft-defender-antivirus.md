---
title: Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base
description: Gestire il modo in cui Microsoft Defender Antivirus riceve la protezione e gli aggiornamenti dei prodotti.
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
ms.date: 05/06/2021
ms.openlocfilehash: 22a173d39c3ab8d1afd91a33b05e02e58da24aaa
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274557"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ddd3f-104">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="ddd3f-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ddd3f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-105">**Applies to:**</span></span>

- [<span data-ttu-id="ddd3f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ddd3f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ddd3f-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ddd3f-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ddd3f-108">Esistono due tipi di aggiornamenti correlati al mantenimento di Microsoft Defender Antivirus aggiornato:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ddd3f-109">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="ddd3f-109">Security intelligence updates</span></span>
- <span data-ttu-id="ddd3f-110">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddd3f-111">Mantenere Microsoft Defender Antivirus aggiornato è fondamentale per garantire ai dispositivi la tecnologia e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="ddd3f-112">Assicurati di aggiornare la protezione antivirus anche se Microsoft Defender Antivirus è in esecuzione in [modalità passiva.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="ddd3f-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security [intelligence per Microsoft Defender Antivirus e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ddd3f-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="ddd3f-114">Security intelligence updates</span></span>

<span data-ttu-id="ddd3f-115">Microsoft Defender Antivirus usa la protezione basata sul [cloud](cloud-protection-microsoft-defender-antivirus.md) (denominata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ddd3f-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="ddd3f-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="ddd3f-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="ddd3f-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="ddd3f-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ddd3f-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ddd3f-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ddd3f-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ddd3f-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti delle informazioni di [sicurezza per Microsoft Defender Antivirus e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ddd3f-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ddd3f-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-124">Product updates</span></span>

<span data-ttu-id="ddd3f-125">Microsoft Defender Antivirus richiede aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della *piattaforma)* e riceverà aggiornamenti delle funzionalità principali insieme alle versioni di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="ddd3f-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ddd3f-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ddd3f-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ddd3f-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ddd3f-129">Il metodo consueto che usi per distribuire gli aggiornamenti di Microsoft e Windows agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ddd3f-130">Per ulteriori informazioni, vedere [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="ddd3f-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ddd3f-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="ddd3f-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="ddd3f-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ddd3f-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="ddd3f-134">All our updates contain</span></span> 
- <span data-ttu-id="ddd3f-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="ddd3f-135">performance improvements;</span></span>
- <span data-ttu-id="ddd3f-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="ddd3f-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="ddd3f-137">miglioramenti all'integrazione (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ddd3f-138">Aprile-2021 (Piattaforma: 4.19.2104.9| Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ddd3f-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ddd3f-140">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ddd3f-141">&ensp;Piattaforma: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="ddd3f-142">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ddd3f-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-144">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-144">What's new</span></span>
- <span data-ttu-id="ddd3f-145">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="ddd3f-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ddd3f-146">Rilevamento dei keylogger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="ddd3f-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-147">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-147">Known Issues</span></span>
<span data-ttu-id="ddd3f-148">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-149">Marzo-2021 (Piattaforma: 4.19.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ddd3f-150">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ddd3f-151">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ddd3f-152">&ensp;Piattaforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="ddd3f-153">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ddd3f-154">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-155">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-155">What's new</span></span>

- <span data-ttu-id="ddd3f-156">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="ddd3f-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ddd3f-157">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="ddd3f-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ddd3f-158">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-159">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-159">Known Issues</span></span>
<span data-ttu-id="ddd3f-160">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ddd3f-161">Febbraio-2021 (Piattaforma: 4.19.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ddd3f-162">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ddd3f-163">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ddd3f-164">&ensp;Piattaforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="ddd3f-165">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ddd3f-166">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-167">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-167">What's new</span></span>

- <span data-ttu-id="ddd3f-168">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ddd3f-169">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-170">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-170">Known Issues</span></span>
<span data-ttu-id="ddd3f-171">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ddd3f-172">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ddd3f-173">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ddd3f-174">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="ddd3f-175">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ddd3f-176">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ddd3f-177">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ddd3f-178">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ddd3f-179">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ddd3f-180">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-181">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-181">What's new</span></span>

- <span data-ttu-id="ddd3f-182">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="ddd3f-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ddd3f-183">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="ddd3f-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ddd3f-184">Miglioramenti delle funzionalità di antitampering nei servizi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ddd3f-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ddd3f-185">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="ddd3f-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ddd3f-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="ddd3f-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-187">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-187">Known Issues</span></span>
<span data-ttu-id="ddd3f-188">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ddd3f-189">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ddd3f-190">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ddd3f-191">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ddd3f-192">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ddd3f-193">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ddd3f-194">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-195">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-195">What's new</span></span>

- <span data-ttu-id="ddd3f-196">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="ddd3f-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-197">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-197">Known Issues</span></span>
<span data-ttu-id="ddd3f-198">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ddd3f-199">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ddd3f-200">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ddd3f-201">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ddd3f-202">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ddd3f-203">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ddd3f-204">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-205">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-205">What's new</span></span>

- <span data-ttu-id="ddd3f-206">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="ddd3f-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ddd3f-207">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="ddd3f-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="ddd3f-208">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="ddd3f-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ddd3f-209">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="ddd3f-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-210">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-210">Known Issues</span></span>

<span data-ttu-id="ddd3f-211">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ddd3f-212">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ddd3f-213">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ddd3f-214">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ddd3f-215">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ddd3f-216">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ddd3f-217">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-218">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-218">What's new</span></span>

- <span data-ttu-id="ddd3f-219">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="ddd3f-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ddd3f-220">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="ddd3f-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="ddd3f-221">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ddd3f-222">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-222">New management interfaces for:</span></span>
   - <span data-ttu-id="ddd3f-223">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="ddd3f-223">UDP Inspection</span></span>
   - <span data-ttu-id="ddd3f-224">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="ddd3f-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ddd3f-225">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="ddd3f-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ddd3f-226">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="ddd3f-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ddd3f-227">Analisi migliorata dei moduli VBA di Office</span><span class="sxs-lookup"><span data-stu-id="ddd3f-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-228">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-228">Known Issues</span></span>

<span data-ttu-id="ddd3f-229">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ddd3f-230">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ddd3f-231">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ddd3f-232">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ddd3f-233">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ddd3f-234">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ddd3f-235">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ddd3f-236">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-236">What's new</span></span>

- <span data-ttu-id="ddd3f-237">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="ddd3f-237">Add more telemetry events</span></span>
- <span data-ttu-id="ddd3f-238">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="ddd3f-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="ddd3f-239">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="ddd3f-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ddd3f-240">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="ddd3f-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="ddd3f-241">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddd3f-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ddd3f-242">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ddd3f-243">Microsoft Defender Antivirus si disattiva automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ddd3f-244">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-244">Known Issues</span></span>
<span data-ttu-id="ddd3f-245">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-246">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ddd3f-247">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ddd3f-248">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ddd3f-249">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ddd3f-250">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ddd3f-251">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-252">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-252">What's new</span></span>

- <span data-ttu-id="ddd3f-253">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="ddd3f-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ddd3f-254">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="ddd3f-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-255">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-255">Known Issues</span></span>
<span data-ttu-id="ddd3f-256">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-257">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ddd3f-258">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ddd3f-259">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ddd3f-260">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ddd3f-261">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ddd3f-262">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-263">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-263">What's new</span></span>

- <span data-ttu-id="ddd3f-264">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ddd3f-265">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ddd3f-266">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="ddd3f-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ddd3f-267">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="ddd3f-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ddd3f-268">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="ddd3f-268">Fixed registry query</span></span> 
- <span data-ttu-id="ddd3f-269">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="ddd3f-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-270">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-270">Known Issues</span></span>
<span data-ttu-id="ddd3f-271">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-272">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ddd3f-273">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ddd3f-274">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ddd3f-275">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ddd3f-276">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ddd3f-277">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-278">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-278">What's new</span></span>

- <span data-ttu-id="ddd3f-279">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="ddd3f-279">Improved logging for scan events</span></span>
- <span data-ttu-id="ddd3f-280">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ddd3f-281">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ddd3f-282">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="ddd3f-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ddd3f-283">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="ddd3f-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ddd3f-284">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ddd3f-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-285">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-285">Known Issues</span></span>
<span data-ttu-id="ddd3f-286">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-287">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ddd3f-288">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ddd3f-289">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ddd3f-290">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ddd3f-291">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ddd3f-292">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-293">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-293">What's new</span></span>
- <span data-ttu-id="ddd3f-294">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="ddd3f-294">WDfilter improvements</span></span>
- <span data-ttu-id="ddd3f-295">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="ddd3f-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ddd3f-296">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="ddd3f-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ddd3f-297">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="ddd3f-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ddd3f-298">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="ddd3f-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ddd3f-299">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="ddd3f-299">UEFI scan capability</span></span>
- <span data-ttu-id="ddd3f-300">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ddd3f-301">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-301">Known Issues</span></span>
<span data-ttu-id="ddd3f-302">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-303">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ddd3f-304">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ddd3f-305">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ddd3f-306">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ddd3f-307">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ddd3f-308">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ddd3f-309">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-309">What's new</span></span>

- <span data-ttu-id="ddd3f-310">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ddd3f-311">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ddd3f-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="ddd3f-312">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ddd3f-313">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="ddd3f-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ddd3f-314">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="ddd3f-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ddd3f-315">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-315">Known Issues</span></span>
<span data-ttu-id="ddd3f-316">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ddd3f-317">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ddd3f-318">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ddd3f-319">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ddd3f-320">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ddd3f-321">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ddd3f-322">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ddd3f-323">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ddd3f-324">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-324">Known Issues</span></span>
<span data-ttu-id="ddd3f-325">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-326">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ddd3f-327">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ddd3f-328">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ddd3f-329">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ddd3f-330">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ddd3f-331">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ddd3f-332">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-332">What's new</span></span>

- <span data-ttu-id="ddd3f-333">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="ddd3f-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ddd3f-334">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="ddd3f-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ddd3f-335">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ddd3f-336">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ddd3f-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="ddd3f-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ddd3f-338">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-338">Known Issues</span></span>

<span data-ttu-id="ddd3f-339">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ddd3f-340">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ddd3f-341">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-341">This update is:</span></span>
> - <span data-ttu-id="ddd3f-342">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="ddd3f-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ddd3f-343">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="ddd3f-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ddd3f-344">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ddd3f-345">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="ddd3f-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ddd3f-346">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ddd3f-347">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ddd3f-348">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ddd3f-349">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ddd3f-350">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ddd3f-351">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ddd3f-352">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ddd3f-353">Novità</span><span class="sxs-lookup"><span data-stu-id="ddd3f-353">What's new</span></span>

- <span data-ttu-id="ddd3f-354">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="ddd3f-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ddd3f-355">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="ddd3f-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ddd3f-356">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="ddd3f-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ddd3f-357">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ddd3f-358">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ddd3f-358">Known Issues</span></span>
<span data-ttu-id="ddd3f-359">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.10.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ddd3f-360">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="ddd3f-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ddd3f-361">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ddd3f-362">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ddd3f-363">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ddd3f-364">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ddd3f-365">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ddd3f-366">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="ddd3f-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ddd3f-367">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ddd3f-368">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ddd3f-369">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ddd3f-370">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="ddd3f-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ddd3f-371">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="ddd3f-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ddd3f-372">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="ddd3f-372">Windows 10 release</span></span>  |<span data-ttu-id="ddd3f-373">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="ddd3f-373">Platform version</span></span>  |<span data-ttu-id="ddd3f-374">Versione motore</span><span class="sxs-lookup"><span data-stu-id="ddd3f-374">Engine version</span></span> |<span data-ttu-id="ddd3f-375">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="ddd3f-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ddd3f-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ddd3f-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ddd3f-377">4.18.1909.6</span></span> |<span data-ttu-id="ddd3f-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ddd3f-378">1.1.17000.2</span></span> | <span data-ttu-id="ddd3f-379">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-380">1909  (19H2)</span></span> |<span data-ttu-id="ddd3f-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ddd3f-381">4.18.1902.5</span></span> |<span data-ttu-id="ddd3f-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ddd3f-382">1.1.16700.3</span></span> | <span data-ttu-id="ddd3f-383">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-384">1903  (19H1)</span></span> |<span data-ttu-id="ddd3f-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ddd3f-385">4.18.1902.5</span></span> |<span data-ttu-id="ddd3f-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ddd3f-386">1.1.15600.4</span></span> | <span data-ttu-id="ddd3f-387">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-388">1809  (RS5)</span></span> |<span data-ttu-id="ddd3f-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ddd3f-389">4.18.1807.18075</span></span> |<span data-ttu-id="ddd3f-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ddd3f-390">1.1.15000.2</span></span> | <span data-ttu-id="ddd3f-391">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-392">1803  (RS4)</span></span> |<span data-ttu-id="ddd3f-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ddd3f-393">4.13.17134.1</span></span> |<span data-ttu-id="ddd3f-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ddd3f-394">1.1.14600.4</span></span> | <span data-ttu-id="ddd3f-395">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-396">1709  (RS3)</span></span> |<span data-ttu-id="ddd3f-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ddd3f-397">4.12.16299.15</span></span> |<span data-ttu-id="ddd3f-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ddd3f-398">1.1.14104.0</span></span> | <span data-ttu-id="ddd3f-399">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-400">1703  (RS2)</span></span> |<span data-ttu-id="ddd3f-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ddd3f-401">4.11.15603.2</span></span> |<span data-ttu-id="ddd3f-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ddd3f-402">1.1.13504.0</span></span> | <span data-ttu-id="ddd3f-403">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ddd3f-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-404">1607 (RS1)</span></span> |<span data-ttu-id="ddd3f-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ddd3f-405">4.10.14393.3683</span></span> |<span data-ttu-id="ddd3f-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ddd3f-406">1.1.12805.0</span></span> | <span data-ttu-id="ddd3f-407">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ddd3f-408">Per informazioni sulla versione di Windows 10, vedi la scheda delle informazioni sul ciclo [di vita di Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ddd3f-409">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ddd3f-410">Ti consigliamo di aggiornare le immagini di installazione di Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 OS con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ddd3f-411">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ddd3f-412">Per ulteriori informazioni, vedere [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ddd3f-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ddd3f-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="ddd3f-414">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ddd3f-415">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ddd3f-416">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ddd3f-417">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-418">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-418">Fixes</span></span>
- <span data-ttu-id="ddd3f-419">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-420">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-420">Additional information</span></span>
- <span data-ttu-id="ddd3f-421">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ddd3f-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="ddd3f-423">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ddd3f-424">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ddd3f-425">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ddd3f-426">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-427">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-427">Fixes</span></span>
- <span data-ttu-id="ddd3f-428">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-429">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-429">Additional information</span></span>
- <span data-ttu-id="ddd3f-430">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ddd3f-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="ddd3f-432">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ddd3f-433">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ddd3f-434">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ddd3f-435">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-436">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-436">Fixes</span></span>
- <span data-ttu-id="ddd3f-437">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-438">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-438">Additional information</span></span>
- <span data-ttu-id="ddd3f-439">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ddd3f-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="ddd3f-441">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ddd3f-442">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ddd3f-443">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ddd3f-444">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-445">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-445">Fixes</span></span>
- <span data-ttu-id="ddd3f-446">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-447">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-447">Additional information</span></span>
- <span data-ttu-id="ddd3f-448">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ddd3f-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="ddd3f-450">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ddd3f-451">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ddd3f-452">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ddd3f-453">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-454">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-454">Fixes</span></span>
- <span data-ttu-id="ddd3f-455">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-456">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-456">Additional information</span></span>
- <span data-ttu-id="ddd3f-457">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ddd3f-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="ddd3f-459">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ddd3f-460">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ddd3f-461">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ddd3f-462">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-463">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-463">Fixes</span></span>
- <span data-ttu-id="ddd3f-464">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-465">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-465">Additional information</span></span>
- <span data-ttu-id="ddd3f-466">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ddd3f-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="ddd3f-468">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ddd3f-469">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ddd3f-470">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ddd3f-471">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-472">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-472">Fixes</span></span>
- <span data-ttu-id="ddd3f-473">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-474">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-474">Additional information</span></span>
- <span data-ttu-id="ddd3f-475">Firme aggiornate di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ddd3f-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ddd3f-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="ddd3f-477">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ddd3f-478">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ddd3f-479">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ddd3f-480">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-481">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-481">Fixes</span></span>
- <span data-ttu-id="ddd3f-482">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-483">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-483">Additional information</span></span>
- <span data-ttu-id="ddd3f-484">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ddd3f-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ddd3f-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="ddd3f-486">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ddd3f-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ddd3f-487">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ddd3f-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ddd3f-488">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ddd3f-489">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ddd3f-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ddd3f-490">Correzioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-490">Fixes</span></span>
- <span data-ttu-id="ddd3f-491">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd3f-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ddd3f-492">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ddd3f-492">Additional information</span></span>
- <span data-ttu-id="ddd3f-493">È stato aggiunto il supporto per le immagini di installazione del sistema operativo Windows 10 RS1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ddd3f-494">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ddd3f-494">Additional resources</span></span>

| <span data-ttu-id="ddd3f-495">Articolo</span><span class="sxs-lookup"><span data-stu-id="ddd3f-495">Article</span></span> | <span data-ttu-id="ddd3f-496">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ddd3f-497">Immagini di installazione dell'aggiornamento di Microsoft Defender per Windows</span><span class="sxs-lookup"><span data-stu-id="ddd3f-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ddd3f-498">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ddd3f-499">Ottenere gli aggiornamenti di Microsoft Defender Antivirus per Le immagini di installazione di Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ddd3f-500">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ddd3f-501">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ddd3f-502">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ddd3f-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ddd3f-503">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ddd3f-504">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="ddd3f-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ddd3f-505">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ddd3f-506">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="ddd3f-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ddd3f-507">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ddd3f-508">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="ddd3f-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ddd3f-509">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
