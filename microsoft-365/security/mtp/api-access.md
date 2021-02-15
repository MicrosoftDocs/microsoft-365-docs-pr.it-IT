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
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="79316-104">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79316-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="79316-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="79316-105">**Applies to:**</span></span>

- <span data-ttu-id="79316-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79316-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79316-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="79316-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="79316-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="79316-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="79316-109">Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="79316-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="79316-110">Queste API consentono di automatizzare i flussi di lavoro e di usare completamente le funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="79316-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="79316-111">In generale, dovrai eseguire la procedura seguente per usare le API:</span><span class="sxs-lookup"><span data-stu-id="79316-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="79316-112">Creare un'applicazione Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79316-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="79316-113">Ottenere un token di accesso con questa applicazione</span><span class="sxs-lookup"><span data-stu-id="79316-113">Get an access token using this application</span></span>
- <span data-ttu-id="79316-114">Usare il token per accedere all'API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79316-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="79316-115">L'accesso api richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="79316-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="79316-116">Per ulteriori informazioni, vedere Flusso del codice di autorizzazione [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="79316-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="79316-117">Una volta completati questi passaggi, è possibile accedere all'API di Microsoft 365 Defender usando un contesto specifico.</span><span class="sxs-lookup"><span data-stu-id="79316-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="79316-118">Contesto dell'applicazione (consigliato)</span><span class="sxs-lookup"><span data-stu-id="79316-118">Application context (Recommended)</span></span>

<span data-ttu-id="79316-119">Usa questo contesto per le app eseguite senza un utente connesso, ad esempio servizi in background o daemon.</span><span class="sxs-lookup"><span data-stu-id="79316-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="79316-120">Creare un'applicazione Web di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79316-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="79316-121">Assegnare le autorizzazioni desiderate all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79316-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="79316-122">Creare una chiave per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79316-122">Create a key for the application.</span></span>
4. <span data-ttu-id="79316-123">Ottieni un token di sicurezza usando l'applicazione e la relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="79316-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="79316-124">Usare il token per accedere all'API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="79316-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="79316-125">Per altre informazioni, vedere **[Creare un'app per accedere a Microsoft 365 Defender senza un utente.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="79316-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="79316-126">Contesto utente</span><span class="sxs-lookup"><span data-stu-id="79316-126">User context</span></span>

<span data-ttu-id="79316-127">Utilizzare questo contesto per eseguire azioni per conto di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="79316-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="79316-128">Creare un'applicazione nativa di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79316-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="79316-129">Assegnare l'autorizzazione desiderata all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79316-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="79316-130">Ottenere un token di sicurezza usando le credenziali utente per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79316-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="79316-131">Usare il token per accedere all'API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="79316-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="79316-132">Per altre informazioni, vedere Creare un'app per accedere alle API di **[Microsoft 365 Defender per conto di un utente.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="79316-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="79316-133">Contesto partner</span><span class="sxs-lookup"><span data-stu-id="79316-133">Partner context</span></span>

<span data-ttu-id="79316-134">Usa questo contesto quando devi fornire un'app a molti utenti in [più tenant.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="79316-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="79316-135">Creare un'applicazione multi-tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79316-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="79316-136">Assegnare l'autorizzazione desiderata all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79316-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="79316-137">Ottenere [il consenso dell'amministratore](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) per l'app da ogni tenant.</span><span class="sxs-lookup"><span data-stu-id="79316-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="79316-138">Ottenere un token di sicurezza usando le credenziali utente in base all'ID tenant di un cliente.</span><span class="sxs-lookup"><span data-stu-id="79316-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="79316-139">Usare il token per accedere all'API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="79316-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="79316-140">Per altre informazioni, vedere **[Creare un'app con accesso partner alle API di Microsoft 365 Defender.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="79316-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="79316-141">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="79316-141">Related articles</span></span>

- [<span data-ttu-id="79316-142">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79316-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="79316-143">Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api</span><span class="sxs-lookup"><span data-stu-id="79316-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="79316-144">Gestire i segreti nelle app server con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="79316-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="79316-145">Creare un'applicazione "Hello world" che accede alle API di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="79316-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
