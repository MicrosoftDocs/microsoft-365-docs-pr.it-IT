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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314465"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="7b641-104">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="7b641-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="7b641-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7b641-105">**Applies to:**</span></span>

- [<span data-ttu-id="7b641-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7b641-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="7b641-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b641-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="7b641-108">Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco.</span><span class="sxs-lookup"><span data-stu-id="7b641-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="7b641-109">Assicurarsi di aggiornare la protezione antivirus, anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="7b641-110">Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:</span><span class="sxs-lookup"><span data-stu-id="7b641-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="7b641-111">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b641-111">Security intelligence updates</span></span>
- <span data-ttu-id="7b641-112">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="7b641-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="7b641-113">Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7b641-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="7b641-114">Aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b641-114">Security intelligence updates</span></span>

<span data-ttu-id="7b641-115">Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.</span><span class="sxs-lookup"><span data-stu-id="7b641-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="7b641-116">Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:</span><span class="sxs-lookup"><span data-stu-id="7b641-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="7b641-117">Antivirus Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="7b641-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="7b641-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="7b641-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="7b641-119">La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare.</span><span class="sxs-lookup"><span data-stu-id="7b641-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="7b641-120">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri).</span><span class="sxs-lookup"><span data-stu-id="7b641-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="7b641-121">Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="7b641-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="7b641-122">Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7b641-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="7b641-123">Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="7b641-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="7b641-124">Aggiornamenti dei prodotti</span><span class="sxs-lookup"><span data-stu-id="7b641-124">Product updates</span></span>

