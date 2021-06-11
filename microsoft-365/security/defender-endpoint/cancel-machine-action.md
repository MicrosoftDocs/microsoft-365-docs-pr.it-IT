---
title: API annulla azione computer
description: Informazioni su come annullare un'azione del computer già avviata
keywords: api, api del grafico,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879756"
---
#   <a name="cancel-machine-action-api"></a>API annulla azione computer 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API

Annullare un'azione del computer già avviata che non è ancora in stato finale (completata, annullata, non riuscita).

## <a name="limitations"></a>Limitazioni

1.  I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)

|     Tipo di autorizzazione     |     Autorizzazione     |    Nome visualizzato autorizzazione     |
|-|-|-|
|    <br>Applicazione    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Raccogliere dati forensi   <br>Isola computer<br>Limitare l'esecuzione del codice<br>  Computer di analisi<br>  Computer offboard<br>   Interrompi e metti in quarantena<br>   Eseguire la risposta in tempo reale in un computer specifico    |
|    <br>Delegato (account aziendale o dell'istituto di istruzione)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Raccogliere dati forensi<br>   Isola computer<br>  Limitare l'esecuzione del codice<br> Computer di analisi<br>Computer offboard<br> Interrompi e metti in quarantena<br> Eseguire la risposta in tempo reale in un computer specifico    |


## <a name="http-request"></a>Richiesta HTTP

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Intestazioni di richiesta

| Name      | Tipo | Descrizione                 |
|---------------|----------|---------------------------------|
| Autorizzazione | Stringa   | Bearer {token}. Obbligatorio.   |
| Content-Type  | stringa   | application/json. Obbligatorio. |

## <a name="request-body"></a>Corpo della richiesta

| Parametro | Tipo | Descrizione                        |
|---------------|----------|----------------------------------------|
| Comment       | Stringa   | Commento da associare all'azione di annullamento.  |

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con un'entità Machine Action. Se l'entità azione del computer con l'ID specificato non è stata trovata - 404 Non trovato.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Argomento correlato

- [API per l'azione del computer](get-machineaction-object.md)