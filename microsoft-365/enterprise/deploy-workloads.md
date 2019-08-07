---
title: Carichi di lavoro e scenari di Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Caricare gli utenti dell’organizzazione per la produttività dei carichi di lavoro di Microsoft 365 Enterprise.
ms.openlocfilehash: 0c81f93b117645974e93870f20d4dfb469dae3ac
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054928"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a>Carichi di lavoro e scenari di Microsoft 365 Enterprise

Per ottenere i vantaggi di creatività e collaborazione di Microsoft 365 Enterprise, distribuire questi carichi di lavoro sull'infrastruttura di base:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

Consultare il carico di lavoro della [migrazione](migration-microsoft-365-enterprise-workload.md) per una roadmap generale per eseguire la migrazione di tutta l'organizzazione a Microsoft 365 Enterprise, che include i prodotti client di Microsoft Office, i prodotti locali di Office Server e i dispositivi Microsoft basati su Windows.

Gli scenari usano le funzionalità e i servizi di Microsoft 365 Enterprise in modo integrato per soddisfare le esigenze aziendali. Una di queste è proteggere dati estremamente regolamentati archiviati in Microsoft 365. I dati estremamente regolamentati includono asset digitali, tra cui:

- Soggetti alle normative internazionali.
- I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.

Per proteggere questi dati da minacce interne ed esterne, leggere le istruzioni nei [siti Microsoft Teams e SharePoint Online per dati estremamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md). Questo scenario rappresenta una guida per configurare un sito di SharePoint Online o un team di Microsoft Teams per archiviare in modo sicuro i dati più importanti.

Ecco i carichi di lavoro e gli scenari della guida di distribuzione generale di Microsoft 365 Enterprise:

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

Per altri scenari, vedere la [raccolta di produttività Microsoft 365](https://www.microsoft.com/microsoft-365/success/). In questa pagina Web digitare una stringa di ricerca o fare **clic su** filtro in base a e specificare industria, ruoli (reparti) e prodotti in Microsoft 365.

Dai risultati, fare clic su una scheda per vedere i passaggi da eseguire.

## <a name="foundation-infrastructure-prerequisites"></a>Prerequisiti dell’infrastruttura di base

*Idealmente*, è necessario distribuire i carichi di lavoro e gli scenari dopo aver configurato tutte le fasi [dell'infrastruttura di base](deploy-foundation-infrastructure.md). Per garantire che tutti i livelli sottostanti siano in posizione per fornire integrazione, sicurezza e la migliore esperienza per gli utenti e i loro dispositivi.

| Fase | Risultato |
|:-------|:-----|
| Rete | La rete viene aggiornata per ottimizzare le prestazioni dei servizi cloud Microsoft 365. |
| Identità | L’identità è sincronizzata e messa al sicuro con l’autenticazione avanzata per gli account degli utenti e la protezione per gli account degli amministratori. |
| Windows 10 Enterprise | I computer che eseguono Windows 7 o Windows 8.1 possono eseguire l'aggiornamento a Windows 10 Enterprise e vengono installati nuovi dispositivi con Windows 10 Enterprise. |
| Office 365 ProPlus | Gli utenti di Microsoft Office esistenti possono eseguire l'aggiornamento a Office 365 ProPlus. |
| Gestione dei dispositivi mobili | I dispositivi possono essere registrati e gestiti. |
| Protezione delle informazioni | Le funzionalità di sicurezza di Office 365 sono abilitate e la riservatezza o le etichette di Azure Information Protection sono pronte per proteggere i documenti. |

Tenere presente che questa soluzione è ideale e può richiedere del tempo per essere pianificata, configurata, testata e verificata, in particolare in organizzazioni di grandi dimensioni con l'infrastruttura esistente e più sedi. Non è necessario mettere tutti i livelli in posizione in tutte le sedi per ottenere più velocemente il valore di business da Microsoft 365 Enterprise. 

Ecco alcuni dei carichi di lavoro abituali per effettuare immediatamente la distribuzione: 

- Dopo che il livello **Identità** dell'infrastruttura di base è stata implementata per gli utenti, molte organizzazioni distribuiscono:
  - [Office 365 ProPlus](office365proplus-infrastructure.md) associato a [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Office 365 ProPlus offre la sicurezza dell'autenticazione moderna e l'esperienza utente dell'ultima versione del client Microsoft Office. La migrazione dei file personali dell'utente a OneDrive for Business riduce l’infrastruttura e la necessità di supportare le home directory e le unità.
  - [Exchange Online](exchangeonline-workload.md) in modo che gli utenti possano iniziare a usare la posta elettronica basata sul cloud.
- Se non si ha l'esigenza immediata di archiviare asset digitali altamente regolamentati nel cloud, distribuire [Microsoft Teams](teams-workload.md) e [SharePoint Online](sharepoint-online-onedrive-workload.md) per gli utenti prima del livello **Information protection**.

È necessario decidere come è meglio ordinare e distribuire la configurazione delle fasi dei prerequisiti dell’infrastruttura di base per soddisfare al meglio le esigenze aziendali.

### <a name="best-practice"></a>Procedura consigliata

È fortemente consigliabile distribuire e implementare la fase **Identità** dell'infrastruttura di base prima di caricare gli utenti su carichi di lavoro o scenari.

La fase **Identità** garantisce che l’identità basata sul cloud, solo cloud o sincronizzata con Active Directory Domain Services (AD DS) locali, contenga gli account di utente e computer e i gruppi per la gestione di accesso e autenticazione. L’autenticazione avanzata per tutti gli utenti, insieme alla protezione avanzata degli account di amministratore, è obbligatoria prima di immettere gli asset digitali dell'organizzazione nel cloud Microsoft 365.

Sebbene fondamentale e molto importante per le prestazioni complessive, l'implementazione della fase **Networking** sulla rete può essere in corso durante il caricamento degli utenti sui carichi di lavoro, con la consapevolezza che l’applicazione Microsoft 365 e le prestazioni del servizio miglioreranno nel tempo.

Ciò vale soprattutto per le organizzazioni aziendali con più sedi e una combinazione di dispositivi periferici e connessioni Internet.
