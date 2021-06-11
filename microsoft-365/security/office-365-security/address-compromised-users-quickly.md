---
title: Risolvere gli account utente compromessi con analisi e risposta automatizzate
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automatizzato, indagine, risposta, correzione, minacce, avanzate, minaccia, protezione, compromessa
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: Scopri come velocizzare il processo di rilevamento e gestione degli account utente compromessi con funzionalità di indagine e risposta automatizzate in Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd84617230e774b92902ef3d11a365c1965ac814
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904141"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="f6e96-104">Risolvere gli account utente compromessi con analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6e96-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="f6e96-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f6e96-105">**Applies to**</span></span>
- [<span data-ttu-id="f6e96-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f6e96-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f6e96-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f6e96-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f6e96-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6e96-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="f6e96-109">[Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) include potenti funzionalità air [(Automated Investigation and Response).](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="f6e96-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="f6e96-110">Tali funzionalità possono risparmiare tempo e fatica al team delle operazioni di sicurezza per affrontare le minacce.</span><span class="sxs-lookup"><span data-stu-id="f6e96-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="f6e96-111">Microsoft continua a migliorare le funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f6e96-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="f6e96-112">Di recente, le funzionalità AIR sono state migliorate per includere un playbook di sicurezza degli utenti compromesso (attualmente in anteprima).</span><span class="sxs-lookup"><span data-stu-id="f6e96-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="f6e96-113">Leggi questo articolo per altre informazioni sul playbook sulla sicurezza degli utenti compromesso.</span><span class="sxs-lookup"><span data-stu-id="f6e96-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="f6e96-114">E vedi il post di blog Velocizzare il tempo per rilevare e rispondere alla compromissione degli utenti e limitare l'ambito di violazione con [Microsoft Defender per](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) Office 365 per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="f6e96-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Indagine automatizzata per un utente compromesso](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="f6e96-116">Il playbook sulla sicurezza degli utenti compromesso consente al team di sicurezza dell'organizzazione di:</span><span class="sxs-lookup"><span data-stu-id="f6e96-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="f6e96-117">Velocizzare il rilevamento degli account utente compromessi;</span><span class="sxs-lookup"><span data-stu-id="f6e96-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="f6e96-118">Limitare l'ambito di una violazione quando un account viene compromesso; e</span><span class="sxs-lookup"><span data-stu-id="f6e96-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="f6e96-119">Rispondere agli utenti compromessi in modo più efficace ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="f6e96-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="f6e96-120">Avvisi utente compromessi</span><span class="sxs-lookup"><span data-stu-id="f6e96-120">Compromised user alerts</span></span>

<span data-ttu-id="f6e96-121">Quando un account utente viene compromesso, si verificano comportamenti atipici o anomali.</span><span class="sxs-lookup"><span data-stu-id="f6e96-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="f6e96-122">Ad esempio, i messaggi di phishing e posta indesiderata potrebbero essere inviati internamente da un account utente attendibile.</span><span class="sxs-lookup"><span data-stu-id="f6e96-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="f6e96-123">Defender for Office 365 può rilevare tali anomalie nei modelli di posta elettronica e nell'attività di collaborazione all'interno Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6e96-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="f6e96-124">In questo caso, vengono attivati gli avvisi e inizia il processo di mitigazione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="f6e96-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="f6e96-125">Ad esempio, ecco un avviso che è stato attivato a causa di un invio di posta elettronica sospetto:</span><span class="sxs-lookup"><span data-stu-id="f6e96-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Avviso attivato a causa dell'invio di posta elettronica sospetto](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="f6e96-127">Ecco un esempio di avviso che è stato attivato quando è stato raggiunto un limite di invio per un utente:</span><span class="sxs-lookup"><span data-stu-id="f6e96-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Avviso attivato dal limite di invio raggiunto](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="f6e96-129">Analizzare e rispondere a un utente compromesso</span><span class="sxs-lookup"><span data-stu-id="f6e96-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="f6e96-130">Quando un account utente viene compromesso, vengono attivati gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f6e96-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="f6e96-131">In alcuni casi, l'account utente viene bloccato e non può inviare ulteriori messaggi di posta elettronica fino a quando il problema non viene risolto dal team delle operazioni di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6e96-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="f6e96-132">In altri casi, viene avviata un'indagine automatizzata che può comportare azioni consigliate da parte del team di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f6e96-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="f6e96-133">Visualizzare e analizzare gli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="f6e96-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="f6e96-134">Visualizzare i dettagli sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6e96-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="f6e96-135">Per eseguire le attività seguenti, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="f6e96-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="f6e96-136">Vedere [Autorizzazioni necessarie per l'utilizzo delle funzionalità AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="f6e96-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="f6e96-137">Visualizzare e analizzare gli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="f6e96-137">View and investigate restricted users</span></span>

<span data-ttu-id="f6e96-138">Sono disponibili alcune opzioni per passare a un elenco di utenti con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="f6e96-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="f6e96-139">Ad esempio, nel Centro sicurezza & conformità, è possibile passare a **Gestione** delle minacce \> **Rivedere** Utenti \> **con restrizioni**.</span><span class="sxs-lookup"><span data-stu-id="f6e96-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="f6e96-140">Nella procedura seguente viene descritto lo spostamento tramite il **dashboard** Avvisi, che rappresenta un ottimo modo per visualizzare vari tipi di avvisi che potrebbero essere stati attivati.</span><span class="sxs-lookup"><span data-stu-id="f6e96-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="f6e96-141">Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f6e96-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="f6e96-142">Nel riquadro di spostamento scegliere **Dashboard** \> **avvisi.**</span><span class="sxs-lookup"><span data-stu-id="f6e96-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="f6e96-143">Nel widget **Altri avvisi** scegliere Utenti **con restrizioni.**</span><span class="sxs-lookup"><span data-stu-id="f6e96-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget Altri avvisi](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="f6e96-145">Verrà aperto l'elenco degli utenti con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="f6e96-145">This opens the list of restricted users.</span></span>

   ![Utenti con restrizioni in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="f6e96-147">Selezionare un account utente nell'elenco per visualizzare i dettagli ed eseguire azioni, ad esempio [il rilascio dell'utente con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="f6e96-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="f6e96-148">Visualizzare i dettagli sulle indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6e96-148">View details about automated investigations</span></span>

<span data-ttu-id="f6e96-149">Una volta avviata un'indagine automatizzata, è possibile visualizzarne i dettagli e i risultati nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="f6e96-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="f6e96-150">Passare a **Indagini sulla gestione delle** \> **minacce** e quindi selezionare un'indagine per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="f6e96-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="f6e96-151">Per ulteriori informazioni, vedere [Visualizzare i dettagli di un'indagine.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="f6e96-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="f6e96-152">Tenere presenti i punti seguenti</span><span class="sxs-lookup"><span data-stu-id="f6e96-152">Keep the following points in mind</span></span>

- <span data-ttu-id="f6e96-153">**Tieniti al primo piano degli avvisi.**</span><span class="sxs-lookup"><span data-stu-id="f6e96-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="f6e96-154">Come sai, più a lungo un compromesso non viene rilevato, maggiore è il potenziale di un impatto diffuso e dei costi per l'organizzazione, i clienti e i partner.</span><span class="sxs-lookup"><span data-stu-id="f6e96-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="f6e96-155">Il rilevamento precoce e la risposta tempestiva sono fondamentali per ridurre le minacce e soprattutto quando l'account di un utente viene compromesso.</span><span class="sxs-lookup"><span data-stu-id="f6e96-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="f6e96-156">**L'automazione assiste, ma non sostituisce, il team delle operazioni di sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="f6e96-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="f6e96-157">Le funzionalità di analisi e risposta automatizzate possono rilevare un utente compromesso nelle prime fasi, ma il team delle operazioni di sicurezza dovrà probabilmente impegnarsi ed eseguire alcune indagini e correzioni.</span><span class="sxs-lookup"><span data-stu-id="f6e96-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="f6e96-158">Serve aiuto per questo?</span><span class="sxs-lookup"><span data-stu-id="f6e96-158">Need some help with this?</span></span> <span data-ttu-id="f6e96-159">Vedi [Rivedere e approvare le azioni.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="f6e96-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="f6e96-160">**Non fare affidamento su un avviso di accesso sospetto come unico indicatore.**</span><span class="sxs-lookup"><span data-stu-id="f6e96-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="f6e96-161">Quando un account utente viene compromesso, potrebbe o meno attivare un avviso di accesso sospetto.</span><span class="sxs-lookup"><span data-stu-id="f6e96-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="f6e96-162">A volte è la serie di attività che si verificano dopo la compromissione di un account che attiva un avviso.</span><span class="sxs-lookup"><span data-stu-id="f6e96-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="f6e96-163">Per saperne di più sugli avvisi, vedere</span><span class="sxs-lookup"><span data-stu-id="f6e96-163">Want to know more about alerts?</span></span> <span data-ttu-id="f6e96-164">Vedere [Criteri di avviso](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f6e96-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6e96-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6e96-165">Next steps</span></span>

- [<span data-ttu-id="f6e96-166">Esaminare le autorizzazioni necessarie per l'utilizzo delle funzionalità AIR</span><span class="sxs-lookup"><span data-stu-id="f6e96-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="f6e96-167">Trovare e analizzare la posta elettronica dannosa in Office 365</span><span class="sxs-lookup"><span data-stu-id="f6e96-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="f6e96-168">Informazioni su AIR in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f6e96-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="f6e96-169">Visitare la Microsoft 365 roadmap per vedere cosa verrà presto e implementazione</span><span class="sxs-lookup"><span data-stu-id="f6e96-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)