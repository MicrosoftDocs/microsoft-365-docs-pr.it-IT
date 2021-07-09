---
title: Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
description: Usa gli strumenti di gestione dei dispositivi mobili per distribuire il pacchetto di configurazione nei dispositivi in modo che i dispositivi siano onboarded nel servizio.
keywords: onboard dei dispositivi con mdm, gestione dei dispositivi, onboard microsoft defender per dispositivi endpoint, mdm
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338578"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a>Onboardare i dispositivi Windows 10 usando gli strumenti di gestione dei dispositivi mobili

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi. Defender for Endpoint supporta gli MMM fornendo OMA-URIs creare criteri per gestire i dispositivi.

Per altre informazioni sull'uso di Defender per CSP endpoint, vedi [CSP WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e [File DDF di WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)

## <a name="before-you-begin"></a>Prima di iniziare
Se stai usando un Microsoft Intune, devi registrare il dispositivo MDM. In caso contrario, le impostazioni non verranno applicate correttamente. 

Per altre informazioni sull'abilitazione di MDM Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard dei dispositivi con Microsoft Intune

[![Immagine del PDF che mostra i dispositivi di onboarding in Defender for Endpoint usando Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Vedi il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) il [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per vedere i vari percorsi nella distribuzione di Defender per Endpoint. 

Seguire le istruzioni di [Intune](/intune/advanced-threat-protection).

Per altre informazioni sull'uso di Defender per CSP endpoint, vedi [CSP WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e [File DDF di WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.
> - La configurazione della frequenza di segnalazione dei dati di diagnostica è disponibile solo per i dispositivi Windows 10 versione 1703.


>[!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia stato correttamente onboarding nel servizio. Per altre informazioni, vedi [Eseguire un test di rilevamento su un dispositivo Microsoft Defender for Endpoint appena onboarded.](run-detection-test.md)


Consulta il [pdf o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) il [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per vedere i vari percorsi nella distribuzione di Microsoft Defender per Endpoint.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard e monitora i dispositivi con gli strumenti di gestione dei dispositivi mobili
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding [da Microsoft 365 Defender portale:](https://security.microsoft.com/)

   1. Nel riquadro di spostamento seleziona **Impostazioni**  >    >    >  **Offboarding** gestione dispositivi endpoint.

   1. Seleziona Windows 10 come sistema operativo.

   1. Nel campo **Metodo di distribuzione** selezionare Gestione dispositivi mobili / **Microsoft Intune**.
    
   1. Fai **clic su Scarica pacchetto** e salva il file .zip file.

2. Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto. Dovresti avere un file denominato *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.

3. Usa il Microsoft Intune di configurazione personalizzato per distribuire le seguenti impostazioni URI OMA supportate.

      URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Tipo di data: String<br/>
      Valore: [Copiare e incollare il valore dal contenuto del file WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Per ulteriori informazioni sulle Microsoft Intune dei criteri, vedere Windows 10 [impostazioni dei criteri in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).


> [!NOTE]
> Il **criterio Stato integrità per i dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

## <a name="related-topics"></a>Argomenti correlati
- [Onboardare Windows 10 dispositivi con Criteri di gruppo](configure-endpoints-gp.md)
- [Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](configure-endpoints-script.md)
- [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded](run-detection-test.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
