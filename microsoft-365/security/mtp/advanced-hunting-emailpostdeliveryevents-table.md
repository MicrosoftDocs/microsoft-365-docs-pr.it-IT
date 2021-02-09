---
title: Tabella EmailPostDeliveryEvents nello schema di ricerca avanzata
description: Informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica di Microsoft 365 nella tabella EmailPostDeliveryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailPostDeliveryEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di phishing, verdetto phishing, numero di allegati, numero di collegamenti, numero di url
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
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145500"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica `EmailPostDeliveryEvents` elaborati da Microsoft 365. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è inoltre possibile utilizzare le tabelle [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) , e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `NetworkMessageId` | stringa | Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365 |
| `InternetMessageId` | stringa | Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio |
| `Action` | stringa | Azione eseguita sull'entità |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento: correzione manuale, Phish ZAP, Malware ZAP |
| `ActionTrigger` | stringa | Indica se un'azione è stata attivata da un amministratore (manualmente o tramite l'approvazione di un'azione automatica in sospeso) o da un meccanismo speciale, ad esempio zap o recapito dinamico |
| `ActionResult` | stringa | Risultato dell'azione |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `DeliveryLocation` | stringa | Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp. |

## <a name="supported-event-types"></a>Tipi di evento supportati
Questa tabella acquisisce gli eventi con i valori `ActionType` seguenti:

- **Correzione manuale: un** amministratore ha preso manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente. Sono incluse le azioni eseguite manualmente tramite [Esplora](../office-365-security/threat-explorer.md) minacce o le approvazioni di azioni di analisi e risposta [automatizzate (AIR).](mtp-autoir-actions.md)
- **PHISH ZAP** - [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.
- **ZAP antimalware-** Zero-hour Auto Purge (ZAP) ha preso azione su un messaggio di posta elettronica trovato contenente malware dopo il recapito.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
