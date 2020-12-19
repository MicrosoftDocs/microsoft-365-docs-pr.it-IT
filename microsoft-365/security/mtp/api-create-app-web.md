---
title: Creare un'app per accedere a Microsoft 365 Defender senza un utente
description: Informazioni su come creare un'app per accedere a Microsoft 365 Defender senza un utente.
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719357"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Creare un'app per accedere a Microsoft 365 Defender senza un utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft 365 Defender senza un utente definito, ad esempio se si sta creando un daemon o un servizio in background.

Se è necessario l'accesso a livello di programmazione a Microsoft 365 Defender per conto di uno o più utenti, vedere [creare un'app per accedere alle API di microsoft 365 Defender per conto di un utente](api-create-app-user-context.md) e [creare un'app con accesso partner alle api di Microsoft 365 Defender](api-partner-access.md). Se non si è certi del tipo di accesso necessario, vedere [Introduzione](api-access.md).

Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentono di automatizzare i flussi di lavoro e di avvalersi delle funzionalità di Microsoft 365 Defender. Questo accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, è necessario eseguire la procedura seguente per utilizzare queste API:

- Creare un'applicazione Azure Active Directory (Azure AD).
- Ottenere un token di accesso utilizzando l'applicazione.
- Utilizzare il token per accedere a Microsoft 365 Defender API.

In questo articolo viene illustrato come eseguire le operazioni seguenti:

- Creare un'applicazione Azure AD
- Ottenere un token di accesso a Microsoft 365 Defender
- Convalidare il token.

## <a name="create-an-app"></a>Creare un'app

1. Accedere a [Azure](https://portal.azure.com) come utente con il ruolo di **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >    >  **nuova registrazione**.

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo scegliere un nome per l'applicazione e quindi fare clic su **registra**.

4. Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**. L'app può ora accedere a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* è un nome precedente per Microsoft 365 Defender e non verrà visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

5. Selezionare **Autorizzazioni applicazione**. Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident. Read. All**, e quindi selezionare **Aggiungi autorizzazioni**.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > È necessario selezionare le autorizzazioni rilevanti per lo scenario. *Leggere tutti gli eventi* non consentiti è solo un esempio. Per determinare le autorizzazioni necessarie, vedere la sezione relativa alle **autorizzazioni** nell'API che si desidera chiamare.
    >
    > Ad esempio, per [eseguire query avanzate](api-advanced-hunting.md), selezionare l'autorizzazione ' Esegui query avanzate '; per [isolare un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selezionare l'autorizzazione ' isolate machine '.

6. Selezionare **Concedi consenso amministratore**. Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi all'amministratore il consenso** per rendere effettive le autorizzazioni.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

7. Per aggiungere un segreto all'applicazione, selezionare **certificati & segreti**, aggiungere una descrizione al segreto e quindi fare clic su **Aggiungi**.

    > [!TIP]
    > Dopo aver selezionato **Aggiungi**, selezionare **copia il valore segreto generato**. Non sarà possibile recuperare il valore segreto dopo l'uscita.

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

8. Registrare l'ID dell'applicazione e l'ID del tenant in una posizione sicura. Sono elencate in **Panoramica** nella pagina dell'applicazione.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

9. **Solo per microsoft 365 Defender Partners**: [seguire queste istruzioni](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) per l'accesso dei partner tramite le API di Microsoft 365 Defender, impostare la propria app come multi-tenant, in modo che possa essere disponibile in tutti i tenant una volta che si riceve il consenso di amministratore. L'accesso dei partner è **necessario** per le app di terze parti, ad esempio se si crea un'app che deve essere eseguita in più tenant dei clienti. Non è **necessario** se si crea un servizio che si desidera eseguire solo nel tenant, ad esempio un'applicazione per l'utilizzo che interagirà solo con i propri dati. Per impostare l'app come multi-tenant:

    - Andare a **autenticazione** e aggiungere https://portal.azure.com come URI di **Reindirizzamento**.

    - Nella parte inferiore della pagina, in **tipi di account supportati**, selezionare gli **account in qualsiasi** autorizzazione dell'applicazione directory organizzativa per l'app multi-tenant.

    Poiché l'applicazione interagisce con Microsoft 365 Defender per conto degli utenti, è necessario approvarla per ogni tenant su cui si intende utilizzarlo.

    L'amministratore globale di Active Directory per ogni tenant deve selezionare il collegamento di consenso e approvare l'app.

    Il collegamento di consenso ha la seguente struttura:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Le cifre `00000000-0000-0000-0000-000000000000` devono essere sostituite con l'ID dell'applicazione.  

**Fatto!** La registrazione di un'applicazione è stata completata correttamente. Vedere gli esempi riportati di seguito per l'acquisizione e la convalida dei token.

## <a name="get-an-access-token"></a>Ottenere un token di accesso

Per ulteriori informazioni sui token di Azure Active Directory, vedere l' [esercitazione su Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Anche se negli esempi di questa sezione è consigliabile incollare i valori segreti a scopo di testing, **non è mai necessario impostare come hardcoded i segreti** in un'applicazione in esecuzione in produzione. Una terza parte può usare il segreto per accedere alle risorse. È possibile proteggere i segreti dell'app utilizzando il [Vault Key di Azure](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Per un esempio pratico del modo in cui è possibile proteggere l'app, vedere [gestire i segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

### <a name="get-an-access-token-using-powershell"></a>Ottenere un token di accesso tramite PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a>Ottenere un token di accesso tramite C\#

> [!NOTE]
> Il codice seguente è stato testato con NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Creare una nuova applicazione console.

1. Installare NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

1. Aggiungere la riga seguente:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copiare e incollare il codice seguente nell'app (non dimenticare di aggiornare le tre variabili: `tenantId` , `clientId` , `appSecret` ):

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Ottenere un token di accesso tramite Python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>Ottenere un token di accesso tramite CURL

> [!NOTE]
> Curl è preinstallato in Windows 10, versione 1803 e versioni successive. Per altre versioni di Windows, scaricare e installare lo strumento direttamente dal [sito web ufficiale di curl](https://curl.haxx.se/windows/).

1. Aprire una finestra del prompt dei comandi e impostare CLIENT_ID sull'ID dell'applicazione di Azure.

1. Impostare CLIENT_SECRET per l'applicazione di Azure segreta.

1. Impostare TENANT_ID sull'ID tenant di Azure del cliente che desidera utilizzare l'app per accedere a Microsoft 365 Defender.

1. Eseguire il comando riportato di seguito:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Una risposta corretta avrà un aspetto simile al seguente:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Convalidare il token

1. Copiare e incollare il token nel [sito Web di convalida del token Web JSON, JWT,](https://jwt.ms) per decodificarlo.

1. Verificare che l'attestazione dei *ruoli* all'interno del token decodificato contenga le autorizzazioni desiderate.

   Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app, con `Incidents.Read.All` , `Incidents.ReadWrite.All` e le `AdvancedHunting.Read.All` autorizzazioni:

   ![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Utilizzare il token per accedere all'API Microsoft 365 Defender

1. Scegliere l'API che si desidera utilizzare (operazioni non consentite o ricerca avanzata). Per ulteriori informazioni, vedere [API di Microsoft 365 Defender supportate](api-supported.md).

2. Nella richiesta HTTP che si sta per inviare, impostare l'intestazione di autorizzazione su `"Bearer" <token>` , *portatore* che è lo schema di autorizzazione e *token* che è il token convalidato.

3. Il token scadrà entro un'ora. È possibile inviare più di una richiesta durante questo periodo con lo stesso token.

Nell'esempio riportato di seguito viene illustrato come inviare una richiesta per ottenere un elenco di operazioni non consentite **tramite C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Creare un'applicazione ' Hello World '](api-hello-world.md)
- [Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente](api-create-app-user-context.md)
- [Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs](api-partner-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Informazioni sui codici di errore](api-error-codes.md)
- [Gestione dei segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
