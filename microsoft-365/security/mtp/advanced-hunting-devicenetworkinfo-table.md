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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3e3b657d1c33e411f38a8f583adb96139cc85207
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907397"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sulla configurazione di rete dei computer, tra cui schede di rete, indirizzi IP e MAC e reti `DeviceNetworkInfo` o domini connessi. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
| `NetworkAdapterName` | stringa | Nome della scheda di rete |
| `MacAddress` | stringa | Indirizzo MAC della scheda di rete |
| `NetworkAdapterType` | stringa | Tipo di scheda di rete. Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | stringa | Stato operativo della scheda di rete. Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | stringa | Protocollo di tunneling, se l'interfaccia viene utilizzata a questo scopo, ad esempio 6to4, Teredo, ISATAP, PPTP, SSTP e SSH |
| `ConnectedNetworks` | stringa | Reti a cui è connessa la scheda. Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet |
| `DnsAddresses` | stringa | Indirizzi del server DNS in formato matrice JSON |
| `IPv4Dhcp` | stringa | Indirizzo IPv4 del server DHCP |
| `IPv6Dhcp` | stringa | Indirizzo IPv6 del server DHCP |
| `DefaultGateways` | stringa | Indirizzi gateway predefiniti in formato matrice JSON |
| `IPAddresses` | stringa | Matrice JSON contenente tutti gli indirizzi IP assegnati alla scheda, insieme al rispettivo prefisso di subnet e allo spazio degli indirizzi IP, ad esempio pubblico, privato o locale di collegamento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)