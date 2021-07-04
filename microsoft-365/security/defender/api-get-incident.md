---
title: API per ottenere eventi imprevisti
description: Scopri come usare l'API Get incidents per ottenere un singolo evento imprevisto in Microsoft 365 Defender.
keywords: api, api del grafico, api supportate, get, file, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289608"
---
# <a name="get-incident-information-api"></a>API per ottenere informazioni sugli eventi imprevisti

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API

Recupera un evento imprevisto specifico in base al relativo ID

## <a name="limitations"></a>Limitazioni

1. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. 

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | Incident.Read.All | "Leggi tutti gli eventi imprevisti"
Applicazione | Incident.ReadWrite.All | "Lettura e scrittura di tutti gli eventi imprevisti"
Delegato (account aziendale o dell'istituto di istruzione) | Incident.Read | "Operazioni non consentite di lettura"
Delegato (account aziendale o dell'istituto di istruzione) | Incident.ReadWrite | "Eventi imprevisti di lettura e scrittura"

> [!NOTE]
>
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati'
> - La risposta includerà solo gli eventi imprevisti a cui l'utente è esposto

## <a name="http-request"></a>Richiesta HTTP

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK e l'entità evento imprevisto nel corpo della risposta. Se non è stato trovato un evento imprevisto con l'ID specificato - 404 Non trovato.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
