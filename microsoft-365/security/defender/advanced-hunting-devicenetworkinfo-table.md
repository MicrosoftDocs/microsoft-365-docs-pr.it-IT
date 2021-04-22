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
ms.openlocfilehash: e6bfb781b3454025c5ce0f43899180c91761a56d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932560"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="9aa7e-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="9aa7e-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9aa7e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9aa7e-105">**Applies to:**</span></span>
- <span data-ttu-id="9aa7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9aa7e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9aa7e-107">La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei computer, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` o domini connessi. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9aa7e-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="9aa7e-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="9aa7e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9aa7e-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9aa7e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9aa7e-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9aa7e-110">Column name</span></span> | <span data-ttu-id="9aa7e-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9aa7e-111">Data type</span></span> | <span data-ttu-id="9aa7e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9aa7e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9aa7e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9aa7e-113">datetime</span></span> | <span data-ttu-id="9aa7e-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="9aa7e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9aa7e-115">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-115">string</span></span> | <span data-ttu-id="9aa7e-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="9aa7e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9aa7e-117">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-117">string</span></span> | <span data-ttu-id="9aa7e-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="9aa7e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="9aa7e-119">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-119">string</span></span> | <span data-ttu-id="9aa7e-120">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="9aa7e-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="9aa7e-121">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-121">string</span></span> | <span data-ttu-id="9aa7e-122">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="9aa7e-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="9aa7e-123">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-123">string</span></span> | <span data-ttu-id="9aa7e-124">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="9aa7e-124">Network adapter type.</span></span> <span data-ttu-id="9aa7e-125">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9aa7e-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="9aa7e-126">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-126">string</span></span> | <span data-ttu-id="9aa7e-127">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="9aa7e-127">Operational status of the network adapter.</span></span> <span data-ttu-id="9aa7e-128">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9aa7e-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="9aa7e-129">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-129">string</span></span> | <span data-ttu-id="9aa7e-130">Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="9aa7e-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="9aa7e-131">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-131">string</span></span> | <span data-ttu-id="9aa7e-132">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="9aa7e-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="9aa7e-133">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="9aa7e-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="9aa7e-134">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-134">string</span></span> | <span data-ttu-id="9aa7e-135">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="9aa7e-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="9aa7e-136">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-136">string</span></span> | <span data-ttu-id="9aa7e-137">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="9aa7e-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="9aa7e-138">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-138">string</span></span> | <span data-ttu-id="9aa7e-139">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="9aa7e-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="9aa7e-140">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-140">string</span></span> | <span data-ttu-id="9aa7e-141">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="9aa7e-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="9aa7e-142">stringa</span><span class="sxs-lookup"><span data-stu-id="9aa7e-142">string</span></span> | <span data-ttu-id="9aa7e-143">Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio degli indirizzi IP, ad esempio pubblico, privato o locale di collegamento</span><span class="sxs-lookup"><span data-stu-id="9aa7e-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="9aa7e-144">long</span><span class="sxs-lookup"><span data-stu-id="9aa7e-144">long</span></span> | <span data-ttu-id="9aa7e-145">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="9aa7e-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9aa7e-146">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="9aa7e-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9aa7e-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9aa7e-147">Related topics</span></span>
- [<span data-ttu-id="9aa7e-148">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="9aa7e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9aa7e-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="9aa7e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9aa7e-150">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="9aa7e-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9aa7e-151">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="9aa7e-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9aa7e-152">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="9aa7e-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9aa7e-153">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="9aa7e-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)