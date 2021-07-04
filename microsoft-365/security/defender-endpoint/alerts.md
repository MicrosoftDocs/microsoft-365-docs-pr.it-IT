---
title: API Per ottenere avvisi
description: Informazioni sui metodi e le proprietà del tipo di risorsa Avviso in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289680"
---
# <a name="alert-resource-type"></a>Tipo di risorsa avviso

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Metodi

Metodo |Tipo restituito |Descrizione
:---|:---|:---
[Ottenere un avviso](get-alert-info-by-id.md) | [Avviso](alerts.md) | Ottenere un singolo [oggetto](alerts.md) avviso.
[Elencare avvisi](get-alerts.md) | [Raccolta avvisi](alerts.md) | Raccolta [avvisi elenco.](alerts.md)
[Avviso di aggiornamento](update-alert.md) | [Avviso](alerts.md) | Aggiorna avviso [specifico](alerts.md).
[Avvisi di aggiornamento in batch](batch-update-alerts.md) | | Aggiornare un batch di [avvisi](alerts.md).
[Creare un avviso](create-alert-by-reference.md)|[Avviso](alerts.md)|Crea un avviso in base ai dati dell'evento ottenuti da [Advanced Hunting.](run-advanced-query-api.md)
[Elencare i domini correlati](get-alert-related-domain-info.md)|Raccolta di domini| Url elenco associati all'avviso.
[Elencare i file correlati](get-alert-related-files-info.md) | [Raccolta file](files.md) |  Elencare [le entità](files.md) file associate all'avviso . [](alerts.md)
[Elenco indirizzi IP correlati](get-alert-related-ip-info.md) | Raccolta IP | Elencare gli INDIRIZZI IP associati all'avviso.
[Ottenere i computer correlati](get-alert-related-machine-info.md) | [Computer](machine.md) | Computer [associato](machine.md) [all'avviso](alerts.md).
[Ottenere utenti correlati](get-alert-related-user-info.md) | [Utente](user.md) | [L'utente](user.md) associato [all'avviso](alerts.md).

## <a name="properties"></a>Proprietà

Proprietà |    Tipo    |    Descrizione
:---|:---|:---
id | Stringa | ID avviso.
title | Stringa | Titolo dell'avviso.
descrizione | Stringa | Descrizione dell'avviso.
alertCreationTime | Nullable DateTimeOffset | Data e ora (in UTC) in cui è stato creato l'avviso.
lastEventTime | Nullable DateTimeOffset | Ultima occorrenza dell'evento che ha attivato l'avviso sullo stesso dispositivo.
firstEventTime | Nullable DateTimeOffset | Prima occorrenza dell'evento che ha attivato l'avviso nel dispositivo.
lastUpdateTime | Nullable DateTimeOffset | Data e ora (in UTC) dell'ultimo aggiornamento dell'avviso.
resolvedTime | Nullable DateTimeOffset | Data e ora in cui lo stato dell'avviso è stato modificato in "Risolto".
incidentId | Nullable Long | ID [evento](view-incidents-queue.md) imprevisto dell'avviso.
investigationId | Nullable Long | ID [dell'indagine](automated-investigations.md) correlato all'avviso.
investigationState | Enumerazione Nullable | Stato corrente dell'oggetto [Investigation.](automated-investigations.md) I valori possibili sono: "Unknown", "Terminated", 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
assignedTo | Stringa | Proprietario dell'avviso.
gravità | Enum | Gravità dell'avviso. I valori possibili sono: 'UnSpecified', 'Informational', 'Low', 'Medium' e 'High'.
status | Enum | Specifica lo stato corrente dell'avviso. I valori possibili sono: 'Unknown', 'New', 'InProgress' e 'Resolved'.
classificazione | Enumerazione Nullable | Specifica dell'avviso. I valori possibili sono: 'Unknown', 'FalsePositive', 'TruePositive'.
determinazione | Enumerazione Nullable | Specifica la determinazione dell'avviso. I valori possibili sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.
category| Stringa | Categoria dell'avviso.
detectionSource | Stringa | Origine di rilevamento.
threatFamilyName | Stringa | Famiglia di minacce.
threatName | Stringa | Nome della minaccia.
machineId | Stringa | ID di [un'entità](machine.md) computer associata all'avviso.
computerDnsName | Stringa | [nome](machine.md) completo del computer.
aadTenantId | Stringa | ID Azure Active Directory.
detectorId | Stringa | ID del rilevatore che ha attivato l'avviso.
commenti | Elenco dei commenti degli avvisi | L'oggetto Alert Comment contiene: stringa di commento, stringa createdBy e createTime date time.
Prove | Elenco delle prove di avviso | Prova relativa all'avviso. Vedere l'esempio che segue.

### <a name="response-example-for-getting-single-alert"></a>Esempio di risposta per ottenere un singolo avviso:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
