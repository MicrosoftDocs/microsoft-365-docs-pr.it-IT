---
title: Microsoft Defender per endpoint per clienti del governo degli Stati Uniti
description: Informazioni sui requisiti e le funzionalità di Microsoft Defender for Endpoint per i clienti governativi degli Stati Uniti disponibili
keywords: governo, gcc, alto, requisiti, funzionalità, defender, Microsoft Defender per endpoint, endpoint, dod
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572670"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender per endpoint per clienti del governo degli Stati Uniti

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint per i clienti del governo degli Stati Uniti, creato nell'ambiente Azure US Government, usa le stesse tecnologie sottostanti di Defender for Endpoint in Azure Commercial.

Questa offerta è disponibile per GCC clienti GCC, High e DoD e si basa sulla stessa prevenzione, rilevamento, indagine e correzione della versione commerciale. Tuttavia, ci sono alcune differenze nella disponibilità di funzionalità per questa offerta.

> [!NOTE]
> Se sei un cliente GCC di Defender for Endpoint in Commercial, fai riferimento alle pagine della documentazione pubblica.

## <a name="licensing-requirements"></a>Requisiti di licenza
Microsoft Defender for Endpoint per i clienti del governo degli Stati Uniti richiede una delle seguenti offerte di contratti multilicenza Microsoft:

### <a name="desktop-licensing"></a>Licenze desktop
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 per GCC High | Windows 10 Enterprise E5 per DOD
| | Microsoft 365 E5 per GCC High | Microsoft 365 G5 per DOD
| | Microsoft 365 Sicurezza G5 per GCC Alta | Microsoft 365 Sicurezza G5 per DOD
Microsoft Defender per Endpoint - GCC | Microsoft Defender per endpoint per GCC alto | Microsoft Defender per Endpoint per DOD

### <a name="server-licensing"></a>Licenze server
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender per endpoint server GCC | Microsoft Defender per Endpoint Server per GCC alto | Microsoft Defender per Endpoint Server per DOD
Azure Defender per server | Azure Defender per server - Governo | Azure Defender per server - Governo

<br />

## <a name="portal-urls"></a>URL portale
Di seguito sono riportati gli URL del portale Microsoft Defender for Endpoint per i clienti del governo degli Stati Uniti:

Tipo di cliente | URL portale
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Versioni endpoint

### <a name="standalone-os-versions"></a>Versioni autonome del sistema operativo
Sono supportate le seguenti versioni del sistema operativo:

Versione del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, versione 20H2 (con [KB4586853)](https://support.microsoft.com/help/4586853) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 2004 (con [KB4586853)](https://support.microsoft.com/help/4586853) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1909 (con [KB4586819)](https://support.microsoft.com/help/4586819) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1903 (con [KB4586819)](https://support.microsoft.com/help/4586819) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1809 (con [KB4586839)](https://support.microsoft.com/help/4586839) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1803 (con [KB4598245)](https://support.microsoft.com/help/4598245) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1709 | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![Sì ](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147)<br />Nota: [deprecato,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)aggiornare | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato
Windows 10, versione 1703 e precedente | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato
Windows Server 2019 (con [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2016 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 8 Pro | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Linux | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
macOS | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Android | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione
iOS | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione

> [!NOTE]
> Se viene specificata una patch, è necessario dislorla prima dell'onboarding del dispositivo per configurare Defender for Endpoint nell'ambiente corretto.

> [!NOTE]
> Tentativo di a bordo di Windows dispositivi precedenti a Windows 10 o Windows Server 2019 utilizzando [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)? Sarà necessario scegliere "Azure US Government" in "Azure Cloud" se si utilizza la [configurazione guidata](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)o se si utilizza una riga [di comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) o [uno script,](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) impostare il parametro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" su 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versioni del sistema operativo quando si usa Azure Defender per server
Le versioni del sistema operativo seguenti sono supportate quando si usa [Azure Defender per server](/azure/security-center/security-center-wdatp):

Versione del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Windows Server 2016 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Impostazioni di connettività necessarie
Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici, aggiungere i domini elencati nel foglio di lavoro scaricabile all'elenco di domini consentiti.

Nel foglio di calcolo scaricabile seguente sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi. Verificare che non vi siano regole di filtro del firewall o della rete che negherebbero l'accesso a questi URL o creeranno *una regola di* consenti specifica per loro.

Foglio di calcolo dell'elenco domini | Descrizione
:-----|:-----
![Immagine thumb per il foglio di calcolo degli URL di Microsoft Defender per endpoint](images/mdatp-urls.png)<br/> | Foglio di calcolo di record DNS specifici per posizioni di servizio, posizioni geografiche e sistema operativo. <br /><br />[Scarica il foglio di calcolo qui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Per ulteriori informazioni, vedere Configurare [le impostazioni del proxy del dispositivo e della connettività Internet](configure-proxy-internet.md).

> [!NOTE]
> Il foglio di calcolo contiene anche URL commerciali, assicurati di controllare le schede "US Gov".
> 
> Quando filtri, cerca i record etichettati come "US Gov" e il tuo cloud specifico sotto la colonna geography.

### <a name="service-backend-ip-ranges"></a>Intervalli IP back-end del servizio

Se i dispositivi di rete non supportano regole basate su DNS, utilizzare invece intervalli IP.

Defender for Endpoint per i clienti del governo degli Stati Uniti è stato creato nell'ambiente Azure US Government, distribuito nelle aree seguenti:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

È possibile trovare gli intervalli IP di Azure in [Intervalli IP di Azure e tag di servizio - US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Come soluzione basata sul cloud, gli intervalli di indirizzi IP possono cambiare. Si consiglia di passare alle regole basate su DNS.

<br />

## <a name="api"></a>API
Anziché gli URI pubblici elencati nella nostra [documentazione api,](apis-intro.md)è necessario utilizzare gli URI seguenti:

Tipo di endpoint | GCC | GCC DoD ad alta &
:---|:---|:---
Accesso | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender per l'API endpoint | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
Siem | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Parità di funzionalità con commerciale
Defender for Endpoint per i clienti del governo degli Stati Uniti non ha la parità completa con l'offerta commerciale. Sebbene il nostro obiettivo sia quello di fornire tutte le funzionalità commerciali ai nostri clienti del governo degli Stati Uniti, ci sono alcune funzionalità non ancora disponibili che vogliamo evidenziare.

Queste sono le lacune note:

Nome della funzionalità | GCC | GCC High | DoD
:---|:---|:---|:---
Gestione e API: API di streaming | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Filtro contenuti Web | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Integrazioni: Azure Sentinel | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) Avvisi <br /> ![No](images/svg/check-no.svg) Incidenti & dati grezzi: in fase di sviluppo | ![Sì](images/svg/check-yes.svg) Avvisi <br /> ![No](images/svg/check-no.svg) Incidenti & dati grezzi: in fase di sviluppo
Integrazioni: Microsoft Cloud App Security | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Integrazioni: Microsoft Compliance Manager | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Integrazioni: Microsoft Defender per l'identità | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Integrazioni: Microsoft Endpoint DLP | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Integrazioni: Microsoft Intune | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Integrazioni: Microsoft Power Automate & App per la logica di Azure | ![Sì](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) Nello sviluppo | ![No](images/svg/check-no.svg) Nello sviluppo
Microsoft Threat Experts | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione | ![No](images/svg/check-no.svg) Sul backlog di progettazione
