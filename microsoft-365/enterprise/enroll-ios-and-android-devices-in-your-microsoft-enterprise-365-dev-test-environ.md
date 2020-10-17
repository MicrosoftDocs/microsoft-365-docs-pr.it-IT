---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione
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
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487697"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

In questo articolo viene descritto come eseguire la registrazione e il testing delle funzionalità di base per la gestione dei dispositivi mobili per iOS e Android nell'ambiente di testing Microsoft 365 for Enterprise.

La registrazione dei dispositivi iOS e Android nell'ambiente di testing comporta tre fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: registrare i dispositivi iOS e Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: gestire i dispositivi iOS e Android in remoto](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera registrare i dispositivi iOS e Android in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera registrare i dispositivi iOS e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi ed è possibile sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrare i dispositivi iOS e Android

In primo luogo, utilizzare le istruzioni riportate in [Install and Sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare l'app portale aziendale di Microsoft Intune per l'ambiente di testing.

Successivamente, seguire le istruzioni riportate in [configurare l'accesso alle risorse aziendali](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.

Successivamente, seguire le istruzioni riportate in [registrazione del dispositivo Android in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gestire i dispositivi iOS e Android in remoto

Microsoft Intune fornisce sia la funzionalità di blocco remoto sia quella di reimpostazione del passcode. Se un utente perde il dispositivo, è possibile bloccare il dispositivo in remoto. Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.
  
Per bloccare in remoto un dispositivo iOS o Android:

1. Accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Nel portale di Azure, immettere **Intune** nella casella di ricerca e quindi fare clic su **Intune**.
3. Fare clic su **dispositivi > tutti i dispositivi**.
4. Nell'elenco dei dispositivi, selezionare un dispositivo iOS o Android, quindi selezionare l'azione **Remote Lock** .
    
Per reimpostare in remoto il codice di accesso:

1. Se necessario, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.
2. Nel portale di Azure, immettere **Intune** nella casella di ricerca e quindi fare clic su **Intune**.
3. Selezionare **dispositivi**per  >  **tutti i dispositivi**.
4. Nell'elenco dei dispositivi gestiti, selezionare un dispositivo iOS o Android, selezionare **... **E quindi seleziona l'azione remota **Rimuovi** dispositivo di accesso.

Per ulteriori esperimenti, vedere [available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).
    
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)
  
[Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)
