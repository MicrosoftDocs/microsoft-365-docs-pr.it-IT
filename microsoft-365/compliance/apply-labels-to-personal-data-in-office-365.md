---
title: Applicare le etichette ai dati personali in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come utilizzare le etichette di Office per il piano di protezione RGPD.
ms.openlocfilehash: 023d6e2d3db1b6ec844801598df1925f3660217f
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256913"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="5c439-103">Applicare le etichette ai dati personali in Office 365</span><span class="sxs-lookup"><span data-stu-id="5c439-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="5c439-104">Consultare questo argomento se si usano etichette di classificazione per il piano di protezione GDPR.</span><span class="sxs-lookup"><span data-stu-id="5c439-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="5c439-105">Se si usano etichette per la protezione dei dati personali in Office 365, Microsoft consiglia di iniziare con le [etichette di conservazione](labels.md).</span><span class="sxs-lookup"><span data-stu-id="5c439-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="5c439-106">Con le etichette di conservazione è possibile:</span><span class="sxs-lookup"><span data-stu-id="5c439-106">With retention labels, you can:</span></span>
- <span data-ttu-id="5c439-107">Usare Advanced Data Governance per applicare automaticamente le etichette in base ai tipi di informazioni sensibili o ad altri criteri.</span><span class="sxs-lookup"><span data-stu-id="5c439-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="5c439-108">Usare le etichette di conservazione con la prevenzione della perdita dei dati per applicare la protezione.</span><span class="sxs-lookup"><span data-stu-id="5c439-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="5c439-109">Usare le etichette con eDiscovery e Ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="5c439-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="5c439-110">Cloud App Security attualmente non supporta le etichette di conservazione, ma è possibile usare i tipi di informazioni riservate di Office 365 con Cloud App Security per monitorare i dati personali che si trovano in altre app SaaS.</span><span class="sxs-lookup"><span data-stu-id="5c439-110">Cloud App Security doesn't currently support retention labels, but you can use Office 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="5c439-111">Le [etichette di riservatezza](sensitivity-labels.md) sono attualmente consigliate per l'applicazione di etichette a file locali e in altri provider e servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="5c439-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="5c439-112">Sono consigliate anche per file in Office 365 che richiedono la crittografia di Azure Information Protection per la protezione dei dati, ad esempio file contenenti segreti commerciali.</span><span class="sxs-lookup"><span data-stu-id="5c439-112">These are also recommended for files in Office 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="5c439-113">Al momento, l'uso di Azure Information Protection per applicare la crittografia non è consigliabile per i file in Office 365 contenenti dati soggetti al GDPR.</span><span class="sxs-lookup"><span data-stu-id="5c439-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Office 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="5c439-114">I servizi di Office 365 attualmente non possono leggere nei file con crittografia AIP.</span><span class="sxs-lookup"><span data-stu-id="5c439-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="5c439-115">Di conseguenza, il servizio non trova i dati sensibili in questi file.</span><span class="sxs-lookup"><span data-stu-id="5c439-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="5c439-116">Le etichette di conservazione possono essere applicate ai messaggi di posta elettronica in Exchange Online e queste etichette funzionano con la prevenzione della perdita dei dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c439-116">Retention labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Le etichette di Office 365 e di Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="5c439-118">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="5c439-118">In the illustration:</span></span>

