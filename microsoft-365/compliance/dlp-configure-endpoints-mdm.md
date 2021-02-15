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
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769480"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili

**Si applica a:**

- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi. La prevenzione della perdita dei dati degli endpoint di Microsoft 365 supporta gli MPM fornendo OMA-URIs creare criteri per la gestione dei dispositivi.


## <a name="before-you-begin"></a>Prima di iniziare
Se si usa Microsoft Intune, è necessario che il dispositivo MDM sia registrato. In caso contrario, le impostazioni non verranno applicate correttamente. 

Per altre informazioni sull'abilitazione di MDM con Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard dei dispositivi con Microsoft Intune

Seguire le istruzioni di [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)

> [!NOTE]
> - Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Eseguire l'offboard e monitorare i dispositivi con gli strumenti di gestione dei dispositivi mobili

Per motivi di sicurezza, il pacchetto usato per l'offboard dei dispositivi scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando scarii un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà conflitti imprevedibili.

1. Ottenere il pacchetto offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del** dispositivo  >  **Offboarding.**

3. Nel campo **Metodo di distribuzione** selezionare Gestione dispositivi **mobili/ Microsoft Intune.**
    
4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto. Dovresti avere un file denominato *DeviceCompliance_valid_until_YYYY-MM-D.offboarding.*

6. Usa i criteri di configurazione personalizzati di Microsoft Intune per distribuire le seguenti impostazioni URI OMA supportate.

      URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo di data: Stringa      
      Valore: [Copiare e incollare il valore dal contenuto del DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Per altre informazioni sulle impostazioni dei criteri di Microsoft Intune, vedi le impostazioni dei criteri di [Windows 10 in Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> Il criterio Stato integrità per i **dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati del dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
