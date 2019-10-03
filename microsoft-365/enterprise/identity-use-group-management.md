---
title: 'Passaggio 5: Usare i gruppi per la gestione'
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
description: È possibile usare i gruppi per automatizzare la gestione di alcune attività amministrative.
ms.openlocfilehash: 769fc0dd69b13978dbb9cf91d890ad271a7d9bb5
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370183"
---
# <a name="step-5-use-groups-for-management"></a>Passaggio 5: Usare i gruppi per la gestione

![Fase 2 - Identità](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Consentire agli utenti di creare e gestire i propri gruppi

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione verranno identificati i gruppi di Azure Active Directory (AD Azure) che possono essere gestiti dai proprietari del gruppo invece che dagli amministratori IT. Detta *gestione dei gruppi in modalità self-service*, questa caratteristica consente ai proprietari del gruppo a cui non sono stati assegnati ruoli di amministrazione per creare e gestire gruppi di sicurezza. 

Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.

>[!Note]
>La gestione dei gruppi in modalità self-service è disponibile solo per specifici di sicurezza di Azure AD e Office 365. Non è disponibile per i gruppi abilitati alla posta elettronica, liste di distribuzione o qualsiasi gruppo che è stato sincronizzato dall'ambiente Active Directory Domain Services (AD DS).
>

Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure AD per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-self-service-groups) per questa sezione.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Configurare l'appartenenza a gruppi dinamici

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione si creerà una serie di regole che aggiungono o rimuovono automaticamente gli account utente dai membri di un gruppo di Azure AD. Questa operazione è denominata *appartenenza dinamica al gruppo*. Le regole si basano sugli attributi dell’account utente, come il reparto o paese.

Le regole si applicano nel seguente modo:

- Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.
- Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.
- Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.
- Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.

Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del Reparto vendite dovrebbero far parte del gruppo delle vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".

Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

I risultati di questa sezione sono:

- Un set di gruppi di Azure AD che può essere configurato per l'appartenenza dinamica
- Un set di regole per ogni gruppo dinamico

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-dyn-groups) per questa sezione.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Configurare l'assegnazione automatica delle licenze

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione è possibile configurare gruppi di sicurezza in Azure AD per assegnare automaticamente licenze da un set di abbonamenti a tutti i membri del gruppo. Questa operazione è denominata *licenze basate sui gruppi*. Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.

Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare la licenza di Microsoft 365 Enterprise appropriata.

Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.

>[!Note]
>Non è necessario configurare l'*assegnazione delle licenze basate su gruppo* per i gruppi contenenti account Azure business to business (B2B).
>

Per ulteriori informazioni, vedere [Informazioni di base sull'assegnazione delle licenze basate su gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Vedere i [passaggi per configurare l'assegnazione delle licenze basate su gruppo per un gruppo di sicurezza Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

I risultati di questa sezione sono:

- Sono stati identificati i gruppi di sicurezza idonei per l'assegnazione delle licenze basate su gruppo.
- Sono stati configurati i gruppi per l'assegnazione delle licenze basate su gruppo.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-group-license) per questa sezione.

|||
|:-------|:-----|
|![Passaggio 6](./media/stepnumbers/Step6.png)| [Configurare la governance delle identità](identity-configure-identity-governance.md) |
