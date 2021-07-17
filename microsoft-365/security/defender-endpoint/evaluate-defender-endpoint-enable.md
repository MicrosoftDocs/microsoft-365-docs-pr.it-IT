---
title: Valutazione pilota di Defender for Endpoint
description: Abilita il tuo Microsoft 365 Defender di prova o un ambiente pilota.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458188"
---
# <a name="pilot-mde-evaluation"></a>Valutazione MDE pilota

>[!NOTE]
>Allo scopo di guidare l'utente attraverso una distribuzione tipica, questo scenario copre solo l'uso di Microsoft Endpoint Configuration Manager. Defender for Endpoint supporta l'uso di altri strumenti di onboarding, ma non copre questi scenari nella guida alla distribuzione. Per altre informazioni, vedi [Onboard di dispositivi a Microsoft Defender per Endpoint.](onboard-configure.md)

## <a name="step-1-check-license-state"></a>Passaggio 1. Controllare lo stato della licenza

Il controllo dello stato della licenza e del provisioning corretto può essere eseguito tramite l'interfaccia di amministrazione o tramite il **portale Microsoft Azure .**

1. Per visualizzare le licenze, passare al **portale di Microsoft Azure** e passare alla Microsoft Azure licenza del [portale.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Immagine della pagina Licenze di Azure](images/atp-licensing-azure-portal.png)

1. In alternativa, nell'interfaccia di amministrazione passare a **Fatturazione**  >  **Abbonamenti.**

    Sullo schermo verranno visualizzate tutte le licenze di cui è stato eseguito il provisioning e il relativo **stato corrente.**

    ![Immagine delle licenze di fatturazione](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Passaggio 2. Onboardare gli endpoint usando uno degli strumenti di gestione supportati

[L'argomento Pianificare](deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.  

Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Dopo aver identificato l'architettura, è necessario decidere quale metodo di distribuzione utilizzare. Lo strumento di distribuzione scelto influisce sulla modalità di onboard degli endpoint nel servizio.

### <a name="onboarding-tool-options"></a>Opzioni dello strumento di onboarding

Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.

| Endpoint     | Opzioni degli strumenti                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script locale (fino a 10 dispositivi)](../defender-endpoint/configure-endpoints-script.md) <br> [Criteri di gruppo](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/ Gestione dispositivi mobili](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [Script VDI](../defender-endpoint/configure-endpoints-vdi.md) <br> [Integrazione con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [Script locali](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [Gestione di dispositivi mobili](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [Script locale](../defender-endpoint/linux-install-manually.md) <br> [Pupazzo](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [Basato su app](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)               |
