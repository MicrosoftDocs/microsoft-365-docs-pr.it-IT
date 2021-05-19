---
title: Gestire gli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: incidente, incidenti, analizzare, risposta, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 725e6226a56b3aae3670cde18969afdda1ec1940
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530839"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e0b5f-104">Gestire gli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0b5f-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e0b5f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e0b5f-105">**Applies to:**</span></span>
- <span data-ttu-id="e0b5f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0b5f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e0b5f-107">La gestione degli incidenti è fondamentale per garantire che le minacce siano contenute e trattate.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="e0b5f-108">È possibile gestire gli eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="e0b5f-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="e0b5f-109">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

<span data-ttu-id="e0b5f-111">Ecco i modi in cui è possibile gestire gli eventi imprevisti:</span><span class="sxs-lookup"><span data-stu-id="e0b5f-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="e0b5f-112">Modificare il nome dell'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e0b5f-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="e0b5f-113">Aggiungere tag agli eventi</span><span class="sxs-lookup"><span data-stu-id="e0b5f-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="e0b5f-114">Assegnare l'evento imprevisto a un account utente</span><span class="sxs-lookup"><span data-stu-id="e0b5f-114">Assign the incident to a user account</span></span>](#assign-incidents)
- [<span data-ttu-id="e0b5f-115">Risolverli</span><span class="sxs-lookup"><span data-stu-id="e0b5f-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="e0b5f-116">Impostare la classificazione e la determinazione</span><span class="sxs-lookup"><span data-stu-id="e0b5f-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="e0b5f-117">Aggiungere commenti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="e0b5f-118">È possibile gestire gli eventi imprevisti dal **riquadro Gestisci eventi imprevisti** per un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="e0b5f-119">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Esempio del riquadro Gestisci evento imprevisto di un evento imprevisto":::

<span data-ttu-id="e0b5f-121">È possibile visualizzare questo riquadro dal **collegamento Gestisci operazioni** non consentite in:</span><span class="sxs-lookup"><span data-stu-id="e0b5f-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="e0b5f-122">Riquadro Proprietà di un evento imprevisto nella coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="e0b5f-123">**Pagina di** riepilogo di un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="e0b5f-124">Nei casi in cui si desidera spostare gli avvisi da un  evento imprevisto a un altro, è possibile farlo anche dalla scheda Avvisi, creando così un evento imprevisto più grande o più piccolo che include tutti gli avvisi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="e0b5f-125">Modificare il nome dell'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e0b5f-125">Edit the incident name</span></span>

<span data-ttu-id="e0b5f-126">Microsoft 365 Defender assegna automaticamente un nome in base agli attributi degli avvisi, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="e0b5f-127">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="e0b5f-128">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="e0b5f-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="e0b5f-129">È possibile modificare il nome dell'evento imprevisto dal **campo Nome** evento imprevisto nel **riquadro Gestisci** evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b5f-130">Gli eventi imprevisti esistenti prima dell'implementazione della funzionalità di denominazione automatica degli eventi imprevisti manterranno il nome.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="e0b5f-131">Aggiungere tag agli eventi</span><span class="sxs-lookup"><span data-stu-id="e0b5f-131">Add incident tags</span></span>

<span data-ttu-id="e0b5f-132">È possibile aggiungere tag personalizzati a un evento imprevisto, ad esempio per contrassegnare un gruppo di eventi imprevisti con una caratteristica comune.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="e0b5f-133">In un secondo momento è possibile filtrare la coda degli eventi imprevisti per tutti gli eventi imprevisti che contengono un tag specifico.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="e0b5f-134">Quando si inizia a digitare, è possibile selezionare da un elenco di tag selezionati.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="e0b5f-135">Assegnare gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-135">Assign incidents</span></span>

<span data-ttu-id="e0b5f-136">Se non è stato ancora assegnato un evento imprevisto, è possibile selezionare **Assegna a** e specificare l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="e0b5f-137">In questo modo viene assegnata la proprietà dell'evento imprevisto e tutti gli avvisi ad esso associati.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="e0b5f-138">Risolvere un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e0b5f-138">Resolve an incident</span></span>

<span data-ttu-id="e0b5f-139">Se l'evento imprevisto è stato risolto, selezionare **Risolvi evento imprevisto** per spostare l'interruttore verso destra.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="e0b5f-140">Si noti che la risoluzione di un evento imprevisto risolve anche tutti gli avvisi collegati e attivi correlati all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="e0b5f-141">Un evento imprevisto non risolto viene visualizzato come **Attivo.**</span><span class="sxs-lookup"><span data-stu-id="e0b5f-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="e0b5f-142">Impostare la classificazione e la determinazione</span><span class="sxs-lookup"><span data-stu-id="e0b5f-142">Set the classification and determination</span></span>

<span data-ttu-id="e0b5f-143">La classificazione degli eventi imprevisti è se si tratta di un avviso vero o falso, configurato dal **campo Classificazione.**</span><span class="sxs-lookup"><span data-stu-id="e0b5f-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="e0b5f-144">Se si tratta di un avviso vero, è necessario specificare anche il tipo di minaccia con il **campo Determinazione.**</span><span class="sxs-lookup"><span data-stu-id="e0b5f-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="e0b5f-145">Se si specifica il tipo di minaccia, il team di sicurezza può visualizzare i modelli di minaccia e agire per difenderne l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="e0b5f-146">Aggiungere commenti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-146">Add comments</span></span>

<span data-ttu-id="e0b5f-147">È possibile aggiungere più commenti a un evento imprevisto con il **campo** Commento.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="e0b5f-148">Ogni commento viene aggiunto agli eventi cronologici dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e0b5f-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="e0b5f-149">È possibile visualizzare i commenti e la cronologia di un evento imprevisto dal collegamento Commenti **e cronologia** nella **pagina Riepilogo.**</span><span class="sxs-lookup"><span data-stu-id="e0b5f-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0b5f-150">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e0b5f-150">Next steps</span></span>

<span data-ttu-id="e0b5f-151">Per i nuovi eventi imprevisti, avviare [l'indagine](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="e0b5f-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="e0b5f-152">Per gli incidenti in-process, continuare [l'indagine](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="e0b5f-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="e0b5f-153">Per gli eventi imprevisti risolti, eseguire una [revisione post-incidente.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="e0b5f-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0b5f-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0b5f-154">See also</span></span>

- [<span data-ttu-id="e0b5f-155">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e0b5f-156">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e0b5f-157">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e0b5f-157">Investigate incidents</span></span>](investigate-incidents.md)
