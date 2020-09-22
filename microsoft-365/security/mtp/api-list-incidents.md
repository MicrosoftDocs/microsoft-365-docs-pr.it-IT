---
title: API degli incidenti di elenco in Microsoft Threat Protection
description: Informazioni su come elencare le API degli incidenti in Microsoft Threat Protection
keywords: elenco, incidenti, incidenti, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195391"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>API degli incidenti di elenco in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descrizione API

L'API Incident consente di ordinare gli eventi non consentiti per definire la priorità e creare una risposta Cybersecurity informata. Espone una raccolta di operazioni non consentite che sono state contrassegnate da dispositivi, account di posta elettronica e utenti della rete, all'interno dell'intervallo di tempo specificato nel criterio di conservazione dell'ambiente. Gli incidenti più recenti vengono visualizzati all'inizio dell'elenco. Ogni evento Incident contiene una matrice di avvisi correlati e le entità correlate.

<br>L'API supporta gli operatori **OData** seguenti:
<br>```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` e ```assignedTo``` Properties.
<br>```$top``` con valore massimo di **100**
<br>```$skip```

## <a name="limitations"></a>Limitazioni

1. La dimensione massima della pagina è di **100 incidenti**.
2. La frequenza massima delle richieste è di **50 chiamate al minuto** e **1500 chiamate all'ora**.

## <a name="permissions"></a>Autorizzazioni

