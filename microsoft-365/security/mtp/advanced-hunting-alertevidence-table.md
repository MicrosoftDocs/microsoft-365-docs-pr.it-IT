---
title: Tabella AlertEvidence nello schema di caccia avanzato
description: Informazioni sui dati associati agli avvisi nella tabella AlertEvidence dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, evidenza, file, indirizzo IP, dispositivo, computer, utente, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430164"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

La `AlertEvidence` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni su diverse entità, ovvero file, indirizzi IP, URL, utenti o dispositivi, associati a avvisi di Microsoft Defender atp, Office 365 ATP, Microsoft cloud app Security e Azure ATP. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AlertId` | stringa | Identificatore univoco dell'avviso |
| `ServiceSource` | stringa | Prodotto o servizio che ha fornito le informazioni sugli avvisi |
| `EntityType` | stringa | Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente |
| `EvidenceRole` | stringa | In che modo l'entità è coinvolta in un avviso, che indica se ha un impatto o è semplicemente correlato |
| `EvidenceDirection` | stringa | Indica se l'entità è l'origine o la destinazione di una connessione di rete |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1. |
| `FileSize` | int | Dimensione del file in byte |
| `ThreatFamily` | stringa | Famiglia di malware che il processo o il file sospetto o dannoso sono stati classificati in |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure Active Directory |
| `DeviceId` | stringa | Identificatore univoco per il dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `LocalIP` | stringa | Indirizzo IP assegnato al dispositivo locale utilizzato durante la comunicazione |
| `NetworkMessageId` | stringa | Identificatore univoco per la posta elettronica, generato da Office 365 |
| `EmailSubject` | stringa | Oggetto del messaggio di posta elettronica |
| `ApplicationId` | stringa | Identificatore univoco per l'applicazione |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'evento nel formato di matrice JSON |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
