---
title: Tabella AADSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate alla Azure Active Directory degli eventi di accesso dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.openlocfilehash: edc9a1e40275631752ca1252a16071f4b07f07f9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286334"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> La tabella è attualmente in versione beta e viene offerta a breve termine per consentire la ricerca tramite eventi di accesso `AADSignInEventsBeta` Azure Active Directory (AAD). Alla fine verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.

La tabella nello schema di ricerca avanzata contiene informazioni Azure Active Directory accesso interattivo `AADSignInEventsBeta` e non interattivo. Altre informazioni sugli Azure Active Directory di attività di accesso [- anteprima.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella. Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

<br>

****

|Nome colonna|Tipo di dati|Descrizione|
|---|---|---|
|`Timestamp`|datetime|Data e ora in cui è stato generato il record|
|`Application`|stringa|Applicazione che ha eseguito l'azione registrata|
|`ApplicationId`|stringa|Identificatore univoco dell'applicazione|
|`LogonType`|stringa|Tipo di sessione di accesso, in modo specifico interattivo, remoto interattivo (RDP), rete, batch e servizio|
|`ErrorCode`|int|Contiene il codice di errore se si verifica un errore di accesso. Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> .|
|`CorrelationId`|stringa|Identificatore univoco dell'evento di accesso|
|`SessionId`|stringa|Numero univoco assegnato a un utente dal server di un sito Web per la durata della visita o della sessione|
|`AccountDisplayName`|stringa|Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un secondo iniziale e un cognome o un cognome.|
|`AccountObjectId`|stringa|Identificatore univoco dell'account in Azure AD|
|`AccountUpn`|stringa|Nome dell'entità utente (UPN) dell'account|
|`IsExternalUser`|int|Indica se l'utente che ha eseguito l'accesso è esterno. Valori possibili: -1 (non impostato), 0 (non esterno), 1 (esterno).|
|`IsGuestUser`|boolean|Indica se l'utente che ha eseguito l'accesso è un guest nel tenant|
|`AlternateSignInName`|stringa|Nome dell'entità utente (UPN) locale dell'utente che accede ad Azure AD|
|`LastPasswordChangeTimestamp`|datetime|Data e ora dell'ultima modifica della password da parte dell'utente che ha eseguito l'accesso|
|`ResourceDisplayName`|stringa|Nome visualizzato della risorsa a cui si accede|
|`ResourceId`|stringa|Identificatore univoco della risorsa a cui si accede|
|`ResourceTenantId`|stringa|Identificatore univoco del tenant della risorsa a cui si accede|
|`DeviceName`|stringa|Nome di dominio completo (FQDN) del computer|
|`AadDeviceId`|stringa|Identificatore univoco per il dispositivo in Azure AD|
|`OSPlatform`|stringa|Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.|
|`DeviceTrustType`|stringa|Indica il tipo di attendibilità del dispositivo che ha eseguito l'accesso. Solo per scenari di dispositivi gestiti. I valori possibili sono Workplace, AzureAd e ServerAd.|
|`IsManaged`|int|Indica se il dispositivo che ha avviato l'accesso è un dispositivo gestito (1) o meno un dispositivo gestito (0)|
|`IsCompliant`|int|Indica se il dispositivo che ha avviato l'accesso è conforme (1) o non conforme (0)|
|`AuthenticationProcessingDetails`|stringa|Dettagli sul processore di autenticazione|
|`AuthenticationRequirement`|stringa|Tipo di autenticazione necessario per l'accesso. Valori possibili: multiFactorAuthentication (era necessaria la MFA) e singleFactorAuthentication (non è stata richiesta alcuna autenticazione a più fattori).|
|`TokenIssuerType`|int|Indica se l'autorità emittente di token Azure Active Directory (0) o Active Directory Federation Services (1)|
|`RiskLevelAggregated`|int|Livello di rischio aggregato durante l'accesso. Valori possibili: 0 (livello di rischio aggregato non impostato), 1 (nessuno), 10 (basso), 50 (medio) o 100 (alto).|
|`RiskDetails`|int|Dettagli sullo stato rischioso dell'utente che ha eseguito l'accesso|
|`RiskState`|int|Indica lo stato utente rischioso. Valori possibili: 0 (nessuno), 1 (sicurezza confermata), 2 (correzione), 3 (ignorato), 4 (a rischio) o 5 (compromesso confermato).|
|`UserAgent`|stringa|Informazioni agente utente dal Web browser o da un'altra applicazione client|
|`ClientAppUsed`|stringa|Indica l'app client usata|
|`Browser`|stringa|Dettagli sulla versione del browser utilizzata per accedere|
|`ConditionalAccessPolicies`|stringa|Dettagli dei criteri di accesso condizionale applicati all'evento di accesso|
|`ConditionalAccessStatus`|int|Stato dei criteri di accesso condizionale applicati all'accesso. I valori possibili sono 0 (criteri applicati), 1 (tentativo di applicazione dei criteri non riuscito) o 2 (criteri non applicati).|
|`IPAddress`|stringa|Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate|
|`Country`|stringa|Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale|
|`State`|stringa|Stato in cui si è verificato l'accesso, se disponibile|
|`City`|stringa|Città in cui si trova l'utente dell'account|
|`Latitude`|stringa|Coordinate da nord a sud della posizione di accesso|
|`Longitude`|stringa|Coordinate da est a ovest della posizione di accesso|
|`NetworkLocationDetails`|stringa|Dettagli percorso di rete del processore di autenticazione dell'evento di accesso|
|`RequestId`|stringa|Identificatore univoco della richiesta|
|`ReportId`|stringa|Identificatore univoco dell'evento|
|

## <a name="related-articles"></a>Articoli correlati

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [Panoramica della rilevazione avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Capire il linguaggio delle query](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Comprensione dello schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
