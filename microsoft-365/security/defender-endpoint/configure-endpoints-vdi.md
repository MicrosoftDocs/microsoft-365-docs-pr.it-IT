---
title: Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti
description: Distribuisci il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che siano onboarded nel servizio Microsoft Defender for Endpoint.
keywords: configurare il dispositivo VDI (Virtual Desktop Infrastructure), vdi, gestione dei dispositivi, configurare gli endpoint di Windows ATP, configurare Microsoft Defender per gli endpoint endpoint
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
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 1e970be7967e221c29017be804a98770a778654f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892794"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Dispositivi VDI (Virtual Desktop Infrastructure)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti

Defender for Endpoint supporta l'onboarding di sessioni VDI non persistenti. 


Quando si esegue l'onboarding di VDI, potrebbero verificarsi problemi associati. Di seguito sono riportate le sfide tipiche per questo scenario:

- Onboarding immediato di sessioni di breve durata, che devono essere onboarding in Defender for Endpoint prima del provisioning effettivo.
- Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.

I dispositivi VDI possono essere visualizzati in Defender for Endpoint Portal come:

- Voce singola per ogni dispositivo.

  > [!NOTE]
  > In questo caso, è *necessario* configurare lo stesso nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.

- Più voci per ogni dispositivo- una per ogni sessione.

I passaggi seguenti ti guideranno nell'onboarding dei dispositivi VDI e indicheranno i passaggi per una o più voci.

>[!WARNING]
> Per gli ambienti in cui le configurazioni delle risorse sono scarse, la procedura di avvio VDI potrebbe rallentare l'onboarding del sensore Defender for Endpoint. 


### <a name="for-windows-10-or-windows-server-2019"></a>Per Windows 10 o Windows Server 2019

1.  Aprire il file ZIP del pacchetto di configurazione VDI (*WindowsDefenderATPOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio. Puoi anche ottenere il pacchetto da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1.  Nel riquadro di spostamento selezionare **Impostazioni**  >  **Onboarding.**

    1. Seleziona Windows 10 come sistema operativo.

    1.  Nel campo **Metodo di** distribuzione selezionare Script **di onboarding VDI per gli endpoint non persistenti.**

    1. Fai **clic su Scarica** pacchetto e salva il file ZIP.

2. Copiare i file dalla cartella WindowsDefenderATPOnboardingPackage estratta dal file ZIP nell'immagine `golden/master` nel percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

    1. Se non stai implementando una singola voce per ogni dispositivo, copia WindowsDefenderATPOnboardingScript.cmd.

    1. Se stai implementando una singola voce per ogni dispositivo, copia sia Onboard-NonPersistentMachine.ps1 windowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Se la cartella non è `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` visualizzata, è possibile che sia nascosta. Dovrai scegliere l'opzione Mostra **cartelle e file** nascosti da Esplora file.

3. Aprire una finestra Editor Criteri di gruppo locali e passare a **Configurazione computer** Impostazioni di  >  **Windows Script**  >    >  **Avvio**.

   > [!NOTE]
   > I Criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non persistenti.

4. A seconda del metodo che vuoi implementare, segui la procedura appropriata:

   - Per una singola voce per ogni dispositivo:
   
     Seleziona la **scheda Script di PowerShell,** quindi fai clic su **Aggiungi** (Esplora risorse si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza). Passare a script di PowerShell di `Onboard-NonPersistentMachine.ps1` onboarding. Non è necessario specificare l'altro file, perché verrà attivato automaticamente.
   
   - Per più voci per ogni dispositivo:
   
     Seleziona la **scheda Script,** quindi fai clic su **Aggiungi** (Esplora risorse si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza). Passare allo script di onboarding bash `WindowsDefenderATPOnboardingScript.cmd` .

5. Testare la soluzione:

   1. Creare un pool con un solo dispositivo.
      
   1. Accesso al dispositivo.
      
   1. Disconnessione dal dispositivo.

   1. Accedere al dispositivo con un altro utente.
      
   1. A seconda del metodo che vuoi implementare, segui la procedura appropriata:
   
      - Per una singola voce per ogni dispositivo: 
    
        Controlla solo una voce in Microsoft Defender Security Center.

      - Per più voci per ogni dispositivo: 
       
        Controllare più voci in Microsoft Defender Security Center.

6. Fare **clic su Elenco** dispositivi nel riquadro di spostamento.

7. Usa la funzione di ricerca immettendo il nome del dispositivo e seleziona **Dispositivo** come tipo di ricerca.


## <a name="for-downlevel-skus"></a>Per SKU di livello inferiore

> [!NOTE]
> Il Registro di sistema seguente è rilevante solo quando l'obiettivo è quello di ottenere una "voce singola per ogni dispositivo".

1. Impostare il valore del Registro di sistema su:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    o utilizzando la riga di comando:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Seguire il [processo di onboarding del server](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016). 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Aggiornamento di immagini VDI (Virtual Desktop Infrastructure) non persistenti
Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare patch alle immagini golden/master.<br>
Ad esempio, puoi usare i comandi seguenti per installare un aggiornamento mentre l'immagine rimane offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Per ulteriori informazioni sui comandi di Gestione e manutenzione immagini distribuzione e sulla manutenzione offline, fare riferimento agli articoli seguenti:
- [Modificare un'immagine Windows con Gestione e manutenzione immagini distribuzione](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Gestione e manutenzione immagini distribuzione Command-Line opzioni](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:

1. Dopo aver avviato l'immagine master per la manutenzione online o l'applicazione di patch, esegui uno script di offboarding per disattivare il sensore Defender for Endpoint. Per altre informazioni, vedi [Offboard devices using a local script.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

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
- [Onboardare dispositivi Windows 10 con Criteri di gruppo](configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](configure-endpoints-mdm.md)
- [Onboarding di dispositivi Windows 10 con uno script locale](configure-endpoints-script.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
