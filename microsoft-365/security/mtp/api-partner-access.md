---
title: Accesso partner tramite API di Microsoft Threat Protection
description: Informazioni su come creare un'applicazione AAD per ottenere l'accesso programmatico a Microsoft Threat Protection per conto dei clienti
keywords: partner, accesso, API, multi tenant, consenso, token di accesso, app
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
ms.openlocfilehash: d78996c0cd37a6b82edde52367b04647560d5cf7
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650357"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a>Accesso partner tramite API di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


In questa pagina viene descritto come creare un'applicazione AAD per ottenere l'accesso programmatico a Microsoft Threat Protection per conto dei clienti.

Microsoft Threat Protection espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentono di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di protezione dalle minacce di Microsoft. L'accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, è necessario eseguire la procedura seguente per utilizzare le API:
- Creare un'applicazione AAD **multi-tenant** .
- Ottenere autorizzato (consenso) dall'amministratore dei clienti per l'applicazione per accedere alle risorse di Microsoft Threat Protection di cui ha bisogno.
- Ottenere un token di accesso utilizzando l'applicazione.
- Utilizzare il token per accedere all'API di Microsoft Threat Protection.

Nella procedura seguente viene descritto come creare un'applicazione AAD, ottenere un token di accesso a Microsoft Threat Protection e convalidare il token.

## <a name="create-the-multi-tenant-app"></a>Creare l'app multi-tenant

1. Accedere al tenant di [Azure](https://portal.azure.com) con un utente che ha un ruolo di **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**. 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo di registrazione:

    - Scegliere un nome per l'applicazione.

    - Tipi di account supportati-account in qualsiasi directory organizzativa.

    - Reindirizza URI-Type: Web, URI: https://portal.azure.com

    ![Immagine della registrazione dell'applicazione partner di Microsoft Azure](../../media/atp-api-new-app-partner.png)


4. Consentire all'applicazione di accedere a Microsoft Threat Protection e assegnargli il set minimo di autorizzazioni necessarie per completare l'integrazione.

   - Nella pagina applicazione fare clic su **autorizzazioni API**  >  **Aggiungi**autorizzazioni API  >  **l'organizzazione utilizza** > tipo **Microsoft Threat Protection** e fare clic su **Microsoft Threat Protection**.

   >[!NOTE]
   >Microsoft Threat Protection non viene visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>Autorizzazioni API richieste

   Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare. 

   Nell'esempio seguente vengono utilizzate le autorizzazioni **' Leggi tutti gli incidenti '** :

   Scegliere le autorizzazioni per l' **applicazione**operazioni non consentite  >  **. tutti** > fare clic su **Aggiungi autorizzazioni**

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)


5. Fare clic su **Concedi consenso**

    >[!NOTE]
    >Ogni volta che si aggiunge l'autorizzazione, è necessario fare clic su **Concedi consenso** per la nuova autorizzazione per rendere effettive le autorizzazioni.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. Aggiungere un segreto all'applicazione.

    - Fare clic su **certificati & segreti**, aggiungere una descrizione al segreto e fare clic su **Aggiungi**.

    >[!IMPORTANT]
    > Dopo aver selezionato **Aggiungi**, **copiare il valore segreto generato**. Non sarà possibile recuperare dopo l'uscita.

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. Annotare l'ID dell'applicazione:

   - Nella pagina applicazione passare a **Panoramica** e copiare quanto segue:

   ![Immagine dell'ID app creato](../../media/app-id.png)

8. Aggiungere l'applicazione al tenant del cliente.

    È necessario che l'applicazione venga approvata in ogni tenant del cliente in cui si intende utilizzarla. Ciò è dovuto al fatto che l'applicazione interagisce con l'applicazione Microsoft Threat Protection per conto del cliente.

    Un utente con **amministratore globale** dal tenant del cliente deve fare clic sul collegamento di consenso e approvare l'applicazione.

    Il collegamento di consenso ha il formato seguente:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Dove 00000000-0000-0000-0000-000000000000 deve essere sostituito con l'ID dell'applicazione

    Dopo aver fatto clic sul collegamento di consenso, effettuare l'accesso con l'amministratore globale del tenant del cliente e acconsentire l'applicazione.

    ![Immagine del consenso](../../media/app-consent-partner.png)

    Inoltre, è necessario chiedere al cliente il proprio ID tenant e salvarlo per un utilizzo futuro quando si acquisisce il token.

- **Fatto!** La registrazione di un'applicazione è stata completata correttamente. 
- Vedere gli esempi riportati di seguito per l'acquisizione e la convalida dei token.

## <a name="get-an-access-token-examples"></a>Ottenere un esempio di token di accesso:

>[!NOTE]
> Per ottenere il token di accesso per conto del cliente, utilizzare l'ID tenant del cliente nelle acquisizioni di token seguenti.

<br>Per ulteriori informazioni su token AAD, fare riferimento a [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>Utilizzo di PowerShell

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

### <a name="using-c"></a>Utilizzo di C#:

>Il codice riportato di seguito è stato testato con NuGet Microsoft. IdentityModel. clients. ActiveDirectory

- Creare una nuova applicazione console
- Installazione di NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Aggiungere il seguente utilizzo

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Copia/incolla il codice riportato di seguito nell'applicazione (non dimenticare di aggiornare le 3 variabili: ```tenantId, appId, appSecret``` )

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>Utilizzo di curl

> [!NOTE]
> Nella procedura seguente è già installato nel computer l'arricciatura supposta per Windows.

- Aprire una finestra di comando
- Impostare CLIENT_ID sull'ID applicazione di Azure
- Impostare CLIENT_SECRET per l'applicazione segreta di Azure
- Impostare TENANT_ID sull'ID tenant di Azure del cliente che desidera utilizzare l'applicazione per accedere all'applicazione Microsoft Threat Protection
- Eseguire il comando riportato di seguito:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Si otterrà una risposta al modulo:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Convalidare il token

Verifica dell'integrità per assicurarsi di avere un token corretto:

- Copia/incolla in [JWT](https://jwt.ms) il token ottenuto nel passaggio precedente per decodificarlo
- Convalidare si ottiene un'attestazione di "ruoli" con le autorizzazioni desiderate
- Nello screenshot riportato di seguito, è possibile visualizzare un token decodificato acquisito da un'applicazione con più autorizzazioni per Microsoft Threat Protection:
- L'attestazione "TID" è l'ID tenant a cui appartiene il token.

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>Utilizzare il token per accedere all'API di Microsoft Threat Protection

- Scegliere l'API che si desidera utilizzare, per ulteriori informazioni, vedere [supported Microsoft Threat Protection Apis](api-supported.md)
- Impostare l'intestazione di autorizzazione nella richiesta HTTP inviata a "portatore {token}" (il portatore è lo schema di autorizzazione)
- La data di scadenza del token è di 1 ora (è possibile inviare più di una richiesta con lo stesso token)

- Esempio di invio di una richiesta per ottenere un elenco di operazioni non consentite **tramite C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a>Argomenti correlati 

- [Accedere alle API di Microsoft Threat Protection](api-access.md)
- [Accedere a Microsoft Threat Protection con il contesto dell'applicazione](api-create-app-web.md)
- [Accedere a Microsoft Threat Protection con contesto utente](api-create-app-user-context.md)
