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
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="868ad-104">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="868ad-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="868ad-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="868ad-105">**Applies to:**</span></span>

- <span data-ttu-id="868ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="868ad-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="868ad-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="868ad-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="868ad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="868ad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="868ad-109">Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="868ad-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="868ad-110">Queste API consentono di automatizzare i flussi di lavoro e di sfruttare appieno le funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="868ad-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="868ad-111">In generale, è necessario eseguire la procedura seguente per utilizzare le API:</span><span class="sxs-lookup"><span data-stu-id="868ad-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="868ad-112">Creare un'applicazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="868ad-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="868ad-113">Ottenere un token di accesso tramite questa applicazione</span><span class="sxs-lookup"><span data-stu-id="868ad-113">Get an access token using this application</span></span>
- <span data-ttu-id="868ad-114">Utilizzare il token per accedere all'API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="868ad-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="868ad-115">L'accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="868ad-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="868ad-116">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="868ad-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="868ad-117">Dopo aver effettuato questi passaggi, si è pronti per accedere all'API Microsoft 365 Defender utilizzando un contesto specifico.</span><span class="sxs-lookup"><span data-stu-id="868ad-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="868ad-118">Contesto dell'applicazione (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="868ad-118">Application context (Recommended)</span></span>

<span data-ttu-id="868ad-119">Utilizzare questo contesto per le app che vengono eseguite senza l'utilizzo di un utente connesso, ad esempio servizi in background o demoni.</span><span class="sxs-lookup"><span data-stu-id="868ad-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="868ad-120">Creare un'applicazione Web di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="868ad-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="868ad-121">Assegnare le autorizzazioni desiderate all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="868ad-122">Creare una chiave per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-122">Create a key for the application.</span></span>
4. <span data-ttu-id="868ad-123">Ottenere un token di sicurezza utilizzando l'applicazione e la relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="868ad-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="868ad-124">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="868ad-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="868ad-125">Per ulteriori informazioni, vedere **[creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)**.</span><span class="sxs-lookup"><span data-stu-id="868ad-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="868ad-126">Contesto utente</span><span class="sxs-lookup"><span data-stu-id="868ad-126">User context</span></span>

<span data-ttu-id="868ad-127">Utilizzare questo contesto per eseguire azioni per conto di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="868ad-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="868ad-128">Creare un'applicazione nativa di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="868ad-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="868ad-129">Assegnare l'autorizzazione desiderata per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="868ad-130">Ottenere un token di sicurezza utilizzando le credenziali utente per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="868ad-131">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="868ad-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="868ad-132">Per ulteriori informazioni, vedere **[Create an app to Access Microsoft 365 Defender APIs per conto di un utente](api-create-app-user-context.md)**.</span><span class="sxs-lookup"><span data-stu-id="868ad-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="868ad-133">Contesto del partner</span><span class="sxs-lookup"><span data-stu-id="868ad-133">Partner context</span></span>

<span data-ttu-id="868ad-134">Utilizzare questo contesto quando è necessario fornire un'app a molti utenti tra [più tenant](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span><span class="sxs-lookup"><span data-stu-id="868ad-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="868ad-135">Creare un'applicazione multi-tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="868ad-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="868ad-136">Assegnare l'autorizzazione desiderata per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="868ad-137">Ottenere il [consenso dell'amministratore](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) per l'app da ogni tenant.</span><span class="sxs-lookup"><span data-stu-id="868ad-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="868ad-138">Ottenere un token di sicurezza utilizzando le credenziali utente in base all'ID tenant del cliente.</span><span class="sxs-lookup"><span data-stu-id="868ad-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="868ad-139">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="868ad-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="868ad-140">Per ulteriori informazioni, vedere **[Create an app with partner Access to Microsoft 365 Defender Apis](api-partner-access.md)**.</span><span class="sxs-lookup"><span data-stu-id="868ad-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="868ad-141">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="868ad-141">Related articles</span></span>

- [<span data-ttu-id="868ad-142">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="868ad-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="868ad-143">OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API</span><span class="sxs-lookup"><span data-stu-id="868ad-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="868ad-144">Gestione dei segreti nelle app del server con il Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="868ad-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="868ad-145">Creare un'applicazione ' Hello World ' che accede alle API di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="868ad-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
