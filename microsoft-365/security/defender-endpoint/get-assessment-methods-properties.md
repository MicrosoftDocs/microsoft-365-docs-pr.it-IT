---
title: Esportare proprietà e metodi di valutazione per dispositivo
description: Fornisce informazioni sulle API che estraeno i gestione di minacce e vulnerabilità". Esistono diverse chiamate API per ottenere diversi tipi di dati. In generale, ogni chiamata API contiene i dati dei requisiti per i dispositivi dell'organizzazione.
keywords: api, api, valutazione dell'esportazione, valutazione per dispositivo, valutazione per computer, report di valutazione delle vulnerabilità, valutazione della vulnerabilità del dispositivo, report di vulnerabilità del dispositivo, valutazione della configurazione sicura, report di configurazione sicura, valutazione delle vulnerabilità software, report di vulnerabilità software, report di vulnerabilità per computer,
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
ms.openlocfilehash: 12a77441f283ed693eae31fff36a7197ff6f0506
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053240"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Esportare proprietà e metodi di valutazione per dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>Descrizione API

Fornisce metodi e dettagli sulle proprietà sulle API che estrae gestione di minacce e vulnerabilità dati in base al dispositivo. Esistono diverse chiamate API per ottenere diversi tipi di dati. In generale, ogni chiamata API contiene i dati dei requisiti per i dispositivi dell'organizzazione.

> [!Note]
>
> Se non diversamente indicato, tutti i metodi di valutazione dell'esportazione elencati sono **_l'esportazione_** completa e per dispositivo **_(noto_** anche **_come per dispositivo)._**

Puoi usare le API di valutazione dell'esportazione per recuperare (esportare) diversi tipi di informazioni:

