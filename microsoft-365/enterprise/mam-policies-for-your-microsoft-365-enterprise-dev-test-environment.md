---
title: Ambiente di testing di criteri di conformità di dispositivo per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per aggiungere criteri di conformità Intune dispositivo per l'organizzazione di 365 Microsoft ambiente di testing.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868908"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente di testing di criteri di conformità di dispositivo per la propria azienda 365 Microsoft

Con le istruzioni riportate in questo articolo, aggiungere criteri di conformità dispositivo Intune all'ambiente di testing Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera configurare i criteri MAM in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Creare un criterio di conformità di dispositivo per i dispositivi Windows 10

In questa fase è creare un criterio di conformità di dispositivo per i dispositivi Windows 10.
  
1. Accedere al portale di Office in ([https://office.com](https://office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.
    
2. In una nuova scheda del browser, aprire il portale Azure al [https://portal.azure.com](https://portal.azure.com).

3. Nella scheda portal Azure nel browser, nel riquadro di spostamento fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.
    
4. Se viene visualizzato un messaggio **non è abilitata la gestione dei dispositivi ancora** su blade **Microsoft Intune** , farvi clic. Su blade **autorità di gestione dei dispositivi mobili** , fare clic su **Autorità MDM Intune**e quindi fare clic su **Scegli**. Aggiornare la scheda browser.
    
5. Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.
    
6. Su blade **gruppi a tutti i gruppi** , fare clic su **+ nuovo gruppo**.
    
7. Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gli utenti di dispositivi gestiti Windows 10** nella casella **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**. 
    
8. Chiudere il pannello **Gruppo**.
    
11. Chiudere blade **gruppi a tutti i gruppi** .
    
12. Su blade **Microsoft Intune** , nell'elenco **attività veloce** , fare clic su **Crea un criterio di conformità**.
    
13. Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.
    
14. In **nome**blade **Creare criteri** , digitare **Windows 10**. **Piattaforma**, selezionare **Windows 10 e versioni successive**, fare clic su **OK** nella blade **Windows 10 criteri di conformità** e quindi fare clic su **Crea**. Chiudere blade **Windows 10** .
    
15. Scegliere il nome del criterio **Windows 10** blade **Profili dei criteri di conformità** .
    
16. Su blade **10 Windows** , fare clic su **assegnazioni**e quindi fare clic su **Seleziona gruppi da includere**.
    
17. Su blade **Selezionare gruppi da includere** fare clic sul gruppo di **utenti di dispositivi gestiti Windows 10** e quindi fare clic su **Seleziona**.
    
18. Fare clic su **Salva**e quindi chiudere blade **Windows 10 - assegnazioni** .
    
19. Chiudere il pannello **Profili dei criteri di conformità**.
    
20. Su blade **Intune Microsoft** , fare clic su **applicazioni Client** nel riquadro di spostamento sinistro.
    
21. Su blade **Applicazioni Client** , fare clic su **App**e quindi fare clic su **Aggiungi**. 

22. In blade **Aggiungi app** , selezionare **il tipo di App**e quindi selezionare **Windows 10** in **Famiglia di prodotti di Office 365**.

23. Fare clic su **Configura Suite App**e quindi fare clic su **OK**.

24. Fare clic su **App Suite informazioni**, digitare **Office applicazioni per Windows 10** in **Nome famiglia di prodotti** **Office applicazioni per Windows 10** nel campo **Descrizione famiglia di prodotti**e quindi fare clic su **OK**.

25. Fare clic su **Impostazioni App famiglia di prodotti**, selezionare **semi-annuale** nel **canale di aggiornamento**e quindi fare clic su **OK**.

26. Su blade **Aggiungi app** , fare clic su **Aggiungi**.

È ora disponibile un criterio di conformità di dispositivo per testare le app selezionate in Criteri di conformità del dispositivo **Windows 10** e per i membri del gruppo di **utenti di dispositivi gestiti Windows 10** . 
  
## <a name="next-step"></a>Passaggio successivo

Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide dei laboratori di testing Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Sicurezza (EMS) + mobilità aziendale](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
