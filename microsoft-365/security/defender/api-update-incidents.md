---
title: Aggiornare l'API degli incidenti
description: Informazioni su come aggiornare gli incidenti utilizzando l'API Microsoft 365 Defender
keywords: aggiornamento, api, incidente
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571782"
---
# <a name="update-incident-api"></a>Aggiornare l'API degli incidenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

## <a name="api-description"></a>Descrizione API

Aggiorna le proprietà dell'incidente esistente. Le proprietà aggiornabili sono: ```status``` , , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quote, allocazione delle risorse e altri vincoli

1. È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di raggiungere la soglia di limitazione.
2. È possibile impostare la `determination` proprietà solo se è `classification` impostata su TruePositive.

Se la richiesta è limitata, restituirà un codice `429` di risposta. Il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, incluso come scegliere le autorizzazioni, [vedere Accedere alle API Microsoft 365 Defender](api-access.md).

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
-|-|-
Applicazione | Incident.ReadWrite.All | Leggere e scrivere tutti gli incidenti
Delegato (account aziendale o dell'istituto di istruzione) | Incident.ReadWrite | Leggere e scrivere incidenti

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente, l'utente deve avere l'autorizzazione per aggiornare l'incidente nel portale.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
-|-|-
Autorizzazione | Stringa | Portatore {token}. **Obbligatorio**.
Content-Type | Stringa | domanda/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta fornire i valori per i campi da aggiornare. Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i relativi valori, a meno che non rocali a causa di modifiche ai valori correlati. Per ottenere prestazioni ottimali, è necessario omettere i valori esistenti che non sono stati modificati.

Proprietà | Tipo | Descrizione
-|-|-
stato | Enum | Specifica lo stato corrente dell'incidente. I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .
assegnatoA | stringa | Proprietario dell'incidente.
classificazione | Enum | Specifica dell'incidente. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'incidente. I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | elenco di stringhe | Elenco di tag Incidente.
commento | stringa | Commento da aggiungere all'incidente.

## <a name="response"></a>Risposta

In caso di esito positivo, questo metodo restituisce `200 OK` . Il corpo della risposta conterrà l'entità incidente con proprietà aggiornate. Se non è stato trovato un incidente con l'ID specificato, il metodo restituisce `404 Not Found` .

## <a name="example"></a>Esempio

**richiesta**

Ecco un esempio della richiesta.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**risposta**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Articoli correlati

- [Accedere alle API Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti e le licenze delle API](api-terms.md)
- [Informazioni i codici di errore](api-error-codes.md)
- [Incidenti delle API](api-incident.md)
- [Elencare incidenti](api-list-incidents.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
