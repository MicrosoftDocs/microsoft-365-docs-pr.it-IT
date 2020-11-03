---
title: Creare un'app per accedere a Microsoft 365 Defender senza un utente
description: Informazioni su come creare un'app per accedere a Microsoft 365 Defender senza un utente
keywords: app, Access, API, creare
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846069"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Creare un'app per accedere a Microsoft 365 Defender senza un utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft 365 Defender senza un utente. Se è necessario l'accesso a livello di programmazione a Microsoft 365 Defender per conto di un utente, vedere [ottenere l'accesso con il contesto utente](api-create-app-user-context.md). Se non si è certi di quale accesso è necessario, vedere [Introduzione](api-access.md).

Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentono di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di Microsoft 365 Defender. L'accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, è necessario eseguire la procedura seguente per utilizzare le API:
- Creare un'applicazione Azure Active Directory (Azure AD).
- Ottenere un token di accesso utilizzando l'applicazione.
- Utilizzare il token per accedere a Microsoft 365 Defender API.

In questo articolo viene illustrato come creare un'applicazione Azure AD, ottenere un token di accesso a Microsoft 365 Defender e convalidare il token.

## <a name="create-an-app"></a>Creare un'app

1. Accedere a [Azure](https://portal.azure.com) con un utente che ha il ruolo di **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**. 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **registra**.

4. Per consentire all'app di accedere a Microsoft 365 Defender e assegnargli le autorizzazioni, nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi autorizzazione** API  >  **l'organizzazione utilizza** >, digitare **Microsoft 365 Defender** e quindi selezionare **Microsoft 365 Defender**.

   > [!NOTE]
   > Microsoft 365 Defender non viene visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)

   - Selezionare **Autorizzazioni applicazione** > scegliere le autorizzazioni rilevanti per lo scenario, ad esempio, **Incident. Read. All** , quindi selezionare **Aggiungi autorizzazioni**.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >È necessario selezionare le autorizzazioni rilevanti per lo scenario, **' Leggi tutti gli incidenti '** è solo un esempio. Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare.

5. Selezionare **Concedi consenso**.

     > [!NOTE]
     > Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi consenso** per rendere effettive le nuove autorizzazioni.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. Per aggiungere un segreto all'applicazione, selezionare **certificati & segreti** , aggiungere una descrizione al segreto e quindi fare clic su **Aggiungi**.

    > [!NOTE]
    > Dopo aver selezionato **Aggiungi** , selezionare **copia il valore segreto generato**. Non sarà possibile recuperare questo valore dopo l'uscita.

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. Annotare l'ID dell'applicazione e l'ID del tenant. Nella pagina applicazione passare a **Panoramica** e copiare quanto segue.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

8. **Solo per i partner di Microsoft 365 Defender**. [Seguire le istruzioni](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)riportate di seguito. Impostare l'app come multi-tenanted (disponibile in tutti i tenant dopo il consenso). Questo è **necessario** per le app di terze parti (ad esempio, se si crea un'app che deve essere eseguita in più tenant dei clienti). Non è **necessario** se si crea un servizio che si desidera eseguire solo nel tenant (ad esempio, se si crea un'applicazione per il proprio utilizzo che interagirà solo con i propri dati). Per impostare l'app come multi-tenant:

    - Andare a **autenticazione** e aggiungere https://portal.azure.com come URI di **Reindirizzamento**.

    - Nella parte inferiore della pagina, in **tipi di account supportati** , selezionare gli **account in qualsiasi** autorizzazione dell'applicazione directory organizzativa per l'app multi-tenant.

    È necessario che l'applicazione venga approvata in ogni tenant in cui si intende utilizzarla. Ciò è dovuto al fatto che l'applicazione interagisce con Microsoft 365 Defender per conto del cliente.

    Se si sta scrivendo un'app di terze parti, l'utente o il cliente deve selezionare il collegamento di consenso e approvare l'app. Il consenso dovrebbe essere effettuato con un utente che dispone di privilegi amministrativi in Active Directory.

    Il collegamento di consenso è formato come indicato di seguito: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Dove 00000000-0000-0000-0000-000000000000 viene sostituito con l'ID dell'applicazione.


**Fatto!** La registrazione di un'applicazione è stata completata correttamente. Vedere gli esempi riportati di seguito per l'acquisizione e la convalida dei token.

## <a name="get-an-access-token"></a>Ottenere un token di accesso

Per ulteriori informazioni sui token di Azure AD, vedere l' [esercitazione di Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>Utilizzo di PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>Utilizzare C#:

Il codice seguente è stato testato con NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Creare una nuova applicazione console.
1. Installare NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Aggiungere gli elementi seguenti:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copiare e incollare il codice seguente nell'app (non dimenticare di aggiornare le tre variabili: ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Utilizzare Python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Utilizzo di curl

> [!NOTE]
> La procedura seguente presuppone che curl per Windows sia già installato nel computer in uso.

1. Aprire una finestra del prompt dei comandi e impostare CLIENT_ID sull'ID dell'applicazione di Azure.
1. Impostare CLIENT_SECRET per l'applicazione di Azure segreta.
1. Impostare TENANT_ID sull'ID tenant di Azure del cliente che desidera utilizzare l'app per accedere a Microsoft 365 Defender.
1. Eseguire il comando seguente:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Si otterrà una risposta nel formato seguente:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Convalidare il token

Assicurarsi di aver ottenuto il token corretto:

1. Copiare e incollare il token ottenuto nel passaggio precedente in [JWT](https://jwt.ms) per decodificarlo.
1. Convalidare che si ottiene un'attestazione di ' ruoli ' con le autorizzazioni desiderate
1. Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` autorizzazioni:

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>Utilizzare il token per accedere a Microsoft 365 Defender API

1. Scegliere l'API che si desidera utilizzare. Per ulteriori informazioni, vedere [API di Microsoft 365 Defender supportate](api-supported.md).

2. Impostare l'intestazione di autorizzazione nella richiesta HTTP inviata a "portatore {token}" (il portatore è lo schema di autorizzazione).

3. La data di scadenza del token è di un'ora. È possibile inviare più di una richiesta con lo stesso token.

Di seguito è riportato un esempio di invio di una richiesta per ottenere un elenco di operazioni non consentite **tramite C#** : 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>Argomenti correlati
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Accedere a Microsoft 365 Defender con contesto dell'applicazione](api-create-app-web.md)
- [Accedere a Microsoft 365 Defender con contesto utente](api-create-app-user-context.md)
