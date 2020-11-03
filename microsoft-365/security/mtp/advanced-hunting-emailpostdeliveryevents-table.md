---
title: Tabella EmailPostDeliveryEvents nello schema di caccia avanzato
description: Informazioni sulle azioni di post-recapito eseguite nei messaggi di posta elettronica di Microsoft 365 nella tabella EmailPostDeliveryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailPostDeliveryEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di malware, verdetto di phishing, conteggio degli allegati
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
ms.openlocfilehash: 59e5d0d51997812689c7382d6a27af6f66a27d25
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842609"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `EmailPostDeliveryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle azioni successive al recapito eseguite nei messaggi di posta elettronica elaborati da Microsoft 365. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.

Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è anche possibile utilizzare le [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabelle, e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `EventId` | stringa | Identificatore univoco per l'evento |
| `NetworkMessageId` | stringa | Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365 |
| `InternetMessageId` | stringa | Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio |
| `Action` | stringa | Azione intrapresa nell'entità |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento: correzione manuale, phishing ZAP, malware ZAP |
| `ActionTrigger` | stringa | Indica se un'azione è stata attivata da un amministratore (manualmente o tramite approvazione di un'azione automatizzata in sospeso) o da un meccanismo speciale, ad esempio uno ZAP o un recapito dinamico. |
| `ActionResult` | stringa | Risultato dell'azione |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `DeliveryLocation` | stringa | Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati |

## <a name="supported-event-types"></a>Tipi di evento supportati
In questa tabella vengono acquisiti gli eventi con i `ActionType` valori seguenti:

- **Correzione manuale** : un amministratore ha eseguito manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente. Sono incluse le azioni eseguite manualmente tramite [Esplora minacce](../office-365-security/threat-explorer.md) o le approvazioni delle [azioni automatiche di analisi e risposta (Air)](mtp-autoir-actions.md).
- **Phishing zap** – [zero-hour auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) ha eseguito un'azione su un messaggio di posta elettronica di phishing dopo il recapito.
- **Malware zap** – zero-hour auto Purge (ZAP) ha eseguito un'azione su un messaggio di posta elettronica contenente malware dopo il recapito.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
