---
title: API per ottenere avvisi correlati al computer
description: Scopri come usare l'API Ottieni avvisi correlati al computer per recuperare tutti gli avvisi relativi a un dispositivo specifico in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivi, correlati, avvisi
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199252"
---
# <a name="get-machine-related-alerts--api"></a>API per ottenere avvisi correlati al computer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API
Recupera tutti gli [avvisi](alerts.md) correlati a un dispositivo specifico.


## <a name="limitations"></a>Limitazioni
1. È possibile eseguire query sui dispositivi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.
2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Alert.Read.All |    "Leggi tutti gli avvisi"
Applicazione |   Alert.ReadWrite.All |   "Lettura e scrittura di tutti gli avvisi"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.Read | "Avvisi di lettura"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.ReadWrite | "Avvisi di lettura e scrittura"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Vuoto

## <a name="response"></a>Risposta
Se l'operazione ha esito positivo e [](alerts.md) il dispositivo esiste: 200 OK con l'elenco delle entità di avviso nel corpo. Se il dispositivo non è stato trovato - 404 Non trovato.
