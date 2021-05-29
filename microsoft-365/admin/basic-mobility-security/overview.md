---
title: Panoramica della mobilità e della sicurezza di base per Microsoft 365
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
description: Usa Dispositivi mobili e sicurezza di base per impostare i criteri di sicurezza dei dispositivi e le regole di accesso.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706311"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Panoramica della mobilità e della sicurezza di base per Microsoft 365

Puoi gestire e proteggere i dispositivi mobili quando sono connessi all'organizzazione Microsoft 365 tramite Dispositivi mobili e sicurezza di base. I dispositivi mobili, come smartphone e tablet, utilizzati per accedere alla posta elettronica di lavoro, al calendario, ai contatti e ai documenti, giocano un ruolo molto importante nell'assicurare ai dipendenti lo svolgimento del loro lavoro ovunque e in qualsiasi momento. È pertanto fondamentale proteggere le informazioni dell'organizzazione quando gli utenti usano i dispositivi. Puoi usare Dispositivi mobili e sicurezza di base per impostare i criteri di sicurezza e le regole di accesso dei dispositivi e cancellare i dispositivi mobili in caso di sperpero o furto.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configurazione di base per dispositivi mobili e sicurezza":::

## <a name="what-types-of-devices-can-you-manage"></a>Quali tipi di dispositivi è possibile gestire?

Puoi usare Dispositivi mobili e sicurezza di base per gestire molti tipi di dispositivi mobili come Windows Phone, Android, iPhone e iPad. Per gestire i dispositivi mobili usati dagli utenti dell'organizzazione, ogni persona deve disporre di una licenza Microsoft 365 applicabile e il dispositivo deve essere registrato in Dispositivi mobili e sicurezza di base.

Per sapere quali dispositivi mobili e sicurezza di base supportano per ogni tipo di dispositivo, vedi [Funzionalità di mobilità e sicurezza di base.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Passaggi di installazione per Dispositivi mobili e sicurezza di base

Un Microsoft 365 globale deve completare i passaggi seguenti per attivare e configurare La mobilità e la sicurezza di base. Per la procedura dettagliata, seguire le istruzioni in [Set up Basic Mobility and Security.](set-up.md) 

Ecco un riepilogo dei passaggi:

**Passaggio 1:** Attivare Dispositivi mobili e sicurezza di base seguendo la procedura descritta in  [Set up Basic Mobility and Security.](set-up.md)

**Passaggio 2:** Configurare dispositivi mobili e sicurezza di base creando ad esempio un certificato APNs per gestire i dispositivi iOS e aggiungendo un record DNS (Domain Name System) per il dominio per supportare i telefoni Windows.

**Passaggio 3:** Crea criteri dispositivo e applicali a gruppi di utenti. Quando si esegue questa operazione, gli utenti ottengono un messaggio di registrazione nel dispositivo e, dopo aver completato la registrazione, i dispositivi sono limitati dai criteri impostati per loro. Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base dei criteri di sicurezza e dispositivi mobili":::

## <a name="device-management-tasks"></a>Attività di gestione dei dispositivi

Dopo aver configurato Dispositivi mobili e sicurezza di base e aver registrato i dispositivi degli utenti, puoi gestire i dispositivi, bloccare l'accesso o cancellare un dispositivo, se necessario. Per altre informazioni su alcune attività comuni di gestione dei dispositivi, inclusa la posizione in cui completare le attività, vedi Gestire i dispositivi registrati in Gestione dispositivi mobili [per Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Altri modi per gestire dispositivi e app

Se hai solo bisogno di gestione delle app per dispositivi mobili (MAM), ad esempio per gli utenti che aggiornano progetti di lavoro nei propri dispositivi, Intune offre un'altra opzione oltre alla registrazione e alla gestione dei dispositivi. Una sottoscrizione di Intune consente di configurare i criteri MAM tramite il portale di Azure, anche se i dispositivi degli utenti non sono registrati in Intune. Per altre info, vedi [Panoramica dei criteri di protezione delle app.](/mem/intune/apps/app-protection-policy)

## <a name="related-content"></a>Contenuto correlato

[Configurare dispositivi mobili e sicurezza di base](set-up.md) (articolo)\
[Registrare il dispositivo mobile con Dispositivi mobili e sicurezza](enroll-your-mobile-device.md) di base (articolo)\
[Gestire i dispositivi registrati in Gestione dispositivi mobili per Microsoft 365](manage-enrolled-devices.md) (articolo)\
[Informazioni dettagliate sui dispositivi gestiti da Dispositivi mobili e sicurezza di base](get-details-about-managed-devices.md) (articolo)