---
title: Abilitare la valutazione di Microsoft Defender for Endpoint, attivare la valutazione per MDE
description: Abilitare il laboratorio Microsoft 365 Defender di valutazione o l'ambiente pilota, incluso il controllo dello stato della licenza e gli enpoint di onboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458098"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Abilitare l'ambiente di valutazione di Microsoft Defender for Endpoint


Questo articolo illustra i passaggi per configurare l'ambiente di valutazione per Microsoft Defender for Endpoint usando i dispositivi di produzione. 


>[!TIP]
>Microsoft Defender for Endpoint include anche un laboratorio di valutazione nel prodotto in cui puoi aggiungere dispositivi preconfigurato ed eseguire simulazioni per valutare le funzionalità della piattaforma. Il laboratorio offre un'esperienza di configurazione semplificata che può aiutare a dimostrare rapidamente il valore di Microsoft Defender per Enpdoint, includendo indicazioni per molte funzionalità come la ricerca avanzata e l'analisi delle minacce. Per ulteriori informazioni, vedere [Evaluate capabilities.](/defender-endpoint/evaluation-lab.md) <br> La differenza principale tra le indicazioni fornite in questo articolo e il laboratorio di valutazione è che l'ambiente di valutazione usa dispositivi di produzione, mentre il laboratorio di valutazione usa dispositivi non di produzione. 

Usa la procedura seguente per abilitare la valutazione per Microsoft Defender per Endpoint.

![Passaggi per abilitare Microsoft Defender per Endpoint nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [Passaggio 1. Controllare lo stato della licenza](#step-1-check-license-state)
- [Passaggio 2. Endpoint di onboard](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Passaggio 1. Controllare lo stato della licenza

Dovrai prima controllare lo stato della licenza per verificare che sia stato eseguito correttamente il provisioning. È possibile eseguire questa operazione tramite l'interfaccia di amministrazione o **tramite il Microsoft Azure portale.**


1. Per visualizzare le licenze, passare al **portale di Microsoft Azure** e passare alla Microsoft Azure licenza del [portale.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Immagine della pagina Licenze di Azure](../../media/defender/atp-licensing-azure-portal.png)

1. In alternativa, nell'interfaccia di amministrazione passare a **Fatturazione**  >  **Abbonamenti.**

    Sullo schermo verranno visualizzate tutte le licenze di cui è stato eseguito il provisioning e il relativo **stato corrente.**

    ![Immagine delle licenze di fatturazione](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Passaggio 2. Onboardare gli endpoint usando uno degli strumenti di gestione supportati

Dopo aver verificato che lo stato della licenza sia stato effettuato correttamente, puoi avviare l'onboarding dei dispositivi nel servizio. 

Ai fini della valutazione di Microsoft Defender for Endpoint, ti consigliamo di scegliere un paio di dispositivi Windows 10 su cui eseguire la valutazione. 

[L'argomento Pianificare](../defender-endpoint/deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.  

Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Opzioni dello strumento di onboarding

Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.

Endpoint | Opzioni degli strumenti
:---|:---
**Windows** | [Script locale (fino a 10 dispositivi),](../defender-endpoint/configure-endpoints-script.md)Criteri di [gruppo,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/ Gestione](../defender-endpoint/configure-endpoints-mdm.md)dispositivi mobili, [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [script VDI,](../defender-endpoint/configure-endpoints-vdi.md)integrazione [con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)
**macOS** | [Script locali](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), Gestione [dispositivi mobili](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux Server** | [Script locale,](../defender-endpoint/linux-install-manually.md)  [Pupazzo,](../defender-endpoint/linux-install-with-puppet.md)  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [Basato su app](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>Passaggio successivo
[Configurare il progetto pilota per Microsoft Defender per Endpoint](eval-defender-endpoint-pilot.md)
 
Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)