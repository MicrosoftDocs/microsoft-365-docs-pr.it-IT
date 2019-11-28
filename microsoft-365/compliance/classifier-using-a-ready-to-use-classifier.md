---
title: Utilizzo di un classificatore pronto all'uso (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 viene fornito con i classificatori pronti all'uso per l'apprendimento automatico che è possibile utilizzare per identificare ed etichettare il contenuto all'interno dell'organizzazione. In questo argomento vengono illustrate le modalità di preparazione per l'utilizzo dei classificatori pronti all'uso.
ms.openlocfilehash: 7e10bb94f84dd10a1ac22126106531d8ad309c47
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633855"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="75489-104">Utilizzo di un classificatore pronto all'uso (anteprima)</span><span class="sxs-lookup"><span data-stu-id="75489-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="75489-105">Microsoft ha formato e testato un certo numero di classificatori che utilizzano set di dati di esempio molto grandi, che possono essere utili per identificare determinate categorie di contenuto.</span><span class="sxs-lookup"><span data-stu-id="75489-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="75489-106">Vedere [Guida introduttiva ai classificatori addestrabili (Preview)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="75489-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="75489-107">Questi classificatori vengono visualizzati nel `Ready to use` gruppo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="75489-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="75489-108">**Lingua offensiva**: consente di rilevare gli elementi di testo che contengono parolacce, legature, scherni e espressioni mascherate (ovvero espressioni che hanno lo stesso significato di un termine più offensivo).</span><span class="sxs-lookup"><span data-stu-id="75489-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="75489-109">**Resumes**: rileva gli elementi che sono account testuali di qualifiche personali, didattiche, professionali del richiedente, esperienze lavorative e altre informazioni di identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="75489-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="75489-110">**Codice sorgente**: consente di rilevare gli elementi che contengono una serie di istruzioni e istruzioni scritte nei linguaggi di programmazione ampiamente utilizzati.</span><span class="sxs-lookup"><span data-stu-id="75489-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="75489-111">**Molestie**: rileva una categoria specifica di elementi di testo di lingua offensiva relativi alla condotta offensiva che mira a una o più persone in base alle caratteristiche seguenti: razza, etnia, religione, origine nazionale, genere, orientamento sessuale, età, disabilità.</span><span class="sxs-lookup"><span data-stu-id="75489-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="75489-112">**Parolacce**: rileva una categoria specifica di elementi di testo di lingua offensiva che contengono espressioni che imbarazzano la maggior parte delle persone.</span><span class="sxs-lookup"><span data-stu-id="75489-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="75489-113">**Threat**: rileva una categoria specifica di elementi di testo offensivi relativi alle minacce per commettere violenze o arrecare danni fisici a una persona o a una proprietà,</span><span class="sxs-lookup"><span data-stu-id="75489-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="75489-114">Prima di utilizzare i classificatori pronti per l'utilizzo nel flusso di lavoro di classificazione e etichettatura, è consigliabile testarlo su un campione del contenuto dell'organizzazione che si adatta alla categoria per verificare che le stime di classificazione soddisfino le proprie aspettative.</span><span class="sxs-lookup"><span data-stu-id="75489-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75489-115">Si noti che la lingua offensiva, la molestia, la profanità e i classificatori di minacce funzionano solo con il testo ricercabile e non sono esaustivi o completi.</span><span class="sxs-lookup"><span data-stu-id="75489-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text and are not exhaustive or complete.</span></span> <span data-ttu-id="75489-116">Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare questi classificatori a propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="75489-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers at its discretion.</span></span> <span data-ttu-id="75489-117">Anche se i classificatori possono assistere la propria organizzazione nel monitoraggio di un'offensiva e di altre lingue utilizzate, i classificatori non affrontano le conseguenze di tale lingua e non sono destinati a fornire il solo mezzo di monitoraggio o di risposta dell'organizzazione all'utilizzo di tale lingua.</span><span class="sxs-lookup"><span data-stu-id="75489-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="75489-118">La propria organizzazione e non Microsoft o le sue affiliate resta responsabile di tutte le decisioni relative al monitoraggio, all'applicazione, al blocco, alla rimozione e alla conservazione di qualsiasi contenuto identificato da un classificatore preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="75489-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal, and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="75489-119">Come prepararsi e usare un classificatore pronto per l'uso</span><span class="sxs-lookup"><span data-stu-id="75489-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="75489-120">Raccogliere gli elementi di contenuto di prova monouso che si ritiene appartenenti alla categoria del classificatore pronto per l'uso (corrispondenze positive) e quelli che non devono essere inclusi (corrispondenze negative) nella categoria che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="75489-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75489-121">Gli elementi di esempio non devono essere crittografati e devono essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="75489-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="75489-122">Creare una cartella di SharePoint Online dedicata. attendere almeno un'ora che la cartella venga aggiunta all'indice di ricerca.</span><span class="sxs-lookup"><span data-stu-id="75489-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="75489-123">Prendere nota dell'URL della cartella.</span><span class="sxs-lookup"><span data-stu-id="75489-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="75489-124">Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e aprire **Microsoft 365 Compliance Center** o **Microsoft 365 Security Center** > **Records Management (Preview)** > **Label Policies** scheda.</span><span class="sxs-lookup"><span data-stu-id="75489-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="75489-125">Scegliere `Auto-apply a label`.</span><span class="sxs-lookup"><span data-stu-id="75489-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="75489-126">Scegliere `Choose a label to auto-apply`.</span><span class="sxs-lookup"><span data-stu-id="75489-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="75489-127">Scegliere `Create new labels` e creare un'etichetta per l'utilizzo solo con questo test.</span><span class="sxs-lookup"><span data-stu-id="75489-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="75489-128">Quando si esegue questa operazione, `Retention` lasciare impostato su disattivato.</span><span class="sxs-lookup"><span data-stu-id="75489-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="75489-129">Non si desidera abilitare alcuna conservazione o altre azioni.</span><span class="sxs-lookup"><span data-stu-id="75489-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="75489-130">In questo caso, l'etichetta di conservazione verrà utilizzata semplicemente come etichetta di testo, senza applicare alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="75489-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="75489-131">Ad esempio, è possibile creare un'etichetta di conservazione denominata "test di classificazione del codice sorgente" senza azioni e quindi applicarla automaticamente a contenuto con classificazione del codice sorgente come condizione.</span><span class="sxs-lookup"><span data-stu-id="75489-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="75489-132">Per ulteriori informazioni sulla creazione di etichette di conservazione, vedere [Overview of retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="75489-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="75489-133">Scegliere `Auto-apply a label` e quindi `Choose a label to auto-apply`.</span><span class="sxs-lookup"><span data-stu-id="75489-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="75489-134">Per ulteriori informazioni sull'utilizzo di una condizione di applicazione automatica di un'etichetta, vedere [applicazione automatica dei criteri delle etichette di conservazione in base a una condizione](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="75489-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="75489-135">Scegliere l'etichetta di test dall'elenco e scegliere `Next`.</span><span class="sxs-lookup"><span data-stu-id="75489-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="75489-136">Scegliere `Apply label to content that matches a trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="75489-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![selezione di classificatore come condizione](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="75489-138">.</span><span class="sxs-lookup"><span data-stu-id="75489-138"></span></span>

10. <span data-ttu-id="75489-139">Scegliere il classificatore dall'elenco, in questo caso`Source Code`</span><span class="sxs-lookup"><span data-stu-id="75489-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="75489-140">Denominare il criterio, ad esempio "codice sorgente pronto per l'uso del test di classificazione".</span><span class="sxs-lookup"><span data-stu-id="75489-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="75489-141">Scegliere `Let me choose specific locations`.</span><span class="sxs-lookup"><span data-stu-id="75489-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="75489-142">Disattiva tutti i percorsi tranne `SharePoint sites` e scegli `Choose sites`.</span><span class="sxs-lookup"><span data-stu-id="75489-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="75489-143">Immettere l'URL del sito dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="75489-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="75489-144">Terminare la procedura guidata e scegliere`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="75489-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="75489-145">Inserire gli elementi di test nella cartella dedicata di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75489-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="75489-146">Consenti l'applicazione dell'etichetta per un'ora.</span><span class="sxs-lookup"><span data-stu-id="75489-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="75489-147">Controllare le proprietà dei documenti per l'etichetta per verificare se il classificatore ha incluso ed escluso il contenuto del test come previsto.</span><span class="sxs-lookup"><span data-stu-id="75489-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="75489-148">Esaminare gli elementi etichettati.</span><span class="sxs-lookup"><span data-stu-id="75489-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="75489-149">Eliminare il contenuto e i criteri di etichetta se il testing è stato completato.</span><span class="sxs-lookup"><span data-stu-id="75489-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="75489-150">Vedere anche:</span><span class="sxs-lookup"><span data-stu-id="75489-150">See also:</span></span>

- [<span data-ttu-id="75489-151">Introduzione ai classificatori sottoponibili a training (anteprima)</span><span class="sxs-lookup"><span data-stu-id="75489-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="75489-152">Panoramica delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="75489-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="75489-153">Applicazione automatica del criterio delle etichette di conservazione in base a una condizione</span><span class="sxs-lookup"><span data-stu-id="75489-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
