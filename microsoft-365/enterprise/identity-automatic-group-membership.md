---
title: "Passaggio 15: configurare l'appartenenza a gruppi dinamica"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'appartenenza automatica a un gruppo dinamico in base agli attributi di un account.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868795"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>Passaggio 15: configurare l'appartenenza a gruppi dinamica

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Con questo passaggio, è possibile creare una serie di regole per aggiungere o rimuovere automaticamente gli account utente in un gruppo di Azure AD. Questa operazione è denominata *appartenenza a gruppi dinamica*. Le regole si basano sugli attributi dell'account utente, come il reparto o il Paese.

Le regole si applicano nel seguente modo:

- Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.
- Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.
- Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.
- Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.

Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del Reparto vendite dovrebbero far parte del gruppo delle vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".

Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

I risultati di questo passaggio sono:

- Un set di gruppi di Azure AD che può essere configurato per l'appartenenza dinamica
- Un set di regole per ogni gruppo dinamico

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-dyn-groups) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di identità](identity-exit-criteria.md)
