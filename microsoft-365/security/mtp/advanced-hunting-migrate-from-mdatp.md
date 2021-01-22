---
title: Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint
description: Informazioni su come modificare le query di Microsoft Defender for Endpoint in modo da poterle usare in Microsoft 365 Defender
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, microsoft defender atp, mdatp, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932311"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="d918a-104">Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="d918a-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d918a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d918a-105">**Applies to:**</span></span>
- <span data-ttu-id="d918a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d918a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d918a-107">Spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender for Endpoint per cercare in modo proattivo le minacce usando un set più ampio di dati.</span><span class="sxs-lookup"><span data-stu-id="d918a-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="d918a-108">In Microsoft 365 Defender, si ottiene l'accesso ai dati da altre soluzioni di sicurezza di Microsoft 365, tra cui:</span><span class="sxs-lookup"><span data-stu-id="d918a-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="d918a-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d918a-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d918a-110">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="d918a-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="d918a-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d918a-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d918a-112">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="d918a-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="d918a-113">La maggior parte dei clienti di Microsoft Defender per endpoint [può usare Microsoft 365 Defender senza licenze aggiuntive.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="d918a-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="d918a-114">Per avviare la transizione dei flussi di lavoro di ricerca avanzata da Defender per Endpoint, [attivare Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="d918a-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="d918a-115">È possibile eseguire la transizione senza influire sui flussi di lavoro di Defender for Endpoint esistenti.</span><span class="sxs-lookup"><span data-stu-id="d918a-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="d918a-116">Le query salvate rimangono intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="d918a-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="d918a-117">Tuttavia, saranno visibili in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d918a-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="d918a-118">Tabelle dello schema solo in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d918a-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="d918a-119">Lo schema di ricerca avanzata di [Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornisce tabelle aggiuntive contenenti i dati di varie soluzioni di sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d918a-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="d918a-120">Le tabelle seguenti sono disponibili solo in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d918a-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="d918a-121">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="d918a-121">Table name</span></span> | <span data-ttu-id="d918a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d918a-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="d918a-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="d918a-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="d918a-124">File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="d918a-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="d918a-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="d918a-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="d918a-126">Avvisi di Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity, incluse le informazioni sulla gravità e le categorie di minacce</span><span class="sxs-lookup"><span data-stu-id="d918a-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="d918a-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="d918a-128">Attività relative ai file nelle app e nei servizi cloud</span><span class="sxs-lookup"><span data-stu-id="d918a-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="d918a-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="d918a-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="d918a-130">Informazioni sui file allegati ai messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d918a-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="d918a-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d918a-132">Eventi di posta elettronica di Microsoft 365, inclusi gli eventi di recapito e blocco della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d918a-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="d918a-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="d918a-134">Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha recapitato i messaggi di posta elettronica alla cassetta postale del destinatario</span><span class="sxs-lookup"><span data-stu-id="d918a-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="d918a-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="d918a-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="d918a-136">Informazioni sugli URL nei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d918a-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="d918a-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="d918a-138">Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="d918a-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="d918a-139">In questa tabella viene illustrata una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="d918a-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="d918a-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="d918a-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="d918a-141">Informazioni sull'account da varie origini, tra cui Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d918a-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="d918a-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="d918a-143">Eventi di autenticazione in Active Directory e Nei servizi online Microsoft</span><span class="sxs-lookup"><span data-stu-id="d918a-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="d918a-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="d918a-145">Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini</span><span class="sxs-lookup"><span data-stu-id="d918a-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="d918a-146">Tabella Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="d918a-147">Le `AlertInfo` tabelle `AlertEvidence` e `DeviceAlertEvents` sostituiscono la tabella nello schema di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="d918a-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="d918a-148">Oltre ai dati relativi agli avvisi per i dispositivi, queste due tabelle includono dati sugli avvisi per identità, app e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d918a-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="d918a-149">Utilizzare la tabella seguente per verificare il mapping `DeviceAlertEvents` delle colonne alle colonne nelle tabelle e nelle `AlertInfo` `AlertEvidence` colonne.</span><span class="sxs-lookup"><span data-stu-id="d918a-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="d918a-150">Oltre alle colonne della tabella seguente, la tabella include molte altre colonne che forniscono un quadro più olistico degli avvisi `AlertEvidence` provenienti da varie origini.</span><span class="sxs-lookup"><span data-stu-id="d918a-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="d918a-151">Visualizzare tutte le colonne AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="d918a-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="d918a-152">Colonna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="d918a-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="d918a-153">Dove trovare gli stessi dati in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d918a-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="d918a-154">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="d918a-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="d918a-155">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="d918a-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="d918a-156">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="d918a-157">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="d918a-158">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="d918a-159">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="d918a-160">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="d918a-161">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="d918a-162">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="d918a-163">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="d918a-164">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="d918a-165">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="d918a-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="d918a-166">Questa colonna viene in genere usata in Microsoft Defender for Endpoint per individuare i record correlati in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="d918a-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="d918a-167">In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="d918a-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="d918a-168">Questa colonna viene in genere usata in Microsoft Defender per Endpoint per ulteriori informazioni sugli eventi in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="d918a-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="d918a-169">In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="d918a-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="d918a-170">Modificare le query esistenti di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d918a-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="d918a-171">Le query di Microsoft Defender per endpoint funzionano così come sono, a meno che non fanno riferimento alla `DeviceAlertEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="d918a-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="d918a-172">Per usare queste query in Microsoft 365 Defender, applicare queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="d918a-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="d918a-173">Sostituire `DeviceAlertEvents` con `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="d918a-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="d918a-174">Unire le `AlertInfo` tabelle e le tabelle per ottenere dati `AlertEvidence` `AlertId` equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d918a-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="d918a-175">Query originale</span><span class="sxs-lookup"><span data-stu-id="d918a-175">Original query</span></span>
<span data-ttu-id="d918a-176">La query seguente usa `DeviceAlertEvents` Microsoft Defender per Endpoint per ottenere gli avvisi che coinvolgono _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="d918a-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="d918a-177">Query modificata</span><span class="sxs-lookup"><span data-stu-id="d918a-177">Modified query</span></span>
<span data-ttu-id="d918a-178">La query seguente è stata modificata per l'uso in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d918a-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="d918a-179">Invece di controllare il nome del file direttamente da , esegue il join e verifica il `DeviceAlertEvents` nome del file nella `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="d918a-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="d918a-180">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d918a-180">Related topics</span></span>
- [<span data-ttu-id="d918a-181">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d918a-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d918a-182">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d918a-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d918a-183">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="d918a-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d918a-184">Ricerca avanzata in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="d918a-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)