---
title: Informazioni sulle barriere di informazioni in Microsoft 365
description: Usare le barriere in fatto di informazioni per garantire la conformità delle comunicazioni con Microsoft Teams all'interno dell'organizzazione.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ef09fbf7a517950ae182472e4b4d5ef896d65e5
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126543"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Informazioni sulle barriere di informazioni in Microsoft 365

I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione. Si supponga tuttavia di voler limitare la comunicazione e la collaborazione tra due gruppi per evitare che si verifichi un conflitto di interesse nell'organizzazione. In caso contrario, è possibile limitare la comunicazione e la collaborazione tra alcune persone all'interno dell'organizzazione per proteggere le informazioni interne. Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi esiste un modo per limitare la comunicazione e la collaborazione tra gruppi specifici di utenti quando necessario? Con le barriere in fatto di informazioni, è possibile!

Microsoft Teams, SharePoint Online e OneDrive for Business supportano le barriere in fatto di informazioni. Presupponendo che [l'abbonamento](#required-licenses-and-permissions) includa barriere in fatto di informazioni, un amministratore di conformità o un amministratore delle barriere di informazioni può definire criteri per consentire o impedire le comunicazioni tra gruppi di utenti in Microsoft Teams. I criteri delle barriere di informazioni possono essere usati in situazioni come queste:

- L'utente nel gruppo di distribuzione giornaliera non deve comunicare o condividere file con il team di marketing
- Il personale finanziario che lavora su informazioni aziendali riservate non deve comunicare o condividere file con determinati gruppi all'interno dell'organizzazione
- Un team interno con materiale segreto commerciale non deve chiamare o chattare online con persone in determinati gruppi all'interno dell'organizzazione
- Un team di ricerca deve chiamare o chattare solo online con un team di sviluppo del prodotto
- Un sito per un gruppo day-group non deve essere condiviso o accessibile da utenti esterni al gruppo day-

> [!IMPORTANT]
> Le barriere di informazioni ***supportano** solo le restrizioni _ bidirezioni. Restrizioni unidireli, come il marketing, possono comunicare e collaborare con gli operatori giornalieri, ma i day traders non possono comunicare e collaborare con il marketing _*_non è supportato_**.

Per tutti questi scenari di esempio (e altro ancora), i criteri delle barriere di informazioni possono essere definiti per impedire o consentire comunicazioni e collaborazione in Microsoft Teams, SharePoint Online e OneDrive. Questi criteri possono impedire agli utenti di chiamare o chattare con quelli che non dovrebbero o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft Teams. Con i criteri delle barriere di informazioni in vigore, ogni volta che gli utenti coperti da tali criteri tentano di comunicare e collaborare con altri utenti in Microsoft Teams, i controlli di SharePoint Online o OneDrive vengono eseguiti per impedire (o consentire) la comunicazione e la collaborazione (come definito dai criteri delle barriere di informazioni).

Per altre informazioni sull'esperienza utente con le barriere in fatto di informazioni, vedere:

- [Barriere di informazioni in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Barriere di informazioni in OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Attualmente, le barriere in fatto di informazioni non si applicano alle comunicazioni di posta elettronica. Inoltre, le barriere delle informazioni sono indipendenti dai [limiti di conformità.](set-up-compliance-boundaries.md)<p> Prima di definire e applicare i criteri delle barriere di informazioni, assicurarsi che l'organizzazione non abbia criteri della rubrica di [Exchange](/exchange/address-books/address-book-policies/address-book-policies) in vigore. Le barriere di informazioni si basano sui criteri della rubrica.

## <a name="what-happens-with-information-barriers"></a>Cosa accade con le barriere in fatto di informazioni

Quando sono presenti criteri delle barriere di informazioni, le persone che non devono comunicare o condividere file con altri utenti specifici non saranno in grado di trovare, selezionare, chattare o chiamare tali utenti. Con le barriere in fatto di informazioni, sono in atto controlli per impedire comunicazioni e collaborazione non autorizzate. 

Le barriere di informazioni si applicano a Microsoft Teams (chat e canali), SharePoint Online e OneDrive. In Microsoft Teams, i criteri delle barriere di informazioni determinano e impediscono i seguenti tipi di comunicazioni non autorizzate:

- Ricerca di un utente
- Aggiunta di un membro a un team
- Avvio di una sessione di chat con un utente
- Avvio di una chat di gruppo
- Invitare qualcuno a partecipare a una riunione
- Condivisione di una schermata
- Esecuzione di una chiamata
- Condivisione di un file con un altro utente
- Accesso al file tramite collegamento di condivisione

Se le persone coinvolte sono incluse in un criterio di barriere di informazioni per impedire l'attività, non potranno procedere. Inoltre, potenzialmente, tutti gli utenti inclusi in un criterio di barriere di informazioni possono essere bloccati dalla comunicazione con altri utenti in Microsoft Teams. Quando le persone interessate dai criteri delle barriere di informazioni fanno parte dello stesso team o chat di gruppo, potrebbero essere rimosse da tali sessioni di chat e potrebbero non essere consentite ulteriori comunicazioni con il gruppo.

Per altre informazioni sull'esperienza utente con le barriere in fatto di informazioni, vedere [barriere di informazioni in Microsoft Teams.](/MicrosoftTeams/information-barriers-in-teams)

In SharePoint Online e OneDrive, i criteri delle barriere di informazioni determinano e impediscono i seguenti tipi di collaborazione non autorizzate:

- Aggiunta di un membro a un sito
- Accesso al sito o al contenuto da parte di un utente
- Condivisione del sito o del contenuto con un altro utente
- Ricerca in un sito

Per ulteriori informazioni sull'esperienza utente con le barriere delle informazioni, vedere [barriere in SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Le barriere di informazioni sono ora in distribuzione e sono incluse nelle sottoscrizioni, ad esempio:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Conformità Microsoft 365 E5/A5
- Gestione dei rischi insider di Microsoft 365

Per altre informazioni, vedere le indicazioni sulle licenze di [Microsoft 365 per la sicurezza & conformità.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Per [definire o modificare i criteri delle barriere di informazioni,](information-barriers-policies.md)è necessario disporre di uno dei ruoli seguenti:

- Amministratore globale di Microsoft 365
- Amministratore globale di Office 365
- Amministratore di conformità
- Gestione della conformità IB

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Autorizzazioni nel Centro sicurezza [& conformità di Office 365.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri delle barriere di informazioni. Anche se nell'articolo di procedura [](information-barriers-policies.md)vengono forniti diversi esempi di cmdlet di PowerShell, è necessario conoscere altri dettagli, ad esempio i parametri, per l'organizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Ulteriori informazioni sulle barriere di informazioni in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ulteriori informazioni sulle barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Ulteriori informazioni sulle barriere di informazioni in OneDrive](/onedrive/information-barriers)
- [Vedere gli attributi che possono essere utilizzati per i criteri delle barriere di informazioni](information-barriers-attributes.md)
- [Definire i criteri per le barriere in fatto di informazioni](information-barriers-policies.md)
- [Modificare (o rimuovere) i criteri delle barriere di informazioni](information-barriers-edit-segments-policies.md)