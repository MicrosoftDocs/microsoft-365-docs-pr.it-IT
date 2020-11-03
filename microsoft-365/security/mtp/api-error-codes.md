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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846009"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Codici di errore dell'API REST comuni di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

I codici di errore elencati nella tabella riportata di seguito possono essere restituiti da un'operazione in una qualsiasi delle API di Microsoft 365 Defender.

Ogni risposta di errore contiene un messaggio di errore che può contribuire alla risoluzione del problema.

Il messaggio è un testo gratuito che può essere modificato.

Nella parte inferiore della pagina, è possibile trovare gli esempi di risposta.

Codice errore |Codice di stato HTTP |Messaggio 
:---|:---|:---
BadRequest | BadRequest (400) | Messaggio di errore generale di richiesta non valida.
ODataError | BadRequest (400) | Query URI OData non valida (è specificato l'errore specifico).
InvalidInput | BadRequest (400) | Input non valido {l'input non valido}.
InvalidRequestBody | BadRequest (400) | Corpo richiesta non valida.
InvalidHashValue | BadRequest (400) | Valore hash {l'hash non valido} non è valido.
InvalidDomainName | BadRequest (400) | Nome di dominio {il dominio non valido} non è valido.
InvalidIpAddress | BadRequest (400) | Indirizzo IP {l'IP non valido} non è valido.
InvalidUrl | BadRequest (400) | URL {l'URL non valido} non è valido.
MaximumBatchSizeExceeded | BadRequest (400) | Dimensioni massime del batch superate. Received: {dimensioni batch ricevute}, consentito: {dimensioni batch consentite}.
MissingRequiredParameter | BadRequest (400) | Parametro {il parametro mancante} è mancante.
OsPlatformNotSupported | BadRequest (400) | Piattaforma OS {la piattaforma del sistema operativo client} non è supportata per questa azione.
ClientVersionNotSupported | BadRequest (400) | {L'azione richiesta} è supportata nella versione client {versione client supportata} e versioni successive.
Non autorizzato | Non autorizzato (401) | Non autorizzato (di solito non valido o scaduto l'intestazione di autorizzazione).
Proibito | Forbidden (403) | Forbidden (token valido ma autorizzazione insufficiente per l'azione).
DisabledFeature | Forbidden (403) | La caratteristica tenant non è abilitata.
DisallowedOperation | Forbidden (403) | {l'operazione non consentita e il motivo}.
NotFound | Non trovato (404) | Messaggio di errore generale non trovato.
ResourceNotFound | Non trovato (404) | Risorsa {la risorsa richiesta} non è stata trovata.
InternalServerError | Errore interno del server (500) | (Nessun messaggio di errore, riprova l'operazione o contattaci se non viene risolto)

## <a name="body-parameters-are-case-sensitive"></a>I parametri corpo sono con distinzione tra maiuscole e minuscole

I parametri del corpo inviati sono attualmente con distinzione tra maiuscole e minuscole.
<br>Se si verifica un errore di **InvalidRequestBody** o **MissingRequiredParameter** , potrebbe essere causato da un valore maiuscolo o minuscolo di un parametro errato.
<br>È consigliabile esaminare la pagina relativa alla documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.

## <a name="correlation-request-id"></a>ID richiesta di correlazione

Ogni risposta di errore contiene un parametro ID univoco per la verifica.
<br>Il nome della proprietà di questo parametro è "target".
<br>Quando ci si mette in contatto con informazioni su un errore, l'associazione di questo ID consentirà di individuare la causa principale del problema.

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

