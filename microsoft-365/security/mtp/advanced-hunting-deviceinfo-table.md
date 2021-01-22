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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931279"
---
# <a name="deviceinfo"></a><span data-ttu-id="6c9a3-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="6c9a3-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c9a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6c9a3-105">**Applies to:**</span></span>
- <span data-ttu-id="6c9a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c9a3-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6c9a3-107">La tabella nello schema di ricerca avanzata contiene informazioni sui computer dell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6c9a3-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="6c9a3-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="6c9a3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6c9a3-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6c9a3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6c9a3-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="6c9a3-110">Column name</span></span> | <span data-ttu-id="6c9a3-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6c9a3-111">Data type</span></span> | <span data-ttu-id="6c9a3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c9a3-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6c9a3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6c9a3-113">datetime</span></span> | <span data-ttu-id="6c9a3-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6c9a3-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6c9a3-115">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-115">string</span></span> | <span data-ttu-id="6c9a3-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="6c9a3-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6c9a3-117">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-117">string</span></span> | <span data-ttu-id="6c9a3-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="6c9a3-119">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-119">string</span></span> | <span data-ttu-id="6c9a3-120">Versione dell'agente endpoint o del sensore in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="6c9a3-121">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-121">string</span></span> | <span data-ttu-id="6c9a3-122">Indirizzo IP pubblico usato dal computer onboarded per connettersi al servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6c9a3-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="6c9a3-123">Può trattarsi dell'indirizzo IP del computer stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="6c9a3-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="6c9a3-124">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-124">string</span></span> | <span data-ttu-id="6c9a3-125">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="6c9a3-126">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-126">string</span></span> | <span data-ttu-id="6c9a3-127">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="6c9a3-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="6c9a3-128">Indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="6c9a3-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="6c9a3-129">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-129">string</span></span> | <span data-ttu-id="6c9a3-130">Versione build del sistema operativo in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="6c9a3-131">boolean</span><span class="sxs-lookup"><span data-stu-id="6c9a3-131">boolean</span></span> | <span data-ttu-id="6c9a3-132">Indicatore booleano che indica se il computer è aggiunto ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c9a3-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="6c9a3-133">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-133">string</span></span> | <span data-ttu-id="6c9a3-134">Elenco di tutti gli utenti registrati nel computer al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="6c9a3-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="6c9a3-135">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-135">string</span></span> | <span data-ttu-id="6c9a3-136">Tag del computer aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="6c9a3-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="6c9a3-137">long</span><span class="sxs-lookup"><span data-stu-id="6c9a3-137">long</span></span> | <span data-ttu-id="6c9a3-138">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="6c9a3-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6c9a3-139">Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="6c9a3-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="6c9a3-140">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-140">string</span></span> | <span data-ttu-id="6c9a3-141">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="6c9a3-142">stringa</span><span class="sxs-lookup"><span data-stu-id="6c9a3-142">string</span></span> | <span data-ttu-id="6c9a3-143">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="6c9a3-143">Machine group of the machine.</span></span> <span data-ttu-id="6c9a3-144">Questo gruppo viene utilizzato dal controllo dell'accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="6c9a3-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6c9a3-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c9a3-145">Related topics</span></span>
- [<span data-ttu-id="6c9a3-146">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6c9a3-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c9a3-147">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="6c9a3-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c9a3-148">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="6c9a3-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6c9a3-149">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="6c9a3-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6c9a3-150">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="6c9a3-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6c9a3-151">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="6c9a3-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
