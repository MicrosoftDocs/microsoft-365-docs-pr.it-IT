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
description: Informazioni su come utilizzare le funzionalità di governance dell'identità di Microsoft 365.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328513"
---
# <a name="manage-microsoft-365-identity-governance"></a>Gestire la governance delle identità di Microsoft 365

Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse strategiche e garantire la produttività dei dipendenti. Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.

Per ulteriori informazioni, vedere questa [Panoramica della governance delle identità per Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Impostare le verifiche di accesso di Azure AD

Le recensioni di Azure AD Access consentono di controllare l'accesso di un utente per assicurarsi che solo le persone giuste abbiano accesso continuato. Ad esempio:

- Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.
- Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.
- Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.

Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.

Per ulteriori informazioni, vedere la [Panoramica delle recensioni di Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

Azure AD Privileged Identity Management (PIM) fornisce controlli aggiuntivi mirati alla protezione dei diritti di accesso alle risorse in Azure AD, Azure e altri servizi cloud Microsoft. Azure AD PIM fornisce un set completo di controlli di governance che agevolano la protezione delle risorse aziendali, ad esempio ruoli delle directory, di Office 365 e delle risorse di Azure. Come con altre forme di accesso, le organizzazioni possono usare le verifiche di accesso per configurare la ricertificazione ricorrente dell'accesso per tutti gli utenti con ruoli di amministratore. Azure AD PIM è disponibile solo con la versione E5 di Microsoft 365 Enterprise.

Vedere questi articoli per configurare tipi diversi di verifica di accesso:

- [Gruppi e app](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Ruoli delle risorse di Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Configurare la gestione dei diritti di Azure AD

Gestione dei diritti di wiht Azure AD, è possibile gestire il ciclo di vita delle identità e dell'accesso in scala automatizzando i flussi di lavoro delle richieste di accesso, le assegnazioni di accesso, le recensioni e la scadenza.

I dipendenti devono accedere a vari gruppi, applicazioni e siti per svolgere il proprio lavoro. La gestione di questo accesso può essere difficile perché i requisiti cambiano, vengono aggiunte nuove applicazioni o gli utenti hanno bisogno di ulteriori diritti di accesso. Quando si collabora con altre organizzazioni, potrebbe non essere possibile sapere chi nell'altra organizzazione ha bisogno di accedere alle risorse dell'organizzazione e gli utenti esterni non sapranno quali applicazioni, gruppi o siti utilizza l'organizzazione.

La gestione dei diritti di Azure AD può aiutare a gestire in modo più efficiente l'accesso ai gruppi, alle applicazioni e ai siti di SharePoint per gli utenti interni ed esterni.
 
Per ulteriori informazioni, vedere la [Panoramica della gestione dei diritti di Azure ad](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).
