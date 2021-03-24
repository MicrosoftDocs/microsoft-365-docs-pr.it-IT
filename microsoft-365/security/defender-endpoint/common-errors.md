---
title: Errori comuni delle API di Microsoft Defender ATP
description: Elenco degli errori comuni delle API di Microsoft Defender ATP con le descrizioni.
keywords: api, api mdatp, errori, risoluzione dei problemi
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
ms.openlocfilehash: ddbbe07bc477ae3a5016feb795b5bad5ed82a30a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064378"
---
# <a name="common-rest-api-error-codes"></a>Codici di errore API REST comuni

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* I codici di errore elencati nella tabella seguente possono essere restituiti da un'operazione su qualsiasi API di Microsoft Defender for Endpoint.
* Oltre al codice di errore, ogni risposta di errore contiene un messaggio di errore che consente di risolvere il problema.
* Il messaggio è un testo libero che può essere modificato.
* Nella parte inferiore della pagina sono disponibili esempi di risposta.

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Codice di errore |Codice di stato HTTP |Messaggio 
:---|:---|:---
BadRequest | BadRequest (400) | Messaggio di errore Generale richiesta non valida.
ODataError | BadRequest (400) | Query URI OData non valida (viene specificato l'errore specifico).
InvalidInput | BadRequest (400) | Input non valido {input non valido}.
InvalidRequestBody | BadRequest (400) | Corpo della richiesta non valido.
InvalidHashValue | BadRequest (400) | Valore hash {hash non valido} non valido.
InvalidDomainName | BadRequest (400) | Nome di dominio {dominio non valido} non valido.
InvalidIpAddress | BadRequest (400) | L'indirizzo IP {l'IP non valido} non è valido.
InvalidUrl | BadRequest (400) | L'URL {l'URL non valido} non è valido.
MaximumBatchSizeExceeded | BadRequest (400) | Dimensione massima batch superata. Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parametro {parametro mancante} mancante.
OsPlatformNotSupported | BadRequest (400) | Piattaforma del sistema operativo {piattaforma del sistema operativo client} non supportata per questa azione.
ClientVersionNotSupported | BadRequest (400) | {L'azione richiesta} è supportata nella versione client {versione client supportata} e versioni successive.
Non autorizzato | Non autorizzato (401) | Non autorizzato (intestazione di autorizzazione non valida o scaduta).
Accesso negato | Accesso negato (403) | Accesso negato (token valido ma autorizzazione insufficiente per l'azione).
DisabledFeature | Accesso negato (403) | La funzionalità tenant non è abilitata.
DisallowedOperation | Accesso negato (403) | {l'operazione non consentita e il motivo}.
NotFound | Non trovato (404) | Messaggio di errore Generale non trovato.
ResourceNotFound | Non trovato (404) | Impossibile trovare la risorsa {la risorsa richiesta}.
InternalServerError | Errore interno del server (500) | (Nessun messaggio di errore, ritentare l'operazione)
TooManyRequests | Troppe richieste (429) | La risposta rappresenterà il raggiungimento del limite di quota in base al numero di richieste o alla CPU.

## <a name="body-parameters-are-case-sensitive"></a>Per i parametri corpo viene distinzione tra maiuscole e minuscole

Per i parametri del corpo inviato viene attualmente fatto distinzione tra maiuscole e minuscole.
<br>Se si verifica un **errore InvalidRequestBody** o **MissingRequiredParameter,** potrebbe essere causato da un parametro errato maiuscolo o minuscolo.
<br>Esaminare la pagina della documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.

## <a name="correlation-request-id"></a>ID richiesta di correlazione

Ogni risposta di errore contiene un parametro ID univoco per il rilevamento.
<br>Il nome della proprietà di questo parametro è "target".
<br>Quando ci viene contattato per un errore, l'associazione di questo ID consente di individuare la causa radice del problema.

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
