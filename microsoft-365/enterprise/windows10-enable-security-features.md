---
title: Distribuzione di funzionalità di sicurezza di Windows 10 Enterprise
description: Istruzioni generali operazioni che è necessario distribuire Enterprise 10 Windows su PC come parte di Microsoft 365 Enterprise.
keywords: Protezione di Windows 10 Enterprise, documentazione Microsoft 365 Microsoft 365 Microsoft 365 Enterprise
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868919"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Passaggio 5: Distribuzione di funzionalità di sicurezza di Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 offre funzionalità per garantire la protezione contro le minacce, Guida proteggere i dispositivi e Guida per il controllo di accesso. 

Per ulteriori informazioni su queste tecnologie, vedere:
* [Protezione dell'accesso](https://docs.microsoft.com/windows/access-protection/) - informazioni su access controllo S/MIME, i certificati digitali, credenziali di protezione, controllo dell'Account utente virtuale smart card, Windows Hello per Business, Windows Firewall con protezione avanzata e altre risorse
* [Sicurezza dei dispositivi](https://docs.microsoft.com/windows/device-security/) - include AppLocker, BitLocker, protezione del dispositivo e Trusted Platform Module
* [Protezione da minacce](https://docs.microsoft.com/windows/threat-protection/) - include Defender Centro sicurezza PC Windows, la protezione di Windows Defender avanzate rischio, Antivirus Defender Windows, Windows Defender applicazione Guard, Windows Defender Smart schermata e la protezione delle informazioni di Windows

Questo passaggio viene illustrato come è possibile distribuire, gestire, configurare e risolvere i problemi utilizzando le funzionalità di protezione:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) è una soluzione antimalware incorporato in Windows 10. Fornisce gestione antimalware e protezione per i server, computer portatili e desktop. Per ulteriori informazioni su Windows Defender AV, i requisiti minimi e come è possibile gestire questa funzionalità, vedere [Windows Defender Antivirus 10 Windows e Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Se non si utilizzano Windows Defender AV come client primario antivirus o se si utilizza anche degli strumenti di analisi di Windows Defender, esistono alcune considerazioni è necessario prendere in considerazione. Per ulteriori informazioni, vedere [compatibilità di Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Distribuzione e gestione
Per distribuire e gestire Windows Defender AV, seguire le istruzioni di seguito:

* [Distribuire, gestire e report su Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Argomenti di riferimento per gli strumenti di configurazione e gestione](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configurazione
Gli utenti possono configurare una serie di funzionalità. Per ulteriori informazioni, vedere le seguenti risorse:

* [Configurare le funzionalità audio/video Defender Windows](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Argomenti di riferimento per gli strumenti di configurazione e gestione](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Consente di acquisire familiarità con le opzioni di configurazione, fare riferimento a questo elenco di tutte le impostazioni (come definita per la configurazione di criteri di gruppo): [le impostazioni di utilizzare criteri di gruppo per configurare e gestire Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

È possibile utilizzare la [protezione di Windows Defender AV Guida alla valutazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) che consentono di valutare il livello di protezione e l'impatto di Windows Defender AV nella rete. Questo può essere utile per la creazione di una configurazione iniziale o come "Guida di avvio rapido" e viene aggiornato periodicamente per fornire i suggerimenti più utili per la configurazione e abilitazione della funzionalità garantire la massima protezione.

### <a name="reporting"></a>Creazione di rapporti
È possibile ottenere report utilizzando uno strumento di configurazione, ad esempio System Center Configuration Manager o Microsoft Intune. È inoltre possibile ottenere report dall'aggiornamento conformità OUTLOOKMOBILE_1ST_NOVER o dall'utilizzo dei registri eventi di Windows nel SIEM. Se si dispone di una licenza per strumenti di analisi di Windows Defender, è possibile ottenere report nei rilevamenti Windows Defender AV ed eseguire risoluzione dei problemi di base. Per ulteriori informazioni, vedere le seguenti risorse:
* [Distribuire, gestire e report su Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Report sulla protezione di Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Panoramica degli strumenti di analisi di Windows Defender del portale](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Risoluzione dei problemi
Per informazioni sulla risoluzione dei problemi relativi a dei codici di errore e di eventi, vedere [esaminare i registri eventi e i codici di errore per la risoluzione dei problemi di Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

È inoltre possibile inviare problemi (ad esempio falsi positivi) tramite il sistema di invio di Business Intelligence di protezione di Windows Defender. Per ulteriori informazioni, vedere [problemi di invio a Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender sfruttare Guard è un nuovo set di funzionalità di protezione contro intrusioni host per Windows 10. Per ulteriori informazioni su Windows Defender sfruttare Guard, i requisiti minimi e come è possibile gestire questa funzionalità, vedere [Windows Defender sfruttare Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Distribuzione, gestione e configurazione
Per distribuire, gestire e configurare Windows Defender sfruttare Guard, seguire le istruzioni di seguito:
* [Sfrutta la protezione](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Protezione della superficie di attacco](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Protezione della rete](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Controllare l'accesso alle cartelle](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

È possibile utilizzare una serie di argomenti valutazione che consentono di valutare il livello di protezione e l'impatto di Windows Defender sfruttare Guard nella rete. Può essere anche utile nella creazione di una configurazione iniziale o come "Guida di avvio rapido" e gli argomenti e le istruzioni vengono aggiornate con regolarità per fornire i suggerimenti più utili per la configurazione e abilitazione della funzionalità garantire la massima protezione. Per ulteriori informazioni, [Valutazione di Windows Defender sfruttare Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Creazione di rapporti
È possibile ottenere report utilizzando uno strumento di configurazione, ad esempio System Center Configuration Manager o Intune. È inoltre possibile ottenere reporting tramite i registri eventi di Windows nel SIEM. Se si dispone di una licenza per strumenti di analisi di Windows Defender, è possibile ottenere report nei rilevamenti Windows Defender AV ed eseguire risoluzione dei problemi di base. Per ulteriori informazioni, vedere le seguenti risorse:
* [Visualizzare gli eventi di Windows Defender sfruttare Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Panoramica degli strumenti di analisi di Windows Defender del portale](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Risoluzione dei problemi
È possibile eseguire la risoluzione dei problemi di base o se lo si desidera fornire a Microsoft file CAB e inviare problemi (ad esempio falsi positivi) tramite il sistema di invio di Business Intelligence di protezione di Windows Defender. Per ulteriori informazioni, vedere [problemi di invio a Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender degli strumenti di analisi, disponibile solo con il piano di Microsoft 365 Enterprise E5 è un servizio di sicurezza che consente agli utenti dell'organizzazione individuare, analizzare e rispondere alle minacce avanzate sulle loro reti. Per ulteriori informazioni su strumenti di analisi di Windows Defender, i requisiti minimi e come è possibile gestire questa funzionalità, vedere:

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisiti minimi](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Distribuzione, gestione e configurazione
Per la distribuzione degli strumenti di analisi di Windows Defender, è necessario avere a disposizione il diritto di licenza di Windows. Dopo aver verificato che si dispone della licenza adatto, è necessario decidere georilevazione per cui verranno archiviati i dati. Al termine, è possibile avviare onboarding endpoint per il servizio.

Per ulteriori informazioni su questi passaggi, vedere gli argomenti principali: 

* [Convalidare il provisioning delle licenze e terminare la configurazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Privacy e archiviazione dei dati](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Endpoint incorporato e access il programma di installazione](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Individuare, analizzare, rispondere
Dopo aver correttamente onboarding endpoint per il servizio, è possibile avviare analisi dei avvisi dal dashboard diversi. Dopo aver aver analizzato gli avvisi, è possibile eseguire le azioni di risposta gli avvisi. 

Per ulteriori informazioni su come eseguire le operazioni seguenti, vedere:
* [Panoramica degli strumenti di analisi di Windows Defender del portale](https://go.microsoft.com/fwlink/?linkid=861596)
* [Utilizzare il portale degli strumenti di analisi di Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Eseguire operazioni di risposta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrazione con strumenti e altri prodotti
Degli strumenti di analisi di Windows Defender integra e supporta diversi altri prodotti e strumenti per espandere le funzionalità di sicurezza. 

Per ulteriori informazioni su strumenti e altri prodotti, vedere:
* [Strumenti SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Consente di creare avvisi personalizzati](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Utilizzare le API](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Creare report Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Risoluzione dei problemi
Potrebbero verificarsi problemi durante on-boarding o l'utilizzo del prodotto. Per ulteriori informazioni su come risolvere i problemi, vedere:
* [Risoluzione dei problemi di on-boarding](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Risoluzione dei problemi di Windows Defender degli strumenti di analisi](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Passaggio successivo

[Criteri di uscita dell'infrastruttura Windows 10 Enterprise](windows10-exit-criteria.md)
