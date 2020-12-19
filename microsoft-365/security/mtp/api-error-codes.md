---
title: Codici di errore dell'API REST comuni di Microsoft 365 Defender
description: Informazioni sui codici di errore dell'API REST di Microsoft 365 Defender comuni
keywords: API, errore, codici, errori comuni, MTP, codici di errore dell'API
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719215"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Codici di errore dell'API REST comuni di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

È possibile che i codici di errore vengano restituiti da un'operazione in una qualsiasi delle API di Microsoft 365 Defender. Ogni risposta di errore conterrà un messaggio di errore che può contribuire a risolvere il problema. Nella colonna messaggio di errore della sezione tabella sono disponibili alcuni messaggi di esempio. Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta. Il contenuto variabile viene indicato nella tabella in base all'angolo tra parentesi quadre.

## <a name="error-codes"></a>Codici di errore

Codice errore | Codice di stato HTTP | Messaggio
-|-|-
BadRequest | BadRequest (400) | Messaggio di errore generale di richiesta non valida.
ODataError | BadRequest (400) | Query URI OData non valida \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Input non valido \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Corpo richiesta non valida.
InvalidHashValue | BadRequest (400) | Il valore hash \<the invalid hash\> non è valido.
InvalidDomainName | BadRequest (400) | Il nome di dominio \<the invalid domain\> non è valido.
InvalidIpAddress | BadRequest (400) | L'indirizzo IP \<the invalid IP\> non è valido.
InvalidUrl | BadRequest (400) | L'URL \<the invalid URL\> non è valido.
MaximumBatchSizeExceeded | BadRequest (400) | Dimensioni massime del batch superate. Ricevuto: \<batch size received\> , consentito: {dimensioni batch consentite}.
MissingRequiredParameter | BadRequest (400) | Il parametro \<the missing parameter\> è mancante.
OsPlatformNotSupported | BadRequest (400) | La piattaforma OS \<the client OS Platform\> non è supportata per questa azione.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> è supportato sulla versione client \<supported client version\> e versioni successive.
Non autorizzato | Non autorizzato (401) | Non autorizzato <br /><br />*Nota: generalmente causata da un'intestazione di autorizzazione non valida o scaduta.*
Proibito | Forbidden (403) | Proibito <br /><br />*Nota: token valido ma autorizzazione insufficiente per l'azione*.
DisabledFeature | Forbidden (403) | La caratteristica tenant non è abilitata.
DisallowedOperation | Forbidden (403) | \<the disallowed operation and the reason\>.
NotFound | Non trovato (404) | Messaggio di errore generale non trovato.
ResourceNotFound | Non trovato (404) | La risorsa \<the requested resource\> non è stata trovata.
InternalServerError | Errore interno del server (500) | *Nota: nessun messaggio di errore, riprovare l'operazione o contattare Microsoft se non viene risolto*

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
> I parametri corpo sono distinzione tra maiuscole e minuscole.

Se si verifica un errore di *InvalidRequestBody* o *MissingRequiredParameter* , potrebbe essere causato da una typo. Esaminare la documentazione relativa all'API e verificare che i parametri inviati corrispondano all'esempio pertinente.

## <a name="tracking-id"></a>ID di rilevamento

Ogni risposta di errore contiene un parametro ID univoco per la verifica. Il nome della proprietà di questo parametro è *target*. Quando ci si mette in contatto con informazioni su un errore, l'associazione di questo ID ci aiuterà a trovare la causa principale del problema.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
