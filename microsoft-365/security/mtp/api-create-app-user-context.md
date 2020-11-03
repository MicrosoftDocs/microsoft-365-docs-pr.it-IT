---
title: Accedere a Microsoft 365 Defender APIs utilizzando per conto dell'utente
description: Informazioni su come accedere a Microsoft 365 Defender APIs utilizzando per conto dell'utente
keywords: accesso, per conto dell'utente, dell'API, dell'applicazione, dell'utente, del token di accesso, del token,
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847357"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="368f9-104">Accedere alle API Microsoft 365 Defender per conto dell'utente</span><span class="sxs-lookup"><span data-stu-id="368f9-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="368f9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="368f9-105">**Applies to:**</span></span>
- <span data-ttu-id="368f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="368f9-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="368f9-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="368f9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="368f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="368f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="368f9-109">In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft 365 Defender per conto di un utente.</span><span class="sxs-lookup"><span data-stu-id="368f9-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="368f9-110">Se è necessario l'accesso a livello di programmazione Microsoft 365 Defender senza un utente, fare riferimento a [creare un'app per accedere a microsoft 365 Defender senza un utente](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="368f9-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="368f9-111">Se non si è certi di quale accesso è necessario, leggere l' [accesso alle API di Microsoft 365 Defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="368f9-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="368f9-112">Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="368f9-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="368f9-113">Tali API consentiranno di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="368f9-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="368f9-114">L'accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="368f9-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="368f9-115">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="368f9-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="368f9-116">In generale, è necessario eseguire la procedura seguente per utilizzare le API:</span><span class="sxs-lookup"><span data-stu-id="368f9-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="368f9-117">Creare un'applicazione AAD</span><span class="sxs-lookup"><span data-stu-id="368f9-117">Create an AAD application</span></span>
- <span data-ttu-id="368f9-118">Ottenere un token di accesso tramite questa applicazione</span><span class="sxs-lookup"><span data-stu-id="368f9-118">Get an access token using this application</span></span>
- <span data-ttu-id="368f9-119">Utilizzare il token per accedere a Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="368f9-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="368f9-120">In questa pagina viene illustrato come creare un'applicazione AAD, ottenere un token di accesso a Microsoft 365 Defender e convalidare il token.</span><span class="sxs-lookup"><span data-stu-id="368f9-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="368f9-121">Quando si accede a Microsoft 365 Defender API per conto di un utente, è necessario disporre delle autorizzazioni appropriate per l'applicazione e l'autorizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="368f9-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="368f9-122">Se si dispone dell'autorizzazione necessaria per eseguire un'azione nel portale, è possibile disporre dell'autorizzazione per eseguire l'azione nell'API.</span><span class="sxs-lookup"><span data-stu-id="368f9-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="368f9-123">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="368f9-123">Create an app</span></span>

1. <span data-ttu-id="368f9-124">Accedere a [Azure](https://portal.azure.com) con l'utente con ruolo di **amministratore globale** .</span><span class="sxs-lookup"><span data-stu-id="368f9-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="368f9-125">Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="368f9-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="368f9-127">Nella registrazione da, immettere le informazioni seguenti, quindi fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="368f9-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="368f9-129">**Nome:** Nome dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="368f9-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="368f9-130">**Tipo di applicazione:** Client pubblico</span><span class="sxs-lookup"><span data-stu-id="368f9-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="368f9-131">**URI di reindirizzamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="368f9-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="368f9-132">Per consentire all'app di accedere a Microsoft 365 Defender e assegnargli le autorizzazioni, nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi autorizzazione** API  >  **l'organizzazione utilizza** >, digitare **Microsoft 365 Defender** e quindi selezionare **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="368f9-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="368f9-133">Microsoft 365 Defender non viene visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="368f9-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="368f9-134">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="368f9-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="368f9-136">Scegliere **autorizzazioni Delegate** > scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident. Read** , quindi selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="368f9-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="368f9-138">È necessario selezionare le autorizzazioni rilevanti.</span><span class="sxs-lookup"><span data-stu-id="368f9-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="368f9-139">Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="368f9-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="368f9-140">Fare clic su **Concedi consenso**</span><span class="sxs-lookup"><span data-stu-id="368f9-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="368f9-141">Ogni volta che si aggiunge l'autorizzazione, è necessario fare clic su **Concedi consenso** per la nuova autorizzazione per rendere effettive le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="368f9-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Immagine delle autorizzazioni di concessione](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="368f9-143">Annotare l'ID dell'applicazione e l'ID tenant:</span><span class="sxs-lookup"><span data-stu-id="368f9-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="368f9-144">Nella pagina applicazione passare a **Panoramica** e copiare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="368f9-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="368f9-146">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="368f9-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="368f9-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="368f9-147">Related topics</span></span>
- [<span data-ttu-id="368f9-148">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="368f9-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="368f9-149">Accedere a Microsoft 365 Defender con contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="368f9-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
