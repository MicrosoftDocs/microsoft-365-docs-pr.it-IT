---
title: Rilevazione avanzata API
ms.reviewer: ''
description: Scopri come usare l'API di ricerca avanzata per eseguire query avanzate in Microsoft Defender per Endpoint. Scopri le limitazioni e vedi un esempio.
keywords: api, api supportate, ricerca avanzata, query
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
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604370"
---
# <a name="advanced-hunting-api"></a>API di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Limitazioni

1. È possibile eseguire una query solo sui dati degli ultimi 30 giorni.

2. I risultati includeranno un massimo di 100.000 righe.

3. Il numero di esecuzioni è limitato per tenant:
   - Chiamate API: fino a 45 chiamate al minuto, fino a 1500 chiamate all'ora.
   - Tempo di esecuzione: 10 minuti di tempo di esecuzione ogni ora e 3 ore di esecuzione al giorno.

4. Il tempo massimo di esecuzione di una singola richiesta è di 10 minuti.

5. La risposta 429 rappresenterà il raggiungimento del limite di quota in base al numero di richieste o alla CPU. Leggere il corpo della risposta per comprendere quale limite è stato raggiunto. 

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   AdvancedQuery.Read.All |    "Esegui query avanzate"
Delegato (account aziendale o dell'istituto di istruzione) | AdvancedQuery.Read | "Esegui query avanzate"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve avere il ruolo AD "Visualizza dati"
>- L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Intestazioni di richiesta

Intestazione | Valore 
:---|:---
Autorizzazione | Bearer {token}. **Obbligatorio**.
Content-Type    | application/json

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:

Parametro | Tipo    | Descrizione
:---|:---|:---
Query | Testo |  Query da eseguire. **Obbligatorio**.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK e _l'oggetto QueryResponse_ nel corpo della risposta.


## <a name="example"></a>Esempio

##### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a>Risposta

Ecco un esempio di risposta.

>[!NOTE]
>L'oggetto risposta mostrato qui potrebbe essere troncato per brevità. Tutte le proprietà verranno restituite da una chiamata effettiva.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione alle API di Microsoft Defender per endpoint](apis-intro.md)
- [Ricerca avanzata dal portale](advanced-hunting-query-language.md)
- [Rilevazione avanzata con PowerShell](run-advanced-query-sample-powershell.md)
