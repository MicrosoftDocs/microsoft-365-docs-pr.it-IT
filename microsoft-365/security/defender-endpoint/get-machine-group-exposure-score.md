---
title: Elencare il punteggio di esposizione per gruppo di dispositivi
description: Recupera un elenco di punteggi di esposizione per gruppo di dispositivi.
keywords: api, api del grafico, api supportate, ottenere, punteggio di esposizione, gruppo di dispositivi, punteggio di esposizione del gruppo di dispositivi
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 54b3e0cd63189e67de0aa101634508ff8833dc6a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500249"
---
# <a name="list-exposure-score-by-device-group"></a>Elencare il punteggio di esposizione per gruppo di dispositivi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera una raccolta di avvisi correlati a un determinato indirizzo di dominio.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | Score.Read.All | "Read Threat and Vulnerability Management score"
Delegato (account aziendale o dell'istituto di istruzione) | Score.Read | "Read Threat and Vulnerability Management score"

## <a name="http-request"></a>Richiesta HTTP

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Intestazioni di richiesta

| Name        | Tipo | Descrizione
|:--------------|:-------|:--------------|
| Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK, con un elenco del punteggio di esposizione per i dati del gruppo di dispositivi nel corpo della risposta.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a>Risposta

Ecco un esempio di risposta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestione delle vulnerabilità basata sui rischi & rischio](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Punteggio di esposizione & rischio di vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
