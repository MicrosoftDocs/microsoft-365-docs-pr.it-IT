---
title: Distribuire le funzionalità di sicurezza di Windows 10 Enterprise
description: Fornisce una guida di alto livello sui passaggi necessari per distribuire le funzionalità di sicurezza di Windows 10 Enterprise nei PC come parte di Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, sicurezza
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: c1c39745b2dc891b4dc079ecd657eaf0d883af23
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627460"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Passaggio 5: distribuire le funzionalità di sicurezza di Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 fornisce funzionalità di sicurezza per proteggere gli utenti dell'organizzazione, arrestare Cyberthreats e prevenire la perdita di dati. 

Per ulteriori informazioni su queste tecnologie, vedere:

* [Identity Protection](https://docs.microsoft.com/windows/security/identity-protection/) -informazioni su Windows Hello for business, la protezione delle credenziali e il controllo di accesso.
* [Protezione dalle minacce](https://docs.microsoft.com/windows/threat-protection/) : informazioni su Microsoft Defender Advanced Threat Protection, una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'analisi automatizzata e la risposta.
* [Information Protection-informazioni](https://docs.microsoft.com/windows/security/information-protection/) su BitLocker, Windows Information Protection e altri modi in cui Windows 10 consente di proteggere i dati dell'organizzazione. 

Questo passaggio illustra come è possibile distribuire, gestire, configurare e risolvere i problemi utilizzando queste funzionalità di sicurezza:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Microsoft Defender Advanced Threat Protection](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) è una soluzione antimalware incorporata in Windows 10. Fornisce la gestione della sicurezza e antimalware per desktop, computer portatili e server. Per ulteriori informazioni su Windows Defender AV, i requisiti minimi e su come gestire questa funzionalità, vedere [Windows Defender antivirus in Windows 10 e Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Se non si utilizza Windows Defender AV come client antivirus principale o se si utilizza anche Microsoft Defender ATP, è necessario tenere in considerazione alcune considerazioni. Per ulteriori informazioni, vedere [compatibilità con Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Distribuzione e gestione
Per distribuire e gestire Windows Defender AV, seguire le istruzioni riportate di seguito:

* [Distribuire, gestire e segnalare su Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Argomenti di riferimento per gli strumenti di gestione e configurazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configurazione
Gli utenti possono configurare una serie di funzionalità. Per altre informazioni, vedere le risorse seguenti:

* [Configurare le funzionalità di Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Argomenti di riferimento per gli strumenti di gestione e configurazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Per informazioni sulle opzioni di configurazione, fare riferimento a questo elenco di tutte le impostazioni (come definito dalla configurazione dei criteri di gruppo): [utilizzare le impostazioni di criteri di gruppo per configurare e gestire Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

È possibile utilizzare la [Guida di valutazione di protezione AV di Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) per valutare il livello di protezione e l'impatto di Windows Defender AV sulla rete. Questo può essere utile anche nella creazione di una configurazione iniziale o come "Guida introduttiva" e viene aggiornato regolarmente per fornire i suggerimenti più utili per la configurazione e l'abilitazione delle caratteristiche per garantire la massima protezione.

### <a name="reporting"></a>Reporting
È possibile ottenere i report utilizzando uno strumento di configurazione, ad esempio Microsoft endpoint Configuration Manager o Microsoft Intune. È inoltre possibile ottenere i report da Update Compliance (OMS) o dal consumo di registri eventi di Windows in SIEM. Se si dispone di una licenza per Microsoft Defender ATP, è anche possibile ottenere rapporti nei rilevamenti AV di Windows Defender ed eseguire la correzione di base. Per altre informazioni, vedere le risorse seguenti:
* [Distribuire, gestire e segnalare su Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Relazione sulla protezione AV di Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Panoramica del portale di Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Risoluzione dei problemi
Per informazioni sulla risoluzione dei problemi di base per i codici di errore e di evento, vedere [Review Event Logs and error codes to troubleshoot issues with Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

È inoltre possibile inviare problemi (come falsi positivi) utilizzando il sistema di invio di intelligence di sicurezza di Windows Defender. Per informazioni, vedere [inviare problemi a Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender exploit Guard è un nuovo set di funzionalità di prevenzione delle intrusioni host per Windows 10. Per ulteriori informazioni su Windows Defender exploit Guard, i requisiti minimi e su come gestire questa funzionalità, vedere [Windows Defender exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Distribuzione, gestione e configurazione
Per distribuire, gestire e configurare Windows Defender exploit Guard, seguire le istruzioni riportate di seguito:
* [Protezione da exploit](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Protezione della superficie di attacco](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Protezione di rete](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Accesso alla cartella controllata](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

È possibile utilizzare una serie di argomenti di valutazione per contribuire a valutare il livello di protezione e l'impatto di Windows Defender exploit Guard sulla rete. Questo può essere utile anche nella creazione di una configurazione iniziale o come "Guida introduttiva" e gli argomenti e le linee guida vengono aggiornati regolarmente per fornire i suggerimenti più utili per la configurazione e l'abilitazione delle caratteristiche per garantire la massima protezione. Per altre informazioni, [valutare Windows Defender exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
È possibile ottenere i report utilizzando uno strumento di configurazione, ad esempio Configuration Manager o Intune. È inoltre possibile ottenere i report utilizzando i registri eventi di Windows in SIEM. Se si dispone di una licenza per Microsoft Defender ATP, è anche possibile ottenere rapporti nei rilevamenti AV di Windows Defender ed eseguire la correzione di base. Per altre informazioni, vedere le risorse seguenti:
* [Visualizzare gli eventi di Windows Defender exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Panoramica del portale di Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Risoluzione dei problemi
È possibile eseguire la risoluzione dei problemi di base o facoltativamente fornire i file con estensione cab e inviare problemi (ad esempio, falsi positivi) utilizzando il sistema di invio di intelligence di sicurezza di Windows Defender. Per informazioni, vedere [inviare problemi a Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection
Microsoft Defender ATP, disponibile solo con il piano Microsoft 365 Enterprise E5, è un servizio di sicurezza che consente ai clienti aziendali di rilevare, analizzare e rispondere alle minacce avanzate nelle reti. Per ulteriori informazioni su Microsoft Defender ATP, i requisiti minimi e su come gestire questa funzionalità, vedere:

* [ATP Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisiti minimi](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Distribuzione, gestione e configurazione
Per distribuire Microsoft Defender ATP, è necessario assicurarsi di disporre della licenza di Windows per il diritto. Dopo aver verificato la corretta licenza, è necessario decidere la Geolocation per la posizione in cui verranno archiviati i dati. Successivamente, è possibile iniziare a onboarding endpoints to the Service.

Per ulteriori informazioni su questi passaggi, vedere i seguenti argomenti principali: 

* [Convalidare il provisioning delle licenze e il set up completo](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Archiviazione e privacy dei dati](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Endpoint di bordo e accesso all'installazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Rilevare, indagare, rispondere
Dopo aver eseguito l'onboarding degli endpoint per il servizio, è possibile iniziare a esaminare gli avvisi provenienti dai vari dashboard. Dopo aver esaminato gli avvisi, è possibile eseguire azioni di risposta sugli avvisi. 

Per altre informazioni su come eseguire queste operazioni, vedere:
* [Panoramica del portale di Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=861596)
* [Utilizzare il portale ATP Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Eseguire le azioni di risposta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrazione con altri prodotti e strumenti
Microsoft Defender ATP integra e supporta vari altri prodotti e strumenti per espandere le proprie funzionalità di sicurezza. 

Per altre informazioni sugli strumenti e altri prodotti, vedere:
* [Strumenti di SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Creare avvisi personalizzati](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Utilizzo delle API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Creare report di Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Risoluzione dei problemi
È possibile che si verifichino problemi durante l'onboarding o durante l'utilizzo del prodotto. Per altre informazioni su come risolvere i problemi, vedere:
* [Risoluzione dei problemi relativi all'onboarding](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Risoluzione dei problemi relativi a Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di Windows 10 Enterprise](windows10-exit-criteria.md)
