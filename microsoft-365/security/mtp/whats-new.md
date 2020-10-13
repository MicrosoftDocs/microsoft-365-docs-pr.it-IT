---
title: Novità di Microsoft Threat Protection
description: Elenca le nuove caratteristiche e funzionalità di Microsoft Threat Protection
keywords: Novità di Microsoft Threat Protection, GA, generalmente disponibile, funzionalità, disponibile, nuovo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1b3cc273b61fcdff3c01b30c9ef64619a0e7a368
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430398"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="13e7d-104">Novità di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="13e7d-104">What's new in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="13e7d-105">Le caratteristiche seguenti sono generalmente disponibili (GA) nella versione più recente di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="13e7d-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="13e7d-106">Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:</span><span class="sxs-lookup"><span data-stu-id="13e7d-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="13e7d-107">Settembre 2020</span><span class="sxs-lookup"><span data-stu-id="13e7d-107">September 2020</span></span>
- [<span data-ttu-id="13e7d-108">Tabella IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="13e7d-108">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="13e7d-109">Individuare gli eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="13e7d-109">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="13e7d-110">Questa tabella dello schema di [caccia avanzata](advanced-hunting-overview.md) copre una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="13e7d-110">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="13e7d-111">Funzione AssignedIPAddresses ()</span><span class="sxs-lookup"><span data-stu-id="13e7d-111">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="13e7d-112">Utilizzare questa funzione nelle query di caccia avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati a un dispositivo o gli indirizzi IP più recenti da un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="13e7d-112">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="13e7d-113">Luglio 2020</span><span class="sxs-lookup"><span data-stu-id="13e7d-113">July 2020</span></span>
- [<span data-ttu-id="13e7d-114">Funzione fileprofile ()</span><span class="sxs-lookup"><span data-stu-id="13e7d-114">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="13e7d-115">Utilizzare questa funzione nelle query di caccia avanzate per arricchire i risultati con informazioni complete sui file.</span><span class="sxs-lookup"><span data-stu-id="13e7d-115">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="13e7d-116">Tabelle di identità e app</span><span class="sxs-lookup"><span data-stu-id="13e7d-116">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="13e7d-117">Ottenere visibilità negli eventi di autenticazione, nelle query di Active Directory e nell'attività correlata all'applicazione con le tabelle [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) nello schema di caccia avanzato.</span><span class="sxs-lookup"><span data-stu-id="13e7d-117">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="13e7d-118">Iniziare la ricerca</span><span class="sxs-lookup"><span data-stu-id="13e7d-118">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="13e7d-119">Rapidamente pivot dall'indagine di un incidente per esaminare un evento specifico, un utente, un dispositivo o altri tipi di entità per la ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="13e7d-119">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="13e7d-120">Giugno 2020</span><span class="sxs-lookup"><span data-stu-id="13e7d-120">June 2020</span></span>
- <span data-ttu-id="13e7d-121">Feed Twitter</span><span class="sxs-lookup"><span data-stu-id="13e7d-121">Twitter feed</span></span> <br> <span data-ttu-id="13e7d-122">Ottenere le ultime ricerche sulla sicurezza, la tecnologia di minacce, le novità del prodotto e altro ancora, direttamente all'interno del dashboard.</span><span class="sxs-lookup"><span data-stu-id="13e7d-122">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="13e7d-123">Tabella dello schema di EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="13e7d-123">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="13e7d-124">Includere informazioni sulle azioni di post-recapito eseguite nei messaggi di posta elettronica nelle query di caccia avanzate.</span><span class="sxs-lookup"><span data-stu-id="13e7d-124">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="13e7d-125">Ispezionare i record nella ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="13e7d-125">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="13e7d-126">Esaminare rapidamente i record nei risultati della query con il nuovo riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="13e7d-126">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="13e7d-127">Maggio 2020</span><span class="sxs-lookup"><span data-stu-id="13e7d-127">May 2020</span></span>
- [<span data-ttu-id="13e7d-128">Rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="13e7d-128">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="13e7d-129">Utilizzare le query di ricerca avanzate per creare regole di rilevamento personalizzate che monitorano e rispondano automaticamente agli eventi di sicurezza e agli Stati del sistema.</span><span class="sxs-lookup"><span data-stu-id="13e7d-129">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="13e7d-130">Febbraio 2020</span><span class="sxs-lookup"><span data-stu-id="13e7d-130">February 2020</span></span>
- [<span data-ttu-id="13e7d-131">Eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="13e7d-131">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="13e7d-132">Sapere esattamente dove è stato avviato un attacco e altri dettagli che consentono di visualizzare l'entità dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="13e7d-132">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="13e7d-133">Analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="13e7d-133">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="13e7d-134">L'AIR consente al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire avvisi e incidenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="13e7d-134">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="13e7d-135">Miglioramenti alla ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="13e7d-135">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="13e7d-136">Cercare in modo proattivo le minacce nell'area di lavoro moderna con il linguaggio di query di Kusto e uno schema ottimizzato per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="13e7d-136">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="13e7d-137">Marzo 2019</span><span class="sxs-lookup"><span data-stu-id="13e7d-137">March 2019</span></span>
- <span data-ttu-id="13e7d-138">Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="13e7d-138">Advanced hunting</span></span> <br> <span data-ttu-id="13e7d-139">Landing page to varie funzionalità di caccia che consentono di trovare in modo proattivo minacce che interessano la posta elettronica e i dati, i dispositivi e le identità.</span><span class="sxs-lookup"><span data-stu-id="13e7d-139">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="13e7d-140">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="13e7d-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="13e7d-141">Misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite.</span><span class="sxs-lookup"><span data-stu-id="13e7d-141">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="13e7d-142">Dopo i consigli sui punteggi di sicurezza è possibile proteggere l'organizzazione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="13e7d-142">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="13e7d-143">Report</span><span class="sxs-lookup"><span data-stu-id="13e7d-143">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="13e7d-144">Include una miriade di schede che coprono una serie di aree in cui gli analisti di sicurezza e gli amministratori rientrano nell'ambito delle operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="13e7d-144">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
