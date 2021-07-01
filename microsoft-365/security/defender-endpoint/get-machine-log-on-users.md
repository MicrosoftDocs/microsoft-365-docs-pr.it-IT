---
title: API Per ottenere gli utenti di accesso al computer
description: Scopri come usare l'API Get machine logon users per recuperare una raccolta di utenti connessi in un dispositivo in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivo, accesso, utenti
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229024"
---
# <a name="get-machine-logon-users-api"></a>API Per ottenere gli utenti di accesso al computer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Recupera una raccolta di utenti connessi in un dispositivo specifico.

## <a name="limitations"></a>Limitazioni
1. È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.
2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |Autorizzazione|Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |User.Read.All |"Lettura profili utente"
Delegato (account aziendale o dell'istituto di istruzione) | User.Read.All | "Lettura profili utente"

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Visualizza dati". Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).
> - La risposta includerà gli utenti solo se il dispositivo è visibile all'utente, in base alle impostazioni del gruppo di dispositivi. Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)

## <a name="http-request"></a>Richiesta HTTP

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se l'operazione ha esito positivo e [](user.md) il dispositivo esiste: 200 OK con l'elenco delle entità utente nel corpo. Se il dispositivo non è stato trovato - 404 Non trovato.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>Risposta

Ecco un esempio di risposta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
