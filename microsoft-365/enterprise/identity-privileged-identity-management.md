---
title: 'Passaggio 3: Configurare gli amministratori globali su richiesta'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su Azure AD Privileged Identity Management e configurazione del prodotto.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868470"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Passaggio 3: Configurare gli amministratori globali su richiesta

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio si procederà alla configurazione di Azure AD Privileged Identity Management (PIM) per ridurre la quantità di tempo per la quale gli account amministratore globale sono vulnerabili agli attacchi da parte di utenti malintenzionati. Su richiesta, PIM fornisce l'assegnazione JIT del ruolo di amministratore globale, se necessario.  

Gli account amministratore globale non sono amministratori permanenti, ma diventano amministratori idonei. Il ruolo di amministratore globale è inattivo fino a quando un utente ne ha bisogno. A questo punto verrà completato un processo di attivazione per aggiungere il ruolo di amministratore globale all'account dell'amministratore globale per un periodo di tempo specifico. Quando il tempo scade, PIM rimuove il ruolo di amministratore globale dall'account amministratore globale.

PIM è disponibile con Azure Active Directory Premium P2, incluso con Microsoft 365 Enterprise E5. In alternativa, è possibile acquistare delle licenze singole per Azure Active Directory Premium P2 per gli account amministratore globale.

Per attivare Azure PIM per gli account tenant e amministratore globale Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pim) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Semplificare le reimpostazioni delle password](identity-password-reset.md) |

