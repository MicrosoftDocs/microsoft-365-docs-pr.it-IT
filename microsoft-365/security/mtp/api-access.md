---
title: Accedere alle API di Microsoft 365 Defender
description: Informazioni su come accedere alle API di Microsoft 365 Defender
keywords: accesso, API, contesto dell'applicazione, contesto utente, applicazione AAD, token di accesso
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719239"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Accedere alle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Queste API consentono di automatizzare i flussi di lavoro e di sfruttare appieno le funzionalità di Microsoft 365 Defender.

In generale, è necessario eseguire la procedura seguente per utilizzare le API:

- Creare un'applicazione di Azure Active Directory
- Ottenere un token di accesso tramite questa applicazione
- Utilizzare il token per accedere all'API Microsoft 365 Defender

> [!NOTE]
> L'accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Dopo aver effettuato questi passaggi, si è pronti per accedere all'API Microsoft 365 Defender utilizzando un contesto specifico.

## <a name="application-context-recommended"></a>Contesto dell'applicazione (scelta consigliata)

Utilizzare questo contesto per le app che vengono eseguite senza l'utilizzo di un utente connesso, ad esempio servizi in background o demoni.

1. Creare un'applicazione Web di Azure Active Directory.
2. Assegnare le autorizzazioni desiderate all'applicazione.
3. Creare una chiave per l'applicazione.
4. Ottenere un token di sicurezza utilizzando l'applicazione e la relativa chiave.
5. Utilizzare il token per accedere a Microsoft 365 Defender API.

Per ulteriori informazioni, vedere **[creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)**.

## <a name="user-context"></a>Contesto utente

Utilizzare questo contesto per eseguire azioni per conto di un singolo utente.

1. Creare un'applicazione nativa di Azure Active Directory.
2. Assegnare l'autorizzazione desiderata per l'applicazione.
3. Ottenere un token di sicurezza utilizzando le credenziali utente per l'applicazione.
4. Utilizzare il token per accedere a Microsoft 365 Defender API.

Per ulteriori informazioni, vedere **[Create an app to Access Microsoft 365 Defender APIs per conto di un utente](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contesto del partner

Utilizzare questo contesto quando è necessario fornire un'app a molti utenti tra [più tenant](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Creare un'applicazione multi-tenant di Azure Active Directory.
2. Assegnare l'autorizzazione desiderata per l'applicazione.
3. Ottenere il [consenso dell'amministratore](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) per l'app da ogni tenant.
4. Ottenere un token di sicurezza utilizzando le credenziali utente in base all'ID tenant del cliente.
5. Utilizzare il token per accedere a Microsoft 365 Defender API.

Per ulteriori informazioni, vedere **[Create an app with partner Access to Microsoft 365 Defender Apis](api-partner-access.md)**.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gestione dei segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Creare un'applicazione ' Hello World ' che accede alle API di Microsoft 365](api-hello-world.md)
