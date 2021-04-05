---
title: Tipo di risorsa di indagine
description: Entità Microsoft Defender for Endpoint Investigation.
keywords: api, api del grafico, api supportate, ottenere, avvisi, indagini
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587684"
---
# <a name="investigation-resource-type"></a>Tipo di risorsa di indagine

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Rappresenta un'entità di indagine automatizzata in Defender for Endpoint.
<br> Per [ulteriori informazioni, vedere](automated-investigations.md) Panoramica delle indagini automatizzate.

## <a name="methods"></a>Metodi
Metodo|Tipo restituito |Descrizione
:---|:---|:---
[Indagini elenco](get-investigation-collection.md) | Raccolta di indagini | Ottenere la raccolta di indagini
[Ottenere un'indagine singola](get-investigation-object.md) | Entità di indagine | Ottiene una singola entità Investigation.
[Avviare indagine](initiate-autoir-investigation.md) | Entità di indagine | Avvia l'analisi in un dispositivo.


## <a name="properties"></a>Proprietà
Proprietà |  Tipo    |   Descrizione
:---|:---|:---
id | Stringa | Identità dell'entità di indagine. 
startTime | DateTime Nullable | Data e ora di creazione dell'indagine. 
endTime | DateTime Nullable | Data e ora di completamento dell'indagine. 
cancelledBy | Stringa | ID dell'utente/applicazione che ha annullato l'indagine. 
investigationState | Enum | Stato corrente dell'indagine. I valori possibili sono: "Unknown", "Terminated", 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails | Stringa | Ulteriori informazioni sullo stato dell'indagine.
machineId | Stringa | ID del dispositivo in cui viene eseguita l'indagine.
computerDnsName | Stringa | Nome del dispositivo in cui viene eseguita l'indagine.
triggeringAlertId | Stringa | ID dell'avviso che ha attivato l'indagine.


## <a name="json-representation"></a>Rappresentazione Json

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
