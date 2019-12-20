---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 8a746f99e16444527c44267eddbaec9f5e5156eb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801631"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise

*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*

Con le istruzioni riportate in questo articolo, è possibile aggiungere un criterio di conformità del dispositivo Intune per i dispositivi Windows 10 e Office 365 ProPlus all'ambiente di testing di Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera solo configurare i criteri MAM in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10

In questa fase, è possibile creare un criterio di conformità del dispositivo per i dispositivi Windows 10.
  
1. Accedere al portale di Office 365 all'indirizzo[https://portal.office.com](https://portal.office.com)() e accedere alla sottoscrizione di laboratorio di testing di Office 365 con l'account di amministratore globale.
    
2. In una nuova scheda del browser, aprire il portale di Azure all' [https://portal.azure.com](https://portal.azure.com)indirizzo.

3. Dalla scheda portale di Azure nel browser, digitare **Intune** nella casella di ricerca e quindi fare clic su **Intune**.
    
4. Se viene visualizzato un messaggio **che non è ancora stato abilitato** per la gestione dei dispositivi nel riquadro di **Microsoft Intune** , fare clic su di esso. Nel riquadro **autorità di gestione dei dispositivi mobili** , fare clic su **autorità MDM di Intune**, quindi fare clic su **Scegli**. Aggiornare la scheda del browser.
    
5. Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.
    
6. Nel riquadro **gruppi-tutti i gruppi** fare clic su **+ nuovo gruppo**.
    
7. Nel riquadro **gruppo** , selezionare **Office 365** o **sicurezza** per il **tipo di gruppo**, digitare **utenti dei dispositivi Windows 10 gestiti** in **nome**, selezionare **assegnato** in **tipo di appartenenza**e quindi fare clic su **Crea**. 
    
8. Fare clic su **Microsoft Intune**. Nell'elenco **attività rapide** del riquadro di **Microsoft Intune** fare clic su **Crea un criterio di conformità**.
    
9. Nel riquadro **profili criteri di conformità** fare clic su **Crea criterio**.
    
10. Nel riquadro **Crea criterio** , in **nome**, digitare **Windows 10**. In **piattaforma**selezionare **Windows 10 e versioni successive**, fare clic su **OK** nel riquadro **criteri di conformità di Windows 10** e quindi fare clic su **Crea**. 
    
11. Fare clic su **profili criteri di conformità**e quindi fare clic sul nome del criterio di **Windows 10** .
    
12. Nel riquadro di **Windows 10** , fare clic su **assegnazioni**, quindi fare clic su **Seleziona gruppi da includere**.
    
13. Nel riquadro **Seleziona gruppi da includere** fare clic sul gruppo **utenti di dispositivi di Windows 10 gestiti** e quindi fare clic su **Seleziona**.
    
14. Fare clic su **Salva**, fare clic su **Microsoft Intune-Panoramica**, quindi fare clic su **app client** nella barra di spostamento a sinistra.
    
15. Nel riquadro **app client** fare clic su **app**e quindi su **Aggiungi**. 

16. Nel riquadro **Aggiungi app** selezionare tipo di **app**e quindi selezionare **Windows 10** in **Office 365 Suite**.

17. Nel riquadro **Aggiungi app** , seleziona **informazioni sulla famiglia di applicazioni**.
 
18. Nel riquadro **delle informazioni della famiglia di applicazioni** , digitare **Office 365 ProPlus** sia in **nome famiglia** che in **Descrizione famiglia**.
Fare clic su OK.

19. Nel riquadro **Aggiungi app** , selezionare **Configure app Suite**, quindi fare clic su **OK**.

20. Nel riquadro **Aggiungi app** selezionare impostazioni della **famiglia di applicazioni**.

21. Per il **canale di aggiornamento**, selezionare **semestrale**e quindi fare clic su **OK**.

22. Nel riquadro **Aggiungi applicazione** fare clic su **Aggiungi**.

Ora si dispone di un criterio di conformità del dispositivo per testare le app selezionate nei criteri di conformità dei dispositivi **Windows 10** e per i membri del gruppo di **utenti del dispositivo Windows 10 gestito** . Tenere presente che selezionando Office 365 come tipo di gruppo verranno create risorse aggiuntive. 
  
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide del laboratorio di testing di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
