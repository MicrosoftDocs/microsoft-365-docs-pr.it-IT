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
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="adcab-103">Passaggio 3: Configurare gli amministratori globali su richiesta</span><span class="sxs-lookup"><span data-stu-id="adcab-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="adcab-104">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="adcab-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="adcab-p101">In questo passaggio si procederà alla configurazione di Azure AD Privileged Identity Management (PIM) per ridurre la quantità di tempo per la quale gli account amministratore globale sono vulnerabili agli attacchi da parte di utenti malintenzionati. Su richiesta, PIM fornisce l'assegnazione JIT del ruolo di amministratore globale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="adcab-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="adcab-p102">Gli account amministratore globale non sono amministratori permanenti, ma diventano amministratori idonei. Il ruolo di amministratore globale è inattivo fino a quando un utente ne ha bisogno. A questo punto verrà completato un processo di attivazione per aggiungere il ruolo di amministratore globale all'account dell'amministratore globale per un periodo di tempo specifico. Quando il tempo scade, PIM rimuove il ruolo di amministratore globale dall'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="adcab-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="adcab-p103">PIM è disponibile con Azure Active Directory Premium P2, incluso con Microsoft 365 Enterprise E5. In alternativa, è possibile acquistare delle licenze singole per Azure Active Directory Premium P2 per gli account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="adcab-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="adcab-113">Per attivare Azure PIM per gli account tenant e amministratore globale Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="adcab-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="adcab-114">Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="adcab-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="adcab-115">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pim) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="adcab-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="adcab-116">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="adcab-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="adcab-117">Semplificare le reimpostazioni delle password</span><span class="sxs-lookup"><span data-stu-id="adcab-117">Simplify password resets</span></span>](identity-password-reset.md) |

