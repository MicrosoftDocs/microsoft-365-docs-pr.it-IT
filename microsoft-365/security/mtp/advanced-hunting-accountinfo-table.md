---
title: Tabella AccountInfo nello schema di caccia avanzato
description: Informazioni sugli account utente nella tabella AccountInfo dello schema di caccia avanzato
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929529"
---
# <a name="accountinfo"></a>AccountInfo

**Si applica a:**
- Microsoft Threat Protection

La `AccountInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `OnPremSid` | stringa | ID di sicurezza locale (SID) dell'account |
| `CloudSid` | stringa | Identificatore di sicurezza cloud dell'account |
| `GivenName` | stringa | Nome o nome specificato dell'utente dell'account |
| `Surname` | stringa | Cognome, nome della famiglia o cognome dell'utente dell'account |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `Department` | stringa | Nome del reparto a cui appartiene l'utente dell'account |
| `JobTitle` | stringa | Titolo del processo dell'utente dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `EmailAddress` | stringa | Indirizzo SMTP dell'account |
| `SipProxyAddress` | stringa | Indirizzo SIP (Voice of over IP (VOIP) Session Initiation Protocol of the account |
| `City` | stringa | Città in cui si trova l'utente dell'account |
| `Country` | stringa | Paese/area geografica in cui si trova l'account utente |
| `IsAccountEnabled` | boolean | Indica se l'account è abilitato o meno. |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
