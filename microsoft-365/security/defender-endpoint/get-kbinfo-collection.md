---
title: Ottenere l'API di raccolta KB
description: Recupera una raccolta di informazioni di knowledge base (KB) e dettagli kb con Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167177"
---
# <a name="get-kb-collection-api"></a>Ottenere l'API di raccolta KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera una raccolta di dettagli di KB e KB.

## <a name="permissions"></a>Autorizzazioni
L'utente necessita delle autorizzazioni di lettura.

## <a name="http-request"></a>Richiesta HTTP
```
GET /testwdatppreview/kbinfo
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

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**Risposta**

Ecco un esempio di risposta.

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
