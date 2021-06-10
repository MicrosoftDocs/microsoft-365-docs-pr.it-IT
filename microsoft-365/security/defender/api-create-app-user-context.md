---
title: Creare un'app per accedere Microsoft 365 DEFENDER API per conto di un utente
description: Scopri come accedere alle MICROSOFT 365 Defender per conto di un utente.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068666"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Creare un'app per accedere Microsoft 365 DEFENDER API per conto di un utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Questa pagina descrive come creare un'applicazione per ottenere l'accesso a livello di codice a Microsoft 365 Defender per conto di un singolo utente.

Se hai bisogno dell'accesso a livello di codice a Microsoft 365 Defender senza un utente definito (ad esempio, se stai scrivendo un'app in background o un daemon), vedi Creare un'app per accedere [a Microsoft 365 Defender](api-create-app-web.md)senza un utente. Se devi fornire l'accesso a più tenant, ad esempio se stai servendo un'organizzazione di grandi dimensioni o un gruppo di clienti, vedi Creare un'app con accesso partner alle API di [Microsoft 365 Defender.](api-partner-access.md) Se non si è certi del tipo di accesso necessario, vedere [Introduzione.](api-access.md)

Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API consentono di automatizzare i flussi di lavoro e di usare Microsoft 365 funzionalità di Defender. L'accesso all'API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, dovrai eseguire la procedura seguente per usare queste API:

- Creare un'Azure Active Directory (Azure AD).
- Ottieni un token di accesso usando questa applicazione.
- Usa il token per accedere Microsoft 365'API Defender.

In questo articolo viene illustrato come:

- Creare un'applicazione Azure AD
- Ottenere un token di accesso a Microsoft 365 Defender
- Convalidare il token

> [!NOTE]
> Quando si accede Microsoft 365'API Defender per conto di un utente, sono necessarie le autorizzazioni dell'applicazione e le autorizzazioni utente corrette.

> [!TIP]
> Se hai l'autorizzazione per eseguire un'azione nel portale, hai l'autorizzazione per eseguire l'azione nell'API.

## <a name="create-an-app"></a>Creare un'app

1. Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo Amministratore** globale.

2. Passare **a** Azure Active Directory  >  **app Nuove**  >  **registrazioni**.

   ![Immagine dell'Microsoft Azure e della navigazione per la registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo scegliere un nome per l'applicazione e immettere le informazioni seguenti per l'URI di reindirizzamento, quindi selezionare **Registra**.

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - **Tipo di applicazione:** Client pubblico
   - **URI di reindirizzamento:**https://portal.azure.com

4. Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi API di autorizzazione che l'organizzazione usa  >    >   >, digita **Microsoft Threat Protection** e seleziona **Microsoft Threat Protection**. La tua app può ora accedere Microsoft 365 Defender.

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

Per altre informazioni sui token Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

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

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usare il token per accedere all'API Microsoft 365 Defender

1. Scegli l'API che vuoi usare (eventi imprevisti o ricerca avanzata). Per altre informazioni, vedi [API Microsoft 365 Defender supportate.](api-supported.md)
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

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Creare un'app "Hello world"](api-hello-world.md)
- [Creare un'app per accedere Microsoft 365 Defender senza un utente](api-create-app-web.md)
- [Creare un'app con accesso partner multi-tenant alle API Microsoft 365 Defender](api-partner-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
- [Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)