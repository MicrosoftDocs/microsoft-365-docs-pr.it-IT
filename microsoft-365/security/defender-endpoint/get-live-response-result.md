---
title: Ottenere risultati di risposta in tempo reale
description: Informazioni su come recuperare un risultato del comando di risposta in tempo reale specifico in base al relativo indice.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879731"
---
#  <a name="get-live-response-results"></a>Ottenere risultati di risposta in tempo reale

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API

Recupera un risultato del comando di risposta in tempo reale specifico in base al relativo indice.

## <a name="limitations"></a>Limitazioni

1.  I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione.](apis-intro.md)

| Tipo di autorizzazione                    | Autorizzazione           | Nome visualizzato autorizzazione                   |
|------------------------------------|----------------------|-------------------------------------------|
| Applicazione                        | Machine.LiveResponse | Eseguire la risposta in tempo reale in un computer specifico |
| Delegato (account aziendale o dell'istituto di istruzione) | Machine.LiveResponse | Eseguire la risposta in tempo reale in un computer specifico |

## <a name="http-request"></a>Richiesta HTTP

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Intestazioni di richiesta

| Name      | Tipo | Descrizione               |
|---------------|----------|-------------------------------|
| Autorizzazione | Stringa   | Bearer {token}. Obbligatorio. |

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce il codice di risposta 200 Ok con l'oggetto che contiene il collegamento al comando che restituisce la *proprietà value.* Questo collegamento è valido per 30 minuti e deve essere usato immediatamente per scaricare il pacchetto in un archivio locale. Un collegamento scaduto può essere ri-creato da un'altra chiamata e non è necessario eseguire di nuovo la risposta in tempo reale.

*Proprietà trascrizione Runscript:*

| Proprietà  | Descrizione                       |
|---------------|---------------------------------------|
| name          | Nome script eseguito                  |
| exit_code     | Codice di uscita script eseguito             |
| script_output | Output standard dello script eseguito       |
| script_error  | Output degli errori standard dello script eseguito |

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Risposta**

Ecco un esempio di risposta.

HTTP/1.1 200 Ok

Content-type: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Contenuto file:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Argomenti correlati

- [API per l'azione del computer](get-machineaction-object.md)
- [Annullare l'azione del computer](cancel-machine-action.md)
- [Esegui risposta in tempo reale](run-live-response.md) 
