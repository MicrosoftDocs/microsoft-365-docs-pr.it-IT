---
title: Criteri di conformità dei dispositivi per l'ambiente Microsoft 365 per l'ambiente di testing aziendale
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
description: Usa questa guida al laboratorio di testing per aggiungere i criteri di conformità dei dispositivi intune all'ambiente Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367096"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Criteri di conformità dei dispositivi per l'ambiente Microsoft 365 per l'ambiente di testing aziendale

*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*

Questo articolo descrive come aggiungere criteri di conformità dei dispositivi Intune per Windows 10 dispositivi e Microsoft 365 Apps for enterprise all'ambiente di testing Microsoft 365 per le aziende.

L'aggiunta di un criterio di conformità dei dispositivi intune prevede due fasi:
- [Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: creare criteri di conformità dei dispositivi per Windows 10 dispositivi](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende

Se si desidera configurare i criteri MAM solo in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: creare criteri di conformità dei dispositivi per Windows 10 dispositivi

In questa fase crei un criterio di conformità dei dispositivi per Windows 10 dispositivi. Questa fase usa Microsoft Intune e [l'Microsoft Endpoint Manager di](https://go.microsoft.com/fwlink/?linkid=2109431) amministrazione per aggiungere un gruppo e creare un criterio di conformità.

1. Passare [all'Microsoft 365 di amministrazione](https://admin.microsoft.com)e accedere all'Microsoft 365 del laboratorio di testing con l'account di amministratore globale. Selezionare **l'Endpoint Manager** di amministrazione. Verrà [Endpoint Manager'interfaccia di amministrazione.](https://go.microsoft.com/fwlink/?linkid=2109431)

    Se viene visualizzato un **messaggio** simile a Non hai ancora abilitato la gestione dei dispositivi, seleziona Intune come autorità MDM. Per la procedura specifica, vedere [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).

    L Endpoint Manager'interfaccia di amministrazione è incentrata sulla gestione dei dispositivi e sulla gestione delle app. Per una panoramica di questa interfaccia di amministrazione, vedere [Esercitazione: Procedura dettagliata di Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. In **Gruppi** aggiungi un nuovo gruppo **di Microsoft 365** o di sicurezza denominato **Utenti** Windows 10 dispositivi gestiti , con un **tipo di appartenenza** Assegnato.  Nei passaggi successivi, i criteri di conformità verranno assegnati a questo gruppo. 

    Per la procedura specifica e per informazioni su **Microsoft 365** **o** gruppi di sicurezza, vedere Aggiungere gruppi per organizzare utenti [e dispositivi.](/mem/intune/fundamentals/groups-add)

3. In **Dispositivi** creare un criterio Windows 10 di conformità. Assegna questo criterio al **gruppo utenti Windows 10 dispositivo gestito** che hai creato.

    Nei criteri è possibile bloccare password semplici, richiedere un firewall, richiedere l'esecuzione del servizio Microsoft Defender Antimalware e altro ancora. Un criterio di conformità include in genere le impostazioni di base o il minimo indispensabile che ogni dispositivo deve avere.

    Per i passaggi specifici e per informazioni sulle impostazioni di conformità disponibili che è possibile configurare, vedere Usare i criteri di conformità per impostare le regole [per i dispositivi gestiti.](/mem/intune/protect/device-compliance-get-started)

Al termine, hai un criterio di conformità dei dispositivi per testare i membri nel gruppo **Utenti Windows 10 dispositivi gestiti.**
  
## <a name="next-step"></a>Passaggio successivo

Esplorare le [funzionalità e le funzionalità](m365-enterprise-test-lab-guides.md#mobile-device-management) di gestione dei dispositivi mobili aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Microsoft 365 guide ai laboratori di testing aziendali](m365-enterprise-test-lab-guides.md).
  
[Registrare dispositivi iOS e Android nell'ambiente di testing Microsoft 365 per le aziende](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
