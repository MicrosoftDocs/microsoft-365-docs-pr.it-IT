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
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843447"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding di dispositivi Windows 10 con uno script locale

**Si applica a:**

- [Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)](./endpoint-dlp-learn-about.md)

Puoi anche eseguire manualmente l'onboardboard dei singoli dispositivi per Microsoft 365 prevenzione della perdita dei dati dell'endpoint. È consigliabile eseguire questa operazione prima di testare il servizio prima di eseguire l'onboarding di tutti i dispositivi della rete.

> [!IMPORTANT]
> Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.
>
> Per eseguire la distribuzione su larga scala, [utilizzare altre opzioni di distribuzione.](dlp-configure-endpoints.md) Ad esempio, puoi distribuire uno script di onboarding in più di 10 dispositivi in produzione con lo script disponibile in Onboard Windows 10 dispositivi usando [Criteri di gruppo.](dlp-configure-endpoints-gp.md)

## <a name="onboard-devices"></a>Eseguire l'onboarding dei dispositivi
 
1.  Aprire il file del pacchetto .zip criteri di gruppo (*DeviceComplianceOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio. È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del dispositivo**.

3. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

4. Fai **clic su Scarica pacchetto** e salva il file .zip file.
  
5. Estrai il contenuto del pacchetto di configurazione in una posizione nel dispositivo che vuoi eseguire l'onboard(ad esempio, desktop). Dovresti avere un file denominato *DeviceOnboardingScript.cmd.*

6.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

    ![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

Per informazioni su come è possibile convalidare manualmente che il dispositivo sia conforme e che i dati del sensore vengano correttamente segnalati, vedere Risoluzione dei Microsoft Defender Advanced Threat Protection problemi di [onboarding.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

## <a name="offboard-devices-using-a-local-script"></a>Dispositivi offboard con uno script locale
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft](https://compliance.microsoft.com)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **offboarding del dispositivo.**

3. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

4. Fai **clic su Scarica pacchetto** e salva il file .zip file.

5. Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dai dispositivi. Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

7.  Passare a **Start** e digitare **cmd**.

8.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

    ![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Premere INVIO **o** fare clic su **OK.**

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
Puoi seguire i diversi passaggi di verifica in [Risolvere i problemi di onboarding]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) per verificare che lo script sia stato completato correttamente e che l'agente sia in esecuzione.

Il monitoraggio può essere eseguito anche direttamente nel portale o utilizzando i diversi strumenti di distribuzione.

### <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Vai a [Microsoft 365 conformità](https://compliance.microsoft.com).

2. Scegliere **Impostazioni**  >  **dispositivi di onboarding del**  >  **dispositivo**.

3. Verificare che i dispositivi siano visualizzati.


## <a name="related-topics"></a>Argomenti correlati
- [Onboardare Windows 10 dispositivi con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i Microsoft Defender Advanced Threat Protection di onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)