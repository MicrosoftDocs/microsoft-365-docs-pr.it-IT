---
title: Creare un criterio di eliminazione dei documenti
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.
ms.openlocfilehash: 00b10e1c86160917c96ed1062f0638acf56ef56e
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342979"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="26770-104">Creare un criterio di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="26770-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26770-105">Se si avanza, è consigliabile utilizzare un criterio di conservazione o le etichette di conservazione create nel centro conformità Microsoft 365, Microsoft 365 Security Center o Office 365 Security &amp; Compliance Center anziché un criterio di eliminazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="26770-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="26770-106">I criteri di eliminazione dei documenti continueranno a funzionare fianco a fianco con i criteri di conservazione, ma se è necessario mantenere o eliminare il contenuto in un punto qualsiasi di Office 365, è consigliabile utilizzare un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="26770-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="26770-107">Per ulteriori informazioni, vedere [use a Retention Policy anziché these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span><span class="sxs-lookup"><span data-stu-id="26770-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="26770-p103">Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.</span><span class="sxs-lookup"><span data-stu-id="26770-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="26770-110">Con un criterio di eliminazione dei documenti, è possibile ridurre in modo proattivo i rischi eliminando i documenti in un sito dopo un determinato periodo di tempo, ad esempio, è possibile eliminare i documenti nei siti di OneDrive for business degli utenti cinque anni dopo la creazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="26770-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="26770-p104">Dopo aver creato un criterio di eliminazione dei documenti, puoi assegnarlo a un modello di raccolta siti, in modo che il criterio sia disponibile per tutte le raccolte di siti create da tale modello. Puoi anche assegnare il criterio a una raccolta di siti specifica, sostituendo tutti i criteri che potrebbero essere stati assegnati al modello di tale raccolta di siti.</span><span class="sxs-lookup"><span data-stu-id="26770-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![Home page del Centro criteri per l'eliminazione dei documenti](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="26770-114">Modelli dei criteri</span><span class="sxs-lookup"><span data-stu-id="26770-114">Policy templates</span></span>

