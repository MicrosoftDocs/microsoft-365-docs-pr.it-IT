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
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430201"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Panoramica della mobilità e della sicurezza di base per Microsoft 365

È possibile gestire e proteggere i dispositivi mobili quando sono connessi all'organizzazione di Microsoft 365 tramite Dispositivi mobili e sicurezza di base. I dispositivi mobili, come smartphone e tablet, utilizzati per accedere alla posta elettronica di lavoro, al calendario, ai contatti e ai documenti, giocano un ruolo molto importante nell'assicurare ai dipendenti lo svolgimento del loro lavoro ovunque e in qualsiasi momento. È pertanto fondamentale proteggere le informazioni dell'organizzazione quando gli utenti usano i dispositivi. Puoi usare Dispositivi mobili e sicurezza di base per impostare i criteri di sicurezza dei dispositivi e le regole di accesso e per cancellare i dispositivi mobili se vengono smarriti o rubati.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configurazione di base per dispositivi mobili e sicurezza":::

## <a name="what-types-of-devices-can-you-manage"></a>Quali tipi di dispositivi è possibile gestire?

Puoi usare Dispositivi mobili e sicurezza di base per gestire molti tipi di dispositivi mobili come Windows Phone, Android, iPhone e iPad. Per gestire i dispositivi mobili usati dagli utenti dell'organizzazione, ogni persona deve disporre di una licenza di Microsoft 365 applicabile e il dispositivo deve essere registrato in Basic Mobility and Security.

Per informazioni sulle funzionalità supportate da Dispositivi mobili e sicurezza di base per ogni tipo di dispositivo, vedere [Funzionalità di mobilità e sicurezza di base.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Passaggi di configurazione per dispositivi mobili e sicurezza di base

Un amministratore globale di Microsoft 365 deve completare la procedura seguente per attivare e configurare Basic Mobility and Security. Per la procedura dettagliata, seguire le istruzioni in [Set up Basic Mobility and Security.](set-up.md) 

Ecco un riepilogo dei passaggi:

**Passaggio 1:** Attivare dispositivi mobili e sicurezza di base seguendo la procedura descritta in  [Set up Basic Mobility and Security.](set-up.md)

**Passaggio 2:** Configurare dispositivi mobili e sicurezza di base creando ad esempio un certificato APNs per gestire i dispositivi iOS e aggiungendo un record DNS (Domain Name System) per il dominio per supportare i telefoni Windows.

**Passaggio 3:** Creare criteri dispositivo e applicarli a gruppi di utenti. Quando si esegue questa operazione, gli utenti ottengono un messaggio di registrazione nel dispositivo e, dopo aver completato la registrazione, i dispositivi sono limitati dai criteri che hai configurato per loro. Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni dei criteri di sicurezza e mobilità di base":::

## <a name="device-management-tasks"></a>Attività di gestione dei dispositivi

Dopo aver configurato Basic Mobility and Security e aver registrato i propri dispositivi, puoi gestire i dispositivi, bloccare l'accesso o cancellare un dispositivo, se necessario. Per altre informazioni su alcune attività comuni di gestione dei dispositivi, inclusa la posizione in cui completare le attività, vedere Gestire i dispositivi registrati in Gestione dispositivi mobili [per Microsoft 365.](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>Altri modi per gestire dispositivi e app

Se è sufficiente la gestione delle app per dispositivi mobili (MAM), ad esempio per gli utenti che aggiornano i progetti di lavoro nei propri dispositivi, Intune offre un'altra opzione oltre a registrare e gestire i dispositivi. Una sottoscrizione a Intune consente di configurare i criteri MAM tramite il portale di Azure, anche se i dispositivi degli utenti non sono registrati in Intune. Per altre info, vedi Panoramica [dei criteri di protezione delle app.](https://go.microsoft.com/fwlink/?LinkId=2132517)

## <a name="related-topics"></a>Argomenti correlati

[Impostare Basic Mobility + Security](set-up.md)

[Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base](enroll-your-mobile-device.md)

[Gestire i dispositivi registrati in Gestione dispositivi mobili per Microsoft 365](manage-enrolled-devices.md)

[Ottenere informazioni dettagliate sui dispositivi gestiti da Basic Mobility and Security](get-details-about-managed-devices.md)