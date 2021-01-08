---
title: Tabella EmailEvents nello schema per ricerca avanzata
description: Informazioni sugli eventi associati ai messaggi di posta elettronica di Microsoft 365 nella tabella EmailEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di malware, verdetto di phishing, conteggio degli allegati
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
ms.openlocfilehash: 6dbd7473074212c6bc257e683288040056426048
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780273"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `EmailEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli eventi che coinvolgono l'elaborazione dei messaggi di posta elettronica su Microsoft Defender per Office 365. Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `EmailId` | stringa | Indirizzo di posta elettronica e identificatore del destinatario univoci |
| `NetworkMessageId` | stringa | Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365 |
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
| `PhishDetectionMethod` | stringa | Metodo utilizzato per rilevare il messaggio di posta elettronica come phishing: reputazione URL dannosi, detonazione URL collegamenti sicuri, filtro phishing avanzato, filtro phishing generale, anti-spoofing: intra-org, anti-spoofing: dominio esterno, rappresentazione del dominio, rappresentazione utente, rappresentazione del marchio |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo utilizzato per rilevare la presenza di malware nel messaggio di posta elettronica: motore antimalware, reputazione dei file, allegati sicuri |
| `EmailAction` | stringa | Azione finale intrapresa sul messaggio di posta elettronica basata su verdetto del filtro, criteri e azioni dell'utente: spostare il messaggio nella cartella posta indesiderata, aggiungere X-Header, modificare l'oggetto, reindirizzare il messaggio, eliminare il messaggio, inviare in quarantena, non eseguire nessuna azione, messaggio in Ccn |
| `EmailActionPolicy` | stringa | Criteri di azione che hanno avuto effetto: filtro posta indesiderata con alta confidenza, filtro posta indesiderata, filtro posta indesiderata per la posta inviata in blocco, filtro posta indesiderata per il phishing, imitazione dominio anti-phishing, imitazione utente anti-phishing, spoofing anti-phishing, imitazione grafico anti-phishing, anti-malware, allegati sicuri, regole del flusso di posta (ETR) |
| `EmailActionPolicyGuid` | stringa | Identificatore univoco dei criteri che hanno determinato l'azione finale per la posta |
| `AttachmentCount` | int | Numero degli allegati nel messaggio di posta elettronica |
| `UrlCount` | int | Numero di URL incorporati nel messaggio di posta elettronica |
| `EmailLanguage` | stringa | Lingua del contenuto del messaggio di posta elettronica rilevata |
| `OrgLevelAction` | stringa | Azione intrapresa sul messaggio di posta elettronica in risposta alle corrispondenze a un criterio definito a livello di organizzazione |
| `OrgLevelPolicy` | stringa | Politica organizzativa che ha attivato l'azione intrapresa sul messaggio di posta elettronica |
| `UserLevelAction` | stringa | Azione intrapresa sul messaggio di posta elettronica in risposta alle corrispondenze a un criterio cassetta postale definito dal destinatario |
| `UserLevelPolicy` | stringa | Criterio cassetta postale dell'utente finale che ha attivato l'azione intrapresa sul messaggio di posta elettronica |
| `Connectors` | stringa | Istruzioni personalizzate per la definizione del flusso di posta organizzativa e del modo in cui il messaggio è stato instradato |
| `SenderDisplayName` | stringa | Nome del mittente visualizzato nella rubrica, in genere una combinazione di un nome o di un cognome, di un iniziale medio e di un ultimo cognome o nome. |
| `SenderObjectId` | stringa |Identificatore univoco per l'account del mittente in Azure AD |
| `ThreatTypes` | stringa | Verdetto dallo stack del filtro della posta elettronica sul fatto che il messaggio di posta elettronica contenga malware, phishing o altre minacce |
| `ThreatNames` | stringa |Nome del rilevamento di malware o altre minacce trovate |
| `DetectionMethods` | stringa | Metodi utilizzati per rilevare malware, tentativi di phishing o altre minacce rilevate nel messaggio di posta elettronica |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
