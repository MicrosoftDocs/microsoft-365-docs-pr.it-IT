---
title: Microsoft Secure Score
description: Descrive Microsoft Secure Score nel Centro sicurezza Microsoft 365, come migliorare la sicurezza e cosa possono aspettarsi gli amministratori della sicurezza.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 236ac67c5a4efeb4d46f59f5fe283b396adb9aa5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906735"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="0c2dc-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="0c2dc-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0c2dc-105">Microsoft Secure Score è una misurazione del livello di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="0c2dc-106">È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="0c2dc-107">Seguendo i consigli relativi al punteggio sicuro è possibile proteggere l'organizzazione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="0c2dc-108">Da un dashboard centralizzato nel Centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="0c2dc-109">Secure Score aiuta le organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="0c2dc-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="0c2dc-110">Report sullo stato corrente della sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="0c2dc-111">Migliora la loro sicurezza fornendo individuabilità, visibilità, guida e controllo.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="0c2dc-112">Confronta con i benchmark e stabiliscono indicatori di prestazioni chiave (KPI).</span><span class="sxs-lookup"><span data-stu-id="0c2dc-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="0c2dc-113">Le organizzazioni ottengono l'accesso a visualizzazioni affidabili di metriche e tendenze, integrazione con altri prodotti Microsoft, confronto dei punteggi con organizzazioni simili e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="0c2dc-114">Il punteggio può anche riflettere quando soluzioni di terze parti hanno indirizzato le azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Home page punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="0c2dc-116">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="0c2dc-116">How it works</span></span>

<span data-ttu-id="0c2dc-117">Ti vengono dati punti per le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c2dc-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="0c2dc-118">Configurazione delle funzionalità di sicurezza consigliate</span><span class="sxs-lookup"><span data-stu-id="0c2dc-118">Configuring recommended security features</span></span>
- <span data-ttu-id="0c2dc-119">Esecuzione di attività correlate alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-119">Doing security-related tasks</span></span>
- <span data-ttu-id="0c2dc-120">Affrontare l'azione di miglioramento con un'applicazione o un software di terze parti o una mitigazione alternativa</span><span class="sxs-lookup"><span data-stu-id="0c2dc-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="0c2dc-121">Alcune azioni di miglioramento forniscono punti solo quando sono completate.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="0c2dc-122">Alcuni forniscono punti parziali se sono completati per alcuni dispositivi o utenti.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="0c2dc-123">Se non è possibile o non si desidera eseguire una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="0c2dc-124">Se si dispone di una licenza per uno dei prodotti Microsoft supportati, verranno visualizzati suggerimenti per tali prodotti.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="0c2dc-125">Viene illustrato il set completo di possibili miglioramenti per un prodotto, indipendentemente dall'edizione, dall'abbonamento o dal piano di licenza.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="0c2dc-126">In questo modo, è possibile comprendere le procedure consigliate per la sicurezza e migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="0c2dc-127">La posizione di sicurezza assoluta, rappresentata da Secure Score, rimane la stessa indipendentemente dalle licenze di proprietà dell'organizzazione per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="0c2dc-128">Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="0c2dc-129">Il punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine delle visualizzazioni e delle azioni di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="0c2dc-130">Secure Score si sincronizza anche ogni giorno per ricevere i dati di sistema sui punti ottenuti per ogni azione.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="0c2dc-131">Scenari chiave</span><span class="sxs-lookup"><span data-stu-id="0c2dc-131">Key scenarios</span></span>

