---
title: App in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: da5798b3412cb69580e5d9adc582f0ca4add1e3e
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289592"
---
# <a name="apps-in-microsoft-managed-desktop"></a>App in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>App in generale

Microsoft include alcune app principali insieme alla licenza Microsoft 365 E3 o E5 necessaria per partecipare a Microsoft Managed Desktop. Tuttavia, anche se vengono fornite queste app, sono ancora presenti determinate responsabilità e azioni da completare.

È inoltre possibile distribuire altre app non Microsoft agli utenti per il servizio self-service tramite il portale aziendale o un'installazione in background necessaria, tutti utilizzando la pipeline di distribuzione di Microsoft Intune. In caso di esperienza, è possibile eseguire la migrazione delle applicazioni necessarie. in alternativa, i Microsoft Consulting Services (MCS) o i fornitori non Microsoft saranno lieti di aiutarvi con un progetto di migrazione e di creazione di pacchetti. Per ulteriori informazioni sull'utilizzo di MCS, vedere [Working with Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>App fornite da Microsoft

In dotazione con la licenza Microsoft Managed Desktop sono disponibili versioni a 64 bit delle app di Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business e OneNote). Le versioni a portata di clic di Microsoft Project e Visio *non* sono incluse per impostazione predefinita, ma è possibile richiederne l'aggiunta. Per ulteriori informazioni su queste app, vedere [Install Microsoft Project o Microsoft Visio su Microsoft Managed Desktop Devices](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Cosa fa Microsoft per supportare le app che forniamo

Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app di Microsoft 365 incluse per Enterprise Apps. Le versioni a portata di clic di Microsoft Project e Visio *non* sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà ai gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuirle in modo appropriato per la propria organizzazione. Microsoft sosterrà gli utenti di queste applicazioni tramite i canali di supporto di Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Cosa devi fare per supportare le app che fornisci

Sono ancora necessarie alcune operazioni da eseguire con queste app:

- **Assegnare le licenze** : si è responsabili dell'ottenimento e dell'assegnazione delle licenze appropriate agli utenti per le app Microsoft 365 per Enterprise.
- **Aggiungere utenti ai gruppi di sicurezza** : se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione corretti. Gli amministratori IT sono anche responsabili del recupero delle licenze da tali utenti se lasciano la società.
- **Distribuire i componenti aggiuntivi di microsoft 365** -se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 per le applicazioni Enterprise, distribuire le app in modo centralizzato come qualsiasi altra applicazione Windows 32. 

## <a name="apps-you-provide"></a>App fornite

Naturalmente, è probabile che si disponga di una serie di altre app necessarie per le operazioni aziendali. Questi possono essere distribuiti solo ai dispositivi Microsoft Managed Desktop mediante la pipeline di distribuzione di Microsoft Intune. Se l'applicazione ne ha bisogno, è possibile farli impacchettare da un fornitore (che potrebbe essere un fornitore non Microsoft o Microsoft Consulting Services (MCS)) oppure se si dispone dei mezzi necessari, è possibile imballarli personalmente. Successivamente, aggiungere questi pacchetti al portale Microsoft Managed Desktop e assegnarli ai gruppi di Azure Active Directory per attivare la distribuzione. 

Se le app vengono attualmente distribuite tramite Microsoft endpoint Configuration Manager, Microsoft Managed Desktop può fornire una query per valutare le app e individuare quelle pronte per la migrazione a Microsoft Intune e quali potrebbero essere necessarie per la rettifica.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparare le proprie app per l'inclusione in Microsoft Managed Desktop
Esaminare le app, verificando:

- Nessuna delle app è vietata o ha un comportamento limitato, come descritto in [Microsoft Managed Desktop App requirements](https://aka.ms/app-req).
- Le app devono essere pronte per la gestione da Microsoft Intune. Per ulteriori informazioni, vedere [distribuzione di app di Windows 10 con Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) e [aggiungere app a Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Altri requisiti di preconfezionamento, ad esempio la fornitura di codici di licenza, il contratto con le condizioni di licenza e la preimpostazione delle connessioni server.

### <a name="decide-how-to-package-apps"></a>Decidere come eseguire il pacchetto di app

Alcuni fornitori di software indipendenti potrebbero richiedere che le app siano inserite in un pacchetto prima di essere distribuite in modo centralizzato. "Packaging" indica che il programma di installazione dell'app è configurato con impostazioni come le chiavi di licenza, le posizioni dei server remoti o i collegamenti desktop in modo che sia possibile installare l'app in background.

Sono disponibili tre opzioni per ottenere i pacchetti delle app: 


- È possibile creare pacchetti per le app
- È possibile collaborare con un fornitore non Microsoft
- È possibile coinvolgere MCS per il pacchetto delle app. Collaborare con il proprio rappresentante dell'account Microsoft. Per ulteriori informazioni, vedere [Working with Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Distribuzione di app

Indipendentemente dal metodo utilizzato per ottenere le app inserite, una volta completata, si è pronti a seguire la procedura descritta in [deploy Apps to Microsoft Managed Desktop Devices](../get-started/deploy-apps.md).


