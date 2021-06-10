---
title: Tabella EmailEvents nello schema per ricerca avanzata
description: Informazioni sugli eventi associati Microsoft 365 messaggi di posta elettronica nella tabella EmailEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto malware, verdetto di phishing, numero di allegati, numero di collegamenti, conteggio url
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
ms.openlocfilehash: 18d3d768b672364f730b042239ae9fa0042f95f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935486"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sugli eventi che coinvolgono l'elaborazione dei messaggi di posta elettronica `EmailEvents` in Microsoft Defender per Office 365. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `NetworkMessageId` | stringa | Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365 |
| `InternetMessageId` | stringa | Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio |
| `SenderMailFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione MITTENTE, noto anche come mittente della busta o indirizzo di ritorno |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari del messaggio sui propri client di posta elettronica |
| `SenderDisplayName` | stringa | Nome del mittente visualizzato nella rubrica, in genere una combinazione di un nome o di un nome, un secondo nome e un cognome o un cognome |
| `SenderObjectId` | stringa |Identificatore univoco dell'account del mittente in Azure AD |
| `SenderMailFromDomain` | stringa | Dominio del mittente nell'intestazione MITTENTE, noto anche come mittente della busta o indirizzo di ritorno |
| `SenderFromDomain` | stringa | Dominio del mittente nell'intestazione DA, visibile ai destinatari sul proprio client di posta elettronica |
| `SenderIPv4` | stringa | Indirizzo IPV4 dell'ultimo server di posta rilevato che ha inoltrato il messaggio |
| `SenderIPv6` | stringa | Indirizzo IPV6 dell'ultimo server di posta rilevato che ha inoltrato il messaggio |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `RecipientObjectId` | stringa | Identificatore univoco del destinatario della posta elettronica in Azure AD |
| `Subject` | stringa | Oggetto del messaggio di posta elettronica |
| `EmailClusterId` | stringa | Identificatore del gruppo di messaggi di posta elettronica simili raggruppati in base a un'analisi euristica del contenuto |
| `EmailDirection` | stringa | Direzione del messaggio di posta elettronica relativa alla rete: in entrata, in uscita, interna all'organizzazione |
| `DeliveryAction` | stringa | Azioni di recapito del messaggio di posta elettronica: consegnato, inserito nella posta indesiderata, bloccato o sostituito |
| `DeliveryLocation` | stringa | Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati |
| `ThreatTypes` | stringa | Verdetto dallo stack di filtro della posta elettronica se il messaggio di posta elettronica contiene malware, phishing o altre minacce |
| `ThreatNames` | stringa |Nome di rilevamento per malware o altre minacce trovate |
| `DetectionMethods` | stringa | Metodi utilizzati per rilevare malware, phishing o altre minacce trovate nel messaggio di posta elettronica |
| `ConfidenceLevel` | stringa | Elenco dei livelli di sicurezza di eventuali verdetti di posta indesiderata o phishing. Per la posta indesiderata, questa colonna mostra il livello di probabilità di posta indesiderata (SCL), che indica se il messaggio di posta elettronica è stato ignorato (-1), non è stato trovato come posta indesiderata (0,1), è stato trovato come posta indesiderata con confidenza moderata (5,6) o è stato trovato come posta indesiderata con alta confidenza (9). Per il phishing, in questa colonna viene visualizzato se il livello di probabilità è "Alto" o "Basso". |
| `EmailAction` | stringa | Azione finale intrapresa sul messaggio di posta elettronica basata su verdetto del filtro, criteri e azioni dell'utente: spostare il messaggio nella cartella posta indesiderata, aggiungere X-Header, modificare l'oggetto, reindirizzare il messaggio, eliminare il messaggio, inviare in quarantena, non eseguire nessuna azione, messaggio in Ccn |
| `EmailActionPolicy` | stringa | Criteri di azione che hanno avuto effetto: filtro posta indesiderata con alta confidenza, filtro posta indesiderata, filtro posta indesiderata per la posta inviata in blocco, filtro posta indesiderata per il phishing, imitazione dominio anti-phishing, imitazione utente anti-phishing, spoofing anti-phishing, imitazione grafico anti-phishing, anti-malware, allegati sicuri, regole del flusso di posta (ETR) |
| `EmailActionPolicyGuid` | stringa | Identificatore univoco dei criteri che hanno determinato l'azione finale per la posta |
| `AttachmentCount` | int | Numero degli allegati nel messaggio di posta elettronica |
| `UrlCount` | int | Numero di URL incorporati nel messaggio di posta elettronica |
| `EmailLanguage` | stringa | Lingua del contenuto del messaggio di posta elettronica rilevata |
| `Connectors` | stringa | Istruzioni personalizzate che definiscono il flusso di posta dell'organizzazione e come è stato instradato il messaggio di posta elettronica |
| `OrgLevelAction` | stringa | Azione eseguita sul messaggio di posta elettronica in risposta a corrispondenze a un criterio definito a livello di organizzazione |
| `OrgLevelPolicy` | stringa | Criteri organizzativi che hanno attivato l'azione eseguita sul messaggio di posta elettronica |
| `UserLevelAction` | stringa | Azione eseguita sul messaggio di posta elettronica in risposta a corrispondenze a un criterio cassetta postale definito dal destinatario |
| `UserLevelPolicy` | stringa | Criterio cassetta postale dell'utente finale che ha attivato l'azione eseguita sul messaggio di posta elettronica |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp. |

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
