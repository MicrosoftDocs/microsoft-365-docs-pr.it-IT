---
title: Tabella EmailEvents nello schema per ricerca avanzata
description: Informazioni sugli eventi associati ai messaggi di posta elettronica di Microsoft 365 nella tabella EmailEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto malware, verdetto di phishing, numero di allegati, numero di collegamenti, conteggio url
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
ms.openlocfilehash: 48a0fe53cb92214d616887741c0c260edf1653c2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928987"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sugli eventi che coinvolgono l'elaborazione dei messaggi di posta elettronica `EmailEvents` in Microsoft Defender per Office 365. [](advanced-hunting-overview.md) Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `EmailId` | stringa | Indirizzo di posta elettronica e identificatore del destinatario univoci |
| `NetworkMessageId` | stringa | Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365 |
| `InternetMessageId` | stringa | Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio |
| `SenderMailFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione MITTENTE, noto anche come mittente della busta o indirizzo di ritorno |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari del messaggio sui propri client di posta elettronica |
| `SenderMailFromDomain` | stringa | Dominio del mittente nell'intestazione MITTENTE, noto anche come mittente della busta o indirizzo di ritorno |
| `SenderFromDomain` | stringa | Dominio del mittente nell'intestazione DA, visibile ai destinatari sul proprio client di posta elettronica |
| `SenderIPv4` | stringa | Indirizzo IPV4 dell'ultimo server di posta rilevato che ha inoltrato il messaggio |
| `SenderIPv6` | stringa | Indirizzo IPV6 dell'ultimo server di posta rilevato che ha inoltrato il messaggio |
| `RecipientEmailAddress` | stringa | Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione |
| `Subject` | stringa | Oggetto del messaggio di posta elettronica |
| `EmailClusterId` | stringa | Identificatore del gruppo di messaggi di posta elettronica simili raggruppati in base a un'analisi euristica del contenuto |
| `EmailDirection` | stringa | Direzione del messaggio di posta elettronica relativa alla rete: in entrata, in uscita, interna all'organizzazione |
| `DeliveryAction` | stringa | Azioni di recapito del messaggio di posta elettronica: consegnato, inserito nella posta indesiderata, bloccato o sostituito |
| `DeliveryLocation` | stringa | Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati |
| `PhishFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene phishing: Phishing o No phishing |
| `PhishDetectionMethod` | stringa | Metodo usato per rilevare la posta elettronica come un falso: reputazione url dannoso, detonazione url collegamenti sicuri, filtro avanzato per il phish, filtro anti-spoofing generale, anti-spoofing: intra-org, anti-spoofing: dominio esterno, rappresentazione del dominio, rappresentazione utente, imitazione del marchio |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo usato per rilevare malware nella posta elettronica: motore antimalware, reputazione file, allegati sicuri |
| `EmailAction` | stringa | Azione finale intrapresa sul messaggio di posta elettronica basata su verdetto del filtro, criteri e azioni dell'utente: spostare il messaggio nella cartella posta indesiderata, aggiungere X-Header, modificare l'oggetto, reindirizzare il messaggio, eliminare il messaggio, inviare in quarantena, non eseguire nessuna azione, messaggio in Ccn |
| `EmailActionPolicy` | stringa | Criteri di azione che hanno avuto effetto: filtro posta indesiderata con alta confidenza, filtro posta indesiderata, filtro posta indesiderata per la posta inviata in blocco, filtro posta indesiderata per il phishing, imitazione dominio anti-phishing, imitazione utente anti-phishing, spoofing anti-phishing, imitazione grafico anti-phishing, anti-malware, allegati sicuri, regole del flusso di posta (ETR) |
| `EmailActionPolicyGuid` | stringa | Identificatore univoco dei criteri che hanno determinato l'azione finale per la posta |
| `AttachmentCount` | int | Numero degli allegati nel messaggio di posta elettronica |
| `UrlCount` | int | Numero di URL incorporati nel messaggio di posta elettronica |
| `EmailLanguage` | stringa | Lingua del contenuto del messaggio di posta elettronica rilevata |
| `OrgLevelAction` | stringa | Azione eseguita sul messaggio di posta elettronica in risposta a corrispondenze a un criterio definito a livello di organizzazione |
| `OrgLevelPolicy` | stringa | Criteri organizzativi che hanno attivato l'azione eseguita sul messaggio di posta elettronica |
| `UserLevelAction` | stringa | Azione eseguita sul messaggio di posta elettronica in risposta a corrispondenze a un criterio cassetta postale definito dal destinatario |
| `UserLevelPolicy` | stringa | Criterio cassetta postale dell'utente finale che ha attivato l'azione eseguita sul messaggio di posta elettronica |
| `Connectors` | stringa | Istruzioni personalizzate che definiscono il flusso di posta dell'organizzazione e come è stato instradato il messaggio di posta elettronica |
| `SenderDisplayName` | stringa | Nome del mittente visualizzato nella rubrica, in genere una combinazione di nome o nome, secondo nome e cognome o cognome |
| `SenderObjectId` | stringa |Identificatore univoco dell'account del mittente in Azure AD |
| `ThreatTypes` | stringa | Verdetto dello stack di filtro della posta elettronica che indica se il messaggio di posta elettronica contiene malware, phishing o altre minacce |
| `ThreatNames` | stringa |Nome di rilevamento per malware o altre minacce rilevate |
| `DetectionMethods` | stringa | Metodi utilizzati per rilevare malware, phishing o altre minacce rilevate nel messaggio di posta elettronica |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
