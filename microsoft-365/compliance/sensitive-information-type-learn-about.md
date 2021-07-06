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
ms.openlocfilehash: 3f64b981b60db9f9089af0555e4bf734864913b9
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300382"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="6acc1-102">Ulteriori informazioni sui tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-102">Learn about sensitive information types</span></span>

<span data-ttu-id="6acc1-103">L'identificazione e la classificazione di elementi sensibili sotto il controllo dell'organizzazione è il primo passaggio della disciplina [di Information Protection.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="6acc1-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="6acc1-104">Microsoft 365 offre tre modi per identificare gli elementi in modo che possano essere classificati:</span><span class="sxs-lookup"><span data-stu-id="6acc1-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="6acc1-105">manualmente dagli utenti</span><span class="sxs-lookup"><span data-stu-id="6acc1-105">manually by users</span></span>
- <span data-ttu-id="6acc1-106">riconoscimento automatico dei pattern, come i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="6acc1-107">machine learning</span><span class="sxs-lookup"><span data-stu-id="6acc1-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="6acc1-108">I tipi di informazioni riservate sono classificatori basati su modelli.</span><span class="sxs-lookup"><span data-stu-id="6acc1-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="6acc1-109">Rilevano informazioni sensibili come i numeri di previdenza sociale, carta di credito o conto corrente bancario per identificare gli elementi sensibili, vedere [Definizioni di](sensitive-information-type-entity-definitions.md) entità tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="6acc1-110">I tipi di informazioni riservate vengono utilizzati in</span><span class="sxs-lookup"><span data-stu-id="6acc1-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="6acc1-111">Criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="6acc1-111">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md) 
- [<span data-ttu-id="6acc1-112">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6acc1-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="6acc1-113">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="6acc1-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="6acc1-114">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="6acc1-114">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="6acc1-115">Conformità delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="6acc1-115">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="6acc1-116">Criteri di etichettatura automatica</span><span class="sxs-lookup"><span data-stu-id="6acc1-116">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="6acc1-117">Parti fondamentali di un tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-117">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="6acc1-118">Ogni entità del tipo di informazioni riservate è definita da questi campi:</span><span class="sxs-lookup"><span data-stu-id="6acc1-118">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="6acc1-119">name: come viene fatto riferimento al tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-119">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="6acc1-120">description: descrive cosa cerca il tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-120">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="6acc1-121">pattern: un modello definisce ciò che rileva un tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="6acc1-121">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="6acc1-122">È costituito dai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6acc1-122">It consists of the following components</span></span>
    - <span data-ttu-id="6acc1-123">Elemento principale: l'elemento principale cercato dal tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="6acc1-123">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="6acc1-124">Può essere **un'espressione regolare** con o senza una convalida del checksum, un elenco di parole **chiave,** un **dizionario** parole chiave o una **funzione**.</span><span class="sxs-lookup"><span data-stu-id="6acc1-124">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="6acc1-125">Elemento di supporto: elementi che fungono da prova di supporto che consentono di aumentare la sicurezza della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6acc1-125">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="6acc1-126">Ad esempio, parola chiave "SSN" in prossimità di un numero SSN.</span><span class="sxs-lookup"><span data-stu-id="6acc1-126">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="6acc1-127">Può essere un'espressione regolare con o senza una convalida del checksum, un elenco di parole chiave, un dizionario di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6acc1-127">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="6acc1-128">Livello di confidenza - I livelli di confidenza (alto, medio, basso) riflettono la quantità di prove di supporto rilevata insieme all'elemento principale.</span><span class="sxs-lookup"><span data-stu-id="6acc1-128">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="6acc1-129">Maggiore è la prova di supporto contenuta in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni riservate che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="6acc1-129">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="6acc1-130">Prossimità: numero di caratteri tra l'elemento principale e l'elemento di supporto</span><span class="sxs-lookup"><span data-stu-id="6acc1-130">Proximity – Number of characters between primary and supporting element</span></span>

![Diagramma della prova corroborativa e della finestra di prossimità](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="6acc1-132">Scopri di più sui livelli di confidenza in questo video</span><span class="sxs-lookup"><span data-stu-id="6acc1-132">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="6acc1-133">Esempio di tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-133">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="6acc1-134">Numero DNI (Argentina National Identity)</span><span class="sxs-lookup"><span data-stu-id="6acc1-134">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="6acc1-135">Formato</span><span class="sxs-lookup"><span data-stu-id="6acc1-135">Format</span></span>

<span data-ttu-id="6acc1-136">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="6acc1-136">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6acc1-137">Modello</span><span class="sxs-lookup"><span data-stu-id="6acc1-137">Pattern</span></span>

<span data-ttu-id="6acc1-138">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="6acc1-138">Eight digits:</span></span>
- <span data-ttu-id="6acc1-139">due cifre</span><span class="sxs-lookup"><span data-stu-id="6acc1-139">two digits</span></span>
- <span data-ttu-id="6acc1-140">un punto</span><span class="sxs-lookup"><span data-stu-id="6acc1-140">a period</span></span>
- <span data-ttu-id="6acc1-141">tre cifre</span><span class="sxs-lookup"><span data-stu-id="6acc1-141">three digits</span></span>
- <span data-ttu-id="6acc1-142">un punto</span><span class="sxs-lookup"><span data-stu-id="6acc1-142">a period</span></span>
- <span data-ttu-id="6acc1-143">tre cifre</span><span class="sxs-lookup"><span data-stu-id="6acc1-143">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6acc1-144">Checksum</span><span class="sxs-lookup"><span data-stu-id="6acc1-144">Checksum</span></span>

<span data-ttu-id="6acc1-145">No</span><span class="sxs-lookup"><span data-stu-id="6acc1-145">No</span></span>

### <a name="definition"></a><span data-ttu-id="6acc1-146">Definizione</span><span class="sxs-lookup"><span data-stu-id="6acc1-146">Definition</span></span>

<span data-ttu-id="6acc1-147">Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:</span><span class="sxs-lookup"><span data-stu-id="6acc1-147">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6acc1-148">L'espressione regolare Regex_argentina_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6acc1-148">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6acc1-149">Viene trovata una parola Keyword_argentina_national_id dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6acc1-149">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6acc1-150">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6acc1-150">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="6acc1-151">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="6acc1-151">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="6acc1-152">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="6acc1-152">Argentina National Identity number</span></span> 
- <span data-ttu-id="6acc1-153">Identity</span><span class="sxs-lookup"><span data-stu-id="6acc1-153">Identity</span></span> 
- <span data-ttu-id="6acc1-154">Carta d'identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="6acc1-154">Identification National Identity Card</span></span> 
- <span data-ttu-id="6acc1-155">DNI</span><span class="sxs-lookup"><span data-stu-id="6acc1-155">DNI</span></span> 
- <span data-ttu-id="6acc1-156">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="6acc1-156">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="6acc1-157">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="6acc1-157">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="6acc1-158">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="6acc1-158">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="6acc1-159">Identidad</span><span class="sxs-lookup"><span data-stu-id="6acc1-159">Identidad</span></span> 
- <span data-ttu-id="6acc1-160">Identificación</span><span class="sxs-lookup"><span data-stu-id="6acc1-160">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="6acc1-161">Ulteriori informazioni sui livelli di probabilità</span><span class="sxs-lookup"><span data-stu-id="6acc1-161">More on confidence levels</span></span>

<span data-ttu-id="6acc1-162">In una definizione di entità del tipo di informazioni **riservate,** il livello di probabilità riflette la quantità di prove di supporto rilevate oltre all'elemento principale.</span><span class="sxs-lookup"><span data-stu-id="6acc1-162">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="6acc1-163">Maggiore è la prova di supporto contenuta in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni riservate che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="6acc1-163">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="6acc1-164">Ad esempio, le corrispondenze con un livello di confidenza elevato conterranno più prove di supporto in prossimità dell'elemento principale, mentre le corrispondenze con un livello di probabilità basso conterranno poco o nessun elemento di supporto in prossimità.</span><span class="sxs-lookup"><span data-stu-id="6acc1-164">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="6acc1-165">Un livello di confidenza elevato restituisce il numero minimo di falsi positivi, ma potrebbe causare più falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="6acc1-165">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="6acc1-166">I livelli di probabilità bassa o media rendono più falsi positivi, ma da pochi a zero falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="6acc1-166">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="6acc1-167">**probabilità bassa**: il valore di 65, gli elementi corrispondenti conterranno il numero minimo di falsi negativi, ma il maggior numero di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="6acc1-167">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="6acc1-168">La probabilità bassa restituisce tutte le corrispondenze di confidenza bassa, media e alta.</span><span class="sxs-lookup"><span data-stu-id="6acc1-168">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="6acc1-169">**probabilità media**: il valore di 75, gli elementi corrispondenti conterranno una quantità media di falsi positivi e falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="6acc1-169">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="6acc1-170">La probabilità media restituisce tutte le corrispondenze di probabilità media e alta.</span><span class="sxs-lookup"><span data-stu-id="6acc1-170">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="6acc1-171">**confidenza** elevata : il valore di 85, gli elementi corrispondenti conterranno il numero minimo di falsi positivi, ma il maggior numero di falsi negativi.</span><span class="sxs-lookup"><span data-stu-id="6acc1-171">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="6acc1-172">La probabilità elevata restituisce solo corrispondenze con confidenza elevata.</span><span class="sxs-lookup"><span data-stu-id="6acc1-172">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="6acc1-173">È consigliabile usare modelli di livello di probabilità elevata con conteggi bassi, ad esempio da cinque a dieci, e modelli di probabilità bassa con conteggi più elevati, ad esempio 20 o più.</span><span class="sxs-lookup"><span data-stu-id="6acc1-173">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="6acc1-174">Se si dispone di criteri esistenti o di tipi di informazioni riservate personalizzati (SIT) definiti utilizzando livelli di confidenza basati sui numeri (anche noto come accuratezza), questi verranno mappati automaticamente ai tre livelli di probabilità discreti; sicurezza bassa, confidenza media e confidenza elevata nell'interfaccia utente del Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="6acc1-174">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="6acc1-175">Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di probabilità compresi tra 76 e 100 verranno mappati a un livello di sicurezza elevato.</span><span class="sxs-lookup"><span data-stu-id="6acc1-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="6acc1-176">Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di probabilità compresi tra 66 e 75 verranno mappati alla probabilità media.</span><span class="sxs-lookup"><span data-stu-id="6acc1-176">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="6acc1-177">Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di confidenza inferiori o uguali a 65 verranno mappati alla probabilità bassa.</span><span class="sxs-lookup"><span data-stu-id="6acc1-177">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="6acc1-178">Creazione dei tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="6acc1-178">Creating custom sensitive information types</span></span>

<span data-ttu-id="6acc1-179">Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="6acc1-179">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="6acc1-180">**Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="6acc1-180">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="6acc1-181">Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6acc1-181">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="6acc1-182">Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="6acc1-182">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="6acc1-183">**Usare EDM** È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM).</span><span class="sxs-lookup"><span data-stu-id="6acc1-183">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="6acc1-184">Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente.</span><span class="sxs-lookup"><span data-stu-id="6acc1-184">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="6acc1-185">Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="6acc1-185">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="6acc1-186">**Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6acc1-186">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="6acc1-187">Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6acc1-187">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="6acc1-188">Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6acc1-188">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="6acc1-189">I livelli di sicurezza migliorati sono disponibili per l'utilizzo immediato all'interno di Prevenzione della perdita di dati per i servizi Microsoft 365, Microsoft Information Protection per i servizi Microsoft 365, Conformità delle comunicazioni, Governance delle informazioni e Gestione record.</span><span class="sxs-lookup"><span data-stu-id="6acc1-189">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="6acc1-190">Microsoft 365 Information Protection ora supporta le lingue dei set di caratteri a due byte per:</span><span class="sxs-lookup"><span data-stu-id="6acc1-190">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="6acc1-191">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="6acc1-191">Chinese (simplified)</span></span>
> - <span data-ttu-id="6acc1-192">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="6acc1-192">Chinese (traditional)</span></span>
> - <span data-ttu-id="6acc1-193">Coreano</span><span class="sxs-lookup"><span data-stu-id="6acc1-193">Korean</span></span>
> - <span data-ttu-id="6acc1-194">Giapponese</span><span class="sxs-lookup"><span data-stu-id="6acc1-194">Japanese</span></span>
> 
> <span data-ttu-id="6acc1-195">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="6acc1-195">This support is available for sensitive information types.</span></span> <span data-ttu-id="6acc1-196">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="6acc1-196">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="6acc1-197">Per rilevare modelli contenenti caratteri cinesi/giapponesi e caratteri a byte singolo o per rilevare modelli contenenti caratteri cinesi/giapponesi e inglesi, definire due varianti della parola chiave o dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="6acc1-197">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="6acc1-198">Ad esempio, per rilevare una parola chiave come "机密的document", usare due varianti della parola chiave: una con uno spazio tra il testo giapponese e quello inglese e un'altra senza spazio tra il testo giapponese e quello inglese.</span><span class="sxs-lookup"><span data-stu-id="6acc1-198">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="6acc1-199">Quindi, le parole chiave da aggiungere nel SIT devono essere "机密的 document" e "机密的document".</span><span class="sxs-lookup"><span data-stu-id="6acc1-199">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="6acc1-200">Analogamente, per rilevare la frase "東京オリンピック2020", devono essere usate due varianti: "東京オリンピック 2020" e "東京オリンピック2020".</span><span class="sxs-lookup"><span data-stu-id="6acc1-200">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="6acc1-201">Quando si crea un'espressione regolare usando un trattino a byte doppio o un punto a byte doppio, assicurarsi di eseguire l'escape di entrambi i caratteri come si farebbe con un trattino o un punto in un'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="6acc1-201">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="6acc1-202">Di seguito è riportata un'espressione regolare di esempio per riferimento:</span><span class="sxs-lookup"><span data-stu-id="6acc1-202">Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="6acc1-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="6acc1-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="6acc1-204">Ti consigliamo di usare la corrispondenza di stringhe anziché la corrispondenza di parole in un elenco di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6acc1-204">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="6acc1-205">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="6acc1-205">For further information</span></span>
- [<span data-ttu-id="6acc1-206">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="6acc1-206">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="6acc1-207">Creare una tipologia personalizzata di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="6acc1-207">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="6acc1-208">Creare un tipo di informazioni riservate personalizzato in PowerShell</span><span class="sxs-lookup"><span data-stu-id="6acc1-208">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="6acc1-209">Per informazioni su come usare i tipi di informazioni riservate per conformarsi alle normative sulla privacy dei dati, vedere Distribuire la protezione delle informazioni per le normative sulla privacy dei dati [con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="6acc1-209">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
