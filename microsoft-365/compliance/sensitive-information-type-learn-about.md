---
title: Ulteriori informazioni sui tipi di informazioni riservate
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: e125a6dfb35b7018b5f85100184c842da9231327
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407326"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="786c4-102">Ulteriori informazioni sui tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-102">Learn about sensitive information types</span></span>

<span data-ttu-id="786c4-103">L'identificazione e la classificazione di elementi sensibili sotto il controllo dell'organizzazione è il primo passaggio nella [disciplina di Information Protection.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="786c4-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="786c4-104">Microsoft 365 offre tre modi per identificare gli elementi in modo che possano essere classificati:</span><span class="sxs-lookup"><span data-stu-id="786c4-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="786c4-105">manualmente dagli utenti</span><span class="sxs-lookup"><span data-stu-id="786c4-105">manually by users</span></span>
- <span data-ttu-id="786c4-106">riconoscimento automatico dei pattern, come i tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="786c4-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="786c4-107">machine learning</span><span class="sxs-lookup"><span data-stu-id="786c4-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="786c4-108">I tipi di informazioni riservate sono classificatori basati su pattern.</span><span class="sxs-lookup"><span data-stu-id="786c4-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="786c4-109">Rilevano informazioni riservate come i numeri di previdenza sociale, carta di credito o conto corrente bancario per identificare gli elementi sensibili, vedere [Definizioni delle](sensitive-information-type-entity-definitions.md) entità dei tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="786c4-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="786c4-110">I tipi di informazioni riservate vengono utilizzati in</span><span class="sxs-lookup"><span data-stu-id="786c4-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="786c4-111">Criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="786c4-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="786c4-112">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="786c4-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="786c4-113">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="786c4-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="786c4-114">Conformità delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="786c4-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="786c4-115">Criteri di applicazione automatica di etichette</span><span class="sxs-lookup"><span data-stu-id="786c4-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="786c4-116">Parti fondamentali di un tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="786c4-117">Ogni entità del tipo di informazioni riservate è definita da questi campi:</span><span class="sxs-lookup"><span data-stu-id="786c4-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="786c4-118">name: come viene fatto riferimento al tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="786c4-119">description: descrive cosa cerca il tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="786c4-120">pattern: un modello definisce cosa rileva un tipo di informazione sensibile.</span><span class="sxs-lookup"><span data-stu-id="786c4-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="786c4-121">È costituito dai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="786c4-121">It consists of the following components</span></span>
    - <span data-ttu-id="786c4-122">Elemento principale: l'elemento principale cercato dal tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="786c4-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="786c4-123">Può essere **un'espressione regolare** con o senza una convalida del checksum, un elenco di parole **chiave,** un dizionario di **parole** chiave o una **funzione.**</span><span class="sxs-lookup"><span data-stu-id="786c4-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="786c4-124">Elemento di supporto: elementi che fungono da prova di supporto che aiutano ad aumentare la sicurezza della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="786c4-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="786c4-125">Ad esempio, parola chiave "SSN" in prossimità di un numero SSN.</span><span class="sxs-lookup"><span data-stu-id="786c4-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="786c4-126">Può essere un'espressione regolare con o senza una convalida del checksum, un elenco di parole chiave, un dizionario di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="786c4-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="786c4-127">Livello di sicurezza - I livelli di probabilità (alto, medio, basso) riflettono la quantità di prove di supporto rilevate insieme all'elemento primario.</span><span class="sxs-lookup"><span data-stu-id="786c4-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="786c4-128">Maggiore è il numero di prove di supporto contenute in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni sensibili che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="786c4-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="786c4-129">Prossimità: numero di caratteri tra l'elemento primario e l'elemento di supporto</span><span class="sxs-lookup"><span data-stu-id="786c4-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagramma della prova corroborativa e della finestra di prossimità](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="786c4-131">Altre informazioni sui livelli di sicurezza in questo video</span><span class="sxs-lookup"><span data-stu-id="786c4-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="786c4-132">Esempio di tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="786c4-133">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="786c4-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="786c4-134">Formato</span><span class="sxs-lookup"><span data-stu-id="786c4-134">Format</span></span>

<span data-ttu-id="786c4-135">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="786c4-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="786c4-136">Modello</span><span class="sxs-lookup"><span data-stu-id="786c4-136">Pattern</span></span>

<span data-ttu-id="786c4-137">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="786c4-137">Eight digits:</span></span>
- <span data-ttu-id="786c4-138">due cifre</span><span class="sxs-lookup"><span data-stu-id="786c4-138">two digits</span></span>
- <span data-ttu-id="786c4-139">un punto</span><span class="sxs-lookup"><span data-stu-id="786c4-139">a period</span></span>
- <span data-ttu-id="786c4-140">tre cifre</span><span class="sxs-lookup"><span data-stu-id="786c4-140">three digits</span></span>
- <span data-ttu-id="786c4-141">un punto</span><span class="sxs-lookup"><span data-stu-id="786c4-141">a period</span></span>
- <span data-ttu-id="786c4-142">tre cifre</span><span class="sxs-lookup"><span data-stu-id="786c4-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="786c4-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="786c4-143">Checksum</span></span>

<span data-ttu-id="786c4-144">No</span><span class="sxs-lookup"><span data-stu-id="786c4-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="786c4-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="786c4-145">Definition</span></span>

<span data-ttu-id="786c4-146">Un criterio DLP ha una probabilità media che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:</span><span class="sxs-lookup"><span data-stu-id="786c4-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="786c4-147">L'espressione regolare Regex_argentina_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="786c4-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="786c4-148">Viene trovata una parola Keyword_argentina_national_id da un utente.</span><span class="sxs-lookup"><span data-stu-id="786c4-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="786c4-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="786c4-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="786c4-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="786c4-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="786c4-151">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="786c4-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="786c4-152">Identità</span><span class="sxs-lookup"><span data-stu-id="786c4-152">Identity</span></span> 
- <span data-ttu-id="786c4-153">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="786c4-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="786c4-154">DNI</span><span class="sxs-lookup"><span data-stu-id="786c4-154">DNI</span></span> 
- <span data-ttu-id="786c4-155">Registro nazionale nic delle persone</span><span class="sxs-lookup"><span data-stu-id="786c4-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="786c4-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="786c4-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="786c4-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="786c4-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="786c4-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="786c4-158">Identidad</span></span> 
- <span data-ttu-id="786c4-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="786c4-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="786c4-160">Altre informazioni sui livelli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="786c4-160">More on confidence levels</span></span>

<span data-ttu-id="786c4-161">In una definizione di entità del tipo di informazioni riservate, il livello di **probabilità** riflette la quantità di prove di supporto rilevate oltre all'elemento principale.</span><span class="sxs-lookup"><span data-stu-id="786c4-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="786c4-162">Maggiore è il numero di prove di supporto contenute in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni sensibili che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="786c4-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="786c4-163">Ad esempio, le corrispondenze con un livello di probabilità elevato conterranno una prova di supporto maggiore in prossimità dell'elemento primario, mentre le corrispondenze con un livello di probabilità basso conterranno poche o nessuna prova di supporto in prossimità.</span><span class="sxs-lookup"><span data-stu-id="786c4-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="786c4-164">Un livello di probabilità elevato restituisce il numero più basso di falsi positivi, ma può comportare più falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="786c4-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="786c4-165">I livelli di probabilità bassa o media rendono più falsi positivi, ma da pochi a zero falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="786c4-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="786c4-166">**probabilità bassa**: valore di 65, gli elementi corrispondenti conterranno il numero minimo di falsi negativi, ma il maggior numero di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="786c4-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="786c4-167">La probabilità bassa restituisce tutte le corrispondenze di confidenza bassa, media e alta.</span><span class="sxs-lookup"><span data-stu-id="786c4-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="786c4-168">**probabilità media:** valore pari a 75, gli elementi corrispondenti conterranno una quantità media di falsi positivi e falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="786c4-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="786c4-169">La probabilità media restituisce tutte le corrispondenze di confidenza media e alta.</span><span class="sxs-lookup"><span data-stu-id="786c4-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="786c4-170">**probabilità elevata:** valore pari a 85, gli elementi corrispondenti conterranno il numero minimo di falsi positivi, ma il maggior numero di falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="786c4-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="786c4-171">La probabilità elevata restituisce solo corrispondenze con confidenza elevata.</span><span class="sxs-lookup"><span data-stu-id="786c4-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="786c4-172">È consigliabile usare modelli di livello di probabilità elevata con conteggi bassi, ad esempio da cinque a dieci, e modelli di probabilità bassa con conteggi più elevati, ad esempio 20 o più.</span><span class="sxs-lookup"><span data-stu-id="786c4-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="786c4-173">Creazione dei tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="786c4-173">Creating custom sensitive information types</span></span>

<span data-ttu-id="786c4-174">Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="786c4-174">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="786c4-175">**Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="786c4-175">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="786c4-176">Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="786c4-176">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="786c4-177">Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="786c4-177">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="786c4-178">**Usare EDM** È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM).</span><span class="sxs-lookup"><span data-stu-id="786c4-178">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="786c4-179">Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente.</span><span class="sxs-lookup"><span data-stu-id="786c4-179">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="786c4-180">Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="786c4-180">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="786c4-181">**Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="786c4-181">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="786c4-182">Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="786c4-182">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="786c4-183">Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="786c4-183">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="786c4-184">I livelli di sicurezza migliorati sono disponibili per l'uso immediato all'interno di Prevenzione della perdita dei dati per i servizi di Microsoft 365, Microsoft Information Protection per i servizi di Microsoft 365, Conformità delle comunicazioni, Governance delle informazioni e Gestione record.</span><span class="sxs-lookup"><span data-stu-id="786c4-184">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="786c4-185">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="786c4-185">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="786c4-186">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="786c4-186">Chinese (simplified)</span></span>
> - <span data-ttu-id="786c4-187">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="786c4-187">Chinese (traditional)</span></span>
> - <span data-ttu-id="786c4-188">Coreano</span><span class="sxs-lookup"><span data-stu-id="786c4-188">Korean</span></span>
> - <span data-ttu-id="786c4-189">Giapponese</span><span class="sxs-lookup"><span data-stu-id="786c4-189">Japanese</span></span>

><span data-ttu-id="786c4-190">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="786c4-190">This support is available for sensitive information types.</span></span> <span data-ttu-id="786c4-191">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="786c4-191">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="786c4-192">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="786c4-192">For further information</span></span>
- [<span data-ttu-id="786c4-193">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="786c4-193">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="786c4-194">Creare una tipologia personalizzata di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="786c4-194">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="786c4-195">Creare un tipo di informazioni sensibili personalizzato in PowerShell</span><span class="sxs-lookup"><span data-stu-id="786c4-195">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
