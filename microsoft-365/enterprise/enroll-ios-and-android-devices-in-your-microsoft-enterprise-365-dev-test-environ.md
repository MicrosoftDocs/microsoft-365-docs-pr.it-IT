---
title: Registrare i dispositivi iOS/iPados e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367084"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

In questo articolo viene descritto come eseguire la registrazione e il testing delle funzionalità di base per la gestione dei dispositivi mobili per iOS/iPados e i dispositivi Android nell'ambiente di testing Microsoft 365 for Enterprise.

La registrazione di dispositivi iOS/iPados e Android nell'ambiente di testing comporta tre fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: registrare i dispositivi iOS/iPados e Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: gestire i dispositivi iOS/iPados e Android in remoto](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera registrare i dispositivi iOS/iPados e Android in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera registrare i dispositivi iOS/iPados e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi ed è possibile sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrare i dispositivi iOS e Android

Se si sta prendendo in considerazione una soluzione di gestione dei dispositivi mobili (MDM) per la gestione del dispositivo, è possibile utilizzare Microsoft Intune. Quando si utilizza un provider MDM, tra cui Intune, i dispositivi vengono "registrati". Quando si effettua la registrazione, ricevono le caratteristiche e le impostazioni configurate. 

In Intune, esistono alcuni modi per registrare i dispositivi iOS/iPados e Android. È possibile scegliere l'opzione di registrazione più adatta per l'organizzazione. Per ulteriori informazioni e indicazioni, vedere gli articoli seguenti:

- [Guida alla distribuzione: registrare i dispositivi iOS e iPados in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guida alla distribuzione: registrare i dispositivi Android in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Se si è pronti per l'utilizzo di Intune per la gestione dei dispositivi e si desidera una guida, è possibile che le informazioni seguenti possano essere utili:

- [Panoramica della gestione dei dispositivi](/mem/intune/fundamentals/what-is-device-management)
- [Esercitazione: procedura dettagliata di Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guida alla distribuzione: installazione o spostamento in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gestire i dispositivi iOS e Android in remoto

Microsoft Intune offre funzionalità di ripristino di codice e di blocco remoto. Se un utente perde il dispositivo, è possibile bloccare il dispositivo in remoto. Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.

- Per bloccare in remoto un dispositivo iOS/iPados o Android, vedere [Remote Lock Devices with Intune](/mem/intune/remote-actions/device-remote-lock).
- Per reimpostare in remoto il codice di accesso, vedere [reimpostare o rimuovere un codice di accesso al dispositivo in Intune](/mem/intune/remote-actions/device-passcode-reset).

Per le attività aggiuntive che è possibile eseguire in remoto, vedere [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)
  
[Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)
