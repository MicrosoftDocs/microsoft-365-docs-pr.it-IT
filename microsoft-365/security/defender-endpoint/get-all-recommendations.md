---
title: Elencare tutti i consigli
description: Recupera un elenco di tutti i suggerimenti per la sicurezza che interessano l'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, suggerimenti sulla sicurezza, api di Microsoft Defender for Endpoint tvm, gestione delle minacce e delle vulnerabilità, api di gestione delle minacce e delle vulnerabilità
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0cb0a1f8a42b419db960e5097667c335bf7f7877
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935018"
---
# <a name="list-all-recommendations"></a>Elencare tutti i consigli

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera un elenco di tutti i suggerimenti per la sicurezza che interessano l'organizzazione.

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   SecurityRecommendation.Read.All |   "Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"
Delegato (account aziendale o dell'istituto di istruzione) | SecurityRecommendation.Read |  "Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"

## <a name="http-request"></a>Richiesta HTTP
```
GET /api/recommendations
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco dei suggerimenti per la sicurezza nel corpo.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

**Risposta**

Ecco un esempio di risposta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a>Vedere anche
- [Gestione delle vulnerabilità basata sui rischi & rischio](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Raccomandazione per la sicurezza & rischio di vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

