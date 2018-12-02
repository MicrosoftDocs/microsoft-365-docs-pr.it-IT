---
title: "Passaggio 12: configurare l'assegnazione automatica delle licenze"
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
description: Comprendere e configurare l'assegnazione delle licenze basate su gruppo per i gruppi di Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868261"
---
# <a name="step-12-set-up-automatic-licensing"></a>Passaggio 12: configurare l'assegnazione automatica delle licenze

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, i gruppi di sicurezza in Azure AD verranno configurati in modo da assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo. Questa funzionalità è conosciuta come *assegnazione delle licenze basate su gruppo*. Se un account utente viene aggiunto o rimosso da un gruppo, le licenze per le sottoscrizioni del gruppo verranno assegnate o rimosse automaticamente dall'account utente.

Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare entrambe queste licenze:

- Office 365 Enterprise E3 o E5
- Enterprise Mobility + Security (EMS) E3 o E5

Utilizzando i gruppi identificati con il Passaggio 2, cercare quelli che contengono un elenco di account in cui tutti i membri del gruppo dispongono di entrambe le licenze di Office 365 ed EMS. Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione sono terminate, i nuovi utenti non potranno ottenerne una fino a quando non saranno di nuovo disponibili.

>[!Note]
>Non è necessario configurare l'*assegnazione delle licenze basate su gruppo* per i gruppi contenenti account Azure business to business (B2B).
>

Per ulteriori informazioni, vedere [Informazioni di base sull'assegnazione delle licenze basate su gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Vedere i [passaggi per configurare l'assegnazione delle licenze basate su gruppo per un gruppo di sicurezza Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

I risultati di questo passaggio sono:

- Sono stati identificati i gruppi di sicurezza idonei per l'assegnazione delle licenze basate su gruppo.
- Sono stati configurati i gruppi per l'assegnazione delle licenze basate su gruppo.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: automatizzare le licenze e l'appartenenza ai gruppi](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-group-license) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Monitorare l'attività di tenant e di accesso](identity-azure-ad-access-usage-reporting.md) |

