---
title: Esaminare gli incidenti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, computer, dispositivi, utenti, identificare, posta, posta elettronica, cassetta postale, indagine, grafico, prova
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846749"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="68136-104">Esaminare gli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68136-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="68136-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="68136-105">**Applies to:**</span></span>

- <span data-ttu-id="68136-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68136-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="68136-107">Microsoft 365 Defender aggrega tutti gli avvisi, le risorse, le indagini e le evidenze correlate da tutti i dispositivi, gli utenti e le cassette postali per fornire una panoramica completa dell'intera gamma di un attacco.</span><span class="sxs-lookup"><span data-stu-id="68136-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="68136-108">Analizzare gli avvisi che riguardano la rete, comprenderne il significato e raccogliere le prove associate agli incidenti consente di poter elaborare un piano di correzione efficace.</span><span class="sxs-lookup"><span data-stu-id="68136-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="68136-109">Analizzare un incidente</span><span class="sxs-lookup"><span data-stu-id="68136-109">Investigate an incident</span></span>

1. <span data-ttu-id="68136-110">Selezionare un incidente dalla relativa coda.</span><span class="sxs-lookup"><span data-stu-id="68136-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="68136-111">Viene visualizzata una finestra laterale che fornisce un'anteprima di informazioni importanti quali stato, gravità, categorie e entità interessate.</span><span class="sxs-lookup"><span data-stu-id="68136-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Immagine del riquadro laterale dell'incidente](../../media/incident-side-panel.png)

2. <span data-ttu-id="68136-113">Selezionare **Apri pagina dell'incidente**.</span><span class="sxs-lookup"><span data-stu-id="68136-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="68136-114">Verrà aperta la pagina degli incidenti in cui sono disponibili ulteriori informazioni sugli incidenti, i commenti e le azioni, le schede (panoramica, avvisi, dispositivi, utenti, indagini, prove).</span><span class="sxs-lookup"><span data-stu-id="68136-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="68136-115">Esaminare gli avvisi, i dispositivi, gli utenti e altre entità coinvolte nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="68136-116">Panoramica dell'incidente</span><span class="sxs-lookup"><span data-stu-id="68136-116">Incident overview</span></span>

<span data-ttu-id="68136-117">La pagina di panoramica offre un quadro generale sugli elementi principali relativi all'incidente a cui prestare attenzione.</span><span class="sxs-lookup"><span data-stu-id="68136-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Immagine della pagina di panoramica degli incidenti](../../media/incidents-overview.png)

<span data-ttu-id="68136-119">Le categorie di attacco forniscono una visualizzazione visiva e numerica di come è progredito l'attacco avanzato rispetto alla catena di Kill.</span><span class="sxs-lookup"><span data-stu-id="68136-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="68136-120">Come per altri prodotti Microsoft per la sicurezza, Microsoft 365 Defender è allineato al quadro di taglio [&CK &trade; ](https://attack.mitre.org/) .</span><span class="sxs-lookup"><span data-stu-id="68136-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="68136-121">La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="68136-122">Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="68136-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="68136-123">La sequenza temporale degli avvisi permette di visualizzare un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui tali avvisi sono collegati a questo incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="68136-124">Infine, la sezione delle prove fornisce un riepilogo di quanti artefatti diversi sono stati inclusi nell'incidente e il relativo stato di correzione, in modo da poter identificare immediatamente se sono necessarie azioni da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="68136-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="68136-125">Questa panoramica può essere utile nella valutazione iniziale dell'incidente fornendo dati analitici relativi alle principali caratteristiche dell'incidente di cui l'utente dovrebbe essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="68136-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="68136-126">Avvisi</span><span class="sxs-lookup"><span data-stu-id="68136-126">Alerts</span></span>

<span data-ttu-id="68136-127">È possibile visualizzare tutti gli avvisi relativi all'incidente e altre informazioni su di esse, ad esempio la gravità, le entità che sono state coinvolte nell'avviso, l'origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for endpoint, Microsoft Defender per Office 365) e il motivo per cui sono stati collegati tra loro.</span><span class="sxs-lookup"><span data-stu-id="68136-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Immagine della pagina degli avvisi dell'incidente](../../media/incident-alerts.png)

