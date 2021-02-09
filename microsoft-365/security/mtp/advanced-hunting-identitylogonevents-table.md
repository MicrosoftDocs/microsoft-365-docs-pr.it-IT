---
title: Tabella IdentityLogonEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di autenticazione registrati da Active Directory nella tabella IdentityLogonEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identità
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
ms.openlocfilehash: 87ac6194374e8e042cf9d00271b17dd8bb785d64
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145356"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sulle attività di autenticazione effettuate tramite Active Directory locale acquisite da Microsoft Defender per l'identità e le attività di autenticazione relative ai servizi online Microsoft acquisiti da `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>Questa tabella illustra le attività di accesso di Azure Active Directory (AD) monitorate da Cloud App Security, in particolare le attività di accesso e autenticazione interattive con ActiveSync e altri protocolli legacy. Gli accessi non interattivi non disponibili in questa tabella possono essere visualizzati nel log di controllo di Azure AD. [Altre informazioni sulla connessione di Cloud App Security a Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere la guida di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) allo schema nel portale |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo:** l'utente interagisce fisicamente con il computer usando la tastiera e lo schermo locali<br><br> - **Accessi remoti interattivi (RDP):** l'utente interagisce con il computer in remoto tramite Desktop remoto, Servizi terminal, Assistenza remota o altri client RDP<br><br> - **Rete** : sessione avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise<br><br> - **Batch** - Sessione avviata da attività pianificate<br><br> - **Servizio** - Sessione avviata dai servizi all'avvio |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `Protocol` | stringa | Protocollo di rete utilizzato |
| `FailureReason` | stringa | Informazioni che spiegano perché l'azione registrata non è riuscita |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere, una combinazione di un nome o di un nome specificato, un'iniziazione intermedia e un cognome o un cognome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `DeviceType` | stringa | Tipo di dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `Port` | stringa | Porta TCP utilizzata durante la comunicazione |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationPort` | stringa | Porta di destinazione delle comunicazioni di rete correlate |
| `TargetDeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata |
| `TargetAccountDisplayName` | stringa | Nome visualizzato dell'account a cui è stata applicata l'azione registrata |
| `Location` | stringa | Città, paese o altra posizione geografica associata all'evento |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint |
| `ReportId` | long | Identificatore univoco dell'evento |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
