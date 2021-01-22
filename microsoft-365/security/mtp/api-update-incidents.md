---
title: API per gli eventi imprevisti di aggiornamento
description: Informazioni su come aggiornare gli eventi imprevisti con l'API di Microsoft 365 Defender
keywords: aggiornamento, api, evento imprevisto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929071"
---
# <a name="update-incidents-api"></a>API per gli eventi imprevisti di aggiornamento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descrizione API

Aggiorna le proprietà dell'evento imprevisto esistente. Le proprietà aggiornabili sono: ```status``` ```determination``` , e ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quote, allocazione delle risorse e altri vincoli

1. È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di raggiunto la soglia di limitazione.
2. È possibile impostare la `determination` proprietà solo se è `classification` impostata su TruePositive.

Se la richiesta è stata limitate, restituirà un codice `429` di risposta. Il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API, è necessaria una delle autorizzazioni seguenti. Per altre informazioni, incluso come scegliere le autorizzazioni, vedere Accedere alle API di [Microsoft 365 Defender.](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazioni
-|-|-
Applicazione | Incident.ReadWrite.All | Lettura e scrittura di tutti gli eventi imprevisti
Delegato (account aziendale o dell'istituto di istruzione) | Incident.ReadWrite | Eventi imprevisti di lettura e scrittura

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente, l'utente deve disporre dell'autorizzazione per aggiornare l'evento imprevisto nel portale.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
-|-|-
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | Stringa | application/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel contenuto della richiesta, specificare i valori per i campi da aggiornare. Le proprietà esistenti che non sono incluse nel contenuto della richiesta manterranno i propri valori, a meno che non siano necessarie ricalcolate a causa di modifiche ai valori correlati. Per ottenere prestazioni ottimali, è consigliabile omettere i valori esistenti che non sono stati modificati.

Proprietà | Tipo | Descrizione
-|-|-
status | Enumerazione | Specifica lo stato corrente dell'avviso. I valori possibili sono: ```Active``` , ```Resolved``` , e ```Redirected``` .
assignedTo | stringa | Proprietario dell'incidente.
classificazione | Enumerazione | Specifica dell'avviso. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enumerazione | Specifica la determinazione dell'avviso. I valori possibili sono: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
tag | string List | Elenco di tag Evento imprevisto.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce `200 OK` . Il contenuto della risposta conterrà l'entità evento imprevisto con proprietà aggiornate. Se non è stato trovato un evento imprevisto con l'ID specificato, il metodo restituisce `404 Not Found` .

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Risposta**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Articoli correlati

- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
- [Incidenti delle API](api-incident.md)
- [Elencare incidenti](api-list-incidents.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
