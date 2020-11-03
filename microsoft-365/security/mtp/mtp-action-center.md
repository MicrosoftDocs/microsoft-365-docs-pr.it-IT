---
title: Accedere al centro notifiche per visualizzare e approvare le indagini automatizzate e le attività di correzione
description: Utilizzare il centro notifiche per visualizzare dettagli relativi alle indagini automatizzate e approvare le azioni in sospeso
keywords: Centro notifiche, protezione dalla minacce, indagine, avviso, in sospeso, automatizzata, rilevamento
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843793"
---
# <a name="the-action-center"></a><span data-ttu-id="f4fef-104">Centro operativo</span><span class="sxs-lookup"><span data-stu-id="f4fef-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f4fef-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f4fef-105">**Applies to:**</span></span>
- <span data-ttu-id="f4fef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4fef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f4fef-107">Utilizzare il centro notifiche per visualizzare i risultati delle indagini attuali e passate sui dispositivi e le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f4fef-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="f4fef-108">A seconda del tipo di minaccia e del verdetto risultante, le [azioni di correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) si verificano automaticamente o dopo l'approvazione da parte del team di operazioni di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f4fef-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="f4fef-109">Tutte le azioni correttive, siano esse in attesa di approvazione o già approvate, vengono consolidate nel centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="f4fef-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![Centro notifiche](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="f4fef-111">Un'esperienza a "riquadro unico"</span><span class="sxs-lookup"><span data-stu-id="f4fef-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="f4fef-112">Il centro notifiche include un "riquadro unico" per le attività, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f4fef-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="f4fef-113">approvazione delle azioni di correzione in sospeso;</span><span class="sxs-lookup"><span data-stu-id="f4fef-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="f4fef-114">visualizzazione di un log di controllo delle azioni di correzione già approvate;</span><span class="sxs-lookup"><span data-stu-id="f4fef-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="f4fef-115">revisione delle azioni di correzione completate.</span><span class="sxs-lookup"><span data-stu-id="f4fef-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="f4fef-116">Il team delle operazioni di sicurezza può operare in modo più efficace ed efficiente, poiché il centro informazioni fornisce una panoramica completa di Microsoft 365 Defender sul lavoro.</span><span class="sxs-lookup"><span data-stu-id="f4fef-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="f4fef-117">Accedere al centro notifiche</span><span class="sxs-lookup"><span data-stu-id="f4fef-117">Go to the Action center</span></span>

