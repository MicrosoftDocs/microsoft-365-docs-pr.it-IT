---
title: API di caccia avanzata Microsoft 365 Defender
description: Informazioni su come eseguire query di caccia avanzate utilizzando l'API di caccia avanzata di Microsoft 365 Defender
keywords: Advanced Hunting, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988117"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API di caccia avanzata Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

[Advanced Hunting](advanced-hunting-overview.md) è uno strumento di ricerca di minacce che utilizza [query appositamente costruite](advanced-hunting-query-language.md) per esaminare gli ultimi 30 giorni di dati degli eventi in Microsoft 365 Defender. È possibile utilizzare le query di ricerca avanzate per ispezionare attività inusuali, individuare possibili minacce e persino rispondere agli attacchi. L'API di ricerca avanzata consente di programatically i dati degli eventi di query.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

Le seguenti condizioni si riferiscono a tutte le query.

1. Le query esplorano e restituiscono dati degli ultimi 30 giorni.
2. I risultati possono restituire fino a 100.000 righe.
3. È possibile effettuare fino a 15 chiamate al minuto per tenant.
4. Si dispone di 10 minuti di tempo di esecuzione per ora per tenant.
5. Si dispone di quattro ore totali di tempo di esecuzione al giorno per tenant.
6. Se si esegue una singola richiesta per più di 10 minuti, il timeout e la restituzione di un errore.
7. Un `429` codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato. Leggere il corpo della risposta per comprendere il limite raggiunto. 

> [!NOTE]
> Tutte le quote sopra elencate (ad esempio 15 chiamate al minuto) sono per dimensione tenant. Queste quote sono minime.

## <a name="permissions"></a>Autorizzazioni

È necessaria una delle autorizzazioni seguenti per chiamare l'API di caccia avanzata. Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Protection Apis](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato per le autorizzazioni
-|-|-
Applicazione | AdvancedHunting. Read. All | Eseguire query avanzate
Delegati (account aziendale o dell'Istituto di istruzione) | AdvancedHunting. Read | Eseguire query avanzate

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>
>- L'utente deve disporre del ruolo di annuncio ' Visualizza dati '
>- L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Intestazioni di richiesta

Intestazione | Valore
-|-
Autorizzazione | Portatore {token} **Note: required**
Content-Type | applicazione/JSON

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:

Parametro | Tipo | Descrizione
-|-|-
Query | Testo | La query da eseguire. **Nota: obbligatoria**

## <a name="response"></a>Risposta

Se l'operazione ha esito positivo, il metodo restituirà `200 OK` un oggetto _QueryResponse_ nel corpo della risposta.

L'oggetto Response contiene tre proprietà di primo livello:

1. Stats-un dizionario delle statistiche delle prestazioni delle query.
2. Schema: lo schema della risposta, un elenco di Name-Type coppie per ogni colonna.
3. Results-un elenco di eventi di caccia avanzati.

## <a name="example"></a>Esempio

Nell'esempio seguente, un utente invia la query in basso e riceve un oggetto Response API contenente `Stats` , `Schema` e `Results` .

### <a name="query"></a>Query

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Oggetto Response

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

## <a name="related-articles"></a>Articoli correlati

- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Informazioni sui codici di errore](api-error-codes.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
