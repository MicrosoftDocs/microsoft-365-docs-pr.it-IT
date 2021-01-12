---
title: 'Eseguire la migrazione di file di Google a Microsoft 365 for business '
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione di file di Google a Microsoft 365 for business tramite Mover.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794638"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Eseguire la migrazione di file di Google a Microsoft 365 for business 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Quando ci si sposta su Microsoft 365 for business, è necessario eseguire la migrazione dei file da Google Drive. È possibile utilizzare l'app Mover per spostare i file da unità personali e condivise. Per ulteriori informazioni, vedere [Mover cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover renderà una copia dei file e sposterà le copie in Microsoft 365 for business. Anche i file originali rimarranno nelle unità di Google.

## <a name="before-you-start"></a>Prima di iniziare

Tutti gli utenti devono avere effettuato l'accesso a Microsoft 365 for business e impostare la propria OneDrive for business. A tale scopo, accedere a [Office.com](https://office.com), accedere con le credenziali di Microsoft 365 per le aziende e quindi scegliere OneDrive.

## <a name="try-it"></a>Perché non provarlo?

### <a name="install-mover"></a>Installazione di Mover

1. Accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com).

1. Scegliere **app**, **Google Workspace Marketplace Apps** e quindi **aggiungere app all'elenco di installazione di dominio**.

1. Cercare Mover e selezionarlo.

1. Scegliere **Domain install**, quindi **continue**.

1. Controllare le autorizzazioni, selezionare la casella di controllo per accettare i termini, quindi selezionare **Consenti**, quindi **fare** clic su **Avanti**.

### <a name="create-connectors-and-run-the-migration"></a>Creare connettori ed eseguire la migrazione

1. Tornare alle **App Marketplace di Google Workspace**.
1. Aggiornare il browser e selezionare l'app **Mover** .
1. Scorrere verso il basso e scegliere il collegamento di spostamento universale.
1. Selezionare **autorizza nuovo connettore**, individuare **G Suite (amministratore)** e scegliere **autorizza**.
1. Se lo si desidera, modificare il **nome visualizzato**, quindi selezionare **autorizza**.
1. Scegliere un account di amministratore di Google, esaminare le autorizzazioni e quindi fare clic su **Consenti**.

    Mover Visualizza il numero di unità di team e unità utente individuate. 

1. In **Seleziona destinazione**, scegliere **autorizza nuovo connettore**, individuare **Office 365** e selezionare **autorizza**.
1. Per concedere le autorizzazioni per l'app Mover in Azure Active Directory, passare a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selezionare **Office 365 Mover**, **Permissions**, **concedere il consenso dell'amministratore per la società**.
1. Scegliere l'account, esaminare le autorizzazioni e selezionare **accetta**.
1. Scegliere **Proprietà** e verificare che l' **assegnazione degli utenti sia obbligatoria?** è attivata.
1. Tornare all'app Mover, cambiare il **nome visualizzato**, se lo si desidera, scegliere **autorizza**, quindi selezionare un account di amministratore Microsoft.

    Mover vi informerà sul numero di siti e utenti di SharePoint Online (o SPO) individuati.
1. Scegliere **continue Migration Setup**, selezionare **Aggiungi utenti**, quindi **individuare e aggiungere automaticamente gli utenti**.

    L'app Mover tenterà di mappare le unità dal percorso di origine di Google al percorso di destinazione in Microsoft 365. 

    Se un'unità non esegue il mapping automatico, aggiungere il percorso di destinazione a un file CSV, che verrà utilizzato in un secondo momento per eseguire la migrazione dell'unità condivisa in una raccolta documenti di SharePoint. 

1. In questo caso, è stato aggiunto un sito di SharePoint denominato file migrati e viene annotato l'URL della pagina documenti. 
1. È stato quindi creato un file CSV utilizzando il formato del percorso di origine, il percorso di destinazione e i tag. 

    Per informazioni dettagliate, vedere [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).

    Quando si aggiunge l'URL del percorso di destinazione, rimuovere tutto dopo la condivisione di documenti, ad esempio, l'URL completo non funzionerà: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Passare a: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Una volta che il file CSV è pronto, seleziona **azioni di migrazione**, **Aggiungi alla migrazione**, **Scegli un file da caricare**.
1. Passare al file CSV, selezionarlo e quindi fare clic su **Apri**.
1. Selezionare le unità utente di cui si desidera eseguire la migrazione e quindi fare clic su **Avvia migrazione utenti**.
1. Leggere le informazioni sulla migrazione, scegliere quando avviare la migrazione, accettare i **termini e le condizioni**, quindi selezionare **continua**.

L'app Mover informerà quando il processo di migrazione è stato completato.