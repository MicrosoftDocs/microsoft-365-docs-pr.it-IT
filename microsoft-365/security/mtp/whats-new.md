---
title: Novità di Microsoft 365 Defender
description: Elenca le nuove funzionalità in Microsoft 365 Defender
keywords: novità di Microsoft Threat Protection, ga, generalmente disponibile, funzionalità, disponibili, nuove
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932023"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="9c295-104">Novità di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c295-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="9c295-105">Si vuole provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9c295-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9c295-106">È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="9c295-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="9c295-107">Le funzionalità seguenti sono generalmente disponibili nella versione più recente di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9c295-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="9c295-108">Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:</span><span class="sxs-lookup"><span data-stu-id="9c295-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> <span data-ttu-id="9c295-109">Si vuole provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9c295-109">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9c295-110">È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="9c295-110">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook)</span></span>
>

## <a name="september-2020"></a><span data-ttu-id="9c295-111">Settembre 2020</span><span class="sxs-lookup"><span data-stu-id="9c295-111">September 2020</span></span>
- [<span data-ttu-id="9c295-112">Tabella IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9c295-112">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="9c295-113">Trovare eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="9c295-113">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9c295-114">In [questa tabella di](advanced-hunting-overview.md) schema di ricerca avanzata viene illustrata una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="9c295-114">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="9c295-115">Funzione AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="9c295-115">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="9c295-116">Utilizzare questa funzione nelle query di ricerca avanzata per ottenere rapidamente gli indirizzi IP più recenti assegnati a un dispositivo o gli indirizzi IP più recenti da un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="9c295-116">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="9c295-117">Luglio 2020</span><span class="sxs-lookup"><span data-stu-id="9c295-117">July 2020</span></span>
- [<span data-ttu-id="9c295-118">Funzione FileProfile()</span><span class="sxs-lookup"><span data-stu-id="9c295-118">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="9c295-119">Utilizzare questa funzione nelle query di ricerca avanzata per arricchire i risultati con informazioni complete sui file.</span><span class="sxs-lookup"><span data-stu-id="9c295-119">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="9c295-120">Tabelle delle identità e delle app</span><span class="sxs-lookup"><span data-stu-id="9c295-120">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="9c295-121">Ottieni visibilità su eventi di autenticazione, query di Active Directory e attività correlate alle app con le tabelle [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) nello schema di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="9c295-121">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="9c295-122">Iniziare la ricerca</span><span class="sxs-lookup"><span data-stu-id="9c295-122">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="9c295-123">È possibile passare rapidamente dall'analisi di un evento all'analisi di un evento specifico, di un utente, di un dispositivo o di altri tipi di entità per la ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="9c295-123">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="9c295-124">Giugno 2020</span><span class="sxs-lookup"><span data-stu-id="9c295-124">June 2020</span></span>
- <span data-ttu-id="9c295-125">Feed Twitter</span><span class="sxs-lookup"><span data-stu-id="9c295-125">Twitter feed</span></span> <br> <span data-ttu-id="9c295-126">Ottieni le ricerche più recenti sulla sicurezza, intelligence per le minacce, notizie sui prodotti e altro ancora, direttamente all'interno del dashboard.</span><span class="sxs-lookup"><span data-stu-id="9c295-126">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="9c295-127">Tabella dello schema EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9c295-127">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="9c295-128">Incorporare informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica nelle query di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="9c295-128">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="9c295-129">Esaminare i record nella ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9c295-129">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="9c295-130">Esaminare rapidamente i record nei risultati della query con il nuovo riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="9c295-130">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="9c295-131">Maggio 2020</span><span class="sxs-lookup"><span data-stu-id="9c295-131">May 2020</span></span>
- [<span data-ttu-id="9c295-132">Rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="9c295-132">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="9c295-133">Utilizzare query di ricerca avanzata per creare regole di rilevamento personalizzate che monitorano e rispondono automaticamente agli eventi di sicurezza e agli stati di sistema.</span><span class="sxs-lookup"><span data-stu-id="9c295-133">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="9c295-134">Febbraio 2020</span><span class="sxs-lookup"><span data-stu-id="9c295-134">February 2020</span></span>
- [<span data-ttu-id="9c295-135">Eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="9c295-135">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="9c295-136">Conoscere esattamente dove è iniziato un attacco e altri dettagli per vedere la portata dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="9c295-136">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="9c295-137">Analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="9c295-137">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="9c295-138">L'AIR consente al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire avvisi e incidenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c295-138">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="9c295-139">Miglioramenti della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9c295-139">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="9c295-140">Ricerca proattiva delle minacce nell'area di lavoro moderna con Kusto Query Language e uno schema ottimizzato per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c295-140">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="9c295-141">Marzo 2019</span><span class="sxs-lookup"><span data-stu-id="9c295-141">March 2019</span></span>
- <span data-ttu-id="9c295-142">Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9c295-142">Advanced hunting</span></span> <br> <span data-ttu-id="9c295-143">Pagina di destinazione per varie funzionalità di ricerca che consentono di individuare in modo proattivo minacce che interessano posta elettronica e dati, dispositivi e identità.</span><span class="sxs-lookup"><span data-stu-id="9c295-143">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="9c295-144">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="9c295-144">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="9c295-145">Misurazione della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica ulteriori azioni di miglioramento intraprese.</span><span class="sxs-lookup"><span data-stu-id="9c295-145">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="9c295-146">Se si segue il punteggio di sicurezza, è possibile proteggere l'organizzazione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="9c295-146">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="9c295-147">Report</span><span class="sxs-lookup"><span data-stu-id="9c295-147">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="9c295-148">Include una serie di schede che coprono un'ampia gamma di aree monitorate dagli analisti e dagli amministratori della sicurezza nell'ambito delle loro operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="9c295-148">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
