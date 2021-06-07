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
ms.date: 06/04/2021
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795983"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="539a1-104">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="539a1-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="539a1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="539a1-105">**Applies to:**</span></span>

- [<span data-ttu-id="539a1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="539a1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="539a1-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="539a1-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="539a1-108">Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:</span><span class="sxs-lookup"><span data-stu-id="539a1-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="539a1-109">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="539a1-109">Security intelligence updates</span></span>
- <span data-ttu-id="539a1-110">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="539a1-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="539a1-111">Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="539a1-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="539a1-112">Assicurarsi di aggiornare la protezione antivirus anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="539a1-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="539a1-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="539a1-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="539a1-114">Security intelligence updates</span></span>

<span data-ttu-id="539a1-115">Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="539a1-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="539a1-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="539a1-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="539a1-117">Antivirus Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="539a1-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="539a1-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="539a1-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="539a1-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="539a1-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="539a1-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="539a1-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="539a1-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="539a1-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="539a1-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="539a1-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="539a1-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="539a1-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="539a1-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="539a1-124">Product updates</span></span>

<span data-ttu-id="539a1-125">Antivirus Microsoft Defender aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della piattaforma *)* e riceveranno aggiornamenti delle funzionalità principali insieme Windows 10 versioni.</span><span class="sxs-lookup"><span data-stu-id="539a1-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="539a1-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="539a1-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="539a1-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="539a1-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="539a1-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="539a1-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="539a1-129">Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="539a1-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="539a1-130">Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="539a1-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="539a1-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="539a1-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="539a1-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="539a1-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="539a1-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="539a1-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="539a1-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="539a1-134">All our updates contain</span></span> 
- <span data-ttu-id="539a1-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="539a1-135">performance improvements;</span></span>
- <span data-ttu-id="539a1-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="539a1-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="539a1-137">miglioramenti all'integrazione (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="539a1-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="539a1-138">Maggio-2021 (Piattaforma: 4.18.2105.4 | Motore: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="539a1-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="539a1-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="539a1-140">&ensp;Rilasciato: **4 giugno 2021**</span><span class="sxs-lookup"><span data-stu-id="539a1-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="539a1-141">&ensp;Piattaforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="539a1-142">&ensp;Motore: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="539a1-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="539a1-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-144">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-144">What's new</span></span>
- <span data-ttu-id="539a1-145">Miglioramenti al [monitoraggio del comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="539a1-146">Funzionalità [di filtro delle notifiche di](network-protection.md) protezione di rete fissa</span><span class="sxs-lookup"><span data-stu-id="539a1-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-147">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-147">Known Issues</span></span>
<span data-ttu-id="539a1-148">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-149">Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="539a1-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="539a1-150">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="539a1-151">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="539a1-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="539a1-152">&ensp;Piattaforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="539a1-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="539a1-153">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="539a1-154">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="539a1-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-155">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-155">What's new</span></span>
- <span data-ttu-id="539a1-156">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="539a1-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="539a1-157">Rilevamento dei keylogger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="539a1-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-158">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-158">Known Issues</span></span>
<span data-ttu-id="539a1-159">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-160">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="539a1-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="539a1-161">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="539a1-162">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="539a1-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="539a1-163">&ensp;Piattaforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="539a1-164">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="539a1-165">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="539a1-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-166">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-166">What's new</span></span>

- <span data-ttu-id="539a1-167">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="539a1-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="539a1-168">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="539a1-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="539a1-169">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="539a1-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-170">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-170">Known Issues</span></span>
<span data-ttu-id="539a1-171">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="539a1-172">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="539a1-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="539a1-173">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="539a1-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="539a1-174">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="539a1-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="539a1-175">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="539a1-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="539a1-176">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="539a1-177">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="539a1-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="539a1-178">&ensp;Piattaforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="539a1-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="539a1-179">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="539a1-180">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-181">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-181">What's new</span></span>

- <span data-ttu-id="539a1-182">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="539a1-183">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="539a1-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-184">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-184">Known Issues</span></span>
<span data-ttu-id="539a1-185">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-186">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="539a1-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="539a1-187">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="539a1-188">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="539a1-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="539a1-189">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="539a1-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="539a1-190">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="539a1-191">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-192">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-192">What's new</span></span>

- <span data-ttu-id="539a1-193">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="539a1-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="539a1-194">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="539a1-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="539a1-195">Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi</span><span class="sxs-lookup"><span data-stu-id="539a1-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="539a1-196">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="539a1-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="539a1-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="539a1-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-198">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-198">Known Issues</span></span>
<span data-ttu-id="539a1-199">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-200">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="539a1-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="539a1-201">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="539a1-202">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="539a1-203">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="539a1-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="539a1-204">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="539a1-205">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-206">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-206">What's new</span></span>

- <span data-ttu-id="539a1-207">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="539a1-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-208">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-208">Known Issues</span></span>
<span data-ttu-id="539a1-209">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-210">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="539a1-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="539a1-211">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="539a1-212">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="539a1-213">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="539a1-214">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="539a1-215">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-216">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-216">What's new</span></span>

- <span data-ttu-id="539a1-217">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="539a1-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="539a1-218">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="539a1-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="539a1-219">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="539a1-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="539a1-220">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="539a1-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-221">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-221">Known Issues</span></span>

<span data-ttu-id="539a1-222">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="539a1-223">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="539a1-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="539a1-224">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="539a1-225">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="539a1-226">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="539a1-227">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="539a1-228">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-229">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-229">What's new</span></span>

- <span data-ttu-id="539a1-230">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="539a1-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="539a1-231">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="539a1-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="539a1-232">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="539a1-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="539a1-233">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="539a1-233">New management interfaces for:</span></span>
   - <span data-ttu-id="539a1-234">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="539a1-234">UDP Inspection</span></span>
   - <span data-ttu-id="539a1-235">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="539a1-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="539a1-236">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="539a1-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="539a1-237">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="539a1-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="539a1-238">Analisi Office modulo VBA migliorata</span><span class="sxs-lookup"><span data-stu-id="539a1-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-239">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-239">Known Issues</span></span>

<span data-ttu-id="539a1-240">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="539a1-241">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="539a1-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="539a1-242">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="539a1-243">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="539a1-244">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="539a1-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="539a1-245">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="539a1-246">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="539a1-247">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-247">What's new</span></span>

- <span data-ttu-id="539a1-248">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="539a1-248">Add more telemetry events</span></span>
- <span data-ttu-id="539a1-249">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="539a1-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="539a1-250">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="539a1-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="539a1-251">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="539a1-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="539a1-252">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="539a1-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="539a1-253">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="539a1-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="539a1-254">Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="539a1-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="539a1-255">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-255">Known Issues</span></span>
<span data-ttu-id="539a1-256">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-257">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="539a1-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="539a1-258">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="539a1-259">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="539a1-260">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="539a1-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="539a1-261">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="539a1-262">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-263">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-263">What's new</span></span>

- <span data-ttu-id="539a1-264">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="539a1-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="539a1-265">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="539a1-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-266">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-266">Known Issues</span></span>
<span data-ttu-id="539a1-267">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-268">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="539a1-269">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="539a1-270">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="539a1-271">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="539a1-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="539a1-272">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="539a1-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="539a1-273">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-274">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-274">What's new</span></span>

- <span data-ttu-id="539a1-275">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="539a1-276">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="539a1-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="539a1-277">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="539a1-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="539a1-278">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="539a1-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="539a1-279">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="539a1-279">Fixed registry query</span></span> 
- <span data-ttu-id="539a1-280">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="539a1-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-281">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-281">Known Issues</span></span>
<span data-ttu-id="539a1-282">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-283">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="539a1-284">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="539a1-285">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="539a1-286">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="539a1-287">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="539a1-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="539a1-288">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-289">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-289">What's new</span></span>

- <span data-ttu-id="539a1-290">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="539a1-290">Improved logging for scan events</span></span>
- <span data-ttu-id="539a1-291">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="539a1-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="539a1-292">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="539a1-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="539a1-293">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="539a1-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="539a1-294">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="539a1-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="539a1-295">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="539a1-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-296">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-296">Known Issues</span></span>
<span data-ttu-id="539a1-297">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-298">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="539a1-299">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="539a1-300">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="539a1-301">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="539a1-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="539a1-302">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="539a1-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="539a1-303">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-304">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-304">What's new</span></span>
- <span data-ttu-id="539a1-305">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="539a1-305">WDfilter improvements</span></span>
- <span data-ttu-id="539a1-306">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="539a1-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="539a1-307">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="539a1-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="539a1-308">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="539a1-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="539a1-309">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="539a1-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="539a1-310">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="539a1-310">UEFI scan capability</span></span>
- <span data-ttu-id="539a1-311">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="539a1-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="539a1-312">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-312">Known Issues</span></span>
<span data-ttu-id="539a1-313">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-314">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="539a1-315">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="539a1-316">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="539a1-317">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="539a1-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="539a1-318">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="539a1-319">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="539a1-320">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-320">What's new</span></span>

- <span data-ttu-id="539a1-321">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="539a1-322">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="539a1-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="539a1-323">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="539a1-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="539a1-324">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="539a1-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="539a1-325">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="539a1-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="539a1-326">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-326">Known Issues</span></span>
<span data-ttu-id="539a1-327">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="539a1-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="539a1-328">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="539a1-329">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="539a1-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="539a1-330">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="539a1-331">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="539a1-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="539a1-332">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="539a1-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="539a1-333">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="539a1-334">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="539a1-335">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-335">Known Issues</span></span>
<span data-ttu-id="539a1-336">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="539a1-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-337">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="539a1-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="539a1-338">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="539a1-339">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="539a1-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="539a1-340">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="539a1-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="539a1-341">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="539a1-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="539a1-342">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="539a1-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="539a1-343">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-343">What's new</span></span>

- <span data-ttu-id="539a1-344">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="539a1-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="539a1-345">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="539a1-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="539a1-346">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="539a1-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="539a1-347">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="539a1-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="539a1-348">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="539a1-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="539a1-349">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-349">Known Issues</span></span>

<span data-ttu-id="539a1-350">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="539a1-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="539a1-351">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="539a1-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="539a1-352">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="539a1-352">This update is:</span></span>
> - <span data-ttu-id="539a1-353">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="539a1-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="539a1-354">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="539a1-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="539a1-355">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="539a1-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="539a1-356">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="539a1-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="539a1-357">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="539a1-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="539a1-358">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="539a1-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="539a1-359">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="539a1-360">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="539a1-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="539a1-361">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="539a1-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="539a1-362">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="539a1-363">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="539a1-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="539a1-364">Novità</span><span class="sxs-lookup"><span data-stu-id="539a1-364">What's new</span></span>

- <span data-ttu-id="539a1-365">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="539a1-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="539a1-366">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="539a1-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="539a1-367">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="539a1-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="539a1-368">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="539a1-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="539a1-369">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="539a1-369">Known Issues</span></span>
<span data-ttu-id="539a1-370">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.10.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="539a1-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="539a1-371">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="539a1-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="539a1-372">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="539a1-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="539a1-373">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="539a1-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="539a1-374">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="539a1-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="539a1-375">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="539a1-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="539a1-376">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="539a1-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="539a1-377">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="539a1-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="539a1-378">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="539a1-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="539a1-379">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="539a1-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="539a1-380">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="539a1-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="539a1-381">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="539a1-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="539a1-382">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="539a1-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="539a1-383">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="539a1-383">Windows 10 release</span></span>  |<span data-ttu-id="539a1-384">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="539a1-384">Platform version</span></span>  |<span data-ttu-id="539a1-385">Versione motore</span><span class="sxs-lookup"><span data-stu-id="539a1-385">Engine version</span></span> |<span data-ttu-id="539a1-386">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="539a1-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="539a1-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="539a1-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="539a1-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="539a1-388">4.18.1909.6</span></span> |<span data-ttu-id="539a1-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="539a1-389">1.1.17000.2</span></span> | <span data-ttu-id="539a1-390">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="539a1-391">1909  (19H2)</span></span> |<span data-ttu-id="539a1-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="539a1-392">4.18.1902.5</span></span> |<span data-ttu-id="539a1-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="539a1-393">1.1.16700.3</span></span> | <span data-ttu-id="539a1-394">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="539a1-395">1903  (19H1)</span></span> |<span data-ttu-id="539a1-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="539a1-396">4.18.1902.5</span></span> |<span data-ttu-id="539a1-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="539a1-397">1.1.15600.4</span></span> | <span data-ttu-id="539a1-398">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="539a1-399">1809  (RS5)</span></span> |<span data-ttu-id="539a1-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="539a1-400">4.18.1807.18075</span></span> |<span data-ttu-id="539a1-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="539a1-401">1.1.15000.2</span></span> | <span data-ttu-id="539a1-402">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="539a1-403">1803  (RS4)</span></span> |<span data-ttu-id="539a1-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="539a1-404">4.13.17134.1</span></span> |<span data-ttu-id="539a1-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="539a1-405">1.1.14600.4</span></span> | <span data-ttu-id="539a1-406">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="539a1-407">1709  (RS3)</span></span> |<span data-ttu-id="539a1-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="539a1-408">4.12.16299.15</span></span> |<span data-ttu-id="539a1-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="539a1-409">1.1.14104.0</span></span> | <span data-ttu-id="539a1-410">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="539a1-411">1703  (RS2)</span></span> |<span data-ttu-id="539a1-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="539a1-412">4.11.15603.2</span></span> |<span data-ttu-id="539a1-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="539a1-413">1.1.13504.0</span></span> | <span data-ttu-id="539a1-414">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="539a1-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="539a1-415">1607 (RS1)</span></span> |<span data-ttu-id="539a1-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="539a1-416">4.10.14393.3683</span></span> |<span data-ttu-id="539a1-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="539a1-417">1.1.12805.0</span></span> | <span data-ttu-id="539a1-418">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="539a1-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="539a1-419">Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="539a1-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="539a1-420">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="539a1-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="539a1-421">È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="539a1-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="539a1-422">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="539a1-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="539a1-423">Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="539a1-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="539a1-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="539a1-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="539a1-425">&ensp;Versione pacchetto: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="539a1-426">&ensp;Versione della piattaforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="539a1-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="539a1-427">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="539a1-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="539a1-428">&ensp;Versione firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-429">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-429">Fixes</span></span>
- <span data-ttu-id="539a1-430">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-431">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-431">Additional information</span></span>
- <span data-ttu-id="539a1-432">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="539a1-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="539a1-434">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="539a1-435">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="539a1-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="539a1-436">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="539a1-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="539a1-437">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-438">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-438">Fixes</span></span>
- <span data-ttu-id="539a1-439">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-440">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-440">Additional information</span></span>
- <span data-ttu-id="539a1-441">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="539a1-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="539a1-443">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="539a1-444">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="539a1-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="539a1-445">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="539a1-446">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-447">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-447">Fixes</span></span>
- <span data-ttu-id="539a1-448">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-449">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-449">Additional information</span></span>
- <span data-ttu-id="539a1-450">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="539a1-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="539a1-452">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="539a1-453">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="539a1-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="539a1-454">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="539a1-455">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-456">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-456">Fixes</span></span>
- <span data-ttu-id="539a1-457">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-458">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-458">Additional information</span></span>
- <span data-ttu-id="539a1-459">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="539a1-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="539a1-461">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="539a1-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="539a1-462">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="539a1-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="539a1-463">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="539a1-464">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-465">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-465">Fixes</span></span>
- <span data-ttu-id="539a1-466">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-467">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-467">Additional information</span></span>
- <span data-ttu-id="539a1-468">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="539a1-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="539a1-470">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="539a1-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="539a1-471">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="539a1-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="539a1-472">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="539a1-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="539a1-473">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-474">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-474">Fixes</span></span>
- <span data-ttu-id="539a1-475">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-476">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-476">Additional information</span></span>
- <span data-ttu-id="539a1-477">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="539a1-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="539a1-479">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="539a1-480">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="539a1-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="539a1-481">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="539a1-482">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-483">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-483">Fixes</span></span>
- <span data-ttu-id="539a1-484">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-485">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-485">Additional information</span></span>
- <span data-ttu-id="539a1-486">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="539a1-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="539a1-488">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="539a1-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="539a1-489">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="539a1-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="539a1-490">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="539a1-491">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-492">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-492">Fixes</span></span>
- <span data-ttu-id="539a1-493">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-494">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-494">Additional information</span></span>
- <span data-ttu-id="539a1-495">Firme Antivirus Microsoft Defender aggiornate</span><span class="sxs-lookup"><span data-stu-id="539a1-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="539a1-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="539a1-497">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="539a1-498">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="539a1-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="539a1-499">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="539a1-500">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-501">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-501">Fixes</span></span>
- <span data-ttu-id="539a1-502">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-503">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-503">Additional information</span></span>
- <span data-ttu-id="539a1-504">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="539a1-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="539a1-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="539a1-506">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="539a1-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="539a1-507">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="539a1-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="539a1-508">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="539a1-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="539a1-509">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="539a1-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="539a1-510">Correzioni</span><span class="sxs-lookup"><span data-stu-id="539a1-510">Fixes</span></span>
- <span data-ttu-id="539a1-511">Nessuno</span><span class="sxs-lookup"><span data-stu-id="539a1-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="539a1-512">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-512">Additional information</span></span>
- <span data-ttu-id="539a1-513">È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="539a1-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="539a1-514">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="539a1-514">Additional resources</span></span>

| <span data-ttu-id="539a1-515">Articolo</span><span class="sxs-lookup"><span data-stu-id="539a1-515">Article</span></span> | <span data-ttu-id="539a1-516">Descrizione</span><span class="sxs-lookup"><span data-stu-id="539a1-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="539a1-517">Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="539a1-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="539a1-518">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="539a1-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="539a1-519">Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.</span><span class="sxs-lookup"><span data-stu-id="539a1-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="539a1-520">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="539a1-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="539a1-521">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="539a1-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="539a1-522">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="539a1-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="539a1-523">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="539a1-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="539a1-524">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="539a1-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="539a1-525">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="539a1-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="539a1-526">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="539a1-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="539a1-527">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="539a1-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="539a1-528">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="539a1-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="539a1-529">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="539a1-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
