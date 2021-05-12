---
title: Microsoft Defender per endpoint per clienti del governo degli Stati Uniti
description: Informazioni sui requisiti e le funzionalità di Microsoft Defender for Endpoint per i clienti del governo statunitense disponibili
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
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
ms.openlocfilehash: 189cb574a436a457cce312f6cb02ca1bf7863a18
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333495"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender per endpoint per clienti del governo degli Stati Uniti

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint per i clienti us government, creato nell'ambiente Azure US Government, usa le stesse tecnologie sottostanti di Defender per Endpoint in Azure Commercial.

Questa offerta è disponibile per i clienti GCC, GCC High e DoD ed è basata sulla stessa prevenzione, rilevamento, indagine e correzione della versione commerciale. Tuttavia, esistono alcune differenze nella disponibilità delle funzionalità per questa offerta.

> [!NOTE]
> Se sei un cliente GCC che usa Defender for Endpoint in Commercial, fai riferimento alle pagine della documentazione pubblica.

## <a name="licensing-requirements"></a>Requisiti per la licenza
Microsoft Defender for Endpoint per i clienti del governo statunitense richiede una delle seguenti offerte di contratti multilicenza Microsoft:

### <a name="desktop-licensing"></a>Licenze desktop
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 per GCC High | Windows 10 Enterprise E5 per DOD
| | Microsoft 365 E5 per GCC High | Microsoft 365 G5 per DOD
| | Microsoft 365 G5 Security for GCC High | Microsoft 365 G5 Security for DOD
Microsoft Defender per endpoint - GCC | Microsoft Defender per Endpoint per GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>Licenze server
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender per Endpoint Server GCC | Microsoft Defender per Endpoint Server per GCC High | Microsoft Defender per Endpoint Server per DOD
Azure Defender per server | Azure Defender per server - Enti pubblici | Azure Defender per server - Enti pubblici

<br />

## <a name="portal-urls"></a>URL portale
Di seguito sono riportati gli URL del portale di Microsoft Defender for Endpoint per i clienti del governo statunitense:

Tipo di cliente | URL portale
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Versioni degli endpoint

### <a name="standalone-os-versions"></a>Versioni autonome del sistema operativo
Sono supportate le versioni del sistema operativo seguenti:

Versione del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, versione 20H2 (con [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 2004 (con [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1909 (con [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1903 (con [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1809 (con [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10, versione 1803 (con [KB4598245](https://support.microsoft.com/help/4598245)) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows 10 versione 1709 | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![Sì ](images/svg/check-yes.svg) con [KB4499147](https://support.microsoft.com/help/4499147)<br />Nota: [deprecato](/lifecycle/announcements/revised-end-of-service-windows-10-1709), eseguire l'aggiornamento | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato
Windows 10, versione 1703 e versioni precedenti | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato | ![No](images/svg/check-no.svg)<br />Nota: non sarà supportato
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
Android | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione
iOS | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione

> [!NOTE]
> Se viene specificata una patch, deve essere distribuita prima dell'onboarding del dispositivo per configurare Defender per Endpoint nell'ambiente corretto.

> [!NOTE]
> Si sta tentando di eseguire l'onboard di dispositivi Windows precedenti a Windows 10 o Windows Server 2019 con [Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) È necessario scegliere "Azure US Government" in "Azure [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)Cloud" se si [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) utilizza la configurazione guidata o se si utilizza una riga di comando o uno [script,](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) impostare il parametro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" su 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versioni del sistema operativo quando si usa Azure Defender per i server
Le versioni del sistema operativo seguenti sono supportate quando si usa [Azure Defender per i server:](/azure/security-center/security-center-wdatp)

Versione del sistema operativo | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Windows Server 2016 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Impostazioni di connettività necessarie
Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici, aggiungere i domini elencati nel foglio di lavoro scaricabile all'elenco di domini consentiti.

Il foglio di calcolo scaricabile seguente elenca i servizi e gli URL associati a cui la rete deve essere in grado di connettersi. Verificare che non siano presenti regole di filtro firewall o di rete che neghino l'accesso *a* questi URL o creino una regola di autorizzazione specifica per tali URL.

Foglio di calcolo dell'elenco dei domini | Descrizione
:-----|:-----
![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/> | Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo. <br /><br />[Scaricare il foglio di calcolo qui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Per ulteriori informazioni, vedere [Configure device proxy and Internet connectivity settings.](configure-proxy-internet.md)

> [!NOTE]
> Il foglio di calcolo contiene anche URL commerciali, assicurati di controllare le schede "US Gov".
> 
> Quando si filtra, cercare i record etichettati come "US Gov" e il cloud specifico nella colonna geography.

### <a name="service-backend-ip-ranges"></a>Intervalli IP back-end del servizio

Se i dispositivi di rete non supportano le regole basate su DNS, usa invece intervalli IP.

Defender for Endpoint per i clienti us government è stato creato nell'ambiente Azure US Government, distribuito nelle aree geografiche seguenti:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Gli intervalli IP di Azure sono disponibili in [Azure IP Ranges and Service Tags – US Government Cloud.](https://www.microsoft.com/download/details.aspx?id=57063)

> [!NOTE]
> Come soluzione basata sul cloud, gli intervalli di indirizzi IP possono cambiare. È consigliabile passare a regole basate su DNS.

<br />

## <a name="api"></a>API
Anziché gli URI pubblici elencati nella documentazione [dell'API,](apis-intro.md)dovrai usare gli URI seguenti:

Tipo di endpoint | GCC | GCC High & DoD
:---|:---|:---
Accesso | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender for Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Parità delle funzionalità con commerciale
Defender for Endpoint per i clienti del governo statunitense non ha la parità completa con l'offerta commerciale. Anche se il nostro obiettivo è fornire tutte le funzionalità e le funzionalità commerciali ai clienti del governo degli Stati Uniti, alcune funzionalità non sono ancora disponibili che vogliamo evidenziare.

Queste sono le lacune note:

Nome della funzionalità | GCC | GCC High | DoD
:---|:---|:---|:---
Gestione e API: API di streaming | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg)
Filtro contenuti Web | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Integrazioni: Azure Sentinel | ![Sì](images/svg/check-yes.svg) | ![Sì](images/svg/check-yes.svg) Avvisi <br /> ![No](images/svg/check-no.svg) Eventi imprevisti & dati non elaborati: in fase di sviluppo | ![Sì](images/svg/check-yes.svg) Avvisi <br /> ![No](images/svg/check-no.svg) Eventi imprevisti & dati non elaborati: in fase di sviluppo
Integrazioni: Microsoft Cloud App Security | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Integrazioni: Microsoft Compliance Manager | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Integrazioni: Microsoft Defender for Identity | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Integrazioni: MICROSOFT Endpoint DLP | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione
Integrazioni: Microsoft Intune | ![Sì](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Integrazioni: Microsoft Power Automate & app per la logica di Azure | ![Sì](images/svg/check-yes.svg) | ![No](images/svg/check-no.svg) In fase di sviluppo | ![No](images/svg/check-no.svg) In fase di sviluppo
Microsoft Threat Experts | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione | ![No](images/svg/check-no.svg) Backlog di progettazione
