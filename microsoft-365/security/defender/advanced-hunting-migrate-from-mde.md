---
title: Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint
description: Scopri come modificare le query di Microsoft Defender for Endpoint in modo da poterle usare in Microsoft 365 Defender
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, Microsoft Defender for Endpoint, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470689"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="df7ed-104">Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="df7ed-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="df7ed-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="df7ed-105">**Applies to:**</span></span>
- <span data-ttu-id="df7ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df7ed-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="df7ed-107">Sposta i flussi di lavoro di ricerca avanzati da Microsoft Defender for Endpoint per cercare in modo proattivo le minacce usando un set più ampio di dati.</span><span class="sxs-lookup"><span data-stu-id="df7ed-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="df7ed-108">In Microsoft 365 Defender, si ottiene l'accesso ai dati da altre soluzioni Microsoft 365 sicurezza, tra cui:</span><span class="sxs-lookup"><span data-stu-id="df7ed-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="df7ed-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="df7ed-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="df7ed-110">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="df7ed-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="df7ed-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="df7ed-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="df7ed-112">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="df7ed-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="df7ed-113">La maggior parte dei clienti di Microsoft Defender per Endpoint [può usare Microsoft 365 Defender senza licenze aggiuntive.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="df7ed-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="df7ed-114">Per avviare la transizione dei flussi di lavoro di ricerca avanzata da Defender for Endpoint, attiva [Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="df7ed-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="df7ed-115">Puoi eseguire la transizione senza influire sui flussi di lavoro esistenti di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="df7ed-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="df7ed-116">Le query salvate rimangono intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="df7ed-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="df7ed-117">Tuttavia, saranno visibili in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="df7ed-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="df7ed-118">Tabelle dello schema solo in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df7ed-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="df7ed-119">Lo [schema Microsoft 365 defender advanced hunting schema](advanced-hunting-schema-tables.md) fornisce tabelle aggiuntive contenenti dati di varie soluzioni Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="df7ed-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="df7ed-120">Le tabelle seguenti sono disponibili solo in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="df7ed-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="df7ed-121">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="df7ed-121">Table name</span></span> | <span data-ttu-id="df7ed-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df7ed-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="df7ed-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="df7ed-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="df7ed-124">File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="df7ed-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="df7ed-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="df7ed-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="df7ed-126">Avvisi da Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender per l'identità, incluse le informazioni sulla gravità e le categorie di minacce</span><span class="sxs-lookup"><span data-stu-id="df7ed-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="df7ed-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="df7ed-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="df7ed-128">Informazioni sui file allegati ai messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="df7ed-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="df7ed-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="df7ed-130">Microsoft 365 di posta elettronica, inclusi il recapito della posta elettronica e gli eventi di blocco</span><span class="sxs-lookup"><span data-stu-id="df7ed-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="df7ed-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="df7ed-132">Eventi di sicurezza che si verificano dopo il recapito, dopo Microsoft 365 recapitato i messaggi di posta elettronica alla cassetta postale del destinatario</span><span class="sxs-lookup"><span data-stu-id="df7ed-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="df7ed-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="df7ed-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="df7ed-134">Informazioni sugli URL nei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="df7ed-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="df7ed-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="df7ed-136">Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="df7ed-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="df7ed-137">In questa tabella viene illustrata una serie di eventi correlati all'identità ed eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="df7ed-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="df7ed-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="df7ed-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="df7ed-139">Informazioni sull'account provenienti da varie fonti, tra cui Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="df7ed-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="df7ed-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="df7ed-141">Eventi di autenticazione in Active Directory e Microsoft online Services</span><span class="sxs-lookup"><span data-stu-id="df7ed-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="df7ed-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="df7ed-143">Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini</span><span class="sxs-lookup"><span data-stu-id="df7ed-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="df7ed-144">Le query e i rilevamenti personalizzati che usano tabelle dello schema disponibili solo in Microsoft 365 Defender possono essere visualizzati solo in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="df7ed-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="df7ed-145">Tabella Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="df7ed-146">Le `AlertInfo` tabelle e `AlertEvidence` sostituiscono la tabella nello schema di Microsoft `DeviceAlertEvents` Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="df7ed-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="df7ed-147">Oltre ai dati sugli avvisi per i dispositivi, queste due tabelle includono i dati sugli avvisi per identità, app e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="df7ed-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="df7ed-148">Utilizzare la tabella seguente per verificare il mapping `DeviceAlertEvents` delle colonne alle colonne nelle tabelle e `AlertInfo` `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="df7ed-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="df7ed-149">Oltre alle colonne della tabella seguente, la tabella include molte altre colonne che forniscono un'immagine più olistica degli avvisi `AlertEvidence` provenienti da varie origini.</span><span class="sxs-lookup"><span data-stu-id="df7ed-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="df7ed-150">Vedi tutte le colonne AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="df7ed-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="df7ed-151">Colonna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="df7ed-152">Dove trovare gli stessi dati in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df7ed-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="df7ed-153">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="df7ed-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="df7ed-154">`AlertInfo` e  `AlertEvidence` tabelle</span><span class="sxs-lookup"><span data-stu-id="df7ed-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="df7ed-155">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="df7ed-156">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="df7ed-157">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="df7ed-158">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="df7ed-159">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="df7ed-160">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="df7ed-161">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="df7ed-162">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="df7ed-163">`AlertEvidence` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="df7ed-164">`AlertInfo` tavolo</span><span class="sxs-lookup"><span data-stu-id="df7ed-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="df7ed-165">Questa colonna viene in genere utilizzata in Microsoft Defender for Endpoint per individuare i record correlati in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="df7ed-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="df7ed-166">In Microsoft 365 Defender puoi ottenere dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="df7ed-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="df7ed-167">Questa colonna viene in genere usata in Microsoft Defender for Endpoint per ulteriori informazioni sugli eventi in altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="df7ed-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="df7ed-168">In Microsoft 365 Defender puoi ottenere dati correlati direttamente dalla `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="df7ed-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="df7ed-169">Modificare le query esistenti di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="df7ed-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="df7ed-170">Le query di Microsoft Defender for Endpoint funzionano così come sono, a meno che non fanno riferimento alla `DeviceAlertEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="df7ed-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="df7ed-171">Per usare queste query in Microsoft 365 Defender, applica queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="df7ed-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="df7ed-172">Sostituire `DeviceAlertEvents` con `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="df7ed-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="df7ed-173">Unire le `AlertInfo` tabelle e le tabelle per ottenere dati `AlertEvidence` `AlertId` equivalenti.</span><span class="sxs-lookup"><span data-stu-id="df7ed-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="df7ed-174">Query originale</span><span class="sxs-lookup"><span data-stu-id="df7ed-174">Original query</span></span>
<span data-ttu-id="df7ed-175">La query seguente usa `DeviceAlertEvents` Microsoft Defender for Endpoint per ottenere gli avvisi che coinvolgono _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="df7ed-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="df7ed-176">Query modificata</span><span class="sxs-lookup"><span data-stu-id="df7ed-176">Modified query</span></span>
<span data-ttu-id="df7ed-177">La query seguente è stata modificata per l'uso in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="df7ed-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="df7ed-178">Invece di controllare il nome del file direttamente da , viene aggiunta e verificata la `DeviceAlertEvents` presenza del nome del file nella `AlertEvidence` tabella.</span><span class="sxs-lookup"><span data-stu-id="df7ed-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="df7ed-179">Eseguire la migrazione di regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="df7ed-179">Migrate custom detection rules</span></span>

<span data-ttu-id="df7ed-180">Quando le regole di Microsoft Defender for Endpoint vengono modificate in Microsoft 365 Defender, continuano a funzionare come prima se la query risultante esamina solo le tabelle dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df7ed-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="df7ed-181">Ad esempio, gli avvisi generati da regole di rilevamento personalizzate che eseguono query solo sulle tabelle dei dispositivi continueranno a essere recapitati al SIEM e genereranno notifiche di posta elettronica, a seconda di come sono stati configurati in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="df7ed-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="df7ed-182">Anche le regole di eliminazione esistenti in Defender for Endpoint continueranno ad essere applicate.</span><span class="sxs-lookup"><span data-stu-id="df7ed-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="df7ed-183">Dopo aver modificato una regola di Defender for Endpoint in modo che esere query sulle tabelle di identità e posta elettronica, disponibili solo in Microsoft 365 Defender, la regola viene spostata automaticamente in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="df7ed-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="df7ed-184">Avvisi generati dalla regola migrata:</span><span class="sxs-lookup"><span data-stu-id="df7ed-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="df7ed-185">Non sono più visibili nel portale defender per endpoint (Microsoft Defender Security Center)</span><span class="sxs-lookup"><span data-stu-id="df7ed-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="df7ed-186">Smettere di essere recapitati al SIEM o generare notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="df7ed-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="df7ed-187">Per risolvere questo problema, configura le notifiche tramite Microsoft 365 Defender per ottenere gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="df7ed-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="df7ed-188">Puoi usare [l'API Microsoft 365 Defender per](api-incident.md) ricevere notifiche per avvisi di rilevamento dei clienti o eventi imprevisti correlati.</span><span class="sxs-lookup"><span data-stu-id="df7ed-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="df7ed-189">Non verrà eliminato da Microsoft Defender per le regole di eliminazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="df7ed-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="df7ed-190">Per impedire la generazione di avvisi per determinati utenti, dispositivi o cassette postali, modificare le query corrispondenti per escludere tali entità in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="df7ed-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="df7ed-191">Se si modifica una regola in questo modo, verrà richiesta una conferma prima dell'applicazione di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="df7ed-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="df7ed-192">I nuovi avvisi generati dalle regole di rilevamento personalizzate in Microsoft 365 Defender Portal vengono visualizzati in una pagina di avviso che fornisce le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df7ed-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="df7ed-193">Titolo e descrizione dell'avviso</span><span class="sxs-lookup"><span data-stu-id="df7ed-193">Alert title and description</span></span> 
- <span data-ttu-id="df7ed-194">Asset influenzati</span><span class="sxs-lookup"><span data-stu-id="df7ed-194">Impacted assets</span></span>
- <span data-ttu-id="df7ed-195">Azioni eseguite in risposta all'avviso</span><span class="sxs-lookup"><span data-stu-id="df7ed-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="df7ed-196">Risultati della query che hanno attivato l'avviso</span><span class="sxs-lookup"><span data-stu-id="df7ed-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="df7ed-197">Informazioni sulla regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="df7ed-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="df7ed-198">![Immagine della pagina del nuovo avviso](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="df7ed-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="df7ed-199">Scrivere query senza DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="df7ed-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="df7ed-200">Nello schema Microsoft 365 Defender vengono fornite le tabelle e per supportare il set di informazioni diverse che accompagnano `AlertInfo` gli avvisi provenienti da diverse `AlertEvidence` origini.</span><span class="sxs-lookup"><span data-stu-id="df7ed-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="df7ed-201">Per ottenere le stesse informazioni di avviso che hai usato per ottenere dalla tabella nello schema di Microsoft Defender for Endpoint, filtra la tabella in base a e quindi unisci ogni ID univoco alla tabella, che fornisce informazioni dettagliate sull'evento e `DeviceAlertEvents` `AlertInfo` sull'entità. `ServiceSource` `AlertEvidence`</span><span class="sxs-lookup"><span data-stu-id="df7ed-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="df7ed-202">Vedi la query di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="df7ed-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="df7ed-203">Questa query restituisce molte più colonne rispetto `DeviceAlertEvents` allo schema di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="df7ed-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="df7ed-204">Per mantenere gestibili i risultati, utilizzare per ottenere solo le colonne `project` a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="df7ed-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="df7ed-205">L'esempio seguente proietta colonne che potrebbero interessarti quando l'indagine ha rilevato l'attività di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="df7ed-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="df7ed-206">Se vuoi filtrare per entità specifiche coinvolte negli avvisi, puoi farlo specificando il tipo di entità e il valore per cui vuoi `EntityType` filtrare.</span><span class="sxs-lookup"><span data-stu-id="df7ed-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="df7ed-207">Nell'esempio seguente viene ricercato un indirizzo IP specifico:</span><span class="sxs-lookup"><span data-stu-id="df7ed-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="df7ed-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df7ed-208">See also</span></span>
- [<span data-ttu-id="df7ed-209">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df7ed-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="df7ed-210">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="df7ed-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df7ed-211">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="df7ed-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="df7ed-212">Ricerca avanzata in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="df7ed-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)