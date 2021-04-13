---
title: API dell'entità di avviso di aggiornamento
description: Scopri come aggiornare un avviso di Microsoft Defender per Endpoint usando questa API. È possibile aggiornare lo stato, la determinazione, la classificazione e le proprietà assignedTo.
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
ms.technology: mde
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688250"
---
# <a name="update-alert"></a>Avviso di aggiornamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Aggiorna le proprietà dell'oggetto [Alert esistente.](alerts.md)
<br>**L'invio di** commenti è disponibile con o senza aggiornare le proprietà.
<br>Le proprietà aggiornabili sono: ```status``` ```determination``` , e ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Limitazioni
1. Puoi aggiornare gli avvisi disponibili nell'API. Per [ulteriori informazioni, vedere Avvisi](get-alerts.md) elenco.
2. I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.


## <a name="permissions"></a>Autorizzazioni
Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Alerts.ReadWrite.All |  "Lettura e scrittura di tutti gli avvisi"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.ReadWrite | "Avvisi di lettura e scrittura"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | Stringa | application/json. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Nel corpo della richiesta specificare i valori per i campi rilevanti da aggiornare.
<br>Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà. 
<br>Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificate.

Proprietà | Tipo | Descrizione
:---|:---|:---
status | Stringa | Specifica lo stato corrente dell'avviso. I valori delle proprietà sono: 'New', 'InProgress' e 'Resolved'.
assignedTo | Stringa | Proprietario dell'avviso
classificazione | Stringa | Specifica la specifica dell'avviso. I valori delle proprietà sono: 'Unknown', 'FalsePositive', 'TruePositive'. 
determinazione | Stringa | Specifica la determinazione dell'avviso. I valori delle proprietà sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | Stringa | Commento da aggiungere all'avviso.

## <a name="response"></a>Risposta
Se ha esito positivo, questo metodo restituisce [](alerts.md) 200 OK e l'entità di avviso nel corpo della risposta con le proprietà aggiornate. Se l'avviso con l'ID specificato non è stato trovato - 404 Non trovato.


## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
