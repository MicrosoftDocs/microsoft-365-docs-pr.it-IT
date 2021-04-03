---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni sul sistema operativo, sul nome del computer e su altre informazioni sul dispositivo nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, deviceinfo, dispositivo, sistema operativo, piattaforma, utenti, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500825"
---
# <a name="deviceinfo"></a><span data-ttu-id="131b4-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="131b4-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="131b4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="131b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="131b4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="131b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="131b4-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="131b4-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="131b4-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="131b4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="131b4-109">La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="131b4-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="131b4-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="131b4-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="131b4-111">Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="131b4-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="131b4-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="131b4-112">Column name</span></span> | <span data-ttu-id="131b4-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="131b4-113">Data type</span></span> | <span data-ttu-id="131b4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="131b4-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="131b4-115">datetime</span><span class="sxs-lookup"><span data-stu-id="131b4-115">datetime</span></span> | <span data-ttu-id="131b4-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="131b4-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="131b4-117">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-117">string</span></span> | <span data-ttu-id="131b4-118">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="131b4-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="131b4-119">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-119">string</span></span> | <span data-ttu-id="131b4-120">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="131b4-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="131b4-121">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-121">string</span></span> | <span data-ttu-id="131b4-122">Versione dell'agente endpoint o del sensore in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="131b4-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="131b4-123">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-123">string</span></span> | <span data-ttu-id="131b4-124">Indirizzo IP pubblico usato dal dispositivo onboarded per connettersi al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="131b4-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="131b4-125">Può trattarsi dell'indirizzo IP del dispositivo stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="131b4-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="131b4-126">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-126">string</span></span> | <span data-ttu-id="131b4-127">Architettura del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="131b4-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="131b4-128">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-128">string</span></span> | <span data-ttu-id="131b4-129">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="131b4-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="131b4-130">Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="131b4-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="131b4-131">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-131">string</span></span> | <span data-ttu-id="131b4-132">Versione build del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="131b4-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="131b4-133">boolean</span><span class="sxs-lookup"><span data-stu-id="131b4-133">boolean</span></span> | <span data-ttu-id="131b4-134">Indicatore booleano che indica se il dispositivo è aggiunto ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="131b4-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="131b4-135">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-135">string</span></span> | <span data-ttu-id="131b4-136">Elenco di tutti gli utenti connessi al dispositivo al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="131b4-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="131b4-137">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-137">string</span></span> | <span data-ttu-id="131b4-138">Tag dispositivo aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="131b4-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="131b4-139">long</span><span class="sxs-lookup"><span data-stu-id="131b4-139">long</span></span> | <span data-ttu-id="131b4-140">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="131b4-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="131b4-141">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="131b4-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="131b4-142">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-142">string</span></span> | <span data-ttu-id="131b4-143">Versione del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="131b4-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="131b4-144">stringa</span><span class="sxs-lookup"><span data-stu-id="131b4-144">string</span></span> | <span data-ttu-id="131b4-145">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="131b4-145">Machine group of the machine.</span></span> <span data-ttu-id="131b4-146">Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="131b4-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="131b4-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="131b4-147">Related topics</span></span>
- [<span data-ttu-id="131b4-148">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="131b4-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="131b4-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="131b4-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="131b4-150">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="131b4-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
