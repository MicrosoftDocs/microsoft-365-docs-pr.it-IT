---
title: Team per un progetto interno di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: in che modo Contoso ha utilizzato un team per i dati altamente regolamentati per un progetto Top-Secret per sviluppare una nuova famiglia di prodotti e servizi.'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068028"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team per un progetto interno di Contoso Corporation

Dopo un Executive fuori sede, il CEO di Contoso ha ordinato lo sviluppo di una nuova famiglia di prodotti e servizi che potrebbe raddoppiare gli utili di Contoso nei prossimi cinque anni. Il progetto Top-Secret per sviluppare il piano aziendale, ingegneristico e di mercato è stato denominato **Project 2x** e il personale chiave in tutta la società sono stati reclutati. 

Le sequenze temporali per la ricerca e lo sviluppo sono state rigorose, il che significa che la collaborazione deve essere efficiente e fornire riunioni sicure, conversazioni e archiviazione dei file.

I risultati finali risultanti per Project 2X sono stati piani aziendali, specifiche di prodotti e di ingegneria e materiali di marketing e pianificazioni in formato Word, Excel e PowerPoint. 

A causa della loro natura sensibile, l'accesso a questi file è stato:

- Limitato ai membri del team di Project 2X.
- Protetto con un criterio di prevenzione della perdita di dati (DLP) per impedire ai membri del team di Project 2X di condividerli all'esterno del team.
- Crittografati e protetti con le autorizzazioni per consentire l'accesso solo ai membri del team di Project 2X, anche se i file sono stati distribuiti all'esterno di contoso.

Il personale IT di Contoso ha utilizzato un [team per i dati altamente regolamentati](secure-teams-highly-regulated-data-scenario.md) per Project 2x e questi passaggi.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Passaggio 1: creazione di un team privato e blocco del sito di SharePoint sottostante

Per proteggere l'accesso al sito di SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i [criteri di accesso di SharePoint consigliati](sharepoint-file-access-policies.md).

Successivamente, un amministratore IT di Contoso ha creato un nuovo team privato denominato Project 2X e aggiunto gli account utente del personale di Project 2X come membri.

Successivamente, sono state configurate le impostazioni di autorizzazione aggiuntive per il sito per impedire che Project 2X condivida l'accesso al sito e impedire ad altri utenti di richiedere l'accesso al sito.

Per informazioni dettagliate sulla configurazione, vedere [impostazioni di SharePoint per un team fortemente regolato](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Passaggio 2: configurazione di un criterio DLP e del sito sottostante per un'etichetta di conservazione 

Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **molto riservata** esistente alla sezione **Documents** del sito di SharePoint sottostante del team di Project 2x.

Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Project 2x** che:

- Utilizza l'etichetta di conservazione di Office 365 estremamente riservata.
- Blocca gli utenti quando tentano di condividere un file nel team di Project 2X all'esterno di contoso.

Per informazioni dettagliate sulla configurazione, vedere [Protect Files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>Passaggio 3: creazione di un'etichetta di riservatezza di Office 365 per il team di Project 2X

Gli amministratori di Contoso hanno creato una nuova etichetta di riservatezza di Office 365 denominata **Project 2x** che:

- Richiede la crittografia.
- Consente le autorizzazioni di creazione condivisa per il gruppo Project 2X Office 365.

Ecco la configurazione risultante del team di Project 2X.

![La configurazione risultante del team di Project 2X](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
I file nella sezione Documents del progetto sottostante 2X sito di SharePoint sono stati protetti da:

- Le autorizzazioni per il sito, che consentono l'accesso solo ai membri del gruppo Project 2X Office 365.
- L'etichetta di conservazione estremamente riservata, che viene assegnata automaticamente ai nuovi file.
- Un criterio DLP che utilizza l'etichetta di conservazione e le impostazioni estremamente riservate che impediscono la condivisione dei file con gli utenti esterni.
- L'etichetta di riservatezza del progetto 2X, con la crittografia e le autorizzazioni che viaggiano con il file se sono state spostate o copiate dal sito.

Di seguito è riportato un esempio di un file archiviato nel sito di progetto 2X sottostante con l'etichetta di conservazione fortemente regolamentata e l'etichetta di riservatezza del progetto 2X assegnata.

![Un esempio di un file archiviato nel sito di progetto 2X sottostante](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Passaggio 4: formazione dei membri del team di Project 2X

Il personale di sicurezza Contoso ha preparato i membri del team del progetto 2X in un corso obbligatorio che ha eseguito i seguenti controlli:

- Come accedere al nuovo team di Project 2X, utilizzare riunioni e chat e come collaborare ai file del team.
- Come creare nuovi file nel team e caricare nuovi file creati localmente.
- Dimostrazione del modo in cui il criterio DLP blocca la condivisione esterna dei file.
- Come assegnare etichette ai file con l'etichetta di sensitivity di Project 2X.
- Dimostrazione del modo in cui l'etichetta del progetto 2X protegge un file anche quando lascia il team.

Il risultato finale è un ambiente sicuro in cui i membri del team di Project 2X hanno collaborato in un ambiente sicuro per chat, riunioni e file.

In una coppia di istanze, Project 2X membri del team hanno scaricato i file protetti dall'etichetta Project 2X su un'unità locale per il lavoro offline. Tuttavia, dopo che sono state richieste le credenziali per l'apertura, si sono accorti del loro errore e li hanno eliminati.

A causa dell'ambiente di collaborazione dei team e delle funzionalità di sicurezza di Microsoft 365, i dettagli di Project 2X sono stati mantenuti segreti per tutta la durata del progetto. Contoso ha annunciato i propri piani ed è in fase di implementazione dei nuovi prodotti e servizi per la gioia dei suoi clienti e investitori e per il disappunto dei suoi concorrenti.

## <a name="next-step"></a>Passaggio successivo

[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.

## <a name="see-also"></a>Vedere anche

[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)
