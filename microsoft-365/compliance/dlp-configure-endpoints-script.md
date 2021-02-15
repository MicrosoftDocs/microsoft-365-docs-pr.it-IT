---
title: Onboarding di dispositivi Windows 10 con uno script locale
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
description: Usa uno script locale per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769470"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding di dispositivi Windows 10 con uno script locale

**Si applica a:**

- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

È inoltre possibile eseguire manualmente l'onboarder dei singoli dispositivi per la prevenzione della perdita di dati degli endpoint di Microsoft 365. È consigliabile eseguire questa operazione prima di testare il servizio prima di eseguire l'onboarding di tutti i dispositivi nella rete.

> [!IMPORTANT]
> Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.
>
> Per eseguire la distribuzione su larga scala, utilizzare [altre opzioni di distribuzione.](dlp-configure-endpoints.md) Ad esempio, puoi distribuire uno script di onboarding in più di 10 dispositivi in produzione con lo script disponibile nei dispositivi [Windows 10](dlp-configure-endpoints-gp.md)con Criteri di gruppo.

## <a name="onboard-devices"></a>Onboard dei dispositivi
 
1.  Apri il file ZIP del pacchetto di configurazione criteri *di gruppo*(DeviceComplianceOnboardingPackage.zip) che hai scaricato dall'onboarding guidato del servizio. È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del dispositivo.**

3. Nel campo **Metodo di distribuzione** selezionare Script **locale.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.
  
5. Estrai il contenuto del pacchetto di configurazione in una posizione nel dispositivo di cui vuoi eseguire l'onboarder (ad esempio, il desktop). Dovresti avere un file denominato *DeviceOnboardingScript.cmd.*

6.  Apri un prompt dei comandi con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

![Menu Start della finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

Per informazioni su come è possibile convalidare manualmente che il dispositivo sia conforme e segnala correttamente i dati del sensore, vedere Risolvere i problemi di [onboarding](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)di Microsoft Defender Advanced Threat Protection.

## <a name="offboard-devices-using-a-local-script"></a>Eseguire l'offboard dei dispositivi con uno script locale
Per motivi di sicurezza, il pacchetto usato per l'offboard dei dispositivi scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando scarii un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà conflitti imprevedibili.

1. Ottenere il pacchetto offboarding dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **offboarding dispositivo.**

3. Nel campo **Metodo di distribuzione** selezionare Script **locale.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrai il contenuto del file ZIP in una posizione condivisa di sola lettura accessibile dai dispositivi. Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

6.  Apri un prompt dei comandi con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

![Menu Start della finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-GG.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione dei dispositivi
È possibile seguire i diversi passaggi di verifica descritti in [Risolvere i problemi di onboarding]( per verificare che lo script sia stato completato correttamente e https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) che l'agente sia in esecuzione.

Il monitoraggio può essere eseguito anche direttamente nel portale o usando i diversi strumenti di distribuzione.

### <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare al [Centro conformità Microsoft 365.](https://compliance.microsoft.com)

2. Choose **Settings**  >  **Device onboarding**  >  **Devices.**

3. Verificare che i dispositivi siano visualizzati.


## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un dispositivo Microsoft Defender ATP appena onboarded](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