<span data-ttu-id="7b641-125">Antivirus Microsoft Defender aggiornamenti [mensili (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) noti come *aggiornamenti della piattaforma*.</span><span class="sxs-lookup"><span data-stu-id="7b641-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="7b641-126">È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b641-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="7b641-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="7b641-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="7b641-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7b641-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="7b641-129">Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.</span><span class="sxs-lookup"><span data-stu-id="7b641-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="7b641-130">Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="7b641-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="7b641-131">Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="7b641-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="7b641-132">In questo articolo sono elencate le modifiche incluse nel canale di rilascio generale.</span><span class="sxs-lookup"><span data-stu-id="7b641-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="7b641-133">[Vedi la versione più recente del canale generale qui](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span><span class="sxs-lookup"><span data-stu-id="7b641-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="7b641-134">Per altre informazioni sul processo di implementazione graduale e per altre informazioni sulla versione successiva, vedi Gestire il processo di implementazione graduale per gli aggiornamenti di [Microsoft Defender.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="7b641-135">Per ulteriori informazioni sugli aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza [Antivirus Microsoft Defender e altri antimalware Microsoft.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7b641-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="7b641-136">Versioni mensili di piattaforma e motore</span><span class="sxs-lookup"><span data-stu-id="7b641-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="7b641-137">Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="7b641-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="7b641-138">Tutti gli aggiornamenti contengono</span><span class="sxs-lookup"><span data-stu-id="7b641-138">All our updates contain</span></span> 
- <span data-ttu-id="7b641-139">miglioramenti delle prestazioni;</span><span class="sxs-lookup"><span data-stu-id="7b641-139">performance improvements;</span></span>
- <span data-ttu-id="7b641-140">miglioramenti di serviceability; e</span><span class="sxs-lookup"><span data-stu-id="7b641-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="7b641-141">miglioramenti all'integrazione (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="7b641-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="7b641-142">Giugno-2021 (Piattaforma: 4.18.2106.5 | Motore: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="7b641-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="7b641-143">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="7b641-144">&ensp;Rilasciato: **28 giugno 2021**</span><span class="sxs-lookup"><span data-stu-id="7b641-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="7b641-145">&ensp;Piattaforma: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="7b641-146">&ensp;Motore: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="7b641-147">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="7b641-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-148">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-148">What's new</span></span>
- <span data-ttu-id="7b641-149">Nuovi controlli per la gestione del processo di implementazione graduale degli aggiornamenti di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7b641-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="7b641-150">Vedi [Gestire il processo di implementazione graduale per gli aggiornamenti di Microsoft Defender.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="7b641-151">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="7b641-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="7b641-152">Miglioramenti all'implementazione delle definizioni antimalware</span><span class="sxs-lookup"><span data-stu-id="7b641-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="7b641-153">Ispezioni di eventi di rete perimetrale estesa</span><span class="sxs-lookup"><span data-stu-id="7b641-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-154">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-154">Known Issues</span></span>
<span data-ttu-id="7b641-155">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-156">Maggio-2021 (Piattaforma: 4.18.2105.4 | Motore: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="7b641-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="7b641-157">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="7b641-158">&ensp;Rilasciato: **3 giugno 2021**</span><span class="sxs-lookup"><span data-stu-id="7b641-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="7b641-159">&ensp;Piattaforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="7b641-160">&ensp;Motore: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="7b641-161">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="7b641-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-162">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-162">What's new</span></span>
- <span data-ttu-id="7b641-163">Miglioramenti al [monitoraggio del comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="7b641-164">Funzionalità [di filtro delle notifiche di](network-protection.md) protezione di rete fissa</span><span class="sxs-lookup"><span data-stu-id="7b641-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-165">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-165">Known Issues</span></span>
<span data-ttu-id="7b641-166">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-167">Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="7b641-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="7b641-168">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="7b641-169">&ensp;Rilasciato: **26 aprile 2021**  (Motore: 1.1.18100.6 rilasciato il 5 maggio 2021) &ensp; Piattaforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="7b641-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="7b641-170">&ensp;Motore: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="7b641-171">&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**</span><span class="sxs-lookup"><span data-stu-id="7b641-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-172">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-172">What's new</span></span>
- <span data-ttu-id="7b641-173">Logica di monitoraggio del comportamento aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="7b641-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="7b641-174">Rilevamento dei key logger in modalità kernel migliorato</span><span class="sxs-lookup"><span data-stu-id="7b641-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="7b641-175">Sono stati aggiunti nuovi controlli per gestire il processo di implementazione graduale per [gli aggiornamenti di Microsoft Defender](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="7b641-176">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-176">Known Issues</span></span>
<span data-ttu-id="7b641-177">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="7b641-178">Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="7b641-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="7b641-179">Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="7b641-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="7b641-180">Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7b641-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="7b641-181">Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="7b641-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="7b641-182">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="7b641-183">&ensp;Rilasciato: **2 aprile 2021**</span><span class="sxs-lookup"><span data-stu-id="7b641-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="7b641-184">&ensp;Piattaforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="7b641-185">&ensp;Motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="7b641-186">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-187">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-187">What's new</span></span>

- <span data-ttu-id="7b641-188">Miglioramento del motore di monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="7b641-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="7b641-189">Mitigazioni di attacchi bruti-forza-forza di rete espanse</span><span class="sxs-lookup"><span data-stu-id="7b641-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="7b641-190">Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="7b641-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-191">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-191">Known Issues</span></span>
<span data-ttu-id="7b641-192">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-193">Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="7b641-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="7b641-194">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="7b641-195">&ensp;Rilasciato: **9 marzo 2021**</span><span class="sxs-lookup"><span data-stu-id="7b641-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="7b641-196">&ensp;Piattaforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="7b641-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="7b641-197">&ensp;Motore: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="7b641-198">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-199">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-199">What's new</span></span>

- <span data-ttu-id="7b641-200">Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="7b641-201">Estendere l'ambito di protezione delle manomissioni</span><span class="sxs-lookup"><span data-stu-id="7b641-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-202">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-202">Known Issues</span></span>
<span data-ttu-id="7b641-203">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-204">Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="7b641-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="7b641-205">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7b641-206">&ensp;Rilasciato: **2 febbraio 2021**</span><span class="sxs-lookup"><span data-stu-id="7b641-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="7b641-207">&ensp;Piattaforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="7b641-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="7b641-208">&ensp;Motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="7b641-209">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-210">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-210">What's new</span></span>

- <span data-ttu-id="7b641-211">Miglioramenti al rilevamento degli exploit shellcode</span><span class="sxs-lookup"><span data-stu-id="7b641-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="7b641-212">Maggiore visibilità per i tentativi di furto delle credenziali</span><span class="sxs-lookup"><span data-stu-id="7b641-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="7b641-213">Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi</span><span class="sxs-lookup"><span data-stu-id="7b641-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="7b641-214">Supporto migliorato per l'emulazione x64 ARM x64</span><span class="sxs-lookup"><span data-stu-id="7b641-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="7b641-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="7b641-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-216">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-216">Known Issues</span></span>
<span data-ttu-id="7b641-217">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-218">Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="7b641-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="7b641-219">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7b641-220">&ensp;Rilasciato: **03 dicembre 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="7b641-221">&ensp;Piattaforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="7b641-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="7b641-222">&ensp;Motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="7b641-223">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-224">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-224">What's new</span></span>

- <span data-ttu-id="7b641-225">Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata</span><span class="sxs-lookup"><span data-stu-id="7b641-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-226">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-226">Known Issues</span></span>
<span data-ttu-id="7b641-227">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-228">Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="7b641-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="7b641-229">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="7b641-230">&ensp;Rilasciato: **29 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="7b641-231">&ensp;Piattaforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="7b641-232">&ensp;Motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="7b641-233">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-234">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-234">What's new</span></span>

- <span data-ttu-id="7b641-235">Nuove descrizioni per categorie di minacce speciali</span><span class="sxs-lookup"><span data-stu-id="7b641-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="7b641-236">Funzionalità di emulazione migliorate</span><span class="sxs-lookup"><span data-stu-id="7b641-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="7b641-237">Funzionalità di autorizzazione/blocco degli indirizzi host migliorate</span><span class="sxs-lookup"><span data-stu-id="7b641-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="7b641-238">Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali</span><span class="sxs-lookup"><span data-stu-id="7b641-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-239">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-239">Known Issues</span></span>

<span data-ttu-id="7b641-240">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7b641-241">Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="7b641-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="7b641-242">&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="7b641-243">&ensp;Rilasciato: **01 ottobre 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="7b641-244">&ensp;Piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="7b641-245">&ensp;Motore: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="7b641-246">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-247">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-247">What's new</span></span>

- <span data-ttu-id="7b641-248">Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="7b641-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="7b641-249">Gli eventi in formato XML sono ora supportati</span><span class="sxs-lookup"><span data-stu-id="7b641-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="7b641-250">Supporto CSP per ignorare le unioni di esclusione</span><span class="sxs-lookup"><span data-stu-id="7b641-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="7b641-251">Nuove interfacce di gestione per:</span><span class="sxs-lookup"><span data-stu-id="7b641-251">New management interfaces for:</span></span>
   - <span data-ttu-id="7b641-252">Ispezione UDP</span><span class="sxs-lookup"><span data-stu-id="7b641-252">UDP Inspection</span></span>
   - <span data-ttu-id="7b641-253">Protezione di rete in Server 2019</span><span class="sxs-lookup"><span data-stu-id="7b641-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="7b641-254">Esclusioni di indirizzi IP per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="7b641-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="7b641-255">Visibilità migliorata nelle misurazioni TPM</span><span class="sxs-lookup"><span data-stu-id="7b641-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="7b641-256">Analisi Office modulo VBA migliorata</span><span class="sxs-lookup"><span data-stu-id="7b641-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-257">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-257">Known Issues</span></span>

<span data-ttu-id="7b641-258">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="7b641-259">Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="7b641-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="7b641-260">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="7b641-261">&ensp;Rilasciato: **27 agosto 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="7b641-262">&ensp;Piattaforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="7b641-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="7b641-263">&ensp;Motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="7b641-264">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="7b641-265">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-265">What's new</span></span>

- <span data-ttu-id="7b641-266">Aggiungere altri eventi di telemetria</span><span class="sxs-lookup"><span data-stu-id="7b641-266">Add more telemetry events</span></span>
- <span data-ttu-id="7b641-267">Telemetria degli eventi di analisi migliorata</span><span class="sxs-lookup"><span data-stu-id="7b641-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="7b641-268">Monitoraggio del comportamento migliorato per le analisi della memoria</span><span class="sxs-lookup"><span data-stu-id="7b641-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="7b641-269">Analisi dei flussi macro migliorata</span><span class="sxs-lookup"><span data-stu-id="7b641-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="7b641-270">Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b641-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="7b641-271">[DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato.</span><span class="sxs-lookup"><span data-stu-id="7b641-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="7b641-272">Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="7b641-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="7b641-273">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-273">Known Issues</span></span>
<span data-ttu-id="7b641-274">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-275">Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="7b641-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="7b641-276">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="7b641-277">&ensp;Rilasciato: **28 luglio 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="7b641-278">&ensp;Piattaforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="7b641-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="7b641-279">&ensp;Motore: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="7b641-280">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-281">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-281">What's new</span></span>

- <span data-ttu-id="7b641-282">Telemetria migliorata per BITS</span><span class="sxs-lookup"><span data-stu-id="7b641-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="7b641-283">Convalida migliorata del certificato di firma del codice Authenticode</span><span class="sxs-lookup"><span data-stu-id="7b641-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-284">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-284">Known Issues</span></span>
<span data-ttu-id="7b641-285">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-286">Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="7b641-287">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="7b641-288">&ensp;Rilasciato: **22 giugno 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="7b641-289">&ensp;Piattaforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="7b641-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="7b641-290">&ensp;Motore: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="7b641-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="7b641-291">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-292">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-292">What's new</span></span>

- <span data-ttu-id="7b641-293">Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="7b641-294">Ignorare l'analisi di catchup aggressivo in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="7b641-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="7b641-295">Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo</span><span class="sxs-lookup"><span data-stu-id="7b641-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="7b641-296">Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata</span><span class="sxs-lookup"><span data-stu-id="7b641-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="7b641-297">Query del Registro di sistema fissa</span><span class="sxs-lookup"><span data-stu-id="7b641-297">Fixed registry query</span></span> 
- <span data-ttu-id="7b641-298">Randomizzazione fissa del tempo di analisi in ADMX</span><span class="sxs-lookup"><span data-stu-id="7b641-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-299">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-299">Known Issues</span></span>
<span data-ttu-id="7b641-300">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-301">Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="7b641-302">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="7b641-303">&ensp;Rilasciato: **26 maggio 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="7b641-304">&ensp;Piattaforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="7b641-305">&ensp;Motore: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="7b641-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="7b641-306">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-307">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-307">What's new</span></span>

- <span data-ttu-id="7b641-308">Registrazione migliorata per gli eventi di analisi</span><span class="sxs-lookup"><span data-stu-id="7b641-308">Improved logging for scan events</span></span>
- <span data-ttu-id="7b641-309">Gestione degli arresti anomalo in modalità utente migliorata.</span><span class="sxs-lookup"><span data-stu-id="7b641-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="7b641-310">Aggiunta dell'analisi degli eventi per la protezione anti-manomissione</span><span class="sxs-lookup"><span data-stu-id="7b641-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="7b641-311">Invio di esempio AMSI fisso</span><span class="sxs-lookup"><span data-stu-id="7b641-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="7b641-312">Risolto il blocco di AMSI Cloud</span><span class="sxs-lookup"><span data-stu-id="7b641-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="7b641-313">Risolto il registro di installazione dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b641-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-314">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-314">Known Issues</span></span>
<span data-ttu-id="7b641-315">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-316">Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="7b641-317">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="7b641-318">&ensp;Rilasciato: **30 aprile 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="7b641-319">&ensp;Piattaforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="7b641-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="7b641-320">&ensp;Motore: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="7b641-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="7b641-321">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-322">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-322">What's new</span></span>
- <span data-ttu-id="7b641-323">Miglioramenti di WDfilter</span><span class="sxs-lookup"><span data-stu-id="7b641-323">WDfilter improvements</span></span>
- <span data-ttu-id="7b641-324">Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="7b641-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="7b641-325">Informazioni sulla versione fisse nei dati di diagnostica e WMI</span><span class="sxs-lookup"><span data-stu-id="7b641-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="7b641-326">È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma</span><span class="sxs-lookup"><span data-stu-id="7b641-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="7b641-327">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="7b641-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="7b641-328">Funzionalità di analisi UEFI</span><span class="sxs-lookup"><span data-stu-id="7b641-328">UEFI scan capability</span></span>
- <span data-ttu-id="7b641-329">Estendere la registrazione per gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="7b641-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="7b641-330">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-330">Known Issues</span></span>
<span data-ttu-id="7b641-331">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-332">Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="7b641-333">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="7b641-334">&ensp;Rilasciato: **24 marzo 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="7b641-335">&ensp;Piattaforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="7b641-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="7b641-336">&ensp;Motore: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="7b641-337">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7b641-338">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-338">What's new</span></span>

- <span data-ttu-id="7b641-339">Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="7b641-340">Migliorare le funzionalità di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7b641-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="7b641-341">ridurre il timeout di Security Intelligence (5 min)</span><span class="sxs-lookup"><span data-stu-id="7b641-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="7b641-342">Estendere la funzionalità di log interno del motore AMSI</span><span class="sxs-lookup"><span data-stu-id="7b641-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="7b641-343">Migliorare la notifica per il blocco dei processi</span><span class="sxs-lookup"><span data-stu-id="7b641-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7b641-344">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-344">Known Issues</span></span>
<span data-ttu-id="7b641-345">[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.</span><span class="sxs-lookup"><span data-stu-id="7b641-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="7b641-346">Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="7b641-347">&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="7b641-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="7b641-348">&ensp;Rilasciato: **25 febbraio 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="7b641-349">&ensp;Piattaforma/client: **-**</span><span class="sxs-lookup"><span data-stu-id="7b641-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="7b641-350">&ensp;Motore: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="7b641-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="7b641-351">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7b641-352">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="7b641-353">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-353">Known Issues</span></span>
<span data-ttu-id="7b641-354">Nessun problema noto</span><span class="sxs-lookup"><span data-stu-id="7b641-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-355">Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="7b641-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="7b641-356">Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="7b641-357">Rilasciato: **30 gennaio 2020**</span><span class="sxs-lookup"><span data-stu-id="7b641-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="7b641-358">Piattaforma/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="7b641-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="7b641-359">Motore: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="7b641-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="7b641-360">&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**</span><span class="sxs-lookup"><span data-stu-id="7b641-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7b641-361">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-361">What's new</span></span>

- <span data-ttu-id="7b641-362">Risolto il problema BSOD in WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="7b641-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="7b641-363">Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete</span><span class="sxs-lookup"><span data-stu-id="7b641-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="7b641-364">Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7b641-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="7b641-365">estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="7b641-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="7b641-366">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="7b641-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7b641-367">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-367">Known Issues</span></span>

<span data-ttu-id="7b641-368">[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.</span><span class="sxs-lookup"><span data-stu-id="7b641-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="7b641-369">I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.</span><span class="sxs-lookup"><span data-stu-id="7b641-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="7b641-370">Questo aggiornamento è:</span><span class="sxs-lookup"><span data-stu-id="7b641-370">This update is:</span></span>
> - <span data-ttu-id="7b641-371">necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;</span><span class="sxs-lookup"><span data-stu-id="7b641-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="7b641-372">ha un flag di riavvio per i sistemi con problemi di sospensione;</span><span class="sxs-lookup"><span data-stu-id="7b641-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="7b641-373">viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="7b641-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="7b641-374">è classificato come aggiornamento a causa del requisito di riavvio; e</span><span class="sxs-lookup"><span data-stu-id="7b641-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="7b641-375">è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="7b641-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7b641-376">Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="7b641-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="7b641-377">Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="7b641-378">Rilasciato: **7 dicembre 2019**</span><span class="sxs-lookup"><span data-stu-id="7b641-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="7b641-379">Piattaforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="7b641-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="7b641-380">Motore: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="7b641-381">Fase di supporto: **nessun supporto**</span><span class="sxs-lookup"><span data-stu-id="7b641-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="7b641-382">Novità</span><span class="sxs-lookup"><span data-stu-id="7b641-382">What's new</span></span>

- <span data-ttu-id="7b641-383">Livello di traccia MpCmdRun fisso</span><span class="sxs-lookup"><span data-stu-id="7b641-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="7b641-384">Informazioni sulla versione wdFilter fisse</span><span class="sxs-lookup"><span data-stu-id="7b641-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="7b641-385">Migliorare le notifiche</span><span class="sxs-lookup"><span data-stu-id="7b641-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="7b641-386">aggiungere log MRT ai file di supporto</span><span class="sxs-lookup"><span data-stu-id="7b641-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7b641-387">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="7b641-387">Known Issues</span></span>
<span data-ttu-id="7b641-388">Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.18.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="7b641-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="7b641-389">Antivirus Microsoft Defender della piattaforma</span><span class="sxs-lookup"><span data-stu-id="7b641-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="7b641-390">Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile.</span><span class="sxs-lookup"><span data-stu-id="7b641-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="7b641-391">Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="7b641-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="7b641-392">La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:</span><span class="sxs-lookup"><span data-stu-id="7b641-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="7b641-393">**Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="7b641-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="7b641-394">**Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="7b641-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="7b641-395">Le versioni della piattaforma precedenti a N-2 non saranno più supportate.\*</span><span class="sxs-lookup"><span data-stu-id="7b641-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="7b641-396">\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="7b641-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="7b641-397">Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier).</span><span class="sxs-lookup"><span data-stu-id="7b641-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="7b641-398">Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (\*).</span><span class="sxs-lookup"><span data-stu-id="7b641-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="7b641-399">Versione della piattaforma inclusa con Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="7b641-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="7b641-400">La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:</span><span class="sxs-lookup"><span data-stu-id="7b641-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="7b641-401">Windows 10 rilascio</span><span class="sxs-lookup"><span data-stu-id="7b641-401">Windows 10 release</span></span>  |<span data-ttu-id="7b641-402">Versione della piattaforma</span><span class="sxs-lookup"><span data-stu-id="7b641-402">Platform version</span></span>  |<span data-ttu-id="7b641-403">Versione motore</span><span class="sxs-lookup"><span data-stu-id="7b641-403">Engine version</span></span> |<span data-ttu-id="7b641-404">Fase di supporto</span><span class="sxs-lookup"><span data-stu-id="7b641-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="7b641-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="7b641-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="7b641-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="7b641-406">4.18.1909.6</span></span> |<span data-ttu-id="7b641-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="7b641-407">1.1.17000.2</span></span> | <span data-ttu-id="7b641-408">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="7b641-409">1909  (19H2)</span></span> |<span data-ttu-id="7b641-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7b641-410">4.18.1902.5</span></span> |<span data-ttu-id="7b641-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="7b641-411">1.1.16700.3</span></span> | <span data-ttu-id="7b641-412">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="7b641-413">1903  (19H1)</span></span> |<span data-ttu-id="7b641-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7b641-414">4.18.1902.5</span></span> |<span data-ttu-id="7b641-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="7b641-415">1.1.15600.4</span></span> | <span data-ttu-id="7b641-416">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="7b641-417">1809  (RS5)</span></span> |<span data-ttu-id="7b641-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="7b641-418">4.18.1807.18075</span></span> |<span data-ttu-id="7b641-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="7b641-419">1.1.15000.2</span></span> | <span data-ttu-id="7b641-420">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="7b641-421">1803  (RS4)</span></span> |<span data-ttu-id="7b641-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="7b641-422">4.13.17134.1</span></span> |<span data-ttu-id="7b641-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="7b641-423">1.1.14600.4</span></span> | <span data-ttu-id="7b641-424">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="7b641-425">1709  (RS3)</span></span> |<span data-ttu-id="7b641-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="7b641-426">4.12.16299.15</span></span> |<span data-ttu-id="7b641-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="7b641-427">1.1.14104.0</span></span> | <span data-ttu-id="7b641-428">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="7b641-429">1703  (RS2)</span></span> |<span data-ttu-id="7b641-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="7b641-430">4.11.15603.2</span></span> |<span data-ttu-id="7b641-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="7b641-431">1.1.13504.0</span></span> | <span data-ttu-id="7b641-432">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7b641-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="7b641-433">1607 (RS1)</span></span> |<span data-ttu-id="7b641-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="7b641-434">4.10.14393.3683</span></span> |<span data-ttu-id="7b641-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="7b641-435">1.1.12805.0</span></span> | <span data-ttu-id="7b641-436">Supporto tecnico per gli aggiornamenti (solo)</span><span class="sxs-lookup"><span data-stu-id="7b641-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="7b641-437">Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="7b641-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="7b641-438">Aggiornamenti per Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="7b641-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="7b641-439">È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="7b641-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="7b641-440">Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="7b641-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="7b641-441">Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="7b641-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="7b641-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="7b641-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="7b641-443">&ensp;Versione pacchetto: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="7b641-444">&ensp;Versione della piattaforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="7b641-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="7b641-445">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7b641-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7b641-446">&ensp;Versione firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-447">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-447">Fixes</span></span>
- <span data-ttu-id="7b641-448">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-449">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-449">Additional information</span></span>
- <span data-ttu-id="7b641-450">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="7b641-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="7b641-452">&ensp;Versione pacchetto: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="7b641-453">&ensp;Versione della piattaforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="7b641-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="7b641-454">&ensp;Versione motore: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7b641-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7b641-455">&ensp;Versione firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-456">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-456">Fixes</span></span>
- <span data-ttu-id="7b641-457">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-458">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-458">Additional information</span></span>
- <span data-ttu-id="7b641-459">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="7b641-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="7b641-461">&ensp;Versione pacchetto: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="7b641-462">&ensp;Versione della piattaforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="7b641-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="7b641-463">&ensp;Versione motore: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="7b641-464">&ensp;Versione firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-465">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-465">Fixes</span></span>
- <span data-ttu-id="7b641-466">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-467">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-467">Additional information</span></span>
- <span data-ttu-id="7b641-468">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="7b641-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="7b641-470">&ensp;Versione pacchetto: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="7b641-471">&ensp;Versione della piattaforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="7b641-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="7b641-472">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7b641-473">&ensp;Versione firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-474">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-474">Fixes</span></span>
- <span data-ttu-id="7b641-475">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-476">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-476">Additional information</span></span>
- <span data-ttu-id="7b641-477">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="7b641-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="7b641-479">&ensp;Versione pacchetto: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="7b641-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="7b641-480">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7b641-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7b641-481">&ensp;Versione motore: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7b641-482">&ensp;Versione firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-483">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-483">Fixes</span></span>
- <span data-ttu-id="7b641-484">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-485">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-485">Additional information</span></span>
- <span data-ttu-id="7b641-486">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="7b641-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="7b641-488">&ensp;Versione pacchetto: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="7b641-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="7b641-489">&ensp;Versione della piattaforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7b641-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7b641-490">&ensp;Versione motore: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7b641-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="7b641-491">&ensp;Versione firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-492">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-492">Fixes</span></span>
- <span data-ttu-id="7b641-493">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-494">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-494">Additional information</span></span>
- <span data-ttu-id="7b641-495">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="7b641-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="7b641-497">&ensp;Versione pacchetto: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="7b641-498">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7b641-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7b641-499">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7b641-500">&ensp;Versione firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-501">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-501">Fixes</span></span>
- <span data-ttu-id="7b641-502">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-503">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-503">Additional information</span></span>
- <span data-ttu-id="7b641-504">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="7b641-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="7b641-506">&ensp;Versione pacchetto: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="7b641-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="7b641-507">&ensp;Versione della piattaforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7b641-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7b641-508">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7b641-509">&ensp;Versione firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-510">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-510">Fixes</span></span>
- <span data-ttu-id="7b641-511">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-512">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-512">Additional information</span></span>
- <span data-ttu-id="7b641-513">Firme Antivirus Microsoft Defender aggiornate</span><span class="sxs-lookup"><span data-stu-id="7b641-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="7b641-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="7b641-515">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7b641-516">&ensp;Versione della piattaforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7b641-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="7b641-517">&ensp;Versione motore: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7b641-518">&ensp;Versione firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-519">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-519">Fixes</span></span>
- <span data-ttu-id="7b641-520">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-521">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-521">Additional information</span></span>
- <span data-ttu-id="7b641-522">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7b641-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="7b641-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="7b641-524">&ensp;Versione pacchetto: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7b641-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7b641-525">&ensp;Versione della piattaforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="7b641-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="7b641-526">&ensp;Versione motore: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7b641-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="7b641-527">&ensp;Versione firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="7b641-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7b641-528">Correzioni</span><span class="sxs-lookup"><span data-stu-id="7b641-528">Fixes</span></span>
- <span data-ttu-id="7b641-529">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b641-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7b641-530">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-530">Additional information</span></span>
- <span data-ttu-id="7b641-531">È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="7b641-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="7b641-532">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b641-532">Additional resources</span></span>

| <span data-ttu-id="7b641-533">Articolo</span><span class="sxs-lookup"><span data-stu-id="7b641-533">Article</span></span> | <span data-ttu-id="7b641-534">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b641-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="7b641-535">Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7b641-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="7b641-536">Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="7b641-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="7b641-537">Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.</span><span class="sxs-lookup"><span data-stu-id="7b641-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="7b641-538">Gestire la modalità di download e applicazione degli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="7b641-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7b641-539">Gli aggiornamenti di protezione possono essere recapitati tramite molte origini.</span><span class="sxs-lookup"><span data-stu-id="7b641-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="7b641-540">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="7b641-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="7b641-541">È possibile pianificare quando scaricare gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="7b641-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="7b641-542">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="7b641-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="7b641-543">Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="7b641-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="7b641-544">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="7b641-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7b641-545">È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="7b641-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="7b641-546">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="7b641-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="7b641-547">È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="7b641-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
