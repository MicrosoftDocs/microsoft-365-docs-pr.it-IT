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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822275"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="fb24d-104">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="fb24d-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="fb24d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fb24d-105">**Applies to:**</span></span>

- [<span data-ttu-id="fb24d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="fb24d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="fb24d-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fb24d-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="fb24d-108">Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:</span><span class="sxs-lookup"><span data-stu-id="fb24d-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="fb24d-109">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb24d-109">Security intelligence updates</span></span>
- <span data-ttu-id="fb24d-110">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="fb24d-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb24d-111">Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="fb24d-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="fb24d-112">Assicurarsi di aggiornare la protezione antivirus anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="fb24d-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fb24d-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="fb24d-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb24d-114">Security intelligence updates</span></span>

<span data-ttu-id="fb24d-115">Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="fb24d-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="fb24d-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="fb24d-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="fb24d-117">Antivirus Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="fb24d-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="fb24d-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="fb24d-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="fb24d-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="fb24d-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="fb24d-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="fb24d-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="fb24d-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="fb24d-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="fb24d-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fb24d-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="fb24d-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="fb24d-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="fb24d-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="fb24d-124">Product updates</span></span>

<span data-ttu-id="fb24d-125">Antivirus Microsoft Defender aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della piattaforma *)* e riceveranno aggiornamenti delle funzionalità principali insieme Windows 10 versioni.</span><span class="sxs-lookup"><span data-stu-id="fb24d-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="fb24d-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb24d-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="fb24d-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="fb24d-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="fb24d-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb24d-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="fb24d-129">Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="fb24d-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="fb24d-130">Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="fb24d-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="fb24d-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="fb24d-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="fb24d-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="fb24d-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="fb24d-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="fb24d-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="fb24d-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="fb24d-134">All our updates contain</span></span> 
- <span data-ttu-id="fb24d-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="fb24d-135">performance improvements;</span></span>
- <span data-ttu-id="fb24d-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="fb24d-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="fb24d-137">miglioramenti all'integrazione (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="fb24d-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="fb24d-138">Maggio-2021 (Piattaforma: 4.18.2105.4 | Motore: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="fb24d-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="fb24d-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="fb24d-140">&ensp;Rilasciato: **4 giugno 2021**</span><span class="sxs-lookup"><span data-stu-id="fb24d-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="fb24d-141">&ensp;Piattaforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="fb24d-142">&ensp;Motore: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="fb24d-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fb24d-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-144">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-144">What's new</span></span>
- <span data-ttu-id="fb24d-145">Miglioramenti al [monitoraggio del comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="fb24d-146">Funzionalità [di filtro delle notifiche di](network-protection.md) protezione di rete fissa</span><span class="sxs-lookup"><span data-stu-id="fb24d-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-147">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-147">Known Issues</span></span>
<span data-ttu-id="fb24d-148">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-149">Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="fb24d-150">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="fb24d-151">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="fb24d-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="fb24d-152">&ensp;Piattaforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="fb24d-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="fb24d-153">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="fb24d-154">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fb24d-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-155">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-155">What's new</span></span>
- <span data-ttu-id="fb24d-156">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="fb24d-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="fb24d-157">Rilevamento dei keylogger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="fb24d-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="fb24d-158">Sono stati aggiunti nuovi controlli per gestire il processo di implementazione graduale per [gli aggiornamenti di Microsoft Defender](updates.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-159">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-159">Known Issues</span></span>
<span data-ttu-id="fb24d-160">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-161">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="fb24d-162">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="fb24d-163">&ensp;Rilasciato: **1 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="fb24d-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="fb24d-164">&ensp;Piattaforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="fb24d-165">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="fb24d-166">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fb24d-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-167">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-167">What's new</span></span>

- <span data-ttu-id="fb24d-168">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="fb24d-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="fb24d-169">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="fb24d-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="fb24d-170">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="fb24d-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-171">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-171">Known Issues</span></span>
<span data-ttu-id="fb24d-172">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="fb24d-173">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="fb24d-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="fb24d-174">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="fb24d-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="fb24d-175">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fb24d-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="fb24d-176">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="fb24d-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="fb24d-177">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="fb24d-178">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="fb24d-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="fb24d-179">&ensp;Piattaforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="fb24d-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="fb24d-180">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="fb24d-181">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-182">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-182">What's new</span></span>

- <span data-ttu-id="fb24d-183">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="fb24d-184">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-185">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-185">Known Issues</span></span>
<span data-ttu-id="fb24d-186">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-187">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="fb24d-188">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fb24d-189">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="fb24d-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="fb24d-190">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="fb24d-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="fb24d-191">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="fb24d-192">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-193">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-193">What's new</span></span>

- <span data-ttu-id="fb24d-194">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="fb24d-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="fb24d-195">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="fb24d-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="fb24d-196">Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi</span><span class="sxs-lookup"><span data-stu-id="fb24d-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="fb24d-197">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="fb24d-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="fb24d-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="fb24d-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-199">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-199">Known Issues</span></span>
<span data-ttu-id="fb24d-200">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-201">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="fb24d-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="fb24d-202">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fb24d-203">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="fb24d-204">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="fb24d-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="fb24d-205">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="fb24d-206">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-207">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-207">What's new</span></span>

- <span data-ttu-id="fb24d-208">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="fb24d-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-209">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-209">Known Issues</span></span>
<span data-ttu-id="fb24d-210">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-211">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="fb24d-212">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="fb24d-213">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="fb24d-214">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="fb24d-215">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="fb24d-216">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-217">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-217">What's new</span></span>

- <span data-ttu-id="fb24d-218">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="fb24d-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="fb24d-219">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="fb24d-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="fb24d-220">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="fb24d-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="fb24d-221">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="fb24d-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-222">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-222">Known Issues</span></span>

<span data-ttu-id="fb24d-223">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fb24d-224">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="fb24d-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="fb24d-225">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="fb24d-226">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="fb24d-227">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="fb24d-228">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="fb24d-229">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-230">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-230">What's new</span></span>

- <span data-ttu-id="fb24d-231">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="fb24d-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="fb24d-232">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="fb24d-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="fb24d-233">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="fb24d-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="fb24d-234">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="fb24d-234">New management interfaces for:</span></span>
   - <span data-ttu-id="fb24d-235">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="fb24d-235">UDP Inspection</span></span>
   - <span data-ttu-id="fb24d-236">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="fb24d-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="fb24d-237">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="fb24d-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="fb24d-238">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="fb24d-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="fb24d-239">Analisi Office modulo VBA migliorata</span><span class="sxs-lookup"><span data-stu-id="fb24d-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-240">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-240">Known Issues</span></span>

<span data-ttu-id="fb24d-241">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="fb24d-242">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="fb24d-243">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="fb24d-244">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="fb24d-245">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="fb24d-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="fb24d-246">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="fb24d-247">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="fb24d-248">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-248">What's new</span></span>

- <span data-ttu-id="fb24d-249">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="fb24d-249">Add more telemetry events</span></span>
- <span data-ttu-id="fb24d-250">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="fb24d-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="fb24d-251">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="fb24d-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="fb24d-252">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="fb24d-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="fb24d-253">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb24d-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="fb24d-254">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="fb24d-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="fb24d-255">Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="fb24d-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="fb24d-256">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-256">Known Issues</span></span>
<span data-ttu-id="fb24d-257">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-258">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="fb24d-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="fb24d-259">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="fb24d-260">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="fb24d-261">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="fb24d-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="fb24d-262">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="fb24d-263">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-264">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-264">What's new</span></span>

- <span data-ttu-id="fb24d-265">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="fb24d-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="fb24d-266">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="fb24d-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-267">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-267">Known Issues</span></span>
<span data-ttu-id="fb24d-268">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-269">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="fb24d-270">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="fb24d-271">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="fb24d-272">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="fb24d-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="fb24d-273">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="fb24d-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="fb24d-274">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-275">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-275">What's new</span></span>

- <span data-ttu-id="fb24d-276">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="fb24d-277">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="fb24d-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="fb24d-278">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="fb24d-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="fb24d-279">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="fb24d-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="fb24d-280">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="fb24d-280">Fixed registry query</span></span> 
- <span data-ttu-id="fb24d-281">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="fb24d-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-282">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-282">Known Issues</span></span>
<span data-ttu-id="fb24d-283">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-284">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="fb24d-285">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="fb24d-286">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="fb24d-287">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="fb24d-288">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="fb24d-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="fb24d-289">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-290">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-290">What's new</span></span>

- <span data-ttu-id="fb24d-291">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="fb24d-291">Improved logging for scan events</span></span>
- <span data-ttu-id="fb24d-292">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="fb24d-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="fb24d-293">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="fb24d-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="fb24d-294">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="fb24d-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="fb24d-295">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="fb24d-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="fb24d-296">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb24d-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-297">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-297">Known Issues</span></span>
<span data-ttu-id="fb24d-298">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-299">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="fb24d-300">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="fb24d-301">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="fb24d-302">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="fb24d-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="fb24d-303">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="fb24d-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="fb24d-304">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-305">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-305">What's new</span></span>
- <span data-ttu-id="fb24d-306">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="fb24d-306">WDfilter improvements</span></span>
- <span data-ttu-id="fb24d-307">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="fb24d-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="fb24d-308">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="fb24d-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="fb24d-309">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fb24d-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="fb24d-310">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="fb24d-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="fb24d-311">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="fb24d-311">UEFI scan capability</span></span>
- <span data-ttu-id="fb24d-312">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="fb24d-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="fb24d-313">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-313">Known Issues</span></span>
<span data-ttu-id="fb24d-314">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-315">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="fb24d-316">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="fb24d-317">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="fb24d-318">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="fb24d-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="fb24d-319">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="fb24d-320">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fb24d-321">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-321">What's new</span></span>

- <span data-ttu-id="fb24d-322">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="fb24d-323">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="fb24d-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="fb24d-324">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="fb24d-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="fb24d-325">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="fb24d-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="fb24d-326">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="fb24d-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fb24d-327">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-327">Known Issues</span></span>
<span data-ttu-id="fb24d-328">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="fb24d-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="fb24d-329">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="fb24d-330">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="fb24d-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="fb24d-331">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="fb24d-332">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="fb24d-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="fb24d-333">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="fb24d-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="fb24d-334">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fb24d-335">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="fb24d-336">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-336">Known Issues</span></span>
<span data-ttu-id="fb24d-337">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fb24d-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-338">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="fb24d-339">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="fb24d-340">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="fb24d-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="fb24d-341">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="fb24d-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="fb24d-342">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="fb24d-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="fb24d-343">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fb24d-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fb24d-344">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-344">What's new</span></span>

- <span data-ttu-id="fb24d-345">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="fb24d-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="fb24d-346">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="fb24d-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="fb24d-347">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fb24d-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="fb24d-348">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fb24d-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="fb24d-349">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="fb24d-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fb24d-350">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-350">Known Issues</span></span>

<span data-ttu-id="fb24d-351">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="fb24d-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="fb24d-352">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="fb24d-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="fb24d-353">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="fb24d-353">This update is:</span></span>
> - <span data-ttu-id="fb24d-354">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="fb24d-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="fb24d-355">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="fb24d-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="fb24d-356">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="fb24d-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="fb24d-357">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="fb24d-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="fb24d-358">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="fb24d-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fb24d-359">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="fb24d-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="fb24d-360">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="fb24d-361">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="fb24d-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="fb24d-362">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="fb24d-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="fb24d-363">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="fb24d-364">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="fb24d-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="fb24d-365">Novità</span><span class="sxs-lookup"><span data-stu-id="fb24d-365">What's new</span></span>

- <span data-ttu-id="fb24d-366">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="fb24d-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="fb24d-367">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="fb24d-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="fb24d-368">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="fb24d-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="fb24d-369">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="fb24d-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fb24d-370">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fb24d-370">Known Issues</span></span>
<span data-ttu-id="fb24d-371">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.18.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fb24d-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="fb24d-372">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fb24d-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="fb24d-373">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="fb24d-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="fb24d-374">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fb24d-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="fb24d-375">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="fb24d-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="fb24d-376">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="fb24d-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="fb24d-377">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="fb24d-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="fb24d-378">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="fb24d-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="fb24d-379">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fb24d-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="fb24d-380">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="fb24d-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="fb24d-381">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="fb24d-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="fb24d-382">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="fb24d-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="fb24d-383">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="fb24d-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="fb24d-384">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="fb24d-384">Windows 10 release</span></span>  |<span data-ttu-id="fb24d-385">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fb24d-385">Platform version</span></span>  |<span data-ttu-id="fb24d-386">Versione motore</span><span class="sxs-lookup"><span data-stu-id="fb24d-386">Engine version</span></span> |<span data-ttu-id="fb24d-387">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="fb24d-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fb24d-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="fb24d-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="fb24d-389">4.18.1909.6</span></span> |<span data-ttu-id="fb24d-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="fb24d-390">1.1.17000.2</span></span> | <span data-ttu-id="fb24d-391">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-392">1909  (19H2)</span></span> |<span data-ttu-id="fb24d-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fb24d-393">4.18.1902.5</span></span> |<span data-ttu-id="fb24d-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="fb24d-394">1.1.16700.3</span></span> | <span data-ttu-id="fb24d-395">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="fb24d-396">1903  (19H1)</span></span> |<span data-ttu-id="fb24d-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fb24d-397">4.18.1902.5</span></span> |<span data-ttu-id="fb24d-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="fb24d-398">1.1.15600.4</span></span> | <span data-ttu-id="fb24d-399">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="fb24d-400">1809  (RS5)</span></span> |<span data-ttu-id="fb24d-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="fb24d-401">4.18.1807.18075</span></span> |<span data-ttu-id="fb24d-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="fb24d-402">1.1.15000.2</span></span> | <span data-ttu-id="fb24d-403">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="fb24d-404">1803  (RS4)</span></span> |<span data-ttu-id="fb24d-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="fb24d-405">4.13.17134.1</span></span> |<span data-ttu-id="fb24d-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="fb24d-406">1.1.14600.4</span></span> | <span data-ttu-id="fb24d-407">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="fb24d-408">1709  (RS3)</span></span> |<span data-ttu-id="fb24d-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="fb24d-409">4.12.16299.15</span></span> |<span data-ttu-id="fb24d-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="fb24d-410">1.1.14104.0</span></span> | <span data-ttu-id="fb24d-411">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="fb24d-412">1703  (RS2)</span></span> |<span data-ttu-id="fb24d-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="fb24d-413">4.11.15603.2</span></span> |<span data-ttu-id="fb24d-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="fb24d-414">1.1.13504.0</span></span> | <span data-ttu-id="fb24d-415">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fb24d-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="fb24d-416">1607 (RS1)</span></span> |<span data-ttu-id="fb24d-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="fb24d-417">4.10.14393.3683</span></span> |<span data-ttu-id="fb24d-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="fb24d-418">1.1.12805.0</span></span> | <span data-ttu-id="fb24d-419">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fb24d-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="fb24d-420">Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="fb24d-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="fb24d-421">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="fb24d-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="fb24d-422">È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="fb24d-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="fb24d-423">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="fb24d-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="fb24d-424">Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="fb24d-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="fb24d-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="fb24d-426">&ensp;Versione pacchetto: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="fb24d-427">&ensp;Versione della piattaforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="fb24d-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="fb24d-428">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fb24d-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fb24d-429">&ensp;Versione firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-430">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-430">Fixes</span></span>
- <span data-ttu-id="fb24d-431">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-432">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-432">Additional information</span></span>
- <span data-ttu-id="fb24d-433">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="fb24d-435">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="fb24d-436">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="fb24d-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="fb24d-437">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fb24d-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fb24d-438">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-439">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-439">Fixes</span></span>
- <span data-ttu-id="fb24d-440">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-441">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-441">Additional information</span></span>
- <span data-ttu-id="fb24d-442">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="fb24d-444">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="fb24d-445">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="fb24d-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="fb24d-446">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="fb24d-447">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-448">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-448">Fixes</span></span>
- <span data-ttu-id="fb24d-449">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-450">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-450">Additional information</span></span>
- <span data-ttu-id="fb24d-451">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="fb24d-453">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="fb24d-454">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="fb24d-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="fb24d-455">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fb24d-456">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-457">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-457">Fixes</span></span>
- <span data-ttu-id="fb24d-458">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-459">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-459">Additional information</span></span>
- <span data-ttu-id="fb24d-460">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="fb24d-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="fb24d-462">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="fb24d-463">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fb24d-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fb24d-464">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fb24d-465">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-466">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-466">Fixes</span></span>
- <span data-ttu-id="fb24d-467">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-468">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-468">Additional information</span></span>
- <span data-ttu-id="fb24d-469">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="fb24d-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="fb24d-471">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="fb24d-472">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fb24d-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fb24d-473">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fb24d-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="fb24d-474">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-475">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-475">Fixes</span></span>
- <span data-ttu-id="fb24d-476">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-477">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-477">Additional information</span></span>
- <span data-ttu-id="fb24d-478">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="fb24d-480">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="fb24d-481">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fb24d-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fb24d-482">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fb24d-483">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-484">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-484">Fixes</span></span>
- <span data-ttu-id="fb24d-485">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-486">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-486">Additional information</span></span>
- <span data-ttu-id="fb24d-487">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="fb24d-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="fb24d-489">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="fb24d-490">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fb24d-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fb24d-491">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fb24d-492">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-493">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-493">Fixes</span></span>
- <span data-ttu-id="fb24d-494">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-495">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-495">Additional information</span></span>
- <span data-ttu-id="fb24d-496">Firme Antivirus Microsoft Defender aggiornate</span><span class="sxs-lookup"><span data-stu-id="fb24d-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="fb24d-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="fb24d-498">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fb24d-499">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fb24d-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="fb24d-500">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fb24d-501">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-502">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-502">Fixes</span></span>
- <span data-ttu-id="fb24d-503">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-504">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-504">Additional information</span></span>
- <span data-ttu-id="fb24d-505">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fb24d-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="fb24d-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="fb24d-507">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fb24d-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fb24d-508">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="fb24d-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="fb24d-509">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fb24d-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="fb24d-510">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="fb24d-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fb24d-511">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fb24d-511">Fixes</span></span>
- <span data-ttu-id="fb24d-512">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb24d-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fb24d-513">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-513">Additional information</span></span>
- <span data-ttu-id="fb24d-514">È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fb24d-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="fb24d-515">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb24d-515">Additional resources</span></span>

| <span data-ttu-id="fb24d-516">Articolo</span><span class="sxs-lookup"><span data-stu-id="fb24d-516">Article</span></span> | <span data-ttu-id="fb24d-517">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb24d-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="fb24d-518">Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fb24d-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="fb24d-519">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="fb24d-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="fb24d-520">Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.</span><span class="sxs-lookup"><span data-stu-id="fb24d-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="fb24d-521">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="fb24d-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fb24d-522">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="fb24d-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="fb24d-523">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="fb24d-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="fb24d-524">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="fb24d-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="fb24d-525">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="fb24d-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="fb24d-526">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="fb24d-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="fb24d-527">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="fb24d-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fb24d-528">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="fb24d-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="fb24d-529">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="fb24d-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="fb24d-530">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="fb24d-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
