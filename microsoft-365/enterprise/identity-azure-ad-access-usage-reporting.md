---
title: "Passaggio 13: monitorare l'attività di tenant e di accesso"
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
description: Comprendere e configurare l'accesso e il report di utilizzo di Azure AD.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868265"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="7444e-103">Passaggio 13: monitorare l'attività di tenant e di accesso</span><span class="sxs-lookup"><span data-stu-id="7444e-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="7444e-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7444e-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7444e-p101">In questo passaggio, è possibile rivedere le attività dei log di controllo e le attività di accesso utilizzando la creazione di report di Azure AD. Sono disponibili due tipi di report.</span><span class="sxs-lookup"><span data-stu-id="7444e-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="7444e-p102">Il **Report delle attività di log di controllo** registra la storia di ogni attività eseguita nel tenant di Azure AD. Questo report può fornire risposte a domande come:</span><span class="sxs-lookup"><span data-stu-id="7444e-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="7444e-109">Chi ha aggiunto un membro al gruppo amministratore?</span><span class="sxs-lookup"><span data-stu-id="7444e-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="7444e-110">Quali utenti hanno effettuato l'accesso in una determinata app?</span><span class="sxs-lookup"><span data-stu-id="7444e-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="7444e-111">Quante reimpostazioni della password sono state eseguite?</span><span class="sxs-lookup"><span data-stu-id="7444e-111">How many password resets are happening?</span></span>

<span data-ttu-id="7444e-p103">Il **Report delle attività di accesso** registra gli utenti che hanno eseguito le attività riportate nei report dei log di controllo. Questo report può fornire risposte a domande come:</span><span class="sxs-lookup"><span data-stu-id="7444e-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="7444e-114">Qual è il criterio di accesso per un utente specifico sotto esame?</span><span class="sxs-lookup"><span data-stu-id="7444e-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="7444e-115">Qual'è il numero degli accessi durante un giorno, una settimana o un mese?</span><span class="sxs-lookup"><span data-stu-id="7444e-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="7444e-116">Quanti tentativi di accesso non hanno avuto esito positivo e per quali account si è verificata questa occorrenza?</span><span class="sxs-lookup"><span data-stu-id="7444e-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="7444e-117">Per ulteriori informazioni sui report e su come accedere ad essi, vedere [Creazione di report di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7444e-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="7444e-118">Il risultato di questo passaggio è acquisire consapevolezza riguardo tali report e comprendere come utilizzarli per comprendere gli eventi e le attività di Azure AD a scopo di pianificazione e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7444e-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="7444e-119">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7444e-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="7444e-120">Consentire agli utenti di creare e gestire i propri gruppi</span><span class="sxs-lookup"><span data-stu-id="7444e-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
