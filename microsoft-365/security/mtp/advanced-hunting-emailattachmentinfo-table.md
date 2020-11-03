---
title: Tabella EmailAttachmentInfo nello schema per Ricerca avanzata
description: Informazioni sugli allegati di posta elettronica nella tabella EmailAttachmentInfo dello schema per Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailAttachmentInfo, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di malware
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 87ebf4ca0ff773dd5622097385173f538d990afc
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847477"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `EmailAttachmentInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli allegati nei messaggi di posta elettronica elaborati da Microsoft Defender per Office 365. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AttachmentId` | stringa | Identificatore univoco dell'allegato di posta elettronica |
| `NetworkMessageId` | stringa | Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365 |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari del messaggio sui propri client di posta elettronica |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FileType` | stringa | Tipo di estensione del file |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo utilizzato per rilevare la presenza di malware nel messaggio di posta elettronica: motore antimalware, reputazione dei file, allegati sicuri |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