<span data-ttu-id="26770-p105">È possibile creare dei criteri per l'eliminazione dei documenti da zero o utilizzare uno dei criteri di esempio. Il centro criteri di conformità include dei criteri di esempio che è possibile utilizzare così come sono. In alternativa, è possibile usarli come punto di partenza per poi rinominarli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="26770-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![Criteri di eliminazione del documento di esempio](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="26770-118">Esempi di come utilizzare i criteri di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="26770-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="26770-119">Una raccolta di siti o un modello di raccolta di siti può contenere uno o più criteri assegnati e ognuno di questi criteri può avere una o più regole.</span><span class="sxs-lookup"><span data-stu-id="26770-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="26770-120">Tuttavia, può essere presente un solo criterio attivo per sito e può essere presente una sola regola di eliminazione attiva in qualsiasi momento per le raccolte all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="26770-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![Diagramma con relazione tra criteri](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="26770-122">Inoltre, puoi selezionare un criterio come obbligatorio o predefinito e puoi selezionare una regola di eliminazione come regola predefinita:</span><span class="sxs-lookup"><span data-stu-id="26770-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="26770-123">**Criteri obbligatori** Quando un criterio viene contrassegnato come obbligatorio, è possibile assegnare un solo criterio alla raccolta siti o al modello.</span><span class="sxs-lookup"><span data-stu-id="26770-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="26770-124">Il criterio deve essere contrassegnato come predefinito e verrà applicato a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="26770-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="26770-125">I proprietari dei siti non possono escludere il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="26770-126">**Criterio predefinito** Quando un criterio è impostato come predefinito, il criterio viene automaticamente attivo in tutti i siti a cui viene assegnata senza alcuna azione richiesta dal proprietario del sito.</span><span class="sxs-lookup"><span data-stu-id="26770-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="26770-127">**Regola predefinita** Quando una regola di eliminazione viene impostata come predefinita, viene applicata automaticamente a tutte le raccolte nei siti che utilizzano il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="26770-128">Nei seguenti esempi viene spiegato quando occorre usare un criterio obbligatorio o criteri e regole predefinite.</span><span class="sxs-lookup"><span data-stu-id="26770-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="26770-129">Esempio 1: applicare un solo criterio con una sola regola a un modello di raccolta di siti</span><span class="sxs-lookup"><span data-stu-id="26770-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="26770-p108">Potresti voler applicare un criterio di eliminazione dei documenti in un'ampia gamma di contenuto non strutturato, come i siti di OneDrive for Business o del team. Se vuoi essere sicuro che un solo criterio di eliminazione dei documenti sia attivo in tutti i siti creati da un modello di raccolta siti, puoi:</span><span class="sxs-lookup"><span data-stu-id="26770-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="26770-132">Creare un unico criterio con una sola regola di eliminazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="26770-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="26770-133">Impostare il criterio come obbligatorio e predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="26770-134">Assegnare il criterio a un modello di raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="26770-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="26770-p109">In questo esempio, la regola di eliminazione predefinita verrà applicata a tutti le librerie in tutte le raccolte di siti create dal modello, e i proprietari del sito non potranno rifiutare esplicitamente il criterio. Questo è il modo più semplice per applicare su vasta scala e rigidamente un criterio di eliminazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="26770-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![Diagramma con un solo criterio obbligatorio](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="26770-138">Esempio 2: applicare un solo criterio con diverse regole a un modello di raccolta siti</span><span class="sxs-lookup"><span data-stu-id="26770-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="26770-p110">I proprietari del sito spesso conoscono bene il tipo di contenuto presente nel sito, quindi potresti scegliere di consentire ai proprietari del sito di selezionare la regola di eliminazione più adatta al loro sito. Potresti inoltre voler consentire ai proprietari del sito di rifiutare completamente un criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="26770-p111">Allo stesso tempo, puoi comunque creare e gestire centralmente i criteri. Puoi anche selezionare un criterio e una regola come predefiniti, in modo che un criterio sia sempre valido finché il proprietario non ne sceglie uno diverso o lo rifiuti. Se vuoi offrire tale flessibilità ai proprietari del sito, puoi:</span><span class="sxs-lookup"><span data-stu-id="26770-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="26770-143">Creare un solo criterio con diverse regole di eliminazione e impostare una regola come predefinita.</span><span class="sxs-lookup"><span data-stu-id="26770-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="26770-144">Impostare il criterio come criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="26770-145">Assegnare il criterio a un modello di raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="26770-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="26770-146">I proprietari del sito possono selezionare una delle regole di eliminazione alternative, rifiutare il criterio o non fare nulla ed essere soggetti al criterio e alla regola predefiniti.</span><span class="sxs-lookup"><span data-stu-id="26770-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![Diagramma con un criterio con molte regole](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="26770-148">Esempio 3: applicare diversi criteri con una o più regole a una raccolta siti</span><span class="sxs-lookup"><span data-stu-id="26770-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="26770-p112">Questo esempio offre la massima flessibilità ai proprietari del sito perché possono scegliere tra diversi criteri e dopo aver selezionato un criterio, possono spesso scegliere tra diverse regole. Un criterio e una regola vengono impostati come predefiniti, in modo che un criterio sia sempre valido finché il proprietario del sito non ne sceglie uno diverso o lo rifiuti. Tieni presente che se non imposti un criterio e una regola come predefiniti, nessun criterio o nessuna regola saranno attivi per le librerie di documenti nel sito finché il proprietario del sito non li selezionerà e applicherà.</span><span class="sxs-lookup"><span data-stu-id="26770-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="26770-p113">Diversamente dai due esempi precedenti, questi criteri vengono assegnati a una raccolta di siti specifica, non al modello di raccolta di siti. Ciò significa che i criteri possono essere ancora più specificatamente personalizzati in base al contenuto in una raccolta di siti specifica.</span><span class="sxs-lookup"><span data-stu-id="26770-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="26770-p114">I criteri e le regole sono ereditate. I proprietari del sito possono selezionare una regola e un criterio per il proprio sito e tutti i siti secondari erediteranno il criterio dal sito principale. Tuttavia, un proprietario di un sito secondario può interrompere l'ereditarietà selezionando un altro criterio e un'altra regola, che a loro volta verranno applicati a tutti i siti secondari finché l'ereditarietà non verrà di nuovo interrotta.</span><span class="sxs-lookup"><span data-stu-id="26770-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="26770-156">Per impostare questo scenario, puoi:</span><span class="sxs-lookup"><span data-stu-id="26770-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="26770-157">Creare diversi criteri che contengono una o più regole.</span><span class="sxs-lookup"><span data-stu-id="26770-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="26770-158">Impostare un criterio e una regola come predefiniti.</span><span class="sxs-lookup"><span data-stu-id="26770-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="26770-159">Assegnare i criteri a una raccolta siti specifica.</span><span class="sxs-lookup"><span data-stu-id="26770-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="26770-160">Inoltre, i criteri e le regole vengono creati in base a una raccolta di siti specifica, dove i proprietari del sito possono interrompere l'ereditarietà selezionando il criterio e la regola più adatti al proprio sito.</span><span class="sxs-lookup"><span data-stu-id="26770-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![Diagramma con molti criteri e regole](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="26770-162">Creare un criterio di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="26770-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="26770-163">Nel centro conformità di &amp; Office 365Security, accedere a \> **conservazione** **della gestione dei dati** .</span><span class="sxs-lookup"><span data-stu-id="26770-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="26770-164">In **Elimina**fare clic su **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**.</span><span class="sxs-lookup"><span data-stu-id="26770-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="26770-165">Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="26770-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="26770-166">La prima volta che si passa dal centro &amp; sicurezza e conformità al centro criteri di eliminazione dei documenti, il centro criteri viene creato automaticamente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="26770-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="26770-167">In alternativa, è possibile creare manualmente il centro criteri [creando la raccolta siti](http://go.microsoft.com/fwlink/p/?LinkID=404342) e scegliendo **centro criteri di conformità** nella scheda **organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="26770-167">Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="26770-168">Scegliere i **criteri di eliminazione**.</span><span class="sxs-lookup"><span data-stu-id="26770-168">Choose **Deletion Policies**.</span></span>
    
    ![Opzione Elimina criteri](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="26770-170">Scegli **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="26770-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="26770-p117">Inserisci un nome e una descrizione per il criterio. I proprietari del sito possono selezionare un criterio per il proprio sito in base al nome o alla descrizione, quindi ti consigliamo di inserire abbastanza informazioni per permettergli di scegliere il criterio corretto.</span><span class="sxs-lookup"><span data-stu-id="26770-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="26770-173">Per creare una regola, scegli **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="26770-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="26770-174">Inserisci un nome e scegli le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="26770-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="26770-175">Scegliere se la regola eliminerà definitivamente i documenti o li sposterà nel Cestino.</span><span class="sxs-lookup"><span data-stu-id="26770-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="26770-176">Il Cestino è una rete di sicurezza aggiuntiva prima che l'elemento venga eliminato in modo permanente da un sito.</span><span class="sxs-lookup"><span data-stu-id="26770-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="26770-177">Per ulteriori informazioni sul Cestino, vedere [empty the Recycle bin o restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span><span class="sxs-lookup"><span data-stu-id="26770-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="26770-178">Scegli se la data di eliminazione deve essere creata dalla data di creazione del documento a da quella dell'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="26770-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="26770-179">Inserisci un numero di giorni, mesi o anni come periodo di tempo dopo il quale un documento deve essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="26770-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="26770-p119">Scegli se la regola è una regola predefinita. La prima regola creata viene automaticamente impostata come la regola predefinita. Una regola predefinita viene automaticamente applicata a tutte le librerie nei siti che usano il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![Pagina Nuova regola di eliminazione](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="26770-184">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="26770-p120">Crea regole aggiuntive se vuoi che i proprietari del sito possano scegliere diverse regole da applicare al proprio sito. Verrà applicata la regola predefinita, se presente, se il proprietario del sito non esegue alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="26770-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="26770-187">Per rimuovere una regola da un criterio, selezionare la regola, fare clic su **Elimina**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26770-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26770-188">Se si elimina una regola e il criterio non contiene una regola predefinita, non verrà applicata alcuna regola per tale criterio, in altre parole, non verranno eliminati documenti.</span><span class="sxs-lookup"><span data-stu-id="26770-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![Messaggio di conferma dell'eliminazione di una regola da un criterio](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="26770-190">Assegnare il criterio di eliminazione dei documenti a un modello di raccolta di siti</span><span class="sxs-lookup"><span data-stu-id="26770-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="26770-191">Assegnando un criterio a un modello di raccolta di siti, puoi rendere disponibile il criterio per tutte le raccolte di siti create dal tale modello, comprese le raccolte di siti esistenti e le raccolte di siti create nel futuro.</span><span class="sxs-lookup"><span data-stu-id="26770-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="26770-192">È importante comprendere che il periodo di tempo specificato per un criterio di eliminazione dei documenti significa che il tempo dopo la creazione o la modifica del documento non è il momento in cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="26770-193">Quando assegni il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano il criterio, verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="26770-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="26770-194">Questo vale per tutti i documenti esistenti, non solo per quelli creati dal momento dell'assegnazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="26770-195">Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** .</span><span class="sxs-lookup"><span data-stu-id="26770-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="26770-196">In **Elimina**fare clic su **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**.</span><span class="sxs-lookup"><span data-stu-id="26770-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="26770-197">Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="26770-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="26770-198">Scegli **Assegnazioni dei criteri per i modelli**.</span><span class="sxs-lookup"><span data-stu-id="26770-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![Opzione Assegnazioni criteri per modelli](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="26770-200">Scegli **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="26770-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="26770-201">Effettua una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26770-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="26770-202">Per assegnare il criterio a un modello di raccolta di siti come il modello Siti del team, seleziona **Assegna a un modello di raccolta di siti**, quindi seleziona il modello di raccolta di siti.</span><span class="sxs-lookup"><span data-stu-id="26770-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="26770-203">Per assegnare il criterio agli utenti di un'unità per le aziende, scegliere **assegna a OneDrive for Business template**, evidenziato di seguito.</span><span class="sxs-lookup"><span data-stu-id="26770-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26770-204">Quando assegni un criterio a un modello di raccolta di siti, tale criterio sarà disponibile sia per le raccolte di siti esistenti create dal modello, sia per quelle che verranno create in futuro.</span><span class="sxs-lookup"><span data-stu-id="26770-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![Pagina di scelta di un modello con opzione OneDrive](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="26770-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26770-207">A ogni modello può essere assegnato solo un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="26770-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="26770-208">Se viene visualizzato un messaggio di errore che indica che a questo modello sono già stati assegnati criteri, scegliere **Annulla** \> **assegna a raccolta siti** nella \> barra di spostamento a sinistra selezionare una raccolta siti per visualizzare e gestire il set di criteri già assegnato.</span><span class="sxs-lookup"><span data-stu-id="26770-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="26770-209">Scegli **Gestisci criteri assegnati**, seleziona i criteri che vuoi assegnati, quindi scegli se un criterio deve essere contrassegnato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="26770-210">Quando configuri un criterio predefinito, tutti i siti in cui è assegnato il criterio hanno automaticamente il criterio attivo senza che il proprietario del sito debba fare nulla.</span><span class="sxs-lookup"><span data-stu-id="26770-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Pagina di aggiunta e gestione criteri](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="26770-212">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="26770-p125">Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato al modello di raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="26770-216">Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="26770-217">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="26770-218">Assegnare il criterio di eliminazione dei documenti a una raccolta di siti</span><span class="sxs-lookup"><span data-stu-id="26770-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="26770-p126">Assegnando un criterio a una raccolta di siti specifica, rendi disponibile il criterio solo per tale raccolta di siti specifica. Ciò significa che puoi meglio adattare i criteri al contenuto della raccolta di siti. Inoltre, i criteri assegnati a una raccolta di siti specifica sostituiranno tutti i criteri assegnati al modello di tale raccolta di siti. Ad esempio, un criterio assegnato alla raccolta di siti Reparto vendite (creato dal modello Siti del team) sostituirà tutti i criteri assegnati al modello Siti del team.</span><span class="sxs-lookup"><span data-stu-id="26770-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="26770-223">È importante comprendere che il periodo di tempo specificato per un criterio di eliminazione dei documenti significa che il tempo dopo la creazione o la modifica del documento non è il momento in cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="26770-224">Quando assegni il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano il criterio, verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="26770-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="26770-225">Questo vale per tutti i documenti esistenti, non solo per quelli creati dal momento dell'assegnazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="26770-226">Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** .</span><span class="sxs-lookup"><span data-stu-id="26770-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="26770-227">In **Elimina**scegliere **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**.</span><span class="sxs-lookup"><span data-stu-id="26770-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="26770-228">Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="26770-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="26770-229">Scegli **Assegnazioni dei criteri per le raccolte di siti**.</span><span class="sxs-lookup"><span data-stu-id="26770-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![Opzione Assegnazioni criteri per raccolte di siti](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="26770-231">Scegli **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="26770-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="26770-232">Scegliere **Scegli una raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="26770-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="26770-233">Cercare la raccolta siti in base al nome o all'URL, selezionare la raccolta siti e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26770-234">A ogni raccolta di siti può essere assegnato solo un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="26770-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="26770-235">Se viene visualizzato un messaggio di errore che indica che la raccolta siti è già stata assegnata ai criteri, scegliere **Annulla** \> **assegna a raccolta siti** e selezionare una raccolta siti per visualizzare e gestire il set di criteri già assegnati.</span><span class="sxs-lookup"><span data-stu-id="26770-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![Pagina di scelta raccolta di siti](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="26770-237">Scegli **Gestisci criteri assegnati**, seleziona i criteri che vuoi assegnati, quindi scegli se un criterio deve essere contrassegnato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="26770-238">Quando configuri un criterio predefinito, tutti i siti in cui è assegnato il criterio hanno automaticamente il criterio attivo senza che il proprietario del sito debba fare nulla.</span><span class="sxs-lookup"><span data-stu-id="26770-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Pagina di aggiunta e gestione criteri](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="26770-240">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="26770-p132">Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato alla raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="26770-244">Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="26770-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="26770-245">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26770-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="26770-246">Eliminare l'assegnazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="26770-246">Delete a policy assignment</span></span>

<span data-ttu-id="26770-247">Quando elimini un'assegnazione, i criteri assegnati non verranno più applicati ai siti nella raccolta di siti o nel modello di raccolta di siti.</span><span class="sxs-lookup"><span data-stu-id="26770-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="26770-248">Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** .</span><span class="sxs-lookup"><span data-stu-id="26770-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="26770-249">In **Elimina**scegliere **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**.</span><span class="sxs-lookup"><span data-stu-id="26770-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="26770-250">Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="26770-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="26770-251">Scegliere una delle opzioni **Assegnazioni dei criteri per i modelli** o **Assegnazioni dei criteri per le raccolte di siti**.</span><span class="sxs-lookup"><span data-stu-id="26770-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="26770-252">Selezionare l'elemento di assegnazione e fare clic su **Elimina elemento**.</span><span class="sxs-lookup"><span data-stu-id="26770-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![Comando Elimina elemento per assegnazione criterio](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="26770-254">Eliminare un criterio</span><span class="sxs-lookup"><span data-stu-id="26770-254">Delete a policy</span></span>

<span data-ttu-id="26770-255">Non è possibile eliminare un criterio in uso.</span><span class="sxs-lookup"><span data-stu-id="26770-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="26770-256">Prima di poter eliminare un criterio, è innanzitutto necessario eliminare tutte le assegnazioni alle raccolte siti e ai modelli di raccolta siti che includono tale criterio, vedere la sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="26770-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="26770-257">Nel centro &amp; \> sicurezza e conformità scegliere **conservazione** della \> \> **gestione dei dati** nel riquadro di spostamento a sinistra in **Delete** \> **Manage document deletion Policies for SharePoint Online and OneDrive per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="26770-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="26770-258">Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="26770-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="26770-259">Scegliere \* \* criteri di eliminazione \* \*.</span><span class="sxs-lookup"><span data-stu-id="26770-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![Opzione Elimina criteri](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="26770-261">Seleziona il criterio.</span><span class="sxs-lookup"><span data-stu-id="26770-261">Select the policy.</span></span>
    
4. <span data-ttu-id="26770-262">Nella scheda \> \*\*\*\* \> elementi della barra multifunzione **rimuovere i criteri**.</span><span class="sxs-lookup"><span data-stu-id="26770-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![Pulsante Rimuovi criterio sulla barra multifunzione](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="26770-264">Se il criterio è in uso, verrà chiesto se si desidera rimuovere il criterio da tutte le raccolte siti in cui viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="26770-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="26770-265">Se si è sicuri, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="26770-265">If you're sure, choose **OK**.</span></span>
    
    ![Messaggio di conferma eliminazione criterio](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="26770-267">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26770-267">See also</span></span>

[<span data-ttu-id="26770-268">Panoramica dei criteri di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="26770-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="26770-269">Applicare o rimuovere un criterio di eliminazione del documento per un sito</span><span class="sxs-lookup"><span data-stu-id="26770-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

