---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per abilitare altre impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: d51f9ada68969823eadbb4fad55392358a6ddee8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072136"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise

Con le istruzioni riportate in questo articolo, è possibile configurare altre impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera configurare una maggiore sicurezza di Microsoft 365 in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare un aumento della sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica dell'aumento della sicurezza di Microsoft 365 non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurare un aumento della sicurezza di Microsoft 365

In questa fase, viene abilitata la sicurezza aumentata di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise. Per ulteriori informazioni e impostazioni, vedere [configurare il tenant di Office 365 per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna

Per le app che non supportano l'autenticazione moderna non è possibile applicare le [configurazioni di identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) , che è un elemento importante della protezione dell'abbonamento a Microsoft 365 e delle risorse digitali. 

1. Accedere all'interfaccia di amministrazione di Microsoft 365[https://portal.microsoft.com](https://portal.microsoft.com)() e accedere alla sottoscrizione di laboratorio di testing di Office 365 con l'account di amministratore globale.
    
  - Se si utilizza l'ambiente di testing Microsoft 365 Lightweight, accedere dal computer locale.
    
  - Se si utilizza l'ambiente di testing Enterprise Microsoft 365 simulato, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi eseguire l'accesso da CLIENT1.
 
2. Nella nuova scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su interfaccia di **amministrazione di > SharePoint**.
3. Nella nuova scheda dell'interfaccia di **amministrazione di SharePoint** , fare clic su **controllo di accesso**.
4. In **app che non supportano l'autenticazione moderna**fare clic su **blocca**e quindi su **OK**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Abilitare Advanced Threat Protection per SharePoint, OneDrive for business e Microsoft Teams

Office 365 Advanced Threat Protection (ATP) per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dall'involontaria condivisione di file dannosi.

1. Accedere al [Centro sicurezza e conformità di Office 365 &](https://protection.office.com) e accedere con l'account di amministratore globale.

2. Nel riquadro di spostamento a sinistra, in **gestione delle minacce**, scegliere **criteri > allegati sicuri**. 

3. Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.

4. Fare clic su **Salva**.


### <a name="enable-anti-malware"></a>Abilitazione anti-malware

Il malware è composto da virus e spyware. I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare. Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware. 

Office 365 dispone di funzionalità di filtro antispamming e di protezione da posta indesiderata che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata. Per ulteriori informazioni, vedere [protezione antimalware di _AMP_ anti-spam in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Per assicurarsi che l'elaborazione antimalware sia in esecuzione su file con tipi di file allegati comuni:

1. Fare clic sul pulsante indietro nel browser per tornare alla pagina dei **criteri** .
2. Fare clic su **anti-malware**.
3. Fare doppio clic sul criterio denominato **default**.
4. Nella finestra **criteri antimalware** fare clic su **Impostazioni**.
4. In **filtro tipi di allegati comuni**, fare clic **su > Save**.


## <a name="phase-3-examine-the-threat-management-dashboard"></a>Fase 3: esaminare il dashboard di gestione delle minacce

La gestione delle minacce di Office 365 può essere utile per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata. È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio. Per ulteriori informazioni, vedere [gestione delle minacce nel centro sicurezza Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Passaggi successivi

Per informazioni e collegamenti per configurare queste impostazioni in produzione, vedere il passaggio [configurazione maggiore sicurezza per Microsoft 365](infoprotect-configure-increased-security-office-365.md) nella fase di **protezione delle informazioni** .

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

