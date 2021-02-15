---
title: Codici di errore comuni dell'API REST di Microsoft 365 Defender
description: Informazioni sui codici di errore comuni dell'API REST di Microsoft 365 Defender
keywords: api, error, codes, common errors, mtp, api error codes
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
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928391"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Codici di errore comuni dell'API REST di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

I codici di errore possono essere restituiti da un'operazione su una qualsiasi delle API di Microsoft 365 Defender. Ogni risposta di errore conterrà un messaggio di errore che può aiutare a risolvere il problema. Nella colonna del messaggio di errore nella sezione della tabella sono disponibili alcuni messaggi di esempio. Il contenuto dei messaggi effettivi varia in base ai fattori che hanno attivato la risposta. Il contenuto delle variabili è indicato nella tabella da parentesi angolari.

## <a name="error-codes"></a>Codici di errore

Codice di errore | Codice di stato HTTP | Messaggio
-|-|-
BadRequest | BadRequest (400) | Messaggio di errore Generale richiesta non valida.
ODataError | BadRequest (400) | Query URI OData non \<the specific error is specified\> valida.
InvalidInput | BadRequest (400) | Input non \<the invalid input\> valido.
InvalidRequestBody | BadRequest (400) | Corpo della richiesta non valido.
InvalidHashValue | BadRequest (400) | Valore hash \<the invalid hash\> non valido.
InvalidDomainName | BadRequest (400) | Nome di dominio \<the invalid domain\> non valido.
InvalidIpAddress | BadRequest (400) | Indirizzo IP \<the invalid IP\> non valido.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> non valido.
MaximumBatchSizeExceeded | BadRequest (400) | Dimensione massima batch superata. Ricevuto: \<batch size received\> , consentito: {dimensione batch consentita}.
MissingRequiredParameter | BadRequest (400) | Parametro \<the missing parameter\> mancante.
OsPlatformNotSupported | BadRequest (400) | Piattaforma del sistema \<the client OS Platform\> operativo non supportata per questa azione.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> è supportato nella versione client \<supported client version\> e versioni successive.
Non autorizzato | Non autorizzato (401) | Non autorizzato <br /><br />*Nota: in genere causata da un'intestazione di autorizzazione non valida o scaduta.*
Accesso negato | Accesso negato (403) | Accesso negato <br /><br />*Nota: token valido ma autorizzazioni insufficienti per l'azione.*
DisabledFeature | Accesso negato (403) | La funzionalità tenant non è abilitata.
DisallowedOperation | Accesso negato (403) | \<the disallowed operation and the reason\>.
NotFound | Non trovato (404) | Messaggio di errore Generale non trovato.
ResourceNotFound | Non trovato (404) | Risorsa \<the requested resource\> non trovata.
InternalServerError | Errore interno del server (500) | *Nota: nessun messaggio di errore, ritenta l'operazione o contatta Microsoft se non viene risolto*

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

## <a name="body-parameters"></a>Parametri del corpo

> [!IMPORTANT]
> Per i parametri del corpo viene fatto distinzione tra maiuscole e minuscole.

Se si verifica un *errore InvalidRequestBody* o *MissingRequiredParameter,* potrebbe essere causato da un errore di digitazione. Esaminare la documentazione dell'API e verificare che i parametri inviati corrispondano all'esempio pertinente.

## <a name="tracking-id"></a>ID tracciabilità

Ogni risposta di errore contiene un parametro ID univoco per la verifica. Il nome della proprietà di questo parametro è *target.* Quando ci viene contattato per un errore, l'associazione di questo ID ci consente di individuare la causa principale del problema.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
