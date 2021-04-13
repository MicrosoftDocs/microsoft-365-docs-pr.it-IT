---
title: Configurare i criteri di Microsoft Defender ATP per macOS in Jamf Pro
description: Scopri come configurare i criteri di Microsoft Defender ATP per macOS in Jamf Pro
keywords: criteri, microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b00d81d3d51c343565ec4eb743181baa2750b01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687734"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Configurare i criteri di Microsoft Defender for Endpoint su macOS in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md)

Questa pagina illustra i passaggi da eseguire per configurare i criteri macOS in Jamf Pro.

Dovrai eseguire la procedura seguente:

1. [Ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Configurare le impostazioni di Microsoft Defender per endpoint](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Configurare le impostazioni di notifica di Microsoft Defender per endpoint](#step-4-configure-notifications-settings)

5. [Configurare Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Concedere l'accesso completo al disco a Microsoft Defender per Endpoint](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Approvare l'estensione kernel per Microsoft Defender for Endpoint](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Approvare le estensioni di sistema per Microsoft Defender per Endpoint](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Configurare l'estensione di rete](#step-9-configure-network-extension)

10. [Pianificare le analisi con Microsoft Defender per Endpoint in macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Distribuire Microsoft Defender per Endpoint in macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Passaggio 1: ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint

1. In [Microsoft Defender Security Center](https://securitycenter.microsoft.com )passare a Impostazioni > **Onboarding.** 

2. Seleziona macOS come sistema operativo e Gestione dispositivi mobili/ Microsoft Intune come metodo di distribuzione.

    ![Immagine di Microsoft Defender Security Center](images/onboarding-macos.png)

3. Seleziona **Scarica pacchetto di onboarding** (WindowsDefenderATPOnboardingPackage.zip).

4. `WindowsDefenderATPOnboardingPackage.zip`Estrai .

5. Copiare il file nella posizione preferita. Ad esempio,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Passaggio 2: Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding

1. Individuare il file `WindowsDefenderATPOnboarding.plist` della sezione precedente.

   ![Immagine del file WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. Nel dashboard di Jamf Pro seleziona **Nuovo**.

    ![Immagine della creazione di un nuovo dashboard jamf pro](images/jamf-pro-configure-profile.png)

3. Immettere i dettagli seguenti:

   **Generale**
   - Nome: onboarding MDATP per macOS
   - Descrizione: onboarding edR MDATP per macOS
   - Categoria: Nessuno
   - Metodo di distribuzione: installazione automatica
   - Livello: Livello computer

4. In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.

    ![Immagine dell'app configurata e delle impostazioni personalizzate](images/jamfpro-mac-profile.png)

5. Seleziona **Carica file (file PLIST),** quindi in **Dominio preferenza** immetti: `com.microsoft.wdav.atp` . 

    ![Immagine del file di caricamento jamfpro plist](images/jamfpro-plist-upload.png)

    ![Immagine del file di elenco delle proprietà del file di caricamento](images/jamfpro-plist-file.png)

7. Selezionare **Apri** e selezionare il file di onboarding.

    ![Immagine del file di onboarding](images/jamfpro-plist-file-onboard.png)

8. Selezionare **Carica**. 

    ![Immagine del caricamento del file plist](images/jamfpro-upload-plist.png)


9. Selezionare la **scheda** Ambito.

    ![Scheda Immagine dell'ambito](images/jamfpro-scope-tab.png)

10. Selezionare i computer di destinazione.

    ![Immagine dei computer di destinazione](images/jamfpro-target-computer.png)

    ![Immagine delle destinazioni](images/jamfpro-targets.png) 

11. Selezionare **Salva**.

    ![Immagine dei computer di destinazione della distribuzione](images/jamfpro-deployment-target.png)

    ![Immagine dei computer di destinazione selezionati](images/jamfpro-target-selected.png)

12. Scegliere **Fatto**.

    ![Immagine dei computer del gruppo di destinazione](images/jamfpro-target-group.png)

    ![Elenco dei profili di configurazione](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Passaggio 3: Configurare Le impostazioni di Microsoft Defender per endpoint

1.  Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:

    - enableRealTimeProtection
    - passiveMode
    
    >[!NOTE]
    >Non attivato per impostazione predefinita, se si prevede di eseguire un av di terze parti per macOS, impostarlo su `true` .

    - esclusioni
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats
    
    >[!NOTE]
    >EICAR è nell'esempio, se si sta passando attraverso un modello di prova, rimuoverlo soprattutto se si sta testando EICAR.
        
    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tag
    - hideStatusMenuIcon
    
     Per informazioni, vedere [Elenco delle proprietà per il profilo di configurazione Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Salvare il file con nome `MDATP_MDAV_configuration_settings.plist` .


3.  Nel dashboard jamf pro selezionare **Generale.**

    ![Immagine del nuovo dashboard jamf pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Immettere i dettagli seguenti:

    **Generale**
    
    - Nome: Impostazioni di configurazione MDATP MDAV
    - Descrizione:\<blank\>
    - Categoria: Nessuna (impostazione predefinita)
    - Metodo di distribuzione: installa automaticamente (impostazione predefinita)
    - Livello: Livello computer(impostazione predefinita)

    ![Immagine delle impostazioni di configurazione MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.

    ![Immagine delle impostazioni personalizzate e dell'app](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Selezionare **Carica file (file PLIST).**

    ![Immagine del file plist delle impostazioni di configurazione](images/6f85269276b2278eca4bce84f935f87b.png)

7. In **Preferences Domain** immettere , quindi selezionare Upload `com.microsoft.wdav`  **PLIST File**.

    ![Immagine del dominio delle preferenze delle impostazioni di configurazione](images/db15f147dd959e872a044184711d7d46.png)

8. Selezionare **Scegli file**.

    ![Immagine del file di scelta delle impostazioni di configurazione](images/526e978761fc571cca06907da7b01fd6.png)

9. Seleziona il **MDATP_MDAV_configuration_settings.plist** e quindi seleziona **Apri.**

    ![Immagine delle impostazioni di configurazione di mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Selezionare **Carica**.

    ![Immagine del caricamento delle impostazioni di configurazione](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Immagine dell'immagine di caricamento delle impostazioni di configurazione](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Se si carica il file di Intune, verrà visualizzato l'errore seguente:<br>
    >![Immagine delle impostazioni di configurazione caricamento file intune](images/8e69f867664668796a3b2904896f0436.png)


11. Selezionare **Salva**. 

    ![Immagine delle impostazioni di configurazione Salva immagine](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. Il file viene caricato.

    ![Immagine dell'immagine del file delle impostazioni di configurazione caricata](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Immagine del file delle impostazioni di configurazione caricato](images/a422e57fe8d45689227e784443e51bd1.png)

13. Selezionare la **scheda** Ambito.

    ![Immagine dell'ambito delle impostazioni di configurazione](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Selezionare **Gruppo di computer di Contoso**. 

15. Seleziona **Aggiungi** e **quindi** Salva.

    ![Immagine delle impostazioni di configurazione addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Immagine delle impostazioni di configurazione salva aggiungi](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Scegliere **Fatto**. Verrà visualizzato il nuovo profilo **di configurazione**.

    ![Immagine del profilo di configurazione delle impostazioni di configurazione](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a>Passaggio 4: Configurare le impostazioni delle notifiche

Questi passaggi sono applicabili a macOS 10.15 (Catalina) o versioni successive.

1. Nel dashboard di Jamf Pro seleziona **Computer**, quindi **Profili di configurazione**.

2. Fare **clic su** Nuovo e immettere i dettagli seguenti per **Opzioni:**
    
    - Scheda **Generale**: 
        - **Name**: MDATP MDAV Notification settings
        - **Descrizione**: macOS 10.15 (Catalina) o versione più recente
        - **Category**: None *(impostazione predefinita)*
        - **Metodo di distribuzione**: Installa *automaticamente (impostazione predefinita)*
        - **Level**: Computer Level *(impostazione predefinita)*

        ![Immagine delle impostazioni del profilo di configurazione mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Scheda **Notifiche**, fare **clic su Aggiungi** e immettere i valori seguenti:
        - **ID bundle**: `com.microsoft.wdav.tray`
        - **Avvisi critici**: fare clic su **Disabilita**
        - **Notifiche**: fare clic su **Abilita**
        - **Tipo di avviso banner:** selezionare **Includi** e **temporaneo** *(impostazione predefinita)*
        - **Notifiche nella schermata di blocco**: fare clic su **Nascondi**
        - **Notifiche nel Centro notifiche**: fare clic **su Visualizza**
        - **Icona dell'app Badge**: fare clic su **Visualizza**

        ![Immagine della barra delle notifiche mdatpmdav delle impostazioni di configurazione](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Scheda **Notifiche,** fare **clic su Aggiungi** ancora una volta, scorrere verso il basso fino a Nuove impostazioni **notifiche**
        - **ID bundle**: `com.microsoft.autoupdate2`
        - Configurare il resto delle impostazioni con gli stessi valori di cui sopra

        ![Immagine delle impostazioni di configurazione mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Tieni presente che ora hai due "tabelle" con configurazioni di notifica, una per **l'ID bundle: com.microsoft.wdav.tray** e un'altra per l'ID **bundle: com.microsoft.autoupdate2.** Sebbene sia possibile configurare le impostazioni degli avvisi in base ai propri requisiti, gli ID bundle devono essere esattamente gli stessi descritti in precedenza e l'opzione **Includi** deve essere **attivata** per le **notifiche.**

3. Seleziona la **scheda Ambito,** quindi seleziona **Aggiungi.**

    ![Immagine dell'ambito delle impostazioni di configurazione add](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Selezionare **Gruppo di computer di Contoso**. 

5. Seleziona **Aggiungi** e **quindi** Salva.
    
    ![Immagine delle impostazioni di configurazione contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Immagine delle impostazioni di configurazione aggiungi salvataggio](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Scegliere **Fatto**. Verrà visualizzato il nuovo profilo **di configurazione**.
    ![Immagine dell'impostazione di configurazione eseguita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Passaggio 5: Configurare Microsoft AutoUpdate (MAU)

1. Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Salvarlo con nome `MDATP_MDAV_MAU_settings.plist` .

3. Nel dashboard jamf pro selezionare **Generale.** 

    ![Immagine dell'immagine generale dell'impostazione di configurazione](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Immettere i dettagli seguenti:

    **Generale** 
    
    - Nome: Impostazioni MDATP MDAV MAU
    - Descrizione: impostazioni di Microsoft AutoUpdate per MDATP per macOS
    - Categoria: Nessuna (impostazione predefinita)
    - Metodo di distribuzione: installa automaticamente (impostazione predefinita)
    - Livello: Livello computer(impostazione predefinita)

5. In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.

    ![Immagine dell'app delle impostazioni di configurazione e delle impostazioni personalizzate](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Selezionare **Carica file (file PLIST).**

    ![Immagine dell'impostazione di configurazione plist](images/1213872db5833aa8be535da57653219f.png)  

7. In **Dominio preferenza** immettere: , quindi selezionare Carica file `com.microsoft.autoupdate2` **PLIST**.

    ![Immagine del dominio pref dell'impostazione di configurazione](images/1213872db5833aa8be535da57653219f.png)

8. Selezionare **Scegli file**.

    ![Immagine dell'impostazione di configurazione choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Selezionare **MDATP_MDAV_MAU_settings.plist**.

    ![Immagine delle impostazioni di configurazione mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Selezionare **Carica**.
    ![Immagine dell'impostazione di configurazione uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Immagine dell'impostazione di configurazione uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Selezionare **Salva**.

    ![Immagine dell'impostazione di configurazione saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Selezionare la **scheda** Ambito.
   
     ![Immagine dell'ambito dell'impostazione di configurazione](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Selezionare **Aggiungi**.
    
    ![Immagine dell'impostazione di configurazione addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Immagine dell'impostazione di configurazione addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Immagine dell'impostazione di configurazione addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Scegliere **Fatto**.
    
    ![Immagine dell'impostazione di configurazione doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Passaggio 6: concedere l'accesso completo al disco a Microsoft Defender per Endpoint

1. Nel dashboard di Jamf Pro seleziona **Profili di configurazione.**

    ![Immagine del profilo di configurazione dell'impostazione di configurazione](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Selezionare **+ Nuovo**. 

3. Immettere i dettagli seguenti:

    **Generale** 
    - Name: MDATP MDAV - grant Full Disk Access to EDR and AV
    - Descrizione: in macOS Catalina o versioni più nuove, il nuovo controllo dei criteri delle preferenze sulla privacy
    - Categoria: Nessuno
    - Metodo di distribuzione: installazione automatica
    - Livello: livello computer


    ![Immagine dell'impostazione di configurazione generale](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. In **Configure Privacy Preferences Policy Control** selezionare **Configure**.

    ![Immagine del controllo dell'informativa sulla privacy della configurazione](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. In **Privacy Preferences Policy Control** immetti i dettagli seguenti:

    - Identificatore: `com.microsoft.wdav`
    - Tipo di identificatore: ID bundle
    - Requisiti del codice: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Immagine dei dettagli del controllo dei criteri di preferenza della privacy dell'impostazione di configurazione](images/22cb439de958101c0a12f3038f905b27.png)

6. Selezionare **+ Aggiungi**.

    ![Immagine dell'impostazione di configurazione aggiungi criteri di sistema a tutti i file](images/bd93e78b74c2660a0541af4690dd9485.png)

    - In App o servizio: impostata su **SystemPolicyAllFiles**

    - In "accesso": impostata su **Consenti**

7. Seleziona **Salva** (non quello in basso a destra).

    ![Immagine dell'impostazione di configurazione salva le immagini](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Fare clic `+` sul segno accanto ad Accesso **app** per aggiungere una nuova voce.

    ![Immagine dell'impostazione di configurazione dell'accesso all'app](images/tcc-add-entry.png)

9. Immettere i dettagli seguenti:

    - Identificatore: `com.microsoft.wdav.epsext`
    - Tipo di identificatore: ID bundle
    - Requisiti del codice: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Selezionare **+ Aggiungi**.

    ![Immagine della voce tcc epsext dell'impostazione di configurazione](images/tcc-epsext-entry.png)

    - In App o servizio: impostata su **SystemPolicyAllFiles**

    - In "accesso": impostata su **Consenti**

11. Seleziona **Salva** (non quello in basso a destra).

    ![Immagine dell'impostazione di configurazione tcc epsext image2](images/tcc-epsext-entry2.png)

12. Selezionare la **scheda** Ambito.

    ![Immagine dell'ambito dell'impostazione di configurazione](images/2c49b16cd112729b3719724f581e6882.png)

13. Selezionare **+ Aggiungi**.

    ![Immagine dell'impostazione di configurazione addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Selezionare **Gruppi di** computer > in Nome gruppo **>** selezionare **MachineGroup di Contoso.** 

    ![Immagine dell'impostazione di configurazione contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Selezionare **Aggiungi**. 

16. Selezionare **Salva**. 
    
17. Scegliere **Fatto**.
    
    ![Immagine dell'impostazione di configurazione donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Immagine dell'impostazione di configurazione donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

In alternativa, è possibile scaricare [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Passaggio 7: Approvare l'estensione kernel per Microsoft Defender for Endpoint

> [!CAUTION]
> I dispositivi Apple Silicon (M1) non supportano KEXT. L'installazione di un profilo di configurazione costituito da criteri KEXT avrà esito negativo in questi dispositivi.

1. In **Profili di configurazione** selezionare **+ Nuovo**.

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Immettere i dettagli seguenti:

    **Generale** 
    
    - Nome: MDATP MDAV Kernel Extension
    - Descrizione: estensione del kernel MDATP (kext)
    - Categoria: Nessuno
    - Metodo di distribuzione: installazione automatica
    - Livello: Livello computer

    ![Immagine delle impostazioni di configurazione del kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. In **Configura estensioni kernel approvate** selezionare **Configura**.

    ![Immagine delle impostazioni di configurazione approvate kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. In **Estensioni kernel approvate** immettere i dettagli seguenti:

    - Nome visualizzato: Microsoft Corp.
    - ID team: UBF8T346G9

    ![Immagine dell'estensione del kernel appr delle impostazioni di configurazione](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Selezionare la **scheda** Ambito.

    ![Immagine della scheda img dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selezionare **+ Aggiungi**.

7. Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.

8. Selezionare **+ Aggiungi**.

    ![Immagine delle impostazioni di configurazione aggiungere immagini](images/0dde8a4c41110dbc398c485433a81359.png)

9. Selezionare **Salva**.

    ![Immagine delle impostazioni di configurazione saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Scegliere **Fatto**.

    ![Immagine delle impostazioni di configurazione eseguite](images/1c9bd3f68db20b80193dac18f33c22d0.png)

In alternativa, è possibile scaricare [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Passaggio 8: Approvare le estensioni di sistema per Microsoft Defender for Endpoint

1. In **Profili di configurazione** selezionare **+ Nuovo**.

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Immettere i dettagli seguenti:

    **Generale**
    
    - Nome: MDATP MDAV System Extensions
    - Descrizione: estensioni di sistema MDATP
    - Categoria: Nessuno
    - Metodo di distribuzione: installazione automatica
    - Livello: Livello computer

    ![Immagine delle impostazioni di configurazione sysext new prof](images/sysext-new-profile.png)

3. In **Estensioni di sistema** selezionare **Configura**.

   ![Immagine delle impostazioni di configurazione sysext config](images/sysext-configure.png)

4. In **Estensioni di sistema** immettere i dettagli seguenti:

   - Nome visualizzato: Microsoft Corp. Estensioni di sistema
   - Tipi di estensioni di sistema: estensioni di sistema consentite
   - Identificatore del team: UBF8T346G9
   - Estensioni di sistema consentite:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Immagine delle impostazioni di configurazione sysextconfig2](images/sysext-configure2.png)

5. Selezionare la **scheda** Ambito.

    ![Immagine dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selezionare **+ Aggiungi**.

7. Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.

8. Selezionare **+ Aggiungi**.

   ![Immagine delle impostazioni di configurazione addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. Selezionare **Salva**.

   ![Immagine dell'ambito sysext delle impostazioni di configurazione](images/sysext-scope.png)

10. Scegliere **Fatto**.

    ![Immagine delle impostazioni di configurazione sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Passaggio 9: Configurare l'estensione di rete

Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender for Endpoint su macOS esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center. Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.

Questi passaggi sono applicabili a macOS 10.15 (Catalina) o versioni successive.

1. Nel dashboard di Jamf Pro seleziona **Computer**, quindi **Profili di configurazione**.

2. Fare **clic su** Nuovo e immettere i dettagli seguenti per **Opzioni:**

    - Scheda **Generale**: 
        - **Nome**: Estensione di rete di Microsoft Defender ATP
        - **Descrizione**: macOS 10.15 (Catalina) o versione più recente
        - **Category**: None *(impostazione predefinita)*
        - **Metodo di distribuzione**: Installa *automaticamente (impostazione predefinita)*
        - **Level**: Computer Level *(impostazione predefinita)*

    - Filtro **contenuto scheda**:
        - **Nome filtro**: Filtro contenuto di Microsoft Defender ATP
        - **Identificatore**: `com.microsoft.wdav`
        - Lasciare **vuoto l'indirizzo** **del** servizio, l'organizzazione, **il** nome utente, la **password,** **il** certificato (**Include** *non è* selezionato)
        - **Filter Order**: Inspector
        - **Filtro socket**: `com.microsoft.wdav.netext`
        - **Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Lasciare **vuoti i** campi filtro di rete **(l'opzione** Includi *non è* selezionata)

        Tieni presente **che i valori di Identifier,** Socket **Filter** e Socket **Filter Designated Requirement** sono esattamente come specificato in precedenza.

        ![Immagine dell'impostazione di configurazione mdatpmdav](images/netext-create-profile.png)

3. Selezionare la **scheda** Ambito.

   ![Immagine della scheda sco delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Selezionare **+ Aggiungi**.

5. Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.

6. Selezionare **+ Aggiungi**.

    ![Immagine delle impostazioni di configurazione adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. Selezionare **Salva**.

    ![Immagine delle impostazioni di configurazione savimg netextscop](images/netext-scope.png)

8. Scegliere **Fatto**.

    ![Immagine delle impostazioni di configurazione netextfinal](images/netext-final.png)

In alternativa, è possibile scaricare [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Passaggio 10: pianificare le analisi con Microsoft Defender for Endpoint in macOS
Segui le istruzioni su [Pianifica analisi con Microsoft Defender for Endpoint in macOS.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Passaggio 11: Distribuire Microsoft Defender per Endpoint in macOS

1. Passare al percorso in cui è stato salvato `wdav.pkg` .

    ![Immagine di Esplora file wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Rinominarlo in `wdav_MDM_Contoso_200329.pkg` .

    ![Immagine di esplora file1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Apri il dashboard di Jamf Pro.

    ![Immagine delle impostazioni di configurazione jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Seleziona il computer e fai clic sull'icona a forma di ingranaggio nella parte superiore, quindi seleziona **Gestione computer.**

    ![Immagine delle impostazioni di configurazione compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. In **Pacchetti** seleziona **+ Nuovo**. 
    ![Un'immagine contenente una descrizione del pacchetto generato automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. In **Nuovo pacchetto** immetti i dettagli seguenti:

    **Scheda Generale**
    - Nome visualizzato: lasciare vuoto per il momento. Perché verrà reimpostato quando scegli il tuo pkg.
    - Categoria: Nessuna (impostazione predefinita)
    - Filename: Choose File

    ![Immagine della scheda generale delle impostazioni di configurazione](images/21de3658bf58b1b767a17358a3f06341.png)

    Aprire il file e puntare a `wdav.pkg` o `wdav_MDM_Contoso_200329.pkg` .
    
    ![Screenshot dello schermo di un computer Descrizione generata automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Seleziona **Apri**. Imposta il **nome visualizzato su** Microsoft Defender Advanced Threat Protection e Microsoft Defender **Antivirus.**

    **File manifesto** non obbligatorio. Microsoft Defender Advanced Threat Protection funziona senza file manifesto.
    
    **Scheda Opzioni**<br> Mantenere i valori predefiniti.

    **Scheda Limitazioni**<br> Mantenere i valori predefiniti.
    
     ![Immagine della scheda limitazione delle impostazioni di configurazione](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. Selezionare **Salva**. Il pacchetto viene caricato in Jamf Pro. 

   ![Immagine delle impostazioni di configurazione pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   La distribuzione del pacchetto può richiedere alcuni minuti.
   
   ![Immagine delle impostazioni di configurazione pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Passare alla **pagina** Criteri.

    ![Immagine delle impostazioni di configurazione](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Selezionare **+ Nuovo** per creare un nuovo criterio.

    ![Immagine delle impostazioni di configurazione nuovo criterio](images/847b70e54ed04787e415f5180414b310.png)


11. In **Generale** Immettere i dettagli seguenti:

    - Nome visualizzato: MDATP Onboarding Contoso 200329 v100.86.92 o versione successiva

    ![Immagine delle impostazioni di configurazionemdatponboard ](images/625ba6d19e8597f05e4907298a454d28.png)

12. Selezionare **Archiviazione ricorrente.** 
    
    ![Immagine dell'archiviazione ricorrente delle impostazioni di configurazione](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. Selezionare **Salva**. 
 
14. Selezionare **Pacchetti > Configura**.
 
    ![Immagine delle impostazioni di configurazione configurate](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Seleziona il **pulsante** Aggiungi accanto a **Microsoft Defender Advanced Threat Protection e Microsoft Defender Antivirus.**

    ![Immagine delle impostazioni di configurazione MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Selezionare **Salva**.

    ![Immagine delle impostazioni di configurazionesavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Selezionare la **scheda** Ambito.  

    ![Immagine delle impostazioni di configurazione scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Selezionare i computer di destinazione.

    ![Immagine delle impostazioni di configurazione tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Ambito**
    
    Selezionare **Aggiungi**.
    
    ![Immagine delle impostazioni di configurazione ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Immagine delle impostazioni di configurazione ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Self-Service**
    
    ![Immagine delle impostazioni di configurazione selfservice](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Scegliere **Fatto**. 

    ![Immagine delle impostazioni di configurazione do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Immagine delle impostazioni di configurazione do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




