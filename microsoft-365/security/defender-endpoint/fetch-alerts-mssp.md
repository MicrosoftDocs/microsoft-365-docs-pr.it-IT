---
title: Recuperare gli avvisi dal tenant del cliente MSSP
description: Informazioni su come recuperare gli avvisi da un tenant del cliente
keywords: provider di servizi di sicurezza gestiti, mssp, configurare, integrazione
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770770"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="97577-104">Recuperare gli avvisi dal tenant del cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="97577-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97577-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="97577-105">**Applies to:**</span></span>
- [<span data-ttu-id="97577-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="97577-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="97577-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="97577-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97577-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="97577-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="97577-109">Questa azione viene eseguita dal provider di servizi condivisi.</span><span class="sxs-lookup"><span data-stu-id="97577-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="97577-110">Esistono due modi per recuperare gli avvisi:</span><span class="sxs-lookup"><span data-stu-id="97577-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="97577-111">Utilizzo del metodo SIEM</span><span class="sxs-lookup"><span data-stu-id="97577-111">Using the SIEM method</span></span>
- <span data-ttu-id="97577-112">Uso delle API</span><span class="sxs-lookup"><span data-stu-id="97577-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="97577-113">Recuperare gli avvisi nel SIEM</span><span class="sxs-lookup"><span data-stu-id="97577-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="97577-114">Per recuperare gli avvisi nel sistema SIEM, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="97577-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="97577-115">Passaggio 1: Creare un'applicazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="97577-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="97577-116">Passaggio 2: ottenere i token di accesso e aggiornamento dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="97577-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="97577-117">Passaggio 3: consentire l'applicazione in Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="97577-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="97577-118">Passaggio 1: Creare un'applicazione in Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="97577-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="97577-119">Dovrai creare un'applicazione e concedervi le autorizzazioni per recuperare gli avvisi dal tenant di Microsoft Defender for Endpoint del cliente.</span><span class="sxs-lookup"><span data-stu-id="97577-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="97577-120">Accedere al portale [di Azure AD](https://aad.portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="97577-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="97577-121">Seleziona **Azure Active Directory**  >  **registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="97577-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="97577-122">Fare **clic su Nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="97577-122">Click **New registration**.</span></span>

4. <span data-ttu-id="97577-123">Specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="97577-123">Specify the following values:</span></span>

    - <span data-ttu-id="97577-124">Nome: \<Tenant_name\> SIEM MSSP Connector (sostituire Tenant_name con il nome visualizzato del tenant)</span><span class="sxs-lookup"><span data-stu-id="97577-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="97577-125">Tipi di account supportati: account solo in questa directory organizzativa</span><span class="sxs-lookup"><span data-stu-id="97577-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="97577-126">URI di reindirizzamento: selezionare Web e digitare `https://<domain_name>/SiemMsspConnector` (sostituire <domain_name> con il nome del tenant)</span><span class="sxs-lookup"><span data-stu-id="97577-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="97577-127">Fare clic **su Registra**.</span><span class="sxs-lookup"><span data-stu-id="97577-127">Click **Register**.</span></span> <span data-ttu-id="97577-128">L'applicazione viene visualizzata nell'elenco delle applicazioni di cui si è proprietari.</span><span class="sxs-lookup"><span data-stu-id="97577-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="97577-129">Selezionare l'applicazione, quindi fare clic su **Panoramica.**</span><span class="sxs-lookup"><span data-stu-id="97577-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="97577-130">Copiare il valore dal **campo ID applicazione (client)** in un luogo sicuro, sarà necessario nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="97577-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="97577-131">Seleziona **Certificati & segreti** nel nuovo pannello applicazioni.</span><span class="sxs-lookup"><span data-stu-id="97577-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="97577-132">Fare **clic su Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="97577-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="97577-133">Descrizione: immettere una descrizione per la chiave.</span><span class="sxs-lookup"><span data-stu-id="97577-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="97577-134">Scadenza: selezionare **Tra 1 anno**</span><span class="sxs-lookup"><span data-stu-id="97577-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="97577-135">Fare **clic** su Aggiungi, copiare il valore del segreto client in un luogo sicuro, sarà necessario nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="97577-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="97577-136">Passaggio 2: ottenere i token di accesso e aggiornamento dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="97577-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="97577-137">Questa sezione illustra come usare uno script di PowerShell per ottenere i token dal tenant del cliente.</span><span class="sxs-lookup"><span data-stu-id="97577-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="97577-138">Questo script usa l'applicazione del passaggio precedente per ottenere i token di accesso e aggiornamento usando il codice di autorizzazione OAuth Flow.</span><span class="sxs-lookup"><span data-stu-id="97577-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="97577-139">Dopo aver fornito le credenziali, dovrai concedere il consenso all'applicazione in modo che l'applicazione sia disponibile nel tenant del cliente.</span><span class="sxs-lookup"><span data-stu-id="97577-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="97577-140">Crea una nuova cartella e deno nome: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="97577-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="97577-141">Scaricare il [modulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) e salvarlo nella `MsspTokensAcquisition` cartella.</span><span class="sxs-lookup"><span data-stu-id="97577-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="97577-142">Nella riga 30 sostituire `authorzationUrl` con `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="97577-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="97577-143">Creare un file con il contenuto seguente e salvarlo con il nome `MsspTokensAcquisition.ps1` nella cartella:</span><span class="sxs-lookup"><span data-stu-id="97577-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="97577-144">Aprire un prompt dei comandi di PowerShell con privilegi elevati nella `MsspTokensAcquisition` cartella.</span><span class="sxs-lookup"><span data-stu-id="97577-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="97577-145">Eseguire il comando seguente: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="97577-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="97577-146">Immettere i comandi seguenti: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="97577-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="97577-147">Sostituisci \<client_id\> con **l'ID applicazione (client)** ottenuto dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="97577-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="97577-148">Sostituire \<app_key\> con il segreto **client** creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="97577-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="97577-149">Sostituire \<customer_tenant_id\> con **l'ID tenant del cliente.**</span><span class="sxs-lookup"><span data-stu-id="97577-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="97577-150">Ti verrà richiesto di fornire le credenziali e il consenso.</span><span class="sxs-lookup"><span data-stu-id="97577-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="97577-151">Ignorare il reindirizzamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="97577-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="97577-152">Nella finestra di PowerShell riceverai un token di accesso e un token di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="97577-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="97577-153">Salvare il token di aggiornamento per configurare il connettore SIEM.</span><span class="sxs-lookup"><span data-stu-id="97577-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="97577-154">Passaggio 3: Consentire l'applicazione in Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="97577-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="97577-155">Dovrai consentire l'applicazione creata in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="97577-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="97577-156">Per consentire l'applicazione,  è necessario disporre dell'autorizzazione Gestione impostazioni di sistema del portale.</span><span class="sxs-lookup"><span data-stu-id="97577-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="97577-157">In caso contrario, dovrai richiedere al cliente di consentire l'applicazione per te.</span><span class="sxs-lookup"><span data-stu-id="97577-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="97577-158">Passare a `https://securitycenter.windows.com?tid=<customer_tenant_id>` (sostituire \<customer_tenant_id\> con l'ID tenant del cliente.</span><span class="sxs-lookup"><span data-stu-id="97577-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="97577-159">Fare **clic Impostazioni**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="97577-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="97577-160">Selezionare la **scheda MSSP.**</span><span class="sxs-lookup"><span data-stu-id="97577-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="97577-161">Immetti **l'ID** applicazione dal primo passaggio e **l'ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="97577-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="97577-162">Fare **clic su Autorizza applicazione.**</span><span class="sxs-lookup"><span data-stu-id="97577-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="97577-163">Ora puoi scaricare il file di configurazione pertinente per il tuo SIEM e connetterti all'API Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="97577-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="97577-164">Per ulteriori informazioni, vedere [Pull alerts to your SIEM tools.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="97577-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="97577-165">Nel file di configurazione di ArcSight/File delle proprietà di autenticazione Splunk scrivi manualmente la chiave dell'applicazione impostando il valore segreto.</span><span class="sxs-lookup"><span data-stu-id="97577-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="97577-166">Invece di acquisire un token di aggiornamento nel portale, usa lo script del passaggio precedente per acquisire un token di aggiornamento (o acquistarlo con altri mezzi).</span><span class="sxs-lookup"><span data-stu-id="97577-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="97577-167">Recuperare gli avvisi dal tenant del cliente MSSP usando le API</span><span class="sxs-lookup"><span data-stu-id="97577-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="97577-168">Per informazioni su come recuperare gli avvisi con l'API REST, vedi [Eseguire il pull degli avvisi tramite l'API REST.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="97577-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="97577-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97577-169">See also</span></span>
- [<span data-ttu-id="97577-170">Concedere a MSSP l'accesso al portale</span><span class="sxs-lookup"><span data-stu-id="97577-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="97577-171">Accedere al portale clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="97577-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="97577-172">Configurare le notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="97577-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
