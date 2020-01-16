---
title: Tabella DeviceNetworkInfo nello schema di caccia avanzato
description: Informazioni sui dati di configurazione della rete nella tabella DeviceNetworkInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machinenetworkinfo, DeviceNetworkInfo, dispositivo, computer, Mac, IP, adattatore, DNS, DHCP, gateway, tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 938eb02da1b37f27f15f06ad67748a9e3beca68a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210418"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="56598-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="56598-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="56598-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="56598-105">**Applies to:**</span></span>
- <span data-ttu-id="56598-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="56598-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="56598-107">La `DeviceNetworkInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulla configurazione di rete dei computer, incluse le schede di rete, gli indirizzi IP e Mac e le reti o i domini connessi.</span><span class="sxs-lookup"><span data-stu-id="56598-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="56598-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="56598-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="56598-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="56598-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="56598-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="56598-110">Column name</span></span> | <span data-ttu-id="56598-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="56598-111">Data type</span></span> | <span data-ttu-id="56598-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56598-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="56598-113">datetime</span><span class="sxs-lookup"><span data-stu-id="56598-113">datetime</span></span> | <span data-ttu-id="56598-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="56598-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="56598-115">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-115">string</span></span> | <span data-ttu-id="56598-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="56598-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="56598-117">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-117">string</span></span> | <span data-ttu-id="56598-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="56598-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="56598-119">long</span><span class="sxs-lookup"><span data-stu-id="56598-119">long</span></span> | <span data-ttu-id="56598-120">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="56598-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="56598-121">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="56598-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="56598-122">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-122">string</span></span> | <span data-ttu-id="56598-123">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="56598-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="56598-124">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-124">string</span></span> | <span data-ttu-id="56598-125">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="56598-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="56598-126">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-126">string</span></span> | <span data-ttu-id="56598-127">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="56598-127">Network adapter type.</span></span> <span data-ttu-id="56598-128">Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="56598-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="56598-129">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-129">string</span></span> | <span data-ttu-id="56598-130">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="56598-130">Operational status of the network adapter.</span></span> <span data-ttu-id="56598-131">Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="56598-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="56598-132">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-132">string</span></span> | <span data-ttu-id="56598-133">Protocollo di tunneling, se l'interfaccia viene utilizzata per questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="56598-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="56598-134">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-134">string</span></span> | <span data-ttu-id="56598-135">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="56598-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="56598-136">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o di dominio), una descrizione e un contrassegno che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="56598-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="56598-137">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-137">string</span></span> | <span data-ttu-id="56598-138">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="56598-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="56598-139">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-139">string</span></span> | <span data-ttu-id="56598-140">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="56598-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="56598-141">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-141">string</span></span> | <span data-ttu-id="56598-142">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="56598-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="56598-143">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-143">string</span></span> | <span data-ttu-id="56598-144">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="56598-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="56598-145">stringa</span><span class="sxs-lookup"><span data-stu-id="56598-145">string</span></span> | <span data-ttu-id="56598-146">Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio di indirizzi IP, ad esempio pubblico, privato o collegamento locale</span><span class="sxs-lookup"><span data-stu-id="56598-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="56598-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="56598-147">Related topics</span></span>
- [<span data-ttu-id="56598-148">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="56598-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="56598-149">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="56598-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="56598-150">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="56598-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="56598-151">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="56598-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="56598-152">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="56598-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="56598-153">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="56598-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
