---
title: Team isolato per un progetto top-secret di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: in che modo Contoso ha usato un team con isolamento della sicurezza per un progetto top-secret per sviluppare una nuova famiglia di prodotti e servizi.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029017"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team isolato per un progetto top-secret di Contoso Corporation

Dopo un executive offsite, il CEO di Contoso ha ordinato lo sviluppo di una nuova famiglia di prodotti e servizi che potrebbe raddoppiare i profitti di Contoso nei prossimi cinque anni. Il progetto top-secret per sviluppare il piano aziendale, ingegneristico e di mercato è stato denominato **Project 2X** e sono stati assunti personale chiave in tutta l'azienda. 

Le tempistiche per la ricerca e lo sviluppo erano rigide, il che significava che la collaborazione doveva essere efficiente e garantire riunioni sicure, conversazioni in corso e archiviazione di file.

I risultati finali risultanti per Project 2X sono i piani aziendali, le specifiche di prodotto e di progettazione, i materiali e le pianificazioni di marketing sotto forma di file di word, Excel e PowerPoint. 

A causa della loro natura sensibile, l'accesso a questi file è stato:

- Limitato a Project membri del team 2X e ai dirigenti senior.
- Crittografato e protetto con autorizzazioni per consentire l'accesso solo Project membri del team 2X e dirigenti senior, anche se i file sono stati distribuiti all'esterno delle cartelle protette.

Il personale IT di Contoso ha utilizzato [un team](secure-teams-security-isolation.md) con isolamento della sicurezza Project 2X e questi passaggi.

## <a name="step-1-created-a-private-team"></a>Passaggio 1: Creare un team privato

Innanzitutto, per proteggere l'accesso al sito SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i criteri di SharePoint [di accesso.](../security/office-365-security/sharepoint-file-access-policies.md)

Successivamente, un amministratore IT di Contoso ha creato un nuovo team privato denominato Project 2X e aggiunto gli account utente di Project 2X come membri. Hanno anche configurato il team in modo che solo Project proprietari del team 2X possano creare canali privati.

Per informazioni dettagliate sulla configurazione, vedere [Create a private team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Passaggio 2: Creare un'etichetta di riservatezza per il team Project 2X

Gli amministratori di Contoso hanno creato una nuova etichetta di riservatezza denominata **Project 2X** che:

- Crittografia abilitata.
- Autorizzazioni Co-Author per il gruppo Project 2X Microsoft 365 gruppo.
- Autorizzazioni visualizzatore consentite per il gruppo Senior Leadership.
- Accesso bloccato ai dispositivi non gestiti.

I file nella **sezione Documents** del sito Project 2X SharePoint sono stati protetti da:

- Autorizzazioni del sito, che consentono solo autorizzazioni complete per i membri del gruppo Project 2X Microsoft 365 e autorizzazioni di lettura per il gruppo Senior Leadership.
- L Project di riservatezza 2X, con crittografia e autorizzazioni che viaggiano con il file se viene spostato o copiato dal sito.

Per i dettagli della configurazione, vedere [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Passaggio 3: Configurare il sito SharePoint sottostante

Innanzitutto, per proteggere l'accesso al sito SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i criteri di SharePoint [di accesso.](../security/office-365-security/sharepoint-file-access-policies.md)

Successivamente, hanno configurato impostazioni di autorizzazione aggiuntive per il sito:

- Per impedire Project membri del gruppo 2X di condividere l'accesso al sito. Per i dettagli di configurazione, vedere [SharePoint per un team con isolamento della sicurezza.](secure-teams-security-isolation.md#sharepoint-settings)
- Per autorizzazioni di lettura per il gruppo Senior Leadership.

Successivamente, hanno configurato impostazioni di autorizzazione aggiuntive per il sito per impedire Project membri del gruppo 2X di condividere l'accesso al sito. 

Durante la creazione dei canali privati Project 2X, il proprietario del gruppo ha disabilitato la condivisione guest e ha impostato il collegamento di condivisione predefinito sul **valore Persone** specifiche.

Ecco la configurazione risultante del team Project 2X con isolamento della sicurezza.

![La configurazione risultante del team Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Passaggio 4: formazione Project membri del team 2X

Il personale di sicurezza di Contoso ha formato Project membri del team 2X in un corso obbligatorio che li ha attraversati:

- Come accedere al nuovo team Project 2X, usare riunioni e chat e come collaborare ai file del team.
- Come creare nuovi file nel team e caricare nuovi file creati localmente.
- Come etichettare i file con l Project di riservatezza 2X.
- Dimostrazione di come l Project etichetta 2X protegge un file anche quando lascia il team.

Il risultato finale è stato un ambiente sicuro in cui Project membri del team 2X hanno collaborato in un ambiente sicuro per chat, riunioni e file.

Ecco un esempio di un file archiviato nel sito Project 2X sottostante con l'etichetta di riservatezza Project 2X assegnata.

![Esempio di file archiviato nel sito Project 2X sottostante](../media/contoso-team-for-top-secret-project-example.png)

In un paio di casi, Project membri del team 2X hanno scaricato file protetti dall'etichetta Project 2X in un'unità locale per il lavoro offline. 

Tuttavia, dopo aver richiesto le credenziali all'apertura, si sono resi conto dell'errore e le hanno eliminate.

A causa dell'ambiente di collaborazione di Teams e delle funzionalità di sicurezza di Microsoft 365, i dettagli di Project 2X sono stati mantenuti segreti per tutta la durata del progetto. Contoso ha annunciato i propri piani ed è in corso l'implementazione dei nuovi prodotti e servizi per la soddisfazione dei clienti e degli investitori e il disappunto dei concorrenti.

## <a name="next-step"></a>Passaggio successivo

[Distribuire un team con isolamento della sicurezza](secure-teams-security-isolation.md) nell'organizzazione.

