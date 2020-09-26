---
title: Gestire le indagini legali in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Utilizzare i casi di eDiscovery nel centro sicurezza & compliance in Office 365 per gestire le indagini legali dell'organizzazione.
ms.openlocfilehash: edc9835cdbefa611af4c0906be5d3e1d0404c635
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285652"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gestire le indagini legali in Microsoft 365

Le organizzazioni hanno molti motivi per rispondere a un caso legale che coinvolge alcuni dirigenti o altri dipendenti dell'organizzazione. Ciò può comportare una rapida individuazione e conservazione per ulteriori informazioni specifiche per le indagini in messaggi di posta elettronica, documenti, conversazioni di messaggistica istantanea e altri percorsi di contenuto utilizzati dalle persone nelle attività quotidiane. È possibile eseguire queste e molte altre attività simili utilizzando gli strumenti case di eDiscovery nel centro sicurezza e conformità.
  
**Volete sapere in che modo Microsoft gestisce le indagini di eDiscovery?** Ecco un [white paper tecnico](https://go.microsoft.com/fwlink/?linkid=852161) che è possibile scaricare che spiega come vengono utilizzati gli stessi strumenti di ricerca e analisi per gestire il flusso di lavoro interno di eDiscovery.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gestire le indagini legali con i casi di eDiscovery

i casi di eDiscovery consentono di controllare gli utenti autorizzati a creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Utilizzare i casi per aggiungere membri e controllare i tipi di azioni che possono eseguire, inserire un'esenzione nei percorsi di contenuto rilevanti per un caso legale e utilizzare lo strumento di ricerca contenuto per cercare i contenuti che potrebbero rispondere al caso. È inoltre possibile esportare e scaricare i risultati per ulteriori indagini da parte di revisori esterni.
  
- [Gestire il flusso di lavoro di eDiscovery](ediscovery-cases.md) mediante la creazione e l'utilizzo di casi di eDiscovery per ogni indagine legale che l'organizzazione deve intraprendere 
    
- [Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md) per controllare chi può creare e gestire i casi di eDiscovery nell'organizzazione 
    
- [Impostare i limiti di conformità](tagging-and-assessment-in-advanced-ediscovery.md) per controllare i percorsi di contenuto utente che i responsabili di eDiscovery possono eseguire ricerche 
    
- [Ricerca di contenuti](search-for-content.md) nell'organizzazione 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare gli script per gli scenari avanzati

Analogamente alla sezione precedente in cui sono elencati gli script per gli scenari di ricerca del contenuto, sono stati creati anche script di PowerShell per la sicurezza & Compliance Center per la gestione dei casi di eDiscovery.
  
- [Creare un rapporto di blocco di eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nell'organizzazione 
    
- [Aggiungere cassette postali e posizioni OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) per un elenco di utenti a un blocco eDiscovery 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gestire le indagini legali con la soluzione avanzata di eDiscovery in Microsoft 365

La soluzione avanzata di eDiscovery in Microsoft 365 si basa sulle funzionalità esistenti di eDiscovery e analisi di Office 365. Questa nuova soluzione, denominata *Advanced eDiscovery*, offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare il contenuto rispondente alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica per la conservazione legale per comunicare con i depositari coinvolti in un caso.

Advanced eDiscovery richiede un abbonamento E5 per l'organizzazione Microsoft 365 o Office 365. Per ulteriori informazioni sulle licenze, vedere [Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Ecco una breve panoramica del flusso di lavoro incorporato in Advanced eDiscovery. Per ulteriori informazioni, vedere [esplorare il flusso di lavoro di Advanced eDiscovery](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow).

- [Creare un caso](create-new-ediscovery-case.md) per iniziare

- [Gestire i depositari](managing-custodians.md) aggiungendoli a un caso e inserendo una conservazione legale sul contenuto nella propria cassetta postale, nell'account OneDrive e nei team di Microsoft che sono membri di

- [Gestire le comunicazioni](managing-custodian-communications.md) con i depositari automatizzando il processo di notifica per la conservazione legale

- [Indicizzare i dati dei depositari](processing-data-for-case.md) e correggere gli errori di indicizzazione in modo da poter raccogliere effettivamente i dati per le indagini

- [Raccogliere i dati](collecting-data-for-ediscovery.md) per un caso e aggiungerli [a un set di revisione](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) per ulteriori indagini

- [Visualizzare ](view-documents-in-review-set.md) i documenti, i dati di [query](review-set-search.md) e gli elementi di [tag](tagging-documents.md) in un set di Revisione

- [Analizzare i dati del caso](analyzing-data-in-review-set.md) con gli strumenti avanzati di analisi

- [Esportare i dati dei casi](exporting-data-ediscover20.md) per la revisione da parte di consulenti esterni

- [Gestire i processi a esecuzione prolungata](managing-jobs-ediscovery20.md) in Advanced eDiscovery