- [<span data-ttu-id="0c2dc-132">Controllare il punteggio corrente</span><span class="sxs-lookup"><span data-stu-id="0c2dc-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="0c2dc-133">Confrontare il punteggio con organizzazioni come la tua</span><span class="sxs-lookup"><span data-stu-id="0c2dc-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="0c2dc-134">Visualizzare le azioni di miglioramento e decidere un piano d'azione</span><span class="sxs-lookup"><span data-stu-id="0c2dc-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="0c2dc-135">Avviare flussi di lavoro per analizzare o implementare</span><span class="sxs-lookup"><span data-stu-id="0c2dc-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="0c2dc-136">Come vengono segnate le azioni di miglioramento</span><span class="sxs-lookup"><span data-stu-id="0c2dc-136">How improvement actions are scored</span></span>

<span data-ttu-id="0c2dc-137">Ogni azione di miglioramento vale 10 punti o meno e la maggior parte viene segnata in modo binario.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="0c2dc-138">Se implementi l'azione di miglioramento, ad esempio la creazione di un nuovo criterio o l'attivazione di un'impostazione specifica, ottieni il 100% dei punti.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="0c2dc-139">Per altre azioni di miglioramento, i punti vengono dati come percentuale della configurazione totale.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="0c2dc-140">Ad esempio, un'azione di miglioramento indica di ottenere 10 punti proteggendo tutti gli utenti con l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="0c2dc-141">Hai solo 50 utenti su 100 protetti, quindi ottieni un punteggio parziale di 5 punti (50 protetti / 100 totali \* 10 pts max = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="0c2dc-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="0c2dc-142">Prodotti inclusi in Secure Score</span><span class="sxs-lookup"><span data-stu-id="0c2dc-142">Products included in Secure Score</span></span>

<span data-ttu-id="0c2dc-143">Attualmente sono disponibili suggerimenti per i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c2dc-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="0c2dc-144">Microsoft 365 (incluso Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="0c2dc-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c2dc-145">Azure Active Directory</span></span>
- <span data-ttu-id="0c2dc-146">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0c2dc-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0c2dc-147">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="0c2dc-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="0c2dc-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0c2dc-148">Cloud App Security</span></span>
- <span data-ttu-id="0c2dc-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c2dc-149">Microsoft Teams</span></span>

<span data-ttu-id="0c2dc-150">Le raccomandazioni per altri prodotti di sicurezza saranno presto disponibili.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="0c2dc-151">I consigli non riguardano tutte le superfici di attacco associate a ogni prodotto, ma sono una buona linea di base.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="0c2dc-152">Puoi anche contrassegnare le azioni di miglioramento come coperte da una mitigazione alternativa o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="0c2dc-153">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-153">Security defaults</span></span>

<span data-ttu-id="0c2dc-154">Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite di sicurezza [in Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)che semplificano la protezione dell'organizzazione con impostazioni di sicurezza preconfigurato per gli attacchi comuni.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="0c2dc-155">Se si attivano le impostazioni predefinite di sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c2dc-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="0c2dc-156">Assicurarsi che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso protetto (9 punti)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="0c2dc-157">Richiedi MFA per i ruoli amministrativi (10 punti)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="0c2dc-158">Abilitare i criteri per bloccare l'autenticazione legacy (7 punti)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="0c2dc-159">Le impostazioni predefinite di sicurezza includono funzionalità di sicurezza che forniscono una sicurezza simile alle azioni di miglioramento "criteri di rischio di accesso" e "criteri di rischio utente".</span><span class="sxs-lookup"><span data-stu-id="0c2dc-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="0c2dc-160">Invece di configurare questi criteri in base alle impostazioni predefinite di sicurezza, è consigliabile aggiornarne gli stati su "Risolto tramite mitigazione alternativa".</span><span class="sxs-lookup"><span data-stu-id="0c2dc-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="0c2dc-161">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="0c2dc-161">Required permissions</span></span>

<span data-ttu-id="0c2dc-162">Per disporre dell'autorizzazione per accedere a Microsoft Secure Score, è necessario disporre di uno dei ruoli seguenti in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="0c2dc-163">Ruoli di lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="0c2dc-163">Read and write roles</span></span>

<span data-ttu-id="0c2dc-164">Con l'accesso in lettura e scrittura, puoi apportare modifiche e interagire direttamente con Secure Score.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="0c2dc-165">È inoltre possibile assegnare l'accesso di sola lettura ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="0c2dc-166">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="0c2dc-166">Global administrator</span></span>
* <span data-ttu-id="0c2dc-167">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-167">Security administrator</span></span>
* <span data-ttu-id="0c2dc-168">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="0c2dc-168">Exchange administrator</span></span>
* <span data-ttu-id="0c2dc-169">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0c2dc-169">SharePoint administrator</span></span>
* <span data-ttu-id="0c2dc-170">Amministratore account</span><span class="sxs-lookup"><span data-stu-id="0c2dc-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="0c2dc-171">Ruoli di sola lettura</span><span class="sxs-lookup"><span data-stu-id="0c2dc-171">Read-only roles</span></span>

<span data-ttu-id="0c2dc-172">Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare aree punteggio o modificare confronti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="0c2dc-173">Amministratore del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="0c2dc-173">Helpdesk administrator</span></span>
* <span data-ttu-id="0c2dc-174">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="0c2dc-174">User administrator</span></span>
* <span data-ttu-id="0c2dc-175">Amministratore del servizio</span><span class="sxs-lookup"><span data-stu-id="0c2dc-175">Service administrator</span></span>
* <span data-ttu-id="0c2dc-176">Amministratore che legge i dati di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-176">Security reader</span></span>
* <span data-ttu-id="0c2dc-177">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-177">Security operator</span></span>
* <span data-ttu-id="0c2dc-178">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="0c2dc-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="0c2dc-179">Consapevolezza dei rischi</span><span class="sxs-lookup"><span data-stu-id="0c2dc-179">Risk awareness</span></span>

<span data-ttu-id="0c2dc-180">Microsoft Secure Score è un riepilogo numerico del comportamento di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misurazioni correlate alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="0c2dc-181">Non è una misura assoluta della probabilità che il sistema o i dati siano violati.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="0c2dc-182">Rappresenta invece la misura in cui sono stati adottati i controlli di sicurezza nell'ambiente Microsoft che possono contribuire a compensare il rischio di violazione.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="0c2dc-183">Nessun servizio online è immune da violazioni della sicurezza e il punteggio sicuro non deve essere interpretato come una garanzia contro le violazioni della sicurezza in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="0c2dc-184">L'opinione degli utenti è importante</span><span class="sxs-lookup"><span data-stu-id="0c2dc-184">We want to hear from you</span></span>

<span data-ttu-id="0c2dc-185">In caso di problemi, contattaci pubblicando la community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="0c2dc-186">Stiamo monitorando la community e forniremo assistenza.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0c2dc-187">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="0c2dc-187">Related resources</span></span>

- [<span data-ttu-id="0c2dc-188">Valutazione del profilo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c2dc-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="0c2dc-189">Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="0c2dc-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="0c2dc-190">Novità in arrivo</span><span class="sxs-lookup"><span data-stu-id="0c2dc-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="0c2dc-191">Novità</span><span class="sxs-lookup"><span data-stu-id="0c2dc-191">What's new</span></span>](microsoft-secure-score-whats-new.md)