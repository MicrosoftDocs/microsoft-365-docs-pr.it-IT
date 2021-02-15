---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per le aziende
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Usare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi Intune all'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367096"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

Questo articolo descrive come aggiungere un criterio di conformità dei dispositivi Intune per i dispositivi Windows 10 e Microsoft 365 Apps for enterprise all'ambiente di testing di Microsoft 365 per le aziende.

L'aggiunta di un criterio di conformità dei dispositivi intune prevede due fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: creare criteri di conformità dei dispositivi per i dispositivi Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera configurare i criteri MAM solo in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Qui viene fornito come opzione, in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: creare criteri di conformità dei dispositivi per i dispositivi Windows 10

In questa fase, crei un criterio di conformità dei dispositivi per i dispositivi Windows 10. Questa fase usa Microsoft Intune e l'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) per aggiungere un gruppo e creare un criterio di conformità.

1. Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale. Selezionare **l'interfaccia di amministrazione di Endpoint Manager.** Verrà [visualizzata l'interfaccia di amministrazione di Endpoint](https://go.microsoft.com/fwlink/?linkid=2109431) Manager.

    Se viene visualizzato un messaggio simile a **You haven't enabled device management yet,** seleziona Intune come autorità MDM. Per la procedura specifica, vedere [Impostare l'autorità di gestione dei dispositivi mobili.](/mem/intune/fundamentals/mdm-authority-set)

    L'interfaccia di amministrazione di Endpoint Manager è incentrata sulla gestione dei dispositivi e sulle app. Per una presentazione di questa interfaccia di amministrazione, vedere [Esercitazione: Procedura dettagliata di Intune in Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. In **Gruppi,** aggiungere un nuovo gruppo  **di Microsoft 365** o sicurezza denominato Utenti di dispositivi Windows **10** gestiti, con un **tipo di appartenenza** assegnato. Nei passaggi successivi, i criteri di conformità verranno assegnati a questo gruppo. 

    Per la procedura specifica e per informazioni su  **Microsoft 365** o sui gruppi di sicurezza, vedere Aggiungere gruppi per organizzare [utenti e dispositivi.](/mem/intune/fundamentals/groups-add)

3. In **Dispositivi** crea un criterio di conformità di Windows 10. Assegna questo criterio al gruppo di utenti del **dispositivo Windows 10** gestito che hai creato.

    Nei criteri, è possibile bloccare password semplici, richiedere un firewall, richiedere l'esecuzione del servizio Microsoft Defender Antimalware e altro ancora. Un criterio di conformità include in genere le impostazioni di base o il minimo indispensabile per ogni dispositivo.

    Per i passaggi specifici e per informazioni sulle impostazioni di conformità disponibili che è possibile configurare, vedere Usare i criteri di conformità per impostare le regole [per i dispositivi gestiti.](/mem/intune/protect/device-compliance-get-started)

Al termine, hai un criterio di conformità dei dispositivi per testare i membri nel gruppo utenti di dispositivi **Windows 10** gestiti.
  
## <a name="next-step"></a>Passaggio successivo

Esplorare altre [funzionalità e funzionalità di gestione](m365-enterprise-test-lab-guides.md#mobile-device-management) dei dispositivi mobili nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

Guide dei laboratori di testing di [Microsoft 365 per le aziende.](m365-enterprise-test-lab-guides.md)
  
[Registrare i dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per le aziende](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
