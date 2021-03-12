---
title: Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: passaggi di migrazione di Active Directory Federation Services (AD FS) per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727468"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland

Questa modifica alla configurazione può essere applicata in qualsiasi momento prima dell'avvio della fase 4.
Al termine della fase 2, la modifica della configurazione funzionerà e sarà possibile accedere agli endpoint globali di Office 365, ad esempio `https://portal.office.com` . Se si implementa la modifica alla configurazione prima della fase 2,  gli endpoint globali di Office 365 non funzionano ancora, ma la nuova relazione di trust della relying party fa ancora parte della configurazione di Active Directory Federation Services (AD FS).

Per eseguire la migrazione della farm AD FS da Microsoft Cloud Deutschland:

1. Eseguire il backup delle impostazioni di AD FS, incluse le info sull'attendibilità FF con [questi passaggi.](#backup) Denoti il nome **Microsoft Cloud Deutschland_Only** per indicare che contiene solo le informazioni del tenant di Microsoft Cloud Deutschland.
2. Testare il ripristino usando il backup di Microsoft Cloud Deutschland_Only, la farm AD FS deve continuare a funzionare solo come Microsoft Cloud Deutschland.

Dopo aver completato e testato il backup di AD FS, eseguire la procedura seguente per aggiungere un nuovo trust relying party alla configurazione di ADFS:

1. Aprire la console di gestione di AD FS
2. Nel riquadro sinistro della console di gestione ADFS espandere **ADFS**, quindi **Relazioni di** trust , quindi **Trust relying party**
3. Nel riquadro destro seleziona **Aggiungi attendibilità componente...**
4. Selezionare **Avanti** nella pagina **iniziale** della procedura guidata Aggiungi attendibilità componente.
5. Nella pagina **Seleziona origine dati** selezionare Importa dati sulla **relying party pubblicata online o in una rete locale.** Il **valore dell'indirizzo dei metadati federativi (nome host o URL)** deve essere impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Fare quindi clic su **Avanti**.
6. Nella pagina **Seleziona origine dati** digitare il nome visualizzato, ad esempio Microsoft Office **365 Identity Platform WorldWide.** Fare quindi clic su **Avanti**.
7. Nella pagina della procedura guidata **Configure Multi-factor Authentication Now?** selezionare la scelta appropriata in base ai requisiti di autenticazione. Se si è ancorati all'impostazione predefinita, selezionare Non si desidera configurare le impostazioni di autenticazione a più fattori per questa attendibilità **relying party in questo momento.** Se lo si desidera, è possibile modificare questa impostazione in un secondo momento.
8. Nella pagina **Scegli regole di autorizzazione rilascio** mantenere Selezionata l'opzione Consenti a tutti gli utenti di accedere a questa **relying party** fare clic su **Avanti**
9. Fare **clic su** Avanti nella pagina Pronto per **aggiungere** attendibilità per completare la procedura guidata.
10. Fare **clic su** Chiudi nella **pagina** Fine.

Chiudendo la procedura guidata, viene stabilita l'attendibilità del componente con i servizi globali di Office 365. Tuttavia, non sono ancora configurate regole di trasformazione rilascio.

È possibile utilizzare [la Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole corrette di trasformazione rilascio. Le regole attestazione generate create con la Guida di AD FS possono essere aggiunte manualmente tramite la console di gestione di AD FS o con PowerShell. La Guida di AD FS genererà gli script di PowerShell necessari che devono essere eseguiti.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Eseguire **la guida Genera** attestazioni in ADFS e copiare lo script di trasformazione delle attestazioni di PowerShell utilizzando l'opzione **Copia** nell'angolo superiore destro dello script.
2. Apri l'editor di testo preferito e incolla lo script di PowerShell in una nuova finestra di testo.
3. Aggiungere le righe di PowerShell seguenti alla fine dello script incollato dal passaggio 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Safe and execute the PowerShell script.
5. Verificare che siano presenti due trust relying party. uno per Microsoft Cloud Deutschland e uno per il servizio Office 365 Global.
6. Eseguire il backup dei trust utilizzando [questa procedura.](#backup) Salvarlo con il nome **FFAndWorldwide**.
7. Completare la migrazione back-end e verificare che ADFS funzioni ancora durante il processo di migrazione.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Ripristino di emergenza AD FS (database WID)

Per ripristinare la farm AD FS in uno strumento di ripristino rapido [di ADFS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) di emergenza deve essere utilizzato. Pertanto, lo strumento deve essere scaricato e prima dell'inizio della migrazione deve essere creato e archiviato in modo sicuro un backup. In questo esempio (ambienti TAT) sono stati eseguiti i comandi seguenti per eseguire il backup della farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Eseguire il backup di una farm AD FS

1. Installare lo strumento di ripristino rapido AD FS nel server AD FS primario.
2. Importare il modulo in una sessione di PowerShell con questo comando.
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. Eseguire il comando di backup:
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. Archiviare il backup in modo sicuro in una destinazione desiderata.

### <a name="restore-an-ad-fs-farm"></a>Ripristinare una farm AD FS

Se la farm ha avuto completamente esito negativo e non è possibile tornare alla farm precedente, eseguire le operazioni seguenti. 

1. Spostare il backup generato e archiviato in precedenza nel nuovo server ADFS primario.
2. Eseguire il seguente `Restore-ADFS` comando di PowerShell. Se necessario, importare il certificato SSL di AD FS in anticipo.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Puntare i nuovi record DNS o il servizio di bilanciamento del carico ai nuovi server AD FS.

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
