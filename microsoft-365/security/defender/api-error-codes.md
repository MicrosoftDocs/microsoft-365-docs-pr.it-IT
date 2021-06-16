---
title: Codici di errore comuni Microsoft 365'API REST di Defender
description: Informazioni sui codici di errore comuni Microsoft 365'API REST di Defender
keywords: api, error, codes, common errors, Microsoft 365 Defender, api error codes
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
ms.openlocfilehash: de24856e8ea7555a96de18cabca5ccadfe71b431
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930272"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Codici di errore comuni Microsoft 365'API REST di Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

I codici di errore possono essere restituiti da un'operazione in una delle API Microsoft 365 Defender. Ogni risposta di errore conterrà un messaggio di errore che consente di risolvere il problema. Nella colonna messaggio di errore nella sezione tabella sono disponibili alcuni messaggi di esempio. Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta. Il contenuto delle variabili è indicato nella tabella da parentesi angolari.

## <a name="error-codes"></a>Codici di errore

Codice di errore | Codice di stato HTTP | Messaggio
-|-|-
BadRequest | BadRequest (400) | Messaggio di errore Generale richiesta non valida.
ODataError | BadRequest (400) | Query URI OData non \<the specific error is specified\> valida.
InvalidInput | BadRequest (400) | Input non \<the invalid input\> valido.
InvalidRequestBody | BadRequest (400) | Corpo della richiesta non valido.
InvalidHashValue | BadRequest (400) | Valore hash \<the invalid hash\> non valido.
InvalidDomainName | BadRequest (400) | Nome di \<the invalid domain\> dominio non valido.
InvalidIpAddress | BadRequest (400) | Indirizzo IP \<the invalid IP\> non valido.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> non valido.
MaximumBatchSizeExceeded | BadRequest (400) | Dimensione massima batch superata. Ricevuto: \<batch size received\> , consentito: {dimensione batch consentita}.
MissingRequiredParameter | BadRequest (400) | Parametro \<the missing parameter\> mancante.
OsPlatformNotSupported | BadRequest (400) | Piattaforma del \<the client OS Platform\> sistema operativo non supportata per questa azione.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> è supportato nella versione client \<supported client version\> e versioni precedenti.
Non autorizzato | Non autorizzato (401) | Non autorizzato <br /><br />*Nota: in genere causata da un'intestazione di autorizzazione non valida o scaduta.*
Accesso negato | Accesso negato (403) | Accesso negato <br /><br />*Nota: token valido ma autorizzazione insufficiente per l'azione.*
DisabledFeature | Accesso negato (403) | La funzionalità tenant non è abilitata.
DisallowedOperation | Accesso negato (403) | \<the disallowed operation and the reason\>.
NotFound | Non trovato (404) | Messaggio di errore Generale non trovato.
ResourceNotFound | Non trovato (404) | Risorsa \<the requested resource\> non trovata.
InternalServerError | Errore interno del server (500) | *Nota: nessun messaggio di errore, ritentare l'operazione o [contattare Microsoft](/microsoft-365/business-video/get-help-support) se non viene risolto*

## <a name="examples"></a>Esempi

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a>Parametri corpo

> [!IMPORTANT]
> Per i parametri corpo viene fatto distinzione tra maiuscole e minuscole.

Se si verifica un *errore InvalidRequestBody* o *MissingRequiredParameter,* potrebbe essere causato da un errore di digitazione. Esaminare la documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.

## <a name="tracking-id"></a>ID tracciabilità

Ogni risposta di errore contiene un parametro ID univoco per il rilevamento. Il nome della proprietà di questo parametro è *target*. Quando ci viene contattato per un errore, l'associazione di questo ID ci aiuterà a trovare la causa principale del problema.

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
