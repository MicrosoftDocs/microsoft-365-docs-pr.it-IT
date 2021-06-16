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
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929444"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="fbe8a-104">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="fbe8a-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="fbe8a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-105">**Applies to:**</span></span>

- [<span data-ttu-id="fbe8a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="fbe8a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="fbe8a-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fbe8a-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="fbe8a-108">Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="fbe8a-109">Assicurarsi di aggiornare la protezione antivirus, anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="fbe8a-110">Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="fbe8a-111">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="fbe8a-111">Security intelligence updates</span></span>
- <span data-ttu-id="fbe8a-112">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="fbe8a-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="fbe8a-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="fbe8a-114">Security intelligence updates</span></span>

<span data-ttu-id="fbe8a-115">Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="fbe8a-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="fbe8a-117">Antivirus Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="fbe8a-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="fbe8a-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="fbe8a-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="fbe8a-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="fbe8a-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="fbe8a-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="fbe8a-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="fbe8a-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="fbe8a-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-124">Product updates</span></span>

<span data-ttu-id="fbe8a-125">Antivirus Microsoft Defender aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della piattaforma *)* e riceveranno aggiornamenti delle funzionalità principali insieme Windows 10 versioni.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="fbe8a-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="fbe8a-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="fbe8a-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fbe8a-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="fbe8a-129">Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="fbe8a-130">Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="fbe8a-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="fbe8a-132">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="fbe8a-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="fbe8a-133">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="fbe8a-134">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="fbe8a-134">All our updates contain</span></span> 
- <span data-ttu-id="fbe8a-135">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="fbe8a-135">performance improvements;</span></span>
- <span data-ttu-id="fbe8a-136">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="fbe8a-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="fbe8a-137">miglioramenti all'integrazione (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="fbe8a-138">Maggio-2021 (Piattaforma: 4.18.2105.4 | Motore: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="fbe8a-139">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="fbe8a-140">&ensp;Rilasciato: **3 giugno 2021**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="fbe8a-141">&ensp;Piattaforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="fbe8a-142">&ensp;Motore: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="fbe8a-143">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-144">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-144">What's new</span></span>
- <span data-ttu-id="fbe8a-145">Miglioramenti al [monitoraggio del comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="fbe8a-146">Funzionalità [di filtro delle notifiche di](network-protection.md) protezione di rete fissa</span><span class="sxs-lookup"><span data-stu-id="fbe8a-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-147">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-147">Known Issues</span></span>
<span data-ttu-id="fbe8a-148">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-149">Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="fbe8a-150">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="fbe8a-151">&ensp;Rilasciato: **26 aprile 2021**  (Motore: 1.1.18100.6 rilasciato il 5 maggio 2021) &ensp; Piattaforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="fbe8a-152">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="fbe8a-153">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-154">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-154">What's new</span></span>
- <span data-ttu-id="fbe8a-155">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="fbe8a-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="fbe8a-156">Rilevamento dei keylogger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="fbe8a-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-157">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-157">Known Issues</span></span>
<span data-ttu-id="fbe8a-158">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-159">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="fbe8a-160">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="fbe8a-161">&ensp;Rilasciato: **2 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="fbe8a-162">&ensp;Piattaforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="fbe8a-163">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="fbe8a-164">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-165">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-165">What's new</span></span>

- <span data-ttu-id="fbe8a-166">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="fbe8a-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="fbe8a-167">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="fbe8a-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="fbe8a-168">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-169">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-169">Known Issues</span></span>
<span data-ttu-id="fbe8a-170">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="fbe8a-171">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="fbe8a-172">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="fbe8a-173">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="fbe8a-174">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="fbe8a-175">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="fbe8a-176">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="fbe8a-177">&ensp;Piattaforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="fbe8a-178">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="fbe8a-179">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-180">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-180">What's new</span></span>

- <span data-ttu-id="fbe8a-181">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="fbe8a-182">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-183">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-183">Known Issues</span></span>
<span data-ttu-id="fbe8a-184">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-185">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="fbe8a-186">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fbe8a-187">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="fbe8a-188">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="fbe8a-189">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="fbe8a-190">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-191">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-191">What's new</span></span>

- <span data-ttu-id="fbe8a-192">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="fbe8a-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="fbe8a-193">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="fbe8a-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="fbe8a-194">Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi</span><span class="sxs-lookup"><span data-stu-id="fbe8a-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="fbe8a-195">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="fbe8a-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="fbe8a-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="fbe8a-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-197">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-197">Known Issues</span></span>
<span data-ttu-id="fbe8a-198">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-199">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="fbe8a-200">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fbe8a-201">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="fbe8a-202">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="fbe8a-203">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="fbe8a-204">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-205">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-205">What's new</span></span>

- <span data-ttu-id="fbe8a-206">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="fbe8a-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-207">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-207">Known Issues</span></span>
<span data-ttu-id="fbe8a-208">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-209">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="fbe8a-210">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="fbe8a-211">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="fbe8a-212">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="fbe8a-213">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="fbe8a-214">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-215">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-215">What's new</span></span>

- <span data-ttu-id="fbe8a-216">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="fbe8a-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="fbe8a-217">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="fbe8a-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="fbe8a-218">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="fbe8a-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="fbe8a-219">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="fbe8a-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-220">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-220">Known Issues</span></span>

<span data-ttu-id="fbe8a-221">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fbe8a-222">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="fbe8a-223">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="fbe8a-224">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="fbe8a-225">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="fbe8a-226">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="fbe8a-227">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-228">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-228">What's new</span></span>

- <span data-ttu-id="fbe8a-229">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="fbe8a-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="fbe8a-230">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="fbe8a-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="fbe8a-231">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="fbe8a-232">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-232">New management interfaces for:</span></span>
   - <span data-ttu-id="fbe8a-233">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="fbe8a-233">UDP Inspection</span></span>
   - <span data-ttu-id="fbe8a-234">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="fbe8a-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="fbe8a-235">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="fbe8a-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="fbe8a-236">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="fbe8a-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="fbe8a-237">Analisi Office modulo VBA migliorata</span><span class="sxs-lookup"><span data-stu-id="fbe8a-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-238">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-238">Known Issues</span></span>

<span data-ttu-id="fbe8a-239">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="fbe8a-240">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="fbe8a-241">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="fbe8a-242">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="fbe8a-243">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="fbe8a-244">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="fbe8a-245">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="fbe8a-246">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-246">What's new</span></span>

- <span data-ttu-id="fbe8a-247">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="fbe8a-247">Add more telemetry events</span></span>
- <span data-ttu-id="fbe8a-248">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="fbe8a-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="fbe8a-249">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="fbe8a-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="fbe8a-250">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="fbe8a-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="fbe8a-251">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbe8a-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="fbe8a-252">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="fbe8a-253">Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="fbe8a-254">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-254">Known Issues</span></span>
<span data-ttu-id="fbe8a-255">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-256">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="fbe8a-257">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="fbe8a-258">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="fbe8a-259">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="fbe8a-260">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="fbe8a-261">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-262">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-262">What's new</span></span>

- <span data-ttu-id="fbe8a-263">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="fbe8a-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="fbe8a-264">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="fbe8a-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-265">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-265">Known Issues</span></span>
<span data-ttu-id="fbe8a-266">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-267">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="fbe8a-268">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="fbe8a-269">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="fbe8a-270">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="fbe8a-271">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="fbe8a-272">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-273">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-273">What's new</span></span>

- <span data-ttu-id="fbe8a-274">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="fbe8a-275">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="fbe8a-276">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="fbe8a-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="fbe8a-277">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="fbe8a-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="fbe8a-278">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="fbe8a-278">Fixed registry query</span></span> 
- <span data-ttu-id="fbe8a-279">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="fbe8a-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-280">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-280">Known Issues</span></span>
<span data-ttu-id="fbe8a-281">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-282">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="fbe8a-283">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="fbe8a-284">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="fbe8a-285">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="fbe8a-286">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="fbe8a-287">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-288">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-288">What's new</span></span>

- <span data-ttu-id="fbe8a-289">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="fbe8a-289">Improved logging for scan events</span></span>
- <span data-ttu-id="fbe8a-290">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="fbe8a-291">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="fbe8a-292">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="fbe8a-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="fbe8a-293">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="fbe8a-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="fbe8a-294">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="fbe8a-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-295">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-295">Known Issues</span></span>
<span data-ttu-id="fbe8a-296">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-297">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="fbe8a-298">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="fbe8a-299">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="fbe8a-300">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="fbe8a-301">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="fbe8a-302">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-303">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-303">What's new</span></span>
- <span data-ttu-id="fbe8a-304">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="fbe8a-304">WDfilter improvements</span></span>
- <span data-ttu-id="fbe8a-305">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="fbe8a-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="fbe8a-306">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="fbe8a-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="fbe8a-307">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fbe8a-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="fbe8a-308">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="fbe8a-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="fbe8a-309">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="fbe8a-309">UEFI scan capability</span></span>
- <span data-ttu-id="fbe8a-310">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="fbe8a-311">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-311">Known Issues</span></span>
<span data-ttu-id="fbe8a-312">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-313">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="fbe8a-314">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="fbe8a-315">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="fbe8a-316">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="fbe8a-317">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="fbe8a-318">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fbe8a-319">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-319">What's new</span></span>

- <span data-ttu-id="fbe8a-320">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="fbe8a-321">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="fbe8a-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="fbe8a-322">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="fbe8a-323">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="fbe8a-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="fbe8a-324">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="fbe8a-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fbe8a-325">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-325">Known Issues</span></span>
<span data-ttu-id="fbe8a-326">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="fbe8a-327">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="fbe8a-328">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="fbe8a-329">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="fbe8a-330">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="fbe8a-331">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="fbe8a-332">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fbe8a-333">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="fbe8a-334">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-334">Known Issues</span></span>
<span data-ttu-id="fbe8a-335">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-336">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="fbe8a-337">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="fbe8a-338">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="fbe8a-339">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="fbe8a-340">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="fbe8a-341">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fbe8a-342">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-342">What's new</span></span>

- <span data-ttu-id="fbe8a-343">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="fbe8a-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="fbe8a-344">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="fbe8a-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="fbe8a-345">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="fbe8a-346">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="fbe8a-347">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="fbe8a-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fbe8a-348">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-348">Known Issues</span></span>

<span data-ttu-id="fbe8a-349">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="fbe8a-350">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="fbe8a-351">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-351">This update is:</span></span>
> - <span data-ttu-id="fbe8a-352">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="fbe8a-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="fbe8a-353">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="fbe8a-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="fbe8a-354">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="fbe8a-355">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="fbe8a-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="fbe8a-356">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fbe8a-357">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="fbe8a-358">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="fbe8a-359">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="fbe8a-360">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="fbe8a-361">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="fbe8a-362">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="fbe8a-363">Novità</span><span class="sxs-lookup"><span data-stu-id="fbe8a-363">What's new</span></span>

- <span data-ttu-id="fbe8a-364">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="fbe8a-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="fbe8a-365">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="fbe8a-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="fbe8a-366">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="fbe8a-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="fbe8a-367">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fbe8a-368">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="fbe8a-368">Known Issues</span></span>
<span data-ttu-id="fbe8a-369">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.18.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="fbe8a-370">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fbe8a-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="fbe8a-371">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="fbe8a-372">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="fbe8a-373">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="fbe8a-374">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="fbe8a-375">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="fbe8a-376">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="fbe8a-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="fbe8a-377">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="fbe8a-378">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="fbe8a-379">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="fbe8a-380">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="fbe8a-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="fbe8a-381">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="fbe8a-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="fbe8a-382">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="fbe8a-382">Windows 10 release</span></span>  |<span data-ttu-id="fbe8a-383">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="fbe8a-383">Platform version</span></span>  |<span data-ttu-id="fbe8a-384">Versione motore</span><span class="sxs-lookup"><span data-stu-id="fbe8a-384">Engine version</span></span> |<span data-ttu-id="fbe8a-385">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="fbe8a-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fbe8a-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="fbe8a-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="fbe8a-387">4.18.1909.6</span></span> |<span data-ttu-id="fbe8a-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="fbe8a-388">1.1.17000.2</span></span> | <span data-ttu-id="fbe8a-389">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-390">1909  (19H2)</span></span> |<span data-ttu-id="fbe8a-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fbe8a-391">4.18.1902.5</span></span> |<span data-ttu-id="fbe8a-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="fbe8a-392">1.1.16700.3</span></span> | <span data-ttu-id="fbe8a-393">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-394">1903  (19H1)</span></span> |<span data-ttu-id="fbe8a-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fbe8a-395">4.18.1902.5</span></span> |<span data-ttu-id="fbe8a-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="fbe8a-396">1.1.15600.4</span></span> | <span data-ttu-id="fbe8a-397">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-398">1809  (RS5)</span></span> |<span data-ttu-id="fbe8a-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="fbe8a-399">4.18.1807.18075</span></span> |<span data-ttu-id="fbe8a-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="fbe8a-400">1.1.15000.2</span></span> | <span data-ttu-id="fbe8a-401">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-402">1803  (RS4)</span></span> |<span data-ttu-id="fbe8a-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="fbe8a-403">4.13.17134.1</span></span> |<span data-ttu-id="fbe8a-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="fbe8a-404">1.1.14600.4</span></span> | <span data-ttu-id="fbe8a-405">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-406">1709  (RS3)</span></span> |<span data-ttu-id="fbe8a-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="fbe8a-407">4.12.16299.15</span></span> |<span data-ttu-id="fbe8a-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="fbe8a-408">1.1.14104.0</span></span> | <span data-ttu-id="fbe8a-409">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-410">1703  (RS2)</span></span> |<span data-ttu-id="fbe8a-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="fbe8a-411">4.11.15603.2</span></span> |<span data-ttu-id="fbe8a-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="fbe8a-412">1.1.13504.0</span></span> | <span data-ttu-id="fbe8a-413">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fbe8a-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-414">1607 (RS1)</span></span> |<span data-ttu-id="fbe8a-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="fbe8a-415">4.10.14393.3683</span></span> |<span data-ttu-id="fbe8a-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="fbe8a-416">1.1.12805.0</span></span> | <span data-ttu-id="fbe8a-417">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="fbe8a-418">Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="fbe8a-419">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="fbe8a-420">È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="fbe8a-421">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="fbe8a-422">Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="fbe8a-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="fbe8a-424">&ensp;Versione pacchetto: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="fbe8a-425">&ensp;Versione della piattaforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="fbe8a-426">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fbe8a-427">&ensp;Versione firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-428">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-428">Fixes</span></span>
- <span data-ttu-id="fbe8a-429">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-430">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-430">Additional information</span></span>
- <span data-ttu-id="fbe8a-431">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="fbe8a-433">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="fbe8a-434">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="fbe8a-435">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fbe8a-436">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-437">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-437">Fixes</span></span>
- <span data-ttu-id="fbe8a-438">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-439">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-439">Additional information</span></span>
- <span data-ttu-id="fbe8a-440">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="fbe8a-442">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="fbe8a-443">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="fbe8a-444">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="fbe8a-445">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-446">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-446">Fixes</span></span>
- <span data-ttu-id="fbe8a-447">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-448">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-448">Additional information</span></span>
- <span data-ttu-id="fbe8a-449">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="fbe8a-451">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="fbe8a-452">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="fbe8a-453">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fbe8a-454">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-455">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-455">Fixes</span></span>
- <span data-ttu-id="fbe8a-456">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-457">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-457">Additional information</span></span>
- <span data-ttu-id="fbe8a-458">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="fbe8a-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="fbe8a-460">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="fbe8a-461">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fbe8a-462">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fbe8a-463">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-464">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-464">Fixes</span></span>
- <span data-ttu-id="fbe8a-465">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-466">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-466">Additional information</span></span>
- <span data-ttu-id="fbe8a-467">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="fbe8a-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="fbe8a-469">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="fbe8a-470">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fbe8a-471">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="fbe8a-472">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-473">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-473">Fixes</span></span>
- <span data-ttu-id="fbe8a-474">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-475">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-475">Additional information</span></span>
- <span data-ttu-id="fbe8a-476">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="fbe8a-478">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="fbe8a-479">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fbe8a-480">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fbe8a-481">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-482">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-482">Fixes</span></span>
- <span data-ttu-id="fbe8a-483">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-484">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-484">Additional information</span></span>
- <span data-ttu-id="fbe8a-485">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="fbe8a-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="fbe8a-487">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="fbe8a-488">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fbe8a-489">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fbe8a-490">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-491">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-491">Fixes</span></span>
- <span data-ttu-id="fbe8a-492">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-493">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-493">Additional information</span></span>
- <span data-ttu-id="fbe8a-494">Firme Antivirus Microsoft Defender aggiornate</span><span class="sxs-lookup"><span data-stu-id="fbe8a-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="fbe8a-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="fbe8a-496">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fbe8a-497">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="fbe8a-498">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fbe8a-499">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-500">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-500">Fixes</span></span>
- <span data-ttu-id="fbe8a-501">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-502">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-502">Additional information</span></span>
- <span data-ttu-id="fbe8a-503">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fbe8a-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="fbe8a-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="fbe8a-505">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fbe8a-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fbe8a-506">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="fbe8a-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="fbe8a-507">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="fbe8a-508">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="fbe8a-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fbe8a-509">Correzioni</span><span class="sxs-lookup"><span data-stu-id="fbe8a-509">Fixes</span></span>
- <span data-ttu-id="fbe8a-510">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbe8a-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fbe8a-511">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-511">Additional information</span></span>
- <span data-ttu-id="fbe8a-512">È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="fbe8a-513">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe8a-513">Additional resources</span></span>

| <span data-ttu-id="fbe8a-514">Articolo</span><span class="sxs-lookup"><span data-stu-id="fbe8a-514">Article</span></span> | <span data-ttu-id="fbe8a-515">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="fbe8a-516">Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fbe8a-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="fbe8a-517">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="fbe8a-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="fbe8a-518">Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="fbe8a-519">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fbe8a-520">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="fbe8a-521">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="fbe8a-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="fbe8a-522">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="fbe8a-523">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="fbe8a-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="fbe8a-524">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="fbe8a-525">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="fbe8a-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fbe8a-526">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="fbe8a-527">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="fbe8a-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="fbe8a-528">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="fbe8a-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
