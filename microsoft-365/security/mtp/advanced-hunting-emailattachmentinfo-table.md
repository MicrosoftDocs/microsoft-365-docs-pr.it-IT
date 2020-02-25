---
title: Tabella EmailAttachmentInfo nello schema per Ricerca avanzata
description: Informazioni sugli allegati di posta elettronica nella tabella EmailAttachmentInfo dello schema per Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailAttachmentInfo, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di malware
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
ms.openlocfilehash: d35313cf481ecd6892725ae385e7db1032565611
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234795"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Si applica a:**
- Microsoft Threat Protection



La tabella `EmailAttachmentInfo` nello schema per [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni riguardanti gli allegati dei messaggi di posta elettronica elaborati da Office 365 ATP. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AttachmentId` | stringa | Identificatore univoco dell'allegato di posta elettronica |
| `NetworkMessageId` | stringa | Identificatore univoco per la posta elettronica, generato da Office 365 |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari del messaggio sui propri client di posta elettronica |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FileType` | stringa | Tipo di estensione del file |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo utilizzato per rilevare malware nei messaggi di posta elettronica: motore antimalware, reputazione dei file, allegati sicuri di ATP |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
