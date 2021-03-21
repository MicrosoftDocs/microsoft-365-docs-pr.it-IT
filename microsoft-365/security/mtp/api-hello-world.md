---
title: API REST hello world per Microsoft 365 Defender
description: Scopri come creare un'app e usare un token per accedere alle API di Microsoft 365 Defender
keywords: app, token, accesso, aad, app, registrazione dell'applicazione, powershell, script, amministratore globale, autorizzazione, microsoft 365 defender
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
ms.openlocfilehash: 65319d46871282c454287af225647f89e3535c78
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924339"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>API REST hello world per Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti prereleased che possono essere sostanzialmente modificati prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Ottenere eventi imprevisti usando un semplice script di PowerShell

Il completamento del progetto dovrebbe richiedere da 5 a 10 minuti. Questa stima del tempo include la registrazione dell'applicazione e l'applicazione del codice dallo script di esempio di PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrare un'app in Azure Active Directory

1. Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo amministratore** globale.

2. Passare ad **Azure Active Directory** App  >  **registrations** Nuova  >  **registrazione**.

   ![Immagine di Microsoft Azure e spostamento nella registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo di registrazione scegliere un nome per l'applicazione, quindi selezionare **Registra.** La selezione di un URI di reindirizzamento è facoltativa. Non è necessario per completare questo esempio.

4. Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi le API di autorizzazione che l'organizzazione usa >, digita  >    >   Microsoft **Threat Protection** e seleziona Microsoft **Threat Protection.** La tua app ora può accedere a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.
   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - Scegliere **Autorizzazioni applicazione**  >  **Incident.Read.All** e selezionare Aggiungi **autorizzazioni**.

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions.PNG)

5. Selezionare **Concedi il consenso dell'amministratore.** Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. Aggiungere un segreto all'applicazione. Selezionare **Certificati & segreti**, aggiungere una descrizione al segreto, quindi selezionare **Aggiungi**.

    > [!TIP]
    > Dopo aver selezionato **Aggiungi,** selezionare **copia il valore segreto generato.** Non sarà possibile recuperare il valore segreto dopo aver lasciato.

    ![Immagine della chiave di creazione dell'app](../../media/webapp-create-key2.png)

7. Registrare l'ID applicazione e l'ID tenant in un luogo sicuro. Sono elencati in **Panoramica nella** pagina dell'applicazione.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Ottieni un token usando l'app e usa il token per accedere all'API

Per altre informazioni sui token di Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Anche se l'esempio in questa app demo ti incoraggia a incollare il valore segreto a scopo di test, non dovresti mai codificare i segreti in modo **hardcoded** in un'applicazione in esecuzione in produzione. Una terza parte potrebbe usare il segreto per accedere alle risorse. Puoi proteggere i segreti dell'app usando [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates) Per un esempio pratico di come proteggere la tua app, vedi Gestire i segreti [nelle app server con Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)

1. Copia lo script seguente e incollalo nell'editor di testo preferito. Salva con **nomeGet-Token.ps1**. È anche possibile eseguire il codice così come è in PowerShell ISE, ma è consigliabile salvarlo, perché sarà necessario eseguirlo di nuovo quando si utilizza lo script di recupero degli eventi imprevisti nella sezione successiva.

    Questo script genererà un token e lo salverà nella cartella di lavoro con il nome *Latest-token.txt*.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>Convalidare il token

1. Copia e incolla il token ricevuto in [JWT](https://jwt.ms) per decodificarlo.
1. *JWT* è *l'acronimo di JSON Web Token*. Il token decodificato conterrà un numero di elementi o attestazioni in formato JSON. Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.

    Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` autorizzazioni:

    ![Immagine jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Ottenere un elenco di eventi imprevisti recenti

Lo script seguente **userà** Get-Token.ps1per accedere all'API. Viene quindi recuperato un elenco di eventi imprevisti che sono stati aggiornati per l'ultima volta nelle ultime 48 ore e l'elenco viene salvato come file JSON.

> [!IMPORTANT]
> Salvare lo script nella stessa cartella salvata **Get-Token.ps1**.

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

Hai finito. Hai avuto esito positivo:

- È stata creata e registrata un'applicazione.
- Autorizzazione concessa all'applicazione per la lettura degli avvisi.
- Connesso all'API.
- È stato usato uno script di PowerShell per restituire gli eventi imprevisti aggiornati nelle ultime 48 ore.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)
- [Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente](api-create-app-user-context.md)
- [Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender](api-partner-access.md)
- [Gestire i segreti nelle app server con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)