---
title: Applicare automaticamente un'etichetta di riservatezza al contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Quando si crea automaticamente un'etichetta di riservatezza, è possibile assegnare un'etichetta a un documento o un messaggio di posta elettronica oppure è possibile chiedere agli utenti di selezionare l'etichetta consigliata.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277213"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="130fe-103">Applicare automaticamente un'etichetta di riservatezza al contenuto</span><span class="sxs-lookup"><span data-stu-id="130fe-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="130fe-104">Quando si crea un'etichetta di riservatezza, è possibile assegnarla automaticamente a contenuti che includono informazioni sensibili oppure è possibile chiedere agli utenti di applicare l'etichetta consigliata.</span><span class="sxs-lookup"><span data-stu-id="130fe-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="130fe-105">La possibilità di applicare automaticamente etichette di riservatezza al contenuto è importante perché:</span><span class="sxs-lookup"><span data-stu-id="130fe-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="130fe-106">Non è necessario formare gli utenti su tutte le classificazioni.</span><span class="sxs-lookup"><span data-stu-id="130fe-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="130fe-107">Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="130fe-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="130fe-108">Gli utenti non hanno più bisogno di conoscere i criteri e possono concentrarsi sul loro lavoro.</span><span class="sxs-lookup"><span data-stu-id="130fe-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="130fe-109">L'assegnazione automatica di etichette nelle app Office per Windows è supportata dal client di etichettatura unificata di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="130fe-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="130fe-110">Per l'etichettatura predefinita nelle app Office, questa funzionalità è disponibile [in versione di anteprima per alcune app](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="130fe-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="130fe-111">Le impostazioni di assegnazione automatica di etichette per le app Office sono disponibili quando si [crea o modifica un'etichetta di riservatezza](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="130fe-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Opzioni di assegnazione automatica delle etichette di riservatezza](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="130fe-113">Come configurare l'assegnazione automatica di etichette per le app Office</span><span class="sxs-lookup"><span data-stu-id="130fe-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="130fe-114">Una delle funzionalità più efficaci delle etichette di riservatezza è la possibilità di applicarle automaticamente al contenuto che soddisfa determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="130fe-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="130fe-115">In questo caso, gli utenti dell'organizzazione non dovranno applicare le etichette di riservatezza, perché Office 365 lo farà al loro posto.</span><span class="sxs-lookup"><span data-stu-id="130fe-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="130fe-116">È possibile scegliere di applicare automaticamente le etichette di riservatezza ai contenuti che includono specifici tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="130fe-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="130fe-117">Scegliere da un elenco di tipi di informazioni sensibili o classificatori:</span><span class="sxs-lookup"><span data-stu-id="130fe-117">Choose from a list of sensitive info types or classifers:</span></span>

![Condizioni delle etichette per l'assegnazione automatica di etichette nelle app Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="130fe-119">Attualmente, l'opzione per **Classificatori** è in anteprima limitata ed è necessario inviare un modulo a Microsoft per abilitare questa funzionalità per il tenant.</span><span class="sxs-lookup"><span data-stu-id="130fe-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="130fe-120">Per ulteriori informazioni, vedere il post di blog [Annuncio dell'assegnazione automatica di etichette nelle app Office tramite i classificatori predefiniti - Anteprima limitata](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span><span class="sxs-lookup"><span data-stu-id="130fe-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="130fe-121">Quando questa etichetta di riservatezza viene applicata automaticamente, l'utente riceve una notifica nella propria app Office.</span><span class="sxs-lookup"><span data-stu-id="130fe-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="130fe-122">Potrà quindi scegliere **OK** per chiudere la notifica.</span><span class="sxs-lookup"><span data-stu-id="130fe-122">They can choose **OK** to dismiss the notification.</span></span>

![Notifica di applicazione automatica di un'etichetta a un documento](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="130fe-124">Configurazione dei tipi di informazioni sensibili per un'etichetta</span><span class="sxs-lookup"><span data-stu-id="130fe-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="130fe-125">Quando si seleziona l'opzione **Tipi di informazioni sensibili**, viene visualizzato lo stesso elenco di tipi di informazioni sensibili mostrato durante la creazione di un criterio di prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="130fe-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="130fe-126">Ad esempio, è possibile applicare automaticamente un'etichetta Estremamente riservato a qualsiasi contenuto che include informazioni personali (PII) dei clienti, ad esempio numeri di carte di credito o codici fiscali:</span><span class="sxs-lookup"><span data-stu-id="130fe-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Tipi di informazioni sensibili per l'assegnazione automatica di etichette nelle app Office](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="130fe-128">Dopo aver selezionato i tipi di informazioni sensibili, è possibile definire la condizione modificando il numero di istanze o l'accuratezza della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="130fe-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="130fe-129">Per altre informazioni su queste opzioni, vedere [Ottimizzazione delle regole affinché siano più facili o difficili da soddisfare](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="130fe-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="130fe-130">Inoltre, è possibile scegliere se una condizione deve rilevare tutti i tipi di informazioni riservate o solo uno.</span><span class="sxs-lookup"><span data-stu-id="130fe-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="130fe-131">Per rendere le condizioni più flessibili o complesse, è possibile aggiungere gruppi e usare operatori logici tra i gruppi.</span><span class="sxs-lookup"><span data-stu-id="130fe-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="130fe-132">Per altre informazioni, vedere [Raggruppamento e operatori logici](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="130fe-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Opzioni per il numero di istanze e l'accuratezza della corrispondenza](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="130fe-134">Configurazione di classificatori per un'etichetta</span><span class="sxs-lookup"><span data-stu-id="130fe-134">Configuring classifers for a label</span></span>

<span data-ttu-id="130fe-135">Selezionando l'opzione **Classificatori**, scegliere uno o più classificatori predefiniti:</span><span class="sxs-lookup"><span data-stu-id="130fe-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Opzioni per i classificatori e le etichette di riservatezza](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="130fe-137">Per ulteriori informazioni su questi classificatori, vedere [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="130fe-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="130fe-138">Durante il periodo di anteprima, le app seguenti supportano i classificatori per le etichette di riservatezza:</span><span class="sxs-lookup"><span data-stu-id="130fe-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="130fe-139">Le applicazioni desktop di Office 365 ProPlus per Windows, da [Office Insider](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="130fe-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="130fe-140">Word</span><span class="sxs-lookup"><span data-stu-id="130fe-140">Word</span></span>
    - <span data-ttu-id="130fe-141">Excel</span><span class="sxs-lookup"><span data-stu-id="130fe-141">Excel</span></span>
    - <span data-ttu-id="130fe-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="130fe-142">PowerPoint</span></span>

- <span data-ttu-id="130fe-143">Office per le app Web, se le [etichette di riservatezza sono abilitate per i file di Office in SharePoint e OneDrive (anteprima pubblica)](sensitivity-labels-sharepoint-onedrive-files.md):</span><span class="sxs-lookup"><span data-stu-id="130fe-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="130fe-144">Word</span><span class="sxs-lookup"><span data-stu-id="130fe-144">Word</span></span>
    - <span data-ttu-id="130fe-145">Excel</span><span class="sxs-lookup"><span data-stu-id="130fe-145">Excel</span></span>
    - <span data-ttu-id="130fe-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="130fe-146">PowerPoint</span></span>
    - <span data-ttu-id="130fe-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="130fe-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="130fe-148">Consigliare all'utente di applicare un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="130fe-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="130fe-149">Se si preferisce, è possibile consigliare agli utenti di applicare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="130fe-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="130fe-150">Con questa opzione, gli utenti possono accettare la classificazione e le eventuali protezioni associate o ignorare il suggerimento se l'etichetta non è adatta al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="130fe-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="130fe-151">Le etichette consigliate sono supportate per Word, PowerPoint ed Excel.</span><span class="sxs-lookup"><span data-stu-id="130fe-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![Opzione per consigliare un'etichetta di riservatezza agli utenti](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="130fe-p110">Ecco un esempio di un avviso quando si configura una condizione per applicare un'etichetta come azione consigliata, con un suggerimento per i criteri personalizzati. È possibile scegliere quale testo visualizzare nel suggerimento per i criteri.</span><span class="sxs-lookup"><span data-stu-id="130fe-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Richiesta di applicazione di un'etichetta consigliata](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="130fe-156">Come vengono applicate le etichette automatiche o consigliate</span><span class="sxs-lookup"><span data-stu-id="130fe-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="130fe-157">L'assegnazione automatica delle etichette si applica a Word, Excel e PowerPoint al salvataggio dei documenti e in Outlook all'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="130fe-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="130fe-158">Queste condizioni rilevano le informazioni riservate nel corpo del testo nei documenti e nei messaggi di posta elettronica e nelle intestazioni e piè di pagina, ma non nella riga dell'oggetto o negli allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="130fe-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="130fe-159">Non è possibile usare l'assegnazione automatica di etichette per le e-mail e i documenti in precedenza etichettati manualmente o associati automaticamente a un grado maggiore di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="130fe-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="130fe-160">È possibile applicare una singola etichetta di riservatezza a un documento o una e-mail (oltre a una singola etichetta di conservazione).</span><span class="sxs-lookup"><span data-stu-id="130fe-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="130fe-161">L'assegnazione di etichette consigliate si applica a Word, Excel e PowerPoint al salvataggio dei documenti.</span><span class="sxs-lookup"><span data-stu-id="130fe-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="130fe-162">Non è possibile usare l'assegnazione di etichette consigliate per i documenti etichettati in precedenza con un grado maggiore di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="130fe-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="130fe-163">Quando il contenuto è già stato etichettato con un grado maggiore di riservatezza, l'utente non visualizzerà l'avviso con il consiglio e il suggerimento per i criteri.</span><span class="sxs-lookup"><span data-stu-id="130fe-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="130fe-164">Modalità di valutazione di più condizioni quando si applicano a più etichette</span><span class="sxs-lookup"><span data-stu-id="130fe-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="130fe-p114">Le etichette sono ordinate per la valutazione in base alla posizione specificata nei criteri: la prima etichetta ha la posizione più bassa (meno riservata) mentre l'ultima etichetta ha la posizione più alta (più riservata). Per altre informazioni sulla priorità, vedere [Priorità dell’etichetta (l’ordine è importante)](sensitivity-labels.md#label-priority-order-matters).</span><span class="sxs-lookup"><span data-stu-id="130fe-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="130fe-167">Non configurare un'etichetta padre in modo che venga applicata automaticamente o consigliata</span><span class="sxs-lookup"><span data-stu-id="130fe-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="130fe-168">Tenere presente che non è possibile applicare al contenuto un'etichetta padre (un'etichetta con sottoetichette).</span><span class="sxs-lookup"><span data-stu-id="130fe-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="130fe-169">Assicurarsi di non configurare un'etichetta padre in modo che venga applicata automaticamente o consigliata perché le etichette padre non vengono applicate al contenuto in app di Office che usano con il client di assegnazione delle etichette unificato Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="130fe-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="130fe-170">Per ulteriori informazioni sulle etichette padre e sulle sottoetichette, vedere [Sottoetichette (raggruppamento etichette)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="130fe-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
