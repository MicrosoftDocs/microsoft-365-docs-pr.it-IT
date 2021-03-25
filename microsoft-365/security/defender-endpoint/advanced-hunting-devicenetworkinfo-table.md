---
title: Tabella DeviceNetworkInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla configurazione di rete nella tabella DeviceNetworkInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, devicenetworkinfo, dispositivo, dispositivo, mac, ip, scheda, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
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
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067053"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="e27f7-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="e27f7-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e27f7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e27f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="e27f7-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e27f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="e27f7-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e27f7-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e27f7-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e27f7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="e27f7-109">La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei dispositivi, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` connesse o domini. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e27f7-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="e27f7-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e27f7-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e27f7-111">Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="e27f7-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="e27f7-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e27f7-112">Column name</span></span> | <span data-ttu-id="e27f7-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e27f7-113">Data type</span></span> | <span data-ttu-id="e27f7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e27f7-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e27f7-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e27f7-115">datetime</span></span> | <span data-ttu-id="e27f7-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="e27f7-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e27f7-117">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-117">string</span></span> | <span data-ttu-id="e27f7-118">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="e27f7-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e27f7-119">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-119">string</span></span> | <span data-ttu-id="e27f7-120">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e27f7-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="e27f7-121">long</span><span class="sxs-lookup"><span data-stu-id="e27f7-121">long</span></span> | <span data-ttu-id="e27f7-122">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e27f7-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e27f7-123">Per identificare eventi univoci, è necessario utilizzare questa colonna insieme alle `DeviceName` colonne e `Timestamp`</span><span class="sxs-lookup"><span data-stu-id="e27f7-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="e27f7-124">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-124">string</span></span> | <span data-ttu-id="e27f7-125">Nome della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="e27f7-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="e27f7-126">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-126">string</span></span> | <span data-ttu-id="e27f7-127">Indirizzo MAC della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="e27f7-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="e27f7-128">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-128">string</span></span> | <span data-ttu-id="e27f7-129">Tipo di scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="e27f7-129">Network adapter type.</span></span> <span data-ttu-id="e27f7-130">Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="e27f7-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="e27f7-131">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-131">string</span></span> | <span data-ttu-id="e27f7-132">Stato operativo della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="e27f7-132">Operational status of the network adapter.</span></span> <span data-ttu-id="e27f7-133">Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="e27f7-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="e27f7-134">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-134">string</span></span> | <span data-ttu-id="e27f7-135">Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="e27f7-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="e27f7-136">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-136">string</span></span> | <span data-ttu-id="e27f7-137">Reti a cui è connessa la scheda.</span><span class="sxs-lookup"><span data-stu-id="e27f7-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="e27f7-138">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="e27f7-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="e27f7-139">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-139">string</span></span> | <span data-ttu-id="e27f7-140">Indirizzi del server DNS in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="e27f7-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="e27f7-141">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-141">string</span></span> | <span data-ttu-id="e27f7-142">Indirizzo IPv4 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="e27f7-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="e27f7-143">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-143">string</span></span> | <span data-ttu-id="e27f7-144">Indirizzo IPv6 del server DHCP</span><span class="sxs-lookup"><span data-stu-id="e27f7-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="e27f7-145">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-145">string</span></span> | <span data-ttu-id="e27f7-146">Indirizzi gateway predefiniti in formato matrice JSON</span><span class="sxs-lookup"><span data-stu-id="e27f7-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="e27f7-147">stringa</span><span class="sxs-lookup"><span data-stu-id="e27f7-147">string</span></span> | <span data-ttu-id="e27f7-148">Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio degli indirizzi IP, ad esempio pubblico, privato o locale di collegamento</span><span class="sxs-lookup"><span data-stu-id="e27f7-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e27f7-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e27f7-149">Related topics</span></span>
- [<span data-ttu-id="e27f7-150">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="e27f7-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e27f7-151">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="e27f7-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e27f7-152">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="e27f7-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)