<span data-ttu-id="68136-129">Per impostazione predefinita, gli avvisi sono ordinati cronologicamente, per consentire di visualizzare prima come si è svolto l'attacco nel tempo.</span><span class="sxs-lookup"><span data-stu-id="68136-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="68136-130">Se si fa clic su ogni avviso, viene configurata la pagina di avviso pertinente, in cui è possibile eseguire un'analisi approfondita di tale avviso.</span><span class="sxs-lookup"><span data-stu-id="68136-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="68136-131">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="68136-131">Devices</span></span>

<span data-ttu-id="68136-132">Nella scheda dei dispositivi sono elencati tutti i dispositivi in cui vengono visualizzati gli avvisi relativi all'incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="68136-133">Facendo clic sul nome del computer in cui si è verificato l'attacco, si accede alla relativa pagina in cui è possibile visualizzare gli avvisi che sono stati attivati e gli eventi correlati forniti per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="68136-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Immagine della scheda dei computer di un incidente](../../media/incident-machines.png)

<span data-ttu-id="68136-135">Selezionando la scheda della sequenza temporale è possibile scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati sul computer in ordine cronologico, intervallati dagli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="68136-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="68136-136">Utenti</span><span class="sxs-lookup"><span data-stu-id="68136-136">Users</span></span>

<span data-ttu-id="68136-137">Visualizzare gli utenti che sono stati identificati come parte di un determinato incidente, oppure relativi a esso.</span><span class="sxs-lookup"><span data-stu-id="68136-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="68136-138">Facendo clic sul nome utente si accede alla pagina di Cloud App Security dell'utente dove è possibile condurre ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="68136-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Immagine della scheda degli utenti di un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="68136-140">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="68136-140">Mailboxes</span></span>

<span data-ttu-id="68136-141">Analizzare tutte le cassette postali che sono state identificate come parte di un relativo incidente, oppure relative a esso.</span><span class="sxs-lookup"><span data-stu-id="68136-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="68136-142">Per ulteriori operazioni di indagine, la selezione dell'avviso relativo alla posta elettronica aprirà Microsoft Defender per Office 365, dove è possibile eseguire operazioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="68136-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Immagine della scheda delle cassette postali di un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="68136-144">Indagini</span><span class="sxs-lookup"><span data-stu-id="68136-144">Investigations</span></span>

<span data-ttu-id="68136-145">Selezionare **indagini** per visualizzare tutte le indagini automatizzate attivate dagli avvisi in questo incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="68136-146">Le indagini eseguono azioni di correzione o attendono l'approvazione dell'analista delle azioni, a seconda di come sono state configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per endpoint e Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="68136-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Immagine della scheda delle indagini di un incidente](../../media/incident-investigations.png)

<span data-ttu-id="68136-148">Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione.</span><span class="sxs-lookup"><span data-stu-id="68136-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="68136-149">Se nell'ambito dell'inchiesta sono presenti azioni in sospeso per l'approvazione, queste verranno visualizzate nella scheda azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="68136-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="68136-150">Prove</span><span class="sxs-lookup"><span data-stu-id="68136-150">Evidence</span></span>

<span data-ttu-id="68136-151">Microsoft 365 Defender analizza automaticamente tutti gli eventi e le entità sospette degli incidenti supportati negli avvisi, fornendo risposta automatica e informazioni sui file importanti, i processi, i servizi, i messaggi di posta elettronica e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="68136-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="68136-152">Ciò consente di rilevare e bloccare rapidamente le potenziali minacce nell'incidente.</span><span class="sxs-lookup"><span data-stu-id="68136-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Immagine della scheda delle prove di un incidente](../../media/incident-evidence.png)

<span data-ttu-id="68136-154">Ognuna delle entità analizzate sarà contrassegnata con un verdetto (Dannosa, Sospetta, Pulita) e uno stato di correzione.</span><span class="sxs-lookup"><span data-stu-id="68136-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="68136-155">Ciò consente di comprendere lo stato di correzione dell'intero incidente e quali sono i prossimi passi che possono essere presi per porre ulteriore rimedio.</span><span class="sxs-lookup"><span data-stu-id="68136-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68136-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="68136-156">Related topics</span></span>

- [<span data-ttu-id="68136-157">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="68136-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="68136-158">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="68136-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="68136-159">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="68136-159">Manage incidents</span></span>](manage-incidents.md)

