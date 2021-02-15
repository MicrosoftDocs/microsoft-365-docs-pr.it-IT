---
title: Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Eseguire l'onboarded dei dispositivi Windows 10 in modo che possano inviare i dati dei sensori alle soluzioni di conformità di Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769643"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)

**Si applica a:**
- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

I dispositivi dell'organizzazione devono essere configurati in modo che il servizio di prevenzione della perdita dei dati degli endpoint di Microsoft 365 possa ottenere i dati dei sensori. Esistono diversi metodi e strumenti di distribuzione che puoi usare per configurare i dispositivi nell'organizzazione.

Sono supportati gli strumenti e i metodi di distribuzione seguenti:

- Criteri di gruppo
- Microsoft Endpoint Configuration Manager
- Gestione di dispositivi mobili (incluso Microsoft Intune)
- script locale

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Onboard dei dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md) | Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.
[Onboard dei dispositivi Windows con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Puoi usare Microsoft Endpoint Configuration Manager (current branch) versione 1606 o Microsoft Endpoint Configuration Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.
[Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md) | Usa gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.
[Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md) | Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.
[Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md) | Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.