Per chiamare l'API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access Microsoft Threat Protection Apis](api-access.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato per le autorizzazioni
:---|:---|:---
Applicazione |   Incident. Read. All | ' Leggi tutti gli eventi non consentiti '
Applicazione |   Incident. ReadWrite. All | ' Leggi e Scrivi tutti gli incidenti '
Delegati (account aziendale o dell'Istituto di istruzione) | Evento Incident. Read | ' Leggi gli incidenti '
Delegati (account aziendale o dell'Istituto di istruzione) | Incident. ReadWrite | ' Operazioni di lettura e scrittura degli incidenti '

> [!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
> - L'utente deve disporre dell'autorizzazione di visualizzazione per gli eventi non consentiti nel portale.
> - La risposta includerà solo gli incidenti a cui l'utente è esposto.

## <a name="http-request"></a>Richiesta HTTP

```
GET /api/incidents
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Portatore {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Nessuna.

## <a name="response"></a>Risposta
Se l'operazione ha esito positivo, questo metodo restituisce 200 OK e un elenco di [operazioni](api-incident.md) non consentite nel corpo della risposta.

## <a name="schema-mapping"></a>Mapping dello schema

| Nome del campo                                | Descrizione                                                                                                                                                                                                                                                                                                                                                                                | Valore di esempio                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metadati degli incidenti**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | Identificatore univoco che rappresenta l'evento Incident.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Viene popolato solo nel caso in cui un evento Incident venga raggruppato insieme a un altro incidente, come parte della logica di elaborazione degli incidenti.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| evento incidentname                              | Valore stringa disponibile per ogni evento Incident.                                                                                                                                                                                                                                                                                                                                                  | Attività ransomware                                                                                                                                                                                                                               |
| createdTime                               | Ora in cui è stato creato l'evento Incident.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | Data e ora dell'ultimo aggiornamento dell'evento in back-end.<br> Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli eventi non consentiti.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| AssegnatoA                                | Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classificazione                            | Specifica per l'evento Incident. I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive*                                                                                                                                                                                                                                                                           | Unknown                                                                                                                                                                                                                                           |
| determinazione                             | Specifica la determinazione dell'evento Incident. I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| stato                                    | Categorizzare gli incidenti (come *attivi*o *risolti*). In questo modo è possibile organizzare e gestire la risposta a eventi non consentiti.                                                                                                                                                                                                                                                                  | Attivazione                                                                                                                                                                                                                                            |
| gravità                                  | Indica il possibile impatto sulle risorse. Maggiore è la gravità più grande è l'impatto. Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.<br>Uno dei valori seguenti: *informativo*, *basso*, * medio e *alto*.                                                                                                                                | Media                                                                                                                                                                                                                                            |
| Tag                                      | Matrice di tag personalizzati associati a un evento imprevisto, ad esempio per contrassegnare un gruppo di incidenti con una caratteristica comune.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| avvisi                                    | Matrice di tutti gli avvisi relativi all'incidente e ad altre informazioni, ad esempio la gravità, le entità che sono state coinvolte nell'avviso, l'origine degli avvisi.                                                                                                                                                                                                                     | \[\] (vedere i dettagli sui campi di avviso riportati di seguito)                                                                                                                                                                                                          |
| **Avvisi dei metadati**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | Identificatore univoco per rappresentare l'avviso                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | Identificatore univoco per rappresentare l'evento anomalo a cui è associato questo avviso                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| serviceSource                             | Servizio da cui proviene l'avviso, ad esempio Microsoft Defender ATP, Microsoft cloud app Security, Azure ATP o Office 365 ATP.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | Ora in cui è stato creato l'avviso.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | Ora dell'ultimo aggiornamento dell'avviso nel backend.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | Ora in cui l'avviso è stato risolto.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | Ora in cui il primo avviso ha riferito che l'attività è stata aggiornata nel backend.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| title                                     | Breve valore stringa di identificazione disponibile per ogni avviso.                                                                                                                                                                                                                                                                                                                                                     | Attività ransomware                                                                                                                                                                                                                               |
| descrizione                               | Valore stringa che descrive ogni avviso.                                                                                                                                                                                                                                                                                                                                                        | La User2 (testUser2@contoso.com) ha modificato i file di 99 con più estensioni che terminano con la *scaricare*di estensione non comune. Si tratta di un numero insolito di manipolazioni dei file ed è indicativo di un potenziale attacco ransomware. |
| Categoria                                  | Visualizzazione e visualizzazione numerica di quanto l'attacco è progredito lungo la catena di Kill. Allineato al [quadro di&CK™ Framework](https://attack.mitre.org/).                                                                                                                                                                                                                           | Impatto                                                                                                                                                                                                                                            |
| stato                                    | Categorizzare gli avvisi (come *nuovi*, *attivi*o *risolti*). In questo modo è possibile organizzare e gestire la risposta agli avvisi.                                                                                                                                                                                                                                                                   | Nuova                                                                                                                                                                                                                                               |
| gravità                                  | Indica il possibile impatto sulle risorse. Maggiore è la gravità più grande è l'impatto. Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.<br>Uno dei valori seguenti: *informativo*, *basso*, * medio e *alto*.                                                                                                                                   | Media                                                                                                                                                                                                                                            |
| investigationId                           | ID analisi automatizzato attivato da questo avviso.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | Informazioni sullo stato corrente dell'indagine. Uno dei seguenti: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, PartiallyInvestigated *, TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *unsupportos*, *UnsupportedAlertType*, *SuppressedAlert*. *PartiallyInvestigated* | UnsupportedAlertType                                                                                                                                                                                                                              |
| classificazione                            | Specifica per l'evento Incident. I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive* o *null*                                                                                                                                                                                                                                                                   | Unknown                                                                                                                                                                                                                                           |
| determinazione                             | Specifica la determinazione dell'evento Incident. I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* o  *null*                                                                                                                                                                                                     | APT                                                                                                                                                                                                                                               |
| AssegnatoA                                | Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorname                                 | Il gruppo di attività, se presente, associato all'avviso.                                                                                                                                                                                                                                                                                                                                        | BORO                                                                                                                                                                                                                                             |
| threatFamilyName                          | Famiglia di minacce associata all'avviso.                                                                                                                                                                                                                                                                                                                                                   | null                                                                                                                                                                                                                                              |
| mitreTechniques                           | Le tecniche di attacco, allineate al [mitra&CK](https://attack.mitre.org/)™ Framework.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| dispositivi                                   | Tutti i dispositivi in cui sono stati inviati avvisi relativi all'evento Incident.                                                                                                                                                                                                                                                                                                     | \[\] (vedere dettagli sui campi entità seguenti)                                                                                                                                                                                                         |
| **Formato dispositivo**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | ID del dispositivo come indicato in Microsoft Defender ATP.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  ID del dispositivo come indicato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD). Disponibile solo per i dispositivi appartenenti al dominio.                                                                                                                                                                                                                                                                                                                              | null                                                                                                                                                                                                                                              |
| deviceDnsName                             | Il nome di dominio completo per il dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | Piattaforma del sistema operativo in cui è in esecuzione il dispositivo.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | La versione di compilazione per il sistema operativo in cui è in esecuzione il dispositivo.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | Il gruppo di [controllo di accesso basato sui ruoli](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) associato al dispositivo.                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Ora in cui è stato visualizzato il dispositivo.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | Lo stato di integrità del dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | Attivazione                                                                                                                                                                                                                                            |
| riskScore                                 | Il Punteggio di rischio per il dispositivo.                                                                                                                                                                                                                                                                                                                                                                       | Fortemente                                                                                                                                                                                                                                              |
| entità                                  | Tutte le entità che sono state identificate come parte di un determinato avviso o che sono correlate a.                                                                                                                                                                                                                                                                                | \[\] (vedere dettagli sui campi entità seguenti)                                                                                                                                                                                                         |
| **Formato entità**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | Entità che sono state identificate come parte di un determinato avviso o che sono correlate.<br>I valori delle proprietà sono: *User*, *IP*, *URL*, *file*, *Process*, *Mailbox*, *MailMessage*, *MailCluster*, *Registry*                                                                                                                                                                                                     | Utente                                                                                                                                                                                                                                              |
| SHA1                                      | Disponibile se entityType è *file*.<br>Hash del file per gli avvisi associati a un file o a un processo.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| SHA256                                    | Disponibile se entityType è *file*.<br>Hash del file per gli avvisi associati a un file o a un processo.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | Disponibile se entityType è *file*.<br>Nome del file per gli avvisi associati a un file o a un processo                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| filePath                                  | Disponibile se entityType è *file*.<br>Percorso del file per gli avvisi associati a un file o a un processo                                                                                                                                                                                                                                                                                    | C: \\ \\ Agent \\ \\ \_ Work \\ \\ \_ temp \\ \\ deploy \_ System 2020-09-06 12 \_ 14 \_ 54 \\ \\ out                                                                                                                                                                    |
| processId                                 | Disponibile se entityType è *Process*.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Disponibile se entityType è *Process*.                                                                                                                                                                                                                                                                                                                                                     | "" \\ Il file è pronto per il Download \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | Disponibile se entityType è *Process*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | Disponibile se entityType è *Process*.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Disponibile se entityType è *Process*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| ipAddress                                 | Disponibile se entityType è *IP*. <br>Indirizzo IP per gli avvisi associati agli eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| URL                                       | Disponibile se entityType è l' *URL*. <br>URL per gli avvisi associati a eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| accountName                               | Disponibile se entityType è *User*.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | Disponibile se entityType è *User*.                                                                                                                                                                                                                                                                                                                                                        | Europe. Corp. contoso                                                                                                                                                                                                                              |
| userSid                                   | Disponibile se entityType è *User*.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Disponibile se entityType è *User*.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Disponibile se entityType è una *cassetta postale*.                                                                                                                                                                                                                                                                                                                                                     | test User2                                                                                                                                                                                                                                        |
| mailboxAddress                            | Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Disponibile se entityType è  *MailCluster*.                                                                                                                                                                                                                                                                                                                                                 | Soggetto P2SenderDomain; ContentType                                                                                                                                                                                                                |
| mittente                                    | Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| destinatario                                 | Disponibile se entityType è *MailMessage*.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | Disponibile se entityType è *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | \[\]Attenzione esterna                                                                                                                                                                                                                            |
| deliveryAction                            | Disponibile se entityType è *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | Consegnato                                                                                                                                                                                                                                         |
| securityGroupId                           | Disponibile se entityType è  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-AB09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Disponibile se entityType è  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | Operatori di configurazione di rete                                                                                                                                                                                                                   |
| registryHive                              | Disponibile se entityType è  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | \_computer locale di HKEY \_                                                                                                                                                                                                                              |
| registryKey                               | Disponibile se entityType è  *Registry*.                                                                                                                                                                                                                                                                                                                                                     | SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Disponibile se entityType è  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | Stringa                                                                                                                                                                                                                                            |
| registryValue                             | Disponibile se entityType è  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | L'ID, se presente, del dispositivo relativo all'entità.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Esempio

**Richiesta**

```
GET https://api.security.microsoft.com/api/incidents
```

**Risposta**
```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-topic"></a>Argomento correlato
- [Incidenti delle API](api-incident.md)
- [Aggiornare incidente](api-update-incidents.md)
