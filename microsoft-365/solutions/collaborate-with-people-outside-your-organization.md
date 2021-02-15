---
title: Collaborare con persone esterne all'organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come configurare le app di Microsoft 365 come Teams, OneDrive e SharePoint per la collaborazione con persone esterne all'organizzazione.
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613455"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Collaborare con persone esterne all'organizzazione

Le funzionalità di condivisione esterna in Microsoft 365 offrono agli utenti dell'organizzazione l'opportunità di collaborare con partner, fornitori, clienti e altri che non dispongono di un account nella directory. È possibile condividere interi team o siti con persone esterne all'organizzazione o solo singoli file.

La collaborazione con persone esterne all'organizzazione è costituita da due componenti principali:

- **Abilitare la** condivisione: configurare i controlli di condivisione in Azure Active Directory, Teams, Gruppi di Microsoft 365 e SharePoint per consentire il livello di condivisione desiderato per l'organizzazione.
-  Abilitare una sicurezza aggiuntiva: anche se le funzionalità di condivisione di base possono essere configurate per richiedere l'autenticazione di persone esterne all'organizzazione, Microsoft 365 offre molte funzionalità di sicurezza e conformità aggiuntive che consentono di proteggere i dati e mantenere i criteri di governance durante la condivisione esterna.

## <a name="enable-sharing"></a>Abilitare la condivisione

Per impostazione predefinita, in Microsoft 365 la condivisione con persone esterne all'organizzazione è abilitata per SharePoint e OneDrive, ma disabilitata per Teams. Molti scenari di condivisione esterna di SharePoint e OneDrive funzionano senza ulteriori configurazioni. Per confermare le impostazioni per uno scenario in uso o abilitarne uno nuovo, scegliere una delle opzioni seguenti:

- [Collaborare ai](collaborate-on-documents.md) documenti: informazioni su come configurare Microsoft 365 per consentire la condivisione e la collaborazione con persone esterne all'organizzazione (utenti guest e utenti non autenticati) su file e cartelle.
- [Collaborare in un sito:](collaborate-in-site.md) informazioni su come configurare Microsoft 365 per abilitare la condivisione di siti di SharePoint con utenti guest.
- [Collaborare come team:](collaborate-as-team.md) informazioni su come configurare Microsoft 365 per abilitare la collaborazione guest in Teams.

Per una panoramica completa delle impostazioni di condivisione guest disponibili in Microsoft 365, vedere Informazioni di riferimento sulle impostazioni di condivisione [guest di Microsoft 365.](microsoft-365-guest-settings.md)

## <a name="enable-additional-security"></a>Abilitare una sicurezza aggiuntiva

Dopo aver abilitato lo scenario che si desidera utilizzare per la condivisione con persone esterne all'organizzazione, prendere in considerazione misure di sicurezza aggiuntive per proteggere il contenuto da condivisione accidentale o intenzionale inappropriata.

- [Procedure consigliate per la condivisione di file](best-practices-anonymous-sharing.md) e cartelle con utenti non autenticati: informazioni sulle procedure consigliate per la condivisione con utenti non autenticati.
- [Limitare l'esposizione accidentale:](share-limit-accidental-exposure.md) informazioni su come ridurre le probabilità di condividere accidentalmente contenuti sensibili con persone esterne all'organizzazione.
- Creare un ambiente di condivisione [guest](create-secure-guest-sharing-environment.md) sicuro: informazioni sugli strumenti forniti in Microsoft 365 per garantire che la condivisione con persone esterne all'organizzazione sia eseguita in modo sicuro e conforme ai requisiti di governance.

## <a name="collaborate-with-partner-companies"></a>Collaborare con società partner

Quando si lavora a un progetto di grandi dimensioni che coinvolge molti utenti guest di un'altra organizzazione o se si ha una relazione continua con i fornitori in cui gli utenti guest cambiano spesso, è possibile utilizzare la gestione dei diritti in Azure Active Directory per semplificare la gestione degli utenti guest e consentire all'azienda partner di condividere tale responsabilità. Per informazioni dettagliate, vedere Creare una [extranet B2B con utenti guest](b2b-extranet.md) gestiti.

## <a name="limit-sharing"></a>Limitare la condivisione

Se alcune delle funzionalità di condivisione in Microsoft 365 sono in conflitto con i criteri di governance, vedere Limitare la condivisione [in Microsoft 365](microsoft-365-limit-sharing.md) per informazioni sulle opzioni per limitare la condivisione.

## <a name="related-topics"></a>Argomenti correlati

[Introduzione alla collaborazione sui file in Microsoft 365](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Pianificare la collaborazione file in SharePoint con Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
