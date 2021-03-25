---
title: Microsoft Defender ATP per Android
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender ATP per Android
keywords: microsoft, defender, atp, android, installazione, distribuire, disinstallazione, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187614"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender per Endpoint per Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint per Android.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender per Endpoint per Android può causare problemi di prestazioni ed errori di sistema imprevedibili.


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>Come installare Microsoft Defender per Endpoint per Android

### <a name="prerequisites"></a>Prerequisiti

-   **Per gli utenti finali**

    -   Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app. Vedere [Requisiti di licenza di Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   L'app Portale aziendale intune può essere scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) ed è disponibile nel dispositivo Android.

        -   Inoltre, i dispositivi possono [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) essere registrati tramite l'app Portale aziendale intune per applicare i criteri di conformità dei dispositivi intune. Ciò richiede che all'utente finale sia assegnata una licenza di Microsoft Intune.

    -   Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Per gli amministratori**

    -   Accesso al portale di Microsoft Defender Security Center.

        > [!NOTE]
        > Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender per Endpoint per Android. Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender per Endpoint per i criteri di conformità dei dispositivi android correlati in Intune. 

    -   Accedere [all'interfaccia di amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.

### <a name="system-requirements"></a>Requisiti di sistema

-   Dispositivi Android che eseguono Android 6.0 e versioni successive.
-   L'app Portale aziendale intune viene scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e installata. La registrazione dei dispositivi è necessaria per applicare i criteri di conformità dei dispositivi di Intune.

### <a name="installation-instructions"></a>Istruzioni di installazione

Microsoft Defender for Endpoint per Android supporta l'installazione in entrambe le modalità dei dispositivi registrati, le modalità Legacy Device Administrator e Android Enterprise.
**Attualmente, i dispositivi di proprietà personale con profilo di lavoro e le irozioni di dispositivi utente completamente gestiti di proprietà dell'azienda sono supportati in Android Enterprise. Il supporto per altre modalità Android Enterprise verrà annunciato quando sarà pronto.**

La distribuzione di Microsoft Defender per Endpoint per Android è tramite Microsoft Intune (MDM).
Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint per Android con Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Microsoft Defender per Endpoint per Android è ora disponibile su [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> Puoi connetterti a Google Play da Intune per distribuire l'app Microsoft Defender for Endpoint, tra le modalità amministratore del dispositivo e entrollment Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>Come configurare Microsoft Defender per Endpoint per Android

Le indicazioni su come configurare le funzionalità di Microsoft Defender per Endpoint per Android sono disponibili in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).



## <a name="related-topics"></a>Argomenti correlati
- [Distribuire Microsoft Defender per Endpoint con Microsoft Intune](android-intune.md)
- [Configurare le funzionalità di Microsoft Defender per Endpoint per Android](android-configure.md)

