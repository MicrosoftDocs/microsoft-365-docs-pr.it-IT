---
title: API delle entità di avviso per l'aggiornamento in batch
description: Scopri come aggiornare gli avvisi di Microsoft Defender for Endpoint in un batch usando questa API. È possibile aggiornare lo stato, la determinazione, la classificazione e le proprietà assignedTo.
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
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290208"
---
# <a name="batch-update-alerts"></a>Avvisi di aggiornamento in batch

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API

Aggiorna le proprietà di un batch di [avvisi esistenti.](alerts.md)

**L'invio di** commenti è disponibile con o senza aggiornare le proprietà.

Le proprietà aggiornabili sono: `status` `determination` , e `classification` `assignedTo` .

## <a name="limitations"></a>Limitazioni

1. Puoi aggiornare gli avvisi disponibili nell'API. Per [ulteriori informazioni, vedere Avvisi](get-alerts.md) elenco.
2. I limiti di frequenza per questa API sono 10 chiamate al minuto e 500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | Alerts.ReadWrite.All | "Lettura e scrittura di tutti gli avvisi"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.ReadWrite | "Avvisi di lettura e scrittura"

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
> - L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | Stringa | application/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta specificare gli ID degli avvisi da aggiornare e i valori dei campi rilevanti che si desidera aggiornare per tali avvisi.

Le proprietà esistenti non incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà.

Per ottenere prestazioni ottimali, non è consigliabile includere valori esistenti che non sono stati modificati.

Proprietà | Tipo | Descrizione
:---|:---|:---
alertIds | Stringa &lt; elenco&gt;| Elenco degli ID degli avvisi da aggiornare. **Obbligatorio**
status | Stringa | Specifica lo stato aggiornato degli avvisi specificati. I valori delle proprietà sono: 'New', 'InProgress' e 'Resolved'.
assignedTo | Stringa | Proprietario degli avvisi specificati
classificazione | Stringa | Specifica la specifica degli avvisi specificati. I valori delle proprietà sono: 'Unknown', 'FalsePositive', 'TruePositive'. 
determinazione | Stringa | Specifica la determinazione degli avvisi specificati. I valori delle proprietà sono: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | Stringa | Commento da aggiungere agli avvisi specificati.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK, con un corpo di risposta vuoto.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
