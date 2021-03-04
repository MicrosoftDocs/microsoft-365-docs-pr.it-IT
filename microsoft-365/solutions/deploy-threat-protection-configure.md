---
title: Passaggi per configurare le funzionalità di protezione dalle minacce in Microsoft 365
description: Informazioni su come distribuire servizi e funzionalità di protezione dalle minacce in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 01f11ee16c45b171d04fb382f65fa95ff84bf980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424169"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurare le funzionalità di protezione dalle minacce in Microsoft 365

Seguire questa procedura per configurare la protezione dalle minacce in Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Passaggio 1: Configurare l'autenticazione a più fattori e i criteri di accesso condizionale

[L'autenticazione a più](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) fattori (MFA) richiede agli utenti di verificare la propria identità con una chiamata telefonica o un'app di autenticazione. [I criteri di accesso](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) condizionale definiscono determinati requisiti che devono essere soddisfatti per consentire agli utenti di accedere alle app e ai dati in Microsoft 365. L'autenticazione a più fattori e i criteri di accesso condizionale funzionano insieme per proteggere l'organizzazione. Ad esempio, se un utente tenta di accedere da un dispositivo mobile usando un account non abilitato per l'autenticazione a più fattori e un criterio di accesso condizionale richiede che l'autenticazione a più fattori sia attiva, all'utente verrà impedito di eseguire l'accesso.  

Microsoft ha testato e consigliato un set specifico di accesso condizionale e criteri correlati per proteggere l'accesso a tutte le applicazioni SaaS, in particolare Microsoft 365. I criteri sono consigliati per la protezione di base, sensibile ed estremamente regolamentata. Iniziare implementando i criteri per la protezione di base. 


[ ![ Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)Vedere una versione più grande di questa 
 [immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Per implementare la protezione di base per Microsoft 365

![Processo di distribuzione della protezione di base](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Configurare i prerequisiti, incluso Azure AD Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Configurare i criteri comuni di identità e accesso ai dispositivi per](../security/office-365-security/identity-access-policies.md) la protezione di base.
3. Configurare i criteri [per gli utenti guest,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online,](../security/office-365-security/secure-email-recommended-policies.md) [SharePoint Online e OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Ulteriori informazioni sulla protezione delle identità

- [Configurazioni di identità e accesso dei dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Indicazioni sulla sicurezza per Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Passaggio 2: Configurare Microsoft Defender per l'identità

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) è una soluzione di sicurezza basata sul cloud che funziona con i segnali di Active Directory Domain Services (AD DS) locali per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni Insider dannose indirizzate all'organizzazione.

Microsoft Defender for Identity consente agli analisti e ai professionisti della sicurezza (SecOps) di rilevare attacchi avanzati in ambienti ibridi per:
- Monitorare gli utenti, il comportamento delle entità e le attività con l'analisi basata sull'apprendimento.
- Proteggere le identità utente e le credenziali archiviate in Active Directory.
- Identificare e analizzare le attività utente sospette e gli attacchi avanzati per tutta la kill chain.
- Fornire informazioni chiare sull'incidente in una sequenza temporale semplice per la valutazione veloce.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Per configurare Microsoft Defender for Identity

![Processo per la distribuzione di Microsoft Defender for Identity](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Configurare Microsoft Defender for Identity per](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) proteggere gli ambienti principali.
2. Proteggere tutti i [controller di dominio e](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) le [foreste.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integrare [gli avvisi di Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) nel flusso di lavoro delle operazioni di sicurezza (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Ulteriori informazioni su Microsoft Defender for Identity

- [Che cosa è Microsoft Defender per identità?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Introduzione a Microsoft Defender per l'identità](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Distribuzione di Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Passaggio 3: attivare Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combina i segnali e orchestra le funzionalità in un'unica soluzione. Con la soluzione microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia che ognuno di questi prodotti riceve e determinare l'ambito completo e l'impatto della minaccia; come è entrato nell'ambiente, cosa ne è interessato e in che modo influisce attualmente sull'organizzazione. Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati.

Microsoft 365 Defender unifica avvisi, eventi imprevisti, analisi e risposta automatizzate e ricerca avanzata tra i carichi di lavoro (Microsoft Defender for Identity, Microsoft Defender per Office 365, Microsoft Defender for Endpoint e Microsoft Cloud App Security) in un unico riquadro di esperienza di visualizzazione. Dopo aver configurato uno o più servizi di Defender per Office 365, attivare Microsoft 365 Defender. Le nuove funzionalità vengono aggiunte continuamente a Microsoft 365 Defender; Prendi in considerazione la possibilità di acconsentire esplicitamente alla ricezione delle funzionalità di anteprima.

### <a name="to-set-up-microsoft-365-defender"></a>Per configurare Microsoft 365 Defender

![Processo per la distribuzione di Microsoft 365 Defender](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Esaminare i prerequisiti.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Attivare Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Acconsentire esplicitamente alle funzionalità di anteprima.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Ulteriori informazioni su Microsoft 365 Defender

- [Che cos'è Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Novità di Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Passaggio 4: Configurare Microsoft Defender per Office 365

[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) protegge l'organizzazione dalle minacce dannose nei messaggi di posta elettronica (allegati e URL), nei documenti di Office e negli strumenti di collaborazione. Nella tabella seguente sono elencate le funzionalità e le funzionalità di Microsoft Defender per Office 365 incluse in Microsoft 365 E5:

|Funzionalità di configurazione, protezione e rilevamento|Funzionalità di automazione, analisi, correzione ed istruzione|
|---|---|
|[Allegati sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Sicurezza documenti](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP per SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Anti-phishing in Defender per la protezione di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Tracker delle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Esplora minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Analisi e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Simulatore di attacchi](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Con Microsoft Defender per Office 365, le persone all'interno dell'organizzazione possono comunicare e collaborare in modo più sicuro, con la protezione dalle minacce per il contenuto della posta elettronica e i documenti di Office.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Per configurare Microsoft Defender per Office 365

![Processo di distribuzione di Microsoft Defender per Office 365](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Configurare i criteri di Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
2. [Visualizzare e usare i report di Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Usare le funzionalità di analisi e risposta alle minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Ulteriori informazioni su Microsoft Defender per Office 365

- [Panoramica di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Novità di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Passaggio 5: Configurare Microsoft Defender per l'endpoint

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) protegge i dispositivi delle organizzazioni (denominati anche endpoint) da minacce informatiche, attacchi avanzati e violazioni dei dati. I team di sicurezza possono essere più efficienti nella gestione della sicurezza degli endpoint. Strumenti affidabili consentono alle organizzazioni di tenere il passo con i sistemi senza problemi che usano il rilevamento delle vulnerabilità con la gestione delle [minacce e delle vulnerabilità.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Le funzionalità di rilevamento e correzione automatizzate, come la riduzione della superficie [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) di [attacco,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)la protezione di nuova [generazione,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)il rilevamento e la risposta degli [endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)e l'analisi e la correzione automatizzate consentono di proteggere i dispositivi dal malware. Oltre a queste funzionalità, i clienti possono ricevere notifiche proattive e consultarsi con Microsoft Threat Experts su richiesta, come parte del servizio di ricerca gestita con consenso esplicito. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurare Microsoft Defender per Endpoint

![Processo per la distribuzione di Microsoft Defender per Endpoint](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Preparare Microsoft Defender per la distribuzione degli endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Configurare la distribuzione di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Eseguire l'onboard nel servizio Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Completare le principali attività amministrative relative alla sicurezza.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Altre informazioni su Microsoft Defender per Endpoint

- [Altre informazioni su Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)
- [Prova il lab di valutazione di Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Passaggio 6: Configurare Microsoft Cloud App Security

[Microsoft Cloud App Security è](https://docs.microsoft.com/cloud-app-security) un Cloud Access Security Broker che supporta la raccolta di log, i connettori API e il proxy inverso. Microsoft Cloud App Security offre visibilità avanzata, controllo sui viaggi dei dati e analisi sofisticate per identificare e contrastare le minacce informatiche in tutti i servizi cloud. Con Microsoft Cloud App Security, le operazioni di sicurezza possono proteggere le informazioni riservate dell'organizzazione, proteggersi da minacce informatiche e anomalie, individuare e monitorare le app che accedono ai dati dell'organizzazione e garantire che le app cloud dell'organizzazione soddisfino i requisiti di conformità.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurare Microsoft Cloud App Security

![Processo di distribuzione di Microsoft Cloud App Security](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Configurare il portale e altri requisiti di base.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Configurare l'individuazione cloud](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) e [connettere le app.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Distribuire il controllo delle app di accesso condizionale per le app in primo piano.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Utilizzare gli strumenti di analisi e i dashboard.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Ulteriori informazioni su Microsoft Cloud App Security

- [Esaminare le nuove caratteristiche e le nuove funzionalità.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Altre informazioni su Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Passaggio 7: monitorare lo stato ed eseguire azioni

Dopo aver configurato e distribuito i servizi e le funzionalità di protezione dalle minacce, il passaggio successivo consiste nel monitorare i rilevamenti delle minacce ed eseguire le azioni appropriate. Il punto di partenza migliore è il Centro sicurezza Microsoft 365 ( ), in cui è possibile monitorare e gestire la sicurezza tra [https://security.microsoft.com](https://security.microsoft.com) identità, dati, dispositivi, app e infrastruttura Microsoft. 

![Centro sicurezza Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

Il Centro sicurezza Microsoft 365 è destinato specificamente agli amministratori della sicurezza e ai team delle operazioni di sicurezza. Nel Centro sicurezza Microsoft 365 è possibile:
- Visualizzare l'integrità della sicurezza complessiva dell'organizzazione [con Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Monitorare e visualizzare report](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) sullo stato di identità, dati, dispositivi, app e infrastruttura.
- Connettere i punti sugli avvisi tramite [eventi imprevisti.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Usare [l'analisi e la correzione automatizzate per](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) affrontare le minacce.
- [Ricerca proattiva di minacce,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)ad esempio tentativi di intrusione o attività di violazione che interessano la posta elettronica, i dati, i dispositivi e le identità.
- [Comprendere le più recenti campagne di attacco e](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) le tecniche con l'analisi delle minacce.
- ... e altro ancora!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Ulteriori informazioni sul Centro sicurezza Microsoft 365

- [Introduzione al Centro sicurezza Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Monitorare e visualizzare i report.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Vedere i portali di sicurezza in Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Passaggio 8: formare gli utenti

La formazione degli utenti può consentire agli utenti e al team delle operazioni di sicurezza di risparmiare molto tempo e frustrazione. Gli utenti esperti hanno meno probabilità di aprire allegati o di fare clic su collegamenti in messaggi di posta elettronica discutibili ed è più probabile che evitino siti Web sospetti. 

Il manuale della campagna per la [cybersecurity](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) della scuola Disaffezione Disaffezione offre un'ottima guida per stabilire una forte cultura della sicurezza all'interno dell'organizzazione, inclusa la formazione degli utenti per identificare gli attacchi di phishing. 

Microsoft 365 fornisce le risorse seguenti per informare gli utenti dell'organizzazione:

|Concetti  |Risorse  |
|---------|---------|
|Microsoft 365     |[Percorsi di apprendimento personalizzabili](https://docs.microsoft.com/office365/customlearning/) <p>Queste risorse possono aiutare a mettere insieme la formazione per gli utenti finali nell'organizzazione        |
|Sicurezza Microsoft 365 |[Modulo di apprendimento: Proteggere l'organizzazione con sicurezza intelligente integrata di Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Questo modulo consente di descrivere il modo in cui le funzionalità di sicurezza di Microsoft 365 funzionano insieme e di illustrare i vantaggi di queste funzionalità di sicurezza. |
|Autenticazione a più fattori     | [Verifica in due passaggi: che cos'è la pagina di verifica aggiuntiva?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Questo articolo consente agli utenti finali di comprendere cos'è l'autenticazione a più fattori e perché viene utilizzata nell'organizzazione.    |

Oltre a queste indicazioni, Microsoft consiglia agli utenti di eseguire le azioni descritte in questo articolo: Proteggere [l'account](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)e i dispositivi da hacker e malware. Queste azioni includono:
- Uso di password complesse
- Protezione dei dispositivi 
- Abilitazione delle funzionalità di sicurezza nei PC Windows 10 e Mac (per dispositivi non gestiti)
    
Microsoft consiglia inoltre agli utenti di proteggere i propri account di posta elettronica personali seguendo le azioni consigliate negli articoli seguenti:
- [Proteggere l'account Outlook.com di posta elettronica](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteggere l'account Gmail con la verifica in due passaggi](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
