---
title: 'Eseguire la migrazione dei file google a Microsoft 365 per le aziende '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione dei file di Google a Microsoft 365 per le aziende tramite Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928199"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Eseguire la migrazione dei file google a Microsoft 365 per le aziende 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Quando si passa a Microsoft 365 per le aziende, è necessario eseguire la migrazione dei file da Google Drive. Puoi usare l'app Mover per spostare i file dalle unità personali e condivise. Per ulteriori informazioni, vedere [Migrazione cloud di Mover](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover crea una copia dei file e sposta le copie in Microsoft 365 per le aziende. Anche i file originali rimarranno in Google Drives.

## <a name="before-you-start"></a>Prima di iniziare

Tutti gli utenti devono aver eseguito l'accesso a Microsoft 365 per le aziende e aver configurato OneDrive for Business. A tale scopo, passare [a office.com,](https://office.com)accedere con le credenziali microsft 365 per le aziende e quindi scegliere OneDrive.

## <a name="try-it"></a>Perché non provarlo?

### <a name="install-mover"></a>Installare Mover

1. Accedere alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).

1. Choose **Apps,** **Google Workspace Marketplace apps,** Then Add app to Domain Install **list.**

1. Cercare Mover e selezionarlo.

1. Choose **Domain Install**, then **Continue**.

1. Esaminare le autorizzazioni, selezionare la casella di controllo per accettare i termini, quindi selezionare **Consenti,** scegliere **Avanti,** quindi **Fine.**

### <a name="create-connectors-and-run-the-migration"></a>Creare connettori ed eseguire la migrazione

1. Torna alle **app marketplace di Google Workspace.**
1. Aggiorna il browser e seleziona l'app **Mover.**
1. Scorrere verso il basso e scegliere il collegamento di spostamento universale.
1. Selezionare **Autorizza nuovo connettore,** individuare **G Suite (amministratore)** e scegliere **Autorizza.**
1. Modificare il **nome visualizzato,** se si desidera, quindi **selezionare Autorizza.**
1. Scegliere un account amministratore di Google, rivedere le autorizzazioni, quindi selezionare **Consenti.**

    Mover visualizza il numero di unità del team e di unità individuate dall'utente. 

1. In **Seleziona destinazione** scegliere **Autorizza nuovo connettore,** individuare Office **365** e selezionare **Autorizza.**
1. Per concedere le autorizzazioni per l'app Mover in Azure Active Directory, passare a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selezionare **Office 365 Mover**, **Autorizzazioni**, Concedere il consenso **dell'amministratore per l'azienda.**
1. Scegliere l'account, esaminare le autorizzazioni e selezionare **Accetta.**
1. Scegliere **Proprietà** e verificare che **l'assegnazione utente sia obbligatoria?** è attivata.
1. Tornare all'app Mover, modificare il **nome** visualizzato, se si desidera, scegliere **Autorizza,** quindi selezionare un account amministratore Microsoft.

    Mover informerà l'utente sul numero di siti e utenti di SharePoint Online (o SharePoint Online) individuati.
1. Choose **Continue Migration Setup,** select **Add Users,** then **Automatically Discover and Add Users.**

    L'app Mover tenterà di eseguire il mapping delle unità dal percorso di origine in Google al percorso di destinazione in Microsoft 365. 

    Se un'unità non viene mappata automaticamente, aggiungere il percorso di destinazione a un file CSV, che verrà utilizzato in seguito per eseguire la migrazione dell'unità condivisa in una raccolta documenti di SharePoint. 

1. In questo caso, è stato aggiunto un sito di SharePoint denominato File migrati e preso nota dell'URL della pagina dei documenti. 
1. Abbiamo quindi creato un file CSV usando il formato percorso di origine, percorso di destinazione e tag. 

    Per informazioni dettagliate, [vedere aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).

    Quando si aggiunge l'URL del percorso di destinazione, rimuovere tutti gli elementi dopo Documenti condivisi, ad esempio, questo URL completo non funzionerà: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Passare a: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Una volta pronto il file CSV, selezionare **Azioni di** migrazione **,** Aggiungi alla migrazione , Scegliere un file **da caricare.**
1. Passare al file CSV, selezionarlo e scegliere **Apri.**
1. Selezionare le unità utente di cui si desidera eseguire la migrazione dei file, quindi scegliere **Avvia migrazione utenti.**
1. Esaminare le informazioni sulla migrazione, scegliere quando avviare la migrazione, accettare i termini e **le condizioni,** quindi selezionare **Continua.**

L'app Mover informerà l'utente quando il processo di migrazione è stato completato.