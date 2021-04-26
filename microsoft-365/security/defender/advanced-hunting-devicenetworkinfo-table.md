---
title: Tabella DeviceNetworkInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla configurazione di rete nella tabella DeviceNetworkInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machinenetworkinfo, DeviceNetworkInfo, dispositivo, computer, mac, ip, scheda, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023190"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="2e3ee-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="2e3ee-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2e3ee-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2e3ee-105">**Applies to:**</span></span>
- <span data-ttu-id="2e3ee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e3ee-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="2e3ee-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2e3ee-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="2e3ee-108">La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei computer, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` o domini connessi. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2e3ee-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="2e3ee-109">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2e3ee-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2e3ee-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2e3ee-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2e3ee-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2e3ee-111">Column name</span></span> | <span data-ttu-id="2e3ee-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2e3ee-112">Data type</span></span> | <span data-ttu-id="2e3ee-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e3ee-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2e3ee-114">datetime</span><span class="sxs-lookup"><span data-stu-id="2e3ee-114">datetime</span></span> | <span data-ttu-id="2e3ee-115">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="2e3ee-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2e3ee-116">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-116">string</span></span> | <span data-ttu-id="2e3ee-117">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="2e3ee-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2e3ee-118">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-118">string</span></span> | <span data-ttu-id="2e3ee-119">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="2e3ee-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="2e3ee-120">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-120">string</span></span> | <span data-ttu-id="2e3ee-121">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="2e3ee-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="2e3ee-122">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-122">string</span></span> | <span data-ttu-id="2e3ee-123">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="2e3ee-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="2e3ee-124">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-124">string</span></span> | <span data-ttu-id="2e3ee-125">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="2e3ee-125">Network adapter type.</span></span> <span data-ttu-id="2e3ee-126">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="2e3ee-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="2e3ee-127">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-127">string</span></span> | <span data-ttu-id="2e3ee-128">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="2e3ee-128">Operational status of the network adapter.</span></span> <span data-ttu-id="2e3ee-129">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="2e3ee-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="2e3ee-130">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-130">string</span></span> | <span data-ttu-id="2e3ee-131">Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="2e3ee-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="2e3ee-132">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-132">string</span></span> | <span data-ttu-id="2e3ee-133">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="2e3ee-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="2e3ee-134">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="2e3ee-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="2e3ee-135">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-135">string</span></span> | <span data-ttu-id="2e3ee-136">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="2e3ee-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="2e3ee-137">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-137">string</span></span> | <span data-ttu-id="2e3ee-138">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="2e3ee-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="2e3ee-139">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-139">string</span></span> | <span data-ttu-id="2e3ee-140">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="2e3ee-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="2e3ee-141">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-141">string</span></span> | <span data-ttu-id="2e3ee-142">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="2e3ee-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="2e3ee-143">stringa</span><span class="sxs-lookup"><span data-stu-id="2e3ee-143">string</span></span> | <span data-ttu-id="2e3ee-144">Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio degli indirizzi IP, ad esempio pubblico, privato o locale di collegamento</span><span class="sxs-lookup"><span data-stu-id="2e3ee-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="2e3ee-145">long</span><span class="sxs-lookup"><span data-stu-id="2e3ee-145">long</span></span> | <span data-ttu-id="2e3ee-146">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="2e3ee-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2e3ee-147">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="2e3ee-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2e3ee-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2e3ee-148">Related topics</span></span>
- [<span data-ttu-id="2e3ee-149">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="2e3ee-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2e3ee-150">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2e3ee-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2e3ee-151">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2e3ee-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2e3ee-152">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="2e3ee-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2e3ee-153">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="2e3ee-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2e3ee-154">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2e3ee-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)