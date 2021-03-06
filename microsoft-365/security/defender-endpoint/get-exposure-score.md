---
title: Ottenere punteggio di esposizione
description: Recupera il punteggio di esposizione dell'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, punteggio di esposizione, punteggio di esposizione dell'organizzazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845391"
---
# <a name="get-exposure-score"></a>Ottenere punteggio di esposizione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera il punteggio di esposizione dell'organizzazione.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | Score.Read.All | "Read Threat and Vulnerability Management score"
Delegato (account aziendale o dell'istituto di istruzione) | Score.Read | "Read Threat and Vulnerability Management score"

## <a name="http-request"></a>Richiesta HTTP

```
GET /api/exposureScore
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK, con i dati di esposizione nel corpo della risposta.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Risposta

Ecco un esempio di risposta.

>[!NOTE]
>L'elenco delle risposte mostrato qui potrebbe essere troncato per brevità. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>Vedere anche

- [Gestione delle vulnerabilità basata sui rischi & rischio](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Punteggio di esposizione & rischio di vulnerabilità](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
