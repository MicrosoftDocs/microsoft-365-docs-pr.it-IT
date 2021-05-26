---
title: Esportare la valutazione della configurazione sicura per dispositivo
description: Restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.
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
ms.openlocfilehash: f2e20415cb64903e8dfe2c82646c1970036b8f6b
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653646"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Esportare la valutazione della configurazione sicura per dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Restituisce tutte le configurazioni e il relativo stato, in base al dispositivo.

Esistono diverse chiamate API per ottenere diversi tipi di dati. Poiché la quantità di dati può essere molto grande, è possibile recuperarla in due modi:

- **OData**  L'API estrae tutti i dati nell'organizzazione come risposte Json, seguendo il protocollo OData. Questo metodo è ideale per _organizzazioni di piccole dimensioni con meno di 100.000 dispositivi._ La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.

- **tramite file** Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100.000 dispositivi. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:

  - Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.

  - Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

I dati raccolti (per _OData_ o _tramite file)_ sono lo snapshot corrente dello stato corrente e non contengono dati storici. Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.

Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Esportare la valutazione della configurazione sicura (OData)

### <a name="11-api-method-description"></a>1.1 Descrizione del metodo API

Questa risposta API contiene la valutazione della configurazione sicura nei dispositivi esposti e restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.

#### <a name="111-limitations"></a>1.1.1 Limitazioni

- La dimensione massima della pagina è 200.000.

- I limiti di frequenza per questa API sono 30 chiamate al minuto e 1000 chiamate all'ora.

### <a name="12-permissions"></a>1.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Vulnerability.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Vulnerability.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 Parametri

- pageSize \( default = 50.000 \) – numero di risultati in risposta

- \$top : il numero di risultati da restituire non \( restituisce \@ odata.nextLink e pertanto non estrae tutti i dati\)

### <a name="15-properties"></a>1.5 Proprietà

>[!Note]
>
>- Le proprietà definite nella tabella seguente sono elencate alfanumericamente in base all'ID proprietà.  Quando si esegue questa API, l'output risultante non verrà necessariamente restituito nello stesso ordine elencato in queste tabelle.
>
>- Nella risposta potrebbero essere restituite alcune colonne aggiuntive. Queste colonne sono temporanee e potrebbero essere rimosse, utilizzare solo le colonne documentate.
>

Proprietà (id) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
ConfigurationCategory | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza | Controlli di sicurezza
ConfigurationId | stringa | Identificatore univoco di una configurazione specifica | scid-10000
ConfigurationImpact | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10) | 9 
ConfigurationName | stringa | Nome visualizzato della configurazione | Aggiungere dispositivi a Microsoft Defender for Endpoint
ConfigurationSubcategory | stringa | Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche. | Dispositivi onboard
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com
IsApplicable | bool | Indica se la configurazione o il criterio è applicabile | true
IsCompliant | bool | Indica se la configurazione o i criteri sono configurati correttamente | false
IsExpectedUserImpact | bool | Indica se ci sarà un impatto sull'utente se la configurazione verrà applicata | true
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms. | Windows10
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None". | Server
RecommendationReference | stringa | Riferimento all'ID suggerimento relativo a questo software. | sca-_-scid-20000
Timestamp | stringa | Ultima volta che la configurazione è stata vista nel dispositivo | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Esempi

#### <a name="161-request-example"></a>1.6.1 Esempio di richiesta

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 Esempio di risposta

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Esportare la valutazione della configurazione sicura (tramite file)

### <a name="21-api-method-description"></a>2.1 Descrizione del metodo API

Questa risposta API contiene la valutazione della configurazione sicura nei dispositivi esposti e restituisce una voce per ogni combinazione univoca di DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Limitazioni

I limiti di frequenza per questa API sono 5 chiamate al minuto e 20 chiamate all'ora.

### <a name="22-permissions"></a>2.2 Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
---|---|---
Applicazione | Vulnerability.Read.All | \'Leggere le informazioni gestione di minacce e vulnerabilità vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | Vulnerability.Read | \'Leggere le informazioni gestione di minacce e vulnerabilità vulnerabilità\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parametri

- sasValidHours: numero di ore per cui saranno validi gli URL di download (massimo 24 ore).

### <a name="25-properties"></a>2.5 Proprietà

>[!Note]
>
>- I file sono compressi con gzip & in formato Json multilinea.
>
>- Gli URL di download sono validi solo per 3 ore. in caso contrario, è possibile utilizzare il parametro .
>
>- Per ottenere la massima velocità di download dei dati, puoi assicurarti di eseguire il download dalla stessa area di Azure in cui si trovano i dati.
>
Proprietà (id) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
Esportare file | stringa \[ di matrice\] | Elenco degli URL di download per i file che tengono lo snapshot corrente dell'organizzazione | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Esempi

#### <a name="261-request-example"></a>2.6.1 Esempio di richiesta

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 Esempio di risposta

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vedere anche

- [Esportare proprietà e metodi di valutazione per dispositivo](get-assessmnt-1methods-properties.md)

- [Esportare la valutazione dell'inventario software per dispositivo](get-assessmnt-software-inventory.md)

- [Esportare la valutazione delle vulnerabilità software per dispositivo](get-assessmnt-software-vulnerabilities.md)

Altre informazioni correlate

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
