---
title: Impostare le opzioni di analisi in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Esaminare i passaggi per configurare le opzioni per il processo di analisi in Office 365 Advanced eDiscovery, inclusi i quasi duplicati, i thread di posta elettronica e i temi.  '
ms.openlocfilehash: e9acb30d991bd2ee0acba5a9ddde619272788ceb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597463"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="01a55-103">Impostare le opzioni di analisi in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="01a55-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="01a55-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="01a55-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="01a55-106">In Advanced eDiscovery, impostare le opzioni Analyze prima di eseguire ANALYZE.</span><span class="sxs-lookup"><span data-stu-id="01a55-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="01a55-107">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="01a55-107">Set Analyze options</span></span>

<span data-ttu-id="01a55-108">Aprire **prepara \> analisi** \> di **installazione**.</span><span class="sxs-lookup"><span data-stu-id="01a55-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="01a55-109">Viene visualizzata la finestra seguente.</span><span class="sxs-lookup"><span data-stu-id="01a55-109">The following window is displayed.</span></span>
  
![Impostare opzioni di analisi](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="01a55-111">**Quasi duplicati e thread di posta elettronica** Selezionare questa casella di controllo se si desidera eseguire l'analisi.</span><span class="sxs-lookup"><span data-stu-id="01a55-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="01a55-112">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="01a55-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="01a55-113">**Somiglianza del documento** Immettere il valore soglia quasi duplicati oppure accettare l'impostazione predefinita 65%.</span><span class="sxs-lookup"><span data-stu-id="01a55-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="01a55-114">**Temi** Selezionare questa casella per elaborare tutti i file e assegnargli i temi.</span><span class="sxs-lookup"><span data-stu-id="01a55-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="01a55-115">Per impostazione predefinita, questa casella di controllo non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="01a55-115">By default, this check box is not selected.</span></span> <span data-ttu-id="01a55-116">Se si desidera eseguire l'elaborazione dei temi, immettere le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="01a55-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="01a55-117">**Numero massimo di temi** Immettere o selezionare un valore per il numero di temi da creare.</span><span class="sxs-lookup"><span data-stu-id="01a55-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="01a55-118">Il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="01a55-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01a55-119">L'aumento del numero di temi influenza le prestazioni e la possibilità di generalizzare un tema.</span><span class="sxs-lookup"><span data-stu-id="01a55-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="01a55-120">Maggiore è il numero di temi, maggiore è il livello di granularità.</span><span class="sxs-lookup"><span data-stu-id="01a55-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="01a55-121">Ad esempio, se un insieme di temi 50 include un tema come "basket, Spurs, Clippers, Lakers"; 300 temi possono includere temi distinti: "Spurs", "Clippers", "Lakers".</span><span class="sxs-lookup"><span data-stu-id="01a55-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="01a55-122">Se non si ha consapevolezza del tema "basket" e si utilizza questa funzionalità per ECA, è possibile utilizzare il tema "basket".</span><span class="sxs-lookup"><span data-stu-id="01a55-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="01a55-123">Tuttavia, se l'elaborazione ha avuto troppi temi, potrebbe non essere possibile visualizzare la parola "basket" e potrebbe non essere in grado di riconoscere che gli Spurs e i Clippers sono buoni temi di basket da rivedere, anziché elementi che vengono utilizzati per i capelli.</span><span class="sxs-lookup"><span data-stu-id="01a55-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="01a55-124">**Temi consigliati** È possibile suggerire parole tematiche per controllare l'elaborazione dei temi.</span><span class="sxs-lookup"><span data-stu-id="01a55-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="01a55-125">Advanced eDiscovery si concentrerà su queste parole suggerite e cercherà di creare uno o più temi rilevanti, in base alle impostazioni "numero massimo di temi".</span><span class="sxs-lookup"><span data-stu-id="01a55-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="01a55-126">Ad esempio, se la parola suggerita è "computer" e si specifica "2" come "numero massimo di temi", Advanced eDiscovery proverà a generare due temi correlati alla parola "computer".</span><span class="sxs-lookup"><span data-stu-id="01a55-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="01a55-127">I due temi potrebbero essere, ad esempio, "software per computer" e "hardware del computer".</span><span class="sxs-lookup"><span data-stu-id="01a55-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="01a55-129">Per visualizzare, aggiungere o modificare i temi suggeriti, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="01a55-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="01a55-130">Nel riquadro **temi consigliati** fare clic sull'icona **Aggiungi** ![icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere un tema.</span><span class="sxs-lookup"><span data-stu-id="01a55-130">In the **Suggested themes** panel, click the **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="01a55-131">Nel riquadro **Aggiungi tema suggerito** aggiungere le parole separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="01a55-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="01a55-132">In **numero di temi**selezionare un valore per determinare il numero di temi avanzati che eDiscovery tenterà di generare per queste parole (l'impostazione predefinita è 1 tema).</span><span class="sxs-lookup"><span data-stu-id="01a55-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="01a55-133">Fare clic su **Salva** e quindi chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="01a55-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01a55-134">Il numero totale di temi include i temi suggeriti.</span><span class="sxs-lookup"><span data-stu-id="01a55-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="01a55-135">I temi totali suggeriti non possono superare i temi totali.</span><span class="sxs-lookup"><span data-stu-id="01a55-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="01a55-136">Se sono presenti molti temi suggeriti rispetto ai temi totali, solo alcuni temi "novelli" verranno rilevati dal sistema perché la maggior parte dei temi sarà dedicata ai temi suggeriti.</span><span class="sxs-lookup"><span data-stu-id="01a55-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="01a55-137">**Modalità** Nell'elenco a discesa selezionare un'opzione **temi** :</span><span class="sxs-lookup"><span data-stu-id="01a55-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="01a55-138">**Create and Apply Model**: calcola i temi in base ai modelli da un segmento dei file e quindi distribuisce i file tra di essi.</span><span class="sxs-lookup"><span data-stu-id="01a55-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="01a55-139">**Create Model**: consente di calcolare un modello di temi da un segmento dei file.</span><span class="sxs-lookup"><span data-stu-id="01a55-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="01a55-140">Il processo di applicazione della divisione dei file viene effettuato separatamente in un altro momento.</span><span class="sxs-lookup"><span data-stu-id="01a55-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="01a55-141">**Applicazione modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non è stato ancora applicato.</span><span class="sxs-lookup"><span data-stu-id="01a55-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="01a55-142">In questo modo i file verranno divisi in base ai temi.</span><span class="sxs-lookup"><span data-stu-id="01a55-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="01a55-143">È inoltre possibile [impostare Ignora testo](set-ignore-text-in-advanced-ediscovery.md) e [set Analyze Advanced Settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span><span class="sxs-lookup"><span data-stu-id="01a55-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="01a55-144">Dopo aver impostato queste opzioni, fare clic su **analizza** per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="01a55-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="01a55-145">[Visualizzare i risultati dell'analisi](view-analyze-results-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="01a55-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="01a55-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01a55-146">See also</span></span>

[<span data-ttu-id="01a55-147">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="01a55-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="01a55-148">Informazioni sulla somiglianza del documento</span><span class="sxs-lookup"><span data-stu-id="01a55-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01a55-149">Imposta Ignora testo</span><span class="sxs-lookup"><span data-stu-id="01a55-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01a55-150">Impostazioni avanzate per l'analisi</span><span class="sxs-lookup"><span data-stu-id="01a55-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01a55-151">Visualizzare i risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="01a55-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

