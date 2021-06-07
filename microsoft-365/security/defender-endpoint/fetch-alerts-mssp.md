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
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Recuperare gli avvisi dal tenant del cliente MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Questa azione viene eseguita dal provider di servizi condivisi.


Esistono due modi per recuperare gli avvisi:
- Utilizzo del metodo SIEM
- Uso delle API

## <a name="fetch-alerts-into-your-siem"></a>Recuperare gli avvisi nel SIEM

Per recuperare gli avvisi nel sistema SIEM, è necessario eseguire la procedura seguente:

Passaggio 1: Creare un'applicazione di terze parti

Passaggio 2: ottenere i token di accesso e aggiornamento dal tenant del cliente
 
Passaggio 3: consentire l'applicazione in Microsoft Defender Security Center
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Passaggio 1: Creare un'applicazione in Azure Active Directory (Azure AD)
 
Dovrai creare un'applicazione e concedervi le autorizzazioni per recuperare gli avvisi dal tenant di Microsoft Defender for Endpoint del cliente.

1. Accedere al portale [di Azure AD](https://aad.portal.azure.com/).

2. Seleziona **Azure Active Directory**  >  **registrazioni app**.
 
3. Fare **clic su Nuova registrazione**.

4. Specificare i valori seguenti:

    - Nome: \<Tenant_name\> SIEM MSSP Connector (sostituire Tenant_name con il nome visualizzato del tenant)
 
    - Tipi di account supportati: account solo in questa directory organizzativa 
    - URI di reindirizzamento: selezionare Web e digitare `https://<domain_name>/SiemMsspConnector` (sostituire <domain_name> con il nome del tenant)

5. Fare clic **su Registra**. L'applicazione viene visualizzata nell'elenco delle applicazioni di cui si è proprietari.

6. Selezionare l'applicazione, quindi fare clic su **Panoramica.**

7. Copiare il valore dal **campo ID applicazione (client)** in un luogo sicuro, sarà necessario nel passaggio successivo.

8. Seleziona **Certificati & segreti** nel nuovo pannello applicazioni.

9. Fare **clic su Nuovo segreto client**.

    - Descrizione: immettere una descrizione per la chiave.
    - Scadenza: selezionare **Tra 1 anno**

 
10. Fare **clic** su Aggiungi, copiare il valore del segreto client in un luogo sicuro, sarà necessario nel passaggio successivo.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Passaggio 2: ottenere i token di accesso e aggiornamento dal tenant del cliente
Questa sezione illustra come usare uno script di PowerShell per ottenere i token dal tenant del cliente. Questo script usa l'applicazione del passaggio precedente per ottenere i token di accesso e aggiornamento usando il codice di autorizzazione OAuth Flow.

Dopo aver fornito le credenziali, dovrai concedere il consenso all'applicazione in modo che l'applicazione sia disponibile nel tenant del cliente.


1. Crea una nuova cartella e deno nome: `MsspTokensAcquisition` .

2. Scaricare il [modulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) e salvarlo nella `MsspTokensAcquisition` cartella.

    >[!NOTE]
    >Nella riga 30 sostituire `authorzationUrl` con `authorizationUrl` .

3. Creare un file con il contenuto seguente e salvarlo con il nome `MsspTokensAcquisition.ps1` nella cartella:
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
4. Aprire un prompt dei comandi di PowerShell con privilegi elevati nella `MsspTokensAcquisition` cartella.

5. Eseguire il comando seguente: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Immettere i comandi seguenti: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Sostituisci \<client_id\> con **l'ID applicazione (client)** ottenuto dal passaggio precedente.
    - Sostituire \<app_key\> con il segreto **client** creato nel passaggio precedente.
    - Sostituire \<customer_tenant_id\> con **l'ID tenant del cliente.** 
 

7. Ti verrà richiesto di fornire le credenziali e il consenso. Ignorare il reindirizzamento della pagina.

8. Nella finestra di PowerShell riceverai un token di accesso e un token di aggiornamento. Salvare il token di aggiornamento per configurare il connettore SIEM. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Passaggio 3: Consentire l'applicazione in Microsoft Defender Security Center
Dovrai consentire l'applicazione creata in Microsoft Defender Security Center.
 
Per consentire l'applicazione,  è necessario disporre dell'autorizzazione Gestione impostazioni di sistema del portale. In caso contrario, dovrai richiedere al cliente di consentire l'applicazione per te.

1. Passare a `https://securitycenter.windows.com?tid=<customer_tenant_id>` (sostituire \<customer_tenant_id\> con l'ID tenant del cliente.

2. Fare **clic Impostazioni**  >  **SIEM**. 

3. Selezionare la **scheda MSSP.**

4. Immetti **l'ID** applicazione dal primo passaggio e **l'ID tenant**.

5. Fare **clic su Autorizza applicazione.** 

 
Ora puoi scaricare il file di configurazione pertinente per il tuo SIEM e connetterti all'API Defender for Endpoint. Per ulteriori informazioni, vedere [Pull alerts to your SIEM tools.](configure-siem.md)
 

- Nel file di configurazione di ArcSight/File delle proprietà di autenticazione Splunk scrivi manualmente la chiave dell'applicazione impostando il valore segreto.
- Invece di acquisire un token di aggiornamento nel portale, usa lo script del passaggio precedente per acquisire un token di aggiornamento (o acquistarlo con altri mezzi).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Recuperare gli avvisi dal tenant del cliente MSSP usando le API
 
Per informazioni su come recuperare gli avvisi con l'API REST, vedi [Eseguire il pull degli avvisi tramite l'API REST.](pull-alerts-using-rest-api.md)


## <a name="see-also"></a>Vedere anche
- [Concedere a MSSP l'accesso al portale](grant-mssp-access.md)
- [Accedere al portale clienti MSSP](access-mssp-portal.md)
- [Configurare le notifiche di avviso](configure-mssp-notifications.md)
