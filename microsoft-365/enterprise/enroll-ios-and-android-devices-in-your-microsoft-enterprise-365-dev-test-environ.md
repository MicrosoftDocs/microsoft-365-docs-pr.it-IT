---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 0dde7acd10ad78327adb4862346639e05a276b4e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981997"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise

Seguendo le istruzioni riportate in questo articolo, sarà possibile registrare e testare le funzionalità di base per la gestione dei dispositivi mobili per iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera registrare i dispositivi iOS e Android in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera registrare i dispositivi iOS e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrare i dispositivi iOS e Android

In primo luogo, utilizzare le istruzioni riportate in [Install and Sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare l'app portale aziendale di Microsoft Intune per l'ambiente di testing.

Successivamente, seguire le istruzioni riportate in [configurare l'accesso alle risorse aziendali](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.

Successivamente, seguire le istruzioni riportate in [registrazione del dispositivo Android in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gestire i dispositivi iOS e Android in remoto

Microsoft Intune fornisce sia la funzionalità di blocco remoto sia quella di reimpostazione del passcode. Se un utente perde il proprio dispositivo, è possibile bloccare il dispositivo in modalità remota. Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.
  
Per bloccare un dispositivo iOS o Android in remoto:

1. Accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Fare clic su **tutti i servizi**, digitare **Intune**, quindi fare clic su **Intune**.
3. Fare clic su **dispositivi > tutti i dispositivi**.
4. Nell'elenco dei dispositivi, fare clic su un dispositivo iOS o Android, quindi fare clic sull'azione **blocco remoto** .

    
Per reimpostare il passcode in remoto:

1. Se necessario, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Fare clic su **tutti i servizi**, digitare **Intune**, quindi fare clic su **Intune**.
3. Fare clic su **dispositivi > tutti i dispositivi**.
4. Dall'elenco dei dispositivi gestiti, fare clic su un dispositivo iOS o Android e scegliere **... Altre informazioni**. Scegliere **quindi l'azione** remota del dispositivo di accesso remoto.

Per ulteriori esperimenti, vedere [available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