- [1. Esportare la valutazione delle configurazioni sicure](#1-export-secure-configurations-assessment)

- [2. Esportare la valutazione dell'inventario software](#2-export-software-inventory-assessment)

- [3. Esportare la valutazione delle vulnerabilità software](#3-export-software-vulnerabilities-assessment)

Le API corrispondenti ai tipi di informazioni di esportazione sono descritte nelle sezioni 1, 2 e 3.

Per ogni metodo, esistono diverse chiamate API per ottenere tipi diversi di dati. Poiché la quantità di dati può essere di grandi dimensioni, è possibile recuperarla in due modi:

- **Risposta JSON**  L'API estrae tutti i dati nell'organizzazione come risposte JSON. Questo metodo è ideale _per organizzazioni di piccole dimensioni con meno di 100 K dispositivi._ La risposta viene impaginata, quindi è possibile utilizzare il campo \@ odata.nextLink dalla risposta per recuperare i risultati successivi.

- **tramite file** Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come indicato di seguito:

  - Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione.

  - Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

I dati raccolti (usando la risposta _JSON_ o _tramite file_) sono lo snapshot corrente dello stato corrente e non contengono dati storici. Per raccogliere i dati storici, i clienti devono salvare i dati nei propri archivi dati.

## <a name="1-export-secure-configurations-assessment"></a>1. Esportare la valutazione delle configurazioni sicure

Restituisce tutte le configurazioni e il relativo stato, in base al dispositivo.

### <a name="11-methods"></a>1.1 Metodi

Metodo | Tipo di dati | Descrizione
:---|:---|:---
Esportare la valutazione della **configurazione sicura (risposta JSON)** | Configurazione sicura in base alla raccolta di dispositivi. Vedi: [1.2 Proprietà (risposta JSON)](#12-properties-json-response) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, ConfigurationId. L'API estrae tutti i dati nell'organizzazione come risposte JSON. Questo metodo è ideale per organizzazioni di piccole dimensioni con meno di 100 K dispositivi. La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi.
Esportare la valutazione della **configurazione sicura (tramite file)** | Configurazione sicura in base alla raccolta di dispositivi. Vedi: [1.3 Proprietà (tramite file)](#13-properties-via-files) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, ConfigurationId. Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come segue: 1.  Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione. 2.  Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

### <a name="12-properties-json-response"></a>1.2 Proprietà (risposta JSON)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
ConfigurationCategory | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza
ConfigurationId | stringa | Identificatore univoco di una configurazione specifica
ConfigurationImpact | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)
ConfigurationName | stringa | Nome visualizzato della configurazione
ConfigurationSubcategory | stringa | Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche.
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio.
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo.
IsApplicable | bool | Indica se la configurazione o il criterio è applicabile
IsCompliant | bool | Indica se la configurazione o i criteri sono configurati correttamente
IsExpectedUserImpact | bool | Indica se ci sarà un impatto sull'utente se la configurazione verrà applicata
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms.
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".
RecommendationReference | stringa | Riferimento all'ID suggerimento relativo a questo software.
Timestamp | stringa | Ultima volta che la configurazione è stata vista nel dispositivo

### <a name="13-properties-via-files"></a>1.3 Proprietà (tramite file)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
Esportare file | stringa \[ di matrice\] | Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione.
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione.

## <a name="2-export-software-inventory-assessment"></a>2. Esportare la valutazione dell'inventario software

Restituisce tutto il software installato e i relativi dettagli in ogni dispositivo.

### <a name="21-methods"></a>2.1 Metodi

Metodo | Tipo di dati | Descrizione
:---|:---|:---
Esportare la valutazione dell'inventario software **(risposta JSON)** | Inventario software per raccolta dispositivi. Vedi: [2.2 Proprietà (risposta JSON)](#22-properties-json-response) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. L'API estrae tutti i dati nell'organizzazione come risposte JSON. Questo metodo è ideale per organizzazioni di piccole dimensioni con meno di 100 K dispositivi. La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi.
Esportare la valutazione dell'inventario **software (tramite file)** | Inventario software in base ai file del dispositivo. Vedere: [2.3 Proprietà (tramite file)](#23-properties-via-files) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come segue: 1.  Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione. 2.  Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.

### <a name="22-properties-json-response"></a>2.2 Proprietà (risposta JSON)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio.
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo.
DiskPaths | Array[string]  | Prova su disco che il prodotto è installato nel dispositivo.
EndOfSupportDate | stringa | Data in cui il supporto per questo software ha o terminerà.
EndOfSupportStatus | stringa | Stato della fine del supporto. Può contenere questi valori possibili: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
Id | stringa | Identificatore univoco del record.
NumberOfWeaknesses | int|Numero di punti deboli su questo software in questo dispositivo
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms.
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".
RegistryPaths | Array[string] | Prova del Registro di sistema che il prodotto è installato nel dispositivo.
SoftwareFirstSeenTimestamp | stringa | La prima volta che questo software è stato visto nel dispositivo.
SoftwareName | stringa | Nome del prodotto software.
SoftwareVendor | stringa | Nome del fornitore del software.
SoftwareVersion | stringa | Numero di versione del prodotto software.

### <a name="23-properties-via-files"></a>2.3 Proprietà (tramite file)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
Esportare file | stringa \[ di matrice\] | Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione.
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Esportare la valutazione delle vulnerabilità software

Restituisce tutte le vulnerabilità note in un dispositivo e i relativi dettagli, per tutti i dispositivi.

### <a name="31-methods"></a>3.1 Metodi

Metodo | Tipo di dati | Descrizione
:---|:---|:---
Esportare la valutazione delle vulnerabilità software **(risposta JSON)** | Raccolta di indagini Vedere: [3.2 Proprietà (risposta JSON)](#32-properties-json-response) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. L'API estrae tutti i dati nell'organizzazione come risposte JSON. Questo metodo è ideale per organizzazioni di piccole dimensioni con meno di 100 K dispositivi. La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi.
Esportare la valutazione delle vulnerabilità software **(tramite file)** | Entità di indagine Vedere: [3.3 Proprietà (tramite file)](#33-properties-via-files) | Restituisce una tabella con una voce per ogni combinazione univoca di DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Questa soluzione API consente di estrarre grandi quantità di dati in modo più rapido e affidabile. Pertanto, è consigliabile per le organizzazioni di grandi dimensioni, con più di 100 dispositivi K. Questa API estrae tutti i dati dell'organizzazione come file di download. La risposta contiene URL per scaricare tutti i dati da Archiviazione di Azure. Questa API consente di scaricare tutti i dati da Archiviazione di Azure come segue: 1.  Chiama l'API per ottenere un elenco di URL di download con tutti i dati dell'organizzazione. 2.  Scarica tutti i file usando gli URL di download ed elabora i dati come vuoi.
**Valutazione delle vulnerabilità** del software di esportazione delta **(risposta JSON)** | Raccolta di indagini Vedere: [3.4 Proprietà Esportazione delta (risposta JSON)](#34-properties-delta-export-json-response) | Restituisce una tabella con una voce per ogni combinazione univoca di: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId ed EventTimestamp. <br><br> L'API estrae i dati nell'organizzazione come risposte JSON. La risposta viene impaginata, quindi è possibile utilizzare il campo @odata.nextLink dalla risposta per recuperare i risultati successivi. A differenza della valutazione completa delle vulnerabilità software (risposta JSON), che viene utilizzata per ottenere un'intera istantanea della valutazione delle vulnerabilità software dell'organizzazione per dispositivo, la chiamata API di esportazione delta viene utilizzata per recuperare solo le modifiche che si sono verificate tra una data selezionata e la data corrente (chiamata API "delta"). Invece di ottenere un'esportazione completa con una grande quantità di dati ogni volta, si otterrà solo informazioni specifiche sulle vulnerabilità nuove, fisse e aggiornate. La chiamata API di esportazione delta può essere utilizzata anche per calcolare indicatori KPI diversi, ad esempio "quante vulnerabilità sono state risolvete?" o "Quante nuove vulnerabilità sono state aggiunte all'organizzazione?"  <br><br> Poiché la chiamata dell'API di esportazione Delta per le vulnerabilità software restituisce dati solo per un intervallo di date mirato, non è considerata _un'esportazione completa._

### <a name="32-properties-json-response"></a>3.2 Proprietà (risposta JSON)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
CveId | stringa | Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures).
CvssScore | stringa | Punteggio CVSS del CVE.
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio.
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo.
DiskPaths | Stringa \[ matrice\] | Prova su disco che il prodotto è installato nel dispositivo.
ExploitabilityLevel | stringa | Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | stringa | La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo.
Id | stringa | Identificatore univoco del record.
LastSeenTimestamp | stringa | Ultima volta che il CVE è stato visualizzato nel dispositivo.
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms.
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".
RecommendationReference | stringa | Riferimento all'ID suggerimento relativo a questo software.
RecommendedSecurityUpdate | stringa | Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità.
RecommendedSecurityUpdateId | stringa | Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti
Stringa della matrice dei percorsi del Registro \[ di sistema\] | Prova del Registro di sistema che il prodotto è installato nel dispositivo.
SoftwareName | stringa | Nome del prodotto software.
SoftwareVendor | stringa | Nome del fornitore del software.
SoftwareVersion | stringa | Numero di versione del prodotto software.
VulnerabilitySeverityLevel | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce.

### <a name="33-properties-via-files"></a>3.3 Proprietà (tramite file)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
Esportare file | stringa \[ di matrice\]  | Elenco di URL di download per i file che tengono lo snapshot corrente dell'organizzazione.
GeneratedTime | stringa | Ora in cui è stata generata l'esportazione.

### <a name="34-properties-delta-export-json-response"></a>3.4 Proprietà (risposta JSON di esportazione delta)

Proprietà (ID) | Tipo di dati | Descrizione
:---|:---|:---
CveId | stringa | Identificatore univoco assegnato alla vulnerabilità della sicurezza nel sistema CVE (Common Vulnerabilities and Exposures).
CvssScore | stringa | Punteggio CVSS del CVE.
DeviceId | stringa | Identificatore univoco del dispositivo nel servizio.
DeviceName | stringa | Nome di dominio completo (FQDN) del dispositivo.
DiskPaths | Array[string] | Prova su disco che il prodotto è installato nel dispositivo.
EventTimestamp | Stringa | Ora in cui è stato trovato questo evento delta.
ExploitabilityLevel | stringa | Livello di sfruttabilità di questa vulnerabilità (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | stringa | La prima volta che il CVE di questo prodotto è stato visualizzato nel dispositivo.
Id | stringa | Identificatore univoco del record.  
LastSeenTimestamp | stringa | Ultima volta che il CVE è stato visualizzato nel dispositivo.
OSPlatform | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. Per informazioni dettagliate, vedere tvm supported operating systems and platforms.
RbacGroupName | stringa | Gruppo RBAC (Role-Based Access Control). Se questo dispositivo non è assegnato ad alcun gruppo RBAC, il valore sarà "Non assegnato". Se l'organizzazione non contiene gruppi RBAC, il valore sarà "None".
RecommendationReference | stringa | Riferimento all'ID suggerimento relativo a questo software.
RecommendedSecurityUpdate  | stringa | Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità.
RecommendedSecurityUpdateId  | stringa | Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti
RegistryPaths  | Array[string] | Prova del Registro di sistema che il prodotto è installato nel dispositivo.
SoftwareName | stringa | Nome del prodotto software.
SoftwareVendor | stringa | Nome del fornitore del software.
SoftwareVersion | stringa | Numero di versione del prodotto software.
Stato | Stringa | **Nuovo**   (per una nuova vulnerabilità introdotta in un dispositivo).  **Risolto**   (per una vulnerabilità che non esiste più nel dispositivo, il che significa che è stato corretti). **Aggiornato**   (per una vulnerabilità in un dispositivo che è cambiata. Le possibili modifiche sono: punteggio CVSS, livello di exploit, livello di gravità, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce.

## <a name="see-also"></a>Vedere anche

- [Esportare la valutazione della configurazione sicura per dispositivo](get-assessment-secure-config.md)

- [Esportare la valutazione dell'inventario software per dispositivo](get-assessment-software-inventory.md)

- [Esportare la valutazione delle vulnerabilità software per dispositivo](get-assessment-software-vulnerabilities.md)

Altre informazioni correlate

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
