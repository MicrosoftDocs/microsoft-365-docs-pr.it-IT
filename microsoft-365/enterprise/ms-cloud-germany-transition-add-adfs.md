---
title: Passaggi di migrazione AD FS per la migrazione da Microsoft Cloud Deutschland
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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Passaggi di migrazione AD FS per la migrazione da Microsoft Cloud Deutschland

Per eseguire la migrazione della farm di Active Directory Federation Services (AD FS) da Microsoft Cloud Deutschland:

1. Eseguire il backup delle impostazioni di ADFS, incluse le informazioni sull'attendibilità FF con [questi passaggi](#backup). Denominare il backup di **Microsoft cloud Deutschland_Only** per indicare che contiene solo le informazioni sul tenant di Microsoft Cloud Deutschland.
2. Testare il ripristino utilizzando il backup di Microsoft Cloud Deutschland_Only, la farm ADFS dovrebbe continuare a funzionare solo con Microsoft Cloud Deutschland.
3. Creare una nuova relazione di trust di relying party da **adfs > servizi di Office 365**.
4. In **Relying Party Trusts** nella console di gestione ad FS, selezionare **Aggiungi attendibilità componente**.
5. Scegliere **Avanti** nella pagina **iniziale** dell'aggiunta guidata attendibilità componente.
6. Nella pagina **Selezione origine dati** selezionare **Importa dati relativi al componente pubblicato online o su una rete locale**. Il valore dell' **indirizzo dei metadati di federazione (nome host o URL)** è impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Fare clic su **Avanti**.
7. Nella pagina **Selezione origine dati** Digitare il nome visualizzato. Microsoft consiglia Microsoft **Office 365 Identity Platform in tutto il mondo**. Fare clic su **Avanti**.
8. Fare clic su **Avanti** per configurare l'autenticazione a più **fattori in questo momento**, **scegliere regole di autorizzazione di rilascio** e **pronto per l'aggiunta di pagine attendibili** .
9. Fare clic su **Chiudi** nella pagina **fine** .

Chiudendo la procedura guidata, viene stabilita la relazione di trust relying party ai servizi di Office 365 eSTS. Tuttavia, non vengono stabilite regole di trasformazione dell'emissione.

È possibile utilizzare la [Guida di ADFS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole di trasformazione di rilascio corrette. Le regole attestazione generate create con la Guida di ADFS possono essere aggiunte manualmente tramite la console di gestione di ADFS o con PowerShell. La Guida di ADFS genererà gli script di PowerShell necessari che devono essere eseguiti.  

1. Eseguire **genera attestazioni** sulla guida di ADFS e copiare lo script di trasformazione delle attestazioni di PowerShell utilizzando l'opzione **copia** all'angolo superiore destro dello script.
2. Incollare la PowerShell generata nei seguenti elementi:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Eseguire lo script completato.
4.  Verificare che siano presenti due trust relying party. uno per tutto il mondo e uno per BF.
5.  Eseguire il backup dei trust utilizzando [questi passaggi](#backup). Salvarlo con il nome **FFAndWorldwide**.
6.  Completare la migrazione di back-end e verificare che ADFS funzioni ancora durante il processo di migrazione.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Ripristino di emergenza ADFS (database WID)

Per ripristinare la farm ADFS in uno strumento di [ripristino rapido di emergenza ad FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , è necessario utilizzarla. Pertanto, è necessario scaricare lo strumento e prima dell'inizio della migrazione è necessario creare un backup e archiviarlo in modo sicuro. In questo esempio (ambienti TAT) sono stati eseguiti i comandi seguenti per eseguire il backup della farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Eseguire il backup di una farm AD FS

1. Installare lo strumento AD FS per il ripristino rapido sul server ADFS primario.
2. Importare il modulo in una sessione di PowerShell con questo comando.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Eseguire il comando backup:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Archiviare il backup in modo sicuro su una destinazione desiderata. 

### <a name="restore-an-ad-fs-farm"></a>Ripristinare una farm AD FS

Se la farm non è stata completata correttamente e non è possibile tornare alla farm precedente, procedere come segue. 

1. Spostare il backup precedentemente generato e archiviato nel nuovo server ADFS primario.
2. Eseguire il seguente `Restore-ADFS` comando di PowerShell. Se necessario, importare il certificato SSL ADFS in anticipo.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Indirizzare i nuovi record DNS o il bilanciamento del carico ai nuovi server AD FS.

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni su [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
