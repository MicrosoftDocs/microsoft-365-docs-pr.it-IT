---
title: Eseguire comandi di risposta in tempo reale in un dispositivo
description: Scopri come eseguire una sequenza di comandi di risposta in tempo reale in un dispositivo.
keywords: api, api del grafico, api supportate, caricamento nella raccolta
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879701"
---
#  <a name="run-live-response-commands-on-a-device"></a>Eseguire comandi di risposta in tempo reale in un dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API

Esegue una sequenza di comandi di risposta in tempo reale in un dispositivo

## <a name="limitations"></a>Limitazioni

1.  I limiti di frequenza per questa API sono 10 chiamate al minuto (le richieste aggiuntive vengono inviate con HTTP 429).

2.  25 sessioni in esecuzione contemporaneamente (le richieste che superano il limite di limitazione riceveranno una risposta "429 - Troppe richieste").

3.  Se il computer non è disponibile, la sessione verrà accodata per un massimo di 3 giorni.

4.  Timeout del comando RunScript dopo 10 minuti.

5.  Quando un comando di risposta in tempo reale ha esito negativo, tutte le azioni seguite non verranno eseguite.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)

| Tipo di autorizzazione                    | Autorizzazione           | Nome visualizzato autorizzazione                   |
|------------------------------------|----------------------|-------------------------------------------|
| Applicazione                        | Machine.LiveResponse | Eseguire la risposta in tempo reale in un computer specifico |
| Delegato (account aziendale o dell'istituto di istruzione) | Machine.LiveResponse | Eseguire la risposta in tempo reale in un computer specifico |

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Intestazioni di richiesta

| Name      | Tipo | Descrizione                 |
|---------------|----------|---------------------------------|
| Autorizzazione | Stringa   | Bearer\<token>\. Obbligatorio.   |
| Content-Type  | stringa   | application/json. Obbligatorio. |

## <a name="request-body"></a>Corpo della richiesta

| Parametro | Tipo | Descrizione                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Comment       | Stringa   | Commento da associare all'azione.                                 |
| Comandi      | Array    | Comandi da eseguire. I valori consentiti sono PutFile, RunScript, GetFile. |

Comandi:

| Tipo di comando | Parametri                                                                          | Descrizione                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Chiave: FileName  <br><br>  Valore: \<file name\>                                                                          | Inserisce un file dalla raccolta al dispositivo. I file vengono salvati in una cartella di lavoro e vengono eliminati al riavvio del dispositivo per impostazione predefinita.
| RunScript    | Chiave: ScriptName<br>Valore: \<Script from library\> <br><br> Key: Args  <br> Valore: \<Script arguments\>                          | Esegue uno script dalla raccolta in un dispositivo.    <br><br>  Il parametro Args viene passato allo script. <br><br> Timeout dopo 10 minuti.     
| GetFile      | Chiave: Path <br> Valore: \<File path\>                                                        | Raccogliere file da un dispositivo. NOTA: le barre rovesciate nel percorso devono essere precedute da caratteri di escape.                                                                      |

## <a name="response"></a>Risposta

-   Se ha esito positivo, questo metodo restituisce 200, Ok.
    Entità Azione. Se il computer con l'ID specificato non è stato trovato - 404 Non trovato.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Risposta**

Ecco un esempio di risposta.

```HTTP
HTTP/1.1 200 Ok
```

Content-type: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Argomenti correlati
- [API per l'azione del computer](get-machineaction-object.md)
- [Ottenere il risultato della risposta in tempo reale](get-live-response-result.md)
- [Annullare l'azione del computer](cancel-machine-action.md)
