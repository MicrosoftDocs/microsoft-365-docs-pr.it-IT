---
title: Hello World per l'API REST di Microsoft Threat Protection
description: Informazioni su come creare un'app e utilizzare un token per accedere alle API di Microsoft Threat Protection
keywords: app, token, Access, AAD, app, registrazione applicazioni, PowerShell, script, amministratore globale, autorizzazione
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
ms.openlocfilehash: cdf3f6a0c007763d2772233b1a299d59c931b2e5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201328"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hello World per l'API REST di Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Ottenere gli eventi imprevisti tramite uno script di PowerShell semplice

### <a name="how-long-it-takes-to-go-through-this-example"></a>Quanto tempo è necessario per passare attraverso questo esempio?
Sono necessari solo 5 minuti in due passaggi:
- Registrazione applicazione
- Esempi di utilizzo: richiede solo copia/incolla di uno script di PowerShell breve

### <a name="do-i-need-a-permission-to-connect"></a>È necessaria un'autorizzazione per la connessione?
Per la fase di registrazione dell'applicazione, è necessario disporre di un ruolo di **amministratore globale** nel tenant di Azure Active Directory (Azure ad).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

1. Accedere a [Azure](https://portal.azure.com) con l'utente **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**. 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **registra**.

4. Consentire all'applicazione di accedere a Microsoft Defender ATP e assegnargli l'autorizzazione **Leggi tutte le operazioni** non consentite:

   - Nella pagina applicazione selezionare **autorizzazioni API**  >  **Aggiungi**autorizzazioni API  >  **l'organizzazione utilizza** > tipo **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**.

   >[!NOTE]
   >Microsoft Threat Protection non viene visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)

   - Scegliere **Application Permissions**  >  **Incident. Read. All** > selezionare su **Add Permissions**

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >È necessario selezionare le autorizzazioni rilevanti. 

     Ad esempio,

     - Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare.

5. Selezionare **Concedi consenso amministratore**

    - >[!NOTE]
      > Ogni volta che si aggiunge l'autorizzazione, è necessario selezionare su **Concedi consenso** per la nuova autorizzazione per rendere effettive le autorizzazioni.

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. Aggiungere un segreto all'applicazione.

    - Selezionare **certificati & segreti**, aggiungere una descrizione al segreto e selezionare **Aggiungi**.

    >[!IMPORTANT]
    > Dopo aver selezionato **Aggiungi**, **copiare il valore segreto generato**. Non sarà possibile recuperare dopo l'uscita.

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. Annotare l'ID dell'applicazione e l'ID tenant:

   - Nella pagina applicazione passare a **Panoramica** e copiare quanto segue:

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)


Fatto! L'applicazione è stata registrata correttamente.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Passaggio 2: ottenere un token utilizzando l'app e utilizzare questo token per accedere all'API.

-   Copiare lo script riportato di seguito in PowerShell ISE o in un editor di testo e salvarlo con il nome "**Get-Token.ps1**"
-   L'esecuzione di questo script genererà un token e lo salverà nella cartella di lavoro con il nome "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   Verifica integrità:<br>
Eseguire lo script.<br>
Nel browser Vai a: https://jwt.ms/ <br>
Copiare il token (il contenuto del file di Latest-token.txt).<br>
Incolla nella casella superiore.<br>
Cercare la sezione "Roles". Individuare il ```Incidents.Read.All``` ruolo.<br>
L'esempio riportato di seguito è costituito da un'app con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` autorizzazioni.

![Immagine jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Consente di ottenere gli incidenti!

-   Lo script riportato di seguito utilizzerà **Get-Token.ps1** per accedere all'API e otterrà gli eventi non consentiti per l'ultimo aggiornamento nelle ultime 48 ore.
-   Salvare lo script nella stessa cartella in cui è stato salvato lo script precedente **Get-Token.ps1**. 
-   Lo script un file JSON con i dati nella stessa cartella degli script.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Tutto finito. È possibile eseguire correttamente le operazioni seguenti:
-   Creazione e registrazione e applicazione
-   Autorizzazione concessa per l'applicazione per la lettura degli avvisi
-   Connesso l'API
-   Utilizzato uno script di PowerShell per restituire gli incidenti creati nelle ultime 48 ore



## <a name="related-topic"></a>Argomento correlato
- [Accedere alle API di Microsoft Threat Protection](api-access.md)
- [Accedere a Microsoft Threat Protection con il contesto dell'applicazione](api-create-app-web.md)
- [Accedere a Microsoft Threat Protection con contesto utente](api-create-app-user-context.md)
