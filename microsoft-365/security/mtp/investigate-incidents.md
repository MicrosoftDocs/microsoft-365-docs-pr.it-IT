---
title: Analizzare gli eventi imprevisti in Microsoft 365 Defender
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
ms.localizationpriority: medium
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
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926895"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="a616a-104">Analizzare gli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a616a-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a616a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a616a-105">**Applies to:**</span></span>

- <span data-ttu-id="a616a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a616a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a616a-107">Microsoft 365 Defender aggrega tutti gli avvisi, le risorse, le indagini e le prove correlati provenienti da dispositivi, utenti e cassette postali per fornire un quadro completo dell'intera gamma di attacchi.</span><span class="sxs-lookup"><span data-stu-id="a616a-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="a616a-108">Analizzare gli avvisi che riguardano la rete, comprenderne il significato e raccogliere le prove associate agli incidenti consente di poter elaborare un piano di correzione efficace.</span><span class="sxs-lookup"><span data-stu-id="a616a-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="a616a-109">Analizzare un incidente</span><span class="sxs-lookup"><span data-stu-id="a616a-109">Investigate an incident</span></span>

1. <span data-ttu-id="a616a-110">Selezionare un incidente dalla relativa coda.</span><span class="sxs-lookup"><span data-stu-id="a616a-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="a616a-111">Si apre un pannello laterale che offre un'anteprima delle informazioni importanti, ad esempio stato, gravità, categorie ed entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="a616a-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Immagine del riquadro laterale dell'incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="a616a-113">Selezionare **Apri pagina dell'incidente**.</span><span class="sxs-lookup"><span data-stu-id="a616a-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="a616a-114">Verrà aperta la pagina dell'evento imprevisto in cui sono disponibili ulteriori informazioni su eventi imprevisti, commenti e azioni, schede (panoramica, avvisi, dispositivi, utenti, indagini, prove).</span><span class="sxs-lookup"><span data-stu-id="a616a-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="a616a-115">Esaminare gli avvisi, i dispositivi, gli utenti e altre entità coinvolte nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="a616a-116">Panoramica dell'incidente</span><span class="sxs-lookup"><span data-stu-id="a616a-116">Incident overview</span></span>

<span data-ttu-id="a616a-117">La pagina di panoramica offre un quadro generale sugli elementi principali relativi all'incidente a cui prestare attenzione.</span><span class="sxs-lookup"><span data-stu-id="a616a-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Immagine della pagina di panoramica degli incidenti](../../media/incidents-overview.png)

<span data-ttu-id="a616a-119">Le categorie di attacco offrono una visualizzazione visiva e numerica dell'avanzamento dell'attacco rispetto alla kill chain.</span><span class="sxs-lookup"><span data-stu-id="a616a-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="a616a-120">Come per altri prodotti di sicurezza Microsoft, Microsoft 365 Defender è allineato al framework [MITRE ATT&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="a616a-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="a616a-121">La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="a616a-122">Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a616a-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="a616a-123">La sequenza temporale degli avvisi permette di visualizzare un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui tali avvisi sono collegati a questo incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="a616a-124">Infine, la sezione delle prove fornisce un riepilogo di quanti artefatti diversi sono stati inclusi nell'incidente e il relativo stato di correzione, in modo da poter identificare immediatamente se sono necessarie azioni da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a616a-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="a616a-125">Questa panoramica può essere utile nella valutazione iniziale dell'incidente fornendo dati analitici relativi alle principali caratteristiche dell'incidente di cui l'utente dovrebbe essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="a616a-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="a616a-126">Avvisi</span><span class="sxs-lookup"><span data-stu-id="a616a-126">Alerts</span></span>

<span data-ttu-id="a616a-127">È possibile visualizzare tutti gli avvisi correlati all'evento imprevisto e altre informazioni su di essi, ad esempio la gravità, le entità coinvolte nell'avviso, l'origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender per Office 365) e il motivo per cui sono stati collegati tra loro.</span><span class="sxs-lookup"><span data-stu-id="a616a-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Immagine della pagina degli avvisi dell'incidente](../../media/incident-alerts.png)