-   <span data-ttu-id="5c439-119">Usare le etichette di conservazione per i dati personali per i file con segreti commerciali e soggetti a normative in SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="5c439-119">Use retention labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="5c439-120">È possibile usare i tipi di informazioni sensibili di Office 365 all'interno di Office 365 e Cloud App Security per monitorare i dati personali che si trovano in altre app SaaS.</span><span class="sxs-lookup"><span data-stu-id="5c439-120">Office 365 sensitive information types can be used within Office 365 and with Cloud App Security to monintor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="5c439-121">Usare le etichette di riservatezza per i file con segreti commerciali e soggetti a normative, la posta elettronica di Exchange Online, file in altri servizi SaaS, file in datacenter locali e file in altri provider cloud.</span><span class="sxs-lookup"><span data-stu-id="5c439-121">Use sensitivity labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="5c439-122">Usare le etichette di conservazione e i tipi di informazioni sensibili in Microsoft 365 per la protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="5c439-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="5c439-123">La figura seguente mostra come usare le etichette di conservazione e i tipi di informazioni sensibili in criteri di etichetta, criteri di prevenzione della perdita dei dati e i criteri di Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="5c439-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etichette di Office e tipi di informazioni riservate](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="5c439-125">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="5c439-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5c439-126"><strong>Elementi di classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="5c439-127"><strong>Criteri delle etichette - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="5c439-128"><strong>Criteri di prevenzione della perdita dei dati - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="5c439-129"><strong>I criteri di Cloud App Security per tutte le app SaaS - 1 esempio</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="5c439-130">Etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="5c439-130">Retention labels.</span></span> <span data-ttu-id="5c439-131">Esempi: Personale, Pubblico, Dati cliente, Dati risorse umane, Riservato, Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="5c439-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="5c439-p105">Applicare automaticamente questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="5c439-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="5c439-135">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="5c439-135">Customer data</span></span></p>
<p><span data-ttu-id="5c439-p106">... ai documenti che corrispondono a questi tipi di informazioni riservate...</span><span class="sxs-lookup"><span data-stu-id="5c439-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="5c439-142">&lt;elenco dei tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="5c439-p107">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="5c439-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="5c439-146">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="5c439-p108">... ai documenti con questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="5c439-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="5c439-153">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="5c439-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="5c439-p109">Avvisa quando i file con questi attributi...</span><span class="sxs-lookup"><span data-stu-id="5c439-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="5c439-157">Scegliere uno o più attributi: attributo PII predefinito, tipologia di informazioni riservate di Office 365, etichetta di riservatezza (AIP), espressione personalizzata</span><span class="sxs-lookup"><span data-stu-id="5c439-157">Choose one or more attribute: predefined PII attribute, Office 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="5c439-158">.</span><span class="sxs-lookup"><span data-stu-id="5c439-158">.</span></span> <span data-ttu-id="5c439-159">.</span><span class="sxs-lookup"><span data-stu-id="5c439-159">.</span></span> <span data-ttu-id="5c439-160">.</span><span class="sxs-lookup"><span data-stu-id="5c439-160">.</span></span> <span data-ttu-id="5c439-161">in qualsiasi app SaaS approvata vengono condivisi all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5c439-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="5c439-162">Nota: le etichette di conservazione non sono attualmente supportate in Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="5c439-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="5c439-p111">Tipi di informazioni riservate. Esempi: Codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese</span><span class="sxs-lookup"><span data-stu-id="5c439-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="5c439-p112">Pubblicare le etichette per gli utenti da applicare manualmente...</span><span class="sxs-lookup"><span data-stu-id="5c439-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="5c439-168">&lt;selezionare etichette&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="5c439-p113">... a questi percorsi...</span><span class="sxs-lookup"><span data-stu-id="5c439-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="5c439-175">&lt;tutte i percorsi oppure percorsi specifici&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="5c439-p114">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="5c439-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="5c439-179">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="5c439-p115">... ai documenti che corrispondono a questi tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="5c439-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="5c439-184">Definire la priorità dei criteri per applicare automaticamente le etichette
</span><span class="sxs-lookup"><span data-stu-id="5c439-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="5c439-p116">Per i dati personali soggetti all'RGPD, Microsoft consiglia di applicare automaticamente le etichette utilizzando le tipologie di informazioni sensibili create per il proprio ambiente. I criteri che applicano automaticamente le etichette devono essere configurati correttamente e occorre testarli per verificare che producano i risultati previsti.
</span><span class="sxs-lookup"><span data-stu-id="5c439-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="5c439-p117">L'ordine con cui vengono creati i criteri da applicare automaticamente e il fatto che gli utenti applichino o meno queste etichette influisce sul risultato. È quindi importante pianificare attentamente l'implementazione. Ecco cosa serve sapere.</span><span class="sxs-lookup"><span data-stu-id="5c439-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="5c439-189">Un'etichetta alla volta</span><span class="sxs-lookup"><span data-stu-id="5c439-189">One label at a time</span></span>

<span data-ttu-id="5c439-190">È possibile assegnare solo un'etichetta a un documento.</span><span class="sxs-lookup"><span data-stu-id="5c439-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="5c439-191">I criteri più vecchi hanno la precedenza
</span><span class="sxs-lookup"><span data-stu-id="5c439-191">Older auto-apply policies win</span></span>

