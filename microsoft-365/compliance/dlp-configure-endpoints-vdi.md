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
description: Distribuire il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che siano onboarded nel servizio di prevenzione della perdita dei dati degli endpoint di Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769453"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti

**Si applica a:**
- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivi VDI (Virtual Desktop Infrastructure)

>[!WARNING]
> Il supporto per la prevenzione della perdita dei dati degli endpoint di Microsoft 365 per Desktop virtuale Windows supporta scenari a sessione singola. Gli scenari con più sessioni in Desktop virtuale Windows non sono attualmente supportati.

## <a name="onboard-vdi-devices"></a>Onboard dei dispositivi VDI

La prevenzione della perdita dei dati degli endpoint di Microsoft 365 supporta l'onboarding di sessioni VDI non persistenti. 

>[!Note]
>Per eseguire l'onboarding di sessioni VDI non persistenti, i dispositivi VDI devono essere in Windows 10 1809 o versione successiva.

Durante l'onboarding di VDI potrebbero verificarsi problemi associati. Di seguito sono riportate alcune problematiche tipiche per questo scenario:

- Onboarding immediato anticipato di sessioni di breve durata, che devono essere onboarding nella prevenzione della perdita di dati degli endpoint di Microsoft 365 prima del provisioning effettivo.
- Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.

I dispositivi VDI possono essere visualizzati nel Centro conformità Microsoft 365 come:

- Voce singola per ogni dispositivo.  
In questo caso, è necessario configurare *lo* stesso nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposte automatico.
- Più voci per ogni dispositivo: una per ogni sessione.

La procedura seguente ti guiderà attraverso l'onboarding dei dispositivi VDI ed evidenzia i passaggi per una o più voci.

>[!WARNING]
> Per gli ambienti in cui le configurazioni delle risorse sono basse, la procedura di avvio VDI potrebbe rallentare l'onboarding della prevenzione della perdita di dati degli endpoint di Microsoft 365. 

1.  Apri il file ZIP del pacchetto di configurazione VDI (*DeviceCompliancePackage.zip*) che hai scaricato dall'onboarding guidato del servizio.

2.  Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding** del  >  dispositivo.

3. Nel campo **Metodo di distribuzione** selezionare gli script di **onboarding VDI per gli endpoint non persistenti.**

5. Fai **clic su Scarica** pacchetto e salva il file ZIP.

6. Copia i file dalla cartella DeviceCompliancePackage estratta dal file ZIP `golden/master` nell'immagine nel `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` percorso. 

7. Se non stai implementando una singola voce per ogni dispositivo, copia DeviceComplianceOnboardingScript.cmd.

8. Se stai implementando una singola voce per ogni dispositivo, copia sia Onboard-NonPersistentMachine.ps1 che DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Se la cartella non è `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` visualizzata, potrebbe essere nascosta. Dovrai scegliere l'opzione Mostra cartelle e **file** nascosti da Esplora file.

9. Apri una finestra dell'Editor Criteri di gruppo locali e passa a **Configurazione computer**- Avvio script  >  **impostazioni di**  >    >  **Windows.**

   > [!NOTE]
   > I Criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non persistenti.

4. A seconda del metodo che si desidera implementare, seguire la procedura appropriata:

   **Per una singola voce per ogni dispositivo**
   
   Selezionare la **scheda PowerShell Scripts,** quindi fare clic su **Add** (Esplora risorse si aprirà direttamente nel percorso in cui è stato copiato lo script di onboarding in precedenza). Passare allo script di PowerShell di `Onboard-NonPersistentMachine.ps1` onboarding.
   
   **Per più voci per ogni dispositivo:**
   
   Seleziona la **scheda Script,** quindi fai clic su **Aggiungi** (Esplora risorse si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza). Passa allo script di onboarding `DeviceComplianceOnboardingScript.cmd` bash.

5. Testare la soluzione:

   1. Creare un pool con un solo dispositivo.
      
   1. Accesso al dispositivo.
      
   1. Disconnessione dal dispositivo.

   1. Accedere al dispositivo con un altro utente.
      
   1. **Per una singola voce per ogni dispositivo:** controlla solo una voce in Microsoft Defender Security Center.<br>
      **Per più voci per ogni dispositivo:** controllare più voci in Microsoft Defender Security Center.

6. Fare **clic sull'elenco** Dispositivi nel riquadro di spostamento.

7. Usa la funzione di ricerca immettendo il nome del dispositivo e seleziona **Dispositivo** come tipo di ricerca.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aggiornamento di immagini VDI (Virtual Desktop Infrastructure) non persistenti
Come procedura consigliata, è consigliabile usare gli strumenti di manutenzione offline per applicare patch alle immagini golden/master.<br>
Ad esempio, puoi usare i comandi seguenti per installare un aggiornamento mentre l'immagine rimane offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Per altre informazioni sui comandi di Gestione e manutenzione immagini distribuzione e sulla manutenzione offline, fai riferimento agli articoli seguenti:
- [Modificare un'immagine Windows con Gestione e manutenzione immagini distribuzione](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opzioni Command-Line gestione immagini di Gestione e manutenzione immagini distribuzione](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se la manutenzione offline non è un'opzione praticabile per l'ambiente VDI non permanente, è necessario eseguire la procedura seguente per garantire la coerenza e l'integrità dei sensori:

1. Dopo aver avviato l'immagine master per la manutenzione online o l'applicazione di patch, eseguire uno script di offboarding per disattivare il sensore di prevenzione della perdita di dati degli endpoint di Microsoft 365. Per altre informazioni, vedi [Eseguire l'offboard dei dispositivi usando uno script locale.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

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

5. Ri-sigillare l'immagine master/d'oro come faresti normalmente.

## <a name="related-topics"></a>Argomenti correlati
- [Onboard dei dispositivi Windows 10 con Criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
