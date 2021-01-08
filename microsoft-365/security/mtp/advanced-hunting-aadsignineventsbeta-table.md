---
title: Tabella AADSignInEventsBeta nello schema di caccia avanzato
description: Informazioni sui dati associati alla tabella eventi di accesso di Azure Active Directory dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.openlocfilehash: 1830eeec674c4948bd6492780ef8a0a8039111b8
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784288"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La `AADSignInEventsBeta` tabella è attualmente in fase di beta e viene offerta a breve termine per consentire la caccia tramite gli eventi di accesso di Azure Active Directory (AAD). Alla fine, verranno spostate tutte le informazioni dello schema di accesso alla `IdentityLogonEvents` tabella.<br><br>
> I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione integrata Microsoft Defender for endpoint di Azure Security Center, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft cloud app Security, non saranno in grado di visualizzare questo schema. 

 

La `AADSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sugli accessi interattivi e non interattivi di Azure Active Directory. Per ulteriori informazioni, vedere sign-ins in [Azure Active Directory Activity Reports-Preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.
Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Nome colonna                 | Tipo di dati | Descrizione          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Data e ora in cui è stato generato il record                                                                                                                                         |
| `Application`                     | stringa        | Applicazione in cui è stata eseguita l'azione registrata                                                                                                                                       |
| `ApplicationId`                   | stringa        | Identificatore univoco per l'applicazione                                                                                                                                               |
| `LogonType`                       | stringa        | Tipo di sessione di accesso, in particolare Interactive, Remote Interactive (RDP), rete, batch e servizio                                                                              |
| `ErrorCode`                       | int        | Contiene il codice di errore nel caso in cui si verifichi un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | stringa        | Identificatore univoco dell'evento di accesso                                                                                                                                              |
| `SessionId`                       | stringa        | Numero univoco assegnato a un utente dal server di un sito Web per tutta la durata della visita o della sessione                                                                                     |
| `AccountDisplayName`              | stringa        | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un iniziale medio e di un ultimo nome.                             |
| `AccountObjectId`                 | stringa        | Identificatore univoco per l'account in Azure AD                                                                                                                                       |
| `AccountUpn`                      | stringa        | Nome dell'entità utente (UPN) dell'account                                                                                                                                            |
| `IsExternalUser`                  | int        | Indica se l'utente che ha eseguito l'accesso è esterno. Valori possibili:-1 (non impostato), 0 (non esterno), 1 (esterno).                                                                   |
| `IsGuestUser`                     | boolean       | Indica se l'utente che ha effettuato l'accesso è un ospite del tenant.                                                                                                                  |
| `AlternateSignInName`             | stringa        | Nome dell'entità utente locale (UPN) dell'utente che effettua l'accesso a Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Data e ora in cui l'utente che ha firmato l'ultima volta ha modificato la propria password                                                                                                              |
| `ResourceDisplayName`             | stringa        | Nome visualizzato della risorsa a cui si accede                                                                                                                                               |
| `ResourceId`                      | stringa        | Identificatore univoco della risorsa a cui si accede                                                                                                                                          |
| `ResourceTenantId`                | stringa        | Identificatore univoco del tenant della risorsa a cui si accede                                                                                                                            |
| `DeviceName`                      | stringa        | Nome di dominio completo (FQDN) del computer                                                                                                                                   |
| `AadDeviceId`                     | stringa   |      Identificatore univoco per il dispositivo in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | stringa        | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.  |
| `DeviceTrustType`                 | stringa        | Indica il tipo di attendibilità del dispositivo che ha eseguito l'accesso. Solo per gli scenari di dispositivi gestiti. I valori possibili sono luogo di lavoro, AzureAd e ServerAd.                                     |
| `IsManaged`                       | int       | Indica se il dispositivo che ha avviato l'accesso è un dispositivo gestito (1) o meno un dispositivo gestito (0).                                                                         |
| `IsCompliant`                     | int       | Indica se il dispositivo che ha avviato l'accesso è conforme (1) o non conforme (0)                                                                                       |
| `AuthenticationProcessingDetails` | stringa        | Informazioni dettagliate sul processore di autenticazione                                                                                                                                          |
| `AuthenticationRequirement`       | stringa        | Tipo di autenticazione necessario per l'accesso. Valori possibili: multiFactorAuthentication (è stato richiesto il Master) e singleFactorAuthentication (non è stato richiesto alcun AMF).                |
| `TokenIssuerType`                 | int        | Indica se l'autorità emittente di token è Azure Active Directory (0) o Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Livello di rischio aggregato durante l'accesso. Valori possibili: 0 (livello di rischio aggregato non impostato), 1 (nessuno), 10 (basso), 50 (medio) o 100 (alto).                               |
| `RiskDetails`                      | int        | Informazioni dettagliate sullo stato rischioso dell'utente che ha eseguito l'accesso                                                                                                                            |
| `RiskState`                       | int        | Indica lo stato dell'utente a rischio. Valori possibili: 0 (nessuno), 1 (sicura confermata), 2 (corretti), 3 (ignorati), 4 (a rischio) o 5 (confermato compromesso).                                |
| `UserAgent`                       | stringa        | Informazioni sull'agente utente dal Web browser o da un'altra applicazione client                                                                                                             |
| `ClientAppUsed`                   | stringa        | Indica l'app client utilizzata                                                                                                                                                       |
| `Browser`                         | stringa        | Informazioni dettagliate sulla versione del browser utilizzata per eseguire l'accesso                                                                                                                            |
| `ConditionalAccessPolicies`       | stringa        | Dettagli dei criteri di accesso condizionale applicati all'evento Sign-in                                                                                                             |
| `ConditionalAccessStatus`         | int        | Stato dei criteri di accesso condizionale applicati alla connessione. I valori possibili sono 0 (criteri applicati), 1 (tentativo di applicare i criteri non riusciti) oppure 2 (criteri non applicati).      |
| `IPAddress`                       | stringa        | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate                                                                                                  |
| `CountryCode`                     | stringa        | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è Geolocated                                                                                                    |
| `State`                           | stringa        | Stato in cui si è verificato l'accesso, se disponibile                                                                                                                                      |
| `City`                            | stringa        | Città in cui si trova l'utente dell'account                                                                                                                                              |
| `Latitude`                        | stringa        | Le coordinate nord-sud del percorso di accesso                                                                                                                              |
| `Longitude`                       | stringa        | Le coordinate da est a ovest del percorso di accesso                                                                                                                                |
| `NetworkLocationDetails`          | stringa        | Dettagli del percorso di rete del processore di autenticazione dell'evento di accesso                                                                                                       |
| `RequestId`                       | stringa        |  Identificatore univoco della richiesta                                                                                                                                                   |
|`ReportId` | stringa | Identificatore univoco per l'evento |

 

 

## <a name="related-articles"></a>Articoli correlati

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Panoramica della ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Capire il linguaggio delle query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Comprensione dello schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