<span data-ttu-id="a616a-129">Per impostazione predefinita, gli avvisi sono ordinati cronologicamente, per consentire di visualizzare prima come si è svolto l'attacco nel tempo.</span><span class="sxs-lookup"><span data-stu-id="a616a-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="a616a-130">Facendo clic su ogni avviso verrà visualizzata la pagina di avviso pertinente in cui è possibile eseguire un'analisi approfondita dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="a616a-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="a616a-131">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="a616a-131">Devices</span></span>

<span data-ttu-id="a616a-132">Nella scheda dei dispositivi sono elencati tutti i dispositivi in cui vengono visualizzati gli avvisi relativi all'incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="a616a-133">Facendo clic sul nome del computer in cui si è verificato l'attacco, si accede alla relativa pagina in cui è possibile visualizzare gli avvisi che sono stati attivati e gli eventi correlati forniti per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="a616a-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Immagine della scheda dei computer di un incidente](../../media/incident-machines.png)

<span data-ttu-id="a616a-135">Selezionando la scheda della sequenza temporale è possibile scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati sul computer in ordine cronologico, intervallati dagli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="a616a-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="a616a-136">Utenti</span><span class="sxs-lookup"><span data-stu-id="a616a-136">Users</span></span>

<span data-ttu-id="a616a-137">Visualizzare gli utenti che sono stati identificati come parte di un determinato incidente, oppure relativi a esso.</span><span class="sxs-lookup"><span data-stu-id="a616a-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="a616a-138">Facendo clic sul nome utente si accede alla pagina di Cloud App Security dell'utente dove è possibile condurre ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="a616a-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Immagine della scheda degli utenti di un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="a616a-140">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="a616a-140">Mailboxes</span></span>

<span data-ttu-id="a616a-141">Analizzare tutte le cassette postali che sono state identificate come parte di un relativo incidente, oppure relative a esso.</span><span class="sxs-lookup"><span data-stu-id="a616a-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="a616a-142">Per eseguire ulteriori attività di indagine, selezionando l'avviso correlato alla posta elettronica si aprirà Microsoft Defender per Office 365 in cui è possibile eseguire azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="a616a-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Immagine della scheda delle cassette postali di un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="a616a-144">Indagini</span><span class="sxs-lookup"><span data-stu-id="a616a-144">Investigations</span></span>

<span data-ttu-id="a616a-145">Selezionare **Indagini per** visualizzare tutte le indagini automatizzate attivate dagli avvisi in questo incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="a616a-146">Le indagini eseguiranno azioni correttive o attenderanno l'approvazione da parte dell'analista delle azioni, a seconda di come sono configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per Endpoint e Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="a616a-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Immagine della scheda delle indagini di un incidente](../../media/incident-investigations.png)

<span data-ttu-id="a616a-148">Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione.</span><span class="sxs-lookup"><span data-stu-id="a616a-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="a616a-149">Se sono presenti azioni in sospeso per l'approvazione nell'ambito dell'indagine, verranno visualizzate nella scheda Azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="a616a-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="a616a-150">Prove</span><span class="sxs-lookup"><span data-stu-id="a616a-150">Evidence</span></span>

<span data-ttu-id="a616a-151">Microsoft 365 Defender analizza automaticamente tutti gli eventi supportati e le entità sospette degli eventi imprevisti negli avvisi, fornendo una risposta automatica e informazioni su file, processi, servizi, messaggi di posta elettronica e altro ancora importanti.</span><span class="sxs-lookup"><span data-stu-id="a616a-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="a616a-152">Ciò consente di rilevare e bloccare rapidamente le potenziali minacce nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="a616a-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Immagine della scheda delle prove di un incidente](../../media/incident-evidence.png)

<span data-ttu-id="a616a-154">Ognuna delle entità analizzate sarà contrassegnata con un verdetto (Dannosa, Sospetta, Pulita) e uno stato di correzione.</span><span class="sxs-lookup"><span data-stu-id="a616a-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="a616a-155">Ciò consente di comprendere lo stato di correzione dell'intero incidente e quali sono i prossimi passi che possono essere presi per porre ulteriore rimedio.</span><span class="sxs-lookup"><span data-stu-id="a616a-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a616a-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a616a-156">Related topics</span></span>

- [<span data-ttu-id="a616a-157">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="a616a-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a616a-158">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="a616a-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a616a-159">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="a616a-159">Manage incidents</span></span>](manage-incidents.md)

