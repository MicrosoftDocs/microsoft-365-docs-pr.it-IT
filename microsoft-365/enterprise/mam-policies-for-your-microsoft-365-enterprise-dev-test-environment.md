---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367096"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

In questo articolo viene descritto come aggiungere un criterio di conformità del dispositivo Intune per i dispositivi Windows 10 e le app Microsoft 365 per Enterprise all'ambiente di testing di Microsoft 365 per Enterprise.

L'aggiunta di un criterio di conformità del dispositivo di Intune implica due fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera configurare i criteri MAM solo in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10

In questa fase, è possibile creare un criterio di conformità del dispositivo per i dispositivi Windows 10. In questa fase vengono utilizzati Microsoft Intune e l'interfaccia di [amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) per aggiungere un gruppo e creare un criterio di conformità.

1. Accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com)e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale. Selezionare l'interfaccia di amministrazione di **Endpoint Manager** . Verrà aperto l'interfaccia di [amministrazione di Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) .

    Se un messaggio simile a non è stato abilitato per la **gestione dei dispositivi** , viene visualizzato il messaggio, quindi selezionare Intune come autorità MDM. Per la procedura specifica, vedere [impostare l'autorità di gestione dei dispositivi mobili](/mem/intune/fundamentals/mdm-authority-set).

    L'interfaccia di amministrazione di Endpoint Manager si concentra sulla gestione dei dispositivi e sulla gestione delle app. Per un tour di questo interfaccia di amministrazione, vedere [tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. In **gruppi**, aggiungere un nuovo gruppo di **sicurezza** o di **Microsoft 365** denominato **utenti del dispositivo Windows 10 gestiti**, con un tipo di appartenenza **assegnato** . Nei passaggi successivi, verranno assegnati i criteri di conformità a questo gruppo. 

    Per i passaggi specifici e per informazioni su **Microsoft 365** o gruppi di **sicurezza** , vedere [aggiungere gruppi per l'organizzazione di utenti e dispositivi](/mem/intune/fundamentals/groups-add).

3. In **dispositivi**, creare un criterio di conformità di Windows 10. Assegnare questo criterio al gruppo di **utenti di dispositivi Windows 10 gestito** creato.

    Nel criterio, è possibile bloccare le password semplici, richiedere un firewall, richiedere che il servizio antimalware di Microsoft Defender sia in esecuzione e altro ancora. I criteri di conformità in genere includono le impostazioni di base o il minimo indispensabile per ogni dispositivo.

    Per i passaggi specifici e per informazioni sulle impostazioni di conformità disponibili che è possibile configurare, vedere [use Compliance Policies to set rules for Devices you manage](/mem/intune/protect/device-compliance-get-started).

Al termine, si dispone di un criterio di conformità del dispositivo per i membri di testing nel gruppo di **utenti di dispositivi Windows 10 gestito** .
  
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Microsoft 365 per le guide dei laboratori di testing Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
