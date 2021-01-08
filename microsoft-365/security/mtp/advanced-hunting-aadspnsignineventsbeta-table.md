---
title: Tabella AADSpnSignInEventsBeta nello schema di caccia avanzato
description: Informazioni sui dati associati alla tabella eventi di accesso di Azure Active Directory Service Principal e Managed Identity per lo schema di ricerca avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, evidenza, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784300"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La `AADSpnSignInEventsBeta` tabella è attualmente in fase di beta e viene offerta a breve termine per consentire la caccia tramite gli eventi di accesso all'entità del servizio di Azure Active Directory (AAD) e dell'identità gestita. Alla fine, verranno spostate tutte le informazioni dello schema di accesso alla `IdentityLogonEvents` tabella.<br><br>
> I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione integrata Microsoft Defender for endpoint di Azure Security Center, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft cloud app Security, non saranno in grado di visualizzare questo schema. 



La `AADSpnSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sull'accesso all'entità servizio di Azure Active Directory e sugli accessi all'identità gestita. Per ulteriori informazioni sui diversi tipi di accesso ai report di attività di [accesso di Azure Active Directory, vedere Preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nome colonna     | Tipo di dati | Descrizione   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Data e ora in cui è stato generato il record                                                                                                     |
| `Application`          | stringa        | Applicazione in cui è stata eseguita l'azione registrata                                                                                                   |
| `ApplicationId`        | stringa        | Identificatore univoco per l'applicazione                                                                                                           |
| `IsManagedIdentity`    | boolean       | Indica se l'accesso è stato avviato da un'identità gestita                                                                               |
| `ErrorCode`            | int        | Contiene il codice di errore nel caso in cui si verifichi un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | stringa        | Identificatore univoco dell'evento di accesso                                                                                                          |
| `ServicePrincipalName` | stringa        | Nome dell'entità servizio che ha avviato l'accesso                                                                                        |
| `ServicePrincipalId`   | stringa        | Identificatore univoco dell'entità servizio che ha avviato l'accesso                                                                           |
| `ResourceDisplayName`  | stringa        | Nome visualizzato della risorsa a cui si accede                                                                                                           |
| `ResourceId`           | stringa        | Identificatore univoco della risorsa a cui si accede                                                                                                      |
| `ResourceTenantId`     | stringa        | Identificatore univoco del tenant della risorsa a cui si accede                                                                                        |
| `IPAddress`            | stringa        | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate                                                              |
| `CountryCode`          | stringa        | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è Geolocated                                                                |
| `State`                | stringa        | Stato in cui si è verificato l'accesso, se disponibile                                                                                                  |
| `City`                 | stringa        | Città in cui si trova l'utente dell'account                                                                                                          |
| `Latitude`             | stringa        | Le coordinate nord-sud del percorso di accesso                                                                                          |
| `Longitude`            | stringa        | Le coordinate da est a ovest del percorso di accesso                                                                                            |
| `RequestId`            | stringa        | Identificatore univoco della richiesta                                                                                                                |
|`ReportId` | stringa | Identificatore univoco per l'evento | 

 

## <a name="related-articles"></a>Articoli correlati

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Panoramica della ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Capire il linguaggio delle query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Comprensione dello schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

