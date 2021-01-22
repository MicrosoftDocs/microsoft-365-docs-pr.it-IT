---
title: Tabella AADSpnSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate all'entità servizio di Azure Active Directory e alla tabella degli eventi di accesso dell'identità gestita dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, prova, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928619"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events. Verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.<br><br>
> I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione Microsoft Defender for Endpoint integrata del Centro sicurezza di Azure, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft Cloud App Security, non potranno visualizzare questo schema. 



La `AADSpnSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sull'entità servizio di Azure Active Directory e sugli account di accesso delle identità gestite. Ulteriori informazioni sui diversi tipi di accesso sono disponibili nei report sulle attività di accesso [di Azure Active Directory - anteprima.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nome colonna     | Tipo di dati | Descrizione   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Data e ora in cui è stato generato il record                                                                                                     |
| `Application`          | stringa        | Applicazione che ha eseguito l'azione registrata                                                                                                   |
| `ApplicationId`        | stringa        | Identificatore univoco dell'applicazione                                                                                                           |
| `IsManagedIdentity`    | boolean       | Indica se l'accesso è stato avviato da un'identità gestita                                                                               |
| `ErrorCode`            | int        | Contiene il codice di errore se si verifica un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare il sito <https://aka.ms/AADsigninsErrorCodes> Web . |
| `CorrelationId`        | stringa        | Identificatore univoco dell'evento di accesso                                                                                                          |
| `ServicePrincipalName` | stringa        | Nome dell'entità servizio che ha avviato l'accesso                                                                                        |
| `ServicePrincipalId`   | stringa        | Identificatore univoco dell'entità servizio che ha avviato l'accesso                                                                           |
| `ResourceDisplayName`  | stringa        | Nome visualizzato della risorsa a cui si accede                                                                                                           |
| `ResourceId`           | stringa        | Identificatore univoco della risorsa a cui si accede                                                                                                      |
| `ResourceTenantId`     | stringa        | Identificatore univoco del tenant della risorsa a cui si accede                                                                                        |
| `IPAddress`            | stringa        | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate                                                              |
| `CountryCode`          | stringa        | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocato                                                                |
| `State`                | stringa        | Stato in cui si è verificato l'accesso, se disponibile                                                                                                  |
| `City`                 | stringa        | Città in cui si trova l'utente dell'account                                                                                                          |
| `Latitude`             | stringa        | Coordinate da nord a sud della posizione di accesso                                                                                          |
| `Longitude`            | stringa        | Coordinate da est a ovest della posizione di accesso                                                                                            |
| `RequestId`            | stringa        | Identificatore univoco della richiesta                                                                                                                |
|`ReportId` | stringa | Identificatore univoco dell'evento | 

 

## <a name="related-articles"></a>Articoli correlati

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Panoramica della ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Capire il linguaggio delle query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Comprensione dello schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

