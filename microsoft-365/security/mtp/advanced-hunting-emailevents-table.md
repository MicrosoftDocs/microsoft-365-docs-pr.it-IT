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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: eefd6848e5ae0ddb077db576d55aaf9555e33729
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898994"
---
# <a name="emailevents"></a>EmailEvents

**Si applica a:**
- Microsoft Threat Protection



La tabella `EmailEvents` nello schema per [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni riguardanti gli eventi che interessano l'elaborazione dei messaggi di posta elettronica in Office 365 ATP. Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.

Per informazioni su altre tabelle nello schema per ricerca avanzata, [vedere il riferimento sulla ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora in cui è stato registrato l'evento |
| `EmailId` | stringa | Indirizzo di posta elettronica e identificatore del destinatario univoci |
| `NetworkMessageId` | stringa | Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365 |
| `InternetMessageId` | stringa | Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio |
| `SenderMailFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione MITTENTE, noto anche come mittente della busta o indirizzo di ritorno |
| `SenderFromAddress` | stringa | Indirizzo di posta elettronica del mittente nell'intestazione DA, visibile ai destinatari nel proprio client di posta elettronica |
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
| `PhishDetectionMethod` | stringa | Metodo usato per rilevare se un messaggio di posta elettronica contiene phishing: reputazione di URL pericolosi, detonazione di URL di Collegamenti sicuri ATP, Filtro avanzato di phishing, Filtro generale di phishing, Anti-spoofing: interno all'organizzazione, Anti-spoofing: dominio esterno, Imitazione del dominio, Imitazione dell'utente, Imitazione del marchio |
| `MalwareFilterVerdict` | stringa | Verdetto del gruppo di filtri della posta elettronica che indica se il messaggio contiene Malware: Malware, No malware |
| `MalwareDetectionMethod` | stringa | Metodo usato per rilevare il malware nel messaggio di posta elettronica: Antimalware Engine, Reputazione file, Allegati sicuri ATP |
| `FinalEmailAction` | stringa | Azione finale intrapresa sul messaggio di posta elettronica basata su verdetto del filtro, criteri e azioni dell'utente: spostare il messaggio nella cartella posta indesiderata, aggiungere X-Header, modificare l'oggetto, reindirizzare il messaggio, eliminare il messaggio, inviare in quarantena, non eseguire nessuna azione, messaggio in Ccn |
| `FinalEmailActionPolicy` | stringa | Criteri di azione che hanno avuto effetto: filtro posta indesiderata con alta confidenza, filtro posta indesiderata, filtro posta indesiderata per la posta inviata in blocco, filtro posta indesiderata per il phishing, imitazione dominio anti-phishing, imitazione utente anti-phishing, spoofing anti-phishing, imitazione grafico anti-phishing, anti-malware, allegati sicuri, regole del flusso di posta (ETR) |
| `FinalEmailActionPolicyGuid` | stringa | Identificatore univoco dei criteri che hanno determinato l'azione finale per la posta |
| `AttachmentCount` | int | Numero degli allegati nel messaggio di posta elettronica |
| `UrlCount` | int | Numero di URL incorporati nel messaggio di posta elettronica |
| `EmailLanguage` | stringa | Lingua del contenuto del messaggio di posta elettronica rilevata |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Conoscere il linguaggio di query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e messaggi di posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
