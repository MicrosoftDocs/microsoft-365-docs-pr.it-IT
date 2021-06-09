---
title: Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint
description: Tieni traccia dell'onboarding dei dispositivi gestiti da Intune in Microsoft Defender per Endpoint e aumenta la frequenza di onboarding.
keywords: onboard, gestione di Intune, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, gestione della configurazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841571"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Ogni dispositivo onboarded aggiunge un ulteriore sensore di rilevamento e risposta degli endpoint (EDR) e aumenta la visibilità sull'attività di violazione nella rete. L'onboarding garantisce inoltre che un dispositivo possa essere controllato alla ricerca di componenti vulnerabili e problemi di configurazione della sicurezza e possa ricevere azioni di correzione critiche durante gli attacchi.

Prima di poter tenere traccia e gestire l'onboarding dei dispositivi:
- [Registrare i dispositivi nella gestione di Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Verificare di disporre delle autorizzazioni necessarie](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Individuare e tenere traccia dei dispositivi non protetti

La scheda **di onboarding** offre una panoramica generale della frequenza di onboarding confrontando il numero di dispositivi Windows 10 che sono stati effettivamente onboarding in Defender per Endpoint con il numero totale di dispositivi Windows 10 gestiti da Intune.

![Scheda di onboarding per la gestione della configurazione dei dispositivi](images/secconmgmt_onboarding_card.png)<br>
*Scheda che mostra i dispositivi onboarded rispetto al numero totale di dispositivi Windows 10 Intune*

>[!NOTE]
>Se hai usato Gestione configurazione Centro sicurezza, lo script di onboarding o altri metodi di onboarding che non usano profili intune, potresti riscontrare discrepanze di dati. Per risolvere queste discrepanze, crea un profilo di configurazione intune corrispondente per Defender per l'onboarding dell'endpoint e assegna il profilo ai dispositivi.

## <a name="onboard-more-devices-with-intune-profiles"></a>Onboardare più dispositivi con profili intune

Defender for Endpoint offre diverse opzioni convenienti per [l'onboarding Windows 10 dispositivi](onboard-configure.md). Per i dispositivi gestiti da Intune, tuttavia, puoi sfruttare i profili di Intune per distribuire comodamente il sensore Defender for Endpoint per selezionare i dispositivi, in modo efficace l'onboarding di questi dispositivi nel servizio.

Nella scheda **Onboarding** seleziona **Onboarding di altri** dispositivi per creare e assegnare un profilo in Intune. Il collegamento consente di accedere alla pagina di conformità del dispositivo in Intune, che fornisce una panoramica simile dello stato di onboarding.

![Pagina conformità dispositivo Microsoft Defender for Endpoint nella gestione dei dispositivi intune](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Pagina conformità dispositivo Microsoft Defender for Endpoint nella gestione dei dispositivi intune*

>[!TIP]
>In alternativa, è possibile passare alla pagina Conformità onboarding di Defender for Endpoint nel portale [di Microsoft Azure](https://portal.azure.com/) da Tutti i servizi **> Intune > Conformità dispositivo > Microsoft Defender ATP**.

>[!NOTE]
> Se vuoi visualizzare i dati del dispositivo più aggiornati, fai clic su Elenco di dispositivi senza sensore **ATP.**

Dalla pagina conformità del dispositivo, crea un profilo di configurazione specifico per la distribuzione del sensore Defender for Endpoint e assegna il profilo ai dispositivi che vuoi eseguire l'onboard. A tale scopo, è possibile:

- Seleziona Crea un profilo di configurazione del dispositivo per configurare il sensore **ATP** in modo che inizi con un profilo di configurazione del dispositivo predefinito.
- Crea il profilo di configurazione del dispositivo da zero.

Per altre informazioni, leggi l'uso dei profili di configurazione dei dispositivi [intune per eseguire l'onboardmento dei dispositivi in Defender per Endpoint.](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Argomenti correlati
- [Verificare che i dispositivi siano configurati correttamente](configure-machines.md)
- [Aumentare la conformità alla linea di base di sicurezza di Defender for Endpoint](configure-machines-security-baseline.md)
- [Ottimizzare la distribuzione e i rilevamenti delle regole asr](configure-machines-asr.md)
