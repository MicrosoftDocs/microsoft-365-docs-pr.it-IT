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
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917972"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding di dispositivi Windows 10 con uno script locale

**Si applica a:**

- [Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)](./endpoint-dlp-learn-about.md)

Puoi anche eseguire manualmente l'onboard di singoli dispositivi per la prevenzione della perdita di dati di Microsoft 365 Endpoint. È consigliabile eseguire questa operazione prima di testare il servizio prima di eseguire l'onboarding di tutti i dispositivi della rete.

> [!IMPORTANT]
> Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.
>
> Per eseguire la distribuzione su larga scala, [utilizzare altre opzioni di distribuzione.](dlp-configure-endpoints.md) Ad esempio, puoi distribuire uno script di onboarding a più di 10 dispositivi in produzione con lo script disponibile nei dispositivi [Windows 10](dlp-configure-endpoints-gp.md)con Criteri di gruppo.

## <a name="onboard-devices"></a>Dispositivi onboard
 
1.  Aprire il file ZIP del pacchetto di configurazione criteri *di gruppo*(DeviceComplianceOnboardingPackage.zip) scaricato dall'onboarding guidato del servizio. È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **Onboarding dispositivo.**

3. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.
  
5. Estrai il contenuto del pacchetto di configurazione in una posizione nel dispositivo che vuoi eseguire l'onboard(ad esempio, desktop). Dovresti avere un file denominato *DeviceOnboardingScript.cmd.*

6.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

Per informazioni su come è possibile verificare manualmente che il dispositivo sia conforme e che i dati del sensore vengano correttamente segnalati, vedere Risoluzione dei problemi di [onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)di Microsoft Defender Advanced Threat Protection.

## <a name="offboard-devices-using-a-local-script"></a>Dispositivi offboard con uno script locale
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **Offboarding dispositivo.**

3. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dai dispositivi. Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
Puoi seguire i diversi passaggi di verifica in [Risolvere i problemi di onboarding](( per verificare che lo script sia stato completato correttamente e https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) che l'agente sia in esecuzione.

Il monitoraggio può essere eseguito anche direttamente nel portale o utilizzando i diversi strumenti di distribuzione.

### <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare al [Centro conformità Microsoft 365](https://compliance.microsoft.com).

2. Scegliere **Impostazioni**  >  **Dispositivi di onboarding dei**  >  **dispositivi**.

3. Verificare che i dispositivi siano visualizzati.


## <a name="related-topics"></a>Argomenti correlati
- [Onboardare dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un dispositivo Microsoft Defender ATP appena onboarded](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)