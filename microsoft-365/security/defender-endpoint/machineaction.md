---
title: tipo di risorsa machineAction
description: Informazioni sui metodi e le proprietà del tipo di risorsa MachineAction in Microsoft Defender per Endpoint.
keywords: api, api supportate, get, machineaction, recente
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
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187386"
---
# <a name="machineaction-resource-type"></a>Tipo di risorsa MachineAction

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Per ulteriori informazioni, vedere [Response Actions.](respond-machine-alerts.md) 

| Metodo                                                            | Tipo restituito                        | Descrizione                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [Elenco MachineActions](get-machineactions-collection.md)           | [Azione computer](machineaction.md) | Elenca [entità azione](machineaction.md) computer.           |
| [Get MachineAction](get-machineaction-object.md)                  | [Azione computer](machineaction.md) | Ottenere una singola [entità Machine Action.](machineaction.md)     |
| [Raccogliere il pacchetto di analisi](collect-investigation-package.md) | [Azione computer](machineaction.md) | Raccogliere il pacchetto di analisi da un [computer](machine.md). |
| [Ottenere l'URI di firma di accesso condiviso del pacchetto di analisi](get-package-sas-uri.md)       | [Azione computer](machineaction.md) | Ottenere l'URI per il download del pacchetto di analisi.          |
| [Isola computer](isolate-machine.md)                             | [Azione computer](machineaction.md) | Isolare [il computer](machine.md) dalla rete.                 |
| [Rilasciare il computer dall'isolamento](unisolate-machine.md)            | [Azione computer](machineaction.md) | Rilasciare [il computer](machine.md) da Isolation.               |
| [Limitare l'esecuzione delle app](restrict-code-execution.md)              | [Azione computer](machineaction.md) | Limitare l'esecuzione dell'applicazione.                             |
| [Rimuovere la restrizione dell'app](unrestrict-code-execution.md)            | [Azione computer](machineaction.md) | Rimuovere la restrizione di esecuzione dell'applicazione.                   |
| [Eseguire l'analisi antivirus](run-av-scan.md)                              | [Azione computer](machineaction.md) | Eseguire un'analisi AV usando Windows Defender (se applicabile).    |
| [Computer offboard](offboard-machine-api.md)                       | [Azione computer](machineaction.md) | Computer [offboard](machine.md) da Microsoft Defender for Endpoint. |
| [Arrestare e mettere in quarantena il file](stop-and-quarantine-file.md)           | [Azione computer](machineaction.md) | Interrompere l'esecuzione di un file in un computer ed eliminarlo.        |

<br>

## <a name="properties"></a>Proprietà

| Proprietà            | Tipo           | Descrizione                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Identità [dell'entità Machine Action.](machineaction.md)                                                                                                                                                     |
| type                | Enum           | Tipo dell'azione. I valori possibili sono: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" e "UnrestrictCodeExecution" |
| ambito               | stringa         | Ambito dell'azione. "Full" o "Selective" per Isolation, "Quick" o "Full" per Anti-Virus Scan.                                                                                                   |
| richiedente           | Stringa         | Identità della persona che ha eseguito l'azione.                                                                                                                                                               |
| requestorComment    | Stringa         | Commento scritto durante l'esecuzione dell'azione.                                                                                                                                                              |
| status              | Enum           | Stato corrente del comando. I valori possibili sono: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" e "Canceled".                                                                                 |
| machineId           | Stringa         | ID del [computer in](machine.md) cui è stata eseguita l'azione.                                                                                                                                              |
| machineId           | Stringa         | Nome del [computer in](machine.md) cui è stata eseguita l'azione.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | Data e ora di creazione dell'azione.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | Data e ora dell'ultimo aggiornamento dello stato dell'azione.                                                                                                                                                     |
| relatedFileInfo     | Classe          | Contiene due proprietà. string ```fileIdentifier``` , Enum ```fileIdentifierType``` con i valori possibili: "Sha1", "Sha256" e "Md5".                                                                         |


## <a name="json-representation"></a>Rappresentazione Json

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
