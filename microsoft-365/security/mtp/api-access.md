---
title: Accedere alle API di Microsoft 365 Defender
description: Informazioni su come accedere alle API di Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932155"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Accedere alle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API consentono di automatizzare i flussi di lavoro e di usare completamente le funzionalità di Microsoft 365 Defender.

In generale, dovrai eseguire la procedura seguente per usare le API:

- Creare un'applicazione Azure Active Directory
- Ottenere un token di accesso con questa applicazione
- Usare il token per accedere all'API di Microsoft 365 Defender

> [!NOTE]
> L'accesso api richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere Flusso del codice di autorizzazione [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Una volta completati questi passaggi, è possibile accedere all'API di Microsoft 365 Defender usando un contesto specifico.

## <a name="application-context-recommended"></a>Contesto dell'applicazione (consigliato)

Usa questo contesto per le app eseguite senza un utente connesso, ad esempio servizi in background o daemon.

1. Creare un'applicazione Web di Azure Active Directory.
2. Assegnare le autorizzazioni desiderate all'applicazione.
3. Creare una chiave per l'applicazione.
4. Ottenere un token di sicurezza usando l'applicazione e la relativa chiave.
5. Usare il token per accedere all'API di Microsoft 365 Defender.

Per altre informazioni, vedere **[Creare un'app per accedere a Microsoft 365 Defender senza un utente.](api-create-app-web.md)**

## <a name="user-context"></a>Contesto utente

Utilizzare questo contesto per eseguire azioni per conto di un singolo utente.

1. Creare un'applicazione nativa di Azure Active Directory.
2. Assegnare l'autorizzazione desiderata all'applicazione.
3. Ottenere un token di sicurezza usando le credenziali utente per l'applicazione.
4. Usare il token per accedere all'API di Microsoft 365 Defender.

Per altre informazioni, vedere Creare un'app per accedere alle API di **[Microsoft 365 Defender per conto di un utente.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Contesto partner

Usa questo contesto quando devi fornire un'app a molti utenti in [più tenant.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Creare un'applicazione multi-tenant di Azure Active Directory.
2. Assegnare l'autorizzazione desiderata all'applicazione.
3. Ottenere [il consenso dell'amministratore](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) per l'app da ogni tenant.
4. Ottenere un token di sicurezza usando le credenziali utente in base all'ID tenant di un cliente.
5. Usare il token per accedere all'API di Microsoft 365 Defender.

Per altre informazioni, vedere **[Creare un'app con accesso partner alle API di Microsoft 365 Defender.](api-partner-access.md)**

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gestire i segreti nelle app server con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Creare un'applicazione "Hello world" che accede alle API di Microsoft 365](api-hello-world.md)
