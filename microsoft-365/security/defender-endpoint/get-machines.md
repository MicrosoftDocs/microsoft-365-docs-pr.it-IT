---
title: List machines API
description: Scopri come usare l'API List machines per recuperare una raccolta di computer che hanno comunicato con il cloud Microsoft Defender ATP.
keywords: api, api del grafico, api supportate, get, dispositivi
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200378"
---
# <a name="list-machines-api"></a>List machines API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API
Recupera una raccolta di [computer](machine.md) che hanno comunicato con Microsoft Defender for Endpoint cloud.
<br>Supporta le [query OData V4.](https://www.odata.org/documentation/)
<br>La query di OData `$filter` è supportata in: `computerDnsName` , , , e `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>Vedi esempi in [Query OData con Defender for Endpoint](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Limitazioni
1. È possibile visualizzare i dispositivi per l'ultima volta in base al periodo di conservazione configurato.
2. Le dimensioni massime della pagina sono 10.000.
3. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora. 


## <a name="permissions"></a>Autorizzazioni

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Machine.Read.All |  "Leggi tutti i profili computer"
Applicazione |   Machine.ReadWrite.All | "Leggere e scrivere tutte le informazioni sul computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.Read | "Leggere le informazioni sul computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.ReadWrite | "Leggere e scrivere informazioni sul computer"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- La risposta includerà solo i dispositivi a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo e i computer [](machine.md) esistono: 200 OK con l'elenco delle entità del computer nel corpo. Se nessun computer recente - 404 Non trovato.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Risposta**

Ecco un esempio di risposta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Argomenti correlati
- [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)
