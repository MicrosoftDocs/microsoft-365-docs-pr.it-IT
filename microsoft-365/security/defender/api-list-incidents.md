---
title: Api elenco incidenti in Microsoft 365 Defender
description: Informazioni su come elencare l'API degli incidenti in Microsoft 365 Defender
keywords: elenco, incidente, incidenti, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572154"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Api elenco incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.


## <a name="api-description"></a>Descrizione API

L'API degli incidenti dell'elenco consente di ordinare gli incidenti per creare una risposta informata alla sicurezza informatica. Espone una raccolta di incidenti contrassegnati nella rete, entro l'intervallo di tempo specificato nei criteri di conservazione dell'ambiente. Gli incidenti più recenti vengono visualizzati nella parte superiore dell'elenco. Ogni incidente contiene una serie di avvisi correlati e le relative entità.

L'API supporta i seguenti **operatori OData:**

- `$filter`sulle `lastUpdateTime` proprietà `createdTime` , , `status` e `assignedTo`
- `$top`, con un valore massimo di **100**
- `$skip`

## <a name="limitations"></a>Limitazioni

1. La dimensione massima della pagina **è di 100 incidenti**.
2. La frequenza massima delle richieste è **di 50 chiamate al minuto** e **1500 chiamate all'ora.**

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, incluso come scegliere le autorizzazioni, vedere [Access Microsoft 365 Defender API](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
-|-|-
Applicazione | Incident.Read.All | Leggi tutti gli incidenti
Applicazione | Incident.ReadWrite.All | Leggere e scrivere tutti gli incidenti
Delegato (account aziendale o dell'istituto di istruzione) | Incidente.Lettura | Leggi gli incidenti
Delegato (account aziendale o dell'istituto di istruzione) | Incident.ReadWrite | Leggere e scrivere incidenti

> [!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve avere l'autorizzazione di visualizzazione per gli incidenti nel portale.
> - La risposta includerà solo gli incidenti a cui l'utente è esposto.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
-|-|-
Autorizzazione | Stringa | Portatore {token}. **Obbligatorio**


## <a name="request-body"></a>Corpo della richiesta

Nessuna.

## <a name="response"></a>Risposta

In caso di esito positivo, questo `200 OK` metodo restituisce e un elenco [di](api-incident.md) incidenti nel corpo della risposta.

## <a name="schema-mapping"></a>Mapping dello schema

### <a name="incident-metadata"></a>Metadati dell'incidente

Nome del campo | Descrizione | Valore di esempio
-|-|-
id incidente | Identificatore univoco per rappresentare l'incidente | 924565
redirectIncidentId | Popolato solo nel caso in cui un incidente venga raggruppato insieme a un altro incidente, come parte della logica di elaborazione degli incidenti. | 924569
incidentName | Valore stringa disponibile per ogni incidente. | Attività ransomware
tempo creato | Ora in cui l'incidente è stato creato per la prima volta. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Ora dell'ultimo aggiornamento dell'incidente nel back-end.<br /><br /> Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli incidenti. | 2020-09-06T14:46:57.29Z
assegnatoA | Proprietario dell'incidente o *null se* non è assegnato alcun proprietario. | secop2@contoso.com
classificazione | Specifica dell'incidente. I valori delle proprietà *sono: Unknown*, *FalsePositive*, *TruePositive* | Unknown
determinazione | Specifica la determinazione dell'incidente. I valori delle proprietà sono: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* | Non disponibile
stato | Categorizzare gli incidenti *(come* attivi o *risolti).* Può aiutarti a organizzare e gestire la tua risposta agli incidenti. | Attivo
severità | Indica il possibile impatto sulle risorse. Maggiore è la gravità, maggiore è l'impatto. In genere gli elementi di gravità più elevata richiedono l'attenzione più immediata.<br /><br />Uno dei valori seguenti: *Informational*, *Low*, *Medium e *High*. | Medio
Tag | Matrice di tag personalizzati associati a un incidente, ad esempio per contrassegnare un gruppo di incidenti con una caratteristica comune. | \[\]
Commenti | Matrice di commenti creati dai secop durante la gestione dell'incidente, ad esempio informazioni aggiuntive sulla selezione della classificazione. | \[\]
Avvisi | Matrice contenente tutti gli avvisi relativi all'incidente, oltre ad altre informazioni, ad esempio la gravità, le entità coinvolte nell'avviso e l'origine degli avvisi. | \[\] (vedere i dettagli sui campi degli avvisi di seguito)

### <a name="alerts-metadata"></a>Avvisi metadati

Nome del campo | Descrizione | Valore di esempio
-|-|-
ID avviso | Identificatore univoco per rappresentare l'avviso | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
id incidente | Identificatore univoco per rappresentare l'incidente a cui è associato questo avviso | 924565
origine servizio | Servizio da cui proviene l'avviso, ad esempio Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity o Microsoft Defender per Office 365. | MicrosoftCloudAppSecurity
tempo di creazione | Ora di creazione dell'avviso. | 2020-09-06T14:46:55.7182276Z
LastUpdatedTime | Ora dell'ultimo aggiornamento dell'avviso nel back-end. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Ora in cui l'avviso è stato risolto. | 2020-09-10T05:22:59Z
prima Attività | Ora in cui l'avviso ha segnalato per la prima volta che l'attività è stata aggiornata al back-end.| 2020-09-04T05:22:59Z
title | Breve identificazione del valore stringa disponibile per ogni avviso. | Attività ransomware
descrizione | Valore stringa che descrive ogni avviso. | L'utente Test User2 (testUser2@contoso.com) ha manipolato 99 file con più estensioni che terminano con l'estensione non *comune herunterladen*. Questo è un numero insolito di manipolazioni di file ed è indicativo di un potenziale attacco ransomware.
categoria | Visualizzazione visiva e numerica di quanto l'attacco è progredito lungo la catena di uccisioni. Allineato al [framework CK&CK™&MITRE](https://attack.mitre.org/). | Impatto
stato | Categorizzare gli avvisi *(come* Nuovi *, Attivi* o *Risolti*). Può aiutarti a organizzare e gestire la tua risposta agli avvisi. | Nuovo
severità | Indica il possibile impatto sulle risorse. Maggiore è la gravità, maggiore è l'impatto. In genere gli elementi di gravità più elevata richiedono l'attenzione più immediata.<br>Uno dei valori seguenti: *Informational*, *Low*, *Medium e *High*. | Medio
ID indagine | ID dell'indagine automatizzato attivato da questo avviso. | 1234
studioStato | Informazioni sullo stato attuale dell'indagine. Uno dei valori seguenti: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | Tipo non supportato
classificazione | Specifica dell'incidente. I valori delle proprietà *sono: Unknown*, *FalsePositive*, *TruePositive* o *null* | Unknown
determinazione | Specifica la determinazione dell'incidente. I valori delle proprietà sono: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* o  *null* | Appartamento
assegnatoA | Proprietario dell'incidente o *null se* non è assegnato alcun proprietario. | secop2@contoso.com
nome attore | Il gruppo di attività, se presente, l'oggetto associato a questo avviso. | boro
threatFamilyName | Famiglia di minacce associata a questo avviso. | null
mitreTechniques | Le tecniche di attacco, allineate con [la MITRE ATT&CK](https://attack.mitre.org/)™ framework. | \[\]
Dispositivi | Tutti i dispositivi in cui sono stati inviati avvisi relativi all'incidente. | \[\] (vedere i dettagli sui campi delle entità di seguito)

### <a name="device-format"></a>Formato dispositivo

Nome del campo | Descrizione | Valore di esempio
-|-|-
Id dispositivo | ID dispositivo come indicato in Microsoft Defender for Endpoint. | 24c222B0B60FE148eeece49ac83910cc6a7ef491
AadDeviceId |  ID dispositivo come indicato in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Disponibile solo per i dispositivi aggiunti al dominio. | null
deviceDnsName | Nome di dominio completo per il dispositivo. | user5cx.middleeast.corp.contoso.com
piattaforma os | La piattaforma del sistema operativo in esecuzione.| WindowsServer2016
edificio del sistema operativo | Versione di compilazione per il sistema operativo in esecuzione nel dispositivo. | 14393
rbacGroupName | Gruppo [di controllo degli accessi](/azure/role-based-access-control/overview) basato sui ruoli (RBAC) associato al dispositivo. | WDATP-Ring0
primaSeen | Ora in cui il dispositivo è stato visto per la prima volta. | 2020-02-06T14:16:01.9330135Z
stato integrità | Stato di integrità del dispositivo. | Attivo
riskScore | Punteggio di rischio per il dispositivo. | Alta
Entità | Tutte le entità identificate come parte o correlate a un determinato avviso. | \[\] (vedere i dettagli sui campi delle entità di seguito)

### <a name="entity-format"></a>Formato entità

Nome del campo | Descrizione | Valore di esempio
-|-|-
tipo entità | Entità che sono state identificate come parte o correlate a un determinato avviso.<br>I valori delle proprietà sono: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster* *,* Registry | Utente
sha1 | Disponibile se entityType è *File*.<br>Hash del file per gli avvisi associati a un file o a un processo. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Disponibile se entityType è *File*.<br>Hash del file per gli avvisi associati a un file o a un processo. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
Filename | Disponibile se entityType è *File*.<br>Nome file per gli avvisi associati a un file o a un processo | Detector.UnitTests.dll
percorsofile | Disponibile se entityType è *File*.<br>Percorso del file per gli avvisi associati a un file o a un processo | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
ID processo | Disponibile se entityType è *Process*. | 24348
processCommandLine | Disponibile se entityType è *Process*. | "Il file è pronto per il \_ download1911150169.exe"
ProcessCreationTime | Disponibile se entityType è *Process*. | 2020-07-18T03:25:38.5269993Z
IdProcesso padre | Disponibile se entityType è *Process*. | 16840
ParentProcessCreationTime | Disponibile se entityType è *Process*. | 2020-07-18T02:12:32.8616797Z
Indirizzoip | Disponibile se entityType è *Ip*. <br>Indirizzo IP per gli avvisi associati a eventi di rete, ad esempio *Comunicazione a una destinazione di rete dannosa*. | 62.216.203.204
URL | Disponibile se entityType è *URL*. <br>URL degli avvisi associati agli eventi di rete, ad esempio *Comunicazione a una destinazione di rete dannosa*. | down.esales360.cn
nome account | Disponibile se entityType è *User*. | Utentetest2
nomedominio | Disponibile se entityType è *User*. | europe.corp.contoso
IDutenti | Disponibile se entityType è *User*. | S-1-5-21-1721254763-462695806-1538882281-4156657
id utenteaad | Disponibile se entityType è *User*. | FC8F7484-F813-4DB2-AFAB-BC1507913FB6
userPrincipalName | Disponibile se entityType è *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
mailboxDisplayName | Disponibile se entityType è *MailBox*. | testare l'utente2
indirizzo cassetta postale | Disponibile se entityType è *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
clusterBy | Disponibile se entityType è  *MailCluster*. | Oggetto; P2SenderDomain; Tipo di contenuto
mittente | Disponibile se entityType è *User* / *MailBox* / *MailMessage*. | user.abc@mail.contoso.co.in
destinatario | Disponibile se entityType è *MailMessage*. | testUser2@contoso.com
subject | Disponibile se entityType è *MailMessage*. | \[ATTENZIONE \] ESTERNA
deliveryAzione | Disponibile se entityType è *MailMessage*. | consegnato
SecurityGroupId | Disponibile se entityType è  *SecurityGroup*. | 301C47C8-E15F-4059-AB09-E2BA9FFD372B
nomegruppodi protezione | Disponibile se entityType è  *SecurityGroup*. | Operatori di configurazione di rete
registroHive | Disponibile se entityType è  *Registry*. | HKEY \_ LOCAL \_ MACHINE |
Chiave del Registro di sistema | Disponibile se entityType è  *Registry*. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
RegistryValueType | Disponibile se entityType è  *Registry*. | Stringa
valore del Registro di sistema | Disponibile se entityType è  *Registry*. | 31-00-00-00
ID dispositivo | ID, se del caso, del dispositivo relativo all'entità. | 986E5DF8B73DACD43C8917D17E523E76B13C75CD

## <a name="example"></a>Esempio

**richiesta**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**risposta**

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

## <a name="related-articles"></a>Articoli correlati

- [Accedere alle API Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti e le licenze delle API](api-terms.md)
- [Informazioni i codici di errore](api-error-codes.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Incidenti delle API](api-incident.md)
- [Aggiornare l'API degli incidenti](api-update-incidents.md)
