---
title: Collaborare con utenti esterni all'organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come configurare Microsoft 365 per la collaborazione con utenti esterni all'organizzazione.
ms.openlocfilehash: 4d5be2d560017978d08bf9f5b06c9e2011606c6d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819413"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Collaborare con utenti esterni all'organizzazione

Le funzionalità di condivisione esterna di Microsoft 365 offrono agli utenti dell'organizzazione la possibilità di collaborare con partner, fornitori, clienti e altri utenti che non dispongono di un account nella directory. È possibile condividere interi team o siti con persone esterne all'organizzazione o solo singoli file.

Collaborare con persone esterne all'organizzazione è costituito da due componenti principali:

- **Abilita condivisione** : configurare i controlli di condivisione in Azure Active Directory, teams, Microsoft 365 Groups e SharePoint per consentire il livello di condivisione desiderato per l'organizzazione.
- **Abilitare la sicurezza aggiuntiva** -mentre le funzionalità di condivisione di base possono essere configurate in modo da richiedere agli utenti esterni all'organizzazione di eseguire l'autenticazione, Microsoft 365 fornisce numerose funzionalità aggiuntive di sicurezza e conformità che consentono di proteggere i dati e di gestire i criteri di governance durante la condivisione esterna.

## <a name="enable-sharing"></a>Abilita condivisione

Per impostazione predefinita, in Microsoft 365, la condivisione con utenti esterni all'organizzazione è abilitata per SharePoint e OneDrive, ma è disabilitata per i team. Molti scenari di condivisione esterna di SharePoint e OneDrive funzionano senza ulteriori configurazioni. Per confermare le impostazioni di uno scenario che si sta utilizzando o abilitarne una nuova, scegliere tra le opzioni seguenti:

- [Collaborare ai documenti](collaborate-on-documents.md) : informazioni su come configurare Microsoft 365 per consentire la condivisione e la collaborazione con persone esterne all'organizzazione (sia ospiti che utenti non autenticati) su file e cartelle.
- [Collaborare in un sito](collaborate-in-site.md) : informazioni su come configurare Microsoft 365 per abilitare la condivisione dei siti di SharePoint con gli utenti.
- [Collaborare come team](collaborate-as-team.md) -informazioni su come configurare Microsoft 365 per abilitare la collaborazione ospite in teams.

Per una panoramica completa delle impostazioni di condivisione Guest disponibili in Microsoft 365, vedere [riferimento alle impostazioni di condivisione Guest di microsoft 365](microsoft-365-guest-settings.md).

## <a name="enable-additional-security"></a>Abilitare la sicurezza aggiuntiva

Dopo aver abilitato lo scenario che si desidera utilizzare per la condivisione con utenti esterni all'organizzazione, prendere in considerazione ulteriori misure di salvaguardia per proteggere il contenuto da una condivisione accidentale o intenzionale.

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md) : informazioni sulle procedure consigliate per la condivisione con utenti non autenticati.
- [Limite di esposizione accidentale](share-limit-accidental-exposure.md) -informazioni su come ridurre le probabilità di condivisione accidentale di contenuti sensibili con utenti esterni all'organizzazione.
- [Creare un ambiente di condivisione Guest sicuro](create-secure-guest-sharing-environment.md) -informazioni sugli strumenti forniti in Microsoft 365 per garantire che la condivisione con persone esterne all'organizzazione venga svolta in modo sicuro e conforme ai requisiti di governance.

## <a name="collaborate-with-partner-companies"></a>Collaborare con le aziende partner

Quando si lavora su un progetto di grandi dimensioni che coinvolge numerosi ospiti di un'altra organizzazione o se si dispone di una relazione del fornitore in corso in cui gli utenti cambiano spesso, è possibile utilizzare la gestione dei diritti in Azure Active Directory per semplificare la gestione degli ospiti e consentire all'azienda partner di condividere tale responsabilità. Per ulteriori informazioni, vedere [Create a B2B Extranet with Managed guests](b2b-extranet.md) .

## <a name="limit-sharing"></a>Limitare la condivisione

Se alcune delle funzionalità di condivisione in Microsoft 365 sono in conflitto con i criteri di governance, vedere [limitare la condivisione in microsoft 365](microsoft-365-limit-sharing.md) per informazioni sulle opzioni di limitazione della condivisione.

## <a name="related-topics"></a>Argomenti correlati

[Introduzione alla collaborazione di file in Microsoft 365](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Pianificare la collaborazione dei file in SharePoint con Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
