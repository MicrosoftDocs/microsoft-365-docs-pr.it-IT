---
title: API per l'impostazione del valore del dispositivo
description: Scopri come specificare il valore di un dispositivo usando un'API di Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, tag, tag del computer
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e14e696169a2d1cd76e4fb5b2ee8de951e9e1280
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771408"
---
# <a name="set-device-value-api"></a>API per l'impostazione del valore del dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API

Imposta il valore del dispositivo di un computer [specifico.](machine.md)<br>
Per [altre informazioni, vedi assegnare](tvm-assign-device-value.md) i valori dei dispositivi.

## <a name="limitations"></a>Limitazioni

1. Puoi pubblicare nei dispositivi l'ultima volta che hai visto in base al periodo di conservazione configurato.

2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |    Autorizzazione    |    Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |    Machine.ReadWrite.All |    "Leggere e scrivere tutte le informazioni sul computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.ReadWrite | "Leggere e scrivere informazioni sul computer"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Gestisci impostazione di sicurezza". Per ulteriori informazioni, vedere [Creare e gestire ruoli.](user-roles.md)
>- L'utente deve avere accesso al computer in base alle impostazioni del gruppo di computer (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di computer)

## <a name="http-request"></a>Richiesta HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | stringa | application/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:

Parametro |    Tipo    | Descrizione
:---|:---|:---
DeviceValue |    Enum |    Valore del dispositivo. I valori consentiti sono: 'Normal', 'Low' e 'High'. **Obbligatorio**.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 - Ok codice di risposta e computer aggiornato nel corpo della risposta.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio di richiesta che aggiunge tag computer.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
