---
title: Microsoft Secure Score
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, come migliorare la posizione di sicurezza e gli amministratori di sicurezza che possono aspettarsi.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center, azioni di miglioramento
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682572"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="6edb9-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="6edb9-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6edb9-105">Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite.</span><span class="sxs-lookup"><span data-stu-id="6edb9-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="6edb9-106">Può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="6edb9-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="6edb9-107">Seguendo i suggerimenti per il Punteggio sicuro è possibile proteggere l'organizzazione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="6edb9-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="6edb9-108">Da un Dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6edb9-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="6edb9-109">Secure Score aiuta le organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="6edb9-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="6edb9-110">Segnalare lo stato corrente della posizione di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6edb9-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="6edb9-111">Migliorare la propria posizione di sicurezza fornendo individuabilità, visibilità, orientamento e controllo.</span><span class="sxs-lookup"><span data-stu-id="6edb9-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="6edb9-112">Confronta con benchmark e stabilisci indicatori di prestazioni chiave (KPI).</span><span class="sxs-lookup"><span data-stu-id="6edb9-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="6edb9-113">Le organizzazioni accedono alla visualizzazione robusta delle metriche e delle tendenze, all'integrazione con altri prodotti Microsoft, al confronto tra organizzazioni simili e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6edb9-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="6edb9-114">Il Punteggio può anche riflettere quando le soluzioni di terze parti sono state indirizzate alle azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="6edb9-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Homepage del Punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="6edb9-116">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="6edb9-116">How it works</span></span>

<span data-ttu-id="6edb9-117">Sono stati assegnati punti per le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6edb9-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="6edb9-118">Configurazione delle funzionalità di sicurezza consigliate</span><span class="sxs-lookup"><span data-stu-id="6edb9-118">Configuring recommended security features</span></span>
- <span data-ttu-id="6edb9-119">Esecuzione di attività correlate alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-119">Performing security-related tasks</span></span>
- <span data-ttu-id="6edb9-120">Risoluzione delle operazioni di miglioramento con un'applicazione o un software di terze parti o una attenuazione alternativa</span><span class="sxs-lookup"><span data-stu-id="6edb9-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="6edb9-121">Alcune azioni di miglioramento offrono solo punti quando sono state completate.</span><span class="sxs-lookup"><span data-stu-id="6edb9-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="6edb9-122">Alcuni forniscono punti parziali se sono stati completati per alcuni dispositivi o utenti.</span><span class="sxs-lookup"><span data-stu-id="6edb9-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="6edb9-123">Se non è possibile o non si desidera applicare una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.</span><span class="sxs-lookup"><span data-stu-id="6edb9-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="6edb9-124">Se si dispone di una licenza per uno dei prodotti Microsoft supportati, verranno visualizzati i suggerimenti per tali prodotti.</span><span class="sxs-lookup"><span data-stu-id="6edb9-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="6edb9-125">Viene mostrato il set completo di possibili miglioramenti per un prodotto, indipendentemente dall'edizione della licenza, dall'abbonamento o dal piano.</span><span class="sxs-lookup"><span data-stu-id="6edb9-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="6edb9-126">In questo modo, è possibile comprendere le procedure consigliate per la sicurezza e migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="6edb9-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="6edb9-127">La posizione di sicurezza assoluta, rappresentata da un punteggio sicuro, rimane invariata indipendentemente dalle licenze possedute dall'organizzazione per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="6edb9-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="6edb9-128">Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="6edb9-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="6edb9-129">Il Punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine di azione per la visualizzazione e il miglioramento.</span><span class="sxs-lookup"><span data-stu-id="6edb9-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="6edb9-130">Secure Score sincronizza anche tutti i giorni per ricevere i dati di sistema relativi ai punti ottenuti per ogni azione.</span><span class="sxs-lookup"><span data-stu-id="6edb9-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="6edb9-131">Scenari principali</span><span class="sxs-lookup"><span data-stu-id="6edb9-131">Key scenarios</span></span>

