---
title: API Per ottenere statistiche IP
description: Ottieni le statistiche più recenti per il tuo IP usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, ip, statistiche, prevalenza
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 55bf10d01093c17ba2d186ce0a1d1313db2c3a75
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770086"
---
# <a name="get-ip-statistics-api"></a>API Per ottenere statistiche IP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API
Recupera le statistiche per l'IP specificato.

## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Ip.Read.All |   "Lettura dei profili degli indirizzi IP"
Delegato (account aziendale o dell'istituto di istruzione) | Ip.Read.All |  "Lettura dei profili degli indirizzi IP"

>[!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)

## <a name="http-request"></a>Richiesta HTTP

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-uri-parameters"></a>Parametri URI di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
lookBackHours | Int32 | Definisce le ore di ricerca per ottenere le statistiche. Il valore predefinito è 30 giorni. **Facoltativo**.

## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo e ip esiste - 200 OK con dati statistici nel corpo. IP non esistente - 404 Non trovato.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**Risposta**

Ecco un esempio di risposta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| Nome | Descrizione |
| :--- | :---------- |
| Prevalenza dell'organizzazione | il conteggio distinto dei dispositivi che hanno aperto la connessione di rete a questo IP. |
| Org first seen | la prima connessione per questo INDIRIZZO IP nell'organizzazione. |
| Org last seen  | l'ultima connessione per questo INDIRIZZO IP nell'organizzazione. |

> [!NOTE]
> Queste informazioni statistiche si basano sui dati degli ultimi 30 giorni. 
