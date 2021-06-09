---
title: Microsoft Defender per Endpoint su Android
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender per Endpoint in Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installazione, distribuzione, disinstallazione, intune
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
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844719"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender per Endpoint su Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint in Android.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender per Endpoint su Android può causare problemi di prestazioni ed errori di sistema imprevedibili.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Come installare Microsoft Defender per Endpoint in Android

### <a name="prerequisites"></a>Prerequisiti

-   **Per gli utenti finali**

    -   Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app. Vedere [Requisiti di licenza di Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Portale aziendale Intune'app può essere scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) ed è disponibile nel dispositivo Android.

        -   Inoltre, i dispositivi possono [](/mem/intune/user-help/enroll-device-android-company-portal) essere registrati tramite l'app Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune. Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.

    -   Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Per gli amministratori**

    -   Accesso al Microsoft Defender Security Center portale.

        > [!NOTE]
        > Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender per Endpoint in Android. Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender per Endpoint nei criteri di conformità dei dispositivi correlati ad Android in Intune. 

    -   Accedere [Microsoft Endpoint Manager'interfaccia di](https://go.microsoft.com/fwlink/?linkid=2109431)amministrazione , per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.
        
### <a name="network-requirements"></a>Requisiti di rete

- Perché Microsoft Defender for Endpoint su Android funzioni quando si è connessi a una rete, sarà necessario configurare il firewall/proxy per consentire l'accesso a Microsoft Defender per gli URL del servizio [endpoint.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Requisiti di sistema

-   Dispositivi Android che eseguono Android 6.0 e versioni successive.
-   Portale aziendale Intune'app viene scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e installata. La registrazione dei dispositivi è necessaria per applicare i criteri di conformità dei dispositivi di Intune.

### <a name="installation-instructions"></a>Istruzioni di installazione

Microsoft Defender per Endpoint su Android supporta l'installazione in entrambe le modalità dei dispositivi registrati, l'amministratore dei dispositivi legacy e le modalità Enterprise Android.
**Attualmente, i dispositivi di proprietà personale con profilo di lavoro e le registrazioni di dispositivi utente completamente gestiti di proprietà aziendale sono supportati in Android Enterprise. Il supporto per altre modalità Enterprise Android verrà annunciato quando sarà pronto.**

La distribuzione di Microsoft Defender per Endpoint su Android è tramite Microsoft Intune (MDM).
Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender per Endpoint su Android è ora disponibile su [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> Puoi connetterti a Google Play da Intune per distribuire l'app Microsoft Defender for Endpoint, tra le modalità di entrollment di Amministratore dispositivi e Android Enterprise di entrollment. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Come configurare Microsoft Defender per Endpoint su Android

Le indicazioni su come configurare Le funzionalità di Microsoft Defender per Endpoint su Android sono disponibili in [Configure Microsoft Defender for Endpoint on Android features.](android-configure.md)



## <a name="related-topics"></a>Argomenti correlati
- [Distribuzione di Microsoft Defender per Endpoint per Android con Microsoft Intune](android-intune.md)
- [Configurare funzionalità di Microsoft Defender per Endpoint su funzionalità Android](android-configure.md)

