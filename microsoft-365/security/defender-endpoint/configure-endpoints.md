---
title: Strumenti e metodi di onboarding per i dispositivi Windows 10
description: Onboard dei dispositivi Windows 10 in modo che possano inviare i dati del sensore al sensore Microsoft Defender ATP
keywords: Onboard dei dispositivi Windows 10, criteri di gruppo, gestione della configurazione degli endpoint, gestione dei dispositivi mobili, script locale, criteri di gruppo, sccm, mdm, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165538"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Strumenti e metodi di onboarding per i dispositivi Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

I dispositivi nell'organizzazione devono essere configurati in modo che il servizio Defender for Endpoint possa ottenere i dati del sensore da essi. Esistono diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.

Sono supportati gli strumenti e i metodi di distribuzione seguenti:

- Criteri di gruppo
- Microsoft Endpoint Configuration Manager
- Gestione dei dispositivi mobili (incluso Microsoft Intune)
- Script locale

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Onboardare dispositivi Windows 10 con Criteri di gruppo](configure-endpoints-gp.md) | Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.
[Onboard dei dispositivi Windows con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Puoi usare Microsoft Endpoint Manager (current branch) versione 1606 o Microsoft Endpoint Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.
[Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](configure-endpoints-mdm.md) | Usa gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.
[Onboarding di dispositivi Windows 10 con uno script locale](configure-endpoints-script.md) | Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.
[Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](configure-endpoints-vdi.md) | Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
