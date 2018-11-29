---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida dei laboratori di testing per registrare i dispositivi nell'ambiente di test Microsoft 365 e gestirle in modalità remota.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868416"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise

Seguendo le istruzioni fornite in questo articolo, sarà possibile registrare e verificare le funzionalità di gestione di dispositivi mobili base iOS e dei dispositivi Android nell'ambiente di test Microsoft 365 aziendale.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera effettuare la registrazione iOS e dispositivi Android un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera registrare iOS e dei dispositivi Android in un'azienda simulato, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Registrare i iOS e i dispositivi Android

Innanzitutto, utilizzare le istruzioni riportate in [installare ed eseguire l'accesso all'app portale della società](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare le app portale della società Intune Microsoft per l'ambiente di testing.

Successivamente, utilizzare le istruzioni in [configurare l'accesso alle risorse della società](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.

Successivamente, utilizzare le istruzioni nella [registrazione dispositivo Android Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Gestire i iOS e dispositivi Android in remoto

Intune Microsoft sono disponibili sia blocco remoto e il passcode reimpostare funzionalità. Se si perde il dispositivo, è possibile bloccare il dispositivo in modalità remota. Se si dimentica il passcode, è possibile reimpostare in remoto.
  
Per bloccare un dispositivo Android o iOS da postazione remota:

1. Accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.
3. Fare clic su **dispositivi > tutti i dispositivi**.
4. Nell'elenco dei dispositivi, fare clic su un dispositivo Android o iOS e quindi fare clic sull'azione **Blocca remoto** .

    
Per reimpostare il passcode in remoto:

1. Se necessario, accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.
3. Fare clic su **dispositivi > tutti i dispositivi**.
4. Dall'elenco dei dispositivi di gestione, fare clic su un dispositivo Android o iOS e scegliere **... Ulteriori**. Scegliere quindi l'azione remoto dispositivo **rimuovere passcode** .

Per la sperimentazione aggiuntiva, vedere [azioni disponibili dispositivi](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Passaggio successivo

Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Criteri MAM per l'ambiente di testing di Microsoft 365 Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Sicurezza (EMS) + mobilità aziendale](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