<span data-ttu-id="5c439-p118">Se sono presenti più regole che assegnano un'etichetta da applicare automaticamente e il contenuto soddisfa le condizioni di più regole, viene assegnata l'etichetta della regola meno recente. Per questo motivo, è importante pianificare con attenzione i criteri delle etichette prima di configurarli. Se un'organizzazione ha l'esigenza di modificare la priorità dei criteri delle etichette, è necessario eliminarli e crearli di nuovo.</span><span class="sxs-lookup"><span data-stu-id="5c439-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="5c439-195">Le etichette applicate manualmente dall'utente hanno la precedenza su quelle applicate automaticamente
</span><span class="sxs-lookup"><span data-stu-id="5c439-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="5c439-p119">Le etichette applicate manualmente dall'utente battono quelle applicate automaticamente. I criteri di applicazione automatica non possono sostituire un'etichetta già applicata da un utente. Gli utenti possono sostituire le etichette applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5c439-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="5c439-199">Le etichette assegnate automaticamente possono essere aggiornate</span><span class="sxs-lookup"><span data-stu-id="5c439-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="5c439-200">Le etichette assegnate automaticamente possono essere aggiornate creando nuovi criteri o aggiornando quelli esistenti.
</span><span class="sxs-lookup"><span data-stu-id="5c439-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="5c439-201">Assicurarsi che il piano di implementazione delle etichette includa:</span><span class="sxs-lookup"><span data-stu-id="5c439-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="5c439-202">Creare i criteri di applicazione automatica secondo l'ordine di priorità.
</span><span class="sxs-lookup"><span data-stu-id="5c439-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="5c439-p120">Allocare il tempo necessario all'applicazione automatica delle etichette prima di consentire agli utenti di applicarle manualmente. Potrebbe essere necessaria anche una settimana per applicare le etichette a tutti i contenuti che corrispondono alle condizioni.
</span><span class="sxs-lookup"><span data-stu-id="5c439-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="5c439-205">Esempio di priorità per creare i criteri di applicazione automatica
</span><span class="sxs-lookup"><span data-stu-id="5c439-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5c439-206"><strong>Etichette</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="5c439-207"><strong>Ordine di priorità per creare criteri da applicare automaticamente</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="5c439-208">Risorse umane - Dati dipendenti</span><span class="sxs-lookup"><span data-stu-id="5c439-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="5c439-209">1</span><span class="sxs-lookup"><span data-stu-id="5c439-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="5c439-210">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="5c439-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="5c439-211">2</span><span class="sxs-lookup"><span data-stu-id="5c439-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="5c439-212">Estremamente riservato
</span><span class="sxs-lookup"><span data-stu-id="5c439-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="5c439-213">3</span><span class="sxs-lookup"><span data-stu-id="5c439-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="5c439-214">Risorse umane - Dati sugli stipendi</span><span class="sxs-lookup"><span data-stu-id="5c439-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="5c439-215">4</span><span class="sxs-lookup"><span data-stu-id="5c439-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="5c439-216">Riservato</span><span class="sxs-lookup"><span data-stu-id="5c439-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="5c439-217">5</span><span class="sxs-lookup"><span data-stu-id="5c439-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="5c439-218">Pubblico</span><span class="sxs-lookup"><span data-stu-id="5c439-218">Public</span></span></td>
<td align="left"><span data-ttu-id="5c439-219">6</span><span class="sxs-lookup"><span data-stu-id="5c439-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="5c439-220">Personale</span><span class="sxs-lookup"><span data-stu-id="5c439-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="5c439-221">Nessun criterio di applicazione automatica</span><span class="sxs-lookup"><span data-stu-id="5c439-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="5c439-222">Creare le etichette e i criteri per applicare le etichette automaticamente
</span><span class="sxs-lookup"><span data-stu-id="5c439-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="5c439-223">Creare le etichette e i criteri nel centro sicurezza o nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="5c439-223">Create labels and policies in the scurity center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5c439-224"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="5c439-225"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5c439-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5c439-226">Assegnare autorizzazioni ai membri del team di conformità.</span><span class="sxs-lookup"><span data-stu-id="5c439-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5c439-p121">I membri del team di conformità che creeranno le etichette necessitano di autorizzazioni per utilizzare il centro sicurezza e/o il centro conformità. Andare a Autorizzazioni nel centro sicurezza o nel centro conformità e modificare i membri del gruppo Amministratori di conformità.</span><span class="sxs-lookup"><span data-stu-id="5c439-p121">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="5c439-229">Vedere <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Concedere agli utenti l'accesso al centro sicurezza e/o al centro conformità</a>.</span><span class="sxs-lookup"><span data-stu-id="5c439-229">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5c439-230">Creare etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="5c439-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="5c439-231">Passare a Classificazioni nel Centro sicurezza o nel Centro conformità, scegliere Etichette di conservazione e creare le etichette per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="5c439-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5c439-232">Creare criteri di applicazione automatica per le etichette.</span><span class="sxs-lookup"><span data-stu-id="5c439-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="5c439-p122">Andare a Classificazione nel centro sicurezza o nel centro conformità, scegliere Criteri etichette e creare i criteri di applicazione automatica delle etichette. Assicurarsi di creare questi criteri nell'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="5c439-p122">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5c439-235">La figura seguente mostra come creare un'etichetta Dati cliente da applicare automaticamente.
</span><span class="sxs-lookup"><span data-stu-id="5c439-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Creare e applicare un'etichetta per i dati del cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="5c439-237">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="5c439-237">In the illustration:</span></span>

- <span data-ttu-id="5c439-238">Viene creata l'etichetta "Dati del cliente".</span><span class="sxs-lookup"><span data-stu-id="5c439-238">The “Customer data” label is created.</span></span>

- <span data-ttu-id="5c439-239">I tipi di informazioni riservate desiderate per l'RGPD sono: codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese.</span><span class="sxs-lookup"><span data-stu-id="5c439-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="5c439-240">La creazione di un criterio di applicazione automatica assegna l'etichetta "Dati del cliente" a qualsiasi file che include uno dei tipi di informazioni riservate aggiunto al criterio.</span><span class="sxs-lookup"><span data-stu-id="5c439-240">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
