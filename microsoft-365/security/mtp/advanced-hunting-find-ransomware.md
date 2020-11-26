---
title: Trovare ransomware con caccia avanzata
description: Utilizzare la ricerca avanzata per individuare i dispositivi potenzialmente danneggiati da ransomware.
keywords: caccia avanzata, ransomware, caccia alle minacce, Cyber-caccia alle minacce, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: aaee2af4b3df849b57b8e1c18ab330603042fe96
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422905"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="ad35b-104">Cerca per ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ad35b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ad35b-105">**Applies to:**</span></span>
- <span data-ttu-id="ad35b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad35b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ad35b-107">Il ransomware si è evoluto rapidamente dall'essere un semplice malware che influisce sui singoli utenti di computer a una minaccia aziendale che ha un impatto grave sulle industrie e sulle istituzioni governative.</span><span class="sxs-lookup"><span data-stu-id="ad35b-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="ad35b-108">Anche se [Microsoft 365 Defender](microsoft-threat-protection.md) fornisce numerose funzionalità che consentono di rilevare e bloccare ransomware e le attività di intrusione associate, l'esecuzione di controlli proattivi per i segni di compromesso può contribuire a garantire la protezione della rete.</span><span class="sxs-lookup"><span data-stu-id="ad35b-108">While [Microsoft 365 Defender](microsoft-threat-protection.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="ad35b-109">Informazioni sul ransomware gestito dall'uomo</span><span class="sxs-lookup"><span data-stu-id="ad35b-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="ad35b-110">Con la [ricerca avanzata](advanced-hunting-overview.md) in Microsoft 365 Defender, è possibile creare query che consentono di individuare singoli elementi associati all'attività ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="ad35b-111">È inoltre possibile eseguire query più sofisticate in grado di cercare i segni di attività e valutare tali segni per individuare i dispositivi che richiedono attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="ad35b-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="ad35b-112">Segni dell'attività ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-112">Signs of ransomware activity</span></span>
<span data-ttu-id="ad35b-113">Microsoft Security ricercatori hanno osservato vari manufatti comuni ma sottili in molte campagne ransomware lanciate da intrusi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="ad35b-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="ad35b-114">Questi segni prevedono principalmente l'utilizzo di strumenti di sistema per preparare la crittografia, impedire il rilevamento e cancellare le evidenze forensi.</span><span class="sxs-lookup"><span data-stu-id="ad35b-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="ad35b-115">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-115">Ransomware activity</span></span> | <span data-ttu-id="ad35b-116">Strumenti comuni</span><span class="sxs-lookup"><span data-stu-id="ad35b-116">Common tools</span></span> | <span data-ttu-id="ad35b-117">Intento</span><span class="sxs-lookup"><span data-stu-id="ad35b-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="ad35b-118">Interrompi processi</span><span class="sxs-lookup"><span data-stu-id="ad35b-118">Stop processes</span></span> | <span data-ttu-id="ad35b-119">_taskkill.exe_, _net stop_</span><span class="sxs-lookup"><span data-stu-id="ad35b-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="ad35b-120">Verificare che i file destinati alla crittografia non siano bloccati da diverse applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ad35b-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="ad35b-121">Disattiva servizi</span><span class="sxs-lookup"><span data-stu-id="ad35b-121">Turn off services</span></span> | <span data-ttu-id="ad35b-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-122">_sc.exe_</span></span> | <span data-ttu-id="ad35b-123">-Verificare che i file destinati alla crittografia non siano bloccati da diverse applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ad35b-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="ad35b-124">-Impedire al software di sicurezza di interrompere la crittografia e altre attività ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="ad35b-125">-Arrestare il software di backup dalla creazione di copie recuperabili.</span><span class="sxs-lookup"><span data-stu-id="ad35b-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="ad35b-126">Eliminare i registri e i file</span><span class="sxs-lookup"><span data-stu-id="ad35b-126">Delete logs and files</span></span> | <span data-ttu-id="ad35b-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="ad35b-128">Rimuovere le evidenze forensi.</span><span class="sxs-lookup"><span data-stu-id="ad35b-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="ad35b-129">Eliminare le copie shadow</span><span class="sxs-lookup"><span data-stu-id="ad35b-129">Delete shadow copies</span></span>  | <span data-ttu-id="ad35b-130">_vsadmin.exe_, _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="ad35b-131">Rimuovere le copie shadow dell'unità che possono essere utilizzate per recuperare i file crittografati.</span><span class="sxs-lookup"><span data-stu-id="ad35b-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="ad35b-132">Eliminare e arrestare i backup</span><span class="sxs-lookup"><span data-stu-id="ad35b-132">Delete and stop backups</span></span> | <span data-ttu-id="ad35b-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-133">_wbadmin.exe_</span></span> | <span data-ttu-id="ad35b-134">Eliminare i backup esistenti e arrestare le attività di backup pianificate, impedendo il ripristino dopo la crittografia.</span><span class="sxs-lookup"><span data-stu-id="ad35b-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="ad35b-135">Modificare le impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="ad35b-135">Modify boot settings</span></span> | <span data-ttu-id="ad35b-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-136">_bcdedit.exe_</span></span> | <span data-ttu-id="ad35b-137">Disattivare gli avvisi e le correzioni automatiche dopo gli errori di avvio che possono essere causati dal processo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ad35b-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="ad35b-138">Disattiva gli strumenti di ripristino</span><span class="sxs-lookup"><span data-stu-id="ad35b-138">Turn off recovery tools</span></span> | <span data-ttu-id="ad35b-139">_schtasks.exe_, _regedit.exe_,</span><span class="sxs-lookup"><span data-stu-id="ad35b-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="ad35b-140">Disattivare Ripristino configurazione di sistema e altre opzioni di ripristino del sistema.</span><span class="sxs-lookup"><span data-stu-id="ad35b-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="ad35b-141">Controllare i singoli segni dell'attività ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="ad35b-142">Molte attività che costituiscono il comportamento di ransomware, incluse le attività descritte nella sezione precedente, possono essere benigne.</span><span class="sxs-lookup"><span data-stu-id="ad35b-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="ad35b-143">Quando si utilizzano le query seguenti per individuare ransomware, eseguire più di una query per verificare se gli stessi dispositivi presentano vari segni di possibili attività ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="ad35b-144">Arresto di più processi tramite _taskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="ad35b-145">Questa query consente di verificare che i tentativi di arrestare almeno 10 processi distinti utilizzino l'utilità _taskkill.exe_ .</span><span class="sxs-lookup"><span data-stu-id="ad35b-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="ad35b-146">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="ad35b-147">Interruzione dei processi tramite _net stop_</span><span class="sxs-lookup"><span data-stu-id="ad35b-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="ad35b-148">Questa query consente di verificare che i tentativi di arrestare almeno 10 processi distinti utilizzino il comando _net stop_ .</span><span class="sxs-lookup"><span data-stu-id="ad35b-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="ad35b-149">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="ad35b-150">Eliminazione dei dati su più unità tramite _cipher.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="ad35b-151">Questa query consente di controllare i tentativi di eliminazione dei dati su più unità tramite _cipher.exe_.</span><span class="sxs-lookup"><span data-stu-id="ad35b-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="ad35b-152">Questa attività è in genere fatta da ransomware per impedire il ripristino dei dati dopo la crittografia.</span><span class="sxs-lookup"><span data-stu-id="ad35b-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="ad35b-153">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="ad35b-154">Eliminazione delle evidenze forensi dai registri eventi mediante _wevtutil_</span><span class="sxs-lookup"><span data-stu-id="ad35b-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="ad35b-155">In questa query vengono verificati i tentativi di cancellare almeno 10 voci di log dai registri eventi mediante _wevtutil_.</span><span class="sxs-lookup"><span data-stu-id="ad35b-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="ad35b-156">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="ad35b-157">Disattivazione dei servizi tramite _sc.exe_</span><span class="sxs-lookup"><span data-stu-id="ad35b-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="ad35b-158">Questa query verifica se i tentativi di disattivazione di almeno 10 servizi esistenti vengono eseguiti utilizzando _sc.exe_.</span><span class="sxs-lookup"><span data-stu-id="ad35b-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="ad35b-159">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="ad35b-160">Disattivazione del ripristino di sistema</span><span class="sxs-lookup"><span data-stu-id="ad35b-160">Turning off System Restore</span></span>
<span data-ttu-id="ad35b-161">Questa query identifica i tentativi di arrestare il ripristino del sistema e impedire al sistema di creare punti di ripristino, che possono essere utilizzati per recuperare i dati crittografati da ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="ad35b-162">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a><span data-ttu-id="ad35b-163">Eliminazione dei backup</span><span class="sxs-lookup"><span data-stu-id="ad35b-163">Backup deletion</span></span>
<span data-ttu-id="ad35b-164">Questa query identifica l'utilizzo di _wmic.exe_ per eliminare gli snapshot della copia shadow prima della crittografia.</span><span class="sxs-lookup"><span data-stu-id="ad35b-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="ad35b-165">Esegui query</span><span class="sxs-lookup"><span data-stu-id="ad35b-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="ad35b-166">Controllare se sono presenti più segni di attività ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="ad35b-167">Invece di eseguire diverse query separatamente, è anche possibile utilizzare una query completa che consente di verificare la possibilità di individuare più segni di attività ransomware per identificare i dispositivi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="ad35b-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="ad35b-168">La query consolidata seguente:</span><span class="sxs-lookup"><span data-stu-id="ad35b-168">The following consolidated  query:</span></span>
- <span data-ttu-id="ad35b-169">Cerca entrambi i segni relativamente concreti e sottili dell'attività ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="ad35b-170">Pesa la presenza di questi segni</span><span class="sxs-lookup"><span data-stu-id="ad35b-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="ad35b-171">Identifica i dispositivi con una maggiore probabilità di essere bersagli di ransomware</span><span class="sxs-lookup"><span data-stu-id="ad35b-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="ad35b-172">Quando viene eseguito, questa query consolidata restituisce un elenco di dispositivi che presentano più segni di attacco.</span><span class="sxs-lookup"><span data-stu-id="ad35b-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="ad35b-173">Viene inoltre visualizzato il numero di ogni tipo di attività ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="ad35b-174">Per eseguire questa query consolidata, copiarla direttamente nell' [editor di query di ricerca avanzata](https://security.microsoft.com/advanced-hunting).</span><span class="sxs-lookup"><span data-stu-id="ad35b-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="ad35b-175">Comprendere e ottimizzare i risultati della query</span><span class="sxs-lookup"><span data-stu-id="ad35b-175">Understand and tweak the query results</span></span>
<span data-ttu-id="ad35b-176">La query consolidata restituisce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad35b-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="ad35b-177">**DeviceID**— identifica il dispositivo coinvolto</span><span class="sxs-lookup"><span data-stu-id="ad35b-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="ad35b-178">**Timestamp**-prima volta che è stato osservato un segno di attività ransomware nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="ad35b-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="ad35b-179">**Segni di attività specifici**, ovvero il numero di ogni segno visualizzato in più colonne, ad esempio _BcdEdit_ o _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="ad35b-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="ad35b-180">**TotalEvidenceCount**-numero di segni osservati</span><span class="sxs-lookup"><span data-stu-id="ad35b-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="ad35b-181">**UniqueEvidenceCount**-numero di tipi di segni osservati</span><span class="sxs-lookup"><span data-stu-id="ad35b-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![Immagine dei risultati delle query per l'attività ransomware](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="ad35b-183">*Risultati delle query che mostrano i dispositivi coinvolti e i conteggi di vari segni dell'attività ransomware*</span><span class="sxs-lookup"><span data-stu-id="ad35b-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="ad35b-184">Per impostazione predefinita, il risultato della query elenca solo i dispositivi con più di due tipi di attività ransomware.</span><span class="sxs-lookup"><span data-stu-id="ad35b-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="ad35b-185">Per visualizzare tutti i dispositivi con qualsiasi segno di attività ransomware, modificare l' `where` operatore seguente e impostare il numero su zero (0).</span><span class="sxs-lookup"><span data-stu-id="ad35b-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="ad35b-186">Per visualizzare meno dispositivi, impostare un numero più alto.</span><span class="sxs-lookup"><span data-stu-id="ad35b-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="ad35b-187">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ad35b-187">Related topics</span></span>
- [<span data-ttu-id="ad35b-188">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ad35b-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ad35b-189">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="ad35b-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ad35b-190">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="ad35b-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ad35b-191">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="ad35b-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ad35b-192">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="ad35b-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ad35b-193">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="ad35b-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)