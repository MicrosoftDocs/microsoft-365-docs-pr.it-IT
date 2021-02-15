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
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769446"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboard dei dispositivi Windows 10 con Criteri di gruppo 

**Si applica a:**

- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Criteri di gruppo

> [!NOTE]
> Per usare gli aggiornamenti di Criteri di gruppo per distribuire il pacchetto, devi essere in Windows Server 2008 R2 o versione successiva.

> Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di Criteri di gruppo.

## <a name="onboard-devices-using-group-policy"></a>Onboard dei dispositivi con Criteri di gruppo

1. Apri il file ZIP del pacchetto di configurazione criteri *di gruppo*(DeviceComplianceOnboardingPackage.zip) che hai scaricato dall'onboarding guidato del servizio. È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del dispositivo.**

3. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrai il contenuto del file ZIP in una posizione condivisa di sola lettura accessibile dal dispositivo. Dovresti avere una cartella denominata *OptionalParamsPolicy* e il file *DeviceComplianceLocalOnboardingScript.cmd.*

6. Apri console [Gestione Criteri](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) di gruppo, fai clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che vuoi configurare e fai clic su **Modifica.**

7. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer,** preferenze **e** quindi impostazioni **del Pannello di controllo.**

8. Fare clic con **il pulsante destro del** mouse su Attività pianificate, scegliere Nuovo e quindi Attività immediata  **(almeno Windows 7).**

9. Nella finestra **attività** visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza fare** clic su Cambia utente o **gruppo** e digitare SISTEMA, quindi fare clic su **Controlla nomi** e quindi **su OK.** NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività.

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con i **privilegi** più elevati.

11. Vai alla scheda **Azioni** e fai clic su **Nuovo...** Verificare che **l'opzione Avvia** programma sia selezionata nel **campo** Azione. Immetti il nome e il percorso del file *WindowsDefenderATPOnboardingScript.cmd* condiviso.

12. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.


## <a name="offboard-devices-using-group-policy"></a>Offboard dei dispositivi con Criteri di gruppo
Per motivi di sicurezza, il pacchetto usato per l'offboard dei dispositivi scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando scarii un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà conflitti imprevedibili.

1. Ottenere il pacchetto offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Nel riquadro di spostamento seleziona **Impostazioni**  >  **//Onboarding dei** dispositivi  >  **Offboarding.**

3. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**

4. Fai **clic su Scarica** pacchetto e salva il file ZIP.

5. Estrai il contenuto del file ZIP in una posizione condivisa di sola lettura accessibile dal dispositivo. Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

6. Apri console [Gestione Criteri](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) di gruppo, fai clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che vuoi configurare e fai clic su **Modifica.**

7. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer,** **Preferenze** e quindi impostazioni **del Pannello di controllo.**

8. Fare clic con **il pulsante destro del mouse su** Attività pianificate, scegliere Nuovo e quindi Attività **immediata.** 

9. Nella finestra **attività** visualizzata passare alla **scheda** Generale. Scegliere l'account utente SYSTEM locale (BUILTIN\SYSTEM) in **Opzioni di protezione.**

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con i **privilegi** più elevati.

11. Passare alla scheda **Azioni** e fare clic su **Nuovo...**. Verificare che **l'opzione Avvia** programma sia selezionata nel **campo** Azione. Immettere il nome e il percorso del file *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-GG.cmd.*

12. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati dei sensori al portale, ma i dati dal dispositivo.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione dei dispositivi
Con Criteri di gruppo non esiste un'opzione per monitorare la distribuzione dei criteri nei dispositivi. Il monitoraggio può essere eseguito direttamente nel portale o usando i diversi strumenti di distribuzione.

## <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare al [Centro conformità Microsoft.](https://compliance.microsoft.com/)
2. Fai **clic sull'elenco** Dispositivi.
3. Verificare che i dispositivi siano visualizzati.

> [!NOTE]
> La visualizzazione dei dispositivi nell'elenco Dispositivi può richiedere **diversi giorni.** Ciò include il tempo necessario per la distribuzione dei criteri nel dispositivo, il tempo necessario prima che l'utente e il tempo necessario all'endpoint per avviare la creazione di report.


## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un nuovo dispositivo Microsoft Defender ATP onboarded](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
