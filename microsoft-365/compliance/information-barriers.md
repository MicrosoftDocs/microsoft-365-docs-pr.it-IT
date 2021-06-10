---
title: Informazioni sulle barriere in Microsoft 365
description: Usare le barriere alle informazioni per garantire la conformità delle comunicazioni Microsoft Teams all'interno dell'organizzazione.
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
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051878"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Informazioni sulle barriere in Microsoft 365

I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione. Si supponga tuttavia di voler limitare la comunicazione e la collaborazione tra due gruppi per evitare che si verifichi un conflitto di interesse nell'organizzazione. In altri casi, è possibile limitare la comunicazione e la collaborazione tra determinate persone all'interno dell'organizzazione per salvaguardare le informazioni interne. Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi esiste un modo per limitare la comunicazione e la collaborazione tra gruppi specifici di utenti quando necessario? Con le barriere di informazioni, è possibile!

Microsoft Teams, SharePoint Online e OneDrive for Business le barriere alle informazioni. Presupponendo che la [sottoscrizione](#required-licenses-and-permissions) includa barriere di informazioni, un amministratore di conformità o un amministratore delle barriere alle informazioni può definire criteri per consentire o impedire le comunicazioni tra gruppi di utenti in Microsoft Teams. I criteri di barriera delle informazioni possono essere utilizzati in situazioni come queste:

- L'utente nel gruppo di utenti del giorno non deve comunicare o condividere file con il team di marketing
- Il personale finanziario che lavora su informazioni aziendali riservate non deve comunicare o condividere file con determinati gruppi all'interno dell'organizzazione
- Un team interno con materiale segreto commerciale non deve chiamare o chattare online con persone di determinati gruppi all'interno dell'organizzazione
- Un team di ricerca deve chiamare o chattare solo online con un team di sviluppo del prodotto
- Un sito per il gruppo di operatore giornaliero non deve essere condiviso o accessibile da nessuno al di fuori del gruppo di utenti giornalieri

> [!IMPORTANT]
> Le barriere alle informazioni ***supportano** solo le restrizioni _ bidirezioni. Le restrizioni unidireli, ad esempio il marketing, possono comunicare e collaborare con i professionisti del giorno, ma i day traders non possono comunicare e collaborare con il marketing _*_non è supportato_**.

Per tutti questi scenari di esempio (e altro ancora), è possibile definire criteri di barriera delle informazioni per impedire o consentire comunicazioni e collaborazione in Microsoft Teams, SharePoint Online e OneDrive. Tali criteri possono impedire agli utenti di chiamare o chattare con quelli che non dovrebbero o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft Teams. Con i criteri di barriera delle informazioni in vigore, ogni volta che gli utenti coperti da tali criteri tentano di comunicare e collaborare con altri utenti in Microsoft Teams, controlli SharePoint Online o OneDrive vengono eseguiti per impedire (o consentire) la comunicazione e la collaborazione (come definito dai criteri di barriera delle informazioni).

Per ulteriori informazioni sull'esperienza utente con le barriere alle informazioni, vedere:

- [Barriere informative in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ostacoli alle informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Barriere informazioni in OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Attualmente, le barriere alle informazioni non si applicano alle comunicazioni di posta elettronica. Inoltre, le barriere alle informazioni sono indipendenti dai [limiti di conformità.](set-up-compliance-boundaries.md)<p> Prima di definire e applicare i criteri di barriera delle informazioni, assicurarsi che l'organizzazione non Exchange i criteri [della](/exchange/address-books/address-book-policies/address-book-policies) rubrica. Le barriere delle informazioni si basano sui criteri della rubrica.

## <a name="what-happens-with-information-barriers"></a>Cosa accade con le barriere delle informazioni

Quando sono presenti criteri di barriera delle informazioni, gli utenti che non devono comunicare o condividere file con altri utenti specifici non saranno in grado di trovare, selezionare, chattare o chiamare tali utenti. Con le barriere alle informazioni, sono in atto controlli per impedire comunicazioni e collaborazione non autorizzate. 

Le barriere di informazione si applicano Microsoft Teams (chat e canali), SharePoint Online e OneDrive. In Microsoft Teams i criteri di barriera informativa determinano e impediscono le seguenti comunicazioni non autorizzate:

- Ricerca di un utente
- Aggiunta di un membro a un team
- Avvio di una sessione di chat con un altro utente
- Avvio di una chat di gruppo
- Invito di altri utenti a partecipare a una riunione
- Condivisione di uno schermo
- Esecuzione di una chiamata
- Condivisione di un file con un altro utente
- Accesso ai file tramite collegamento di condivisione

Se le persone coinvolte sono incluse in un criterio di barriera informativa per la prevenzione dell'attività, non potranno procedere. Inoltre, è possibile che a tutti gli utenti inclusi in un criterio di barriera informativa sia impedito di comunicare con altri utenti in Microsoft Teams. Quando gli utenti coinvolti nei criteri di barriera informativa fanno parte della stessa chat del team o del gruppo, essi potrebbero essere rimossi da tali sessioni di chat senza la possibilità di comunicare ulteriormente con il gruppo.

Per ulteriori informazioni sull'esperienza utente con le barriere alle informazioni, vedere [ostacoli alle informazioni in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

In SharePoint Online e OneDrive, i criteri di barriera delle informazioni determinano e impediscono i seguenti tipi di collaborazioni non autorizzate:

- Aggiunta di un membro a un sito
- Accesso al sito o al contenuto da parte di un utente
- Condivisione del sito o del contenuto con un altro utente
- Ricerca in un sito

Per ulteriori informazioni sull'esperienza utente con le barriere alle informazioni, vedere ostacoli alle [informazioni in SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Le barriere alle informazioni sono ora disponibili e sono incluse nelle sottoscrizioni, ad esempio:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 Conformità E5/A5
- Gestione dei rischi Insider Microsoft 365

Per ulteriori informazioni, vedere linee [guida Microsoft 365 licenze per la sicurezza & conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

Per [definire o modificare i criteri di barriera delle](information-barriers-policies.md)informazioni, è necessario disporre di uno dei ruoli seguenti:

- Amministratore globale di Microsoft 365
- Amministratore globale di Office 365
- Amministratore di conformità
- Gestione della conformità IB

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Autorizzazioni nel Centro Office 365 [sicurezza & conformità.](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)

Per definire, convalidare o modificare i criteri di protezione delle informazioni, è necessario avere familiarità con i cmdlet di PowerShell. Anche se nell'articolo sulla procedura [](information-barriers-policies.md)vengono forniti diversi esempi di cmdlet di PowerShell, è necessario conoscere altri dettagli, ad esempio i parametri, per l'organizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Ulteriori informazioni sulle barriere di informazione in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ulteriori informazioni sulle barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Altre informazioni sulle barriere di informazione in OneDrive](/onedrive/information-barriers)
- [Vedere gli attributi che possono essere utilizzati per i criteri di barriera delle informazioni](information-barriers-attributes.md)
- [Definire i criteri per le barriere informative](information-barriers-policies.md)
- [Modificare (o rimuovere) i criteri delle barriere informative](information-barriers-edit-segments-policies.md)