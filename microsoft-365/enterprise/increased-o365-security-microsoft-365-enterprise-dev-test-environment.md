---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Usare questa guida del laboratorio di testing per abilitare altre impostazioni di sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 7c3300111f5999714b87a176087207a1651cdcaf
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487401"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

Con le istruzioni riportate in questo articolo, è possibile configurare altre impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per l'organizzazione.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](../downloads/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera configurare una maggiore sicurezza di Microsoft 365 in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare un aumento della sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica dell'aumento della sicurezza di Microsoft 365 non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurare un aumento della sicurezza di Microsoft 365

In questa fase, viene abilitata l'aumento della sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione. Per ulteriori informazioni e impostazioni, vedere [configurare il tenant per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna

Per le app che non supportano l'autenticazione moderna non è possibile applicare le [configurazioni di identità e accesso ai dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) , che è un elemento importante della protezione dell'abbonamento a Microsoft 365 e delle risorse digitali. 

1. Accedere all'interfaccia di amministrazione di Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e accedere alla sottoscrizione di laboratorio di testing di microsoft 365 con l'account di amministratore globale.
    
  - Se si utilizza l'ambiente di testing Microsoft 365 Lightweight, accedere dal computer locale.
    
  - Se si utilizza l'ambiente di testing Enterprise Microsoft 365 simulato, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi eseguire l'accesso da CLIENT1.
 
2. Nella nuova scheda dell'interfaccia di **amministrazione di Microsoft 365** , in interfaccia di **Amministrazione** nel riquadro di spostamento a sinistra, fare clic su **SharePoint**.
3. Nella nuova scheda dell'interfaccia di **amministrazione di SharePoint** , fare clic su **criteri > controllo di accesso**.
4. Fare clic su **app che non supportano l'autenticazione moderna**, selezionare **Blocca accesso**e quindi fare clic su **Salva**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Abilitare Advanced Threat Protection per SharePoint, OneDrive for business e Microsoft Teams

Office 365 Advanced Threat Protection (ATP) per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dall'involontaria condivisione di file dannosi.

1. Accedere al [Centro sicurezza & Compliance](https://protection.office.com) e accedere con l'account di amministratore globale.

2. Nel riquadro di spostamento a sinistra, in **gestione minacce**, fare clic su **criteri**, quindi fare clic su **allegati sicuri di ATP**. 

3. In **proteggere i file in SharePoint, OneDrive e Microsoft teams**. Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.

4. Fare clic su **Salva**.


### <a name="enable-anti-malware"></a>Abilitazione anti-malware

Il malware è composto da virus e spyware. I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare. Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware. 

Microsoft 365 dispone di funzionalità di filtro antispamming e di protezione da posta indesiderata che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata. Per ulteriori informazioni, vedere [anti-spam & anti-malware Protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Per assicurarsi che l'elaborazione antimalware sia in esecuzione su file con tipi di file allegati comuni:

1. Fare clic sul pulsante indietro nel browser per tornare alla pagina dei **criteri** .
2. Fare clic su **anti-malware**.
3. Fare doppio clic sul criterio denominato **default**.
4. Nella finestra **criteri antimalware** fare clic su **Impostazioni**.
4. In **filtro tipi di allegati comuni**selezionare **On**attivato e quindi fare clic su **Salva**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: esaminare il dashboard di sicurezza

La gestione delle minacce in Microsoft 365 può essere utile per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata. È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio. 

Per visualizzare il dashboard di sicurezza:

1. Se necessario, passare al [Centro sicurezza & Compliance](https://protection.office.com) e accedere con l'account di amministratore globale.

2. Nel riquadro di spostamento a sinistra, in **gestione minacce**, fare clic su **Dashboard**.

Esaminare tutte le schede del dashboard per acquisire familiarità con le informazioni fornite.

Per ulteriori informazioni, vedere [Dashboard della sicurezza](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: esaminare il Punteggio sicuro di Microsoft

Microsoft Secure Score Visualizza la posizione di sicurezza come numero, che indica il livello corrente rispetto alle caratteristiche disponibili nell'abbonamento. Inoltre, viene fornito un elenco delle azioni di miglioramento che è possibile eseguire per migliorare il punteggio.

1. Creare una nuova scheda nel browser e passare al [Centro sicurezza Microsoft 365](https://security.microsoft.com/), quindi fare clic su **Secure Score**.
2. Nella scheda **Panoramica**  , prendere nota del Punteggio sicuro corrente e di come viene confrontato con la media globale e con le sottoscrizioni con un numero analogo di licenze.
3. Nella scheda **azioni di miglioramento** leggere l'elenco delle azioni che è possibile eseguire per aumentare il punteggio.

Per ulteriori informazioni, vedere [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Passaggi successivi

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
