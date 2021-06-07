---
title: API Per aggiungere o rimuovere tag computer
description: Scopri come usare l'API Add or Remove machine tags per aggiungere o rimuovere un tag per un computer in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, tag, tag del computer
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769822"
---
# <a name="add-or-remove-machine-tags-api"></a>API Per aggiungere o rimuovere tag computer

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API

Aggiunge o rimuove tag a un computer [specifico.](machine.md)

## <a name="limitations"></a>Limitazioni

1. È possibile pubblicare nei computer l'ultima volta che si è visto in base al periodo di conservazione configurato.

2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, incluso come scegliere le autorizzazioni, vedi [Usare Defender per le API endpoint](apis-intro.md)

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
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
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
Valore |    Stringa |    Nome del tag. **Obbligatorio**.
Azione    | Enum |    Aggiungi o Rimuovi. I valori consentiti sono: 'Add' o 'Remove'. **Obbligatorio**.


## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 - Ok codice di risposta e computer aggiornato nel corpo della risposta.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio di richiesta che aggiunge tag computer.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Per rimuovere il tag machine, imposta Action su 'Remove' invece di 'Add' nel corpo della richiesta.
