---
title: Esportare la valutazione delle vulnerabilità software per dispositivo
description: La risposta api è per dispositivo e contiene software vulnerabile installato nei dispositivi esposti, nonché eventuali vulnerabilità note in questi prodotti software. La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.
keywords: api, api, valutazione dell'esportazione, valutazione per dispositivo, report di valutazione delle vulnerabilità, valutazione della vulnerabilità del dispositivo, report di vulnerabilità del dispositivo, valutazione della configurazione sicura, report di configurazione sicura, valutazione delle vulnerabilità software, report di vulnerabilità software, report sulle vulnerabilità in base al computer,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: be21be07758c1123cdde38e3750cafe739bfb66a
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653654"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Esportare la valutazione delle vulnerabilità software per dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Restituisce tutte le vulnerabilità note e i relativi dettagli per tutti i dispositivi, in base al dispositivo.

Esistono diverse chiamate API per ottenere diversi tipi di dati. Poiché la quantità di dati può essere molto grande, è possibile recuperarla in due modi:

- **OData**  L'API estrae tutti i dati nell'organizzazione come risposte Json, seguendo il protocollo OData. Questo metodo è ideale per _organizzazioni di piccole dimensioni con meno di 100.000 dispositivi._ La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.

- **tramite file** Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100.000 dispositivi. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:

  - Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.

  - Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

I dati raccolti (per _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici. Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.

Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Esportare la valutazione delle vulnerabilità software (OData)

### <a name="11-api-method-description"></a>1.1 Descrizione del metodo API

Questa risposta API contiene tutti i dati del software installato per dispositivo. Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="limitations"></a>Limitazioni

>- La dimensione massima della pagina è 200.000.
>
>- I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.

### <a name="12-permissions"></a>1.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Vulnerability.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Vulnerability.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 Parametri

- pageSize (impostazione predefinita = 50.000): numero di risultati in risposta
- $top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)

### <a name="15-properties"></a>1.5 Proprietà
>
>[!Note]
>
>- Ogni record è di circa 1 KB di dati. È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.
>
>- Nella risposta potrebbero essere restituite alcune colonne aggiuntive. Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.
>
>- Le proprietà definite nella tabella seguente sono elencate alfanumericamente in base all'ID proprietà.  Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in queste tabelle.
>

Proprietà (id) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
CveId | stringa | Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures). | CVE-2020-15992
CvssScore | stringa | Punteggio CVSS del CVE. | 6.2
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com
DiskPaths  | Stringa \[ matrice\] | Prova su disco che il prodotto è installato nel dispositivo. | [ "C:\Programmi (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | stringa | Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | stringa | La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo. | 2020-11-03 10:13:34.8476880
Id | stringa | Identificatore univoco del record. | 123ABG55_573AG&mnp!
LastSeenTimestamp | stringa | Ultima volta che il CVE è stato visualizzato nel dispositivo. | 2020-11-03 10:13:34.8476880
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms. | Windows10
RbacGroupName  | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None". | Server
RecommendationReference | stringa | Riferimento all'ID suggerimento relativo a questo software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (facoltativo) | stringa | Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità. | Aggiornamenti della sicurezza di aprile 2020
RecommendedSecurityUpdateId (facoltativo) | stringa | Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti | 4550961
RegistryPaths  | Stringa \[ matrice\] | Prova del Registro di sistema che il prodotto è installato nel dispositivo. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | stringa | Nome del prodotto software. | chrome
SoftwareVendor | stringa | Nome del fornitore del software. | google
SoftwareVersion | stringa | Numero di versione del prodotto software. | 81.0.4044.138
VulnerabilitySeverityLevel  | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce. | Medio

### <a name="16-examples"></a>1.6 Esempi

#### <a name="161-request-example"></a>1.6.1 Esempio di richiesta

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 Esempio di risposta

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Esportare la valutazione delle vulnerabilità software (tramite file)

### <a name="21-api-method-description"></a>2.1 Descrizione del metodo API

Questa risposta API contiene tutti i dati del software installato per dispositivo. Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Limitazioni

I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.

### <a name="22-permissions"></a>2.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Vulnerability.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Vulnerability.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 Parametri

- sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore)

### <a name="25-properties"></a>2.5 Proprietà

>[!Note]
>
>- I file sono compressi con gzip & in formato Json multilinea.
>
>- Gli URL di download sono validi solo per 3 ore. in caso contrario, è possibile utilizzare il parametro .
>
>- Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.
>

>[!Note]
>
>- Ogni record è di circa 1 KB di dati. È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.
>
>- Nella risposta potrebbero essere restituite alcune colonne aggiuntive. Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.
>
>- Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà.  Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in queste tabelle.
>

Proprietà (id) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
Esportare file | stringa \[ di matrice\]  | Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Esempi

#### <a name="261-request-example"></a>2.6.1 Esempio di richiesta

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 Esempio di risposta

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vedere anche

- [Esportare proprietà e metodi di valutazione per dispositivo](get-assessmnt-1methods-properties.md)

- [Esportare la valutazione della configurazione sicura per dispositivo](get-assessmnt-secure-cfg.md)

- [Esportare la valutazione dell'inventario software per dispositivo](get-assessmnt-software-inventory.md)

Altre informazioni correlate

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
