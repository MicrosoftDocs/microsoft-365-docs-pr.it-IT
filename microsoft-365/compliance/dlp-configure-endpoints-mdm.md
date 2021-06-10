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

- [Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)](./endpoint-dlp-learn-about.md)

Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi. Microsoft 365 La prevenzione della perdita dei dati degli endpoint supporta gli MMM fornendo OMA-URIs creare criteri per gestire i dispositivi.


## <a name="before-you-begin"></a>Prima di iniziare
Se stai usando un Microsoft Intune, devi registrare il dispositivo MDM. In caso contrario, le impostazioni non verranno applicate correttamente. 

Per altre informazioni sull'abilitazione di MDM Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard dei dispositivi con Microsoft Intune

Seguire le istruzioni di [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard e monitora i dispositivi con gli strumenti di gestione dei dispositivi mobili

Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del**  >  **dispositivo**.

3. Nel campo **Metodo di distribuzione** selezionare Gestione dispositivi mobili / **Microsoft Intune**.
    
4. Fai **clic su Scarica pacchetto** e salva il file .zip file.

5. Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto. Dovresti avere un file denominato *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Usa il Microsoft Intune di configurazione personalizzato per distribuire le seguenti impostazioni URI OMA supportate.

      URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo di data: String      
      Valore: [Copiare e incollare il valore dal contenuto del file DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Per ulteriori informazioni sulle Microsoft Intune dei criteri, vedere Windows 10 [impostazioni dei criteri in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> Il **criterio Stato integrità per i dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

## <a name="related-topics"></a>Argomenti correlati
- [Onboardare Windows 10 dispositivi con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Risolvere i Microsoft Defender Advanced Threat Protection di onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)