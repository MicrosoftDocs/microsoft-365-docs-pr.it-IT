---
title: Onboard dei dispositivi non Windows nel servizio Microsoft Defender for Endpoint
description: Configura i dispositivi non Windows in modo che possano inviare i dati del sensore al servizio Microsoft Defender ATP.
keywords: onboardare dispositivi non Windows, macos, linux, gestione dei dispositivi, configurare i dispositivi Windows ATP, configurare Microsoft Defender per i dispositivi endpoint
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687878"
---
# <a name="onboard-non-windows-devices"></a>Aggiungere dispositivi non Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Piattaforme**
- macOS
- Linux

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint offre un'esperienza operativa di sicurezza centralizzata per Windows e per le piattaforme non Windows. Potrai visualizzare gli avvisi di vari sistemi operativi supportati in Microsoft Defender Security Center e proteggere meglio la rete dell'organizzazione. 

Per il funzionamento dell'integrazione, devi conoscere esattamente le versioni di Linux e macOS compatibili con Defender for Endpoint. Per altre informazioni, vedere:
- [Requisiti di sistema di Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- Requisiti di sistema di [Microsoft Defender per Endpoint su macOS](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Onboarding di dispositivi non Windows
Dovrai eseguire la procedura seguente per eseguire l'onboard di dispositivi non Windows:
1. Seleziona il metodo di onboarding preferito:

   - Per i dispositivi macOS, puoi scegliere di eseguire l'onboardboard tramite Microsoft Defender ATP o tramite una soluzione di terze parti. Per altre informazioni, vedi [Microsoft Defender per Endpoint per Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - Per altri dispositivi non Windows scegli **Onboard di dispositivi non Windows tramite l'integrazione di terze parti.**   
    1. Nel riquadro di spostamento selezionare **Partner di**  >  **interoperabilità**. Verificare che la soluzione di terze parti sia elencata.
    2. Nella scheda **Applicazioni partner** seleziona il partner che supporta i dispositivi non Windows.
    3. Seleziona **Apri pagina partner** per aprire la pagina del partner. Segui le istruzioni fornite nella pagina.
    4. Dopo aver creato un account o aver accettato la sottoscrizione alla soluzione partner, è consigliabile arrivare a una fase in cui a un amministratore globale tenant dell'organizzazione viene richiesto di accettare una richiesta di autorizzazione dall'applicazione partner. Leggere attentamente la richiesta di autorizzazione per assicurarsi che sia allineata al servizio richiesto. 

        
2. Eseguire un test di rilevamento seguendo le istruzioni della soluzione di terze parti.

## <a name="offboard-non-windows-devices"></a>Offboard di dispositivi non Windows

1. Seguire la documentazione di terze parti per disconnettere la soluzione di terze parti da Microsoft Defender per Endpoint.

2. Rimuovere le autorizzazioni per la soluzione di terze parti nel tenant di Azure AD.
   1. Accedere al [portale di Azure](https://portal.azure.com).
   2. Selezionare **Azure Active Directory > Enterprise Applications**.
   3. Seleziona l'applicazione che vuoi offboard.
   4. Selezionare il **pulsante** Elimina.


## <a name="related-topics"></a>Argomenti correlati
- [Aggiungere di dispositivi Windows 10](configure-endpoints.md)
- [Server di onboard](configure-server-endpoints.md)
- [Configurare le impostazioni di connettività Proxy e Internet](configure-proxy-internet.md)
- [Risoluzione dei problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
