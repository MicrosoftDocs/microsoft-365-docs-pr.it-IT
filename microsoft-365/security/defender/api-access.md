---
title: Accedere alle API di Microsoft 365 Defender
description: Informazioni su come accedere alle API Microsoft 365 Defender di rete
keywords: access, api, contesto dell'applicazione, contesto utente, applicazione aad, token di accesso
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
ms.openlocfilehash: 3cbd329c63d7cf1868083c66919773e14ed51156
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029598"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Accedere alle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API consentono di automatizzare i flussi di lavoro e di usare completamente Microsoft 365 Defender funzionalità di un utente.

In generale, dovrai eseguire la procedura seguente per usare le API:

- Creare un'Azure Active Directory applicazione
- Ottenere un token di accesso con questa applicazione
- Usare il token per accedere all'API Microsoft 365 Defender

> [!NOTE]
> L'accesso API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Una volta completati questi passaggi, sei pronto per accedere all'API Microsoft 365 Defender usando un contesto specifico.

## <a name="application-context-recommended"></a>Contesto dell'applicazione (scelta consigliata)

Usa questo contesto per le app eseguite senza un utente connesso, ad esempio servizi in background o daemon.

1. Creare un'Azure Active Directory Web.
2. Assegnare le autorizzazioni desiderate all'applicazione.
3. Creare una chiave per l'applicazione.
4. Ottieni un token di sicurezza usando l'applicazione e la relativa chiave.
5. Usa il token per accedere all'API Microsoft 365 Defender.

Per altre informazioni, vedi **[Creare un'app per accedere Microsoft 365 Defender senza un utente.](api-create-app-web.md)**

## <a name="user-context"></a>Contesto utente

Usa questo contesto per eseguire azioni per conto di un singolo utente.

1. Creare un'Azure Active Directory nativa.
2. Assegnare l'autorizzazione desiderata all'applicazione.
3. Ottenere un token di sicurezza usando le credenziali utente per l'applicazione.
4. Usa il token per accedere all'API Microsoft 365 Defender.

Per altre informazioni, vedi **[Creare un'app per accedere Microsoft 365 Defender API per conto di un utente.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Contesto partner

Usa questo contesto quando devi fornire un'app a molti utenti in [più tenant.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Creare un'Azure Active Directory multi-tenant.
2. Assegnare l'autorizzazione desiderata all'applicazione.
3. Ottieni [il consenso dell'amministratore](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) per l'app da ogni tenant.
4. Ottenere un token di sicurezza usando le credenziali utente in base all'ID tenant di un cliente.
5. Usa il token per accedere all'API Microsoft 365 Defender.

Per altre informazioni, vedi **[Creare un'app con accesso partner Microsoft 365 Defender API](api-partner-access.md)**.

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Defender Panoramica delle API](api-overview.md)
- [Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gestire i segreti nelle app server con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Creare un'applicazione "Hello world" che accede Microsoft 365 API](api-hello-world.md)
