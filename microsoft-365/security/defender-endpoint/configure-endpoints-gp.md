---
title: Onboard di dispositivi Windows 10 a Microsoft Defender for Endpoint tramite Criteri di gruppo
description: Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi Windows 10 in modo che siano onboarded nel servizio.
keywords: configurare i dispositivi usando Criteri di gruppo, gestione dei dispositivi, configurare i dispositivi Windows ATP, onboard microsoft defender per dispositivi endpoint, criteri di gruppo
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b839cf204e8ab042e0c88a8f8c48df79770e7b4f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893635"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboardare dispositivi Windows 10 con Criteri di gruppo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- Criteri di gruppo
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> Per usare gli aggiornamenti di Criteri di gruppo per distribuire il pacchetto, devi essere in Windows Server 2008 R2 o versione successiva.
> 
> Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di Criteri di gruppo.

## <a name="onboard-devices-using-group-policy"></a>Aggiungere dispositivi con Criteri di gruppo

[![Immagine del PDF che mostra i vari percorsi di distribuzione](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

Consultare il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per visualizzare i vari percorsi nella distribuzione di Defender per Endpoint. 



1. Aprire il file ZIP del pacchetto di configurazione criteri *di gruppo*(WindowsDefenderATPOnboardingPackage.zip) scaricato dall'onboarding guidato del servizio. Puoi anche ottenere il pacchetto da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)
 
    1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Onboarding.**

    1. Seleziona Windows 10 come sistema operativo.
    
    1. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**
    
    1. Fai **clic su Scarica** pacchetto e salva il file ZIP.

2. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere una cartella denominata *OptionalParamsPolicy* e il file *WindowsDefenderATPOnboardingScript.cmd.*

3. Aprire console [Gestione Criteri di](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

4. **Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** quindi **Preferenze** e quindi impostazioni del Pannello **di controllo.**

5. Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Attività immediata **(almeno Windows 7).**

6. Nella **finestra Attività** visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza** fare clic su Cambia utente o **gruppo** e digitare SISTEMA e quindi fare clic su **Controlla nomi** e quindi su **OK.** NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività.

7. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati.

8. Vai alla scheda **Azioni** e fai clic su **Nuovo...** Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione. Immettere il nome e il percorso del file *WindowsDefenderATPOnboardingScript.cmd* condiviso.

9. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

>[!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che il dispositivo sia stato correttamente onboarding nel servizio. Per altre informazioni, vedi Eseguire un test di rilevamento in un dispositivo [Defender per endpoint appena onboarded.](run-detection-test.md)

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Ulteriori impostazioni di configurazione di Defender per endpoint
Per ogni dispositivo, puoi indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per l'analisi approfondita.

È possibile utilizzare Criteri di gruppo per configurare le impostazioni, ad esempio le impostazioni per la condivisione di esempio utilizzata nella funzionalità di analisi approfondita.

### <a name="configure-sample-collection-settings"></a>Configurare le impostazioni della raccolta di esempio
1.  Nel dispositivo di gestione Criteri di gruppo copiare i file seguenti dal pacchetto di configurazione:

    - Copia _AtpConfiguration.admx_ in _C: \\ Windows \\ PolicyDefinitions_

    - Copia _AtpConfiguration.adml_ in _C: \\ Windows \\ PolicyDefinitions \\ en-US_

    Se si utilizza un [archivio centrale per i modelli](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)amministrativi di Criteri di gruppo, copiare i file seguenti dal pacchetto di configurazione:
    
    - Copiare _AtpConfiguration.admx_ in _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions_

    - Copiare _AtpConfiguration.adml_ in _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_

2.  Aprire la [Console Gestione Criteri di gruppo,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

5.  Fare **clic su** Componenti di Windows e quindi Windows Defender **ATP.**

6.  Scegli se abilitare o disabilitare la condivisione dei campioni dai dispositivi.

>[!NOTE]
> Se non si imposta un valore, il valore predefinito è abilitare la raccolta di esempi.


## <a name="other-recommended-configuration-settings"></a>Altre impostazioni di configurazione consigliate

### <a name="update-endpoint-protection-configuration"></a>Aggiornare la configurazione di endpoint protection

Dopo aver configurato lo script di onboarding, continuare a modificare gli stessi criteri di gruppo per aggiungere configurazioni di endpoint protection. Eseguire modifiche ai Criteri di gruppo da un sistema che esegue Windows 10 o Server 2019 per assicurarsi di disporre di tutte le funzionalità di Microsoft Defender Antivirus necessarie. Potrebbe essere necessario chiudere e riaprire l'oggetto Criteri di gruppo per registrare le impostazioni di configurazione di Defender ATP.

Tutti i criteri si trovano in `Computer Configuration\Policies\Administrative Templates` .

**Percorso dei criteri:** \Componenti di Windows\Windows Defender ATP

Criteri | Impostazione 
:---|:---
Enable\Disable Sample collection|   Enabled - "Enable sample collection on machines" checked

<br/>

**Percorso dei criteri:**  \Componenti di Windows\Windows Defender Antivirus

Criteri | Impostazione 
:---|:---
Configurare il rilevamento per applicazioni potenzialmente indesiderate | Enabled, Block

<br/>

**Percorso dei criteri:** \Componenti di Windows\Windows Defender Antivirus\MAPS

Criteri | Impostazione 
:---|:---
Partecipare a Microsoft MAPS | Enabled, Advanced MAPS
Inviare esempi di file quando è necessaria un'ulteriore analisi | Enabled, Send safe samples

<br/>

**Percorso dei criteri:** \Componenti di Windows\Windows Defender Antivirus\Protezione in tempo reale

Criteri | Impostazione 
:---|:---
Disattivare la protezione in tempo reale|Disabilitato
Attivare il monitoraggio del comportamento|Abilitato
Analizzare tutti i file e gli allegati scaricati|Abilitato
Monitorare le attività di file e programmi nel computer|Abilitato

<br/>

**Percorso dei criteri:**  \Componenti di Windows\Windows Defender Antivirus\Scan

Queste impostazioni configurano analisi periodiche dell'endpoint. È consigliabile eseguire un'analisi rapida settimanale, permettendo le prestazioni.

Criteri | Impostazione 
:---|:---
Prima di eseguire un'analisi pianificata, verificare la disponibilità delle informazioni di sicurezza più recenti su virus e spyware |Abilitato


<br/>

**Posizione dei criteri:** \Componenti di Windows\Windows Defender Antivirus\Windows Defender Exploit Guard\Riduzione della superficie di attacco

Ottenere l'elenco corrente dei GUID di riduzione della superficie di attacco da [Personalizzare le regole di riduzione della superficie di attacco](customize-attack-surface-reduction.md)

1. Apri il **criterio Configura riduzione superficie di** attacco.

1. Selezionare **Abilitato**.

1. Selezionare il **pulsante** Mostra.

1. Aggiungere ogni GUID nel **campo Nome valore** con un valore pari a 2.

   Questa impostazione verrà impostata solo per il controllo.

   ![Immagine della configurazione di riduzione della superficie di attacco](images/asr-guid.png)



Criteri | Impostazione 
:---|:---
Configurare l'accesso controllato alle cartelle| Abilitato, modalità di controllo



## <a name="offboard-devices-using-group-policy"></a>Dispositivi offboard con Criteri di gruppo
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Offboarding.**

    1. Seleziona Windows 10 come sistema operativo.
    
    1. Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**

    1. Fai **clic su Scarica** pacchetto e salva il file ZIP.

2. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere un file denominato *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Aprire console [Gestione Criteri di](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

4. **Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** Quindi **Preferenze** e quindi Impostazioni pannello **di controllo.**

5. Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Fare clic su **Attività immediata.**

6. Nella **finestra Attività** visualizzata passare alla **scheda** Generale. Scegliere l'account utente SYSTEM locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza**.

7. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la **casella** di controllo Esegui con privilegi più elevati.

8. Passare alla scheda **Azioni** e fare clic su **Nuovo...**. Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione. Immettere il nome e il percorso del file  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* condiviso.

9. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
Con Criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi. Il monitoraggio può essere eseguito direttamente nel portale o utilizzando i diversi strumenti di distribuzione.

## <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare a [Microsoft Defender Security Center](https://securitycenter.windows.com/).
2. Fare **clic su Elenco dispositivi**.
3. Verificare che i dispositivi siano visualizzati.

> [!NOTE]
> L'inizio della visualizzazione dei dispositivi nell'elenco Dispositivi può richiedere **diversi giorni.** Ciò include il tempo necessario per la distribuzione dei criteri al dispositivo, il tempo necessario prima che l'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.


## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](configure-endpoints-script.md)
- [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un Microsoft Defender per dispositivi endpoint appena onboarded](run-detection-test.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
