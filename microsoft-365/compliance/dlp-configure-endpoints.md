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
description: Dispositivi di bordo di Windows 10 in modo che possano inviare i dati del sensore alle soluzioni di conformità di Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769643"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Strumenti e metodi di onboarding per i dispositivi Windows 10 (anteprima)

**Si applica a:**
- [Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)

I dispositivi nell'organizzazione devono essere configurati in modo che il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint possa ottenere i dati dei sensori. Sono disponibili diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.

Sono supportati gli strumenti e i metodi di distribuzione seguenti:

- criteri di gruppo
- Microsoft Endpoint Configuration Manager
- Gestione dei dispositivi mobili (tra cui Microsoft Intune)
- script locale

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Dispositivi di bordo di Windows 10 con criteri di gruppo](dlp-configure-endpoints-gp.md) | Utilizzare criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.
[Dispositivi di bordo di Windows con Microsoft endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | È possibile utilizzare Microsoft endpoint Configuration Manager (Current Branch) versione 1606 o Microsoft endpoint Configuration Manager (Current Branch) versione 1602 o versioni precedenti per distribuire il pacchetto di configurazione nei dispositivi.
[Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili](dlp-configure-endpoints-mdm.md) | Utilizzare gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.
[Dispositivi di bordo di Windows 10 con uno script locale](dlp-configure-endpoints-script.md) | Informazioni su come utilizzare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.
[Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo](dlp-configure-endpoints-vdi.md) | Informazioni su come utilizzare il pacchetto di configurazione per configurare i dispositivi VDI.
