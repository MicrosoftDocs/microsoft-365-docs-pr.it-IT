---
title: Tabella IdentityLogonEvents nello schema di caccia avanzato
description: Informazioni sugli eventi di autenticazione registrati da Active Directory nella tabella IdentityLogonEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identità
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
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899376"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Si applica a:**
- Microsoft Threat Protection

La `IdentityLogonEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività di autenticazione registrate da Azure Active Directory e altre app e servizi cloud di Microsoft. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo** -utente interagisce fisicamente con il computer utilizzando la tastiera e lo schermo locali<br><br> - **Accessi Remote interattivi (RDP)** -l'utente interagisce con il computer in remoto tramite Desktop remoto, Servizi terminal, assistenza remota o altri client RDP<br><br> - La sessione di **rete** è stata avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise.<br><br> - Sessione **batch** iniziata dalle attività pianificate<br><br> - Sessione di **servizio** avviata dai servizi all'avvio |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `DeviceType` | stringa | Tipo di dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `Location` | stringa | Città, paese o altra località geografica associata all'evento |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
