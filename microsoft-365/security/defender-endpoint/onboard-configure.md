---
title: Onboard dei dispositivi al servizio Microsoft Defender for Endpoint
description: Onboard di dispositivi Windows 10, server, dispositivi non Windows e scopri come eseguire un test di rilevamento.
keywords: onboarding, Microsoft Defender for Endpoint onboarding, sccm, criteri di gruppo, mdm, script locale, test di rilevamento
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
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933554"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Onboard dei dispositivi al servizio Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Dovrai passare alla sezione onboarding del portale di Defender for Endpoint per eseguire l'onboarding di uno dei dispositivi supportati. A seconda del dispositivo, sarai guidato con i passaggi appropriati e le opzioni degli strumenti di gestione e distribuzione disponibili per il dispositivo. 

In generale, per eseguire l'onboardboard dei dispositivi nel servizio:

- Verificare che il dispositivo soddisfa i [requisiti minimi](minimum-requirements.md)
- A seconda del dispositivo, segui i passaggi di configurazione forniti nella sezione onboarding del portale defender per endpoint
- Usare lo strumento di gestione e il metodo di distribuzione appropriati per i dispositivi
- Eseguire un test di rilevamento per verificare che i dispositivi siano correttamente onboarded e segnalare al servizio

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Opzioni dello strumento di onboarding
Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.

| Endpoint     | Opzioni degli strumenti                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script locale (fino a 10 dispositivi)](configure-endpoints-script.md) <br>  [Criteri di gruppo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Script VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Script locali](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gestione di dispositivi mobili](mac-install-with-other-mdm.md) |
| **Linux Server** | [Script locale](linux-install-manually.md) <br> [Pupazzo](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Basato su app](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Aggiungere versioni precedenti di Windows](onboard-downlevel.md)| Onboard di dispositivi Windows 7 e Windows 8.1 a Defender per Endpoint. 
[Aggiungere di dispositivi Windows 10](configure-endpoints.md) | Dovrai eseguire l'onboardboard dei dispositivi per segnalare al servizio Defender for Endpoint. Scopri gli strumenti e i metodi che puoi usare per configurare i dispositivi nell'organizzazione.
[Server di onboard](configure-server-endpoints.md) |  Onboarding di Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) versione 1803 e successive, Windows Server 2019 e versioni successive e Windows Server 2019 core edition per Defender for Endpoint.
[Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md) | Defender for Endpoint offre un'esperienza operativa di sicurezza centralizzata per Windows e per le piattaforme non Windows. Potrai visualizzare gli avvisi di vari sistemi operativi supportati in Microsoft Defender Security Center e proteggere meglio la rete dell'organizzazione. Questa esperienza sfrutta i dati del sensore di prodotti di sicurezza di terze parti. 
[Eseguire un test di rilevamento in un dispositivo appena aggiunto](run-detection-test.md) | Esegui uno script su un dispositivo appena onboarded per verificare che sia correttamente segnalato al servizio Defender for Endpoint.
[Configurare le impostazioni proxy e Internet](configure-proxy-internet.md)| Abilitare la comunicazione con il servizio cloud Defender for Endpoint configurando le impostazioni di connettività Internet e proxy.
[Risolvere i problemi di onboarding](troubleshoot-onboarding.md) | Informazioni sulla risoluzione dei problemi che potrebbero verificarsi durante l'onboarding.

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
