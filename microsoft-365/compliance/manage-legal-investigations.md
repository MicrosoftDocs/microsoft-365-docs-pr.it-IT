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
description: Usare i casi di eDiscovery nel Centro sicurezza & conformità in Office 365 per gestire le indagini legali dell'organizzazione.
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840705"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gestire le indagini legali in Microsoft 365

Le organizzazioni hanno molti motivi per rispondere a un caso legale che coinvolge alcuni dirigenti o altri dipendenti dell'organizzazione. Ciò potrebbe comportare l'individuazione e la conservazione rapida di ulteriori informazioni specifiche dell'indagine in posta elettronica, documenti, conversazioni di messaggistica istantanea e altri percorsi di contenuto utilizzati dalle persone nelle loro attività lavorative quotidiane. È possibile eseguire queste e molte altre attività simili utilizzando gli strumenti del caso di eDiscovery nel Centro sicurezza e conformità.
  
**Vuoi sapere in che modo Microsoft gestisce le indagini di eDiscovery?** Ecco un white [paper tecnico che è](https://go.microsoft.com/fwlink/?linkid=852161) possibile scaricare in cui viene illustrato come vengono utilizzati gli stessi strumenti di ricerca e analisi per gestire il flusso di lavoro interno di eDiscovery.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gestire le indagini legali con i casi di eDiscovery

I casi di eDiscovery consentono di controllare chi può creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Utilizzare i casi per aggiungere membri e controllare i tipi di azioni che possono eseguire, impostare un blocco sui percorsi di contenuto rilevanti per un caso legale e utilizzare lo strumento Ricerca contenuto per cercare nei percorsi di blocco il contenuto che potrebbe rispondere al caso. È quindi possibile esportare e scaricare tali risultati per ulteriori indagini da parte di revisori esterni.
  
- [Gestire il flusso di lavoro di eDiscovery](ediscovery-cases.md) creando e utilizzando casi di eDiscovery per ogni indagine legale che l'organizzazione deve intraprendere.

- [Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md) per controllare chi può creare e gestire i casi di eDiscovery nell'organizzazione.

- [Impostare i limiti di conformità per](set-up-compliance-boundaries.md) controllare i percorsi dei contenuti degli utenti che i responsabili di eDiscovery possono cercare.

- [Cercare contenuto](search-for-content.md) nell'organizzazione.

### <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare script per scenari avanzati

Come nella sezione precedente in cui sono elencati gli script per gli scenari di ricerca di contenuto, sono stati creati anche alcuni script di PowerShell del Centro sicurezza & conformità per facilitare la gestione dei casi di eDiscovery.
  
- [Creare un report di blocco di eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) contenente informazioni su tutti i blocchi associati ai casi di eDiscovery nell'organizzazione.

- [Aggiungere cassette postali e percorsi di OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) per un elenco di utenti a un blocco di eDiscovery.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gestire le indagini legali con la soluzione Advanced eDiscovery in Microsoft 365

La soluzione Advanced eDiscovery in Microsoft 365 si basa sulle funzionalità eDiscovery e analisi esistenti in Office 365. Questa nuova soluzione, denominata *Advanced eDiscovery,* offre un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare contenuti reattivi alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica della conservazione per comunicare con i responsabile coinvolti in un caso.

Advanced eDiscovery richiede un abbonamento a E5 per l'organizzazione di Microsoft 365 o Office 365. Per ulteriori informazioni sulle licenze, vedere [Set up Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

Ecco una rapida panoramica del flusso di lavoro incorporato in Advanced eDiscovery. Per ulteriori informazioni, vedere [Gestire il flusso di lavoro advanced eDiscovery.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Creare un caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) per iniziare.

- [Gestire i responsabile](managing-custodians.md) aggiungendoli a un caso e impostando un blocco legale sul contenuto nella cassetta postale, nell'account OneDrive e in Microsoft Teams di cui sono membri.

- [Gestire le comunicazioni](managing-custodian-communications.md) con i responsabile automatizzando il processo di notifica della conservazione a mano a mano.

- [Indicizzare i dati dei depositario](processing-data-for-case.md) e correggere gli errori di indicizzazione in modo da poter raccogliere in modo efficace i dati per le indagini.

- [Raccogliere i dati](collecting-data-for-ediscovery.md) per un caso e [aggiungerli a un insieme da rivedere per](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) ulteriori indagini.

- [Consente di](view-documents-in-review-set.md) visualizzare documenti, dati di [query](review-set-search.md) ed [elementi tag](tagging-documents.md) in un insieme da rivedere.

- [Analizzare i dati del caso](analyzing-data-in-review-set.md) con strumenti di analisi avanzati.

- [Esportare i dati del caso](exporting-data-ediscover20.md) per la revisione da parte di consulenti esterni.

- [Gestire i processi di lunga durata](managing-jobs-ediscovery20.md) in Advanced eDiscovery.
