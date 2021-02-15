---
title: Passaggi di migrazione ad FS per la migrazione da Microsoft Cloud Deutschland
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
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688666"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Passaggi di migrazione ad FS per la migrazione da Microsoft Cloud Deutschland

Per eseguire la migrazione della farm di Active Directory Federation Services (AD FS) da Microsoft Cloud Deutschland:

1. Eseguire il backup delle impostazioni di AD FS, incluse le informazioni di trust FF con [questi passaggi.](#backup) Assegnare al backup **il nome Microsoft Cloud Deutschland_Only** per indicare che contiene solo le informazioni sul tenant di Microsoft Cloud Deutschland.
2. Testare il ripristino usando il backup di Microsoft Cloud Deutschland_Only, la farm AD FS deve continuare a funzionare solo come Microsoft Cloud Deutschland.
3. Creare una nuova relazione di trust relying party **da ADFS > servizi di Office 365.**
4. In **Attendibilità componente nella** console di gestione di AD FS selezionare Aggiungi **attendibilità componente.**
5. Selezionare **Avanti** nella pagina **iniziale** della procedura guidata Aggiungi attendibilità componente.
6. Nella pagina **Seleziona origine dati** selezionare Importa dati sulla **relying party pubblicata online o in una rete locale.** Il **valore dell'indirizzo dei metadati federativi (nome host o URL)** è impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Fare clic su **Avanti**.
7. Nella pagina **Seleziona origine dati** digitare il nome visualizzato. Microsoft consiglia di **Microsoft Office 365 Identity Platform WorldWide.** Fare clic su **Avanti**.
8. Fare **clic** su Avanti nelle pagine Configura autenticazione a **più fattori?**, Scegliere **Regole** di autorizzazione rilascio e Pronto per aggiungere **le pagine** attendibilità.
9. Fare **clic** su Chiudi nella **pagina** Fine.

Chiudendo la procedura guidata, viene stabilita l'attendibilità del componente per i servizi di Office 365 eSTS. Non vengono tuttavia stabilite regole di trasformazione rilascio.

È possibile utilizzare [la Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole corrette di trasformazione rilascio. Le regole attestazione generate create con la Guida di AD FS possono essere aggiunte manualmente tramite la console di gestione di AD FS o con PowerShell. La Guida di AD FS genererà gli script di PowerShell necessari che devono essere eseguiti.  

1. Eseguire **la Guida** genera attestazioni in AD FS e  copiare lo script di trasformazione delle attestazioni di PowerShell usando l'opzione Copia nell'angolo superiore destro dello script.
2. Incollare powershell generato nel modo seguente:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Eseguire lo script completato.
4.  Verificare che siano presenti due attendibilità relying party; uno per il mondo e uno per BF.
5.  Eseguire il backup delle relazioni di trust [utilizzando questa procedura.](#backup) Salvarlo con il nome **FFAndWorldwide.**
6.  Completare la migrazione back-end e verificare che ADFS funzioni ancora durante il processo di migrazione.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Ripristino di emergenza AD FS (database WID)

Per ripristinare la farm AD FS in uno strumento di ripristino rapido [di AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) di emergenza deve essere utilizzato. Pertanto, lo strumento deve essere scaricato e prima dell'inizio della migrazione deve essere creato e archiviato in modo sicuro un backup. In questo esempio (ambienti TAT) sono stati eseguiti i comandi seguenti per eseguire il backup della farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Eseguire il backup di una farm AD FS

1. Installare lo strumento di ripristino rapido di AD FS nel server AD FS primario.
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

Se la farm ha avuto esito completamente negativo e non è possibile tornare alla farm precedente, eseguire le operazioni seguenti. 

1. Spostare il backup generato e archiviato in precedenza nel nuovo server AD FS primario.
2. Eseguire il comando `Restore-ADFS` di PowerShell seguente. Se necessario, importare il certificato SSL ad FS in anticipo.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Puntare i nuovi record DNS o il servizio di bilanciamento del carico ai nuovi server AD FS.

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [AD FS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
