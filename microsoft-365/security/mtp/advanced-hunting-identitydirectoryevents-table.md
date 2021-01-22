---
title: Tabella IdentityDirectoryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi del controller di dominio e di Active Directory nella tabella IdentityDirectoryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityDirectoryEvents, controller di dominio, Active Directory, Azure ATP, identità
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929935"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene gli eventi che coinvolgono un controller di dominio locale che `IdentityDirectoryEvents` esegue Active Directory (AD). [](advanced-hunting-overview.md) Questa tabella acquisisce vari eventi correlati all'identità, come le modifiche delle password, la scadenza delle password e le modifiche al nome dell'entità utente (UPN). Acquisisce inoltre gli eventi di sistema nel controller di dominio, ad esempio la pianificazione delle attività e l'attività di PowerShell. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere le informazioni di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) sullo schema nel portale |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `TargetAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata |
| `TargetAccountDisplayName` | stringa | Nome visualizzato dell'account a cui è stata applicata l'azione registrata |
| `TargetDeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationPort` | stringa | Porta di destinazione dell'attività |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure Active Directory |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `IPAddress` | stringa | Indirizzo IP assegnato al dispositivo durante la comunicazione |
| `Port` | stringa | Porta TCP utilizzata durante la comunicazione |
| `Location` | stringa | Città, paese o altra posizione geografica associata all'evento |
| `ISP` | stringa | Provider di servizi Internet associato all'indirizzo IP |
| `ReportId` | long | Identificatore univoco dell'evento |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
