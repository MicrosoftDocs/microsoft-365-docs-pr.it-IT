---
title: Procedura per configurare le funzionalità di protezione dalle minacce in Microsoft 365
description: Informazioni su come distribuire i servizi e le funzionalità di protezione dalle minacce in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 5183e6f60d825ff523db4da165d16752b3aa3cc8
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399350"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurare le funzionalità di protezione dalle minacce in Microsoft 365

Seguire questa procedura per configurare la protezione delle minacce in Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Passaggio 1: configurare l'autenticazione a più fattori e i criteri di accesso condizionale

[L'autenticazione](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) a più fattori richiede agli utenti di verificare la propria identità con una chiamata telefonica o l'app Authenticator. I [criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definiscono alcuni requisiti che devono essere soddisfatti per consentire agli utenti di accedere alle app e ai dati in Microsoft 365. I criteri di accesso condizionale e di Mae interagiscono per proteggere l'organizzazione. Ad esempio, se un utente tenta di eseguire l'accesso da un dispositivo mobile utilizzando un account non abilitato per l'AMF e un criterio di accesso condizionale richiede che l'AMF sia attiva, non sarà possibile eseguire l'accesso.  

Microsoft ha testato e raccomandato una serie specifica di criteri di accesso condizionale e relativi per la protezione dell'accesso a tutte le applicazioni SaaS, in particolare Microsoft 365. I criteri sono consigliati per la protezione di base, sensibile e altamente regolamentata. Iniziare implementando i criteri per la protezione di base. 


[ ![ Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Per implementare la protezione di base per Microsoft 365

![Processo di distribuzione della protezione di base](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Configurare i prerequisiti, inclusa la protezione delle identità di Azure](../security/office-365-security/identity-access-prerequisites.md).
2. [Configurazione dei criteri comuni di identità e accesso ai dispositivi](../security/office-365-security/identity-access-policies.md) per la protezione della linea di base.
3. Configurare i criteri per [gli utenti Guest](../security/office-365-security/identity-access-policies-guest-access.md), [Microsoft teams](../security/office-365-security/teams-access-policies.md), [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)e [SharePoint Online e OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Ulteriori informazioni sulla protezione delle identità

- [Configurazioni di identità e accesso dei dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Linee guida per la sicurezza per Azure Mae](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>Passaggio 2: configurare Azure Advanced Threat Protection

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) è una soluzione di sicurezza basata sul cloud che funziona con i segnali di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) locali per identificare, rilevare ed esaminare le minacce avanzate, le identità compromesse e le azioni Insider dannose indirizzate alla propria organizzazione.

Azure ATP consente alle operazioni di sicurezza (secops) di analisti e professionisti della sicurezza che lottano per rilevare attacchi avanzati in ambienti ibridi per:
- Monitorare gli utenti, il comportamento delle entità e le attività con l'analisi basata sull'apprendimento.
- Proteggere le identità utente e le credenziali archiviate in Active Directory.
- Identificare e analizzare le attività utente sospette e gli attacchi avanzati per tutta la kill chain.
- Fornire informazioni chiare sull'incidente in una sequenza temporale semplice per la valutazione veloce.

### <a name="to-set-up-azure-atp"></a>Per configurare l'ATP di Azure

![Processo per la distribuzione di Azure ATP](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Configurare](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) l'ambiente ATP di Azure per proteggere gli ambienti principali.
2. Proteggere tutti i [controller di dominio](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) e le [foreste](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest).
3. Integrare gli [avvisi di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) nel flusso di lavoro operazioni di sicurezza (secops).

### <a name="more-information-about-azure-atp"></a>Ulteriori informazioni su Azure ATP

- [Che cos'è Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Introduzione a Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Distribuzione di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>Passaggio 3: abilitare Microsoft Threat Protection

[Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combina segnali e orchestra le funzionalità in una singola soluzione. Con la soluzione integrata Microsoft Threat Protection, i professionisti della sicurezza possono unire i segnali di minaccia che ognuno di questi prodotti riceve e determina l'intero ambito e l'impatto della minaccia; come è entrata nell'ambiente, cosa ne è interessata e come sta attualmente influenzando l'organizzazione. Microsoft Threat Protection interviene automaticamente per impedire o arrestare l'attacco e la correzione automatica delle cassette postali, degli endpoint e delle identità degli utenti.

Microsoft Threat Protection unifica gli avvisi, gli incidenti, l'analisi automatizzata e la risposta e la ricerca avanzata tra i carichi di lavoro (Azure ATP, Office 365 ATP, Microsoft Defender ATP e Microsoft cloud app Security) in un unico riquadro di Glass Experience. Dopo aver configurato uno o più servizi di protezione avanzata dalle minacce, abilitare Microsoft Threat Protection. Le nuove funzionalità vengono aggiunte continuamente a Microsoft Threat Protection; prendere in considerazione la possibilità di ricevere funzionalità di anteprima.

### <a name="to-set-up-microsoft-threat-protection"></a>Per configurare Microsoft Threat Protection

![Processo di distribuzione di Microsoft Threat Protection](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Esaminare i prerequisiti](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Attiva Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. [Opt-in per le funzionalità di anteprima](https://docs.microsoft.com/microsoft-365/security/mtp/preview).

### <a name="more-information-about-microsoft-threat-protection"></a>Ulteriori informazioni su Microsoft Threat Protection

- [Che cos’è Microsoft Threat Protection?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Novità di Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>Passaggio 4: configurare Office 365 Advanced Threat Protection

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) salvaguarda la propria organizzazione dalle minacce dannose nei messaggi di posta elettronica (allegati e URL), nei documenti di Office e negli strumenti di collaborazione. Nella tabella seguente sono elencate le funzionalità e le funzionalità ATP di Office 365 incluse in Microsoft 365 E5:

|Funzionalità di configurazione, protezione e rilevamento|Funzionalità di automazione, analisi, correzione e formazione|
|---|---|
|[Allegati sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Sicurezza documenti](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP per SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Protezione anti-phishing ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Tracker delle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Esplora minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Analisi e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Simulatore di attacchi](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Con Office 365 ATP, le persone all'interno dell'organizzazione possono comunicare e collaborare in modo più sicuro, con protezione dalle minacce per il contenuto della posta elettronica e i documenti di Office.

### <a name="to-set-up-office-365-atp"></a>Per configurare Office 365 ATP

![Processo per la distribuzione di Office 365 ATP](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Impostare e configurare i criteri ATP di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
2. [Visualizzare e usare i rapporti ATP di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Utilizzare le funzionalità di analisi e risposta alle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-office-365-atp"></a>Ulteriori informazioni su Office 365 ATP

- [Panoramica di Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Novità di Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>Passaggio 5: configurare Microsoft Defender Advanced Threat Protection

[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP) protegge i dispositivi delle organizzazioni (definiti anche endpoint) da Cyberthreats, attacchi avanzati e violazioni dei dati. I team di sicurezza possono essere più efficienti nella gestione della sicurezza degli endpoint. Gli strumenti robusti aiutano le organizzazioni a tenere il passo con i sistemi non inviati usando il rilevamento delle vulnerabilità con la [gestione di minacce e vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Le funzionalità di rilevamento e correzione automatizzate, ad esempio la [riduzione della superficie di attacco](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction), la protezione di [prossima generazione](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10), il [rilevamento e la risposta degli endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)e l' [analisi e la correzione automatizzate](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) consentono di mantenere i dispositivi sicuri da malware. Oltre a queste funzionalità, i clienti possono ottenere notifiche proattive e consultarsi con gli esperti di Microsoft Threat su richiesta, come parte del servizio di caccia gestito con consenso esplicito. 


### <a name="set-up-microsoft-defender-atp"></a>Configurare Microsoft Defender ATP

![Processo per la distribuzione di Microsoft Defender ATP](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Preparare la distribuzione ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Configurare la distribuzione ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Onboard to the Microsoft Defender ATP Service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Completare le attività amministrative di sicurezza principali](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation).

### <a name="more-information-about-microsoft-defender-atp"></a>Ulteriori informazioni su Microsoft Defender ATP

- [Per ulteriori informazioni, vedere ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection).
- [Provare il Microsoft Defender ATP Evaluation Lab](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Passaggio 6: configurare Microsoft cloud app Security

[Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security) è un broker di sicurezza per l'accesso cloud che supporta la raccolta di log, i connettori API e il proxy inverso. Microsoft cloud app Security offre una vasta visibilità, il controllo dei dati di viaggio e analisi sofisticate per identificare e combattere Cyberthreats in tutti i servizi cloud. Con Microsoft cloud app Security, le operazioni di sicurezza in grado di proteggere le informazioni riservate dell'organizzazione, proteggersi da Cyberthreats e anomalie, individuare e monitorare le app che accedono ai dati dell'organizzazione e contribuire a garantire che le app cloud dell'organizzazione soddisfino i requisiti di conformità.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurare Microsoft cloud app Security

![Processo per la distribuzione di Microsoft cloud app Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Configurare il portale e altri requisiti di base](https://docs.microsoft.com/cloud-app-security/general-setup).
2. [Configurare le app Cloud Discovery](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) e [Connect](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Distribuire il controllo delle app con accesso condizionale per le app in primo piano](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Utilizzare gli strumenti di analisi e i dashboard](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Ulteriori informazioni su Microsoft Cloud App Security

- [Esaminare nuove caratteristiche e funzionalità](https://docs.microsoft.com/cloud-app-security/release-notes).
- [Per ulteriori informazioni, vedere Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Passaggio 7: monitorare lo stato e intraprendere le azioni

Dopo aver configurato e distribuito i servizi e le funzionalità di protezione dalle minacce, il passaggio successivo consiste nel monitorare i rilevamenti delle minacce e nel prendere le azioni appropriate. Il punto di partenza migliore è Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), in cui è possibile monitorare e gestire la sicurezza tra le identità, i dati, i dispositivi, le app e l'infrastruttura di Microsoft. 

![Centro sicurezza Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 Security Center è stato appositamente progettato per gli amministratori della sicurezza e i team delle operazioni di sicurezza. Nel centro sicurezza Microsoft 365 è possibile:
- Visualizzazione dell'integrità generale della sicurezza dell'organizzazione con [Punteggio sicuro](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Monitorare e visualizzare i report](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) sullo stato delle identità, dei dati, degli strumenti, delle app e dell'infrastruttura.
- Connettere i punti su avvisi tramite [incidenti](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Utilizzare l' [analisi automatizzata e la correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) per risolvere le minacce.
- [Cercare in modo proattivo le minacce](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview), ad esempio i tentativi di intrusioni o le attività di violazione che interessano la posta elettronica, i dati, i dispositivi e le identità.
- [Comprendere le campagne e le tecniche di attacco più recenti](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) con Threat Analytics.
- ... e altro ancora!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Ulteriori informazioni sul centro sicurezza di Microsoft 365

- Iniziare [a usare il Centro sicurezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Monitorare e visualizzare i report](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Vedere i portali di sicurezza in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Passaggio 8: formazione degli utenti

Formazione gli utenti possono salvare gli utenti e le operazioni di sicurezza del team molto tempo e frustrazione. Gli utenti esperti hanno meno probabilità di aprire allegati o fare clic su collegamenti nei messaggi di posta elettronica discutibili e hanno maggiori probabilità di evitare siti Web sospetti. 

Il [manuale della campagna](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) di Harvard Kennedy School Cybersecurity fornisce indicazioni eccellenti sulla creazione di una forte cultura della consapevolezza della sicurezza all'interno dell'organizzazione, tra cui la formazione degli utenti per identificare gli attacchi di phishing. 

Microsoft 365 fornisce le risorse seguenti per informare gli utenti nell'organizzazione:

|Concetti  |Risorse  |
|---------|---------|
|Microsoft 365     |[Percorsi di apprendimento personalizzabili](https://docs.microsoft.com/office365/customlearning/) <p>Tali risorse consentono di creare una formazione per gli utenti finali nell'organizzazione        |
|Sicurezza Microsoft 365 |[Modulo di apprendimento: proteggere l'organizzazione con sicurezza integrata e intelligente da Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Questo modulo consente di descrivere in che modo le funzionalità di sicurezza di Microsoft 365 interagiscono e di articolare i vantaggi di queste funzionalità di sicurezza. |
|Autenticazione a più fattori     | [Verifica in due passaggi: che cos'è la pagina di verifica aggiuntiva?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Questo articolo aiuta gli utenti finali a capire cosa sia l'autenticazione a più fattori e il motivo per cui viene utilizzato all'interno dell'organizzazione.    |

Oltre a queste linee guida, Microsoft consiglia agli utenti di eseguire le azioni descritte in questo articolo: [proteggere l'account e i dispositivi da hacker e malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Queste azioni includono:
- Utilizzo di password complesse
- Protezione di dispositivi 
- Abilitazione delle funzionalità di sicurezza nei PC Windows 10 e Mac (per i dispositivi non gestiti)
    
Microsoft consiglia inoltre agli utenti di proteggere gli account di posta elettronica personali adottando le azioni consigliate negli articoli seguenti:
- [Proteggi il tuo account di posta elettronica di Outlook.com](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteggi l'account di Gmail con la verifica in due passaggi](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
