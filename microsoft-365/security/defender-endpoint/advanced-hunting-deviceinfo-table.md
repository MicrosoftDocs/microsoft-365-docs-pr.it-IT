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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067066"
---
# <a name="deviceinfo"></a><span data-ttu-id="0c436-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="0c436-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c436-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0c436-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c436-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0c436-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="0c436-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0c436-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c436-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0c436-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="0c436-109">La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0c436-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="0c436-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="0c436-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0c436-111">Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="0c436-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="0c436-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0c436-112">Column name</span></span> | <span data-ttu-id="0c436-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0c436-113">Data type</span></span> | <span data-ttu-id="0c436-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c436-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c436-115">datetime</span><span class="sxs-lookup"><span data-stu-id="0c436-115">datetime</span></span> | <span data-ttu-id="0c436-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="0c436-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0c436-117">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-117">string</span></span> | <span data-ttu-id="0c436-118">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="0c436-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0c436-119">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-119">string</span></span> | <span data-ttu-id="0c436-120">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c436-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="0c436-121">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-121">string</span></span> | <span data-ttu-id="0c436-122">Versione dell'agente endpoint o del sensore in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c436-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="0c436-123">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-123">string</span></span> | <span data-ttu-id="0c436-124">Indirizzo IP pubblico usato dal dispositivo onboarded per connettersi al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0c436-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="0c436-125">Può trattarsi dell'indirizzo IP del dispositivo stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="0c436-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="0c436-126">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-126">string</span></span> | <span data-ttu-id="0c436-127">Architettura del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c436-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="0c436-128">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-128">string</span></span> | <span data-ttu-id="0c436-129">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c436-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0c436-130">Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="0c436-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="0c436-131">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-131">string</span></span> | <span data-ttu-id="0c436-132">Versione build del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c436-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="0c436-133">boolean</span><span class="sxs-lookup"><span data-stu-id="0c436-133">boolean</span></span> | <span data-ttu-id="0c436-134">Indicatore booleano che indica se il dispositivo è aggiunto ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c436-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="0c436-135">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-135">string</span></span> | <span data-ttu-id="0c436-136">Elenco di tutti gli utenti connessi al dispositivo al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="0c436-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="0c436-137">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-137">string</span></span> | <span data-ttu-id="0c436-138">Tag dispositivo aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="0c436-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="0c436-139">long</span><span class="sxs-lookup"><span data-stu-id="0c436-139">long</span></span> | <span data-ttu-id="0c436-140">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="0c436-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0c436-141">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="0c436-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="0c436-142">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-142">string</span></span> | <span data-ttu-id="0c436-143">Versione del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c436-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="0c436-144">stringa</span><span class="sxs-lookup"><span data-stu-id="0c436-144">string</span></span> | <span data-ttu-id="0c436-145">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="0c436-145">Machine group of the machine.</span></span> <span data-ttu-id="0c436-146">Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="0c436-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0c436-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c436-147">Related topics</span></span>
- [<span data-ttu-id="0c436-148">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="0c436-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c436-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="0c436-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c436-150">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="0c436-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
