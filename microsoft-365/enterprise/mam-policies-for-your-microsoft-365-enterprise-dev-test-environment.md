---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487413"
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

In questa fase, creare un criterio di conformità del dispositivo per i dispositivi Windows 10.
  
1. Accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale.
1. In una nuova scheda del browser, aprire il portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .
1. Nella casella di ricerca del portale di Azure, immettere **Intune**e quindi fare clic su **Intune**.
1. Se viene visualizzato un messaggio **che non è ancora stato abilitato** per la gestione dei dispositivi nel riquadro di **Microsoft Intune** , selezionarlo. Nel riquadro **autorità di gestione dei dispositivi mobili** selezionare **autorità**di amministrazione di Intune, quindi **scegliere Scegli**.
1. Aggiornare la scheda del browser.
1. Nel riquadro di spostamento a sinistra, selezionare **gruppi**.
1. Nel riquadro **gruppi-tutti i gruppi** selezionare **+ nuovo gruppo**.
1. Nel riquadro **gruppo** selezionare **Microsoft 365** o **sicurezza** per tipo di **gruppo**, immettere **gli utenti del dispositivo Windows 10 gestiti** in **nome**, selezionare **assegnato** in **tipo di appartenenza**e quindi selezionare **Crea**.
1. Selezionare **Microsoft Intune**.
1. Nell'elenco **attività rapide** del riquadro di **Microsoft Intune** selezionare **Crea un criterio di conformità**.
1. Nel riquadro **profili criteri di conformità** , selezionare **Crea criterio**.
1. Nel riquadro **Crea criterio** , in **nome**, immettere **Windows 10**. In **piattaforma**selezionare **Windows 10 e versioni successive**, fare clic su **OK** nel riquadro **criteri di conformità di Windows 10** e quindi selezionare **Crea**.
1. Selezionare **profili dei criteri di conformità**e quindi selezionare il nome del criterio di **Windows 10** .
1. Nel riquadro di **Windows 10** , selezionare **assegnazioni**, quindi selezionare **gruppi da includere**.
1. Nel riquadro **Seleziona gruppi da includere** selezionare il gruppo di **utenti del dispositivo Windows 10 gestito** e quindi selezionare **Seleziona**.
1. Selezionare **Salva**, selezionare **Microsoft Intune-Panoramica**, quindi selezionare **app client** nella barra di spostamento a sinistra.
1. Nel riquadro **app client** , selezionare **app**, quindi fare clic su **Aggiungi**.
1. Nel riquadro **Aggiungi app** selezionare tipo di **app**e quindi selezionare **Windows 10** in **Microsoft 365 Suite**.
1. Nel riquadro **Aggiungi app** , seleziona **informazioni sulla famiglia di applicazioni**.
1. Nel riquadro **delle informazioni della famiglia** di applicazioni, immettere **Microsoft 365 Apps for Enterprise** sia in **Suite Name** che nella **Descrizione della famiglia**, quindi selezionare **OK**.
1. Nel riquadro **Aggiungi applicazione** , selezionare **Configura app Suite**, quindi fare clic su **OK**.
1. Nel riquadro **Aggiungi app** selezionare impostazioni della **famiglia di applicazioni**.
1. Per il **canale di aggiornamento**, selezionare **organizzazione semestrale**e quindi fare clic su **OK**.
1. Nel riquadro **Aggiungi applicazione** selezionare **Aggiungi**.

Ora si dispone di un criterio di conformità del dispositivo per testare le app selezionate nei criteri di conformità dei dispositivi **Windows 10** e per i membri del gruppo di **utenti del dispositivo Windows 10 gestito** . Tenere presente che se si seleziona **Microsoft 365** come tipo di gruppo, vengono create altre risorse.
  
## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Microsoft 365 per le guide dei laboratori di testing Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