1. <span data-ttu-id="f4fef-118">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso.</span><span class="sxs-lookup"><span data-stu-id="f4fef-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f4fef-119">Nel riquadro di spostamento, scegliere **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="f4fef-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f4fef-120">Nel centro azioni vengono visualizzate due schede: in **sospeso** e **cronologia**.</span><span class="sxs-lookup"><span data-stu-id="f4fef-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="f4fef-121">Nella scheda **In sospeso** sono elencate le indagini che richiedono la revisione e l'approvazione da parte di qualcuno nel team delle operazioni di sicurezza per continuare.</span><span class="sxs-lookup"><span data-stu-id="f4fef-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="f4fef-122">Assicurarsi di rivedere e agire sugli elementi in sospeso visualizzati nella scheda.</span><span class="sxs-lookup"><span data-stu-id="f4fef-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="f4fef-123">Nella scheda **Cronologia** sono elencate le indagini precedenti e le azioni correttive intraprese automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f4fef-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="f4fef-124">È possibile visualizzare i dati relativi all'ultimo giorno, mese, all'ultima settimana o agli ultimi sei mesi.</span><span class="sxs-lookup"><span data-stu-id="f4fef-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="f4fef-125">Per visualizzare solo le colonne desiderate, selezionare **Personalizza colonne**.</span><span class="sxs-lookup"><span data-stu-id="f4fef-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="f4fef-126">![Centro azioni in Microsoft 365 Defender](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="f4fef-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="f4fef-127">Selezionare un elemento nell'elenco per visualizzare maggiori dettagli relativi a un'indagine.</span><span class="sxs-lookup"><span data-stu-id="f4fef-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="f4fef-128">Si aprirà la visualizzazione dei dettagli dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="f4fef-128">The investigation details view opens.</span></span><br/>![Dettagli indagine](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="f4fef-130">Se l'indagine è relativa al contenuto della posta elettronica (ad esempio, l'entità è una cassetta postale), i dettagli dell'indagine vengono aperti nel centro sicurezza & Compliance ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ).</span><span class="sxs-lookup"><span data-stu-id="f4fef-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="f4fef-131">Se l'indagine riguarda un dispositivo, i dettagli dell'indagine vengono aperti nel Centro sicurezza ([https://security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="f4fef-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="f4fef-132">Se si pensa che qualcosa è stato perso o erroneamente rilevato dalle funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender, fatecelo sapere!</span><span class="sxs-lookup"><span data-stu-id="f4fef-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="f4fef-133">Vedere [How to report false positives/negatives in Automatic Investigation and Response (Air) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="f4fef-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="f4fef-134">Azioni disponibili</span><span class="sxs-lookup"><span data-stu-id="f4fef-134">Available actions</span></span>

<span data-ttu-id="f4fef-135">Poiché vengono eseguite azioni di correzione, sono elencate nella scheda cronologia del centro operazioni.</span><span class="sxs-lookup"><span data-stu-id="f4fef-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="f4fef-136">Tali azioni includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4fef-136">Such actions include the following:</span></span>

- <span data-ttu-id="f4fef-137">Raccolta del pacchetto di analisi</span><span class="sxs-lookup"><span data-stu-id="f4fef-137">Collect investigation package</span></span> 
- <span data-ttu-id="f4fef-138">Dispositivo isolato (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="f4fef-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="f4fef-139">Macchina trasferisce</span><span class="sxs-lookup"><span data-stu-id="f4fef-139">Offboard machine</span></span> 
- <span data-ttu-id="f4fef-140">Esecuzione del codice di rilascio</span><span class="sxs-lookup"><span data-stu-id="f4fef-140">Release code execution</span></span> 
- <span data-ttu-id="f4fef-141">Rilascio dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="f4fef-141">Release from quarantine</span></span> 
- <span data-ttu-id="f4fef-142">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="f4fef-142">Request sample</span></span> 
- <span data-ttu-id="f4fef-143">Limitare l'esecuzione del codice (questa azione può essere annullata)</span><span class="sxs-lookup"><span data-stu-id="f4fef-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="f4fef-144">Eseguire l'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="f4fef-144">Run antivirus scan</span></span> 
- <span data-ttu-id="f4fef-145">Arresto e quarantena</span><span class="sxs-lookup"><span data-stu-id="f4fef-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="f4fef-146">Autorizzazioni necessarie per le attività del centro notifiche</span><span class="sxs-lookup"><span data-stu-id="f4fef-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="f4fef-147">Per approvare o rifiutare le azioni in sospeso nel centro notifiche, è necessario disporre delle autorizzazioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="f4fef-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="f4fef-148">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f4fef-148">Remediation action</span></span> |<span data-ttu-id="f4fef-149">Ruoli e autorizzazioni necessari</span><span class="sxs-lookup"><span data-stu-id="f4fef-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="f4fef-150">Microsoft Defender per la correzione di endpoint (dispositivi)</span><span class="sxs-lookup"><span data-stu-id="f4fef-150">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="f4fef-151">Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="f4fef-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="f4fef-152">--- o ---</span><span class="sxs-lookup"><span data-stu-id="f4fef-152">--- or ---</span></span><br/><span data-ttu-id="f4fef-153">Ruolo di azione di correzione attivo assegnato in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f4fef-153">Active remediation actions role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="f4fef-154">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4fef-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="f4fef-155">- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f4fef-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="f4fef-156">- [Creare e gestire i ruoli per il controllo di accesso basato sui ruoli (Microsoft Defender per endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="f4fef-156">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="f4fef-157">Microsoft Defender per la correzione di Office 365 (contenuto e posta elettronica di Office)</span><span class="sxs-lookup"><span data-stu-id="f4fef-157">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="f4fef-158">Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="f4fef-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="f4fef-159">--- e ---</span><span class="sxs-lookup"><span data-stu-id="f4fef-159">--- and ---</span></span> <br/><span data-ttu-id="f4fef-160">Ruolo di ricerca e spurgo assegnato al centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="f4fef-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="f4fef-161">**Importante** : se il ruolo amministratore della sicurezza è assegnato solo nel centro sicurezza & Compliance, non sarà possibile accedere al centro azioni o alle funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f4fef-161">**IMPORTANT** : If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f4fef-162">È necessario avere il ruolo di amministratore della protezione assegnato in Azure Active Directory o nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4fef-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="f4fef-163">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4fef-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="f4fef-164">- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f4fef-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="f4fef-165">- [Autorizzazioni nel centro sicurezza & conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="f4fef-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="f4fef-166">Gli utenti che hanno il ruolo di amministratore globale assegnato in Azure Active Directory possono approvare o rifiutare qualsiasi azione in sospeso nel centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="f4fef-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="f4fef-167">Tuttavia, come procedura consigliata, l'organizzazione dovrebbe limitare il numero di persone a cui è assegnato il ruolo di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f4fef-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="f4fef-168">È consigliabile usare i ruoli di amministratore della protezione, azioni correttive attive e ricerca ed eliminazione elencati in precedenza per le autorizzazioni del centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="f4fef-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4fef-169">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f4fef-169">Next steps</span></span> 

- [<span data-ttu-id="f4fef-170">Approvare o rifiutare le azioni in sospeso dopo un'analisi automatizzata</span><span class="sxs-lookup"><span data-stu-id="f4fef-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="f4fef-171">Visualizzare i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="f4fef-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

