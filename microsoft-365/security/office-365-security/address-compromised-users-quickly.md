---
title: Indirizzare gli account utente compromessi con indagini e risposte automatiche
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzato, minaccia, protezione, compromesso
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Informazioni su come velocizzare il processo di rilevamento e indirizzamento degli account utente compromessi con le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: 19c9bad33263178f92c6fe523b44497cf38ebd53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616738"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="cfd74-104">Indirizzare gli account utente compromessi con indagini e risposte automatiche</span><span class="sxs-lookup"><span data-stu-id="cfd74-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cfd74-105">[Microsoft Defender per Office 365 piano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) include potenti funzionalità [di analisi e risposta automatizzate](office-365-air.md) (Air).</span><span class="sxs-lookup"><span data-stu-id="cfd74-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="cfd74-106">Tali funzionalità sono in grado di salvare il team di operazioni di sicurezza molto tempo e lo sforzo per gestire le minacce.</span><span class="sxs-lookup"><span data-stu-id="cfd74-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="cfd74-107">Microsoft continua a migliorare le funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfd74-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="cfd74-108">Recentemente, le funzionalità AEREe sono state migliorate per includere un playbook di sicurezza degli utenti compromesso (attualmente in anteprima).</span><span class="sxs-lookup"><span data-stu-id="cfd74-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="cfd74-109">Leggere questo articolo per ulteriori informazioni sul PlayBook di sicurezza degli utenti compromessi.</span><span class="sxs-lookup"><span data-stu-id="cfd74-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="cfd74-110">Per ulteriori informazioni, vedere il post del Blog [velocizzare il tempo necessario per rilevare e rispondere al compromesso degli utenti e limitare l'ambito di violazione con Microsoft Defender per Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) .</span><span class="sxs-lookup"><span data-stu-id="cfd74-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Analisi automatizzata per un utente compromesso](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="cfd74-112">Il PlayBook di sicurezza utente compromesso consente al team di sicurezza dell'organizzazione di:</span><span class="sxs-lookup"><span data-stu-id="cfd74-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="cfd74-113">Velocizzare il rilevamento degli account utente compromessi;</span><span class="sxs-lookup"><span data-stu-id="cfd74-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="cfd74-114">Limitare l'ambito di una violazione quando un account è compromesso; e</span><span class="sxs-lookup"><span data-stu-id="cfd74-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="cfd74-115">Rispondere agli utenti compromessi in modo più efficace ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="cfd74-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="cfd74-116">Avvisi degli utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="cfd74-116">Compromised user alerts</span></span>

<span data-ttu-id="cfd74-117">Quando un account utente viene compromesso, si verificano comportamenti atipici o anomali.</span><span class="sxs-lookup"><span data-stu-id="cfd74-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="cfd74-118">Ad esempio, i messaggi di phishing e di posta indesiderata possono essere inviati internamente da un account utente attendibile.</span><span class="sxs-lookup"><span data-stu-id="cfd74-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="cfd74-119">Defender per Office 365 è in grado di rilevare tali anomalie nei modelli di posta elettronica e attività di collaborazione all'interno di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfd74-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="cfd74-120">In questo caso, gli avvisi vengono attivati e il processo di attenuazione delle minacce inizia.</span><span class="sxs-lookup"><span data-stu-id="cfd74-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="cfd74-121">Ad esempio, ecco un avviso che è stato attivato a causa dell'invio di messaggi di posta elettronica sospetti:</span><span class="sxs-lookup"><span data-stu-id="cfd74-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Avviso attivato a causa dell'invio di messaggi di posta elettronica sospetti](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="cfd74-123">Di seguito è riportato un esempio di avviso che è stato attivato quando è stato raggiunto un limite di invio per un utente:</span><span class="sxs-lookup"><span data-stu-id="cfd74-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Avviso attivato tramite l'invio del limite raggiunto](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="cfd74-125">Esaminare e rispondere a un utente compromesso</span><span class="sxs-lookup"><span data-stu-id="cfd74-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="cfd74-126">Quando un account utente viene compromesso, vengono attivati gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="cfd74-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="cfd74-127">In alcuni casi, l'account utente viene bloccato e impedito l'invio di ulteriori messaggi di posta elettronica fino a quando il problema non viene risolto dal team di operazioni di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfd74-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="cfd74-128">In altri casi, viene avviata un'indagine automatizzata che può provocare le azioni consigliate che il team di sicurezza deve eseguire.</span><span class="sxs-lookup"><span data-stu-id="cfd74-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="cfd74-129">Visualizzazione e analisi degli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="cfd74-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="cfd74-130">Visualizzare i dettagli sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="cfd74-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="cfd74-131">È necessario disporre delle autorizzazioni appropriate per eseguire le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="cfd74-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="cfd74-132">Vedere le [autorizzazioni necessarie per utilizzare le funzionalità aeree](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="cfd74-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="cfd74-133">Visualizzazione e analisi degli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="cfd74-133">View and investigate restricted users</span></span>

<span data-ttu-id="cfd74-134">Sono disponibili alcune opzioni per l'esplorazione di un elenco di utenti con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="cfd74-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="cfd74-135">Ad esempio, nel centro sicurezza & conformità, è possibile accedere a utenti con restrizioni di verifica di **gestione delle minacce** \>  \> .</span><span class="sxs-lookup"><span data-stu-id="cfd74-135">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="cfd74-136">Nella procedura seguente viene descritta la struttura di spostamento tramite il dashboard **avvisi** , che consente di visualizzare diversi tipi di avvisi che potrebbero essere stati attivati.</span><span class="sxs-lookup"><span data-stu-id="cfd74-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="cfd74-137">Andare su <https://protection.office.com> ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cfd74-137">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="cfd74-138">Nel riquadro di spostamento, scegliere  \> **Dashboard** avvisi.</span><span class="sxs-lookup"><span data-stu-id="cfd74-138">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="cfd74-139">Nell' **altro widget avvisi** scegliere utenti con **restrizioni**.</span><span class="sxs-lookup"><span data-stu-id="cfd74-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Altri widget avvisi](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="cfd74-141">Verrà aperto l'elenco degli utenti con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="cfd74-141">This opens the list of restricted users.</span></span>

   ![Utenti con restrizioni in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="cfd74-143">Selezionare un account utente nell'elenco per visualizzare i dettagli e intraprendere un'azione, ad esempio [il rilascio dell'utente con restrizioni](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="cfd74-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="cfd74-144">Visualizzare i dettagli sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="cfd74-144">View details about automated investigations</span></span>

<span data-ttu-id="cfd74-145">Dopo aver avviato un'indagine automatizzata, è possibile visualizzare i dettagli e i risultati nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="cfd74-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="cfd74-146">Andare a indagini sulla **gestione delle minacce** \> e quindi selezionare un'analisi per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="cfd74-146">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="cfd74-147">Per ulteriori informazioni, vedere [visualizzare i dettagli di un'indagine](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="cfd74-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="cfd74-148">Tenere in considerazione i seguenti punti</span><span class="sxs-lookup"><span data-stu-id="cfd74-148">Keep the following points in mind</span></span>

- <span data-ttu-id="cfd74-149">**Rimanere al di sopra degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="cfd74-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="cfd74-150">Come si sa, più a lungo non viene rilevato un compromesso, maggiore è il potenziale di impatto e costo diffuso per l'organizzazione, i clienti e i partner.</span><span class="sxs-lookup"><span data-stu-id="cfd74-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="cfd74-151">Il rilevamento precoce e la risposta tempestiva sono fondamentali per attenuare le minacce e, soprattutto, quando l'account di un utente viene compromesso.</span><span class="sxs-lookup"><span data-stu-id="cfd74-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="cfd74-152">**L'automazione fornisce assistenza, ma non sostituisce il team delle operazioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="cfd74-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="cfd74-153">L'analisi automatizzata e le funzionalità di risposta possono rilevare un utente compromesso all'inizio, ma il team delle operazioni di sicurezza avrà probabilmente bisogno di intraprendere indagini e correzioni.</span><span class="sxs-lookup"><span data-stu-id="cfd74-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="cfd74-154">Serve aiuto?</span><span class="sxs-lookup"><span data-stu-id="cfd74-154">Need some help with this?</span></span> <span data-ttu-id="cfd74-155">Vedere [operazioni di revisione e approvazione](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="cfd74-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="cfd74-156">**Non fare affidamento su un avviso di accesso sospetto come solo indicatore**.</span><span class="sxs-lookup"><span data-stu-id="cfd74-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="cfd74-157">Quando un account utente viene compromesso, potrebbe essere attivato o meno un avviso di accesso sospetto.</span><span class="sxs-lookup"><span data-stu-id="cfd74-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="cfd74-158">A volte è la serie di attività che si verificano dopo che un account è stato compromesso che attiva un avviso.</span><span class="sxs-lookup"><span data-stu-id="cfd74-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="cfd74-159">Per ulteriori informazioni sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="cfd74-159">Want to know more about alerts?</span></span> <span data-ttu-id="cfd74-160">Vedere [criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="cfd74-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cfd74-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cfd74-161">Next steps</span></span>

- [<span data-ttu-id="cfd74-162">Esaminare le autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe</span><span class="sxs-lookup"><span data-stu-id="cfd74-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="cfd74-163">Trovare e indagare messaggi di posta elettronica dannosi in Office 365</span><span class="sxs-lookup"><span data-stu-id="cfd74-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="cfd74-164">Informazioni su AIR in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cfd74-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="cfd74-165">Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita</span><span class="sxs-lookup"><span data-stu-id="cfd74-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
