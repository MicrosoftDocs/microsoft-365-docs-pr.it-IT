---
title: Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa gli strumenti di gestione dei dispositivi mobili per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917992"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili

**Si applica a:**

- [Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)](./endpoint-dlp-learn-about.md)

Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi. La prevenzione della perdita dei dati degli endpoint di Microsoft 365 supporta gli MMM fornendo OMA-URIs creare criteri per la gestione dei dispositivi.


## <a name="before-you-begin"></a>Prima di iniziare
Se si usa Microsoft Intune, è necessario che il dispositivo MDM sia registrato. In caso contrario, le impostazioni non verranno applicate correttamente. 

Per altre informazioni sull'abilitazione di MDM con Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboardare i dispositivi con Microsoft Intune

Seguire le istruzioni di [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard e monitora i dispositivi con gli strumenti di gestione dei dispositivi mobili

Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **Onboarding del dispositivo Offboarding.**  >  

3. Nel campo **Metodo di distribuzione** seleziona Gestione dispositivi mobili / Microsoft **Intune.**
    
4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto. Dovresti avere un file denominato *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Usa i criteri di configurazione personalizzati di Microsoft Intune per distribuire le seguenti impostazioni URI OMA supportate.

      URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo di data: String      
      Valore: [Copiare e incollare il valore dal contenuto del file DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Per altre informazioni sulle impostazioni dei criteri di Microsoft Intune, vedi Impostazioni dei criteri [di Windows 10 in Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> Il **criterio Stato integrità per i dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

## <a name="related-topics"></a>Argomenti correlati
- [Onboardare dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)