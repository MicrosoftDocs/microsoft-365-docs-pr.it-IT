---
title: API di ricerca avanzata di Microsoft 365 Defender
description: Informazioni su come eseguire query di ricerca avanzata con l'API di ricerca avanzata di Microsoft 365 Defender
keywords: Advanced Hunting, APIs, api, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932083"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API di ricerca avanzata di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

[La ricerca](advanced-hunting-overview.md) avanzata è uno [](advanced-hunting-query-language.md) strumento di ricerca delle minacce che usa query appositamente costruite per esaminare i dati degli eventi degli ultimi 30 giorni in Microsoft 365 Defender. È possibile utilizzare query di ricerca avanzate per esaminare attività insolite, rilevare possibili minacce e persino rispondere agli attacchi. L'API di ricerca avanzata consente di eseguire query a livello di codice sui dati degli eventi.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

Le condizioni seguenti sono correlate a tutte le query.

1. Le query esplorano e restituiscono i dati degli ultimi 30 giorni.
2. I risultati possono restituire fino a 100.000 righe.
3. È possibile effettuare fino a 10 chiamate al minuto per ogni tenant.
4. Hai 10 minuti di tempo di esecuzione all'ora per ogni tenant.
5. Hai quattro ore totali di tempo di esecuzione per ogni tenant.
6. Se una singola richiesta viene eseguita per più di 10 minuti, si verifica il timeout e viene restituito un errore.
7. Un codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato. Il corpo della risposta includerà il tempo fino al ripristino della quota raggiunta.

## <a name="permissions"></a>Autorizzazioni

Una delle autorizzazioni seguenti è necessaria per chiamare l'API di ricerca avanzata. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedere Accedere alle API di [Microsoft 365 Defender Protection](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazioni
-|-|-
Applicazione | AdvancedHunting.Read.All | Eseguire query avanzate
Delegato (account aziendale o dell'istituto di istruzione) | AdvancedHunting.Read | Eseguire query avanzate

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>
>- L'utente deve avere il ruolo ad "Visualizza dati"
>- L'utente deve avere accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Intestazioni di richiesta

Intestazione | Valore
-|-
Autorizzazione | Bearer {token} **Nota: obbligatorio**
Content-Type | application/json

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:

Parametro | Tipo | Descrizione
-|-|-
Query | Testo | Query da eseguire. **Nota: obbligatorio**

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituirà `200 OK` e un _oggetto QueryResponse_ nel corpo della risposta.

L'oggetto risposta contiene tre proprietà di primo livello:

1. Statistiche - Dizionario di statistiche sulle prestazioni delle query.
2. Schema: lo schema della risposta, un elenco di coppie Name-Type per ogni colonna.
3. Risultati - Elenco di eventi di ricerca avanzata.

## <a name="example"></a>Esempio

Nell'esempio seguente un utente invia la query seguente e riceve un oggetto risposta API contenente `Stats` `Schema` , e `Results` .

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
- [Comprendere i codici di errore](api-error-codes.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
