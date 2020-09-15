---
title: Accedere alle API di Microsoft Threat Protection
description: Informazioni su come accedere alle API di Microsoft Threat Protection
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650386"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="8db31-104">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="8db31-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8db31-105">**Applies to:**</span></span>
- <span data-ttu-id="8db31-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8db31-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="8db31-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8db31-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8db31-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="8db31-109">Microsoft Threat Protection espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="8db31-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8db31-110">Tali API consentiranno di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di protezione dalle minacce di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8db31-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="8db31-111">L'accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="8db31-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8db31-112">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="8db31-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="8db31-113">In generale, è necessario eseguire la procedura seguente per utilizzare le API:</span><span class="sxs-lookup"><span data-stu-id="8db31-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="8db31-114">Creare un'applicazione AAD</span><span class="sxs-lookup"><span data-stu-id="8db31-114">Create an AAD application</span></span>
- <span data-ttu-id="8db31-115">Ottenere un token di accesso tramite questa applicazione</span><span class="sxs-lookup"><span data-stu-id="8db31-115">Get an access token using this application</span></span>
- <span data-ttu-id="8db31-116">Utilizzare il token per accedere all'API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="8db31-117">È possibile accedere all'API Microsoft Threat Protection con contesto dell' **applicazione** o **contesto utente**.</span><span class="sxs-lookup"><span data-stu-id="8db31-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="8db31-118">**Contesto dell'applicazione: (scelta consigliata)**</span><span class="sxs-lookup"><span data-stu-id="8db31-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="8db31-119">Utilizzato dalle app eseguite senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="8db31-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="8db31-120">ad esempio, le app che vengono eseguite come servizi in background o demoni.</span><span class="sxs-lookup"><span data-stu-id="8db31-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="8db31-121">Passaggi da eseguire per accedere all'API di Microsoft Threat Protection con il contesto dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8db31-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="8db31-122">Creare un'applicazione Web AAD.</span><span class="sxs-lookup"><span data-stu-id="8db31-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="8db31-123">Assegnare l'autorizzazione desiderata all'esempio applicationFor, **Incident. Read. All**, **AdvancedHunting. Read. All**.</span><span class="sxs-lookup"><span data-stu-id="8db31-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="8db31-124">Creare una chiave per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8db31-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="8db31-125">Ottenere il token utilizzando l'applicazione con la relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="8db31-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="8db31-126">Utilizzare il token per accedere all'API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="8db31-127">Per ulteriori informazioni, vedere [Get Access with Application context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="8db31-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="8db31-128">**Contesto utente:**</span><span class="sxs-lookup"><span data-stu-id="8db31-128">**User Context:**</span></span> <br>
    <span data-ttu-id="8db31-129">Utilizzato per eseguire azioni nell'API per conto di un utente.</span><span class="sxs-lookup"><span data-stu-id="8db31-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="8db31-130">Passaggi da eseguire per accedere all'API di Microsoft Threat Protection con il contesto dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8db31-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="8db31-131">Creare un'applicazione nativa AAD.</span><span class="sxs-lookup"><span data-stu-id="8db31-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="8db31-132">Assegnare l'autorizzazione desiderata per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8db31-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="8db31-133">Ad esempio, **Incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="8db31-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="8db31-134">Ottenere il token utilizzando l'applicazione con le credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="8db31-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="8db31-135">Utilizzare il token per accedere all'API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="8db31-136">Per ulteriori informazioni, vedere [ottenere l'accesso con il contesto utente](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="8db31-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="8db31-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8db31-137">Related topics</span></span>
- [<span data-ttu-id="8db31-138">API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8db31-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="8db31-139">Accedere a Microsoft Threat Protection con il contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8db31-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8db31-140">Accedere a Microsoft Threat Protection con contesto utente</span><span class="sxs-lookup"><span data-stu-id="8db31-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
