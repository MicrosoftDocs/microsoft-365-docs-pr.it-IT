---
title: Tabella EmailAttachmentInfo nello schema per Ricerca avanzata
description: Informazioni sugli allegati di posta elettronica nella tabella EmailAttachmentInfo dello schema per Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailAttachmentInfo, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto malware
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c6cab4d813eba79e298d0082072888e3ef1ad1cd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927003"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sugli allegati nei messaggi di posta elettronica `EmailAttachmentInfo` elaborati da Microsoft Defender per Office 365. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `AttachmentId` | stringa | Identificatore univoco dell'allegato di posta elettronica |
| `NetworkMessageId` | stringa | Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365 |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari del messaggio sui propri client di posta elettronica |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FileType` | stringa | Tipo di estensione del file |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo usato per rilevare malware nella posta elettronica: motore antimalware, reputazione file, allegati sicuri |
| `SenderDisplayName` | stringa | Nome del mittente visualizzato nella rubrica, in genere una combinazione di nome o nome, secondo nome e cognome o cognome |
| `SenderObjectId` | stringa | Identificatore univoco dell'account del mittente in Azure AD |
| `ThreatTypes` | stringa | Verdetto dello stack di filtro della posta elettronica che indica se il messaggio di posta elettronica contiene malware, phishing o altre minacce |
| `ThreatNames` | stringa | Nome di rilevamento per malware o altre minacce rilevate |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
