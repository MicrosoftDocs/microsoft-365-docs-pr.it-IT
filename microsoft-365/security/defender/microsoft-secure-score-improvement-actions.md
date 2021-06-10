---
title: Valutare il proprio livello di sicurezza tramite Microsoft Secure Score
description: Descrive come eseguire un'azione per migliorare microsoft Secure Score nel centro sicurezza Microsoft 365 sicurezza.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246398"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="40d6d-104">Valutare il proprio stato di sicurezza con Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="40d6d-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="40d6d-105">Microsoft Secure Score è una misurazione della postura di sicurezza di una organizzazione, in cui i numeri più alti indicano l'esecuzione di più azioni di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="40d6d-106">È disponibile nel centro sicurezza https://security.microsoft.com/securescore [Microsoft 365 sicurezza.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="40d6d-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="40d6d-107">Per trovare più rapidamente le informazioni necessarie, le azioni di miglioramento Microsoft sono organizzate in gruppi:</span><span class="sxs-lookup"><span data-stu-id="40d6d-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="40d6d-108">Identità (Azure Active Directory account & ruoli)</span><span class="sxs-lookup"><span data-stu-id="40d6d-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="40d6d-109">Dispositivo (Microsoft Defender for Endpoint, noto come [Microsoft Secure Score per dispositivi](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="40d6d-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="40d6d-110">App (app di posta elettronica e cloud, Office 365 e Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="40d6d-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="40d6d-111">Nella recente versione di Microsoft Secure Score è stato rilasciato un modello di punteggio migliorato che ha reso Microsoft Secure Score temporaneamente incompatibile con Identity Secure Score e l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="40d6d-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="40d6d-112">Visualizza dettagli</span><span class="sxs-lookup"><span data-stu-id="40d6d-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="40d6d-113">Nella pagina panoramica di Microsoft Secure Score, visualizzare la modalità di suddivisione dei punti tra questi gruppi e i punti disponibili.</span><span class="sxs-lookup"><span data-stu-id="40d6d-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="40d6d-114">Puoi anche ottenere una visualizzazione generale del punteggio totale, della tendenza storica del punteggio sicuro con confronti di benchmark e delle azioni di miglioramento con priorità che possono essere intraprese per migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="40d6d-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Home page punteggio sicuro](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="40d6d-116">Controllare il punteggio corrente</span><span class="sxs-lookup"><span data-stu-id="40d6d-116">Check your current score</span></span>

<span data-ttu-id="40d6d-117">Per controllare il punteggio corrente, passare alla pagina Panoramica del punteggio sicuro Microsoft e cercare il riquadro **Il punteggio sicuro**.</span><span class="sxs-lookup"><span data-stu-id="40d6d-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="40d6d-118">Il punteggio verrà visualizzato come percentuale, insieme al numero di punti ottenuti rispetto al totale dei punti possibili.</span><span class="sxs-lookup"><span data-stu-id="40d6d-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="40d6d-119">Inoltre, se si seleziona il **pulsante Includi** accanto al punteggio, è possibile scegliere diverse visualizzazioni del punteggio.</span><span class="sxs-lookup"><span data-stu-id="40d6d-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="40d6d-120">Queste diverse visualizzazioni del punteggio verranno visualizzate nel grafico nel riquadro del punteggio e nel grafico di suddivisione dei punti.</span><span class="sxs-lookup"><span data-stu-id="40d6d-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="40d6d-121">Di seguito sono riportati i punteggi che è possibile aggiungere alla visualizzazione del punteggio complessivo per ottenere un quadro più completo del punteggio complessivo:</span><span class="sxs-lookup"><span data-stu-id="40d6d-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="40d6d-122">**Punteggio pianificato**: mostra il punteggio proiettato al termine delle azioni pianificate</span><span class="sxs-lookup"><span data-stu-id="40d6d-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="40d6d-123">**Punteggio di licenza corrente:** mostra il punteggio che può essere ottenuto con la licenza Microsoft corrente</span><span class="sxs-lookup"><span data-stu-id="40d6d-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="40d6d-124">**Punteggio raggiungibile**: Mostra il punteggio che può essere ottenuto con le licenze Microsoft e l'accettazione del rischio corrente</span><span class="sxs-lookup"><span data-stu-id="40d6d-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="40d6d-125">Questa visualizzazione è l'aspetto che avrà se hai incluso tutte le possibili visualizzazioni del punteggio:</span><span class="sxs-lookup"><span data-stu-id="40d6d-125">This view is what it will look like if you've included all possible score views:</span></span>

