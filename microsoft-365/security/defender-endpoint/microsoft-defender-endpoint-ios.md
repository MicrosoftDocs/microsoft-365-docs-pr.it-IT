---
title: Panoramica di Microsoft Defender ATP per iOS
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender ATP per iOS
keywords: microsoft, defender, atp, ios, panoramica, installazione, distribuzione, disinstallazione, intune
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
ms.openlocfilehash: 7d4bc095a9fbc0b9cd166d3133ed291a2c8c01da
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615424"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a>Microsoft Defender per endpoint per iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint per iOS** offrirà protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app. Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro in Microsoft Defender Security Center. Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint per iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.

## <a name="pre-requisites"></a>Prerequisiti

**Per gli utenti finali**

- Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app. Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- I dispositivi vengono registrati tramite [l'app](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Portale aziendale intune per applicare i criteri di conformità dei dispositivi intune. Ciò richiede che all'utente finale sia assegnata una licenza di Microsoft Intune.
    - L'app Portale aziendale intune può essere scaricata [dall'App Store di Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.

- Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Per gli amministratori**

- Accesso al portale di Microsoft Defender Security Center.

    > [!NOTE]
    > Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender for Endpoint per iOS. Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender for Endpoint per i criteri di conformità dei dispositivi correlati a iOS in Intune.

- Accesso [all'interfaccia di amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.

**Requisiti di sistema**

- Dispositivi iOS che eseguono iOS 11.0 e superiori. I dispositivi iPad sono ufficialmente supportati dalla versione 1.1.15010101 e così via.

- Il dispositivo viene registrato con [l'app Portale aziendale intune](https://apps.apple.com/us/app/intune-company-portal/id719171358).

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender for Endpoint) per iOS è ora disponibile su [Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Istruzioni di installazione

La distribuzione di Microsoft Defender per Endpoint per iOS è tramite Microsoft Intune (MDM) e sono supportati sia i dispositivi supervisionati che i dispositivi senza supervisione.
Per altre informazioni, vedi [Distribuire Microsoft Defender for Endpoint per iOS.](ios-install.md)

## <a name="resources"></a>Risorse

- Rimanere informati sulle prossime versioni [visitando Novità di Microsoft Defender per Endpoint per iOS](ios-whatsnew.md) o il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire Microsoft Defender per Endpoint per iOS](ios-install.md)
- [Configurare Le funzionalità di Microsoft Defender per Endpoint per iOS](ios-configure-features.md)
