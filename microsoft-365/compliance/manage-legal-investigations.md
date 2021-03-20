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
description: Usare i casi di eDiscovery nel Centro sicurezza & conformità in Office 365 per gestire l'indagine legale dell'organizzazione.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903460"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gestire le indagini legali in Microsoft 365

Le organizzazioni hanno molti motivi per rispondere a un caso legale che coinvolge alcuni dirigenti o altri dipendenti dell'organizzazione. Ciò potrebbe comportare la ricerca e la conservazione rapidamente per ulteriori informazioni specifiche dell'indagine nei messaggi di posta elettronica, nei documenti, nelle conversazioni di messaggistica istantanea e in altri percorsi di contenuto utilizzati dagli utenti nelle attività lavorative quotidiane. È possibile eseguire queste e molte altre attività simili utilizzando gli strumenti del caso di eDiscovery nel Centro sicurezza e conformità.
  
**Vuoi sapere come Microsoft gestisce le indagini eDiscovery?** Ecco un [white paper tecnico che è](https://go.microsoft.com/fwlink/?linkid=852161) possibile scaricare in cui viene illustrato come vengono utilizzati gli stessi strumenti di ricerca e analisi per gestire il flusso di lavoro interno di eDiscovery.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gestire le indagini legali con i casi di eDiscovery

I casi di eDiscovery consentono di controllare chi può creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Utilizzare i casi per aggiungere membri e controllare i tipi di azioni che possono eseguire, impostare un blocco sui percorsi di contenuto rilevanti per un caso legale e utilizzare lo strumento Ricerca contenuto per cercare nei percorsi di archiviazione il contenuto che potrebbe rispondere al caso. È quindi possibile esportare e scaricare tali risultati per ulteriori indagini da parte di revisori esterni.
  
- [Gestire il flusso di lavoro di eDiscovery](./get-started-core-ediscovery.md) creando e utilizzando casi di eDiscovery per ogni indagine legale che l'organizzazione deve intraprendere.

- [Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md) per controllare chi può creare e gestire i casi di eDiscovery nell'organizzazione.

- [Configurare i limiti di conformità per](set-up-compliance-boundaries.md) controllare le posizioni dei contenuti degli utenti in cui i responsabili di eDiscovery possono eseguire ricerche.

- [Cercare contenuto](search-for-content.md) nell'organizzazione.

### <a name="use-scripts-for-advanced-scenarios"></a>Usare script per scenari avanzati

Come nella sezione precedente in cui sono elencati gli script per gli scenari di ricerca del contenuto &, sono stati creati anche alcuni script di PowerShell del Centro sicurezza e conformità per la gestione dei casi di eDiscovery.
  
- [Creare un report di blocco di eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) contenente informazioni su tutti i blocchi associati ai casi di eDiscovery nell'organizzazione.

- [Aggiungere cassette postali e percorsi di OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) per un elenco di utenti a un blocco di eDiscovery.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gestire indagini legali con la soluzione Advanced eDiscovery in Microsoft 365

La soluzione Advanced eDiscovery in Microsoft 365 si basa sulle funzionalità esistenti di eDiscovery e analisi in Office 365. Questa nuova soluzione, denominata *Advanced eDiscovery,* offre un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare contenuto reattivo alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica di blocco legale per comunicare con i custodi coinvolti in un caso.

Advanced eDiscovery richiede una sottoscrizione E5 per l'organizzazione di Microsoft 365 o Office 365. Per ulteriori informazioni sulle licenze, vedere [Set up Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Ecco una breve panoramica del flusso di lavoro incorporato in Advanced eDiscovery. Per ulteriori informazioni, vedere [Manage the Advanced eDiscovery workflow.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Crea un caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) per iniziare.

- [Gestire i custodi](managing-custodians.md) aggiungendoli a un caso e mettendo un blocco legale sul contenuto nella cassetta postale, nell'account OneDrive e in Microsoft Teams di cui sono membri.

- [Gestire le comunicazioni](managing-custodian-communications.md) con i custodi automatizzando il processo di notifica del blocco legale.

- [Indicizzare i dati del](processing-data-for-case.md) responsabile e correggere gli errori di indicizzazione in modo da poter raccogliere in modo efficace i dati per le indagini.

- [Raccogliere i dati](collecting-data-for-ediscovery.md) per un caso e [aggiungerli a un set di revisione per](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) ulteriori indagini.

- [Visualizzare](view-documents-in-review-set.md) documenti, [dati di query](review-set-search.md) ed elementi [tag](tagging-documents.md) in un set di revisioni.

- [Analizzare i dati dei casi](analyzing-data-in-review-set.md) con strumenti di analisi avanzati.

- [Esportare i dati del caso](exporting-data-ediscover20.md) per la revisione da parte di consulenti esterni.

- [Gestire i processi a esecuzione avanzata](managing-jobs-ediscovery20.md) in Advanced eDiscovery.