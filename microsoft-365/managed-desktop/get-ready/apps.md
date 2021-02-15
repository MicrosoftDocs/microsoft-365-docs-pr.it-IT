---
title: App in Microsoft Managed Desktop
description: Spiega come vengono gestite le app, incluso come creare un pacchetto, distribuirle e supportarle.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840694"
---
# <a name="apps-in-microsoft-managed-desktop"></a>App in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>App in generale

Microsoft include alcune app chiave insieme alla licenza di Microsoft 365 E3 o E5 necessaria per partecipare a Microsoft Managed Desktop. Tuttavia, anche se forniamo queste app, hai ancora alcune responsabilità e azioni da completare.

Puoi anche distribuire altre app non Microsoft agli utenti per il self-service tramite il portale aziendale o un'installazione in background necessaria, usando la pipeline di distribuzione di Microsoft Intune. Se hai esperienza, puoi eseguire la migrazione delle app che ti servono; in alternativa, Microsoft Consulting Services (MCS) o fornitori non Microsoft saranno lieti di aiutarti con un progetto di creazione di pacchetti e migrazione. Per ulteriori informazioni sull'utilizzo di MCS, vedere [Utilizzo di Microsoft Consulting Services.](apps-MCS.md)


## <a name="apps-provided-by-microsoft"></a>App fornite da Microsoft

La licenza Microsoft Managed Desktop include versioni a 64 bit delle app in Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote). Per impostazione predefinita, le versioni A  to-Run di Microsoft Project e Visio non sono incluse, ma è possibile richiederle di essere aggiunte. Per ulteriori informazioni su queste app, vedere [Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Cosa fa Microsoft per supportare le app fornite

Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app di Microsoft 365 Apps for enterprise incluse. Le versioni A click-to-Run  di Microsoft Project e Visio non sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuire tali applicazioni in modo appropriato per l'organizzazione. Microsoft supporterà gli utenti di queste applicazioni tramite i canali di supporto di Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Cosa devi fare per supportare le app fornite

Esistono ancora alcune operazioni da eseguire con queste app:

- **Assegnare** licenze: si è responsabili di ottenere e assegnare le licenze appropriate agli utenti per Microsoft 365 Apps for enterprise.
- **Aggiungere utenti ai gruppi di** sicurezza: se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione appropriati. Gli amministratori IT sono inoltre responsabili del recupero delle licenze da tali utenti se lasciano l'azienda.
- Distribuire i componenti aggiuntivi di **Microsoft 365:** se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 Apps for enterprise, distribuirli centralmente come qualsiasi altra app di Windows 32. 

## <a name="apps-you-provide"></a>App fornite

Probabilmente hai altre app necessarie per le operazioni aziendali. Queste app possono essere distribuite solo nei dispositivi Microsoft Managed Desktop tramite la pipeline di distribuzione di Microsoft Intune. Se l'app ne ha bisogno, puoi inserirle in un pacchetto da un fornitore (che potrebbe essere un fornitore non Microsoft o Microsoft Consulting Services (MCS)) oppure, se hai i mezzi necessari, puoi creare il pacchetto manualmente. Questi pacchetti vengono quindi aggiunti al portale Microsoft Managed Desktop e assegnati ai gruppi di Azure Active Directory per attivare la distribuzione. 

Se attualmente distribuisci le tue app usando Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop può fornire una query per valutare le tue app e scoprire quali sono pronte per la migrazione a Microsoft Intune e quali potrebbero richiedere alcune regolazioni.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparazione delle tue app per l'inclusione in Microsoft Managed Desktop
Controlla le tue app, controllando:

- Nessuna delle app è proibita o ha un comportamento limitato, come descritto nei [requisiti delle app di Microsoft Managed Desktop.](https://aka.ms/app-req)
- Le app devono essere pronte per la gestione da parte di Microsoft Intune. Per altre informazioni su questo argomento, vedi Distribuzione di app di [Windows 10 con Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) e Aggiungi app a Microsoft [Intune.](https://docs.microsoft.com/intune/apps-add)
- Altri requisiti di pre-creazione del pacchetto, ad esempio la fornitura di codici di licenza, l'accordo con le condizioni di licenza e la pre-impostazione delle connessioni server.

### <a name="decide-how-to-package-apps"></a>Decidere come creare il pacchetto delle app

Alcuni editori di software indipendenti potrebbero richiedere che le tue app siano in pacchetto prima della distribuzione centralizzata. "Creazione di pacchetti" significa che il programma di installazione dell'app è configurato con impostazioni come codici di licenza, percorsi server remoti o collegamenti sul desktop in modo che l'app possa essere installata in background.

Sono disponibili tre opzioni per il pacchetto delle tue app: 


- Puoi creare il pacchetto delle app manualmente
- È possibile collaborare con un fornitore non Microsoft
- Puoi interagire con MCS per creare un pacchetto delle tue app. Collaborare con il rappresentante dell'account Microsoft. Per ulteriori informazioni, vedere [Utilizzo di Microsoft Consulting Services.](apps-MCS.md)



## <a name="deploying-apps"></a>Distribuzione di app

Indipendentemente dal metodo utilizzato per ottenere le app in pacchetto, una volta completata la procedura, è possibile seguire i passaggi descritti in Distribuire le app ai [dispositivi Desktop gestito Microsoft.](../get-started/deploy-apps.md)


