---
title: Accedere a API di Microsoft Defender per endpoint .
ms.reviewer: ''
description: Informazioni su come usare le API per automatizzare i flussi di lavoro e innovare in base alle funzionalità di Microsoft Defender for Endpoint
keywords: api, api, wdatp, open api, microsoft defender for endpoint api, microsoft defender atp, api pubbliche, api supportate, avvisi, dispositivo, utente, dominio, ip, file, ricerca avanzata, query
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571830"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="87aa1-104">Accedere a API di Microsoft Defender per endpoint .</span><span class="sxs-lookup"><span data-stu-id="87aa1-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87aa1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="87aa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="87aa1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87aa1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87aa1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="87aa1-108">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="87aa1-108">**Applies to:**</span></span> 
- [<span data-ttu-id="87aa1-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="87aa1-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="87aa1-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="87aa1-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="87aa1-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="87aa1-112">Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="87aa1-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="87aa1-113">Queste API ti consentiranno di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="87aa1-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="87aa1-114">L'accesso API richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="87aa1-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="87aa1-115">Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="87aa1-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="87aa1-116">Guarda questo video per una breve panoramica delle API di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="87aa1-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="87aa1-117">In generale, dovrai eseguire la procedura seguente per usare le API:</span><span class="sxs-lookup"><span data-stu-id="87aa1-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="87aa1-118">Creare [un'applicazione AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="87aa1-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="87aa1-119">Ottenere un token di accesso con questa applicazione</span><span class="sxs-lookup"><span data-stu-id="87aa1-119">Get an access token using this application</span></span>
- <span data-ttu-id="87aa1-120">Usare il token per accedere all'API di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="87aa1-121">Puoi accedere all'API defender per endpoint con **il contesto dell'applicazione** **o il contesto utente.**</span><span class="sxs-lookup"><span data-stu-id="87aa1-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="87aa1-122">**Contesto applicazione: (scelta consigliata)**</span><span class="sxs-lookup"><span data-stu-id="87aa1-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="87aa1-123">Usato dalle app eseguite senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="87aa1-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="87aa1-124">ad esempio app eseguite come servizi in background o daemon.</span><span class="sxs-lookup"><span data-stu-id="87aa1-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="87aa1-125">Passaggi da eseguire per accedere all'API defender per endpoint con il contesto dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="87aa1-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="87aa1-126">Creare un'applicazione Web AAD.</span><span class="sxs-lookup"><span data-stu-id="87aa1-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="87aa1-127">Assegnare l'autorizzazione desiderata all'applicazione, ad esempio "Avvisi di lettura", "Isola computer".</span><span class="sxs-lookup"><span data-stu-id="87aa1-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="87aa1-128">Crea una chiave per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87aa1-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="87aa1-129">Ottenere il token usando l'applicazione con la relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="87aa1-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="87aa1-130">Usare il token per accedere all'API di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="87aa1-131">Per ulteriori informazioni, vedere [Ottenere l'accesso con il contesto dell'applicazione.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="87aa1-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="87aa1-132">**Contesto utente:**</span><span class="sxs-lookup"><span data-stu-id="87aa1-132">**User Context:**</span></span> <br>
    <span data-ttu-id="87aa1-133">Usato per eseguire azioni nell'API per conto di un utente.</span><span class="sxs-lookup"><span data-stu-id="87aa1-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="87aa1-134">Passaggi da eseguire per accedere all'API defender per endpoint con il contesto dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="87aa1-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="87aa1-135">Creare un'applicazione nativa di AAD.</span><span class="sxs-lookup"><span data-stu-id="87aa1-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="87aa1-136">Assegnare l'autorizzazione desiderata all'applicazione, ad esempio "Avvisi di lettura", "Isola computer" e così via.</span><span class="sxs-lookup"><span data-stu-id="87aa1-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="87aa1-137">Ottenere il token usando l'applicazione con le credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="87aa1-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="87aa1-138">Usare il token per accedere all'API di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="87aa1-139">Per ulteriori informazioni, vedere [Ottenere l'accesso con il contesto utente.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="87aa1-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="87aa1-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="87aa1-140">Related topics</span></span>
- [<span data-ttu-id="87aa1-141">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="87aa1-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="87aa1-142">Accedere a Microsoft Defender for Endpoint con il contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="87aa1-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="87aa1-143">Accedere a Microsoft Defender per Endpoint con contesto utente</span><span class="sxs-lookup"><span data-stu-id="87aa1-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
