---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Usare questa guida al laboratorio di testing per abilitare ulteriori impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051271"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

Con le istruzioni contenute in questo articolo, configurare ulteriori impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per le aziende.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](../downloads/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera solo configurare una maggiore sicurezza di Microsoft 365 in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare una maggiore sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il testing di una maggiore sicurezza di Microsoft 365 non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurare una maggiore sicurezza di Microsoft 365

In questa fase, si abilita una maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende. Per ulteriori dettagli e impostazioni, vedere [Configure your tenant for increased security.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna

Alle app che non supportano l'autenticazione moderna non possono essere applicate configurazioni di identità e accesso ai dispositivi, che è un elemento importante per proteggere l'abbonamento a Microsoft 365 e le relative risorse digitali. [](../security/defender-365-security/microsoft-365-policies-configurations.md) 

1. Accedere all'interfaccia di amministrazione di Microsoft 365 ( ) e accedere all'abbonamento al laboratorio di testing di [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 con l'account di amministratore globale.
    
  - Se si utilizza l'ambiente di testing leggero di Microsoft 365, accedere dal computer locale.
    
  - Se si usa l'ambiente di testing di Microsoft 365 aziendale simulato, usare il portale di [Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi accedere da CLIENT1.
 
2. Nella nuova scheda interfaccia di amministrazione di **Microsoft 365,** in **Interfaccia di** amministrazione nel riquadro di spostamento sinistro fare clic su **SharePoint.**
3. Nella nuova scheda **interfaccia di amministrazione di SharePoint** fare clic su Criteri > controllo di **accesso**.
4. Fare **clic su App che non supportano l'autenticazione moderna,** selezionare Blocca **accesso** e quindi fare clic su **Salva.**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Abilitare Defender per Office 365 per SharePoint, OneDrive for Business e Microsoft Teams

Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.

1. Passare al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account di amministratore globale.

2. Nel riquadro di spostamento sinistro, in **Gestione delle minacce,** fare clic **su Criteri** e quindi su **Allegati sicuri.** 

3. In **Proteggi file in SharePoint, OneDrive e Microsoft Teams**. selezionare **Attiva ATP per SharePoint, OneDrive e Microsoft Teams.**

4. Fare clic su **Salva**.


### <a name="enable-anti-malware"></a>Abilitare l'antimalware

Il malware è composto da virus e spyware. I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare. Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware. 

Microsoft 365 include funzionalità di filtro antimalware e posta indesiderata integrate che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggerti dalla posta indesiderata. Per ulteriori informazioni, vedere [Protezione da posta indesiderata & antimalware](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).

Per garantire che l'elaborazione antimalware venga eseguita su file con tipi di file allegati comuni:

1. Fai clic sul pulsante Indietro nel browser per tornare alla **pagina** Criteri.
2. Fare **clic su Antimalware**.
3. Fare doppio clic sul criterio denominato **Default.**
4. Nella finestra **Criteri antimalware** fare clic su **Impostazioni.**
4. In **Filtro tipi di allegati comuni** selezionare **Su** e quindi fare clic su **Salva.**


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: esaminare il dashboard di sicurezza

La gestione delle minacce in Microsoft 365 consente di controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e posta indesiderata. È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti stanno effettuando lo spoofing dannoso degli account dal dominio. 

Per visualizzare il dashboard di sicurezza:

1. Se necessario, passare al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account amministratore globale.

2. Nel riquadro di spostamento sinistro, in **Gestione delle minacce,** fare clic su **Dashboard.**

Esaminare da vicino tutte le schede del dashboard per acquisire familiarità con le informazioni fornite.

Per ulteriori informazioni, vedere [Dashboard di sicurezza](../security/defender-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: esaminare Microsoft Secure Score

Microsoft Secure Score mostra la posizione di sicurezza come un numero, che indica il livello corrente rispetto alle funzionalità disponibili nell'abbonamento. Fornisce inoltre un elenco delle azioni di miglioramento che è possibile eseguire per migliorare il punteggio.

1. Creare una nuova scheda nel browser e passare al Centro sicurezza [Microsoft 365](https://security.microsoft.com/)e quindi fare clic su **Punteggio sicuro.**
2. Nella scheda **Panoramica**  annotare il punteggio di protezione corrente e il confronto con la media globale e le sottoscrizioni con un numero simile di licenze.
3. Nella scheda **Azioni di miglioramento** leggere l'elenco delle azioni che è possibile eseguire per aumentare il punteggio.

Per ulteriori informazioni, vedere [Microsoft Secure Score.](../security/defender/microsoft-secure-score.md)

## <a name="next-steps"></a>Passaggi successivi

Esplorare ulteriori [funzionalità e funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)