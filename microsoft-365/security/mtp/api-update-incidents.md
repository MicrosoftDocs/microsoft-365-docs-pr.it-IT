---
title: Aggiornare l'API degli incidenti
description: Informazioni su come aggiornare gli eventi non consentiti tramite Microsoft 365 Defender API
keywords: Update, API, Incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719405"
---
# <a name="update-incidents-api"></a>Aggiornare l'API degli incidenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descrizione API

Aggiorna le proprietà dell'evento Incident esistente. Le proprietà aggiornabili sono:,,, ```status``` ```determination``` ```classification``` ```assignedTo``` e ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quote, allocazione delle risorse e altri vincoli

1. È possibile effettuare fino a 50 chiamate al minuto o 1500 chiamate all'ora prima di colpire la soglia di limitazione.
2. È possibile impostare la `determination` proprietà solo se `classification` è impostata su TruePositive.

Se la richiesta viene sottoposta a limitazione, restituirà un `429` codice di risposta. Il corpo di risposta indicherà l'ora in cui è possibile iniziare a effettuare nuove chiamate.

## <a name="permissions"></a>Autorizzazioni

Per chiamare l'API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Apis](api-access.md).

Tipo di autorizzazione | Autorizzazione | Nome visualizzato per le autorizzazioni
-|-|-
Applicazione | Incident. ReadWrite. All | Leggere e scrivere tutti gli eventi non consentiti
Delegati (account aziendale o dell'Istituto di istruzione) | Incident. ReadWrite | Operazioni di lettura e scrittura degli incidenti

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente, l'utente deve disporre dell'autorizzazione necessaria per aggiornare l'evento Incident nel portale.

## <a name="http-request"></a>Richiesta HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
-|-|-
Autorizzazione | Stringa | Portatore {token}. **Obbligatorio**.
Content-Type | Stringa | applicazione/JSON. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta fornire i valori per i campi che devono essere aggiornati. Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i propri valori, a meno che non debbano essere ricalcolate a causa delle modifiche apportate ai valori correlati. Per prestazioni ottimali, è consigliabile omettere i valori esistenti che non sono stati modificati.

Proprietà | Tipo | Descrizione
-|-|-
stato | Enum | Specifica lo stato corrente dell'avviso. I valori possibili sono: ```Active``` , ```Resolved``` e ```Redirected``` .
AssegnatoA | stringa | Proprietario dell'evento Incident.
classificazione | Enum | Specifica dell'avviso. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'avviso. I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | Elenco di stringhe | Elenco dei tag Incident.

## <a name="response"></a>Risposta

Se l'operazione ha esito positivo, il metodo restituisce `200 OK` . Il corpo di risposta conterrà l'entità Incident con le proprietà aggiornate. Se non è stato trovato un problema con l'ID specificato, il metodo restituisce `404 Not Found` .

## <a name="example"></a>Esempio

**Richiesta**

Di seguito è riportato un esempio della richiesta.

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
- [Informazioni sui codici di errore](api-error-codes.md)
- [Incidenti delle API](api-incident.md)
- [Elencare incidenti](api-list-incidents.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
