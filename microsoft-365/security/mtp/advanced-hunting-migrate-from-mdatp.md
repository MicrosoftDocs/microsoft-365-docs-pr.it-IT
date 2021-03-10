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
ms.openlocfilehash: 4d29f4f3df3d65ad72a19f059763523d7f7cba31
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597005"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="a65a3-104">Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="a65a3-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a65a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a65a3-105">**Applies to:**</span></span>
- <span data-ttu-id="a65a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65a3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a65a3-107">Spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender for Endpoint per cercare in modo proattivo le minacce usando un set più ampio di dati.</span><span class="sxs-lookup"><span data-stu-id="a65a3-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="a65a3-108">In Microsoft 365 Defender, si ottiene l'accesso ai dati da altre soluzioni di sicurezza di Microsoft 365, tra cui:</span><span class="sxs-lookup"><span data-stu-id="a65a3-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="a65a3-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a65a3-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a65a3-110">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a65a3-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="a65a3-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a65a3-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a65a3-112">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="a65a3-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="a65a3-113">La maggior parte dei clienti di Microsoft Defender per endpoint [può usare Microsoft 365 Defender senza licenze aggiuntive.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="a65a3-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="a65a3-114">Per avviare la transizione dei flussi di lavoro di ricerca avanzata da Defender per Endpoint, [attivare Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="a65a3-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="a65a3-115">È possibile eseguire la transizione senza influire sui flussi di lavoro di Defender for Endpoint esistenti.</span><span class="sxs-lookup"><span data-stu-id="a65a3-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="a65a3-116">Le query salvate rimangono intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="a65a3-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="a65a3-117">Tuttavia, saranno visibili in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a65a3-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="a65a3-118">Tabelle dello schema solo in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65a3-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="a65a3-119">Lo schema di ricerca avanzata di [Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornisce tabelle aggiuntive contenenti i dati di varie soluzioni di sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65a3-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="a65a3-120">Le tabelle seguenti sono disponibili solo in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="a65a3-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="a65a3-121">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="a65a3-121">Table name</span></span> | <span data-ttu-id="a65a3-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a65a3-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="a65a3-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a65a3-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="a65a3-124">File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="a65a3-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="a65a3-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a65a3-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="a65a3-126">Avvisi di Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity, incluse le informazioni sulla gravità e le categorie di minacce</span><span class="sxs-lookup"><span data-stu-id="a65a3-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="a65a3-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="a65a3-128">Attività relative ai file nelle app e nei servizi cloud</span><span class="sxs-lookup"><span data-stu-id="a65a3-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="a65a3-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="a65a3-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="a65a3-130">Informazioni sui file allegati ai messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a65a3-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="a65a3-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="a65a3-132">Eventi di posta elettronica di Microsoft 365, inclusi gli eventi di recapito e blocco della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a65a3-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="a65a3-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="a65a3-134">Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha recapitato i messaggi di posta elettronica alla cassetta postale del destinatario</span><span class="sxs-lookup"><span data-stu-id="a65a3-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="a65a3-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="a65a3-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="a65a3-136">Informazioni sugli URL nei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a65a3-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="a65a3-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="a65a3-138">Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="a65a3-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="a65a3-139">In questa tabella viene illustrata una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="a65a3-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="a65a3-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="a65a3-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="a65a3-141">Informazioni sull'account da varie origini, tra cui Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a65a3-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="a65a3-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="a65a3-143">Eventi di autenticazione in Active Directory e Nei servizi online Microsoft</span><span class="sxs-lookup"><span data-stu-id="a65a3-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="a65a3-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="a65a3-145">Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini</span><span class="sxs-lookup"><span data-stu-id="a65a3-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="a65a3-146">Le query e i rilevamenti personalizzati che usano tabelle dello schema disponibili solo in Microsoft 365 Defender possono essere visualizzati solo in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a65a3-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="a65a3-147">Tabella Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="a65a3-148">Le `AlertInfo` tabelle `AlertEvidence` e `DeviceAlertEvents` sostituiscono la tabella nello schema di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="a65a3-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="a65a3-149">Oltre ai dati relativi agli avvisi per i dispositivi, queste due tabelle includono dati sugli avvisi per identità, app e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a65a3-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="a65a3-150">Utilizzare la tabella seguente per verificare il mapping `DeviceAlertEvents` delle colonne alle colonne nelle tabelle e nelle `AlertInfo` `AlertEvidence` colonne.</span><span class="sxs-lookup"><span data-stu-id="a65a3-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="a65a3-151">Oltre alle colonne della tabella seguente, la tabella include molte altre colonne che forniscono un quadro più olistico degli avvisi `AlertEvidence` provenienti da varie origini.</span><span class="sxs-lookup"><span data-stu-id="a65a3-151">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="a65a3-152">Visualizzare tutte le colonne AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a65a3-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="a65a3-153">Colonna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="a65a3-154">Dove trovare gli stessi dati in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65a3-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="a65a3-155">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="a65a3-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="a65a3-156">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="a65a3-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="a65a3-157">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="a65a3-158">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="a65a3-159">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="a65a3-160">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="a65a3-161">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="a65a3-162">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="a65a3-163">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="a65a3-164">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="a65a3-165">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="a65a3-166">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="a65a3-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="a65a3-167">Questa colonna viene in genere usata in Microsoft Defender for Endpoint per individuare i record correlati in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="a65a3-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="a65a3-168">In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="a65a3-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="a65a3-169">Questa colonna viene in genere usata in Microsoft Defender per Endpoint per ulteriori informazioni sugli eventi in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="a65a3-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="a65a3-170">In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="a65a3-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="a65a3-171">Modificare le query esistenti di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a65a3-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="a65a3-172">Le query di Microsoft Defender per endpoint funzionano così come sono, a meno che non fanno riferimento alla `DeviceAlertEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="a65a3-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="a65a3-173">Per usare queste query in Microsoft 365 Defender, applicare queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="a65a3-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="a65a3-174">Sostituire `DeviceAlertEvents` con `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="a65a3-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="a65a3-175">Unire le `AlertInfo` tabelle e le tabelle per ottenere dati `AlertEvidence` `AlertId` equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a65a3-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="a65a3-176">Query originale</span><span class="sxs-lookup"><span data-stu-id="a65a3-176">Original query</span></span>
<span data-ttu-id="a65a3-177">La query seguente usa `DeviceAlertEvents` Microsoft Defender per Endpoint per ottenere gli avvisi che coinvolgono _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="a65a3-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="a65a3-178">Query modificata</span><span class="sxs-lookup"><span data-stu-id="a65a3-178">Modified query</span></span>
<span data-ttu-id="a65a3-179">La query seguente è stata modificata per l'uso in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a65a3-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="a65a3-180">Invece di controllare il nome del file direttamente da , esegue il join e verifica il `DeviceAlertEvents` nome del file nella `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="a65a3-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="a65a3-181">Eseguire la migrazione di regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="a65a3-181">Migrate custom detection rules</span></span>

<span data-ttu-id="a65a3-182">Quando le regole di Microsoft Defender per endpoint vengono modificate in Microsoft 365 Defender, continuano a funzionare come prima se la query risultante esamina solo le tabelle dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a65a3-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="a65a3-183">Ad esempio, gli avvisi generati da regole di rilevamento personalizzate che eseguono query solo sulle tabelle dei dispositivi continueranno a essere recapitati al SIEM e genereranno notifiche tramite posta elettronica, a seconda di come sono stati configurati in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a65a3-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a65a3-184">Anche le regole di eliminazione esistenti in Defender per Endpoint continueranno a essere applicate.</span><span class="sxs-lookup"><span data-stu-id="a65a3-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="a65a3-185">Dopo aver modificato una regola di Defender per endpoint in modo che eserviti query sulle tabelle di identità e di posta elettronica, disponibili solo in Microsoft 365 Defender, la regola viene spostata automaticamente in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a65a3-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="a65a3-186">Avvisi generati dalla regola migrata:</span><span class="sxs-lookup"><span data-stu-id="a65a3-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="a65a3-187">Non sono più visibili nel portale di Defender for Endpoint (Microsoft Defender Security Center)</span><span class="sxs-lookup"><span data-stu-id="a65a3-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="a65a3-188">Interrompere il recapito al SIEM o generare notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a65a3-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="a65a3-189">Per risolvere questo problema, configurare le notifiche tramite Microsoft 365 Defender per ottenere gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a65a3-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="a65a3-190">È possibile usare [l'API di Microsoft 365 Defender per](api-incident.md) ricevere notifiche per avvisi di rilevamento dei clienti o eventi imprevisti correlati.</span><span class="sxs-lookup"><span data-stu-id="a65a3-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="a65a3-191">Non verrà eliminato da Microsoft Defender per le regole di eliminazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a65a3-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="a65a3-192">Per impedire la generazione di avvisi per determinati utenti, dispositivi o cassette postali, modificare le query corrispondenti per escludere tali entità in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a65a3-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="a65a3-193">Se si modifica una regola in questo modo, verrà richiesta una conferma prima dell'applicazione di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="a65a3-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="a65a3-194">I nuovi avvisi generati dalle regole di rilevamento personalizzate nel portale di Microsoft 365 Defender vengono visualizzati in una pagina di avviso che fornisce le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a65a3-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="a65a3-195">Titolo e descrizione dell'avviso</span><span class="sxs-lookup"><span data-stu-id="a65a3-195">Alert title and description</span></span> 
- <span data-ttu-id="a65a3-196">Asset influenzati</span><span class="sxs-lookup"><span data-stu-id="a65a3-196">Impacted assets</span></span>
- <span data-ttu-id="a65a3-197">Azioni intraprese in risposta all'avviso</span><span class="sxs-lookup"><span data-stu-id="a65a3-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="a65a3-198">Risultati della query che hanno attivato l'avviso</span><span class="sxs-lookup"><span data-stu-id="a65a3-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="a65a3-199">Informazioni sulla regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="a65a3-199">Information on the custom detection rule</span></span> 
 
![Immagine della pagina nuovo avviso](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="a65a3-201">Scrivere query senza DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="a65a3-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="a65a3-202">Nello schema di Microsoft 365 Defender, le tabelle e le tabelle sono disponibili per supportare il set di informazioni diverse che accompagnano gli avvisi `AlertInfo` `AlertEvidence` provenienti da varie origini.</span><span class="sxs-lookup"><span data-stu-id="a65a3-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="a65a3-203">Per ottenere le stesse informazioni sull'avviso che hai usato per ottenere dalla tabella nello schema di Microsoft Defender for Endpoint, filtra la tabella in base a e quindi unisci ogni ID univoco alla tabella, che fornisce informazioni dettagliate su eventi ed `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entità.</span><span class="sxs-lookup"><span data-stu-id="a65a3-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="a65a3-204">Vedi la query di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a65a3-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="a65a3-205">Questa query restituisce molte più colonne rispetto allo `DeviceAlertEvents` schema di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="a65a3-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="a65a3-206">Per mantenere gestibili i risultati, `project` utilizzare per ottenere solo le colonne a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="a65a3-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="a65a3-207">L'esempio seguente proietta colonne che potrebbero interessarti quando l'indagine ha rilevato attività di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a65a3-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="a65a3-208">Se vuoi filtrare per entità specifiche coinvolte negli avvisi, puoi farlo specificando il tipo di entità e il valore per cui vuoi `EntityType` filtrare.</span><span class="sxs-lookup"><span data-stu-id="a65a3-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="a65a3-209">Nell'esempio seguente viene ricercato un indirizzo IP specifico:</span><span class="sxs-lookup"><span data-stu-id="a65a3-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="a65a3-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a65a3-210">See also</span></span>
- [<span data-ttu-id="a65a3-211">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65a3-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a65a3-212">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a65a3-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a65a3-213">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a65a3-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a65a3-214">Ricerca avanzata in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="a65a3-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)