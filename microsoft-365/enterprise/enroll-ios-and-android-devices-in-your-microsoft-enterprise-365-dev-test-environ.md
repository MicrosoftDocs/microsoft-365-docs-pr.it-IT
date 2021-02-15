---
title: Registrare i dispositivi iOS/iPadOS e Android nell'ambiente di testing di Microsoft 365 per le aziende
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
description: Usare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367084"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrare i dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

Questo articolo descrive come registrare e testare le funzionalità di gestione dei dispositivi mobili di base per i dispositivi iOS/iPadOS e Android nell'ambiente di testing di Microsoft 365 per le aziende.

La registrazione dei dispositivi iOS/iPadOS e Android nell'ambiente di testing prevede tre fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: registrare i dispositivi iOS/iPadOS e Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: gestire i dispositivi iOS/iPadOS e Android in remoto](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se vuoi registrare i dispositivi iOS/iPadOS e Android in modo leggero con i requisiti minimi, segui le istruzioni in [Configurazione di base leggera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se vuoi registrare i dispositivi iOS/iPadOS e Android in un'azienda simulata, segui le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Qui viene fornito come opzione, in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrare i dispositivi iOS e Android

Se stai valutando una soluzione di gestione dei dispositivi mobili (MDM) per gestire i dispositivi, puoi usare Microsoft Intune. Quando si lavora con qualsiasi provider MDM, incluso Intune, i dispositivi vengono "registrati". Al momento della registrazione, ricevono le funzionalità e le impostazioni configurate. 

In Intune, esistono alcuni modi per registrare i dispositivi iOS/iPadOS e Android. Puoi scegliere l'opzione di registrazione più adatta alla tua organizzazione. Per ulteriori informazioni e indicazioni, vedere gli articoli seguenti:

- [Guida alla distribuzione: Registrare i dispositivi iOS e iPadOS in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guida alla distribuzione: Registrare i dispositivi Android in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Se si è pronti a usare Intune per la gestione dei dispositivi e si desiderano indicazioni, le informazioni seguenti potrebbero essere utili:

- [Panoramica della gestione dei dispositivi](/mem/intune/fundamentals/what-is-device-management)
- [Esercitazione: Procedura dettagliata di Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guida alla distribuzione: Installazione o passaggio a Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gestire i dispositivi iOS e Android in remoto

Microsoft Intune offre funzionalità di blocco remoto e reimpostazione del passcode. Se qualcuno perde il dispositivo, puoi bloccare il dispositivo in remoto. Se qualcuno dimentica il passcode, puoi reimpostarlo in remoto.

- Per bloccare in remoto un dispositivo iOS/iPadOS o Android, vedi Bloccare in remoto [i dispositivi con Intune.](/mem/intune/remote-actions/device-remote-lock)
- Per reimpostare in remoto il passcode, vedere [Reimpostare o rimuovere un passcode del dispositivo in Intune.](/mem/intune/remote-actions/device-passcode-reset)

Per altre attività che puoi eseguire in remoto, vedi [le azioni del dispositivo disponibili.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Passaggio successivo

Esplorare altre [funzionalità e funzionalità di gestione](m365-enterprise-test-lab-guides.md#mobile-device-management) dei dispositivi mobili nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)
  
[Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per le aziende](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)
