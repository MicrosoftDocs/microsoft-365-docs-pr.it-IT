---
title: Tabella AADSpnSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate all'entità Azure Active Directory e agli eventi di accesso dell'identità gestita della tabella degli eventi di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, prova, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347908"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La tabella è attualmente in versione beta e viene offerta a breve termine per consentire la ricerca tramite l'entità servizio Azure Active Directory (AAD) e gli eventi di accesso delle identità `AADSpnSignInEventsBeta` gestite. Alla fine verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.



La `AADSpnSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sull Azure Active Directory'entità servizio e sugli account di accesso delle identità gestite. Ulteriori informazioni sui diversi tipi di accesso in Azure Active Directory attività di [accesso - anteprima.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nome colonna | Tipo di dati | Descrizione |
|-----|-----|-----|
| `Timestamp` | datetime | Data e ora in cui è stato generato il record |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `ApplicationId` | stringa | Identificatore univoco dell'applicazione |
| `IsManagedIdentity`    | boolean       | Indica se l'accesso è stato avviato da un'identità gestita |
| `ErrorCode`    | int | Contiene il codice di errore se si verifica un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | stringa        | Identificatore univoco dell'evento di accesso |
| `ServicePrincipalName` | stringa        | Nome dell'entità servizio che ha avviato l'accesso  |
| `ServicePrincipalId`   | stringa        | Identificatore univoco dell'entità servizio che ha avviato l'accesso  |
| `ResourceDisplayName`  | stringa        | Nome visualizzato della risorsa a cui si accede  |
| `ResourceId`           | stringa        | Identificatore univoco della risorsa a cui si accede  |
| `ResourceTenantId`     | stringa        | Identificatore univoco del tenant della risorsa a cui si accede |
| `IPAddress`            | stringa        | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate  |
| `Country`          | stringa        | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale |
| `State`                | stringa        | Stato in cui si è verificato l'accesso, se disponibile |
| `City`                 | stringa        | Città in cui si trova l'utente dell'account  |
| `Latitude`             | stringa        | Coordinate da nord a sud della posizione di accesso |
| `Longitude`            | stringa        | Coordinate da est a ovest della posizione di accesso |
| `RequestId`            | stringa        | Identificatore univoco della richiesta |
|`ReportId` | stringa | Identificatore univoco dell'evento |

 

## <a name="related-articles"></a>Articoli correlati

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Panoramica della rilevazione avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Capire il linguaggio delle query](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Comprensione dello schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
