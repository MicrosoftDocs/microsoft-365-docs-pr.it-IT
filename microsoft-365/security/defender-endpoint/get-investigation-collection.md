---
title: List Investigations API
description: Usa questa API per creare chiamate correlate al get investigations collection
keywords: api, api del grafico, api supportate, raccolta Investigations
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
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167117"
---
# <a name="list-investigations-api"></a>List Investigations API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Recupera un insieme [di oggetti Investigations.](investigation.md)
<br>Supporta le [query OData V4.](https://www.odata.org/documentation/)
<br>La query di OData ```$filter``` è supportata su: ```startTime``` , e sulle ```state``` ```machineId``` ```triggeringAlertId``` proprietà.
<br>Vedi esempi in [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Limitazioni
1. Le dimensioni massime della pagina sono 10.000.
2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora. 


## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Alert.Read.All |    "Leggi tutti gli avvisi"
Applicazione |   Alert.ReadWrite.All |   "Lettura e scrittura di tutti gli avvisi"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.Read | "Avvisi di lettura"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.ReadWrite | "Avvisi di lettura e scrittura"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)

## <a name="http-request"></a>Richiesta HTTP
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con una raccolta [di entità Investigations.](investigation.md)


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio di richiesta di ottenere tutte le indagini: 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

**Risposta**

Ecco un esempio di risposta:

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
