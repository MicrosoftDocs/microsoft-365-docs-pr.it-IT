---
title: Carichi di lavoro e scenari di Microsoft 365 per le aziende
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Caricare gli utenti dell’organizzazione nei carichi di lavoro produttivi di Microsoft 365 per le aziende.
ms.openlocfilehash: 692deeee652a4d27b8cc46a8e02890cccb8bb311
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633144"
---
# <a name="microsoft-365-for-enterprise-workloads-and-scenarios"></a>Carichi di lavoro e scenari di Microsoft 365 per le aziende

Per ottenere i vantaggi in termini di creatività e collaborazione di Microsoft 365 per le aziende, distribuire questi carichi di lavoro sull'infrastruttura di base:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint e OneDrive](sharepoint-online-onedrive-workload.md)

Vedere l'articolo sulla [migrazione](migration-microsoft-365-enterprise-workload.md) per una roadmap generale su come eseguire la migrazione di tutta l'organizzazione a Microsoft 365 per le aziende che includa i prodotti client di Microsoft Office, i prodotti locali di Office Server e i dispositivi basati su Microsoft Windows.

Gli scenari usano le funzionalità e i servizi di Microsoft 365 per le aziende in modo integrato per soddisfare le esigenze aziendali. 

Una di queste esigenze è assicurarsi che i dipendenti possano lavorare in modo produttivo e sicuro quando non sono direttamente connessi alla Intranet aziendale. Per una roadmap generale su come distribuire gli elementi dell'infrastruttura e favorire l'adozione da parte degli utenti remoti per i carichi di lavoro chiave, ad esempio Team ed Exchange Online, vedere lo scenario [Supportare i lavoratori remoti](empower-people-to-work-remotely.md).

Un'altra di queste esigenze è proteggere dati estremamente regolamentati archiviati in Microsoft 365. I dati estremamente regolamentati includono asset digitali, tra cui:

- Soggetti alle normative internazionali.
- I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.

Per proteggere questi dati da minacce interne ed esterne, vedere:

- [Teams per dati altamente regolamentati](secure-teams-highly-regulated-data-scenario.md)
- [Siti di SharePoint per dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md). 

Questi scenari rappresentano una guida per configurare un team di Microsoft Teams o un sito di SharePoint per archiviare in modo sicuro i dati più importanti.

Ecco i carichi di lavoro e gli scenari della guida di distribuzione generale di Microsoft 365 per le aziende:

![Carichi di lavoro e scenari della guida di distribuzione generale di Microsoft 365 per le aziende](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

Vedere la [raccolta di produttività Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary) per altri scenari. 

## <a name="foundation-infrastructure-prerequisites"></a>Prerequisiti dell’infrastruttura di base

*Idealmente*, è necessario distribuire i carichi di lavoro e gli scenari dopo aver configurato tutte le fasi [dell'infrastruttura di base](deploy-foundation-infrastructure.md). Per garantire che tutti i livelli sottostanti dell’infrastruttura di base siano in posizione per fornire integrazione, sicurezza e la migliore esperienza per gli utenti e i loro dispositivi.

| Fase | Risultato |
|:-------|:-----|
| Rete | La rete viene aggiornata per ottimizzare le prestazioni dei servizi cloud Microsoft 365. |
| Identità | L’identità è sincronizzata e messa al sicuro con l’autenticazione avanzata per gli account degli utenti e la protezione per gli account degli amministratori. |
| Windows 10 Enterprise | I computer che eseguono Windows 7 o Windows 8.1 possono eseguire l'aggiornamento a Windows 10 Enterprise e vengono installati nuovi dispositivi con Windows 10 Enterprise. |
| Office 365 ProPlus | Gli utenti di Microsoft Office esistenti possono eseguire l'aggiornamento a Office 365 ProPlus. |
| Gestione dei dispositivi mobili | I dispositivi possono essere registrati e gestiti. |
| Protezione delle informazioni | Le funzionalità di protezione delle informazioni di Microsoft 365 sono configurate e la riservatezza o le etichette di Azure Information Protection sono pronte per proteggere i documenti e la posta elettronica. |

Tenere presente che questa soluzione è ideale e può richiedere del tempo per essere pianificata, configurata, testata e verificata, in particolare in organizzazioni di grandi dimensioni con l'infrastruttura esistente e più sedi. Non è necessario completare queste fasi in tutte le sedi per sfruttare più velocemente il valore aziendale di Microsoft 365 per le aziende. 

Ecco alcuni dei carichi di lavoro abituali per effettuare immediatamente la distribuzione: 

- Dopo che la fase **Identità** dell'infrastruttura di base è stata implementata per gli utenti, molte organizzazioni distribuiscono:
  - [Office 365 ProPlus](office365proplus-infrastructure.md) associato a [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Office 365 ProPlus offre la sicurezza dell'autenticazione moderna e l'esperienza utente dell'ultima versione del client Microsoft Office. La migrazione dei file personali dell'utente a OneDrive consente di ridurre l'infrastruttura e non è più necessario supportare home directory e le unità.
  - [Exchange Online](exchangeonline-workload.md) in modo che gli utenti possano iniziare a usare la posta elettronica basata sul cloud.
- Se non è immediatamente necessario archiviare asset digitali altamente riservati nel cloud, distribuire [Microsoft Teams](teams-workload.md) e [SharePoint](sharepoint-online-onedrive-workload.md) per gli utenti prima della fase **Protezione delle informazioni**.

È necessario decidere come è meglio ordinare e distribuire la configurazione delle fasi dei prerequisiti dell’infrastruttura di base per soddisfare le esigenze aziendali.

### <a name="best-practice"></a>Procedura consigliata

È fortemente consigliabile distribuire e implementare la fase **Identità** dell'infrastruttura di base prima di caricare gli utenti su carichi di lavoro o scenari.

La fase **Identità** garantisce che l’identità basata sul cloud, solo cloud o sincronizzata con Active Directory Domain Services (AD DS) locali, contenga gli account di utente e computer e i gruppi per la gestione di accesso e autenticazione. L’autenticazione avanzata per tutti gli utenti, insieme alla protezione avanzata degli account di amministratore, è obbligatoria prima di immettere gli asset digitali dell'organizzazione nel cloud Microsoft 365.

Sebbene fondamentale e molto importante per le prestazioni complessive, l'implementazione della fase **Rete** può essere in corso durante il caricamento degli utenti sui carichi di lavoro, con la consapevolezza che il carico di lavoro e le prestazioni del servizio di Microsoft 365 miglioreranno nel tempo. Ciò vale soprattutto per le organizzazioni aziendali con più sedi e una combinazione di dispositivi periferici e connessioni Internet.
