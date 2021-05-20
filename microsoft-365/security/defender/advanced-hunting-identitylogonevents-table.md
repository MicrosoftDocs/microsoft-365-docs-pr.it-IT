---
title: IdentityLogonEvents nello schema di ricerca avanzato
description: Informazioni sugli eventi di autenticazione registrati da Active Directory nella tabella IdentityLogonEvents dello schema di ricerca avanzato
keywords: caccia avanzata, ricerca di minacce, caccia alle minacce informatiche, Microsoft 365 Defender, microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender per identità, identità
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572754"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella dello schema di ricerca avanzato contiene informazioni sulle attività di autenticazione effettuate tramite Active Directory locale acquisite da Microsoft Defender per `IdentityLogonEvents` le attività di identità e autenticazione correlate ai servizi online Microsoft acquisiti [](advanced-hunting-overview.md) da Microsoft Cloud App Security. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi `ActionType` (valori) supportati da una tabella, utilizzare il riferimento allo schema incorporato disponibile nel Centro sicurezza.

>[!NOTE]
>Questa tabella illustra Azure Active Directory di accesso (Azure AD) monitorate da Cloud App Security, in particolare le attività interattive di accesso e autenticazione con ActiveSync e altri protocolli legacy. Gli accessi non interattivi non disponibili in questa tabella possono essere visualizzati nel registro di controllo di Azure AD. [Ulteriori informazioni sulla connessione Cloud App Security a Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere il riferimento allo schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) nel portale |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo** : l'utente interagisce fisicamente con la macchina utilizzando la tastiera e lo schermo locali<br><br> - **Accessi RDP (Remote Interactive)** - L'utente interagisce con il computer in remoto utilizzando Desktop remoto, Servizi terminal, Assistenza remota o altri client RDP<br><br> - **Rete** - Sessione avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise<br><br> - **Batch** - Sessione avviata da attività pianificate<br><br> - **Servizio** - Sessione avviata dai servizi all'avvio |
| `Protocol` | stringa | Protocollo di rete utilizzato |
| `FailureReason` | stringa | Informazioni che spiegano perché l'azione registrata non è riuscita |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome entità utente (UPN) dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. Tipicamente una combinazione di un dato o nome, un'iniziazione media e un cognome o cognome. |
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
| `ReportId` | long | Identificatore univoco per l'evento |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)