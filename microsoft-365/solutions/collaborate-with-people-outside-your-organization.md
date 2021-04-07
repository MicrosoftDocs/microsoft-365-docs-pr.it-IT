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
ms.openlocfilehash: 85aa77982fa15adb62bd587856546d2828edb942
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599820"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Collaborare con persone esterne all'organizzazione

Le funzionalità di condivisione esterna in Microsoft 365 offrono agli utenti dell'organizzazione l'opportunità di collaborare con partner, fornitori, clienti e altri che non dispongono di un account nella directory. È possibile condividere interi team o siti con persone esterne all'organizzazione o solo singoli file.

La collaborazione con persone esterne all'organizzazione è costituita da due componenti principali:

- **Abilitare la** condivisione: configurare i controlli di condivisione tra Azure Active Directory, Teams, Gruppi di Microsoft 365 e SharePoint per consentire il livello di condivisione desiderato per l'organizzazione.
-  Abilitare sicurezza aggiuntiva: sebbene le funzionalità di condivisione di base possano essere configurate in modo da richiedere l'autenticazione a persone esterne all'organizzazione, Microsoft 365 offre molte funzionalità di sicurezza e conformità aggiuntive per proteggere i dati e mantenere i criteri di governance durante la condivisione esterna.

Leggere [Configurare una collaborazione sicura con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams) e Microsoft Teams per informazioni su come la condivisione esterna si lega con le indicazioni generali sulla collaborazione di Microsoft 365.

## <a name="enable-sharing"></a>Abilitare la condivisione

Per impostazione predefinita, in Microsoft 365 è abilitata la condivisione con persone esterne all'organizzazione. Molti scenari di condivisione esterna funzionano senza ulteriori configurazioni. Per verificare le impostazioni per uno scenario in uso o abilitarne uno nuovo, scegliere una delle opzioni seguenti:

- [Collaborare ai documenti:](collaborate-on-documents.md) informazioni su come configurare Microsoft 365 per consentire la condivisione e la collaborazione con utenti esterni all'organizzazione (sia guest che utenti non autenticati) su file e cartelle.
- [Collaborare in un sito:](collaborate-in-site.md) informazioni su come configurare Microsoft 365 per abilitare la condivisione di siti di SharePoint con utenti guest.
- [Collaborare come team:](collaborate-as-team.md) informazioni su come configurare Microsoft 365 per abilitare la collaborazione guest in Teams.

Per un'occhiata completa alle impostazioni di condivisione guest disponibili in Microsoft 365, vedere Riferimento alle impostazioni di condivisione guest di [Microsoft 365.](microsoft-365-guest-settings.md)

## <a name="enable-additional-security"></a>Abilitare sicurezza aggiuntiva

Dopo aver abilitato lo scenario che si desidera utilizzare per la condivisione con persone esterne all'organizzazione, prendere in considerazione misure di sicurezza aggiuntive per proteggere il contenuto da condivisione accidentale o intenzionale inappropriata.

- [Procedure consigliate per la condivisione](best-practices-anonymous-sharing.md) di file e cartelle con utenti non autenticati - Informazioni sulle procedure consigliate per la condivisione con utenti non autenticati.
- [Limitare l'esposizione accidentale:](share-limit-accidental-exposure.md) informazioni su come ridurre le possibilità di condivisione accidentale di contenuti sensibili con persone esterne all'organizzazione.
- [Creare](create-secure-guest-sharing-environment.md) un ambiente di condivisione guest sicuro- Informazioni sugli strumenti disponibili in Microsoft 365 per garantire che la condivisione con persone esterne all'organizzazione sia eseguita in modo sicuro e conforme ai requisiti di governance.

## <a name="collaborate-with-partner-companies"></a>Collaborare con le società partner

Quando si lavora a un progetto di grandi dimensioni che coinvolge molti utenti guest di un'altra organizzazione o se si dispone di una relazione fornitore continua in cui gli utenti guest cambiano spesso, è possibile utilizzare la gestione dei diritti in Azure Active Directory per semplificare la gestione degli utenti guest e consentire all'azienda partner di condividere tale responsabilità. Per informazioni dettagliate, vedere Create [a B2B Extranet with managed guests.](b2b-extranet.md)

## <a name="limit-sharing"></a>Limitare la condivisione

Se alcune delle funzionalità di condivisione in Microsoft 365 sono in conflitto con i criteri di governance, vedere Limitare la condivisione [in Microsoft 365](microsoft-365-limit-sharing.md) per informazioni sulle opzioni per limitare la condivisione.

## <a name="related-topics"></a>Argomenti correlati

[Introduzione alla collaborazione su file in Microsoft 365](/sharepoint/intro-to-file-collaboration)

[Pianificare la collaborazione file in SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)
