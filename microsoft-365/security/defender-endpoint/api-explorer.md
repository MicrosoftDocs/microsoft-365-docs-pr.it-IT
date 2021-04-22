---
title: Esplora API in Microsoft Defender per endpoint
ms.reviewer: ''
description: Usare Esplora API per creare ed eseguire query API, testare e inviare richieste per qualsiasi API disponibile
keywords: api, explorer, inviare, richiedere, ottenere, pubblicare,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930114"
---
# <a name="api-explorer"></a><span data-ttu-id="8a6fe-104">Esplora API</span><span class="sxs-lookup"><span data-stu-id="8a6fe-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a6fe-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8a6fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a6fe-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8a6fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="8a6fe-107">Microsoft Defender for Endpoint API Explorer è uno strumento che consente di esplorare in modo interattivo diverse API di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="8a6fe-108">Esplora API semplifica la creazione e l'esecuzione di query API, test e invio di richieste per qualsiasi endpoint API Defender for Endpoint disponibile.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="8a6fe-109">Usa Esplora API per eseguire azioni o trovare dati che potrebbero non essere ancora disponibili tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="8a6fe-110">Lo strumento è utile durante lo sviluppo di app.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-110">The tool is useful during app development.</span></span> <span data-ttu-id="8a6fe-111">Consente di eseguire query API che rispettino le impostazioni di accesso degli utenti, riducendo la necessità di generare token di accesso.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="8a6fe-112">È inoltre possibile utilizzare lo strumento per esplorare la raccolta di query di esempio, copiare esempi di codice dei risultati e generare informazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="8a6fe-113">Con Esplora API puoi:</span><span class="sxs-lookup"><span data-stu-id="8a6fe-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="8a6fe-114">Eseguire richieste per qualsiasi metodo e visualizzare le risposte in tempo reale</span><span class="sxs-lookup"><span data-stu-id="8a6fe-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="8a6fe-115">Sfoglia rapidamente gli esempi di API e scopri quali parametri supportano</span><span class="sxs-lookup"><span data-stu-id="8a6fe-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="8a6fe-116">Effettuare chiamate API con facilità; non è necessario eseguire l'autenticazione oltre l'accesso al portale di gestione</span><span class="sxs-lookup"><span data-stu-id="8a6fe-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="8a6fe-117">Esplora API di Access</span><span class="sxs-lookup"><span data-stu-id="8a6fe-117">Access API Explorer</span></span>

<span data-ttu-id="8a6fe-118">Nel menu di spostamento a sinistra seleziona **Partner & API**  >  **Explorer.**</span><span class="sxs-lookup"><span data-stu-id="8a6fe-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="8a6fe-119">API supportate</span><span class="sxs-lookup"><span data-stu-id="8a6fe-119">Supported APIs</span></span>

<span data-ttu-id="8a6fe-120">Esplora API supporta tutte le API offerte da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="8a6fe-121">L'elenco delle API supportate è disponibile nella documentazione [relativa alle API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8a6fe-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="8a6fe-122">Introduzione a Esplora API</span><span class="sxs-lookup"><span data-stu-id="8a6fe-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="8a6fe-123">Nel riquadro sinistro è disponibile un elenco di richieste di esempio che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="8a6fe-124">Seguire i collegamenti e fare clic **su Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="8a6fe-125">Per alcuni esempi potrebbe essere necessario specificare un parametro nell'URL, ad esempio {machine- ID}.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="8a6fe-126">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="8a6fe-126">FAQ</span></span>

<span data-ttu-id="8a6fe-127">**Devo avere un token API per usare Esplora API?**</span><span class="sxs-lookup"><span data-stu-id="8a6fe-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="8a6fe-128">Le credenziali per accedere a un'API non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="8a6fe-129">Esplora API usa il token defender per il portale di gestione degli endpoint ogni volta che effettua una richiesta.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="8a6fe-130">La credenziale di autenticazione utente con accesso viene usata per verificare che Esplora API sia autorizzato ad accedere ai dati per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="8a6fe-131">Le richieste API specifiche sono limitate in base ai privilegi RBAC.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="8a6fe-132">Ad esempio, una richiesta di "indicatore di invio" è limitata al ruolo di amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8a6fe-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
