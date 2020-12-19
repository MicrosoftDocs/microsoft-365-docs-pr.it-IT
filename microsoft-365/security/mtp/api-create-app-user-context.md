---
title: Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente
description: Informazioni su come accedere alle API di Microsoft 365 Defender per conto di un utente.
keywords: accesso, per conto dell'utente, dell'API, dell'applicazione, dell'utente, del token di accesso, del token,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719417"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft 365 Defender per conto di un singolo utente.

Se è necessario l'accesso a livello di programmazione a Microsoft 365 Defender senza un utente definito (ad esempio, se si sta scrivendo un'app o un daemon in background), vedere [creare un'app per accedere a microsoft 365 Defender senza un utente](api-create-app-web.md). Se è necessario fornire l'accesso per più tenant, ad esempio se si sta servendo un'organizzazione di grandi dimensioni o un gruppo di clienti, vedere [creare un'app con accesso partner a Microsoft 365 Defender Apis](api-partner-access.md). Se non si è certi del tipo di accesso necessario, vedere [Introduzione](api-access.md).

Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentono di automatizzare i flussi di lavoro e di avvalersi delle funzionalità di Microsoft 365 Defender. Questo accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, è necessario eseguire la procedura seguente per utilizzare queste API:

- Creare un'applicazione Azure Active Directory (Azure AD).
- Ottenere un token di accesso utilizzando l'applicazione.
- Utilizzare il token per accedere a Microsoft 365 Defender API.

In questo articolo viene illustrato come eseguire le operazioni seguenti:

- Creare un'applicazione Azure AD
- Ottenere un token di accesso a Microsoft 365 Defender
- Convalidare il token

> [!NOTE]
> Quando si accede a Microsoft 365 Defender API per conto di un utente, è necessario disporre delle autorizzazioni appropriate per l'applicazione e delle autorizzazioni utente.

> [!TIP]
> Se si dispone dell'autorizzazione necessaria per eseguire un'azione nel portale, è possibile disporre dell'autorizzazione per eseguire l'azione nell'API.

## <a name="create-an-app"></a>Creare un'app

1. Accedere a [Azure](https://portal.azure.com) come utente con il ruolo di **amministratore globale** .

2. Passare a registrazione delle app di **Azure Active Directory**  >    >  **nuova registrazione**.

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. Nel modulo scegliere un nome per l'applicazione e immettere le informazioni seguenti per l'URI di reindirizzamento, quindi selezionare **registra**.

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - **Tipo di applicazione:** Client pubblico
   - **URI di reindirizzamento:**https://portal.azure.com

4. Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**. L'app può ora accedere a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* è un nome precedente per Microsoft 365 Defender e non verrà visualizzato nell'elenco originale. È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - Scegliere **autorizzazioni delegate**. Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident. Read**, e quindi fare clic su **Aggiungi autorizzazioni**.

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > È necessario selezionare le autorizzazioni rilevanti per lo scenario. *Leggere tutti gli eventi* non consentiti è solo un esempio. Per determinare le autorizzazioni necessarie, vedere la sezione relativa alle **autorizzazioni** nell'API che si desidera chiamare.
    >
    > Ad esempio, per [eseguire query avanzate](api-advanced-hunting.md), selezionare l'autorizzazione ' Esegui query avanzate '; per [isolare un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selezionare l'autorizzazione ' isolate machine '.

5. Selezionare **Concedi consenso amministratore**. Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi all'amministratore il consenso** per rendere effettive le autorizzazioni.

   ![Immagine delle autorizzazioni di concessione](../../media/grant-consent-delegated.PNG)

6. Registrare l'ID dell'applicazione e l'ID del tenant in una posizione sicura. Sono elencate in **Panoramica** nella pagina dell'applicazione.

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Ottenere un token di accesso

Per ulteriori informazioni sui token di Azure Active Directory, vedere l' [esercitazione su Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

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

1. Copiare e incollare il token in [JWT](https://jwt.ms) per decodificarlo.
1. Verificare che l'attestazione dei *ruoli* all'interno del token decodificato contenga le autorizzazioni desiderate.

Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` e le ```AdvancedHunting.Read.All``` autorizzazioni:

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
- [Creare un'app ' Hello World '](api-hello-world.md)
- [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md)
- [Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs](api-partner-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Informazioni sui codici di errore](api-error-codes.md)
- [OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
