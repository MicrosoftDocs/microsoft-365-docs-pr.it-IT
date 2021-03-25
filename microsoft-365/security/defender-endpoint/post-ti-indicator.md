---
title: API per l'invio o l'aggiornamento degli indicatori
description: Scopri come usare l'API Invia o Aggiorna indicatore per inviare o aggiornare una nuova entità Indicatore in Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, inviare, ti, indicatore, aggiornamento
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187256"
---
# <a name="submit-or-update-indicator-api"></a>API per l'invio o l'aggiornamento degli indicatori

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API
Invia o aggiorna la nuova [entità Indicatore.](ti-indicator.md)
<br>La notazione CIDR per gli IP non è supportata.

## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.
2. Esiste un limite di 15.000 indicatori attivi per tenant. 


## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Ti.ReadWrite |  "Indicatori di lettura e scrittura"
Applicazione |   Ti.ReadWrite.All |  "Lettura e scrittura di tutti gli indicatori"
Delegato (account aziendale o dell'istituto di istruzione) |    Ti.ReadWrite |  "Indicatori di lettura e scrittura"


## <a name="http-request"></a>Richiesta HTTP
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | stringa | application/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta
Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:

Parametro | Tipo    | Descrizione
:---|:---|:---
indicatorValue | Stringa | Identità [dell'entità Indicator.](ti-indicator.md) **Obbligatorio**
indicatorType | Enum | Tipo dell'indicatore. I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url". **Obbligatorio**
action | Enum | Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione. I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed". **Obbligatorio**
application | Stringa | Applicazione associata all'indicatore. **Facoltativo**
title | Stringa | Titolo dell'avviso indicatore. **Obbligatorio**
descrizione | Stringa | Descrizione dell'indicatore. **Obbligatorio**
expirationTime | DateTimeOffset | Ora di scadenza dell'indicatore. **Facoltativo**
gravità | Enum | Gravità dell'indicatore. i valori possibili sono: "Informational", "Low", "Medium" e "High". **Facoltativo**
recommendedActions | Stringa | Azioni consigliate per l'avviso dell'indicatore TI. **Facoltativo**
rbacGroupNames | Stringa | Elenco delimitato da virgole di nomi di gruppi RBAC a cui verrà applicato l'indicatore. **Facoltativo**


## <a name="response"></a>Risposta
- Se ha esito positivo, questo metodo restituisce 200 - OK codice di risposta e l'entità [Indicator](ti-indicator.md) creata/aggiornata nel corpo della risposta.
- In caso di esito negativo: questo metodo restituisce 400 - Richiesta non valida. La richiesta non valida in genere indica un corpo errato.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Argomento correlato
- [Gestire gli indicatori](manage-indicators.md)
