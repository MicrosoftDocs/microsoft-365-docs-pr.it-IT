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
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246417"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender per endpoint su iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint su iOS** offrirà protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app. Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro nella Microsoft Defender Security Center. Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint in iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.

## <a name="pre-requisites"></a>Prerequisiti

**Per gli utenti finali**

- Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app. Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- I dispositivi vengono registrati tramite [l'app](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune. Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.
    - Portale aziendale Intune'app può essere scaricata [dall'Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.

- Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Per gli amministratori**

- Accesso al Microsoft Defender Security Center portale.

    > [!NOTE]
    > Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender for Endpoint in iOS. Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender for Endpoint nei criteri di conformità dei dispositivi correlati a iOS in Intune.

- Accesso a [Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431), per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.

**Requisiti di rete**
- Perché Microsoft Defender for Endpoint su iOS funzioni quando si è connessi a una rete, sarà necessario configurare il firewall/proxy per consentire l'accesso a [Microsoft Defender per](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) gli URL del servizio endpoint

**Requisiti di sistema**

- Dispositivi iOS che eseguono iOS 11.0 e superiori. iPad sono ufficialmente supportati dalla versione 1.1.15010101 e versioni successive.

- Il dispositivo viene [](https://apps.apple.com/us/app/intune-company-portal/id719171358)registrato con l Portale aziendale Intune app .

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender per Endpoint) su iOS è ora disponibile su [Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Istruzioni di installazione

La distribuzione di Microsoft Defender per Endpoint su iOS è tramite Microsoft Intune (MDM) e sono supportati sia i dispositivi supervisionati che i dispositivi non supervisionati.
Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint in iOS.](ios-install.md)

## <a name="resources"></a>Risorse

- Rimanere informati sulle prossime versioni [visitando Novità di Microsoft Defender per Endpoint su iOS](ios-whatsnew.md) o il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire Microsoft Defender per Endpoint in iOS](ios-install.md)
- [Configurare Microsoft Defender per le funzionalità di Endpoint in iOS](ios-configure-features.md)
