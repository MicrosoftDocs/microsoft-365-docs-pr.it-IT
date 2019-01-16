---
title: Sicurezza aumentata di Office 365 per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per abilitare ulteriori impostazioni di protezione di Office 365 l'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868546"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Sicurezza aumentata di Office 365 per l'ambiente di testing di Microsoft 365 Enterprise

Con le istruzioni riportate in questo articolo, è configurare impostazioni aggiuntive di Office 365 per aumentare la protezione dell'ambiente di test Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera configurare aumentare la protezione di Office 365 in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare aumentare la protezione di Office 365 in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test aumentare la protezione di Office 365 non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 


## <a name="phase-2-configure-increased-office-365-security"></a>Fase 2: Configurare aumentare la protezione di Office 365

In questa fase si abilita aumentare la protezione di Office 365 per l'ambiente di test Microsoft 365 Enterprise. Per ulteriori informazioni e le impostazioni, vedere [Configure Office 365 tenant per aumentare la protezione](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurare SharePoint Online per bloccare le applicazioni che non supportano l'autenticazione moderno

Applicazioni che non supportano l'autenticazione moderno non possono avere [identità e il dispositivo accedere configurazioni](microsoft-365-policies-configurations.md) applicato alle stesse, ovvero un importante elemento di protezione dell'abbonamento Microsoft 365 e le risorse digitali. 

1. Accedere al portale di Office ([https://office.com](https://office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.
    
  - Se si utilizza l'ambiente di testing Microsoft 365 semplificata, l'accesso dal computer locale.
    
  - Se si utilizza l'ambiente di testing simulato aziendale Microsoft 365, utilizzare il [portale Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi effettuare l'accesso da CLIENT1.
 
2. Dalla scheda di **interfaccia di amministrazione di Microsoft 365** , fare clic su **amministratore**.
3. Nella nuova scheda di **interfaccia di amministrazione di Microsoft 365** , fare clic su **Admin Center > SharePoint**.
4. Nella nuova scheda di **interfaccia di amministrazione di SharePoint** , fare clic su **controllo di accesso**.
5. In **applicazioni che non supportano l'autenticazione moderno**, fare clic su **blocco**e fare clic su **OK**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Abilita avanzate di protezione da minacce) per SharePoint, OneDrive for Business e team di Microsoft

Office 365 avanzate Threat Protection (degli strumenti di analisi) è una funzionalità di Exchange Online Protection (EOP) che consente di mantenere malware fuori la posta elettronica. Con degli strumenti di analisi, creare i criteri nell'interfaccia di amministrazione di Exchange (EAC) o la protezione e accedere a centro conformità per garantire che gli utenti solo collegamenti o allegati nei messaggi di posta elettronica che vengono identificati come non dannoso. Per ulteriori informazioni, vedere [protezione rischio avanzata per gli allegati sicuri e collegamenti sicuri](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).

1. Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.
2. Nella scheda **sicurezza e conformità** nuova, fare clic su **gestione delle minacce > criteri**.
3. Fare clic su **allegati sicuri degli strumenti di analisi**.
4. Nel riquadro **allegati sicuri** selezionare **attiva degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**e quindi fare clic su **Salva**.

### <a name="enable-anti-malware"></a>Abilitare anti-malware

Malware è costituito da virus e spyware. Virus infettare altri programmi e i dati e vengono distribuiti in tutto il computer per programmi infetti. Spyware fa riferimento a malware che raccoglie informazioni personali, ad esempio informazioni di accesso e i dati personali e lo invia all'autore di malware. 

Office 365 dispone di funzionalità di migliorare la protezione dei messaggi in ingresso e in uscita da malware e garantire la protezione da posta indesiderata di filtraggio della posta indesiderata e antimalware incorporata. Per ulteriori informazioni, vedere [protezione antispam e antimalware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Per verificare che l'elaborazione anti-malware viene eseguita nel file con tipi di file allegato comuni:

1. Fare clic sul pulsante Indietro nel browser per tornare alla pagina del **criterio** .
2. Fare clic su **protezione Anti-malware**.
3. Fare doppio clic sul criterio denominato **Default**.
4. Nella finestra **criteri Anti-malware** , fare clic su **Impostazioni**.
4. Nella sezione **filtro comuni tipi di allegati**, fare clic su **in > Salva**.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>Fase 3: Esaminare i registri e gli strumenti di protezione di Office 365

In questa fase è esaminare servizi incorporati informano gli eventi di protezione e misurano le generali di sicurezza.

### <a name="threat-management-dashboard"></a>Dashboard di gestione dei rischi

Gestione di Office 365 rischio consentono di definire e gestire l'accesso dei dispositivi mobili per i dati dell'organizzazione, proteggere l'organizzazione da perdita di dati e migliorare la protezione dei messaggi in ingresso e in uscita da posta indesiderata e malware. È inoltre possibile utilizzare threat management per la protezione di reputazione del dominio e per determinare se i mittenti sono da utenti malintenzionati lo spoofing degli account di dominio. Per ulteriori informazioni, vedere [gestione delle minacce nel centro di conformità e sicurezza di Office 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

Utilizzare la procedura seguente per visualizzare il dashboard di Office 365 Threat management:

1. Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.
2. Nella scheda **sicurezza e conformità** nuova, fare clic su **gestione delle minacce > Dashboard**.
3. Nella scheda nuova **Dashboard** nel browser, nota tendenze malware, sui concetti e altre sezioni del dashboard.

### <a name="office-365-cloud-app-security-dashboard"></a>Dashboard di sicurezza App Cloud di Office 365

Protezione di Office 365 Cloud App, in precedenza noto come Office 365 Advanced Security Management, consente di creare i criteri che per monitorare e informano l'utente delle attività potenzialmente dannoso nella sottoscrizione a Office 365, in modo da poter analizzare e richiedere possibili azione di risoluzione dei problemi. Per ulteriori informazioni, vedere [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

1. Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.
2. Nella scheda **sicurezza e conformità** nuova, fare clic su **avvisi > Gestisci avvisi avanzate > passare a Office 365 Cloud App sicurezza**.
3. Nella scheda **Sicurezza App Cloud** nuovo, tenere presente la visualizzazione di dashboard e l'elenco dei criteri predefiniti che monitorare per varie attività nella sottoscrizione a Office 365.
4. Fare clic sull'icona del dashboard per visualizzare un riepilogo delle attività di sicurezza di applicazione Cloud che si desidera tenere traccia.
5. Fare clic su **indagare** (l'icona a forma di lente) e quindi **registro attività** per visualizzare l'elenco di recente gli accessi e altre attività.

### <a name="secure-score"></a>Punteggio protetto

1. Creare una nuova scheda nel browser e passare a **securescore.office.com**.
2. Nella **scheda del Dashboard**, si noti il punteggio sicura corrente e l'elenco delle operazioni nella coda per incrementare il punteggio.

Nella fase di **protezione delle informazioni** per informazioni e collegamenti per configurare queste impostazioni nell'ambiente di produzione, vedere la sezione [configurare maggiore sicurezza per Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) .

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

