---
title: Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili
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
description: Utilizzare gli strumenti di gestione dei dispositivi mobili per distribuire il pacchetto di configurazione nei dispositivi in modo che vengano onboarded to the Service.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769480"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili

**Si applica a:**

- [Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)

È possibile utilizzare soluzioni di gestione dispositivi mobili (MDM) per configurare i dispositivi. La prevenzione della perdita di dati di Microsoft 365 endpoint supporta MDMs fornendo OMA-URIs per la creazione di criteri per la gestione dei dispositivi.


## <a name="before-you-begin"></a>Prima di iniziare
Se si utilizza Microsoft Intune, è necessario che il dispositivo MDM sia registrato. In caso contrario, le impostazioni non verranno applicate correttamente. 

Per ulteriori informazioni sull'abilitazione di MDM con Microsoft Intune, vedere [dispositivo di registrazione (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Dispositivi di bordo tramite Microsoft Intune

Seguire le istruzioni di [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

> [!NOTE]
> - Lo **stato di integrità dei criteri per i dispositivi onboarded** utilizza proprietà di sola lettura e non può essere rimediato.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Trasferisce e monitorare i dispositivi tramite gli strumenti di gestione dei dispositivi mobili

Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato. I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando si scarica un pacchetto di Offboarding verrà inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.

1. Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com/).

2. Nel riquadro di spostamento, selezionare **Impostazioni**  >  **onboarding del dispositivo**  >  **offboarding** .

3. Nel campo **metodo di distribuzione** selezionare **Gestione dispositivi mobili/Microsoft Intune** .
    
4. Fare clic su **Download package** e salvare il file con estensione zip.

5. Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere gli amministratori di rete che distribuiscono il pacchetto. È necessario disporre di un file denominato *DeviceCompliance_valid_until_YYYY-mm-dd. offboarding* .

6. Utilizzare il criterio di configurazione personalizzato di Microsoft Intune per distribuire le seguenti impostazioni di URI OMA supportate.

      OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo di data: stringa      
      Valore: [copia e incolla il valore dal contenuto del file DeviceCompliance_valid_until_YYYY-MM-GG. offboarding]

Per ulteriori informazioni sulle impostazioni dei criteri di Microsoft Intune, vedere [impostazioni dei criteri di Windows 10 in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> Lo **stato di integrità dei criteri per i dispositivi di offboarded** utilizza proprietà di sola lettura e non può essere rimediato.

> [!IMPORTANT]
> Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale, ma i dati del dispositivo, incluso il riferimento agli avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

## <a name="related-topics"></a>Argomenti correlati
- [Dispositivi di bordo di Windows 10 con criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivi di bordo di Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo](dlp-configure-endpoints-vdi.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
