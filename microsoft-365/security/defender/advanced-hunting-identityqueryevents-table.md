---
title: Tabella IdentityQueryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di query di Active Directory nella tabella IdentityQueryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identità, query LDAP
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
ms.openlocfilehash: 40383524ffe26326800369570856499d149e31c3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500388"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sulle query eseguite su oggetti Active Directory, ad esempio `IdentityQueryEvents` utenti, gruppi, dispositivi [](advanced-hunting-overview.md) e domini. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) informazioni di riferimento sullo schema nel portale |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `QueryType` | stringa | Tipo di query, ad esempio QueryGroup, QueryUser o EnumerateUsers |
| `QueryTarget` | stringa | Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query |
| `Query` | stringa | Stringa utilizzata per eseguire la query |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) dell'endpoint |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `Port` | stringa | Porta TCP utilizzata durante la comunicazione |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationPort` | stringa | Porta di destinazione delle comunicazioni di rete correlate |
| `TargetDeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata |
| `TargetAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata |
| `TargetAccountDisplayName` | stringa | Nome visualizzato dell'account a cui è stata applicata l'azione registrata |
| `Location` | stringa | Città, paese o altra posizione geografica associata all'evento |
| `ReportId` | long | Identificatore univoco dell'evento |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
