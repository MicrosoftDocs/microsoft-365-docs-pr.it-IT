---
title: API per la raccolta di gruppi di computer RBAC
description: Scopri come usare l'API Per recuperare una raccolta di gruppi di dispositivi RBAC in Microsoft Defender Advanced Threat Protection.
keywords: api, api del grafico, api supportate, get, RBAC, gruppo
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167021"
---
# <a name="get-kb-collection-api"></a>Ottenere l'API di raccolta KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Recupera una raccolta di gruppi di dispositivi RBAC.

## <a name="permissions"></a>Autorizzazioni
L'utente necessita delle autorizzazioni di lettura.

## <a name="http-request"></a>Richiesta HTTP
```
GET /testwdatppreview/machinegroups
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
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Risposta**

Ecco un esempio di risposta.
L'ID campo contiene **l'ID** del gruppo di dispositivi ed è uguale al **campo rbacGroupId** nelle informazioni sui dispositivi. Il **campo non raggruppato** è true solo per un gruppo per tutti i dispositivi che non sono stati assegnati ad alcun gruppo. Il nome di questo gruppo è "UnassignedGroup".

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
