---
title: API Per ottenere i computer correlati agli utenti
description: Scopri come usare l'API Get user-related machines per recuperare una raccolta di dispositivi correlati a un ID utente in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere, utente, avvisi correlati all'utente
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229456"
---
# <a name="get-user-related-machines-api"></a>API Per ottenere i computer correlati agli utenti

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API
Recupera una raccolta di dispositivi correlati a un DETERMINATO ID utente.

## <a name="limitations"></a>Limitazioni

I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |Autorizzazione|Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |Machine.Read.All|"Leggi tutti i profili computer"
Applicazione |Machine.ReadWrite.All |"Leggere e scrivere tutte le informazioni sul computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.Read | "Leggere le informazioni sul computer"
Delegato (account aziendale o dell'istituto di istruzione) | Machine.ReadWrite | "Leggere e scrivere informazioni sul computer"

> [!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente:
>
> - L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Visualizza dati". Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md))
> - La risposta includerà solo i dispositivi a cui l'utente può accedere, in base alle impostazioni del gruppo di dispositivi. Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)

## <a name="http-request"></a>Richiesta HTTP

```http
GET /api/users/{id}/machines
```

**L'ID non è l'UPN completo, ma solo il nome utente. (ad esempio, per recuperare i computer user1@contoso.com usare /api/users/user1/machines)**

## <a name="request-headers"></a>Intestazioni di richiesta

Nome | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Vuoto

## <a name="response"></a>Risposta

Se l'operazione ha esito positivo e [](machine.md) l'utente esiste: 200 OK con l'elenco delle entità computer nel corpo. Se l'utente non esiste- 404 Non trovato.

## <a name="example"></a>Esempio

### <a name="request"></a>Richiesta

Ecco un esempio della richiesta.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
