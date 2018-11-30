---
title: 'Passaggio 14: consentire agli utenti di creare e gestire i propri gruppi'
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
description: Capire e configurare la gestione dei gruppi self-service di Azure AD
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868608"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>Passaggio 14: consentire agli utenti di creare e gestire i propri gruppi

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, vengono identificati i gruppi di Azure Active Directory (AD) che possono essere gestiti da proprietari di gruppi invece che da amministratori IT. Nota come *gestione gruppi self-service*, questa funzione consente ai proprietari dei gruppi senza ruolo amministrativo di creare e gestire gruppi di sicurezza. 

Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.

>[!Note]
>La gestione gruppi self-service è disponibile solo per la sicurezza Azure AD e i gruppi Office 365. Non è disponibile per i gruppi abilitati alla posta elettronica, liste di distribuzione o per gruppi sincronizzati da Windows Server Active Directory (AD) locale.
>

Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure Active Directory per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-self-service-groups) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [Configurare l'appartenenza a gruppi dinamica](identity-automatic-group-membership.md) |
