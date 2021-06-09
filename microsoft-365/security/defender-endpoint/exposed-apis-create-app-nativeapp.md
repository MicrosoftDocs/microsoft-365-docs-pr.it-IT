---
title: Usare Microsoft Defender per le API degli endpoint
ms.reviewer: ''
description: Scopri come progettare un'app Windows nativa per ottenere l'accesso a livello di codice a Microsoft Defender per Endpoint senza un utente.
keywords: api, api del grafico, api supportate, attore, avvisi, dispositivo, utente, dominio, ip, file, ricerca avanzata, query
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 876dddf7a68b9844dea6a30ff4ebbbe3c2b75b69
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844551"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Usare Microsoft Defender per le API degli endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Questa pagina descrive come creare un'applicazione per ottenere l'accesso a livello di codice a Defender per Endpoint per conto di un utente.

Se è necessario accedere a livello di codice a Microsoft Defender for Endpoint senza un utente, fare riferimento a [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).

Se non si è certi dell'accesso necessario, leggere la [pagina Introduzione.](apis-intro.md)

Microsoft Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API ti consentiranno di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Microsoft Defender for Endpoint. L'accesso API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In generale, dovrai eseguire la procedura seguente per usare le API:
- Creare un'applicazione AAD
- Ottenere un token di accesso con questa applicazione
- Usare il token per accedere all'API di Defender for Endpoint

Questa pagina spiega come creare un'applicazione AAD, ottenere un token di accesso a Microsoft Defender for Endpoint e convalidare il token.

>[!NOTE]
> Quando si accede all'API di Microsoft Defender per endpoint per conto di un utente, sono necessarie l'autorizzazione applicazione e l'autorizzazione utente corrette.
> Se non si ha familiarità con le autorizzazioni utente in Microsoft Defender for Endpoint, vedere [Manage portal access using role-based access control](rbac.md).

>[!TIP]
> Se hai l'autorizzazione per eseguire un'azione nel portale, hai l'autorizzazione per eseguire l'azione nell'API.

## <a name="create-an-app"></a>Creare un'app

