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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289920"
---
# <a name="delete-indicator-api"></a>API indicatore di eliminazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API

Elimina [un'entità Indicator](ti-indicator.md) in base all'ID.

## <a name="limitations"></a>Limitazioni

I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | Ti.ReadWrite | "Indicatori TI di lettura e scrittura"
Applicazione | Ti.ReadWrite.All | "Indicatori di lettura e scrittura"

## <a name="http-request"></a>Richiesta HTTP

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

If Indicator exist and deleted successfully - 204 OK without content.

Se l'indicatore con l'ID specificato non è stato trovato - 404 Non trovato.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
