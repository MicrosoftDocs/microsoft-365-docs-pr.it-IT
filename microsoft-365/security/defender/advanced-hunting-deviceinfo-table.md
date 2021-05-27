---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni sul sistema operativo, sul nome del computer e su altre informazioni sul computer nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, dispositivo, computer, sistema operativo, piattaforma, utenti
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689110"
---
# <a name="deviceinfo"></a><span data-ttu-id="2a3dd-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="2a3dd-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a3dd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2a3dd-105">**Applies to:**</span></span>
- <span data-ttu-id="2a3dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a3dd-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="2a3dd-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2a3dd-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="2a3dd-108">La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2a3dd-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="2a3dd-109">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2a3dd-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2a3dd-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2a3dd-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2a3dd-111">Column name</span></span> | <span data-ttu-id="2a3dd-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2a3dd-112">Data type</span></span> | <span data-ttu-id="2a3dd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a3dd-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2a3dd-114">datetime</span><span class="sxs-lookup"><span data-stu-id="2a3dd-114">datetime</span></span> | <span data-ttu-id="2a3dd-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="2a3dd-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2a3dd-116">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-116">string</span></span> | <span data-ttu-id="2a3dd-117">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="2a3dd-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2a3dd-118">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-118">string</span></span> | <span data-ttu-id="2a3dd-119">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="2a3dd-120">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-120">string</span></span> | <span data-ttu-id="2a3dd-121">Versione dell'agente endpoint o del sensore in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="2a3dd-122">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-122">string</span></span> | <span data-ttu-id="2a3dd-123">Indirizzo IP pubblico utilizzato dal computer onboarded per connettersi al servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="2a3dd-124">Può trattarsi dell'indirizzo IP del computer stesso, di un dispositivo NAT o di un proxy</span><span class="sxs-lookup"><span data-stu-id="2a3dd-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="2a3dd-125">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-125">string</span></span> | <span data-ttu-id="2a3dd-126">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2a3dd-127">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-127">string</span></span> | <span data-ttu-id="2a3dd-128">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2a3dd-129">Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="2a3dd-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="2a3dd-130">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-130">string</span></span> | <span data-ttu-id="2a3dd-131">Versione build del sistema operativo in esecuzione nel computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="2a3dd-132">boolean</span><span class="sxs-lookup"><span data-stu-id="2a3dd-132">boolean</span></span> | <span data-ttu-id="2a3dd-133">Indicatore booleano che indica se il computer è aggiunto al Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a3dd-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="2a3dd-134">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-134">string</span></span> | <span data-ttu-id="2a3dd-135">Identificatore univoco per il dispositivo in Azure AD</span><span class="sxs-lookup"><span data-stu-id="2a3dd-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="2a3dd-136">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-136">string</span></span> | <span data-ttu-id="2a3dd-137">Elenco di tutti gli utenti connessi al computer al momento dell'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="2a3dd-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="2a3dd-138">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-138">string</span></span> | <span data-ttu-id="2a3dd-139">Tag computer aggiunto tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2a3dd-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="2a3dd-140">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-140">string</span></span> | <span data-ttu-id="2a3dd-141">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="2a3dd-142">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-142">string</span></span> | <span data-ttu-id="2a3dd-143">Gruppo di computer del computer.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-143">Machine group of the machine.</span></span> <span data-ttu-id="2a3dd-144">Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer</span><span class="sxs-lookup"><span data-stu-id="2a3dd-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="2a3dd-145">long</span><span class="sxs-lookup"><span data-stu-id="2a3dd-145">long</span></span> | <span data-ttu-id="2a3dd-146">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2a3dd-147">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="2a3dd-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="2a3dd-148">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-148">string</span></span> | <span data-ttu-id="2a3dd-149">Indica se il dispositivo è attualmente onboarded o meno in Microsoft Defender For Endpoint o se il dispositivo non è supportato</span><span class="sxs-lookup"><span data-stu-id="2a3dd-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="2a3dd-150">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-150">string</span></span> | <span data-ttu-id="2a3dd-151">Informazioni aggiuntive sull'evento in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="2a3dd-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="2a3dd-152">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-152">string</span></span> | <span data-ttu-id="2a3dd-153">Classificazione più ampia che raggruppa determinati tipi di dispositivi nelle categorie seguenti: Endpoint, Dispositivo di rete, IoT, Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="2a3dd-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="2a3dd-154">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-154">string</span></span> | <span data-ttu-id="2a3dd-155">Tipo di dispositivo basato su scopo e funzionalità, ad esempio dispositivo di rete, workstation, server, mobile, console di gioco o stampante</span><span class="sxs-lookup"><span data-stu-id="2a3dd-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="2a3dd-156">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-156">string</span></span> | <span data-ttu-id="2a3dd-157">Modificatore aggiuntivo per determinati tipi di dispositivi, ad esempio, un dispositivo mobile può essere un tablet o uno smartphone</span><span class="sxs-lookup"><span data-stu-id="2a3dd-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="2a3dd-158">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-158">string</span></span> | <span data-ttu-id="2a3dd-159">Nome del modello o numero del prodotto dal fornitore o dal produttore</span><span class="sxs-lookup"><span data-stu-id="2a3dd-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="2a3dd-160">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-160">string</span></span> | <span data-ttu-id="2a3dd-161">Nome del fornitore o del produttore del prodotto</span><span class="sxs-lookup"><span data-stu-id="2a3dd-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="2a3dd-162">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-162">string</span></span> | <span data-ttu-id="2a3dd-163">Distribuzione della piattaforma del sistema operativo, ad esempio Ubuntu o RedHat per piattaforme Linux</span><span class="sxs-lookup"><span data-stu-id="2a3dd-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="2a3dd-164">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-164">string</span></span> | <span data-ttu-id="2a3dd-165">Ulteriori informazioni sulla versione del sistema operativo, ad esempio il nome popolare, il nome in codice o il numero di versione</span><span class="sxs-lookup"><span data-stu-id="2a3dd-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="2a3dd-166">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-166">string</span></span> | <span data-ttu-id="2a3dd-167">ID dispositivo precedenti assegnati allo stesso dispositivo</span><span class="sxs-lookup"><span data-stu-id="2a3dd-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="2a3dd-168">stringa</span><span class="sxs-lookup"><span data-stu-id="2a3dd-168">string</span></span> | <span data-ttu-id="2a3dd-169">L'ID dispositivo più recente assegnato a un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2a3dd-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="2a3dd-170">La `DeviceInfo` tabella fornisce informazioni sul dispositivo in base agli heartbeat, ovvero report periodici o segnali provenienti da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="2a3dd-171">Ogni quindici minuti, il dispositivo invia un heartbeat parziale che contiene attributi che cambiano frequentemente, ad esempio `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="2a3dd-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="2a3dd-172">Una volta al giorno, viene inviato un heartbeat completo contenente gli attributi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a3dd-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="2a3dd-173">Puoi usare la query di esempio seguente per ottenere lo stato più recente di un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="2a3dd-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="2a3dd-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a3dd-174">Related topics</span></span>
- [<span data-ttu-id="2a3dd-175">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="2a3dd-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a3dd-176">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2a3dd-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a3dd-177">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2a3dd-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2a3dd-178">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="2a3dd-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2a3dd-179">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="2a3dd-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a3dd-180">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2a3dd-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
