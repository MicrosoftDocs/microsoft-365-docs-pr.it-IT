---
title: Tabella DeviceNetworkInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla configurazione di rete nella tabella DeviceNetworkInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machinenetworkinfo, DeviceNetworkInfo, dispositivo, computer, mac, ip, scheda, dns, dhcp, gateway, tunnel
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9a3806d3e2bff66e04f4adb50217fc1c6f267364
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382604"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="f8935-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="f8935-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8935-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f8935-105">**Applies to:**</span></span>
- <span data-ttu-id="f8935-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8935-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f8935-107">La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei computer, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` o domini connessi. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f8935-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="f8935-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="f8935-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f8935-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f8935-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f8935-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="f8935-110">Column name</span></span> | <span data-ttu-id="f8935-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f8935-111">Data type</span></span> | <span data-ttu-id="f8935-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8935-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f8935-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f8935-113">datetime</span></span> | <span data-ttu-id="f8935-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f8935-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f8935-115">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-115">string</span></span> | <span data-ttu-id="f8935-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="f8935-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f8935-117">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-117">string</span></span> | <span data-ttu-id="f8935-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="f8935-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="f8935-119">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-119">string</span></span> | <span data-ttu-id="f8935-120">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="f8935-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="f8935-121">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-121">string</span></span> | <span data-ttu-id="f8935-122">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="f8935-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f8935-123">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-123">string</span></span> | <span data-ttu-id="f8935-124">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="f8935-124">Network adapter type.</span></span> <span data-ttu-id="f8935-125">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f8935-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="f8935-126">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-126">string</span></span> | <span data-ttu-id="f8935-127">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="f8935-127">Operational status of the network adapter.</span></span> <span data-ttu-id="f8935-128">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f8935-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="f8935-129">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-129">string</span></span> | <span data-ttu-id="f8935-130">Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="f8935-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f8935-131">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-131">string</span></span> | <span data-ttu-id="f8935-132">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="f8935-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="f8935-133">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="f8935-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="f8935-134">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-134">string</span></span> | <span data-ttu-id="f8935-135">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="f8935-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="f8935-136">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-136">string</span></span> | <span data-ttu-id="f8935-137">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="f8935-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="f8935-138">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-138">string</span></span> | <span data-ttu-id="f8935-139">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="f8935-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="f8935-140">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-140">string</span></span> | <span data-ttu-id="f8935-141">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="f8935-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="f8935-142">stringa</span><span class="sxs-lookup"><span data-stu-id="f8935-142">string</span></span> | <span data-ttu-id="f8935-143">Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio degli indirizzi IP, ad esempio pubblico, privato o locale di collegamento</span><span class="sxs-lookup"><span data-stu-id="f8935-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="f8935-144">long</span><span class="sxs-lookup"><span data-stu-id="f8935-144">long</span></span> | <span data-ttu-id="f8935-145">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="f8935-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f8935-146">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="f8935-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f8935-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f8935-147">Related topics</span></span>
- [<span data-ttu-id="f8935-148">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="f8935-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f8935-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="f8935-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f8935-150">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="f8935-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f8935-151">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="f8935-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f8935-152">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="f8935-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f8935-153">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="f8935-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)