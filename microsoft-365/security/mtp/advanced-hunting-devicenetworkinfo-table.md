---
title: Tabella DeviceNetworkInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla configurazione di rete nella tabella DeviceNetworkInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machinenetworkinfo, DeviceNetworkInfo, dispositivo, computer, mac, ip, scheda, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931207"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="7c1b9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="7c1b9-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7c1b9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7c1b9-105">**Applies to:**</span></span>
- <span data-ttu-id="7c1b9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c1b9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7c1b9-107">La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei computer, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` o domini connessi. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7c1b9-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="7c1b9-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7c1b9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7c1b9-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7c1b9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7c1b9-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7c1b9-110">Column name</span></span> | <span data-ttu-id="7c1b9-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7c1b9-111">Data type</span></span> | <span data-ttu-id="7c1b9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1b9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7c1b9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7c1b9-113">datetime</span></span> | <span data-ttu-id="7c1b9-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7c1b9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7c1b9-115">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-115">string</span></span> | <span data-ttu-id="7c1b9-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="7c1b9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7c1b9-117">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-117">string</span></span> | <span data-ttu-id="7c1b9-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="7c1b9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="7c1b9-119">long</span><span class="sxs-lookup"><span data-stu-id="7c1b9-119">long</span></span> | <span data-ttu-id="7c1b9-120">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="7c1b9-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7c1b9-121">Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="7c1b9-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="7c1b9-122">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-122">string</span></span> | <span data-ttu-id="7c1b9-123">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="7c1b9-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="7c1b9-124">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-124">string</span></span> | <span data-ttu-id="7c1b9-125">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="7c1b9-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="7c1b9-126">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-126">string</span></span> | <span data-ttu-id="7c1b9-127">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="7c1b9-127">Network adapter type.</span></span> <span data-ttu-id="7c1b9-128">Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7c1b9-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="7c1b9-129">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-129">string</span></span> | <span data-ttu-id="7c1b9-130">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="7c1b9-130">Operational status of the network adapter.</span></span> <span data-ttu-id="7c1b9-131">Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7c1b9-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="7c1b9-132">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-132">string</span></span> | <span data-ttu-id="7c1b9-133">Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="7c1b9-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="7c1b9-134">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-134">string</span></span> | <span data-ttu-id="7c1b9-135">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="7c1b9-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="7c1b9-136">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="7c1b9-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="7c1b9-137">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-137">string</span></span> | <span data-ttu-id="7c1b9-138">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="7c1b9-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="7c1b9-139">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-139">string</span></span> | <span data-ttu-id="7c1b9-140">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="7c1b9-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="7c1b9-141">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-141">string</span></span> | <span data-ttu-id="7c1b9-142">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="7c1b9-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="7c1b9-143">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-143">string</span></span> | <span data-ttu-id="7c1b9-144">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="7c1b9-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="7c1b9-145">stringa</span><span class="sxs-lookup"><span data-stu-id="7c1b9-145">string</span></span> | <span data-ttu-id="7c1b9-146">Array JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e spazio degli indirizzi IP, ad esempio pubblico, privato o locale del collegamento</span><span class="sxs-lookup"><span data-stu-id="7c1b9-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7c1b9-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7c1b9-147">Related topics</span></span>
- [<span data-ttu-id="7c1b9-148">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7c1b9-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7c1b9-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7c1b9-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7c1b9-150">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="7c1b9-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7c1b9-151">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="7c1b9-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7c1b9-152">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7c1b9-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7c1b9-153">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="7c1b9-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
