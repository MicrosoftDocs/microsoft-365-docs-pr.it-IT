---
title: Microsoft Defender per endpoint su iOS
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender for Endpoint in iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, panoramica, installazione, distribuzione, disinstallazione, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194854"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender per endpoint su iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint su iOS** offre protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app. Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro nella Microsoft Defender Security Center. Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint in iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.

## <a name="pre-requisites"></a>Prerequisiti

**Per gli utenti finali**

- Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app. Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- **Per i dispositivi registrati:** i [](/mem/intune/user-help/enroll-your-device-in-intune-ios) dispositivi vengono registrati tramite l'app Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune. Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.
    - Portale aziendale Intune'app può essere scaricata [dall'Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.

- **Per i dispositivi non registrati:** i dispositivi vengono registrati con Azure Active Directory. Ciò richiede che l'utente finale sia connesso [tramite Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Per gli amministratori**

- Accesso al Microsoft Defender Security Center portale.

- Accesso a [Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431), per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.

    > [!NOTE]
    > Microsoft Intune è l'unica soluzione UEM (Unified Endpoint Management) supportata per la distribuzione di Microsoft Defender for Endpoint e l'applicazione di Defender per i criteri di conformità dei dispositivi correlati all'endpoint in Intune.

**Requisiti di sistema**

- Dispositivo iOS che esegue iOS 11.0 e successive. iPad sono ufficialmente supportati dalla versione 1.1.15010101 e versioni successive.

- Il dispositivo viene registrato con [l'app Portale aziendale Intune](https://apps.apple.com/us/app/intune-company-portal/id719171358) o registrato con Azure Active Directory tramite [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).

## <a name="installation-instructions"></a>Istruzioni di installazione

La distribuzione di Microsoft Defender per Endpoint su iOS può essere eseguita tramite Microsoft Endpoint Manager (MEM) e sono supportati sia i dispositivi supervisionati che i dispositivi senza supervisione. Gli utenti finali possono anche installare direttamente l'app [dall'App Store di Apple.](https://aka.ms/mdatpiosappstore)
Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint in iOS.](ios-install.md)

## <a name="resources"></a>Risorse

- Rimanere informati sulle prossime versioni [visitando Novità di Microsoft Defender per Endpoint su iOS](ios-whatsnew.md) o il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire Microsoft Defender per Endpoint in iOS](ios-install.md)
- [Configurare Microsoft Defender per le funzionalità di Endpoint in iOS](ios-configure-features.md)
