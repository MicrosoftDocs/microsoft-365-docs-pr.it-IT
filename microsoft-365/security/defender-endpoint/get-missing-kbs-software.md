---
title: Ottenere gli indicatori KPI mancanti in base all'ID software
description: Recupera gli aggiornamenti della sicurezza mancanti in base all'ID software
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, ID software, api di gestione delle minacce & vulnerabilità, Api di Microsoft Defender per Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 25ac8ce2c9fb17b2576f86dae1da984865b19018
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933890"
---
# <a name="get-missing-kbs-by-software-id"></a>Ottenere gli indicatori KPI mancanti in base all'ID software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera gli indicatori KPI mancanti (aggiornamenti della sicurezza) in base all'ID software

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.

Tipo di autorizzazione |   Autorizzazione   |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |Software.Read.All |   "Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"
Delegato (account aziendale o dell'istituto di istruzione) | Software.Read |   "Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"

## <a name="http-request"></a>Richiesta HTTP

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a>Intestazione della richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK, con i dati kb mancanti del software specificato nel corpo.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a>Risposta

Ecco un esempio di risposta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestione delle vulnerabilità basata sui rischi & rischio](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Threat & Vulnerability software inventory](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
