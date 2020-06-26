---
title: Tabella AlertEvidence nello schema di caccia avanzato
description: Informazioni sui file, sull'indirizzo di rete, sull'utente o sul dispositivo associati a avvisi generati nella tabella AlertEvidence dello schema di caccia avanzato
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899352"
---
# <a name="alertevidence"></a>AlertEvidence

**Si applica a:**
- Microsoft Threat Protection

La `AlertEvidence` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni su diverse entità, ovvero file, indirizzi IP, URL, utenti o dispositivi, associati a avvisi di Microsoft Defender atp, Office 365 ATP, Microsoft cloud app Security e Azure ATP. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AlertId` | stringa | Identificatore univoco dell'avviso |
| `EntityType` | stringa | Tipo di oggetto, ad esempio un file, un processo, un dispositivo o un utente |
| `EvidenceRole` | stringa | In che modo l'entità è coinvolta in un avviso, che indica se ha un impatto o è semplicemente correlato |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `ThreatFamily` | stringa | Famiglia di malware che il processo o il file sospetto o dannoso sono stati classificati in |
| `EvidenceDirection` | stringa | Indica se l'entità è l'origine o la destinazione di una connessione di rete |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'evento nel formato di matrice JSON |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