![Il punteggio sicuro, incluso il punteggio pianificato, il punteggio della licenza corrente e il punteggio raggiungibile](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="40d6d-127">Agire per migliorare il punteggio</span><span class="sxs-lookup"><span data-stu-id="40d6d-127">Take action to improve your score</span></span>

<span data-ttu-id="40d6d-128">Nella **scheda Azioni di miglioramento** sono elencati i suggerimenti per la sicurezza che affrontano le possibili superfici di attacco.</span><span class="sxs-lookup"><span data-stu-id="40d6d-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="40d6d-129">Include anche il loro stato (per affrontare, pianificato, rischio accettato, risolto tramite terze parti, risolto tramite mitigazione alternativa e completato).</span><span class="sxs-lookup"><span data-stu-id="40d6d-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="40d6d-130">È possibile cercare, filtrare e raggruppare tutte le azioni di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="40d6d-131">Classificazione</span><span class="sxs-lookup"><span data-stu-id="40d6d-131">Ranking</span></span>

<span data-ttu-id="40d6d-132">La classificazione si basa sul numero di punti da raggiungere, sulla difficoltà di implementazione, sull'impatto dell'utente e sulla complessità.</span><span class="sxs-lookup"><span data-stu-id="40d6d-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="40d6d-133">Le azioni di miglioramento di livello più alto hanno un gran numero di punti rimanenti con difficoltà, impatto utente e complessità bassi.</span><span class="sxs-lookup"><span data-stu-id="40d6d-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="40d6d-134">Visualizzare i dettagli delle azioni di miglioramento</span><span class="sxs-lookup"><span data-stu-id="40d6d-134">View improvement action details</span></span>

<span data-ttu-id="40d6d-135">Quando si seleziona un'azione di miglioramento specifica, viene visualizzato un riquadro a comparsa a pagina intera.</span><span class="sxs-lookup"><span data-stu-id="40d6d-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![Esempio di riquadro a comparsa azione di miglioramento](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="40d6d-137">Per completare l'azione, sono disponibili alcune opzioni:</span><span class="sxs-lookup"><span data-stu-id="40d6d-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="40d6d-138">Seleziona **Gestisci** per passare alla schermata di configurazione e apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="40d6d-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="40d6d-139">Potrai quindi ottenere i punti che valgono l'azione, visibili nel fly out. L'aggiornamento dei punti in genere è di circa 24 ore.</span><span class="sxs-lookup"><span data-stu-id="40d6d-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="40d6d-140">Selezionare **Condividi** per copiare il collegamento diretto all'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="40d6d-141">È inoltre possibile scegliere la piattaforma per condividere il collegamento, ad esempio posta elettronica, Microsoft Teams o Microsoft Planner.</span><span class="sxs-lookup"><span data-stu-id="40d6d-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="40d6d-142">Aggiungere **note** per tenere traccia dello stato o di qualsiasi altro elemento su cui si desidera aggiungere commenti.</span><span class="sxs-lookup"><span data-stu-id="40d6d-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="40d6d-143">Se aggiungi tag  personalizzati all'azione di miglioramento, puoi filtrare in base a tali tag.</span><span class="sxs-lookup"><span data-stu-id="40d6d-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="40d6d-144">Scegliere lo stato di un'azione di miglioramento</span><span class="sxs-lookup"><span data-stu-id="40d6d-144">Choose an improvement action status</span></span>

<span data-ttu-id="40d6d-145">Scegliere eventuali stati e registrare note specifiche per l'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="40d6d-146">**Da affrontare:** si riconosce che l'azione di miglioramento è necessaria e si prevede di affrontarla a un certo punto in futuro.</span><span class="sxs-lookup"><span data-stu-id="40d6d-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="40d6d-147">Questo stato si applica anche alle azioni rilevate parzialmente, ma non completamente completate.</span><span class="sxs-lookup"><span data-stu-id="40d6d-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="40d6d-148">**Pianificato:** sono in atto piani concreti per completare l'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="40d6d-149">**Rischio accettato:** la sicurezza deve essere sempre bilanciata con l'usabilità e non tutte le raccomandazioni funzioneranno per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="40d6d-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="40d6d-150">In questo caso, è possibile scegliere di accettare il rischio o il rischio rimanente e non di eseguire l'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="40d6d-151">Non verranno dati punti, ma l'azione non sarà più visibile nell'elenco delle azioni di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="40d6d-152">È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="40d6d-153">**Risolto tramite terze parti** e **risolto** tramite mitigazione alternativa: l'azione di miglioramento è già stata affrontata da un'applicazione o un software di terze parti o uno strumento interno.</span><span class="sxs-lookup"><span data-stu-id="40d6d-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="40d6d-154">Potrai ottenere i punti che valgono l'azione, in modo che il punteggio rifletta meglio la tua posizione di sicurezza complessiva.</span><span class="sxs-lookup"><span data-stu-id="40d6d-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="40d6d-155">Se uno strumento interno o di terze parti non copre più il controllo, puoi scegliere un altro stato.</span><span class="sxs-lookup"><span data-stu-id="40d6d-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="40d6d-156">Tieni presente che Microsoft non avrà visibilità sulla completezza dell'implementazione se l'azione di miglioramento viene contrassegnata come uno di questi stati.</span><span class="sxs-lookup"><span data-stu-id="40d6d-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="40d6d-157">Azioni di & gestione delle vulnerabilità di miglioramento delle minacce</span><span class="sxs-lookup"><span data-stu-id="40d6d-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="40d6d-158">Per le azioni di miglioramento nella categoria "Dispositivo", non puoi scegliere gli stati.</span><span class="sxs-lookup"><span data-stu-id="40d6d-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="40d6d-159">Al contrario, verrà indirizzato all'gestione di minacce e vulnerabilità [di](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) sicurezza associata nella Microsoft Defender Security Center [per](/windows/security/threat-protection/microsoft-defender-atp/use) eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="40d6d-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="40d6d-160">L'eccezione scelta e la giustificazione da scrivere saranno specifiche per tale portale.</span><span class="sxs-lookup"><span data-stu-id="40d6d-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="40d6d-161">Non sarà presente nel portale Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="40d6d-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="40d6d-162">Azioni di miglioramento completate</span><span class="sxs-lookup"><span data-stu-id="40d6d-162">Completed improvement actions</span></span>

<span data-ttu-id="40d6d-163">Le azioni di miglioramento hanno uno stato "completato" dopo aver raggiunto tutti i punti possibili per l'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="40d6d-164">Le azioni di miglioramento completate vengono confermate anche se i dati Microsoft sono stati confermati e non è possibile modificare lo stato.</span><span class="sxs-lookup"><span data-stu-id="40d6d-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="40d6d-165">Valutare le informazioni ed esaminare l'impatto degli utenti</span><span class="sxs-lookup"><span data-stu-id="40d6d-165">Assess information and review user impact</span></span>

<span data-ttu-id="40d6d-166">La sezione **"A colpo d'occhio"** ti dirà la categoria, gli attacchi da cui può proteggersi e il prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d6d-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="40d6d-167">**L'impatto** dell'utente è ciò che gli utenti  sperimenteranno se viene eseguita l'azione di miglioramento e gli utenti interessati sono le persone che saranno interessate.</span><span class="sxs-lookup"><span data-stu-id="40d6d-167">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="40d6d-168">Implementare l'azione di miglioramento</span><span class="sxs-lookup"><span data-stu-id="40d6d-168">Implement the improvement action</span></span>

<span data-ttu-id="40d6d-169">La **sezione Implementazione** mostra tutti i prerequisiti, i passaggi successivi dettagliati per completare l'azione di miglioramento, lo stato di implementazione corrente dell'azione di miglioramento e altri collegamenti.</span><span class="sxs-lookup"><span data-stu-id="40d6d-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="40d6d-170">I prerequisiti includono le licenze necessarie o le azioni da completare prima che venga affrontata l'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="40d6d-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="40d6d-171">Assicurati di disporre di postazioni sufficienti nella licenza per completare l'azione di miglioramento e che tali licenze siano applicate agli utenti necessari.</span><span class="sxs-lookup"><span data-stu-id="40d6d-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="40d6d-172">L'opinione degli utenti è importante</span><span class="sxs-lookup"><span data-stu-id="40d6d-172">We want to hear from you</span></span>

<span data-ttu-id="40d6d-173">In caso di problemi, contattaci pubblicando la community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="40d6d-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="40d6d-174">Stiamo monitorando la community e forniremo assistenza.</span><span class="sxs-lookup"><span data-stu-id="40d6d-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="40d6d-175">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="40d6d-175">Related resources</span></span>

- [<span data-ttu-id="40d6d-176">Panoramica di Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="40d6d-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="40d6d-177">Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="40d6d-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="40d6d-178">Novità in arrivo</span><span class="sxs-lookup"><span data-stu-id="40d6d-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="40d6d-179">Novità</span><span class="sxs-lookup"><span data-stu-id="40d6d-179">What's new</span></span>](microsoft-secure-score-whats-new.md)