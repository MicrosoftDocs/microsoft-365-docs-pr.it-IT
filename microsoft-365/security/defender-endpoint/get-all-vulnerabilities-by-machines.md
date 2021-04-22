---
title: Ottenere tutte le vulnerabilità dal computer e dal software
description: Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione in base al computer e al software
keywords: api, api del grafico, api supportate, ottenere, informazioni sulla vulnerabilità, Api di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933410"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>Elencare le vulnerabilità per computer e software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione per [computer](machine.md) e [software.](software.md)
- Se la vulnerabilità ha un KB di correzione, verrà visualizzata nella risposta.
- Supporta le [query OData V4.](https://www.odata.org/documentation/)
- OData ```$filter``` è supportato in tutte le proprietà.

>[!Tip]
>Si tratta di un'API ideale per [l'integrazione di Power BI.](api-power-bi.md)

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Vulnerability.Read.All |    "Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"
Delegato (account aziendale o dell'istituto di istruzione) | Vulnerability.Read |   "Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"

## <a name="http-request"></a>Richiesta HTTP
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco delle vulnerabilità nel corpo.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

**Risposta**

Ecco un esempio di risposta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>Vedere anche

- [Gestione delle minacce e delle vulnerabilità basate sui rischi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Vulnerabilità nell'organizzazione](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
