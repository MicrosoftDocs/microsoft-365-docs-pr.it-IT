---
title: Panoramica della sicurezza e della mobilità di base per Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Utilizzare la sicurezza e la mobilità di base per impostare i criteri di sicurezza del dispositivo e le regole di accesso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430201"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Panoramica della sicurezza e della mobilità di base per Microsoft 365

È possibile gestire e proteggere i dispositivi mobili quando sono connessi all'organizzazione Microsoft 365 utilizzando la sicurezza e la mobilità di base. I dispositivi mobili, come smartphone e tablet, utilizzati per accedere alla posta elettronica di lavoro, al calendario, ai contatti e ai documenti, giocano un ruolo molto importante nell'assicurare ai dipendenti lo svolgimento del loro lavoro ovunque e in qualsiasi momento. Pertanto, è importante contribuire alla protezione delle informazioni dell'organizzazione quando gli utenti utilizzano i dispositivi. È possibile utilizzare la sicurezza e la mobilità di base per impostare i criteri di sicurezza del dispositivo e le regole di accesso e per cancellare i dispositivi mobili se sono stati persi o rubati.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configurazione di base per dispositivi mobili e sicurezza":::

## <a name="what-types-of-devices-can-you-manage"></a>Quali tipi di dispositivi è possibile gestire?

È possibile utilizzare la sicurezza e la mobilità di base per gestire numerosi tipi di dispositivi mobili, come Windows Phone, Android, iPhone e iPad. Per gestire i dispositivi mobili utilizzati dagli utenti dell'organizzazione, ogni persona deve disporre di una licenza di Microsoft 365 applicabile e il dispositivo deve essere registrato in mobilità e sicurezza di base.

Per sapere cosa supporta la sicurezza e la mobilità di base per ogni tipo di dispositivo, vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Procedure di installazione per la sicurezza e la mobilità di base

Per attivare e configurare la sicurezza e la mobilità di base, è necessario che un amministratore globale di Microsoft 365 completi i passaggi seguenti. Per la procedura dettagliata, seguire le istruzioni riportate in [configurare la sicurezza e la mobilità di base](set-up.md). 

Di seguito è riportata una sintesi dei passaggi:

**Passaggio 1:** Attivare la sicurezza e la mobilità di base attenendosi alla procedura descritta in [set up Basic Mobility and Security](set-up.md).

**Passaggio 2:** Configurare la sicurezza e la mobilità di base, ad esempio creando un certificato APNs per gestire i dispositivi iOS e aggiungendo un record DNS (Domain Name System) per il dominio per il supporto dei telefoni Windows.

**Passaggio 3:** Creare i criteri per i dispositivi e applicarli ai gruppi di utenti. Quando si esegue questa operazione, gli utenti ricevono un messaggio di registrazione nel dispositivo e, al termine della registrazione, i dispositivi sono limitati dai criteri che sono stati configurati. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base per i criteri di sicurezza e dispositivi mobili":::

## <a name="device-management-tasks"></a>Attività di gestione dei dispositivi

Dopo aver impostato la sicurezza e la mobilità di base e gli utenti hanno registrato i propri dispositivi, è possibile gestire i dispositivi, bloccare l'accesso o cancellare un dispositivo, se necessario. Per ulteriori informazioni su alcune attività comuni di gestione dei dispositivi, tra cui il completamento delle attività, vedere [gestire i dispositivi registrati nella gestione dei dispositivi mobili per Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Altre modalità di gestione di dispositivi e app

Se è necessaria solo la gestione delle app per dispositivi mobili, forse per gli utenti che aggiornano i progetti di lavoro sui propri sistemi, Intune fornisce un'altra opzione oltre alla registrazione e alla gestione dei dispositivi. Un abbonamento a Intune consente di configurare i criteri MAM tramite il portale di Azure, anche se i dispositivi non sono registrati in Intune. Per altre informazioni, vedere [Panoramica dei criteri di protezione delle app](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Argomenti correlati

[Impostare Basic Mobility + Security](set-up.md)

[Registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base](enroll-your-mobile-device.md)

[Gestire i dispositivi registrati nella gestione dei dispositivi mobili per Microsoft 365](manage-enrolled-devices.md)

[Ottenere informazioni dettagliate sui dispositivi gestiti da mobilità e sicurezza di base](get-details-about-managed-devices.md)