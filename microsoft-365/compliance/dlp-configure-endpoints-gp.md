---
title: Onboarding di dispositivi Windows 10 tramite Criteri di gruppo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi Windows 10 in modo che siano onboarded nel servizio.
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918022"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboardare dispositivi Windows 10 con Criteri di gruppo 

**Si applica a:**

- [Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)](./endpoint-dlp-learn-about.md)
- Criteri di gruppo

> [!NOTE]
> Per usare gli aggiornamenti di Criteri di gruppo per distribuire il pacchetto, devi essere in Windows Server 2008 R2 o versione successiva.

> Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di Criteri di gruppo.

## <a name="onboard-devices-using-group-policy"></a>Onboardare i dispositivi con Criteri di gruppo

1. Aprire il file ZIP del pacchetto di configurazione criteri *di gruppo*(DeviceComplianceOnboardingPackage.zip) scaricato dall'onboarding guidato del servizio. È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **Onboarding dispositivo.**

3. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere una cartella denominata *OptionalParamsPolicy* e il file *DeviceComplianceLocalOnboardingScript.cmd.*

6. Aprire console [Gestione Criteri di](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

7. **Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** quindi **Preferenze** e quindi impostazioni del Pannello **di controllo.**

8. Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Attività immediata **(almeno Windows 7).**

9. Nella **finestra Attività** visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza** fare clic su Cambia utente o **gruppo** e digitare SISTEMA e quindi fare clic su **Controlla nomi** e quindi su **OK.** NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività.

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati.

11. Vai alla scheda **Azioni** e fai clic su **Nuovo...** Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione. Immettere il nome e il percorso del file *WindowsDefenderATPOnboardingScript.cmd* condiviso.

12. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.


## <a name="offboard-devices-using-group-policy"></a>Dispositivi offboard con Criteri di gruppo
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **//Onboarding del** dispositivo  >  **Offboarding.**

3. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Aprire console [Gestione Criteri di](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

7. **Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** Quindi **Preferenze** e quindi Impostazioni pannello **di controllo.**

8. Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Fare clic su **Attività immediata.**

9. Nella **finestra Attività** visualizzata passare alla **scheda** Generale. Scegliere l'account utente SYSTEM locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza**.

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la **casella** di controllo Esegui con privilegi più elevati.

11. Passare alla scheda **Azioni** e fare clic su **Nuovo...**. Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione. Immettere il nome e il percorso del file *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

12. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
Con Criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi. Il monitoraggio può essere eseguito direttamente nel portale o utilizzando i diversi strumenti di distribuzione.

## <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare al [Centro conformità Microsoft](https://compliance.microsoft.com/).
2. Fai clic **su Elenco** dispositivi.
3. Verificare che i dispositivi siano visualizzati.

> [!NOTE]
> L'inizio della visualizzazione dei dispositivi nell'elenco Dispositivi può richiedere **diversi giorni.** Ciò include il tempo necessario per la distribuzione dei criteri al dispositivo, il tempo necessario prima che l'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.


## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un nuovo dispositivo Microsoft Defender ATP onboarded](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)