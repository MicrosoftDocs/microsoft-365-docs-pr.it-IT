---
title: 'Passaggio 7: Configurare Identity Governance'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su Identity Governance per il tenant di Azure AD e su come configurarlo.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543995"
---
# <a name="step-6-configure-identity-governance"></a>Passaggio 6: Configurare Identity Governance

![Fase 2: identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse strategiche e garantire la produttività dei dipendenti. Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.

Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) per maggiori informazioni su Identity Governance per Azure Active Directory (Azure AD).


*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Impostare le verifiche di accesso di Azure AD

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

In questo passaggio verranno configurate le verifiche di accesso di Azure AD, che consentono di verificare l'accesso di un utente per garantire che solo le persone giuste dispongano di un accesso continuo. Ad esempio:

- Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.
- Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.
- Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.

Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.

Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) per maggiori informazioni sulle verifiche di accesso di Azure AD.

Azure AD Privileged Identity Management (PIM) fornisce controlli aggiuntivi mirati alla protezione dei diritti di accesso alle risorse in Azure AD, Azure e altri servizi cloud Microsoft. Azure AD PIM fornisce un set completo di controlli di governance che agevolano la protezione delle risorse aziendali, ad esempio ruoli delle directory, di Office 365 e delle risorse di Azure. Come con altre forme di accesso, le organizzazioni possono usare le verifiche di accesso per configurare la ricertificazione ricorrente dell'accesso per tutti gli utenti con ruoli di amministratore. Azure AD PIM è disponibile solo con la versione E5 di Microsoft 365 Enterprise.

Vedere questi articoli per configurare tipi diversi di verifica di accesso:

- [Gruppi e app](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Ruoli delle risorse di Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-access-reviews) per questa sezione.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di identità](identity-exit-criteria.md)

