---
title: Rimuovere l'API di restrizione dell'app
description: Usa questa API per creare chiamate correlate alla rimozione di una restrizione dall'esecuzione delle applicazioni.
keywords: api, api del grafico, api supportate, rimuovere il dispositivo dall'isolamento
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
ms.openlocfilehash: abff4e02bfdfe6f5598ca96121815930dce3c85e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199322"
---
# <a name="remove-app-restriction-api"></a>Rimuovere l'API di restrizione dell'app

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Abilita l'esecuzione di qualsiasi applicazione nel dispositivo.


## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Machine.RestrictExecution | "Limita l'esecuzione del codice"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.RestrictExecution | "Limita l'esecuzione del codice"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
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
Comment |   Stringa | Commento da associare all'azione. **Obbligatorio**.

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


Per limitare l'esecuzione di codice in un dispositivo, vedi [Limitare l'esecuzione di app.](restrict-code-execution.md)