- [<span data-ttu-id="6edb9-132">Controllare il punteggio corrente</span><span class="sxs-lookup"><span data-stu-id="6edb9-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="6edb9-133">Confronta il tuo punteggio con organizzazioni come le tue</span><span class="sxs-lookup"><span data-stu-id="6edb9-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="6edb9-134">Visualizzare le azioni di miglioramento e decidere un piano d'azione</span><span class="sxs-lookup"><span data-stu-id="6edb9-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="6edb9-135">Avviare i flussi di lavoro per l'analisi o l'implementazione</span><span class="sxs-lookup"><span data-stu-id="6edb9-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="6edb9-136">Centro sicurezza e integrazione di Microsoft 365 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="6edb9-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="6edb9-137">Come vengono segnate le azioni di miglioramento</span><span class="sxs-lookup"><span data-stu-id="6edb9-137">How improvement actions are scored</span></span>

<span data-ttu-id="6edb9-138">Ogni azione di miglioramento vale 10 punti o meno e la maggior parte è classificata in modo binario.</span><span class="sxs-lookup"><span data-stu-id="6edb9-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="6edb9-139">Se si implementa l'azione di miglioramento, ad esempio crea un nuovo criterio o si attiva un'impostazione specifica, si ottiene il 100% dei punti.</span><span class="sxs-lookup"><span data-stu-id="6edb9-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="6edb9-140">Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale.</span><span class="sxs-lookup"><span data-stu-id="6edb9-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="6edb9-141">Ad esempio, un'azione di miglioramento dichiara di ottenere 10 punti proteggendo tutti gli utenti con l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="6edb9-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="6edb9-142">Si hanno solo 50 di 100 utenti totali protetti, quindi si otterrebbe un punteggio parziale di 5 punti (50 protected/100 Total \* 10 Max PTS = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="6edb9-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="6edb9-143">Prodotti inclusi nel punteggio sicuro</span><span class="sxs-lookup"><span data-stu-id="6edb9-143">Products included in Secure Score</span></span>

<span data-ttu-id="6edb9-144">Sono attualmente disponibili suggerimenti per Microsoft 365 (incluso Exchange Online), Azure Active Directory, Microsoft Defender per endpoint, Microsoft Defender per Identity e cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="6edb9-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="6edb9-145">Sono disponibili suggerimenti per gli altri prodotti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6edb9-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="6edb9-146">I suggerimenti non riguarderanno tutte le superfici di attacco associate a ciascun prodotto, ma sono una buona linea di base.</span><span class="sxs-lookup"><span data-stu-id="6edb9-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="6edb9-147">È inoltre possibile contrassegnare le azioni di miglioramento riportate da terze parti o da una attenuazione alternativa.</span><span class="sxs-lookup"><span data-stu-id="6edb9-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="6edb9-148">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-148">Security defaults</span></span>

<span data-ttu-id="6edb9-149">Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.</span><span class="sxs-lookup"><span data-stu-id="6edb9-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="6edb9-150">Se si attivano le impostazioni predefinite per la sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:</span><span class="sxs-lookup"><span data-stu-id="6edb9-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="6edb9-151">Verificare che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro (9 punti)</span><span class="sxs-lookup"><span data-stu-id="6edb9-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="6edb9-152">Richiedere l'AMF per i ruoli amministrativi (10 punti)</span><span class="sxs-lookup"><span data-stu-id="6edb9-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="6edb9-153">Abilitare il criterio per bloccare l'autenticazione legacy (7 punti)</span><span class="sxs-lookup"><span data-stu-id="6edb9-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="6edb9-154">Le impostazioni predefinite per la sicurezza includono funzionalità di sicurezza che forniscono una sicurezza analoga alle azioni di miglioramento "criterio di accesso a rischio" e "criterio di rischio utente".</span><span class="sxs-lookup"><span data-stu-id="6edb9-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="6edb9-155">Invece di impostare questi criteri in base alle impostazioni predefinite per la sicurezza, è consigliabile aggiornare i relativi stati in "risolti tramite attenuazione alternativa".</span><span class="sxs-lookup"><span data-stu-id="6edb9-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6edb9-156">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6edb9-156">Required permissions</span></span>

<span data-ttu-id="6edb9-157">Per avere l'autorizzazione per accedere a Microsoft Secure score, è necessario essere assegnati a uno dei ruoli seguenti in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6edb9-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="6edb9-158">Ruoli di lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="6edb9-158">Read and write roles</span></span>

<span data-ttu-id="6edb9-159">Con l'accesso in lettura e in scrittura, è possibile apportare modifiche e interagire direttamente con il Punteggio sicuro.</span><span class="sxs-lookup"><span data-stu-id="6edb9-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="6edb9-160">È inoltre possibile assegnare l'accesso in sola lettura ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="6edb9-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="6edb9-161">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="6edb9-161">Global administrator</span></span>
* <span data-ttu-id="6edb9-162">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-162">Security administrator</span></span>
* <span data-ttu-id="6edb9-163">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="6edb9-163">Exchange administrator</span></span>
* <span data-ttu-id="6edb9-164">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6edb9-164">SharePoint administrator</span></span>
* <span data-ttu-id="6edb9-165">Amministratore account</span><span class="sxs-lookup"><span data-stu-id="6edb9-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="6edb9-166">Ruoli di sola lettura</span><span class="sxs-lookup"><span data-stu-id="6edb9-166">Read-only roles</span></span>

<span data-ttu-id="6edb9-167">Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare le aree dei punteggi o modificare i confronti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6edb9-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="6edb9-168">Amministratore del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="6edb9-168">Helpdesk administrator</span></span>
* <span data-ttu-id="6edb9-169">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="6edb9-169">User administrator</span></span>
* <span data-ttu-id="6edb9-170">Amministratore del servizio</span><span class="sxs-lookup"><span data-stu-id="6edb9-170">Service administrator</span></span>
* <span data-ttu-id="6edb9-171">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-171">Security reader</span></span>
* <span data-ttu-id="6edb9-172">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-172">Security operator</span></span>
* <span data-ttu-id="6edb9-173">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="6edb9-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="6edb9-174">Sensibilizzazione ai rischi</span><span class="sxs-lookup"><span data-stu-id="6edb9-174">Risk awareness</span></span>

<span data-ttu-id="6edb9-175">Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6edb9-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="6edb9-176">Non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati.</span><span class="sxs-lookup"><span data-stu-id="6edb9-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="6edb9-177">Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft che possono contribuire a compensare il rischio di essere violati.</span><span class="sxs-lookup"><span data-stu-id="6edb9-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="6edb9-178">Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="6edb9-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="6edb9-179">L'opinione degli utenti è importante</span><span class="sxs-lookup"><span data-stu-id="6edb9-179">We want to hear from you</span></span>

<span data-ttu-id="6edb9-180">In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="6edb9-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="6edb9-181">Si sta monitorando la community e viene fornita assistenza.</span><span class="sxs-lookup"><span data-stu-id="6edb9-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="6edb9-182">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="6edb9-182">Related resources</span></span>

- [<span data-ttu-id="6edb9-183">Valutazione del profilo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6edb9-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="6edb9-184">Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="6edb9-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="6edb9-185">Novità in arrivo</span><span class="sxs-lookup"><span data-stu-id="6edb9-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="6edb9-186">Novità</span><span class="sxs-lookup"><span data-stu-id="6edb9-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
