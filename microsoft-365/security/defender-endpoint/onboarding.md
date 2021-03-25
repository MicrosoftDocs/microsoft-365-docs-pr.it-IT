---
title: Onboard al servizio Microsoft Defender ATP
description: Informazioni su come eseguire l'onboardboard degli endpoint nel servizio Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186930"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Onboard al servizio Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Informazioni sulle varie fasi della distribuzione di Microsoft Defender for Endpoint e su come configurare le funzionalità all'interno della soluzione. 

La distribuzione di Defender per Endpoint è un processo in tre fasi:

| [![fase di distribuzione - preparazione](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: preparare](prepare-deployment.md) | [![fase di distribuzione - installazione](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: installazione](production-deployment.md) | ![fase di distribuzione - onboard](images/phase-diagrams/onboard.png)<br>Fase 3: onboard |
| ----- | ----- | ----- |
| | |*Sei qui!*|

Si è attualmente in fase di onboarding.

Questi sono i passaggi da eseguire per distribuire Defender for Endpoint:

- Passaggio 1: eseguire il onboard degli endpoint nel servizio 
- Passaggio 2: Configurare le funzionalità 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Passaggio 1: onboardare gli endpoint usando uno degli strumenti di gestione supportati
[L'argomento Pianificare](deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.  


Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



Dopo aver identificato l'architettura, è necessario decidere quale metodo di distribuzione utilizzare. Lo strumento di distribuzione scelto influisce sulla modalità di onboard degli endpoint nel servizio. 

### <a name="onboarding-tool-options"></a>Opzioni dello strumento di onboarding

Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.

| Endpoint     | Opzioni degli strumenti                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script locale (fino a 10 dispositivi)](configure-endpoints-script.md) <br>  [Criteri di gruppo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Script VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Script locali](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gestione di dispositivi mobili](mac-install-with-other-mdm.md) |
| **Linux Server** | [Script locale](linux-install-manually.md) <br> [Pupazzo](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Basato su app](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Passaggio 2: Configurare le funzionalità
Dopo l'onboarding degli endpoint, configurerai le varie funzionalità, ad esempio il rilevamento e la risposta degli endpoint, la protezione di nuova generazione e la riduzione della superficie di attacco. 


## <a name="example-deployments"></a>Distribuzioni di esempio
In questa guida alla distribuzione verrà illustrato come usare due strumenti di distribuzione per eseguire l'onboarding degli endpoint e come configurare le funzionalità.

Gli strumenti nelle distribuzioni di esempio sono:
- [Onboarding con Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarding con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Usando gli strumenti di distribuzione menzionati in precedenza, sarai quindi guidato nella configurazione delle funzionalità di Defender for Endpoint seguenti:
- Rilevamento degli endpoint e configurazione della risposta
- Configurazione di protezione di nuova generazione
- Configurazione della riduzione della superficie di attacco

## <a name="related-topics"></a>Argomenti correlati
- [Onboarding con Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarding con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
