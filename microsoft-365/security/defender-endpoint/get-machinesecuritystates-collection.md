---
title: API per la raccolta degli stati di sicurezza dei computer
description: Recupera una raccolta di stati di sicurezza dei dispositivi usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivo, sicurezza, stato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200366"
---
# <a name="get-machines-security-states-collection-api"></a>API per la raccolta degli stati di sicurezza get machines

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera una raccolta di stati di sicurezza dei dispositivi.

## <a name="permissions"></a>Autorizzazioni
L'utente necessita delle autorizzazioni di lettura.

## <a name="http-request"></a>Richiesta HTTP
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>Intestazioni di richiesta

Intestazione | Valore 
:---|:---
Autorizzazione | Bearer {token}. **Obbligatorio**.
Tipo contenuto | application/json

## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo - 200 OK.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

**Risposta**

Ecco un esempio di risposta.
*L'ID* campo contiene l'ID del dispositivo ed è uguale all'ID *campo** nelle informazioni sui dispositivi. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
