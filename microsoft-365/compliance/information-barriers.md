---
title: Panoramica delle barriere informative
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare le barriere informative per garantire la conformità della comunicazione tramite Microsoft teams all'interno dell'organizzazione.
ms.openlocfilehash: c4a9213e74129126da0cbc41b7bc210a10b34db2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083733"
---
# <a name="information-barriers"></a>Barriere informative

## <a name="overview"></a>Panoramica

I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione. Tuttavia, si supponga di voler limitare le comunicazioni tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione. In alternativa, è possibile limitare le comunicazioni tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne. Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi è possibile limitare le comunicazioni tra i gruppi di utenti specifici, se necessario. Con barriere informative, è possibile! 

Gli ostacoli alle informazioni stanno per essere implementati ora, a partire da Microsoft teams. Presupponendo che la [sottoscrizione](#required-licenses-and-permissions) includa barriere informative, un amministratore di conformità o un amministratore delle informazioni barriere può definire criteri per consentire o impedire le comunicazioni tra gruppi di utenti in Microsoft teams. I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:

- Un trader diurno non può chiamare qualcuno del team di marketing
- Il personale finanziario che lavora su informazioni aziendali riservate non è in grado di ricevere chiamate da determinati gruppi all'interno dell'organizzazione
- Un team interno con materiale segreto commerciale non può chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.
- Un team di ricerca può solo chiamare o chattare online con un team di sviluppo del prodotto

Per tutti questi scenari di esempio e altro ancora, è possibile definire i criteri di barriera delle informazioni per impedire o consentire le comunicazioni in Microsoft teams. Tali criteri possono impedire agli utenti di effettuare chiamate o chattare con coloro che non devono o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft teams. Con i criteri di protezione delle informazioni in vigore, quando gli utenti interessati da tali criteri tentano di comunicare con altri membri di Microsoft teams, vengono eseguiti i controlli per impedire (o consentire) la comunicazione (come definito dai criteri di barriera delle informazioni). Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere [barriere informative in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> Attualmente, le barriere informative non si applicano alle comunicazioni di posta elettronica o alla condivisione di file tramite SharePoint Online o OneDrive. Inoltre, le barriere informative sono indipendenti dai [limiti di conformità](tagging-and-assessment-in-advanced-ediscovery.md).<p>Prima di definire e applicare i criteri di barriera delle informazioni, assicurarsi che l'organizzazione non disponga di [Criteri rubrica di Exchange](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) in vigore. (Le barriere informative si basano sui criteri della rubrica). 

## <a name="what-happens-with-information-barriers"></a>Cosa accade con barriere informative

Quando vengono attivati i criteri di protezione delle informazioni, gli utenti che non devono comunicare con altri utenti specifici non saranno in grado di trovare, selezionare, chattare o chiamare tali utente. Con barriere informative, sono disponibili controlli che impediscono la comunicazione non autorizzata.

Inizialmente, gli ostacoli alle informazioni si applicano solo alle chat e ai canali di Microsoft teams. In Microsoft teams, i criteri barriera di informazioni determinano e impediscono i seguenti tipi di comunicazioni non autorizzate:
- Ricerca di un utente
- Aggiunta di un membro a un team
- Avvio di una sessione di chat con un utente
- Avvio di una chat di gruppo
- Invitare un utente a partecipare a una riunione
- Condivisione di una schermata
- Effettuazione di una chiamata 

Se le persone coinvolte sono incluse in un criterio barriera informativo per impedire l'attività, non saranno in grado di procedere. Inoltre, potenzialmente, tutti gli elementi inclusi in un criterio barriera informativo possono essere bloccati dalla comunicazione con altri utenti di Microsoft teams. Quando le persone coinvolte nei criteri di barriera delle informazioni fanno parte dello stesso team o chat di gruppo, potrebbero essere rimosse dalle sessioni di chat e potrebbe non essere consentita un'ulteriore comunicazione con il gruppo.

Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere [barriere informative in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

Gli ostacoli alle informazioni stanno per essere implementati e sono inclusi negli abbonamenti, ad esempio:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 E5 Information Protection and Compliance

Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Per [definire o modificare criteri di barriera delle informazioni](information-barriers-policies.md), è necessario essere assegnati a uno dei ruoli seguenti:

- Microsoft 365 amministratore globale
- Amministratore globale di Office 365
- Amministratore di conformità
- IB Compliance Management (questo è un nuovo ruolo)

Per ulteriori informazioni sui ruoli e le autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).

È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri di barriera delle informazioni. Anche se vengono forniti diversi esempi di cmdlet di PowerShell nell' [articolo How-to](information-barriers-policies.md), è necessario conoscere ulteriori dettagli, ad esempio i parametri, per l'organizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Per ulteriori informazioni, vedere barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [Visualizzare gli attributi che è possibile utilizzare per i criteri di barriera delle informazioni](information-barriers-attributes.md)

- [Definire i criteri per le barriere informative](information-barriers-policies.md)

- [Modificare (o rimuovere) i criteri di barriera delle informazioni](information-barriers-edit-segments-policies.md.md) 

