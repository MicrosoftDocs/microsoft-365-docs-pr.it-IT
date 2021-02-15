---
title: Gestire la governance delle identità di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni su come usare le funzionalità di governance delle identità di Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370347"
---
# <a name="manage-microsoft-365-identity-governance"></a>Gestire la governance delle identità di Microsoft 365

Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse strategiche e garantire la produttività dei dipendenti. Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.

Per ulteriori informazioni, vedere questa [panoramica della governance delle identità per Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Impostare le verifiche di accesso di Azure AD

Le verifiche di accesso di Azure AD consentono di esaminare l'accesso di un utente per garantire che l'accesso continui solo alle persone giuste. Ad esempio:

- Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.
- Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.
- Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.

Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.

Per ulteriori informazioni, vedere la panoramica [delle verifiche di accesso.](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Vedere questi articoli per configurare tipi diversi di verifica di accesso:

- [Gruppi e app](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Ruoli delle risorse di Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Configurare la gestione dei diritti di Azure AD

Wiht Azure AD entitlement management, è possibile gestire il ciclo di vita di identità e accesso su vasta scala automatizzando i flussi di lavoro delle richieste di accesso, le assegnazioni di accesso, le revisioni e la scadenza.

I dipendenti devono accedere a vari gruppi, applicazioni e siti per svolgere il proprio lavoro. La gestione di questo accesso può essere difficile perché i requisiti cambiano, vengono aggiunte nuove applicazioni o gli utenti necessitano di diritti di accesso aggiuntivi. Quando si collabora con altre organizzazioni, è possibile che non si sappia chi nell'altra organizzazione deve accedere alle risorse dell'organizzazione e gli utenti esterni non conoscono le applicazioni, i gruppi o i siti in uso nell'organizzazione.

La gestione dei diritti di Azure AD consente di gestire in modo più efficiente l'accesso a gruppi, applicazioni e siti di SharePoint per utenti interni ed esterni.
 
Per altre informazioni, vedi la panoramica [della gestione dei diritti di Azure AD.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
