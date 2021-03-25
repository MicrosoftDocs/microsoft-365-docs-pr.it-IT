---
title: API indicatore di eliminazione.
description: Scopri come usare l'API dell'indicatore di eliminazione per eliminare un'entità Indicatore in base all'ID in Microsoft Defender per Endpoint.
keywords: api, api pubbliche, api supportate, eliminare, indicatore ti, entità, id
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
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167105"
---
# <a name="delete-indicator-api"></a>API indicatore di eliminazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Elimina [un'entità Indicator](ti-indicator.md) in base all'ID.


## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Ti.ReadWrite |  "Indicatori TI di lettura e scrittura"
Applicazione |   Ti.ReadWrite.All |  "Indicatori di lettura e scrittura"


## <a name="http-request"></a>Richiesta HTTP
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
If Indicator exist and deleted successfully - 204 OK without content.
Se l'indicatore con l'ID specificato non è stato trovato - 404 Non trovato.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
