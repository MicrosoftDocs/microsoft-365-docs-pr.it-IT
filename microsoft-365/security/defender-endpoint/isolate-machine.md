---
title: ISOLA API del computer
description: Scopri come usare l'API Isola computer per isolare un dispositivo dall'accesso alla rete esterna in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, isolare il dispositivo
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187833"
---
# <a name="isolate-machine-api"></a>ISOLA API del computer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Isola un dispositivo dall'accesso alla rete esterna.


## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Machine.Isolate |   "Isola computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.Isolate |  "Isola computer"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)


## <a name="http-request"></a>Richiesta HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
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
Comment |   Stringa |    Commento da associare all'azione. **Obbligatorio**.
IsolationType   | Stringa |  Tipo di isolamento. I valori consentiti sono: "Full" o "Selective".

**IsolationType** controlla il tipo di isolamento da eseguire e può essere uno dei seguenti:
- Completo - Isolamento completo
- Selettivo: limitare l'accesso alla rete solo a un set limitato di applicazioni (per ulteriori dettagli, vedere [Isolare](respond-machine-alerts.md#isolate-devices-from-the-network) i dispositivi dalla rete)


## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Per rilasciare un dispositivo dall'isolamento, vedi [Rilasciare il dispositivo dall'isolamento.](unisolate-machine.md)
