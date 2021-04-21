---
title: Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST
description: Scopri come chiamare un endpoint API di Microsoft Defender for Endpoint per eseguire il pull dei rilevamenti in formato JSON usando l'API REST SIEM.
keywords: rilevamenti, rilevamenti pull, api rest, richiesta, risposta
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
ms.openlocfilehash: 06028f64a3340aeeef52269bc8a1e739d18e6db7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903119"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.
>-L'API di Microsoft Defender for Endpoint Alert è l'API più recente per il consumo di avvisi e contiene un elenco dettagliato di prove correlate per ogni avviso. Per ulteriori informazioni, vedere [Metodi e proprietà degli](alerts.md) avvisi e Avvisi [elenco.](get-alerts.md)

Microsoft Defender for Endpoint supporta il protocollo OAuth 2.0 per il pull dei rilevamenti dall'API.

In generale, il protocollo OAuth 2.0 supporta quattro tipi di flussi:
- Flusso di concessione dell'autorizzazione
- Flusso implicito
- Flusso delle credenziali client
- Flusso proprietario risorsa

Per ulteriori informazioni sulle specifiche OAuth, vedere il sito Web [OAuth.](http://www.oauth.net)

Microsoft Defender for Endpoint  supporta il flusso di concessione dell'autorizzazione e il flusso delle credenziali _client_ per ottenere l'accesso ai rilevamenti di pull, con Azure Active Directory (AAD) come server di autorizzazione.

Il _flusso di concessione dell'autorizzazione_ usa le credenziali utente per ottenere un codice di autorizzazione, che viene quindi usato per ottenere un token di accesso.

Il _flusso di credenziali client usa_ le credenziali client per eseguire l'autenticazione nell'URL dell'endpoint di Microsoft Defender for Endpoint. Questo flusso è adatto agli scenari in cui un client OAuth crea richieste a un'API che non richiede credenziali utente.

Usa il metodo seguente nell'API di Microsoft Defender for Endpoint per estrarre i rilevamenti in formato JSON.

>[!NOTE]
>Microsoft Defender Security Center unisce rilevamenti di avvisi simili in un singolo avviso. Questa API esegue il pull dei rilevamenti degli avvisi nella forma non elaborata in base ai parametri di query impostati, consentendo di applicare il proprio raggruppamento e filtro. 

## <a name="before-you-begin"></a>Prima di iniziare
- Prima di chiamare l'endpoint di Microsoft Defender for Endpoint per il pull dei rilevamenti, è necessario abilitare l'applicazione di integrazione SIEM in Azure Active Directory (AAD). Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Microsoft Defender per Endpoint.](enable-siem-integration.md)

- Prendere nota dei valori seguenti nella registrazione dell'applicazione Azure. Sono necessari questi valori per configurare il flusso OAuth nel servizio o nell'app daemon:
  - ID applicazione (univoco per l'applicazione)
  - Chiave dell'app o segreto (univoco per l'applicazione)
  - Endpoint token OAuth 2.0 della tua app
    - Trova questo valore facendo **clic su Visualizza endpoint** nella parte inferiore del portale di gestione di Azure nella pagina dell'app. L'endpoint sarà simile `https://login.microsoftonline.com/{tenantId}/oauth2/token` a .

## <a name="get-an-access-token"></a>Ottenere un token di accesso
Prima di creare chiamate all'endpoint, devi ottenere un token di accesso.

Userai il token di accesso per accedere alla risorsa protetta, ovvero i rilevamenti in Microsoft Defender per Endpoint.

Per ottenere un token di accesso, devi eseguire una richiesta POST all'endpoint di emissione del token. Ecco una richiesta di esempio:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
La risposta includerà un token di accesso e informazioni sulla scadenza.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Ora puoi usare il valore nel campo *access_token* in una richiesta all'API Defender for Endpoint.

## <a name="request"></a>Richiesta
Con un token di accesso, la tua app può effettuare richieste autenticate all'API di Microsoft Defender per endpoint. L'app deve aggiungere il token di accesso all'intestazione Authorization di ogni richiesta.

