---
title: API per arrestare e mettere in quarantena i file
description: Scopri come interrompere l'esecuzione di un file in un dispositivo ed eliminare il file in Microsoft Defender per Endpoint. Vedi un esempio.
keywords: api, api del grafico, api supportate, file di arresto e quarantena
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771407"
---
# <a name="stop-and-quarantine-file-api"></a>API per arrestare e mettere in quarantena i file

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Interrompere l'esecuzione di un file in un dispositivo ed eliminarlo.


## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Machine.StopAndQuarantine | "Interrompi e metti in quarantena"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.StopAndQuarantine | "Interrompi e metti in quarantena"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Azioni di correzione attive" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
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
Sha1 |  Stringa   | Sha1 del file da arrestare e mettere in quarantena nel dispositivo. **Obbligatorio**.

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce 201 - Codice di risposta creato e [Azione del](machineaction.md) computer nel corpo della risposta.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
