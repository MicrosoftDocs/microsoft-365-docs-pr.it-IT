---
title: Tabella AlertEvidence nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate agli avvisi nella tabella AlertEvidence dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, prova, file, indirizzo IP, dispositivo, computer, utente, account
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
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932584"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni su varie entità, ad esempio file, indirizzi IP, URL, utenti o dispositivi, associate agli avvisi di `AlertEvidence` Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for [](advanced-hunting-overview.md) Identity. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AlertId` | stringa | Identificatore univoco dell'avviso |
| `ServiceSource` | stringa | Prodotto o servizio che ha fornito le informazioni sull'avviso |
| `EntityType` | stringa | Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente |
| `EvidenceRole` | stringa | In che modo l'entità è coinvolta in un avviso, che indica se è influenzata o è semplicemente correlata |
| `EvidenceDirection` | stringa | Indica se l'entità è l'origine o la destinazione di una connessione di rete |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. Questo campo in genere non viene popolato: utilizzare la colonna SHA1 quando disponibile. |
| `FileSize` | int | Dimensioni del file in byte |
| `ThreatFamily` | stringa | Famiglia di malware in cui è stato classificato il file o il processo sospetto o dannoso |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure Active Directory |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `LocalIP` | stringa | Indirizzo IP assegnato al dispositivo locale utilizzato durante la comunicazione |
| `NetworkMessageId` | stringa | Identificatore univoco per la posta elettronica, generato da Office 365 |
| `EmailSubject` | stringa | Oggetto del messaggio di posta elettronica |
| `ApplicationId` | stringa | Identificatore univoco dell'applicazione |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'evento in formato matrice JSON |
| `RegistryKey` |stringa | Chiave del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` |stringa | Nome del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` |stringa | Dati del valore del Registro di sistema a cui è stata applicata l'azione registrata |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