### <a name="request-syntax"></a>Sintassi delle richieste
Metodo | URI richiesta
:---|:---|
GET| Usa l'URI applicabile per la tua area geografica. <br><br> **Per l'UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Per gli Stati Uniti**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Per il Regno Unito**: `https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Intestazione della richiesta
Intestazione | Tipo | Descrizione|
:--|:--|:--
Autorizzazione | stringa | Obbligatorio. Token di accesso di Azure AD nel formato **Token Bearer** &lt;  &gt; . |

### <a name="request-parameters"></a>Parametri di richiesta

Utilizzare parametri di query facoltativi per specificare e controllare la quantità di dati restituiti in una risposta. Se si chiama questo metodo senza parametri, la risposta contiene tutti gli avvisi nell'organizzazione nelle ultime 2 ore.

Name | Valore| Descrizione
:---|:---|:---
sinceTimeUtc | DateTime | Definisce gli avvisi di tempo inferiore da cui vengono recuperati gli avvisi in base al campo: <br> `LastProcessedTimeUtc` <br> L'intervallo di tempo sarà: da sinceTimeUtc time a current time. <br><br> **NOTA:** se non specificato, vengono recuperati tutti gli avvisi generati nelle ultime due ore.
untilTimeUtc | DateTime | Definisce gli avvisi limite temporale superiore recuperati. <br> L'intervallo di tempo sarà: `sinceTimeUtc` di tanto in `untilTimeUtc` tanto. <br><br> **NOTA:** se non specificato, il valore predefinito sarà l'ora corrente.
ago | stringa | Estrae gli avvisi nel seguente intervallo di tempo: `(current_time - ago)` di tanto in `current_time` tanto. <br><br> Il valore deve essere impostato in base al formato di durata **ISO 8601** <br> Esempio: `ago=PT10M` verranno pull degli avvisi ricevuti negli ultimi 10 minuti.
limite | int | Definisce il numero di avvisi da recuperare. Gli avvisi più recenti verranno recuperati in base al numero definito.<br><br> **NOTA:** se non specificato, verranno recuperati tutti gli avvisi disponibili nell'intervallo di tempo.
machinegroups | stringa | Specifica i gruppi di dispositivi da cui estrarre gli avvisi. <br><br> **NOTA:** se non specificato, verranno recuperati gli avvisi di tutti i gruppi di dispositivi. <br><br> Esempio: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | stringa | Tag dispositivo singolo dal Registro di sistema.
CloudCreatedMachineTags | stringa | Tag del dispositivo creati in Microsoft Defender Security Center.

### <a name="request-example"></a>Esempio di richiesta
Nell'esempio seguente viene illustrato come recuperare tutti i rilevamenti nell'organizzazione.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

L'esempio seguente illustra una richiesta per ottenere gli ultimi 20 rilevamenti dal 2016-09-12 alle 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Risposta
Il valore restituito è una matrice di oggetti avviso in formato JSON.

Ecco un valore restituito di esempio:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Esempi di codice
### <a name="get-access-token"></a>Ottenere il token di accesso
Gli esempi di codice seguenti illustrano come ottenere un token di accesso per chiamare l'API SIEM di Microsoft Defender per endpoint.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Usare il token per connettersi all'endpoint di rilevamento
Gli esempi di codice seguenti illustrano come usare un token di accesso per chiamare l'API Defender for Endpoint SIEM per ottenere avvisi.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Codici di errore
L'API REST di Microsoft Defender per endpoint restituisce i codici di errore seguenti causati da una richiesta non valida.

Codice di errore HTTP | Descrizione
:---|:---
401 | Richiesta non valida o token non valido.
403 | Eccezione non autorizzata: uno dei domini non viene gestito dall'amministratore tenant o lo stato del tenant viene eliminato.
500 | Errore nel servizio.

## <a name="related-topics"></a>Argomenti correlati
- [Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint](enable-siem-integration.md)
- [Configurare ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint](configure-arcsight.md)
- [Eseguire il pull dei rilevamenti agli strumenti SIEM](configure-siem.md)
- [Campi di Microsoft Defender per il rilevamento degli endpoint](api-portal-mapping.md)
- [Risolvere i problemi di integrazione degli strumenti SIEM](troubleshoot-siem.md)
