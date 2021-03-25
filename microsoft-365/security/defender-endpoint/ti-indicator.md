---
title: Tipo di risorsa indicatore
description: Specifica i dettagli dell'entità e definisci la scadenza dell'indicatore usando Microsoft Defender per Endpoint.
keywords: api, api supportate, get, TiIndicator, Indicatore, recente
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187208"
---
# <a name="indicator-resource-type"></a>Tipo di risorsa indicatore

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Vedere la [pagina Indicatori corrispondente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) nel portale. 

Metodo|Tipo restituito |Descrizione
:---|:---|:---
[Indicatori elenco](get-ti-indicators-collection.md) | [Indicatore](ti-indicator.md) Raccolta | Entità [indicatore](ti-indicator.md) elenco.
[Indicatore di invio](post-ti-indicator.md) | [Indicatore](ti-indicator.md) | Inviare o aggiornare [l'entità Indicatore.](ti-indicator.md)
[Indicatori di importazione](import-ti-indicators.md) | [Indicatore](ti-indicator.md) Raccolta | Inviare o aggiornare [entità](ti-indicator.md) Indicatori.
[Elimina indicatore](delete-ti-indicator-by-id.md) | Nessun contenuto | Elimina [l'entità Indicatore.](ti-indicator.md)


## <a name="properties"></a>Proprietà
Proprietà |  Tipo    |   Descrizione
:---|:---|:---
id | Stringa | Identità [dell'entità Indicator.](ti-indicator.md)
indicatorValue | Stringa | Valore dell'oggetto [Indicator.](ti-indicator.md)
indicatorType | Enum | Tipo dell'indicatore. I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".
application | Stringa | Applicazione associata all'indicatore. 
action | Enum | Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione. I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed".
sourceType | Enum | "Utente" nel caso in cui l'indicatore creato da un utente (ad esempio dal portale), "AadApp" nel caso in cui sia stato inviato utilizzando l'applicazione automatizzata tramite l'API.
source | stringa | Nome dell'utente/applicazione che ha inviato l'indicatore.
createdBy | Stringa | Identità univoca dell'utente/applicazione che ha inviato l'indicatore.
lastUpdatedBy | Stringa | Identità dell'utente/applicazione che ha aggiornato l'indicatore per l'ultima volta.
creationTimeDateTimeUtc | DateTimeOffset | Data e ora di creazione dell'indicatore.
expirationTime | DateTimeOffset | Ora di scadenza dell'indicatore.
lastUpdateTime | DateTimeOffset | L'ultima volta che l'indicatore è stato aggiornato.
gravità | Enum | Gravità dell'indicatore. i valori possibili sono: "Informational", "Low", "Medium" e "High".
title | Stringa | Titolo indicatore.
descrizione | Stringa | Descrizione dell'indicatore.
recommendedActions | Stringa | Azioni consigliate per l'indicatore.
rbacGroupNames | Elenco di stringhe | Nomi dei gruppi di dispositivi RBAC in cui l'indicatore è esposto e attivo. Elenco vuoto nel caso in cui sia esposto a tutti i dispositivi.


## <a name="json-representation"></a>Rappresentazione Json

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
