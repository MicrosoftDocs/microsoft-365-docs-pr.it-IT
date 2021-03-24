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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060802"
---
# <a name="update-incidents-api"></a>API per gli eventi imprevisti di aggiornamento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

## <a name="api-description"></a>Descrizione API

Aggiorna le proprietà dell'evento imprevisto esistente. Le proprietà aggiornabili sono: ```status``` , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quote, allocazione delle risorse e altri vincoli

1. È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di ottenere la soglia di limitazione.
2. È possibile impostare `determination` la proprietà solo se è `classification` impostata su TruePositive.

Se la richiesta viene limitato, restituirà un codice `429` di risposta. Il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Accedere alle API di Microsoft 365 Defender.](api-access.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
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

Nel corpo della richiesta specificare i valori per i campi da aggiornare. Le proprietà esistenti non incluse nel corpo della richiesta manterranno i relativi valori, a meno che non sia necessario ricalcolarne il ricalcolo a causa di modifiche ai valori correlati. Per ottenere prestazioni ottimali, è consigliabile omettere i valori esistenti che non sono stati modificati.

Proprietà | Tipo | Descrizione
-|-|-
status | Enum | Specifica lo stato corrente dell'avviso. I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .
assignedTo | stringa | Proprietario dell'evento imprevisto.
classificazione | Enum | Specifica dell'avviso. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'avviso. I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
tag | string List | Elenco di tag Evento imprevisto.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce `200 OK` . Il corpo della risposta conterrà l'entità evento imprevisto con proprietà aggiornate. Se non è stato trovato un evento imprevisto con l'ID specificato, il metodo restituisce `404 Not Found` .

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
