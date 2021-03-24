---
title: Analizzare gli incidenti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, computer, dispositivi, utenti, identificare, posta, posta elettronica, cassetta postale, indagine, grafico, prova
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 10fa2765a4fe5bd256e0588af0db51f5a22339a2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062013"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="0d2f6-104">Analizzare gli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d2f6-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0d2f6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0d2f6-105">**Applies to:**</span></span>

- <span data-ttu-id="0d2f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d2f6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0d2f6-107">Microsoft 365 Defender aggrega tutti gli avvisi, gli asset, le indagini e le prove correlati provenienti da dispositivi, utenti e cassette postali per fornire una panoramica completa dell'intera ampiezza di un attacco.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="0d2f6-108">Analizzare gli avvisi che riguardano la rete, comprenderne il significato e raccogliere le prove associate agli incidenti consente di poter elaborare un piano di correzione efficace.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="0d2f6-109">Analizzare un incidente</span><span class="sxs-lookup"><span data-stu-id="0d2f6-109">Investigate an incident</span></span>

1. <span data-ttu-id="0d2f6-110">Selezionare un incidente dalla relativa coda.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="0d2f6-111">Viene aperto un pannello laterale che offre un'anteprima di informazioni importanti, ad esempio stato, gravità, categorie ed entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Immagine del riquadro laterale dell'incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="0d2f6-113">Selezionare **Apri pagina dell'incidente**.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="0d2f6-114">Verrà aperta la pagina dell'evento imprevisto in cui sono disponibili ulteriori informazioni su dettagli, commenti e azioni, schede (panoramica, avvisi, dispositivi, utenti, indagini, prove).</span><span class="sxs-lookup"><span data-stu-id="0d2f6-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="0d2f6-115">Esaminare gli avvisi, i dispositivi, gli utenti e altre entità coinvolte nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="0d2f6-116">Panoramica dell'incidente</span><span class="sxs-lookup"><span data-stu-id="0d2f6-116">Incident overview</span></span>

<span data-ttu-id="0d2f6-117">La pagina di panoramica offre un quadro generale sugli elementi principali relativi all'incidente a cui prestare attenzione.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Immagine della pagina di panoramica degli incidenti](../../media/incidents-overview.png)

<span data-ttu-id="0d2f6-119">Le categorie di attacco offrono una visualizzazione visiva e numerica dell'avanzamento dell'attacco contro la catena di uccidi.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="0d2f6-120">Come per altri prodotti di sicurezza Microsoft, Microsoft 365 Defender è allineato al framework [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="0d2f6-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="0d2f6-121">La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="0d2f6-122">Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="0d2f6-123">La sequenza temporale degli avvisi permette di visualizzare un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui tali avvisi sono collegati a questo incidente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="0d2f6-124">Infine, la sezione delle prove fornisce un riepilogo di quanti artefatti diversi sono stati inclusi nell'incidente e il relativo stato di correzione, in modo da poter identificare immediatamente se sono necessarie azioni da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="0d2f6-125">Questa panoramica può essere utile nella valutazione iniziale dell'incidente fornendo dati analitici relativi alle principali caratteristiche dell'incidente di cui l'utente dovrebbe essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="0d2f6-126">Avvisi</span><span class="sxs-lookup"><span data-stu-id="0d2f6-126">Alerts</span></span>

<span data-ttu-id="0d2f6-127">È possibile visualizzare tutti gli avvisi correlati all'evento imprevisto e altre informazioni su di essi, ad esempio la gravità, le entità coinvolte nell'avviso, l'origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender per Office 365) e il motivo per cui sono stati collegati tra loro.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Immagine della pagina degli avvisi dell'incidente](../../media/incident-alerts.png)

