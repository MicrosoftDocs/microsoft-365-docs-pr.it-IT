---
title: Esportare la valutazione dell'inventario software per dispositivo
description: Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
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
ms.openlocfilehash: 639f850119498222684c4b3804b32a29dda3eac4
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022883"
---
# <a name="export-software-inventory-assessment-per-device"></a>Esportare la valutazione dell'inventario software per dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Esistono diverse chiamate API per ottenere diversi tipi di dati. Poiché la quantità di dati può essere di grandi dimensioni, è possibile recuperarla in due modi:

- [Esportare la risposta JSON di valutazione **dell'inventario software**](#1-export-software-inventory-assessment-json-response) L'API estrae tutti i dati nell'organizzazione come risposte Json. Questo metodo è ideale _per organizzazioni di piccole dimensioni con meno di 100 K dispositivi._ La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.

- [Esportare la valutazione dell'inventario **software tramite file**](#2-export-software-inventory-assessment-via-files)  Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:

  - Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.

  - Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

I dati raccolti (tramite _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici. Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.

> [!Note]
>
> Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**

## <a name="1-export-software-inventory-assessment-json-response"></a>1. Esportare la valutazione dell'inventario software (risposta JSON)

### <a name="11-api-method-description"></a>1.1 Descrizione del metodo API

Questa risposta API contiene tutti i dati del software installato per dispositivo. Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="limitations"></a>Limitazioni

- La dimensione massima della pagina è 200.000.

- I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.

### <a name="12-permissions"></a>1.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Software.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Software.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 Parametri

- pageSize (impostazione predefinita = 50.000): numero di risultati in risposta.

- $top - Numero di risultati da restituire (non restituisce @odata.nextLink e pertanto non estrae tutti i dati)

### <a name="15-properties"></a>1.5 Proprietà

>[!NOTE]
>
>- Ogni record è di circa 0,5 KB di dati. È consigliabile prendere in considerazione questo parametro quando si sceglie il parametro pageSize corretto.
>
>- Le proprietà definite nella tabella seguente sono elencate in ordine alfabetico in base all'ID proprietà. Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in questa tabella.
>
>- Nella risposta potrebbero essere restituite alcune colonne aggiuntive. Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.

<br/>

Proprietà (ID) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com
DiskPaths | Array[string]  | Prova su disco che il prodotto è installato nel dispositivo. | [ "C: \\ Programmi (x86) \\ Microsoft Silverlight Application \\ \\ \\silverlight.exe" ]
EndOfSupportDate | stringa | Data in cui il supporto per questo software ha o terminerà. | 2020-12-30
EndOfSupportStatus | stringa | Stato della fine del supporto. Può contenere questi valori possibili: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software. | EOS imminente
Id | stringa | Identificatore univoco del record. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Numero di punti deboli su questo software in questo dispositivo | 3
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms. | Windows10
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None". | Server
RegistryPaths | Array[string] | Prova del Registro di sistema che il prodotto è installato nel dispositivo. | [ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]
SoftwareFirstSeenTimestamp | stringa | La prima volta che questo software è stato visto nel dispositivo. | 2019-04-07 02:06:47
SoftwareName | stringa | Nome del prodotto software. | Silverlight
SoftwareVendor | stringa | Nome del fornitore del software. | microsoft
SoftwareVersion | stringa | Numero di versione del prodotto software. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Esempi

#### <a name="161-request-example"></a>1.6.1 Esempio di richiesta

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 Esempio di risposta

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Esportare la valutazione dell'inventario software (tramite file)

### <a name="21-api-method-description"></a>2.1 Descrizione del metodo API

Questa risposta API contiene tutti i dati del software installato per dispositivo. Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Limitazioni

I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.

### <a name="22-permissions"></a>2.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Software.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Software.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parametri

- sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore)

### <a name="25-properties"></a>2.5 Proprietà

>[!Note]
>
>- I file sono compressi con gzip & in formato JSON multilinea.
>
>- Gli URL di download sono validi solo per 3 ore. In caso contrario, è possibile utilizzare il parametro .
>
>- Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.

<br/><br/>

Proprietà (ID) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
Esportare file | stringa \[ di matrice\] | Elenco degli URL di download per i file che tengono lo snapshot corrente dell'organizzazione | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Esempi

#### <a name="261-request-example"></a>2.6.1 Esempio di richiesta

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 Esempio di risposta

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vedere anche

- [Esportare proprietà e metodi di valutazione per dispositivo](get-assessment-methods-properties.md)

- [Esportare la valutazione della configurazione sicura per dispositivo](get-assessment-secure-config.md)

- [Esportare la valutazione delle vulnerabilità software per dispositivo](get-assessment-software-vulnerabilities.md)

Altre informazioni correlate

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
