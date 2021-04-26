---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni sul sistema operativo, sul nome del computer e su altre informazioni sul computer nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, dispositivo, computer, sistema operativo, piattaforma, utenti
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
ms.technology: m365d
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023130"
---
# <a name="deviceinfo"></a><span data-ttu-id="c8ea0-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c8ea0-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8ea0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c8ea0-105">**Applies to:**</span></span>
- <span data-ttu-id="c8ea0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8ea0-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c8ea0-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c8ea0-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="c8ea0-108">La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c8ea0-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c8ea0-109">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c8ea0-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c8ea0-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c8ea0-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="c8ea0-111">Column name</span></span> | <span data-ttu-id="c8ea0-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c8ea0-112">Data type</span></span> | <span data-ttu-id="c8ea0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8ea0-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c8ea0-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c8ea0-114">datetime</span></span> | <span data-ttu-id="c8ea0-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c8ea0-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c8ea0-116">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-116">string</span></span> | <span data-ttu-id="c8ea0-117">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="c8ea0-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c8ea0-118">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-118">string</span></span> | <span data-ttu-id="c8ea0-119">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c8ea0-120">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-120">string</span></span> | <span data-ttu-id="c8ea0-121">Versione dell'agente endpoint o del sensore in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c8ea0-122">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-122">string</span></span> | <span data-ttu-id="c8ea0-123">Indirizzo IP pubblico utilizzato dal computer onboarded per connettersi al servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="c8ea0-124">Può trattarsi dell'indirizzo IP del computer stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="c8ea0-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c8ea0-125">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-125">string</span></span> | <span data-ttu-id="c8ea0-126">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c8ea0-127">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-127">string</span></span> | <span data-ttu-id="c8ea0-128">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c8ea0-129">Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="c8ea0-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c8ea0-130">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-130">string</span></span> | <span data-ttu-id="c8ea0-131">Versione build del sistema operativo in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c8ea0-132">boolean</span><span class="sxs-lookup"><span data-stu-id="c8ea0-132">boolean</span></span> | <span data-ttu-id="c8ea0-133">Indicatore booleano che indica se il computer è aggiunto ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c8ea0-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="c8ea0-134">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-134">string</span></span> | <span data-ttu-id="c8ea0-135">Identificatore univoco per il dispositivo in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8ea0-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c8ea0-136">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-136">string</span></span> | <span data-ttu-id="c8ea0-137">Elenco di tutti gli utenti connessi al computer al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="c8ea0-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c8ea0-138">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-138">string</span></span> | <span data-ttu-id="c8ea0-139">Tag computer aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c8ea0-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="c8ea0-140">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-140">string</span></span> | <span data-ttu-id="c8ea0-141">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c8ea0-142">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-142">string</span></span> | <span data-ttu-id="c8ea0-143">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-143">Machine group of the machine.</span></span> <span data-ttu-id="c8ea0-144">Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="c8ea0-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="c8ea0-145">long</span><span class="sxs-lookup"><span data-stu-id="c8ea0-145">long</span></span> | <span data-ttu-id="c8ea0-146">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c8ea0-147">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="c8ea0-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="c8ea0-148">stringa</span><span class="sxs-lookup"><span data-stu-id="c8ea0-148">string</span></span> | <span data-ttu-id="c8ea0-149">Informazioni aggiuntive sull'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="c8ea0-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="c8ea0-150">La `DeviceInfo` tabella fornisce informazioni sul dispositivo in base agli heartbeat, ovvero report periodici o segnali provenienti da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="c8ea0-151">Ogni quindici minuti, il dispositivo invia un heartbeat parziale che contiene attributi che cambiano frequentemente, ad esempio `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="c8ea0-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="c8ea0-152">Una volta al giorno, viene inviato un heartbeat completo contenente gli attributi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ea0-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="c8ea0-153">Puoi usare la query di esempio seguente per ottenere lo stato più recente di un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c8ea0-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="c8ea0-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c8ea0-154">Related topics</span></span>
- [<span data-ttu-id="c8ea0-155">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="c8ea0-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c8ea0-156">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="c8ea0-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c8ea0-157">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="c8ea0-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c8ea0-158">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="c8ea0-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c8ea0-159">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="c8ea0-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c8ea0-160">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="c8ea0-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
