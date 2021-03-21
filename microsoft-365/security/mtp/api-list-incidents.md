---
title: API di elenchi di eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come elencare le API per gli eventi imprevisti in Microsoft 365 Defender
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d1e2ceb4c5cc662fe0aff248f2d0662ad6a2cc82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922235"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>API di elenchi di eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti prereleased che possono essere sostanzialmente modificati prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descrizione API

L'API elenca eventi imprevisti consente di ordinare gli eventi imprevisti per creare una risposta informata alla sicurezza informatica. Espone una raccolta di eventi imprevisti contrassegnati nella rete, entro l'intervallo di tempo specificato nei criteri di conservazione dell'ambiente. Gli eventi imprevisti più recenti vengono visualizzati all'inizio dell'elenco. Ogni evento imprevisto contiene una matrice di avvisi correlati e le relative entità.

L'API supporta gli operatori **OData** seguenti:

- `$filter`nelle `lastUpdateTime` proprietà , `createdTime` , `status` e `assignedTo`
- `$top`, con un valore massimo **di 100**
- `$skip`

## <a name="limitations"></a>Limitazioni

1. La dimensione massima della pagina **è 100 eventi imprevisti.**
2. La velocità massima delle richieste **è di 50 chiamate al minuto** e **1500 chiamate all'ora.**

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Accedere alle [API di Microsoft 365 Defender](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
-|-|-
Applicazione | Incident.Read.All | Leggere tutti gli eventi imprevisti
Applicazione | Incident.ReadWrite.All | Lettura e scrittura di tutti gli eventi imprevisti
Delegato (account aziendale o dell'istituto di istruzione) | Incident.Read | Eventi imprevisti di lettura
Delegato (account aziendale o dell'istituto di istruzione) | Incident.ReadWrite | Eventi imprevisti di lettura e scrittura

> [!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve disporre dell'autorizzazione di visualizzazione per gli eventi imprevisti nel portale.
> - La risposta includerà solo gli eventi imprevisti a cui l'utente è esposto.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
-|-|-
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**


## <a name="request-body"></a>Corpo della richiesta

Nessuna.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce `200 OK` e un elenco di eventi [imprevisti](api-incident.md) nel corpo della risposta.

## <a name="schema-mapping"></a>Mapping dello schema

### <a name="incident-metadata"></a>Metadati degli eventi imprevisti

Nome del campo | Descrizione | Valore di esempio
-|-|-
incidentId | Identificatore univoco per rappresentare l'evento imprevisto | 924565
redirectIncidentId | Popolato solo nel caso in cui un evento imprevisto venga raggruppato insieme a un altro evento imprevisto, come parte della logica di elaborazione degli eventi imprevisti. | 924569
incidentName | Valore stringa disponibile per ogni evento imprevisto. | Attività ransomware
createdTime | Ora di creazione dell'evento imprevisto. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Ora dell'ultimo aggiornamento dell'evento imprevisto nel back-end.<br /><br /> Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli eventi imprevisti. | 2020-09-06T14:46:57.29Z
assignedTo | Proprietario dell'evento imprevisto oppure *null se* non è assegnato alcun proprietario. | secop2@contoso.com
classificazione | Specifica per l'evento imprevisto. I valori delle proprietà *sono: Unknown,* *FalsePositive,* *TruePositive* | Unknown
determinazione | Specifica la determinazione dell'evento imprevisto. I valori delle proprietà sono: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* | NotAvailable
status | Categorizzare gli eventi imprevisti *(come Active* o *Resolved).* Può essere utile per organizzare e gestire la risposta agli eventi imprevisti. | Attivo
gravità | Indica il possibile impatto sulle risorse. Maggiore è la gravità, maggiore sarà l'impatto. In genere, gli elementi di gravità superiore richiedono l'attenzione più immediata.<br /><br />Uno dei valori seguenti: *Informational,* *Low,**Medium e *High.* | Medio
tag | Matrice di tag personalizzati associati a un evento imprevisto, ad esempio per contrassegnare un gruppo di eventi imprevisti con una caratteristica comune. | \[\]
avvisi | Matrice contenente tutti gli avvisi correlati all'evento imprevisto, oltre ad altre informazioni, ad esempio la gravità, le entità coinvolte nell'avviso e l'origine degli avvisi. | \[\] (vedi i dettagli sui campi degli avvisi di seguito)

### <a name="alerts-metadata"></a>Metadati degli avvisi

Nome del campo | Descrizione | Valore di esempio
-|-|-
alertId | Identificatore univoco per rappresentare l'avviso | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Identificatore univoco per rappresentare l'evento imprevisto a cui è associato questo avviso | 924565
serviceSource | Servizio da cui proviene l'avviso, ad esempio Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity o Microsoft Defender per Office 365. | MicrosoftCloudAppSecurity
creationTime | Ora di creazione dell'avviso. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Ora dell'ultimo aggiornamento dell'avviso nel back-end. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Ora in cui l'avviso è stato risolto. | 2020-09-10T05:22:59Z
firstActivity | Ora in cui l'avviso ha segnalato per la prima volta che l'attività è stata aggiornata nel back-end.| 2020-09-04T05:22:59Z
title | Breve valore stringa di identificazione disponibile per ogni avviso. | Attività ransomware
descrizione | Valore stringa che descrive ogni avviso. | L'utente Test User2 (testUser2@contoso.com) ha modificato 99 file con più estensioni che terminano con l'estensione non comune *herunterladen*. Si tratta di un numero insolito di manipolazioni di file ed è indicativo di un potenziale attacco ransomware.
category | Visual and numeric view of how far the attack has progressed along the kill chain. Allineato al framework [MITRE ATT&CK™](https://attack.mitre.org/). | Impatto
status | Categorizzare gli avvisi *(come Nuovo,* *Attivo* o *Risolto).* Può essere utile per organizzare e gestire la risposta agli avvisi. | Nuova
gravità | Indica il possibile impatto sulle risorse. Maggiore è la gravità, maggiore sarà l'impatto. In genere, gli elementi di gravità superiore richiedono l'attenzione più immediata.<br>Uno dei valori seguenti: *Informational,* *Low,**Medium e *High.* | Medio
investigationId | ID dell'indagine automatizzata attivato da questo avviso. | 1234
investigationState | Informazioni sullo stato corrente dell'indagine. Uno dei valori seguenti: *Unknown,* *Terminated,* *SuccessfullyRemediated,* *Benign,* *Failed,* *PartiallyRemediated,* *Running,* *PendingApproval,* *PendingResource,* *PartiallyInvestigated,* *TerminatedByUser,* *TerminatedBySystem,* *Queued,* *InnerFailure,* *PreexistingAlert,* *UnsupportedOs,* *UnsupportedAlertType,* *SuppressedAlert.* | UnsupportedAlertType
classificazione | Specifica per l'evento imprevisto. I valori delle proprietà *sono: Unknown,* *FalsePositive,* *TruePositive* o *null* | Unknown
determinazione | Specifica la determinazione dell'evento imprevisto. I valori delle proprietà sono: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* o  *null* | Apt
assignedTo | Proprietario dell'evento imprevisto oppure *null se* non è assegnato alcun proprietario. | secop2@contoso.com
actorName | Gruppo di attività, se presente, associato a questo avviso. | BORON
threatFamilyName | Famiglia di minacce associata a questo avviso. | null
mitreTechniques | Le tecniche di attacco, allineate al framework di&CK ™ [MITRE.](https://attack.mitre.org/) | \[\]
dispositivi | Tutti i dispositivi in cui sono stati inviati avvisi relativi all'evento imprevisto. | \[\] (vedi i dettagli sui campi dell'entità di seguito)

### <a name="device-format"></a>Formato dispositivo

Nome del campo | Descrizione | Valore di esempio
-|-|-
DeviceId | ID dispositivo designato in Microsoft Defender ATP. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  ID dispositivo designato in [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-whatis) Disponibile solo per i dispositivi aggiunti a un dominio. | null
deviceDnsName | Nome di dominio completo per il dispositivo. | user5cx.middleeast.corp.contoso.com
osPlatform | Piattaforma del sistema operativo in esecuzione nel dispositivo.| WindowsServer2016
osBuild | Versione della build per il sistema operativo in esecuzione nel dispositivo. | 14393
rbacGroupName | Gruppo [di controllo di accesso](/azure/role-based-access-control/overview) basato sui ruoli associato al dispositivo. | WDATP-Ring0
firstSeen | Ora in cui il dispositivo è stato visualizzato per la prima volta. | 2020-02-06T14:16:01.9330135Z
healthStatus | Stato di integrità del dispositivo. | Attivo
riskScore | Punteggio di rischio per il dispositivo. | Alta
entità | Tutte le entità identificate come parte o correlate a un determinato avviso. | \[\] (vedi i dettagli sui campi dell'entità di seguito)

### <a name="entity-format"></a>Formato entità

Nome del campo | Descrizione | Valore di esempio
-|-|-
entityType | Entità identificate come parte o correlate a un determinato avviso.<br>I valori delle proprietà sono: *User,* *Ip,* *Url,* *File,* *Process,* *MailBox,* *MailMessage,* *MailCluster,* *Registry* | Utente
sha1 | Disponibile se entityType è *File*.<br>Hash del file per gli avvisi associati a un file o a un processo. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Disponibile se entityType è *File*.<br>Hash del file per gli avvisi associati a un file o a un processo. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Disponibile se entityType è *File*.<br>Nome file per gli avvisi associati a un file o a un processo | Detector.UnitTests.dll
filePath | Disponibile se entityType è *File*.<br>Percorso file per gli avvisi associati a un file o a un processo | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Disponibile se entityType è *Process*. | 24348
processCommandLine | Disponibile se entityType è *Process*. | "Il file è pronto per il download \_1911150169.exe"
processCreationTime | Disponibile se entityType è *Process*. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Disponibile se entityType è *Process*. | 16840
parentProcessCreationTime | Disponibile se entityType è *Process*. | 2020-07-18T02:12:32.8616797Z
ipAddress | Disponibile se entityType è *Ip*. <br>Indirizzo IP per gli avvisi associati a eventi di rete, ad esempio *Comunicazione con una destinazione di rete dannosa.* | 62.216.203.204
url | Disponibile se entityType è *Url*. <br>URL per gli avvisi associati a eventi di rete, ad esempio Comunicazione *con una destinazione di rete dannosa.* | down.esales360.cn
accountName | Disponibile se entityType è *User*. | testUser2
domainName | Disponibile se entityType è *User*. | europe.corp.contoso
userSid | Disponibile se entityType è *User*. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Disponibile se entityType è *User*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Disponibile se entityType è *User* / *MailBox* / *MailMessage.* | testUser2@contoso.com
mailboxDisplayName | Disponibile se entityType è *MailBox*. | test User2
mailboxAddress | Disponibile se entityType è *User* / *MailBox* / *MailMessage.* | testUser2@contoso.com
clusterBy | Disponibile se entityType è  *MailCluster*. | Subject; P2SenderDomain; ContentType
mittente | Disponibile se entityType è *User* / *MailBox* / *MailMessage.* | user.abc@mail.contoso.co.in
destinatario | Disponibile se entityType è *MailMessage.* | testUser2@contoso.com
subject | Disponibile se entityType è *MailMessage.* | \[Attenzione \] ESTERNA
deliveryAction | Disponibile se entityType è *MailMessage.* | Recapitati
securityGroupId | Disponibile se entityType è *SecurityGroup.* | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Disponibile se entityType è *SecurityGroup.* | Network Configuration Operators
registryHive | Disponibile se entityType è  *Registry*. | HKEY \_ COMPUTER \_ LOCALE |
registryKey | Disponibile se entityType è  *Registry*. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Disponibile se entityType è  *Registry*. | Stringa
registryValue | Disponibile se entityType è  *Registry*. | 31-00-00-00
deviceId | ID, se presente, del dispositivo correlato all'entità. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Esempio

**Richiesta**

```HTTP
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

## <a name="related-articles"></a>Articoli correlati

- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Incidenti delle API](api-incident.md)
- [API per gli eventi imprevisti di aggiornamento](api-update-incidents.md)