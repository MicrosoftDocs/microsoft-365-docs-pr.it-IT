---
title: API di caccia avanzate
description: Informazioni su come eseguire query di ricerca avanzata tramite l'API Microsoft Threat Protection
keywords: Ricerca avanzata, API, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650384"
---
# <a name="advanced-hunting-apis"></a>API di caccia avanzate

**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>Limitazioni
1. È possibile eseguire una query solo sui dati degli ultimi 30 giorni.
2. I risultati includono un massimo di 100.000 righe.
3. Il numero di esecuzioni è limitato per tenant: fino a 15 chiamate al minuto, 15 minuti di tempo di esecuzione ogni ora e 4 ore di tempo di esecuzione al giorno.
4. Il tempo di esecuzione massimo di una singola richiesta è di 10 minuti.

## <a name="permissions"></a>Autorizzazioni
Per chiamare l'API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Access the Microsoft Threat Protection Apis](api-access.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato per le autorizzazioni
:---|:---|:---
Applicazione |   AdvancedHunting. Read. All |  ' Esegui query avanzate '
Delegati (account aziendale o dell'Istituto di istruzione) | AdvancedHunting. Read | ' Esegui query avanzate '

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre del ruolo di annuncio ' Visualizza dati '
>- L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.

## <a name="http-request"></a>Richiesta HTTP
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Intestazioni di richiesta

Intestazione | Valore 
:---|:---
Autorizzazione | Portatore {token}. **Obbligatorio**.
Content-Type    | applicazione/JSON

## <a name="request-body"></a>Corpo della richiesta
Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:

Parametro | Tipo    | Descrizione
:---|:---|:---
Query | Testo |  La query da eseguire. **Obbligatorio**.

## <a name="response"></a>Risposta
Se l'operazione ha esito positivo, questo metodo restituirà 200 OK e l'oggetto _QueryResponse_ nel corpo della risposta. <br><br>

L'oggetto Response è suddiviso in tre parti (proprietà):<br>
1) ```Stats``` -Statistiche sulle prestazioni delle query.<br>
2) ```Schema``` -Lo schema della risposta, un elenco delle coppie nome-tipo per ogni colonna. <br>
3) ```Results``` -Un elenco di eventi di caccia avanzati.

## <a name="example"></a>Esempio

Richiesta

Di seguito è riportato un esempio della richiesta.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Risposta

Di seguito è riportato un esempio di risposta.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Argomento correlato
- [Accedere alle API di Microsoft Threat Protection](api-access.md)
