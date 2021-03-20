---
title: 'Eseguire la migrazione dei file di Google a Microsoft 365 per le aziende '
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
description: Informazioni su come eseguire la migrazione dei file di Google a Microsoft 365 per le aziende tramite Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913575"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Eseguire la migrazione dei file di Google a Microsoft 365 per le aziende 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Quando si passa a Microsoft 365 per le aziende, è necessario eseguire la migrazione dei file da Google Drive. Puoi usare l'app Mover per spostare i file dalle unità personali e condivise. Per ulteriori informazioni, vedere [Mover Cloud Migration.](/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover crea una copia dei file e sposta le copie in Microsoft 365 per le aziende. Anche i file originali rimarranno in Google Drives.

## <a name="before-you-start"></a>Prima di iniziare

Tutti gli utenti devono aver eseguito l'accesso a Microsoft 365 per le aziende e aver configurato OneDrive for Business. A tale scopo, passare [a office.com](https://office.com), accedere con le credenziali di Microsoft 365 per le aziende e quindi scegliere OneDrive.

## <a name="try-it"></a>Perché non provarlo?

### <a name="install-mover"></a>Installare Mover

1. Accedi alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).

1. Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list**.

1. Cerca Mover e selezionalo.

1. Scegliere **Domain Install**, quindi **Continue**.

1. Rivedere le autorizzazioni, selezionare la casella di controllo per accettare i termini, quindi selezionare **Consenti,** scegliere **Avanti,** quindi **Fatto.**

### <a name="create-connectors-and-run-the-migration"></a>Creare connettori ed eseguire la migrazione

1. Torna alle **app di Google Workspace Marketplace.**
1. Aggiorna il browser e seleziona l'app **Mover.**
1. Scorrere verso il basso e scegliere il collegamento di spostamento universale.
1. Seleziona **Autorizza nuovo connettore,** individua **G Suite (amministratore)** e scegli **Autorizza**.
1. Modificare il **nome visualizzato**, se si desidera, quindi selezionare **Autorizza**.
1. Scegli un account amministratore di Google, rivedi le autorizzazioni, quindi seleziona **Consenti.**

    Mover visualizza il numero di unità del team e unità utente individuate. 

1. In **Seleziona destinazione** scegliere **Autorizza nuovo connettore,** individuare Office **365** e **selezionare Autorizza**.
1. Per concedere le autorizzazioni per l'app Mover in Azure Active Directory, passare a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selezionare **Office 365 Mover**, **Autorizzazioni**, Concedere il consenso **dell'amministratore per la società**.
1. Scegliere l'account, esaminare le autorizzazioni e selezionare **Accetta.**
1. Scegliere **Proprietà** e verificare che **l'assegnazione utente necessaria?** sia attivata.
1. Tornare all'app Mover, modificare il **nome** visualizzato, se si desidera, scegliere **Autorizza** e quindi selezionare un account di amministratore Microsoft.

    Mover informerà l'utente sul numero di siti di SharePoint Online (o di SharePoint Online) e degli utenti individuati.
1. Scegliere **Continua l'installazione della** migrazione, selezionare Aggiungi **utenti,** quindi Individua e aggiungi utenti **automaticamente.**

    L'app Mover tenterà di mappare le unità dal percorso di origine in Google al percorso di destinazione in Microsoft 365. 

    Se un'unità non viene mappata automaticamente, aggiungere il relativo percorso di destinazione a un file CSV, che verrà utilizzato in seguito per eseguire la migrazione dell'unità condivisa in una raccolta documenti di SharePoint. 

1. In questo caso, è stato aggiunto un sito di SharePoint denominato File migrati e preso nota dell'URL per la pagina dei documenti. 
1. Abbiamo quindi creato un file CSV usando il formato Percorso di origine, Percorso di destinazione e Tag. 

    Per informazioni [dettagliate, vedere aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).

    Quando si aggiunge l'URL percorso di destinazione, rimuovere tutti gli elementi dopo Documenti condivisi. Ad esempio, questo URL completo non funziona: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Passare a: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Una volta pronto il file CSV, selezionare **Azioni di migrazione**, **Aggiungi** alla migrazione , Scegliere un file **da caricare**.
1. Passare al file CSV, selezionarlo, quindi scegliere **Apri.**
1. Selezionare le unità utente di cui si desidera eseguire la migrazione dei file, quindi scegliere **Avvia migrazione utenti**.
1. Esaminare le informazioni sulla migrazione, scegliere quando avviare la migrazione, accettare i Termini e **condizioni,** quindi selezionare **Continua.**

L'app Mover ti informerà al termine del processo di migrazione.