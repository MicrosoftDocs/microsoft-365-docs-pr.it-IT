---
title: Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo
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
description: Distribuire il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che sia onboarded to the Microsoft 365 Endpoint Data Loss Prevention Service.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769453"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo

**Si applica a:**
- [Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivi VDI (Virtual Desktop Infrastructure)

>[!WARNING]
> Supporto per la prevenzione della perdita di dati di Microsoft 365 endpoint per Windows Virtual Desktop supporta scenari di sessione singola. Gli scenari a più sessioni su desktop virtuale di Windows non sono attualmente supportati.

## <a name="onboard-vdi-devices"></a>Dispositivi VDI onboard

La prevenzione della perdita di dati di Microsoft 365 endpoint supporta l'onboarding delle sessioni VDI non permanenti. 

>[!Note]
>Per l'onboarding delle sessioni VDI non permanenti, i dispositivi VDI devono essere su Windows 10 1809 o versione successiva.

Potrebbero verificarsi problemi associati all'onboarding di VDIs. Di seguito sono riportate le sfide tipiche di questo scenario:

- Instant Early onboarding di una sessione di breve durata, che deve essere onboarded to Microsoft 365 endpoint prevenzione della perdita di dati prima del provisioning effettivo.
- Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.

I dispositivi VDI possono essere visualizzati nel centro conformità di Microsoft 365 come indicato di seguito:

- Voce singola per ogni dispositivo.  
Tenere presente che, in questo caso, è necessario configurare lo *stesso* nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.
- Più voci per ogni dispositivo-uno per ogni sessione.

Nei passaggi seguenti viene illustrato come eseguire l'onboarding dei dispositivi VDI e vengono evidenziati i passaggi per le voci singole e multiple.

>[!WARNING]
> Per gli ambienti in cui sono presenti configurazioni di risorse insufficienti, la procedura di avvio VDI potrebbe rallentare l'onboarding di prevenzione della perdita di dati di Microsoft 365 endpoint. 

1.  Aprire il file con estensione zip del pacchetto di configurazione VDI ( *DeviceCompliancePackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi.

2.  Nel riquadro di spostamento selezionare impostazioni onboarding del dispositivo di **configurazione**  >  **Device onboarding**  >  **Onboarding** .

3. Nel campo **metodo di distribuzione** selezionare gli **script di onboarding VDI per gli endpoint non permanenti** .

5. Fare clic su **Download package** e salvare il file con estensione zip.

6. Copiare i file dalla cartella DeviceCompliancePackage estratta dal file con estensione zip nell' `golden/master` immagine sotto il percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Se non si sta implementando una singola voce per ogni dispositivo, copiare DeviceComplianceOnboardingScript. cmd.

8. Se si sta implementando una singola voce per ogni dispositivo, copiare sia Onboard-NonPersistentMachine.ps1 che DeviceComplianceOnboardingScript. cmd.
    
    > [!NOTE]
    > Se la cartella non viene visualizzata `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , potrebbe essere nascosta. È necessario scegliere l'opzione **Mostra file nascosti e cartelle** da Esplora file.

9. Aprire una finestra dell'Editor criteri di gruppo locali e **Computer Configuration** passare all'  >  **avvio delle impostazioni di Windows** per la configurazione del computer  >  **Scripts**  >  **Startup** .

   > [!NOTE]
   > I criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non permanenti.

4. A seconda del metodo che si desidera implementare, attenersi alla procedura appropriata:

   **Per voce singola per ogni dispositivo**
   
   Selezionare la scheda **script di PowerShell** , quindi fare clic su **Aggiungi** (Esplora risorse verrà aperto direttamente nel percorso in cui è stato copiato lo script di onboarding precedente). Passare allo script di PowerShell onboarding `Onboard-NonPersistentMachine.ps1` .
   
   **Per più voci per ogni dispositivo** :
   
   Selezionare la scheda **script** , quindi fare clic su **Aggiungi** (Esplora risorse verrà aperto direttamente nel percorso in cui è stato copiato lo script di onboarding precedente). Passare allo script bash onboarding `DeviceComplianceOnboardingScript.cmd` .

5. Testare la soluzione:

   1. Creare un pool con un solo dispositivo.
      
   1. Accesso al dispositivo.
      
   1. Disconnessione dal dispositivo.

   1. Accedere al dispositivo con un altro utente.
      
   1. **Per voce singola per ogni dispositivo** : selezionare una sola voce in Microsoft Defender Security Center.<br>
      **Per più voci per ogni dispositivo** : selezionare più voci in Microsoft Defender Security Center.

6. Fare clic su **elenco dispositivi** nel riquadro di spostamento.

7. Utilizzare la funzione di ricerca digitando il nome del dispositivo e selezionando **dispositivo** come tipo di ricerca.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aggiornamento delle immagini VDI (Virtual Desktop Infrastructure) non permanenti
Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare la patch alle immagini Golden/Master.<br>
Ad esempio, è possibile utilizzare i comandi riportati di seguito per installare un aggiornamento quando l'immagine rimane offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Per ulteriori informazioni sui comandi DISM e la manutenzione offline, vedere gli articoli seguenti:
- [Modificare un'immagine di Windows tramite DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opzioni di gestione immagini DISM Command-Line](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:

1. Dopo l'avvio dell'immagine master per la manutenzione o l'applicazione di patch online, eseguire uno script di Offboarding per disattivare il sensore di prevenzione della perdita di dati di Microsoft 365 endpoint. Per ulteriori informazioni, vedere [dispositivi di trasferisce che utilizzano uno script locale](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Verificare che il sensore sia interrotto eseguendo il comando seguente in una finestra CMD:

   ```console
   sc query sense
   ```

3. Service l'immagine in base alle esigenze.

4. Eseguire i comandi riportati di seguito utilizzando PsExec.exe (che può essere scaricato da https://download.sysinternals.com/files/PSTools.zip) per pulire il contenuto della cartella Cyber che potrebbe essere stato accumulato dal sensore dopo l'avvio:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Ri-Seal l'immagine Golden/Master come si farebbe normalmente.

## <a name="related-topics"></a>Argomenti correlati
- [Dispositivi di bordo di Windows 10 con criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Dispositivi di bordo di Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
