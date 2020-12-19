---
title: Hello World per Microsoft 365 Defender REST API
description: Informazioni su come creare un'app e utilizzare un token per accedere alle API di Microsoft 365 Defender
keywords: app, token, Access, AAD, app, registrazione applicazioni, PowerShell, script, amministratore globale, autorizzazione, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719311"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World per Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Ottenere gli eventi imprevisti tramite uno script di PowerShell semplice

Per completare il progetto, è necessario eseguire 5-10 minuti. Questa stima di tempo include la registrazione dell'applicazione e l'applicazione del codice allo script di esempio di PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrare un'app in Azure Active Directory

1. Accedere a [Azure](https://portal.azure.com) come utente con il ruolo di **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >    >  **nuova registrazione**.

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **registra**. La selezione di un URI di reindirizzamento è facoltativa. Non sarà necessario uno per completare questo esempio.

4. Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**. L'app può ora accedere a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* è un nome precedente per Microsoft 365 Defender e non verrà visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.
   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - Scegliere **Application Permissions**  >  **Incident. Read. All** e selezionare **Add Permissions**.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

5. Selezionare **Concedi consenso amministratore**. Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi all'amministratore il consenso** per rendere effettive le autorizzazioni.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. Aggiungere un segreto all'applicazione. Selezionare **certificati & segreti**, aggiungere una descrizione al segreto, quindi fare clic su **Aggiungi**.

    > [!TIP]
    > Dopo aver selezionato **Aggiungi**, selezionare **copia il valore segreto generato**. Non sarà possibile recuperare il valore segreto dopo l'uscita.

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. Registrare l'ID dell'applicazione e l'ID del tenant in una posizione sicura. Sono elencate in **Panoramica** nella pagina dell'applicazione.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Ottenere un token utilizzando l'app e utilizzare il token per accedere all'API

Per ulteriori informazioni sui token di Azure Active Directory, vedere l' [esercitazione su Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Anche se l'esempio in questa app dimostrativa consiglia di incollare il valore segreto a scopo di testing, **non è mai necessario impostare come hardcoded i segreti** in un'applicazione in esecuzione in produzione. Una terza parte può usare il segreto per accedere alle risorse. È possibile proteggere i segreti dell'app utilizzando il [Vault Key di Azure](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Per un esempio pratico del modo in cui è possibile proteggere l'app, vedere [gestire i segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

1. Copiare lo script riportato di seguito e incollarlo nell'editor di testo preferito. Salva come **Get-Token.ps1**. È inoltre possibile eseguire il codice così com'è in PowerShell ISE, ma è necessario salvarlo, perché sarà necessario eseguirlo di nuovo quando si utilizza lo script per il recupero degli incidenti nella sezione successiva.

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

1. Copiare e incollare il token ricevuto in [JWT](https://jwt.ms) per decodificarlo.
1. *JWT* è l'acronimo di *token Web JSON*. Il token decodificato conterrà un numero di attestazioni o elementi in formato JSON. Verificare che l'attestazione dei *ruoli* all'interno del token decodificato contenga le autorizzazioni desiderate.

    Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` e le ```AdvancedHunting.Read.All``` autorizzazioni:

    ![Immagine jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Ottenere un elenco degli incidenti recenti

Lo script riportato di seguito utilizzerà **Get-Token.ps1** per accedere all'API. Viene quindi recuperato un elenco di eventi non consentiti che sono stati aggiornati l'ultima volta nelle ultime 48 ore e l'elenco viene salvato come file JSON.

> [!IMPORTANT]
> Salvare lo script nella stessa cartella in cui è stato salvato **Get-Token.ps1**.

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

Tutto finito. Ha esito positivo:

- Ha creato e registrato un'applicazione.
- Autorizzazione concessa per l'applicazione per la lettura degli avvisi.
- Connesso all'API.
- Utilizzo di uno script di PowerShell per restituire gli eventi non consentiti aggiornati nelle ultime 48 ore.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)
- [Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente](api-create-app-user-context.md)
- [Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs](api-partner-access.md)
- [Gestione dei segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
