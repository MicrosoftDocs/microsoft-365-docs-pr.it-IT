---
title: Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti
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
description: Distribuisci il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che siano onboarded nel servizio di prevenzione della perdita dei dati Microsoft 365 Endpoint.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226876"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti

**Si applica a:**
- [Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)](./endpoint-dlp-learn-about.md)

- Dispositivi VDI (Virtual Desktop Infrastructure)

> [!WARNING]
> Microsoft 365 Il supporto per la prevenzione della perdita dei dati degli endpoint Windows desktop virtuale supporta scenari a sessione singola. Gli scenari multi-sessione Windows desktop virtuale non sono attualmente supportati.

## <a name="onboard-vdi-devices"></a>Onboard dei dispositivi VDI

Microsoft 365 La prevenzione della perdita dei dati degli endpoint supporta l'onboarding di sessioni VDI non persistenti.

> [!NOTE]
> Per eseguire l'onboarding di sessioni VDI non persistenti, i dispositivi VDI devono essere Windows 10 1809 o versioni successive.

Quando si esegue l'onboarding di VDI, potrebbero verificarsi problemi associati. Di seguito sono riportate le sfide tipiche per questo scenario:

- Onboarding immediato di sessioni di breve durata, che devono essere onboarding Microsoft 365 prevenzione della perdita di dati dell'endpoint prima del provisioning effettivo.
- Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.

I dispositivi VDI possono essere visualizzati nel Centro Microsoft 365 conformità come uno dei seguenti:

- Voce singola per ogni dispositivo.
Si noti che in  questo caso, è necessario configurare lo stesso nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.
- Più voci per ogni dispositivo- una per ogni sessione.

I passaggi seguenti ti guideranno nell'onboarding dei dispositivi VDI e indicheranno i passaggi per una o più voci.

> [!WARNING]
> Per gli ambienti in cui le configurazioni delle risorse sono scarse, la procedura di avvio VDI potrebbe rallentare l'onboarding Microsoft 365 di prevenzione della perdita di dati dell'endpoint.

1. Apri il pacchetto di configurazione VDI .zip file (*DeviceCompliancePackage.zip*) scaricato dall'onboarding guidato del servizio.

2. Nel riquadro di spostamento seleziona **Impostazioni**  >    >  **onboarding del dispositivo.**

3. Nel campo **Metodo di** distribuzione selezionare Script **di onboarding VDI per gli endpoint non persistenti.**

4. Fai **clic su Scarica pacchetto** e salva il file .zip file.

5. Copiare i file dalla cartella DeviceCompliancePackage estratta dal file .zip `golden/master` nell'immagine nel percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .

6. Se non stai implementando una singola voce per ogni dispositivo, copia DeviceComplianceOnboardingScript.cmd.

7. Se stai implementando una singola voce per ogni dispositivo, copia sia Onboard-NonPersistentMachine.ps1 che DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Se la cartella non è `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` visualizzata, è possibile che sia nascosta. Dovrai scegliere l'opzione Mostra **cartelle e file** nascosti da Esplora file.

8. Aprire una finestra Editor Criteri di gruppo locali e passare a **Configurazione computer**  >  **Windows Impostazioni**  >  **Script di**  >  **avvio**.

   > [!NOTE]
   > I Criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non persistenti.

9. A seconda del metodo che vuoi implementare, segui la procedura appropriata:

   **Per una singola voce per ogni dispositivo**

   Selezionare la **scheda Script di PowerShell,** quindi fare clic **su** Aggiungi (Windows Explorer si aprirà direttamente nel percorso in cui è stato copiato lo script di onboarding in precedenza). Passare a script di PowerShell di `Onboard-NonPersistentMachine.ps1` onboarding.

   **Per più voci per ogni dispositivo:**

   Seleziona la **scheda Script,** quindi fai clic su **Aggiungi** (Windows Explorer si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza). Passare allo script di onboarding bash `DeviceComplianceOnboardingScript.cmd` .

10. Testare la soluzione:
    1. Creare un pool con un solo dispositivo.
    1. Accesso al dispositivo.
    1. Disconnessione dal dispositivo.
    1. Accedere al dispositivo con un altro utente.
    1. **Per una singola voce per ogni dispositivo:** controlla solo una voce in Microsoft Defender Security Center.
       **Per più voci per ogni dispositivo**: Controllare più voci in Microsoft Defender Security Center.

11. Fare **clic su Elenco** dispositivi nel riquadro di spostamento.

12. Usa la funzione di ricerca immettendo il nome del dispositivo e seleziona **Dispositivo** come tipo di ricerca.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aggiornamento di immagini VDI (Virtual Desktop Infrastructure) non persistenti

Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare patch alle immagini golden/master.

Ad esempio, puoi usare i comandi seguenti per installare un aggiornamento mentre l'immagine rimane offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Per ulteriori informazioni sui comandi di Gestione e manutenzione immagini distribuzione e sulla manutenzione offline, fare riferimento agli articoli seguenti:

- [Modificare un'Windows immagine con Gestione e manutenzione immagini distribuzione](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Gestione e manutenzione immagini distribuzione Command-Line opzioni](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:

1. Dopo aver avviato l'immagine master per la manutenzione online o l'applicazione di patch, eseguire uno script di offboarding per disattivare il sensore di prevenzione della perdita dei dati Microsoft 365 endpoint. Per altre informazioni, vedi [Offboard devices using a local script.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Assicurati che il sensore sia arrestato eseguendo il comando seguente in una finestra CMD:

   ```console
   sc query sense
   ```

3. Utilizzare l'immagine in base alle esigenze.

4. Esegui i comandi seguenti usando PsExec.exe (che può essere scaricato da per pulire il contenuto della cartella cyber che il sensore potrebbe aver https://download.sysinternals.com/files/PSTools.zip) accumulato dopo l'avvio:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Re-seal the golden/master image as you normally would.

## <a name="related-topics"></a>Argomenti correlati

- [Onboardare Windows 10 dispositivi con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