<span data-ttu-id="0d2f6-129">Per impostazione predefinita, gli avvisi sono ordinati cronologicamente, per consentire di visualizzare prima come si è svolto l'attacco nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="0d2f6-130">Facendo clic su ogni avviso verrà visualizzata la pagina di avviso pertinente in cui è possibile eseguire un'analisi approfondita dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="0d2f6-131">Informazioni su come usare le pagine di avviso e la coda di avvisi unificati in [Analizzare gli avvisi](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0d2f6-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="0d2f6-132">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="0d2f6-132">Devices</span></span>

<span data-ttu-id="0d2f6-133">Nella scheda dei dispositivi sono elencati tutti i dispositivi in cui vengono visualizzati gli avvisi relativi all'incidente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="0d2f6-134">Facendo clic sul nome del computer in cui si è verificato l'attacco, si accede alla relativa pagina in cui è possibile visualizzare gli avvisi che sono stati attivati e gli eventi correlati forniti per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Immagine della scheda dei computer di un incidente](../../media/incident-machines.png)

<span data-ttu-id="0d2f6-136">Selezionando la scheda della sequenza temporale è possibile scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati sul computer in ordine cronologico, intervallati dagli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="0d2f6-137">Utenti</span><span class="sxs-lookup"><span data-stu-id="0d2f6-137">Users</span></span>

<span data-ttu-id="0d2f6-138">Visualizzare gli utenti che sono stati identificati come parte di un determinato incidente, oppure relativi a esso.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="0d2f6-139">Facendo clic sul nome utente si accede alla pagina di Cloud App Security dell'utente dove è possibile condurre ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Immagine della scheda degli utenti di un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="0d2f6-141">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="0d2f6-141">Mailboxes</span></span>

<span data-ttu-id="0d2f6-142">Analizzare tutte le cassette postali che sono state identificate come parte di un relativo incidente, oppure relative a esso.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="0d2f6-143">Per eseguire ulteriori attività di indagine, selezionando l'avviso correlato alla posta elettronica verrà aperto Microsoft Defender per Office 365 in cui è possibile eseguire azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Immagine della scheda delle cassette postali di un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="0d2f6-145">Indagini</span><span class="sxs-lookup"><span data-stu-id="0d2f6-145">Investigations</span></span>

<span data-ttu-id="0d2f6-146">Selezionare **Indagini per** visualizzare tutte le indagini automatizzate attivate dagli avvisi in questo evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="0d2f6-147">Le indagini eseguiranno azioni di correzione o attenderanno l'approvazione degli analisti delle azioni, a seconda di come sono configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per Endpoint e Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Immagine della scheda delle indagini di un incidente](../../media/incident-investigations.png)

<span data-ttu-id="0d2f6-149">Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="0d2f6-150">Se sono presenti azioni in sospeso per l'approvazione nell'ambito dell'indagine, verranno visualizzate nella scheda Azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="0d2f6-151">Prove</span><span class="sxs-lookup"><span data-stu-id="0d2f6-151">Evidence</span></span>

<span data-ttu-id="0d2f6-152">Microsoft 365 Defender analizza automaticamente tutti gli eventi supportati e le entità sospette degli incidenti negli avvisi, fornendoti la risposta automatica e le informazioni sui file, i processi, i servizi, i messaggi di posta elettronica e altro ancora importanti.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="0d2f6-153">Ciò consente di rilevare e bloccare rapidamente le potenziali minacce nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-153">This helps quickly detect and block potential threats in the incident.</span></span>

![Immagine della scheda delle prove di un incidente](../../media/incident-evidence.png)

<span data-ttu-id="0d2f6-155">Ognuna delle entità analizzate sarà contrassegnata con un verdetto (Dannosa, Sospetta, Pulita) e uno stato di correzione.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="0d2f6-156">Ciò consente di comprendere lo stato di correzione dell'intero incidente e quali sono i prossimi passi che possono essere presi per porre ulteriore rimedio.</span><span class="sxs-lookup"><span data-stu-id="0d2f6-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d2f6-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0d2f6-157">Related topics</span></span>

- [<span data-ttu-id="0d2f6-158">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="0d2f6-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0d2f6-159">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="0d2f6-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="0d2f6-160">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="0d2f6-160">Manage incidents</span></span>](manage-incidents.md)

