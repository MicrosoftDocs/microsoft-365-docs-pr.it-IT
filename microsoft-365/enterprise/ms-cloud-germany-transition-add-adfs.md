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
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838414"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland

Questa modifica alla configurazione deve essere applicata ogni volta prima dell'avvio della fase 2.
Una volta completata la fase 2, la modifica della configurazione funzionerà e sarà possibile accedere tramite endpoint globali di Office 365, ad esempio `https://portal.office.com` . Se si implementa la modifica alla configurazione prima della fase 2,  gli endpoint globali di Office 365 non funzionano ancora, ma la nuova relazione di trust della relying party fa ancora parte della configurazione di Active Directory Federation Services (AD FS).

I clienti che utilizzano l'autenticazione federata con Active Directory Federation Services (ADFS) non devono apportare modifiche agli URI dell'autorità emittente utilizzati per tutte le autenticazioni con Servizi di dominio Active Directory locale durante la migrazione. La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio. Gli URI dell'autorità emittente possono essere modificati direttamente  in AD FS o quando un dominio viene convertito da gestito a _federato_ e viceversa. È consigliabile non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati al termine della migrazione.

Per preparare la farm AD FS per la migrazione da Microsoft Cloud Deutschland, eseguire la procedura seguente:

1. Eseguire il backup delle impostazioni di AD FS, inclusa l'attendibilità del relying party Microsoft Cloud Deutschland esistente, con [questi passaggi.](#backup) Assegnare al backup **il nome MicrosoftCloudDeutschlandOnly** per indicare che contiene solo le informazioni sul tenant di Microsoft Cloud Deutschland.

   > [!NOTE]
   > Il backup conterrà non solo la relying party trust di Office 365 esistente per Microsoft Cloud Deutschland, ma anche tutti gli altri trust relying party presenti nella rispettiva farm AD FS.

2. Testare il ripristino utilizzando il backup MicrosoftCloudDeutschlandOnly, la farm AD FS deve continuare a funzionare solo come Microsoft Cloud Deutschland.

Dopo aver completato e testato il backup di AD FS, eseguire la procedura seguente per aggiungere un nuovo trust relying party alla configurazione di ADFS:

1. Aprire la console di gestione di AD FS.

2. Nel riquadro sinistro della console di gestione ADFS passare al menu **Relying Party Trusts.**

3. Nel riquadro destro seleziona **Aggiungi attendibilità componente...**

4. Selezionare **Avvia** nella pagina **iniziale** della procedura guidata Aggiungi attendibilità componente.

5. Nella pagina **Seleziona origine dati** selezionare Importa dati sulla **relying party pubblicata online o in una rete locale.** Il **valore dell'indirizzo dei metadati federativi (nome host o URL)** deve essere impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Fare clic su **Avanti**.

6. Nella pagina **Specifica nome visualizzato** digitare il nome visualizzato, ad esempio Microsoft Office **365 Identity Platform WorldWide.** Fare clic su **Avanti**.

7. Se si utilizza ADFS in Windows Server 2012, nella pagina della procedura guidata Configurare l'autenticazione a più fattori **ora?** selezionare la scelta appropriata in base ai requisiti di autenticazione. Se si è ancorati all'impostazione predefinita, selezionare Non si desidera configurare le impostazioni di autenticazione a più fattori per questa attendibilità **relying party in questo momento.** Se lo si desidera, è possibile modificare questa impostazione in un secondo momento.

8. Per AD FS 2012: nella pagina **Scegli** regole di autorizzazione rilascio mantenere Selezionata l'opzione Consenti a tutti gli utenti di accedere a questa **relying party** e fare clic su **Avanti.**

8. Per AD FS 2016 e AD FS 2019: nella pagina **Scegli** criteri di controllo di accesso selezionare il criterio di controllo di accesso appropriato e fare clic su **Avanti.** Se non si sceglie nessuno, l'attendibilità del componente **NON funzionerà.**

9. Fare **clic su** Avanti nella pagina Pronto per **aggiungere** attendibilità per completare la procedura guidata.

10. Fare **clic su** Chiudi nella **pagina** Fine.

Chiudendo la procedura guidata, viene stabilita l'attendibilità relying party con il servizio globale di Office 365. Tuttavia, non sono ancora configurate regole di trasformazione rilascio.

È possibile utilizzare [la Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole corrette di trasformazione rilascio. Le regole attestazione generate create con la Guida di AD FS possono essere aggiunte manualmente tramite la console di gestione di AD FS o con PowerShell. La Guida di AD FS genererà gli script di PowerShell necessari che devono essere eseguiti.  

> [!NOTE]
> [La Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genererà le regole di trasformazione di rilascio standard che vengono forniti con il prodotto. Tuttavia, se le regole di trasformazione di rilascio personalizzate sono presenti in Microsoft Cloud Deutschland Relying Party Trust (ad esempio, URI dell'autorità emittente personalizzata, ID non standard non modificabili o altre personalizzazioni), le regole generate dalla Guida di AD FS devono essere modificate in modo che si adattino alla logica personalizzata attualmente in uso per l'attendibilità del componente Microsoft Cloud Deutschland. Se queste personalizzazioni non sono integrate nelle regole generate tramite la Guida di [ADFS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)l'autenticazione  **a Microsoft Office 365 Identity Platform WorldWide** probabilmente non funzionerà per le identità federate.

1. Eseguire **Generate Claims** on AD FS [Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) e copiare lo script di PowerShell usando l'opzione **Copy** nell'angolo superiore destro dello script.

2. Seguire i passaggi descritti nella Guida [di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) su come eseguire lo script di PowerShell nella farm AD FS per generare il trust relying party globale.

3. Verificare che siano presenti due relying partyTtrust; uno per Microsoft Cloud Deutschland e uno per il servizio Office 365 Global. Il comando seguente può essere utilizzato per il controllo. Deve restituire due righe e i rispettivi nomi e identificatori.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Eseguire il backup della configurazione di migrazione completa, inclusi entrambi i trust relying party, utilizzando [questi passaggi.](#backup) Salvarlo con il nome **MicrosoftCloudDeutschlandAndWorldwide**.

5. Durante la migrazione del tenant, verificare regolarmente che l'autenticazione AD FS funzioni con Microsoft Cloud Deutschland e microsoft global cloud nei vari passaggi di migrazione supportati.


## <a name="ad-fs-disaster-recovery-wid-database"></a>Ripristino di emergenza AD FS (database WID)

Per ripristinare la farm AD FS in uno strumento di ripristino rapido [di ADFS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) di emergenza deve essere utilizzato. Pertanto, lo strumento deve essere scaricato e prima dell'inizio della migrazione deve essere creato e archiviato in modo sicuro un backup. In questo esempio sono stati eseguiti i comandi seguenti per eseguire il backup di una farm in esecuzione in un database WID:

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


## <a name="more-information"></a>Altre informazioni

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
