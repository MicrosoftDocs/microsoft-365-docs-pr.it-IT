---
title: Tabella AADSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate alla tabella degli eventi di accesso di Azure Active Directory dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.openlocfilehash: 174db150920d2d95c043bb5d6e5a4593ea1ea39d
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145428"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> The `AADSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) sign-in events. Verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.<br><br>
> I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione Microsoft Defender for Endpoint integrata del Centro sicurezza di Azure, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft Cloud App Security, non potranno visualizzare questo schema. 

 

La tabella nello schema di ricerca avanzata contiene informazioni sugli accesso interattivi e non interattivi `AADSignInEventsBeta` di Azure Active Directory. Ulteriori informazioni sugli account di accesso nei report attività di accesso [di Azure Active Directory - anteprima.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.
Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Nome colonna                 | Tipo di dati | Descrizione          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Data e ora in cui è stato generato il record                                                                                                                                         |
| `Application`                     | stringa        | Applicazione che ha eseguito l'azione registrata                                                                                                                                       |
| `ApplicationId`                   | stringa        | Identificatore univoco dell'applicazione                                                                                                                                               |
| `LogonType`                       | stringa        | Tipo di sessione di accesso, in particolare interattiva, remote interactive (RDP), rete, batch e servizio                                                                              |
| `ErrorCode`                       | int        | Contiene il codice di errore se si verifica un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare il sito <https://aka.ms/AADsigninsErrorCodes> Web .                                     |
| `CorrelationId`                   | stringa        | Identificatore univoco dell'evento di accesso                                                                                                                                              |
| `SessionId`                       | stringa        | Numero univoco assegnato a un utente dal server di un sito Web per la durata della visita o della sessione                                                                                     |
| `AccountDisplayName`              | stringa        | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un secondo nome e un cognome o un cognome.                             |
| `AccountObjectId`                 | stringa        | Identificatore univoco per l'account in Azure AD                                                                                                                                       |
| `AccountUpn`                      | stringa        | Nome dell'entità utente (UPN) dell'account                                                                                                                                            |
| `IsExternalUser`                  | int        | Indica se l'utente che ha eseguito l'accesso è esterno. Valori possibili: -1 (non impostato), 0 (non esterno), 1 (esterno).                                                                   |
| `IsGuestUser`                     | boolean       | Indica se l'utente che ha eseguito l'accesso è un guest nel tenant                                                                                                                  |
| `AlternateSignInName`             | stringa        | Nome dell'entità utente (UPN) locale dell'utente che accede ad Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Data e ora dell'ultima modifica della password da parte dell'utente che ha eseguito l'accesso                                                                                                              |
| `ResourceDisplayName`             | stringa        | Nome visualizzato della risorsa a cui si accede                                                                                                                                               |
| `ResourceId`                      | stringa        | Identificatore univoco della risorsa a cui si accede                                                                                                                                          |
| `ResourceTenantId`                | stringa        | Identificatore univoco del tenant della risorsa a cui si accede                                                                                                                            |
| `DeviceName`                      | stringa        | Nome di dominio completo (FQDN) del computer                                                                                                                                   |
| `AadDeviceId`                     | stringa   |      Identificatore univoco per il dispositivo in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | stringa        | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.  |
| `DeviceTrustType`                 | stringa        | Indica il tipo di attendibilità del dispositivo che ha effettuato l'accesso. Solo per scenari di dispositivi gestiti. I valori possibili sono Workplace, AzureAd e ServerAd.                                     |
| `IsManaged`                       | int       | Indica se il dispositivo che ha avviato l'accesso è un dispositivo gestito (1) o non un dispositivo gestito (0)                                                                         |
| `IsCompliant`                     | int       | Indica se il dispositivo che ha avviato l'accesso è conforme (1) o non conforme (0)                                                                                       |
| `AuthenticationProcessingDetails` | stringa        | Dettagli sul processore di autenticazione                                                                                                                                          |
| `AuthenticationRequirement`       | stringa        | Tipo di autenticazione necessario per l'accesso. Valori possibili: multiFactorAuthentication (era necessaria l'autenticazione a più fattori) e singleFactorAuthentication (non è stata richiesta alcuna autenticazione a più fattori).                |
| `TokenIssuerType`                 | int        | Indica se l'autorità emittente di token è Azure Active Directory (0) o Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Livello di rischio aggregato durante l'accesso. Valori possibili: 0 (livello di rischio aggregato non impostato), 1 (nessuno), 10 (basso), 50 (medio) o 100 (alto).                               |
| `RiskDetails`                      | int        | Dettagli sullo stato rischioso dell'utente che ha eseguito l'accesso                                                                                                                            |
| `RiskState`                       | int        | Indica lo stato utente rischioso. Valori possibili: 0 (nessuno), 1 (sicuro confermato), 2 (correzione), 3 (ignorato), 4 (a rischio) o 5 (compromesso confermato).                                |
| `UserAgent`                       | stringa        | Informazioni sull'agente utente dal Web browser o da un'altra applicazione client                                                                                                             |
| `ClientAppUsed`                   | stringa        | Indica l'app client usata                                                                                                                                                       |
| `Browser`                         | stringa        | Dettagli sulla versione del browser usata per accedere                                                                                                                            |
| `ConditionalAccessPolicies`       | stringa        | Dettagli dei criteri di accesso condizionale applicati all'evento di accesso                                                                                                             |
| `ConditionalAccessStatus`         | int        | Stato dei criteri di accesso condizionale applicati all'accesso. I valori possibili sono 0 (criteri applicati), 1 (tentativo di applicare i criteri non riuscito) o 2 (criteri non applicati).      |
| `IPAddress`                       | stringa        | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate                                                                                                  |
| `Country`                     | stringa        | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocato                                                                                                    |
| `State`                           | stringa        | Stato in cui si è verificato l'accesso, se disponibile                                                                                                                                      |
| `City`                            | stringa        | Città in cui si trova l'utente dell'account                                                                                                                                              |
| `Latitude`                        | stringa        | Coordinate da nord a sud della posizione di accesso                                                                                                                              |
| `Longitude`                       | stringa        | Coordinate da est a ovest della posizione di accesso                                                                                                                                |
| `NetworkLocationDetails`          | stringa        | Dettagli del percorso di rete del processore di autenticazione dell'evento di accesso                                                                                                       |
| `RequestId`                       | stringa        |  Identificatore univoco della richiesta                                                                                                                                                   |
|`ReportId` | stringa | Identificatore univoco dell'evento |

 

 

## <a name="related-articles"></a>Articoli correlati

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Panoramica della ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Capire il linguaggio delle query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Comprensione dello schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
