---
title: Tabella IdentityInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sull'account utente nella tabella IdentityInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935822"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `IdentityInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!NOTE]
>Questa tabella è stata rinominata da `AccountInfo` . Durante le ridenominazioni, tutte le query salvate nel portale vengono aggiornate automaticamente. Controllare le query salvate altrove.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure AD |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `OnPremSid` | stringa | Identificatore di sicurezza (SID) locale dell'account |
| `CloudSid` | stringa | Identificatore di sicurezza cloud dell'account |
| `GivenName` | stringa | Nome o nome specificato dell'utente dell'account |
| `Surname` | stringa | Cognome, cognome o cognome dell'utente dell'account |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome. |
| `Department` | stringa | Nome del reparto a cui appartiene l'utente dell'account |
| `JobTitle` | stringa | Posizione dell'utente dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `EmailAddress` | stringa | Indirizzo SMTP dell'account |
| `SipProxyAddress` | stringa | Indirizzo SIP (Voice over IP) dell'account |
| `City` | stringa | Città in cui si trova l'utente dell'account |
| `Country` | stringa | Paese/area geografica in cui si trova l'utente dell'account |
| `IsAccountEnabled` | boolean | Indica se l'account è abilitato o meno |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
