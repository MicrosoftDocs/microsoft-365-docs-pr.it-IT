---
title: Dispositivi di bordo di Windows 10 tramite criteri di gruppo
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
description: Utilizzare criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi Windows 10 in modo che siano onboarded to the Service.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769446"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Dispositivi di bordo di Windows 10 con criteri di gruppo 

**Si applica a:**

- [Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Criteri di gruppo

> [!NOTE]
> Per utilizzare gli aggiornamenti di criteri di gruppo per distribuire il pacchetto, è necessario essere su Windows Server 2008 R2 o versione successiva.

> Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di criteri di gruppo.

## <a name="onboard-devices-using-group-policy"></a>Dispositivi di bordo che utilizzano criteri di gruppo

1. Aprire il file con estensione zip del pacchetto di configurazione GP ( *DeviceComplianceOnboardingPackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi. È anche possibile ottenere il pacchetto dal [centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Nel riquadro di spostamento, selezionare **Settings**  >  **onboarding del dispositivo** di impostazioni.

3. Nel campo **metodo di distribuzione** selezionare **criteri di gruppo** .

4. Fare clic su **Download package** e salvare il file con estensione zip.

5. Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere dal dispositivo. È necessario disporre di una cartella denominata *OptionalParamsPolicy* e del file *DeviceComplianceLocalOnboardingScript. cmd* .

6. Aprire la [console Gestione criteri di gruppo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **modifica** .

7. In **Editor gestione criteri di gruppo** andare a **Configurazione computer** , quindi **Preferenze** e quindi impostazioni del **Pannello di controllo** .

8. Fare clic con il pulsante destro del mouse su **attività pianificate** , scegliere **nuovo** e quindi fare clic su **attività immediata (almeno Windows 7)** .

9. Nella finestra **attività** visualizzata passare alla scheda **generale** . In **Opzioni di sicurezza** fare clic su **Cambia utente o gruppo** e digitare sistema e quindi fare clic su **Controlla nomi** e quindi su **OK** . NT AUTHORITY\SYSTEM viene visualizzato come account utente in cui verrà eseguita l'attività.

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella **di controllo Esegui con i privilegi più alti** .

11. Passare alla scheda **azioni** e fare clic su **nuovo...** Verificare che sia selezionata l'opzione **avvia un programma** nel campo **azione** . Immettere il nome del file e il percorso del file *WindowsDefenderATPOnboardingScript. cmd* condiviso.

12. Fare clic su **OK** e chiudere tutte le finestre aperte di GPMC.


## <a name="offboard-devices-using-group-policy"></a>Dispositivi di trasferisce che utilizzano criteri di gruppo
Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato. I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando si scarica un pacchetto di Offboarding verrà inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.

1. Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. Nel riquadro di spostamento, selezionare **Impostazioni**  >  **//Device onboarding**  >  **offboarding** .

3. Nel campo **metodo di distribuzione** selezionare **criteri di gruppo** .

4. Fare clic su **Download package** e salvare il file con estensione zip.

5. Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere dal dispositivo. È necessario disporre di un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

6. Aprire la [console Gestione criteri di gruppo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **modifica** .

7. In **Editor gestione criteri di gruppo** andare a **Configurazione computer,** quindi **Preferenze** e quindi impostazioni del **Pannello di controllo** .

8. Fare clic con il pulsante destro del mouse su **attività pianificate** , scegliere **nuovo** e quindi fare clic su **attività immediata** .

9. Nella finestra **attività** visualizzata passare alla scheda **generale** . Scegliere l'account utente del sistema locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza** .

10. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella **di controllo Esegui con i privilegi più alti** .

11. Passare alla scheda **azioni** e fare clic su **nuovo...** . Verificare che sia selezionata l'opzione **avvia un programma** nel campo **azione** . Immettere il nome del file e il percorso del file di  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* condiviso.

12. Fare clic su **OK** e chiudere tutte le finestre aperte di GPMC.

> [!IMPORTANT]
> Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale, ma i dati del dispositivo.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
Con criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi. Il monitoraggio può essere effettuato direttamente sul portale oppure tramite gli strumenti di distribuzione diversi.

## <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Accedere al [centro conformità Microsoft](https://compliance.microsoft.com/).
2. Fare clic su elenco **dispositivi** .
3. Verificare che i dispositivi vengano visualizzati.

> [!NOTE]
> È possibile che i dispositivi vengano visualizzati alcuni giorni nell' **elenco dispositivi** . Questo include il tempo necessario per la distribuzione dei criteri nel dispositivo, il tempo necessario per l'accesso dell'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.


## <a name="related-topics"></a>Argomenti correlati
- [Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Dispositivi di bordo di Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