1. Accedere ad [Azure](https://portal.azure.com) con un account utente con il **ruolo amministratore** globale.

2. Passare **a** Azure Active Directory  >  **app Nuove**  >  **registrazioni**. 

   ![Immagine dell'Microsoft Azure e della navigazione per la registrazione dell'applicazione](images/atp-azure-new-app2.png)

3. Quando viene **visualizzata la pagina Registra** un'applicazione, immettere le informazioni di registrazione dell'applicazione:

   - **Nome:** immettere un nome di applicazione significativo che verrà visualizzato agli utenti dell'app.
   - **Tipi di account supportati:** selezionare gli account che si desidera supportare dall'applicazione.

       | Tipi di account supportati | Descrizione |
       |-------------------------|-------------|
       | **Account solo in questa directory organizzativa** | Selezionare questa opzione se si sta creando un'applicazione line-of-business (LOB). Questa opzione non è disponibile se non si sta registrando l'applicazione in una directory.<br><br>Questa opzione esegue il mapping ad Azure AD solo a tenant singolo.<br><br>Questa è l'opzione predefinita, a meno che tu non registri l'app all'esterno di una directory. Nei casi in cui l'app viene registrata all'esterno di una directory, il valore predefinito è Azure AD multi-tenant e account Microsoft personali. |
       | **Account in qualsiasi directory dell'organizzazione** | Selezionare questa opzione se si desidera scegliere come destinazione tutti i clienti aziendali ed educativi.<br><br>Questa opzione è mappata solo a un multi-tenant di Azure AD.<br><br>Se l'app è stata registrata come singolo tenant di Azure AD, è possibile aggiornarla in modo che sia multi-tenant di Azure AD e tornare a single-tenant tramite il pannello **Autenticazione.** |
       | **Account in qualsiasi directory organizzativa e account Microsoft personali** | Selezionare questa opzione per scegliere come target il set più ampio di clienti.<br><br>Questa opzione è mappata agli account Microsoft personali e multi-tenant di Azure AD.<br><br>Se l'app è stata registrata come account Microsoft personali e multi-tenant di Azure AD, non è possibile modificarla nell'interfaccia utente. È invece necessario utilizzare l'editor del manifesto dell'applicazione per modificare i tipi di account supportati. |

   - URI di reindirizzamento **(facoltativo):** seleziona il tipo di app che stai creando, il client **Web** o pubblico **(desktop & mobile)** e quindi immetti l'URI di reindirizzamento (o URL di risposta) per l'applicazione.
       - Per le applicazioni Web, specifica l'URL di base della tua app. Ad esempio, `http://localhost:31544` potrebbe essere l'URL di un'app Web in esecuzione nel computer locale. Gli utenti utilizzerebbe questo URL per accedere a un'applicazione client Web.
       - Per le applicazioni client pubbliche, fornire l'URI usato da Azure AD per restituire risposte di token. Immettere un valore specifico per l'applicazione, ad esempio `myapp://auth` .

     Per visualizzare esempi specifici per le applicazioni Web o le applicazioni native, vedere le [guide introduttive](/azure/active-directory/develop/#quickstarts).

     Al termine, selezionare **Registra**.

4. Consenti all'applicazione di accedere a Microsoft Defender per Endpoint e assegnarle l'autorizzazione "Lettura avvisi":

    - Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi API di autorizzazione che l'organizzazione usa >  >    >   **digitare WindowsDefenderATP** e selezionare **in WindowsDefenderATP.**

    - **Nota:** *WindowsDefenderATP* non viene visualizzato nell'elenco originale. Iniziare a scrivere il nome nella casella di testo per visualizzarlo.

      ![aggiungere l'autorizzazione](images/add-permission.png)

    - Scegliere **Autorizzazioni delegate**  >  **Alert.Read >** selezionare Aggiungi **autorizzazioni**

      ![autorizzazioni dell'applicazione](images/application-permissions-public-client.png)

    - **Nota importante:** selezionare le autorizzazioni pertinenti. Gli avvisi di lettura sono solo un esempio.

      Ad esempio,

      - Per [eseguire query avanzate,](run-advanced-query-api.md)selezionare l'autorizzazione "Esegui query avanzate"
      - Per [isolare un dispositivo,](isolate-machine.md)selezionare l'autorizzazione "Isola computer"
      - Per determinare l'autorizzazione necessaria, vedi **la sezione Autorizzazioni** nell'API che vuoi chiamare.

    - Selezionare **Concedi consenso**

      **Nota:** ogni volta che aggiungi l'autorizzazione, devi selezionare Concedi **il** consenso perché la nuova autorizzazione sia effettiva.

      ![Immagine delle autorizzazioni di concessione](images/grant-consent.png)

6. Annota l'ID applicazione e l'ID tenant:

   - Nella pagina dell'applicazione passare a **Panoramica** e copiare le informazioni seguenti:

   ![Immagine dell'ID app creato](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a>Ottenere un token di accesso

Per altre informazioni sui token AAD, vedi Esercitazione [su Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-c"></a>Utilizzo di C #

- Copia/Incolla la classe seguente nell'applicazione.
- Usa **il metodo AcquireUserTokenAsync** con l'ID applicazione, l'ID tenant, il nome utente e la password per acquisire un token.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>Convalidare il token

Verificare di avere un token corretto:
- Copia/incolla in [JWT](https://jwt.ms) il token ottenuto nel passaggio precedente per decodificarlo
- Verifica di ottenere un'attestazione "scp" con le autorizzazioni dell'app desiderate
- Nello screenshot seguente puoi vedere un token decodificato acquisito dall'app nell'esercitazione:

![Immagine della convalida dei token](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Usare il token per accedere all'API di Microsoft Defender for Endpoint

- Scegli l'API che vuoi usare - [API supportate di Microsoft Defender per endpoint](exposed-apis-list.md)
- Imposta l'intestazione Authorization nella richiesta HTTP inviata a "Bearer {token}" (Bearer è lo schema di autorizzazione)
- La scadenza del token è di 1 ora (è possibile inviare più di una richiesta con lo stesso token)

- Esempio di invio di una richiesta per ottenere un elenco di avvisi **tramite C#** 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Vedere anche
- [API di Microsoft Defender per endpoint](exposed-apis-list.md)
- [Accedere a Microsoft Defender for Endpoint con il contesto dell'applicazione](exposed-apis-create-app-webapp.md)
