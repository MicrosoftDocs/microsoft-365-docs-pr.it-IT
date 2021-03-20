---
title: Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente
description: Scopri come accedere alle API di Microsoft 365 Defender per conto di un utente.
keywords: accesso, per conto di utente, api, applicazione, utente, token di accesso, token,
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
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903953"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti prereleased che possono essere sostanzialmente modificati prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Questa pagina descrive come creare un'applicazione per ottenere l'accesso a livello di codice a Microsoft 365 Defender per conto di un singolo utente.

Se è necessario l'accesso a livello di codice a Microsoft 365 Defender senza un utente definito (ad esempio, se stai scrivendo un'app in background o un daemon), vedi Creare un'app per accedere a [Microsoft 365 Defender](api-create-app-web.md)senza un utente. Se devi fornire l'accesso a più tenant, ad esempio se stai servendo un'organizzazione di grandi dimensioni o un gruppo di clienti, vedi Creare un'app con accesso partner alle API di [Microsoft 365 Defender.](api-partner-access.md) Se non si è certi del tipo di accesso necessario, vedere [Introduzione.](api-access.md)

Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API consentono di automatizzare i flussi di lavoro e di usare le funzionalità di Microsoft 365 Defender. L'accesso all'API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere Flusso del codice di autorizzazione [OAuth 2.0.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

In generale, dovrai eseguire la procedura seguente per usare queste API:

- Creare un'applicazione Azure Active Directory (Azure AD).
- Ottieni un token di accesso usando questa applicazione.
- Usa il token per accedere all'API di Microsoft 365 Defender.

In questo articolo viene illustrato come:

- Creare un'applicazione Azure AD
- Ottenere un token di accesso a Microsoft 365 Defender
- Convalidare il token

> [!NOTE]
> Quando si accede all'API di Microsoft 365 Defender per conto di un utente, sono necessarie le autorizzazioni dell'applicazione e le autorizzazioni utente corrette.

> [!TIP]
> Se hai l'autorizzazione per eseguire un'azione nel portale, hai l'autorizzazione per eseguire l'azione nell'API.

## <a name="create-an-app"></a>Creare un'app

1. Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo Amministratore** globale.

2. Passare ad **Azure Active Directory** App  >  **registrations** Nuova  >  **registrazione**.

   ![Immagine di Microsoft Azure e spostamento nella registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo scegliere un nome per l'applicazione e immettere le informazioni seguenti per l'URI di reindirizzamento, quindi selezionare **Registra**.

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - **Tipo di applicazione:** Client pubblico
   - **URI di reindirizzamento:**https://portal.azure.com

4. Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi le API di autorizzazione che l'organizzazione usa >, digita  >    >   Microsoft **Threat Protection** e seleziona Microsoft **Threat Protection.** La tua app ora può accedere a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - Scegliere **Autorizzazioni delegate**. Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident.Read,** e quindi **selezionare Aggiungi autorizzazioni**.

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > È necessario selezionare le autorizzazioni pertinenti per lo scenario. *Leggere tutti gli eventi imprevisti* è solo un esempio. Per determinare l'autorizzazione necessaria, consulta la **sezione Autorizzazioni** nell'API che vuoi chiamare.
    >
    > Ad esempio, per [eseguire query avanzate,](api-advanced-hunting.md)selezionare l'autorizzazione "Esegui query avanzate". per [isolare un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleziona l'autorizzazione "Isola computer".

5. Selezionare **Concedi il consenso dell'amministratore.** Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.

   ![Immagine delle autorizzazioni di concessione](../../media/grant-consent-delegated.PNG)

6. Registrare l'ID applicazione e l'ID tenant in un luogo sicuro. Sono elencati in **Panoramica nella** pagina dell'applicazione.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Ottenere un token di accesso

Per altre informazioni sui token di Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Ottenere un token di accesso tramite PowerShell

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>Convalidare il token

1. Copia e incolla il token in [JWT](https://jwt.ms) per decodificarlo.
1. Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.

Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` autorizzazioni:

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usare il token per accedere all'API di Microsoft 365 Defender

1. Scegli l'API che vuoi usare (eventi imprevisti o ricerca avanzata). Per altre informazioni, vedi [API supportate di Microsoft 365 Defender.](api-supported.md)
2. Nella richiesta http che stai per inviare, imposta l'intestazione di autorizzazione su , Bearer è lo schema di autorizzazione e il token è `"Bearer" <token>` il token  convalidato. 
3. Il token scadrà entro un'ora. Puoi inviare più di una richiesta durante questo periodo di tempo con lo stesso token.

Nell'esempio seguente viene illustrato come inviare una richiesta per ottenere un elenco di eventi imprevisti **tramite C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Creare un'app "Hello world"](api-hello-world.md)
- [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)
- [Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender](api-partner-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
- [Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)