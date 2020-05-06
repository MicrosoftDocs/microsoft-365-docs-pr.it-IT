---
title: Applicare o rimuovere un criterio di eliminazione del documento per un sito
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come creare, eliminare e gestire un criterio di eliminazione dei documenti in una raccolta siti di Office 365.
ms.openlocfilehash: 7a9cbec25349de02da35f0aaf0cc206774a9b59a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034340"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="04689-103">Applicare o rimuovere un criterio di eliminazione del documento per un sito</span><span class="sxs-lookup"><span data-stu-id="04689-103">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="04689-104">Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="04689-104">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="04689-105">Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali.</span><span class="sxs-lookup"><span data-stu-id="04689-105">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="04689-106">Per questo motivo, è possibile che l'organizzazione abbia creato un criterio di eliminazione dei&mdash;documenti per il sito, ad esempio, i documenti aziendali generali potrebbero essere necessari per essere eliminati cinque anni dopo la loro creazione.</span><span class="sxs-lookup"><span data-stu-id="04689-106">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="04689-107">A seconda dell'organizzazione, un criterio di eliminazione del documento può essere:</span><span class="sxs-lookup"><span data-stu-id="04689-107">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="04689-108">**Obbligatorio** Il proprietario di un sito non può escludere un criterio obbligatorio, che viene automaticamente applicato al sito.</span><span class="sxs-lookup"><span data-stu-id="04689-108">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="04689-109">**Predefinito** Un criterio predefinito è applicato al sito automaticamente, ma il proprietario del sito può:</span><span class="sxs-lookup"><span data-stu-id="04689-109">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="04689-110">Selezionare un altro criterio, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="04689-110">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="04689-111">Escludere completamente il criterio se non è pertinente per il contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="04689-111">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="04689-112">**Né obbligatorio né predefinito** In questo caso, nessun criterio è applicato al sito automaticamente e il proprietario del sito deve eseguire determinate azioni per applicarne uno.</span><span class="sxs-lookup"><span data-stu-id="04689-112">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="04689-113">Un criterio di eliminazione dei documenti può contenere più di&mdash;una regola, ad esempio, una regola potrebbe dire eliminare i documenti un anno dopo che sono stati creati, ma un'altra regola potrebbe dire eliminare i documenti un anno dopo l'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="04689-113">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="04689-114">Se un criterio contiene più di una regola, è possibile selezionare la regola che meglio si applica al sito.</span><span class="sxs-lookup"><span data-stu-id="04689-114">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="04689-115">La regola di eliminazione verrà applicata a tutte le raccolte all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="04689-115">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="04689-116">Solo un criterio e una regola alla volta possono essere attivi in un sito.</span><span class="sxs-lookup"><span data-stu-id="04689-116">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="04689-117">Analogamente a un criterio, è possibile impostare una regola come predefinita, in modo che venga applicata automaticamente quando viene applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="04689-117">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="04689-p103">Infine, i criteri di eliminazione del documento vengono ereditati. Quando selezioni un criterio o una regola per il tuo sito, tale scelta viene ereditata da tutti i siti secondari, anche se il proprietario di un sito secondario può interrompere l'ereditarietà selezionando un criterio o una regola diversi. Quando selezioni un criterio o una regola, tieni presente il contenuto di eventuali siti secondari all'interno del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="04689-p103">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="04689-121">Visualizzare i criteri di eliminazione del documento disponibili in una raccolta siti</span><span class="sxs-lookup"><span data-stu-id="04689-121">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="04689-p104">La tua organizzazione può assegnare criteri diversi a raccolte siti diverse. A livello della raccolta siti, il proprietario di una raccolta siti può visualizzare tutti i criteri di eliminazione del documento disponibili per tale raccolta siti. I criteri possono essere stati resi disponibili per il modello della raccolta siti (e di conseguenza per tutte le raccolte siti create da quel modello) oppure per quella specifica raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="04689-p104">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="04689-125">Nel sito principale della raccolta siti, nell'angolo in alto a destra, scegliere **Impostazioni** [icona Gear] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="04689-125">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="04689-126">In **criteri di eliminazione dei documenti**di **Amministrazione** \> raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="04689-126">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04689-127">Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="04689-127">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="04689-128">Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** .</span><span class="sxs-lookup"><span data-stu-id="04689-128">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="04689-129">In questa pagina puoi trovare:</span><span class="sxs-lookup"><span data-stu-id="04689-129">On this page you can view:</span></span>
    
  - <span data-ttu-id="04689-p106">I criteri attualmente assegnati e le regole associate. Seleziona un criterio per visualizzare le regole nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="04689-p106">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="04689-132">Se presente, il criterio predefinito presenta l'opzione **Sì** nella colonna **predefinita**.</span><span class="sxs-lookup"><span data-stu-id="04689-132">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="04689-133">Se è stato assegnato un criterio **obbligatorio**, al di sotto dell'elenco viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="04689-133">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="04689-p107">Questo elenco è solo in modalità visualizzazione e consente al proprietario della raccolta siti di vedere tutti i criteri e le regole disponibili. Per informazioni sull'applicazione di un criterio, consulta la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="04689-p107">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Visualizzare i criteri di eliminazione dei documenti assegnati a una raccolta siti](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="04689-137">Applicare o rimuovere un criterio di eliminazione del documento per un sito</span><span class="sxs-lookup"><span data-stu-id="04689-137">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="04689-138">È possibile che la tua organizzazione abbia creato dei criteri che, in qualità di proprietario di un sito o di una raccolta siti, puoi sia applicare al tuo sito sia disattivare completamente.</span><span class="sxs-lookup"><span data-stu-id="04689-138">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="04689-139">Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="04689-139">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="04689-140">In **criteri di eliminazione dei documenti**di amministrazione \> del **sito** .</span><span class="sxs-lookup"><span data-stu-id="04689-140">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04689-141">Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="04689-141">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="04689-142">Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** .</span><span class="sxs-lookup"><span data-stu-id="04689-142">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="04689-143">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04689-143">Do one of the following:</span></span>
    
  - <span data-ttu-id="04689-144">**Per applicare un criterio** Selezionare un criterio \> selezionare una regola per il \> **salvataggio**di un criterio.</span><span class="sxs-lookup"><span data-stu-id="04689-144">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="04689-p109">Solo un criterio e una regola alla volta possono essere attivi in un sito. L'organizzazione può fornire più criteri e regole tra cui scegliere oppure metterne a disposizione solo uno.</span><span class="sxs-lookup"><span data-stu-id="04689-p109">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Selezionare l'opzione criterio](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="04689-148">**Per rifiutare l'esclusione di un criterio** Scegliere **opt-out: do note Delete** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="04689-148">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="04689-149">Come proprietario di un sito, è possibile escludere un criterio di eliminazione dei documenti se si determina che il criterio non è applicabile al contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="04689-149">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="04689-150">Tuttavia, non è possibile escludere un criterio contrassegnato come **obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="04689-150">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opzione opt-out](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="04689-152">I criteri di eliminazione del documento ignorano altri criteri</span><span class="sxs-lookup"><span data-stu-id="04689-152">Document deletion policies override other policies</span></span>

<span data-ttu-id="04689-153">Un sito può utilizzare altri criteri per il mantenimento e l'eliminazione dei contenuti:</span><span class="sxs-lookup"><span data-stu-id="04689-153">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="04689-154">Criteri tipo di contenuto per la raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="04689-154">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="04689-155">Criteri di gestione delle informazioni per un elenco o una libreria.</span><span class="sxs-lookup"><span data-stu-id="04689-155">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="04689-156">Se applichi un criterio di eliminazione del documento a un sito che già utilizza criteri tipo di contenuto o criteri di gestione delle informazioni per un elenco o una libreria, tali criteri vengono ignorati mentre il criterio di eliminazione del documento è attivo.</span><span class="sxs-lookup"><span data-stu-id="04689-156">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="04689-157">Se altri criteri vengono ignorati, verrà visualizzato il messaggio "contenuto in questo sito utilizza i criteri di eliminazione dei documenti".</span><span class="sxs-lookup"><span data-stu-id="04689-157">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="04689-158">Questo significa che dovresti pianificare un sito che utilizzi solo criteri destinati a contenuti strutturati (criteri di gestione delle informazioni e criteri tipo di contenuto) o contenuti non strutturati (criteri di eliminazione del documento) e non ad entrambi.</span><span class="sxs-lookup"><span data-stu-id="04689-158">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="04689-159">Se si sceglie di escludere un criterio di eliminazione dei documenti, l'avviso non verrà visualizzato e altri tipi di criteri continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="04689-159">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="04689-160">I criteri di eliminazione del documento non hanno alcun effetto sui criteri sito.</span><span class="sxs-lookup"><span data-stu-id="04689-160">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="04689-161">Determinare se i criteri tipo di contenuto vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="04689-161">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="04689-162">Se il tuo sito stava utilizzando criteri tipo di contenuto e ne ricevi il messaggio solo adesso, quei criteri non sono più attivi.</span><span class="sxs-lookup"><span data-stu-id="04689-162">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="04689-163">Per ripristinare i criteri dei tipi di contenuto, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="04689-163">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="04689-164">Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="04689-164">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="04689-165">Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="04689-165">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="04689-166">In \> **modelli di criteri tipo di contenuto** **Amministrazione sito** .</span><span class="sxs-lookup"><span data-stu-id="04689-166">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="04689-168">Determinare se i criteri di gestione delle informazioni vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="04689-168">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="04689-169">Se il tuo sito stava utilizzando criteri di gestione delle informazioni e ne ricevi il messaggio solo adesso, quei criteri non sono più attivi.</span><span class="sxs-lookup"><span data-stu-id="04689-169">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="04689-170">Per ripristinare i criteri di gestione delle informazioni, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="04689-170">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="04689-171">Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="04689-171">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="04689-172">Per un elenco o una raccolta, nelle impostazioni \> della \> **raccolta** \> **schede della raccolta della** barra multifunzione in **autorizzazioni e gestione** \> delle informazioni di gestione **delle impostazioni dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="04689-172">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="04689-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04689-174">See also</span></span>

[<span data-ttu-id="04689-175">Panoramica dei criteri di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="04689-175">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="04689-176">Creare un criterio di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="04689-176">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

