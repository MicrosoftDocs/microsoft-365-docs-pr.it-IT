---
title: Criteri MAM per l'ambiente di testing di Microsoft 365 Enterprise
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
description: Utilizzare questa guida dei laboratori di testing per aggiungere criteri di gestione (MAM) Intune applicazione per dispositivi mobili per l'organizzazione di 365 Microsoft ambiente di testing.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868908"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Criteri MAM per l'ambiente di testing di Microsoft 365 Enterprise

Con le istruzioni riportate in questo articolo, aggiungere criteri di gestione (MAM) Intune applicazione per dispositivi mobili per l'organizzazione di 365 Microsoft ambiente di testing.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera configurare i criteri MAM in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>Fase 2: creare e distribuire criteri MAM per i dispositivi iOS e Android

In questa fase, è possibile creare e distribuire due diversi criteri MAM: uno per i dispositivi iOS e uno per i dispositivi Android.
  
1. Accedere al portale di Office 365 in ([https://portal.office.com](https://portal.office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.
    
2. In una nuova scheda del browser, aprire il portale Azure al [https://portal.azure.com](https://portal.azure.com).

3. Nella scheda Azure portale in Internet Explorer, nel riquadro di spostamento fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.
    
4. Se viene visualizzato un messaggio **non è abilitata la gestione dei dispositivi ancora** su blade **Microsoft Intune** , farvi clic. Su blade **autorità di gestione dei dispositivi mobili** , fare clic su **Autorità MDM Intune**e quindi fare clic su **Scegli**. Aggiornare la scheda browser.
    
5. Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.
    
6. Su blade **gruppi a tutti i gruppi** , fare clic su **+ nuovo gruppo**.
    
7. Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gestiti gli utenti di dispositivi iOS** nella casella **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**. 
    
8. Chiudere il pannello **Gruppo**.
    
9. Su blade **gruppi a tutti i gruppi** , fare clic su **Aggiungi**.
    
10. Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gestiti Android utente dispositivo** in **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**.
    
11. Chiudere blade **gruppi a tutti i gruppi** .
    
12. Nel pannello **Intune**, nell'elenco **Attività rapide** fare clic su **Crea nuovi criteri di conformità**.
    
13. Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.
    
14. Nel pannello **Crea criterio**, in **Nome** digitare **iOS**. In **Piattaforma**, selezionare **iOS**, fare clic su **OK** nel pannello **Criteri di conformità di iOS**, quindi fare clic su **Crea**.
    
15. Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.
    
16. Nel pannello **Crea criterio**, in **Nome** digitare **Android**. In **Piattaforma**, selezionare **Android**, fare clic su **OK** nel pannello **Criteri di conformità di Android**, quindi fare clic su **Crea**.
    
17. Nel pannello **Profili dei criteri di conformità**, fare clic sul nome del criterio **Android**.
    
18. Nella barra di spostamento a sinistra del pannello **Android - Proprietà**, fare clic su **Assegnazioni**, quindi su **Seleziona gruppi**.
    
19. Nel pannello **Seleziona gruppi**, fare clic sul gruppo **Utenti dei dispositivi Android gestiti**, quindi fare clic su **Seleziona**.
    
20. Fare clic su **Salva**e quindi chiudere blade **Android - assegnazioni** .
    
21. Nel pannello **Profili dei criteri di conformità**, fare clic sul nome del criterio **iOS**.
    
22. Nella barra di spostamento a sinistra del pannello **iOS - Proprietà**, fare clic su **Assegnazioni**, quindi su **Seleziona gruppi**.
    
23. Nel pannello **Seleziona gruppi**, fare clic sul gruppo **Utenti dei dispositivi iOS gestiti**, quindi fare clic su **Seleziona**.
    
24. Fare clic su **Salva**e quindi chiudere blade **iOS - assegnazioni** .
    
25. Chiudere il pannello **Profili dei criteri di conformità**.
    
26. Nel pannello **Intune**, fare clic su **Gestisci app** nella barra di spostamento a sinistra.
    
27. Nel pannello **App mobili**, fare clic su **App**.
    
28. Nell'elenco delle app, fare clic su **PowerPoint**,  
    
29. Nel pannello **Panoramica di PowerPoint**, fare clic su **Assegnazioni > Seleziona gruppi > Dispositivi iOS gestiti > Seleziona**. In **Tipo**, selezionare **Disponibile**, quindi fare clic su **Salva**.
    
30. Ripetere il passaggio 29 per le applicazioni seguenti:
    
    - Outlook per Android
    
    - Word per iOS
    
    - Excel per iOS
    
    - Outlook per iOS
    
    - Microsoft Dynamics CRM su iPad per iOS
    
    - Microsoft Dynamics CRM su iPhone per iOS
    
    - Dynamics CRM per telefoni per Android
    
    - Dynamics CRM per tablet per Android
    
    - Excel per Android
    
    - Word per Android
    
    - OneNote per iOS
    
31. Chiudere il pannello **App mobili - App**.
    
32. Nel pannello **App mobili**, fare clic su **Criteri di protezione delle app**.
    
33. Nel pannello **Criteri di protezione delle app**, fare clic su **Aggiungi un criterio**.
    
34. Nel pannello **Aggiungi un criterio**, digitare **iOS**, quindi fare clic su **Selezionare le app richieste**.
    
35. Nel pannello **App**, fare clic su **PowerPoint**, **Microsoft Dynamics CRM su iPhone**, **Excel**, **Microsoft Dynamics CRM su iPhone**, **Word**, **OneNote** e **Outlook**, quindi fare clic su **Seleziona**.
    
36. Nel pannello **Aggiungi un criterio**, fare clic su **Crea**.
    
37. Nel pannello **Criteri di protezione delle app**, fare clic su **Aggiungi un criterio**.
    
38. Nel pannello **Aggiungi un criterio**, digitare **Android**, selezionare **Android** in **Piattaforma**, quindi fare clic su **Selezionare le app richieste**.
    
39. Nel pannello **App**, fare clic su **PowerPoint**, **Dynamics CRM per tablet**, **Excel**, **Word**, **Outlook** e **Dynamics CRM per cellulari**, quindi fare clic su **Seleziona**.
    
40. Nel pannello **Aggiungi un criterio**, fare clic su **Crea**.
    
Ora si dispone di due criteri MAM, uno per i dispositivi iOS e uno per i dispositivi Android, e sono pronti per essere utilizzati con le impostazioni di testing per le app selezionate. 
  
## <a name="next-step"></a>Passaggio successivo

Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide dei laboratori di testing Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Sicurezza (EMS) + mobilità aziendale](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
