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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 176f131ad020d001b72b97332d54be71feef5548
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847417"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `IdentityLogonEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività di autenticazione effettuate tramite Active Directory locale acquisito da Microsoft Defender per le attività di autenticazione e identità relative ai servizi Microsoft Online acquisiti da Microsoft cloud app Security. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.

>[!NOTE]
>In questa tabella vengono illustrate le attività di accesso di Azure Active Directory (AD) registrate dalla protezione delle app Cloud, in particolare gli accessi interattivi e le attività di autenticazione che utilizzano ActiveSync e altri protocolli legacy. Gli accessi non interattivi non disponibili in questa tabella possono essere visualizzati nel log di controllo di Azure AD. [Per ulteriori informazioni, vedere Connecting cloud app Security to Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni dettagliate, vedere la Guida [di riferimento allo schema in-Portal.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo** -utente interagisce fisicamente con il computer utilizzando la tastiera e lo schermo locali<br><br> - **Accessi Remote interattivi (RDP)** -l'utente interagisce con il computer in remoto tramite Desktop remoto, Servizi terminal, assistenza remota o altri client RDP<br><br> - La sessione di **rete** è stata avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise.<br><br> - Sessione **batch** iniziata dalle attività pianificate<br><br> - Sessione di **servizio** avviata dai servizi all'avvio |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `Protocol` | stringa | Protocollo di rete utilizzato |
| `FailureReason` | stringa | Informazioni che spiegano perché l'azione registrata non è riuscita |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `DeviceType` | stringa | Tipo di dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `TargetDeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata |
| `TargetAccountDisplayName` | stringa | Nome visualizzato dell'account a cui è stata applicata l'azione registrata |
| `Location` | stringa | Città, paese o altra località geografica associata all'evento |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint |
| `ReportId` | long | Identificatore univoco per l'evento |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
