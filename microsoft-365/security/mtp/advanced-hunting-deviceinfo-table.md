---
title: Tabella DeviceInfo nello schema di caccia avanzato
description: Informazioni sul sistema operativo, sul nome del computer e su altri computer nella tabella DeviceInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, Device, Machine, OS, Platform, Users
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 94302f1b8a4316dec2abec2fc361d82e734549b4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197258"
---
# <a name="deviceinfo"></a><span data-ttu-id="7261d-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="7261d-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7261d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7261d-105">**Applies to:**</span></span>
- <span data-ttu-id="7261d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7261d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7261d-107">La `DeviceInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sui computer nell'organizzazione, tra cui la versione del sistema operativo, gli utenti attivi e il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="7261d-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="7261d-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7261d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7261d-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7261d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7261d-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7261d-110">Column name</span></span> | <span data-ttu-id="7261d-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7261d-111">Data type</span></span> | <span data-ttu-id="7261d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7261d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7261d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7261d-113">datetime</span></span> | <span data-ttu-id="7261d-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7261d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7261d-115">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-115">string</span></span> | <span data-ttu-id="7261d-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="7261d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7261d-117">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-117">string</span></span> | <span data-ttu-id="7261d-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="7261d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="7261d-119">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-119">string</span></span> | <span data-ttu-id="7261d-120">Versione dell'agente endpoint o del sensore in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="7261d-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="7261d-121">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-121">string</span></span> | <span data-ttu-id="7261d-122">Indirizzo IP pubblico utilizzato dal computer onboarded per la connessione al servizio ATP Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7261d-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="7261d-123">Questo potrebbe essere l'indirizzo IP del computer stesso, un dispositivo NAT o un proxy</span><span class="sxs-lookup"><span data-stu-id="7261d-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="7261d-124">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-124">string</span></span> | <span data-ttu-id="7261d-125">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="7261d-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="7261d-126">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-126">string</span></span> | <span data-ttu-id="7261d-127">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="7261d-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7261d-128">Questo indica sistemi operativi specifici, tra cui le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="7261d-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="7261d-129">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-129">string</span></span> | <span data-ttu-id="7261d-130">Versione di compilazione del sistema operativo in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="7261d-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="7261d-131">boolean</span><span class="sxs-lookup"><span data-stu-id="7261d-131">boolean</span></span> | <span data-ttu-id="7261d-132">Indicatore booleano del fatto che il computer sia aggiunto a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7261d-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="7261d-133">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-133">string</span></span> | <span data-ttu-id="7261d-134">Elenco di tutti gli utenti che hanno effettuato l'accesso al computer al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="7261d-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="7261d-135">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-135">string</span></span> | <span data-ttu-id="7261d-136">Tag del computer aggiunto tramite il registro di sistema</span><span class="sxs-lookup"><span data-stu-id="7261d-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="7261d-137">long</span><span class="sxs-lookup"><span data-stu-id="7261d-137">long</span></span> | <span data-ttu-id="7261d-138">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="7261d-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7261d-139">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="7261d-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="7261d-140">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-140">string</span></span> | <span data-ttu-id="7261d-141">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="7261d-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="7261d-142">stringa</span><span class="sxs-lookup"><span data-stu-id="7261d-142">string</span></span> | <span data-ttu-id="7261d-143">Gruppo di macchine del computer.</span><span class="sxs-lookup"><span data-stu-id="7261d-143">Machine group of the machine.</span></span> <span data-ttu-id="7261d-144">Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="7261d-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7261d-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7261d-145">Related topics</span></span>
- [<span data-ttu-id="7261d-146">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7261d-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7261d-147">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7261d-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7261d-148">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="7261d-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7261d-149">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="7261d-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7261d-150">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7261d-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7261d-151">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="7261d-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
