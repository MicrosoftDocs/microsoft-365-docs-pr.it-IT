---
title: Metodi e strumenti di onboarding per Windows 10 dispositivi
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
description: Onboard Windows 10 dispositivi in modo che possano inviare i dati del sensore alle soluzioni Microsoft 365 conformità
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341701"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Strumenti e metodi di onboarding per i dispositivi Windows 10

**Si applica a:**
- [Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)](./endpoint-dlp-learn-about.md)

I dispositivi nell'organizzazione devono essere configurati in modo che il Microsoft 365 endpoint di prevenzione della perdita dei dati possa ottenere i dati del sensore da essi. Esistono diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.

Sono supportati gli strumenti e i metodi di distribuzione seguenti:

- Criteri di gruppo
- Microsoft Endpoint Configuration Manager
- Gestione dei dispositivi mobili (Microsoft Intune)
- script locale

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Onboardare Windows 10 dispositivi con Criteri di gruppo](dlp-configure-endpoints-gp.md) | Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.
[Onboard Windows dispositivi con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Puoi usare Microsoft Endpoint Configuration Manager (current branch) versione 1606 o Microsoft Endpoint Configuration Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.
[Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md) | Usa gli strumenti di gestione dei dispositivi mobili Microsoft Intune distribuire il pacchetto di configurazione nel dispositivo.
[Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md) | Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.
[Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md) | Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.