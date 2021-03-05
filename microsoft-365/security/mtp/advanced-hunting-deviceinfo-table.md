---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni su sistema operativo, nome computer e altre informazioni sul computer nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, dispositivo, computer, sistema operativo, piattaforma, utenti
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
ms.technology: m365d
ms.openlocfilehash: 53948f3d470fb85ddfda8dbcf5b64024755ca50e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461624"
---
# <a name="deviceinfo"></a><span data-ttu-id="6439f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="6439f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6439f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6439f-105">**Applies to:**</span></span>
- <span data-ttu-id="6439f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6439f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6439f-107">La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6439f-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="6439f-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="6439f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6439f-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6439f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6439f-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="6439f-110">Column name</span></span> | <span data-ttu-id="6439f-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6439f-111">Data type</span></span> | <span data-ttu-id="6439f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6439f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6439f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6439f-113">datetime</span></span> | <span data-ttu-id="6439f-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6439f-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6439f-115">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-115">string</span></span> | <span data-ttu-id="6439f-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="6439f-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6439f-117">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-117">string</span></span> | <span data-ttu-id="6439f-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="6439f-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="6439f-119">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-119">string</span></span> | <span data-ttu-id="6439f-120">Versione dell'agente endpoint o del sensore in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="6439f-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="6439f-121">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-121">string</span></span> | <span data-ttu-id="6439f-122">Indirizzo IP pubblico usato dal computer onboarded per connettersi al servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6439f-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="6439f-123">Può trattarsi dell'indirizzo IP del computer stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="6439f-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="6439f-124">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-124">string</span></span> | <span data-ttu-id="6439f-125">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="6439f-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="6439f-126">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-126">string</span></span> | <span data-ttu-id="6439f-127">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="6439f-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="6439f-128">Indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="6439f-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="6439f-129">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-129">string</span></span> | <span data-ttu-id="6439f-130">Versione build del sistema operativo in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="6439f-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="6439f-131">boolean</span><span class="sxs-lookup"><span data-stu-id="6439f-131">boolean</span></span> | <span data-ttu-id="6439f-132">Indicatore booleano che indica se il computer è aggiunto ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6439f-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="6439f-133">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-133">string</span></span> | <span data-ttu-id="6439f-134">Identificatore univoco per il dispositivo in Azure AD</span><span class="sxs-lookup"><span data-stu-id="6439f-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="6439f-135">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-135">string</span></span> | <span data-ttu-id="6439f-136">Elenco di tutti gli utenti registrati nel computer al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="6439f-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="6439f-137">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-137">string</span></span> | <span data-ttu-id="6439f-138">Tag del computer aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="6439f-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="6439f-139">long</span><span class="sxs-lookup"><span data-stu-id="6439f-139">long</span></span> | <span data-ttu-id="6439f-140">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="6439f-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6439f-141">Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="6439f-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="6439f-142">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-142">string</span></span> | <span data-ttu-id="6439f-143">Ulteriori informazioni sull'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="6439f-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="6439f-144">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-144">string</span></span> | <span data-ttu-id="6439f-145">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="6439f-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="6439f-146">stringa</span><span class="sxs-lookup"><span data-stu-id="6439f-146">string</span></span> | <span data-ttu-id="6439f-147">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="6439f-147">Machine group of the machine.</span></span> <span data-ttu-id="6439f-148">Questo gruppo viene utilizzato dal controllo dell'accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="6439f-148">This group is used by role-based access control to determine access to the machine</span></span> |

<span data-ttu-id="6439f-149">La `DeviceInfo` tabella fornisce informazioni sul dispositivo in base agli heartbeat, ovvero report periodici o segnali provenienti da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6439f-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="6439f-150">Ogni quindici minuti, il dispositivo invia un heartbeat parziale che contiene attributi che cambiano frequentemente, ad esempio `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="6439f-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="6439f-151">Una volta al giorno, viene inviato un heartbeat completo contenente gli attributi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6439f-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="6439f-152">Puoi usare la query di esempio seguente per ottenere lo stato più recente di un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6439f-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="6439f-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6439f-153">Related topics</span></span>
- [<span data-ttu-id="6439f-154">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6439f-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6439f-155">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="6439f-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6439f-156">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="6439f-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6439f-157">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="6439f-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6439f-158">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="6439f-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6439f-159">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="6439f-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
