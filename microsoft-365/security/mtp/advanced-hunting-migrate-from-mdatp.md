---
title: Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender ATP
description: Informazioni su come modificare le query di Microsoft Defender ATP in modo che sia possibile utilizzarle in Microsoft Threat Protection
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Microsoft Defender ATP, mdatp, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, mapping
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
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1738180e192baafa60f76fada1e433319922b91
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412683"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="f15e1-104">Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f15e1-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f15e1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f15e1-105">**Applies to:**</span></span>
- <span data-ttu-id="f15e1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f15e1-107">Spostare i flussi di lavoro avanzati di caccia da Microsoft Defender ATP per cercare in modo proattivo le minacce utilizzando un set di dati più ampio.</span><span class="sxs-lookup"><span data-stu-id="f15e1-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="f15e1-108">In Microsoft Threat Protection, è possibile accedere ai dati di altre soluzioni di sicurezza di Microsoft 365, tra cui:</span><span class="sxs-lookup"><span data-stu-id="f15e1-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="f15e1-109">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="f15e1-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="f15e1-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f15e1-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f15e1-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="f15e1-113">La maggior parte dei clienti Microsoft Defender ATP può [utilizzare Microsoft Threat Protection senza licenze aggiuntive](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f15e1-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="f15e1-114">Per iniziare a eseguire la transizione dei flussi di lavoro avanzati di caccia da Microsoft Defender ATP, [attivare Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f15e1-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="f15e1-115">È possibile eseguire la transizione senza influire sui flussi di lavoro di Microsoft Defender ATP esistenti.</span><span class="sxs-lookup"><span data-stu-id="f15e1-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="f15e1-116">Le query salvate restano intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="f15e1-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="f15e1-117">Tuttavia, saranno visibili in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f15e1-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="f15e1-118">Tabelle dello schema solo in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="f15e1-119">Lo [schema di protezione avanzata di Microsoft Threat Protection](advanced-hunting-schema-tables.md) fornisce ulteriori tabelle contenenti dati provenienti da varie soluzioni di sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f15e1-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="f15e1-120">Le tabelle seguenti sono disponibili solo in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="f15e1-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="f15e1-121">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="f15e1-121">Table name</span></span> | <span data-ttu-id="f15e1-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f15e1-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="f15e1-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f15e1-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="f15e1-124">File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="f15e1-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="f15e1-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="f15e1-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="f15e1-126">Avvisi di Microsoft Defender ATP, Office 365 ATP, Microsoft cloud app Security e Azure ATP, incluse le informazioni sulla gravità e le categorie di minacce</span><span class="sxs-lookup"><span data-stu-id="f15e1-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="f15e1-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="f15e1-128">Attività correlate ai file nelle app e nei servizi cloud</span><span class="sxs-lookup"><span data-stu-id="f15e1-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="f15e1-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="f15e1-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="f15e1-130">Informazioni sui file allegati ai messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f15e1-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="f15e1-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="f15e1-132">Microsoft 365 eventi di posta elettronica, inclusi gli eventi di blocco e recapito della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f15e1-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="f15e1-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="f15e1-134">Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha inviato i messaggi di posta elettronica alla cassetta postale del destinatario</span><span class="sxs-lookup"><span data-stu-id="f15e1-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="f15e1-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="f15e1-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="f15e1-136">Informazioni sugli URL nei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f15e1-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="f15e1-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="f15e1-138">Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f15e1-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f15e1-139">In questa tabella viene illustrata una serie di eventi relativi a identità e eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="f15e1-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="f15e1-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f15e1-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="f15e1-141">Informazioni sugli account provenienti da origini diverse, tra cui Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f15e1-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="f15e1-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="f15e1-143">Eventi di autenticazione in Active Directory e nei Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="f15e1-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="f15e1-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="f15e1-145">Query per gli oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini</span><span class="sxs-lookup"><span data-stu-id="f15e1-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="f15e1-146">Tabella DeviceAlertEvents map</span><span class="sxs-lookup"><span data-stu-id="f15e1-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="f15e1-147">Le `AlertInfo` `AlertEvidence` tabelle e sostituiscono la `DeviceAlertEvents` tabella nello schema ATP Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f15e1-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="f15e1-148">Oltre ai dati relativi agli avvisi dei dispositivi, queste due tabelle includono dati relativi agli avvisi relativi a identità, app e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f15e1-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="f15e1-149">Utilizzare la tabella seguente per controllare in che modo le `DeviceAlertEvents` colonne devono essere mappate alle colonne nelle `AlertInfo` `AlertEvidence` tabelle e.</span><span class="sxs-lookup"><span data-stu-id="f15e1-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="f15e1-150">Oltre alle colonne nella tabella seguente, la `AlertEvidence` tabella include molte altre colonne che forniscono un'immagine più olistica degli avvisi provenienti da varie origini.</span><span class="sxs-lookup"><span data-stu-id="f15e1-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="f15e1-151">Vedere tutte le colonne di AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f15e1-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="f15e1-152">Colonna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="f15e1-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="f15e1-153">Dove trovare gli stessi dati in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="f15e1-154">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="f15e1-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="f15e1-155">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="f15e1-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="f15e1-156">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="f15e1-157">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="f15e1-158">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="f15e1-159">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="f15e1-160">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="f15e1-161">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="f15e1-162">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="f15e1-163">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="f15e1-164">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="f15e1-165">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="f15e1-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="f15e1-166">Questa colonna è in genere utilizzata in Microsoft Defender ATP per individuare i record correlati in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="f15e1-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="f15e1-167">In Microsoft Threat Protection, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="f15e1-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="f15e1-168">Questa colonna è in genere utilizzata in Microsoft Defender ATP per ulteriori informazioni sugli eventi in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="f15e1-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="f15e1-169">In Microsoft Threat Protection, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="f15e1-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="f15e1-170">Modificare le query esistenti di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f15e1-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="f15e1-171">Le query di Microsoft Defender ATP funzioneranno così come sono, a meno che non facciano riferimento alla `DeviceAlertEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="f15e1-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="f15e1-172">Per utilizzare queste query in Microsoft Threat Protection, applicare le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="f15e1-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="f15e1-173">Sostituisci `DeviceAlertEvents` con `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="f15e1-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="f15e1-174">Aggiungere la `AlertInfo` e le `AlertEvidence` tabelle `AlertId` per ottenere dati equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f15e1-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="f15e1-175">Query originale</span><span class="sxs-lookup"><span data-stu-id="f15e1-175">Original query</span></span>
<span data-ttu-id="f15e1-176">La query seguente utilizza `DeviceAlertEvents` Microsoft Defender ATP per ottenere gli avvisi che coinvolgono _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="f15e1-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="f15e1-177">Query modificata</span><span class="sxs-lookup"><span data-stu-id="f15e1-177">Modified query</span></span>
<span data-ttu-id="f15e1-178">La query seguente è stata regolata per l'utilizzo in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f15e1-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="f15e1-179">Invece di controllare direttamente il nome del file `DeviceAlertEvents` , si unisce `AlertEvidence` e controlla il nome del file in quella tabella.</span><span class="sxs-lookup"><span data-stu-id="f15e1-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="f15e1-180">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f15e1-180">Related topics</span></span>
- [<span data-ttu-id="f15e1-181">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f15e1-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f15e1-182">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="f15e1-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f15e1-183">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="f15e1-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f15e1-184">Ricerca avanzata in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f15e1-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)