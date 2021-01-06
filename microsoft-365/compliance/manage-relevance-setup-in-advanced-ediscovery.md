---
title: Gestire la configurazione della pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Alcuni consigli per configurare il training della rilevanza in Advanced eDiscovery per classificare i file in base alla rilevanza e generare risultati analitici.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760210"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="a14f2-103">Gestire la configurazione della pertinenza in Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="a14f2-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="a14f2-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a14f2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="a14f2-p102">La tecnologia della rilevanza di Advanced eDiscovery si avvale del software e della guida di specialisti per classificare i file in base alla rilevanza. Questa tecnologia può essere utilizzata per le valutazioni preliminari dei casi, l'eliminazione selettiva e la revisione di campioni di file.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="a14f2-p103">Advanced eDiscovery include i componenti per il training della rilevanza e l'aggiunta di tag ai file che sono rilevanti per un determinato caso. Advanced eDiscovery prima apprende in base ai campioni di file rilevanti e non rilevanti forniti nel training e poi assegna ai file analizzati i punteggi di rilevanza e genera i risultati analitici che possono essere usati durante e dopo il processo di revisione dei file.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="a14f2-110">Linee guida per configurare il training della rilevanza</span><span class="sxs-lookup"><span data-stu-id="a14f2-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="a14f2-p104">In Advance eDiscovery, nella finestra **Casi**, selezionare un caso e fare clic su **Passa al caso**. Fare clic su **Rilevanza** \> **Configurazione della rilevanza**. Seguire le linee guida consigliate per configurare la rilevanza.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevance setup**. Follow these recommended guidelines to set up Relevance.</span></span> 
  
- <span data-ttu-id="a14f2-114">**Aggiunta di tag**: l'efficacia del training della rilevanza dipende dall'abilità dello specialista di contrassegnare i campioni di file con precisione e coerenza.</span><span class="sxs-lookup"><span data-stu-id="a14f2-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>

- <span data-ttu-id="a14f2-115">**Casi**:</span><span class="sxs-lookup"><span data-stu-id="a14f2-115">**Case issues**:</span></span>
  
  - <span data-ttu-id="a14f2-p105">Per ogni caso, è opportuno avvalersi dello stesso specialista per l'intero processo di training della rilevanza. Non è consentito a specialisti diversi di aggiungere contemporaneamente i tag per lo stesso caso.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
  
  - <span data-ttu-id="a14f2-118">Determinare se ogni gruppo di file è pertinente solo per un caso specifico.</span><span class="sxs-lookup"><span data-stu-id="a14f2-118">Determine if each group of files is pertinent only to a specific issue.</span></span>

  - <span data-ttu-id="a14f2-p106">Se un caso è definito in modo troppo generico, Advanced eDiscovery potrebbe generare troppi file non rilevanti. Se invece un caso è definito in modo troppo specifico, il processo di training della rilevanza potrebbe richiedere più tempo.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 

  - <span data-ttu-id="a14f2-121">Durante ciascun ciclo di training della rilevanza, Advanced eDiscovery si occupa di un solo caso attivo e i risultati dei campioni intermedi vengono visualizzati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a14f2-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>

  - <span data-ttu-id="a14f2-p107">In uno scenario con più casi, la modalità di campionamento consente di selezionare i casi da considerare nell'elaborazione. I casi "inattivi" non vengono elaborati fino a quando la loro modalità di campionamento non viene modificata. Un caso può essere "inattivo" o "attivo" per un solo specialista.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>

  - <span data-ttu-id="a14f2-p108">Advanced eDiscovery può essere usato per generare i file candidati a cui potrebbero applicarsi privilegi o esenzioni particolari. Innanzitutto è necessario configurare un caso separato in base al privilegio. Se possibile, è meglio eseguire prima il training ed eliminare in base alla rilevanza, poi eseguire il training in base al privilegio solo sul set di file eliminato (ricaricare il set eliminato come caso separato).</span><span class="sxs-lookup"><span data-stu-id="a14f2-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 

  - <span data-ttu-id="a14f2-p109">Il calcolo del batch può essere eseguito solo quando non sono presenti campioni aperti (quando si fa clic su Calcolo batch, verrà visualizzato un elenco di utenti con campioni aperti). Per "chiudere" i campioni di altri utenti (questo dovrebbe essere eseguito solo se questi utenti non contrassegnano questi esempi), un amministratore può utilizzare l'utilità "Modifica rilevanza" con l'opzione "Tutti i campioni di utenti".</span><span class="sxs-lookup"><span data-stu-id="a14f2-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>

- <span data-ttu-id="a14f2-p110">**Metadati**: Advanced eDiscovery analizza il contenuto. Non considera i metadati nell'ambito dei criteri di rilevanza.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span>

- <span data-ttu-id="a14f2-132">**Rilevanza**: se la rilevanza di un problema ha un valore inferiore al 3% dopo la valutazione, si consiglia di effettuare il seeding del training della rilevanza con file rilevanti e non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="a14f2-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>

- <span data-ttu-id="a14f2-p111">**Dimensione del file**: i file di grandi dimensioni (oltre 5.242.880 caratteri di testo estratto) vengono ignorati nella rilevanza. I file non partecipano al training della rilevanza e non vengono classificati per rilevanza dopo il calcolo del batch. I file oltre i 5 MB possono essere inclusi nel set di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a14f2-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5 MB can be included in the Assessment set.</span></span>

## <a name="setting-up-case-issues"></a><span data-ttu-id="a14f2-136">Configurazione dei casi</span><span class="sxs-lookup"><span data-stu-id="a14f2-136">Setting up case issues</span></span>

<span data-ttu-id="a14f2-137">I parametri descritti in questa sezione sono disponibili nella tecnologia di rilevanza di Advanced eDiscovery  \> **Configurazione della rilevanza**.</span><span class="sxs-lookup"><span data-stu-id="a14f2-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span>
  
- <span data-ttu-id="a14f2-138">I problemi devono essere assegnati a un utente che dovrà occuparsi del training dei file.</span><span class="sxs-lookup"><span data-stu-id="a14f2-138">Issues must be assigned to a user who will train the files.</span></span>

- <span data-ttu-id="a14f2-139">I file importati devono quindi essere aggiunti al carico di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a14f2-139">Imported files must then be added to the load being processed.</span></span>

- <span data-ttu-id="a14f2-140">Definire e organizzare con attenzione i problemi, poiché i risultati del training della rilevanza possono esserne influenzati.</span><span class="sxs-lookup"><span data-stu-id="a14f2-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>

<span data-ttu-id="a14f2-141">Dopo aver impostato i parametri, il revisore/lo specialista può avviare il training dei file nella scheda **Rilevanza**.</span><span class="sxs-lookup"><span data-stu-id="a14f2-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span>
