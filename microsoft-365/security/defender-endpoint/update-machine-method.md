---
title: API dell'entità computer di aggiornamento
description: Scopri come aggiornare i tag del computer usando questa API. Puoi aggiornare i tag e le proprietà devicevalue.
keywords: api, api del grafico, api supportate, ottenere, avviso, informazioni, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985752"
---
# <a name="update-machine"></a>Aggiorna computer 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Aggiorna le proprietà del computer [esistente.](machine.md)
<br>Le proprietà aggiornabili sono: ```machineTags``` e ```deviceValue``` .


## <a name="limitations"></a>Limitazioni
1. Puoi aggiornare i computer disponibili nell'API. 
2. Il computer di aggiornamento aggiunge solo tag alla raccolta di tag. Se i tag esistono, devono essere inclusi nell'insieme tags nel corpo.
3. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Machine.ReadWrite.All | "Leggere e scrivere informazioni sul computer per tutti i computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.ReadWrite | "Leggere e scrivere informazioni sul computer"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Avvisi indagine". Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).
>- L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi. Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)

## <a name="http-request"></a>Richiesta HTTP
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | Stringa | application/json. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Nel corpo della richiesta specificare i valori per i campi rilevanti da aggiornare.
<br>Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà. 
<br>Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificate.

Proprietà | Tipo | Descrizione
:---|:---|:---
machineTags | Insieme String | Set di [tag del](machine.md) computer.
deviceValue | Enumerazione Nullable | Valore [del dispositivo](tvm-assign-device-value.md). I valori possibili sono: 'Normal', 'Low' e 'High'.

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce [](machine.md) 200 OK e l'entità computer nel corpo della risposta con le proprietà aggiornate. Se la raccolta di tag di computer nel corpo non contiene tag di computer esistenti- 400 Input non valido e un messaggio che informa del tag/i mancante.
Se il computer con l'ID specificato non è stato trovato - 404 Non trovato.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
