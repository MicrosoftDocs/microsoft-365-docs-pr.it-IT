---
title: Disciplinare le informazioni soggette alla normativa sulla privacy dei dati
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Utilizzare le etichette e i criteri di conservazione di Microsoft 365 per gestire i dati personali nell'ambiente Microsoft 365.
ms.openlocfilehash: 4c65eafa167d7224c4022d5634ce089952fada19
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695162"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="e1773-103">Disciplinare le informazioni soggette alla normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="e1773-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="e1773-104">I controlli di governance delle informazioni possono essere utilizzati nel proprio ambiente per aiutare a soddisfare le esigenze di conformità alla privacy dei dati, tra cui un numero specifico per il regolamento generale sulla protezione dei dati (GDPR), HIPAA-HITECH (United States Health Care Privacy Act), California Consumer Protection Act (CCPA) e the Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="e1773-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="e1773-105">Questi controlli rientrano principalmente nelle aree di soluzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1773-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="e1773-106">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="e1773-106">Retention policies</span></span>
- <span data-ttu-id="e1773-107">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="e1773-107">Retention labels</span></span>
- <span data-ttu-id="e1773-108">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="e1773-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="e1773-109">Normative sulla privacy dei dati che influiscono sui controlli di governance</span><span class="sxs-lookup"><span data-stu-id="e1773-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="e1773-110">Ecco un elenco di esempi di regolamenti sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="e1773-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="e1773-111">Articolo GDPR (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="e1773-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="e1773-112">Articolo di GDPR (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="e1773-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="e1773-113">HIPAA-HITECH (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="e1773-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="e1773-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="e1773-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="e1773-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="e1773-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="e1773-116">LGPD articolo 46</span><span class="sxs-lookup"><span data-stu-id="e1773-116">LGPD Article 46</span></span>

<span data-ttu-id="e1773-117">Per ulteriori informazioni su queste normative, vedere l' [articolo valutare i rischi per la privacy dei dati e identificare le informazioni riservate](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="e1773-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="e1773-118">Per la governance delle informazioni, le normative sulla privacy dei dati in genere richiedono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e1773-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="e1773-119">È consigliabile utilizzare un sistema tecnico per la conservazione e l'eliminazione dei dati personali archiviati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1773-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="e1773-120">Se si desidera archiviare i dati personali, informare l'oggetto del periodo di archiviazione dei dati, che è una prassi standard ora disponibile nei sistemi Web front-end.</span><span class="sxs-lookup"><span data-stu-id="e1773-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="e1773-121">I dati personali devono essere protetti dall'elaborazione, dalla perdita o dall'alterazione accidentale mediante metodi verificabili.</span><span class="sxs-lookup"><span data-stu-id="e1773-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="e1773-122">Tutte le azioni eseguite nei confronti dei dati personali devono essere documentate e la documentazione deve essere conservata per un periodo specificato.</span><span class="sxs-lookup"><span data-stu-id="e1773-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="e1773-123">Poiché le normative sulla privacy dei dati non sono molto specifiche per quanto riguarda la conservazione e l'eliminazione dei dati, è necessario tenere in considerazione altri fattori che possono imporre linee guida per la governance delle informazioni per le informazioni personali archiviate nell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1773-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="e1773-124">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="e1773-124">Here are a few examples:</span></span>

- <span data-ttu-id="e1773-125">Invecchiamento degli account consumer dopo 5 anni di inattività e richiede l'eliminazione o la Anonymization dei dati degli account dopo quel momento, richiedendo l'orchestrazione tra il sistema che archivia i dati e i flussi di lavoro relativi alle notifiche e ad altre automazioni.</span><span class="sxs-lookup"><span data-stu-id="e1773-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="e1773-126">Configuring rules for keeping Policy and Procedures related to GDPR around per tre anni dopo che sono stati sostituiti, che si allinea con la pianificazione di conservazione dell'organizzazione per i criteri e le procedure.</span><span class="sxs-lookup"><span data-stu-id="e1773-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="e1773-127">Gestione di una sottoscrizione separata per la comunicazione con i consumatori tramite l'organizzazione di supporto.</span><span class="sxs-lookup"><span data-stu-id="e1773-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="e1773-128">Tutte le comunicazioni di posta elettronica sono state conservate ed eliminate dopo due settimane per ridurre la formazione di debiti sulla privacy nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e1773-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="e1773-129">Una domanda fondamentale per rispondere è:</span><span class="sxs-lookup"><span data-stu-id="e1773-129">A key question to answer is:</span></span> 

- <span data-ttu-id="e1773-130">In che modo le informazioni contenenti i dati personali devono essere mantenute in giro per motivi aziendali validi per evitare che le procedure vengano "conservate per sempre"?</span><span class="sxs-lookup"><span data-stu-id="e1773-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="e1773-131">Questo deve essere bilanciato con le esigenze di conservazione per la continuità aziendale.</span><span class="sxs-lookup"><span data-stu-id="e1773-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="e1773-132">Indipendentemente dai motivi legali e aziendali per mantenere le informazioni personali intorno o eliminarlo, Microsoft fornisce una serie di funzionalità per implementare lo schema di governance dei dati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1773-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="e1773-133">Gestione della governance delle informazioni in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1773-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="e1773-134">Per iniziare, vedere [Manage information governance](../compliance/manage-information-governance.md) and [data retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="e1773-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="e1773-135">Sviluppare pianificazioni di conservazione dei dati per contenitori, messaggi di posta elettronica e contenuto</span><span class="sxs-lookup"><span data-stu-id="e1773-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="e1773-136">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e1773-136">Keep the following in mind:</span></span>

- <span data-ttu-id="e1773-137">La creazione di una pianificazione di conservazione dei dati per i tipi di informazioni definite deve essere considerata un prerequisito per l'implementazione di qualsiasi schema di conservazione o eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e1773-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="e1773-138">Dato il numero di tipi di informazioni che la maggior parte delle organizzazioni considera importanti e le corrispondenti pianificazioni di conservazione dei record di grandi dimensioni che vengono configurate con essi, l'implementazione di una strategia di conservazione e gestione di record richiede la pianificazione</span><span class="sxs-lookup"><span data-stu-id="e1773-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="e1773-139">La chiave per la definizione di una strategia di governance dei dati efficace di questo tipo è quella di concentrarsi sulle funzioni aziendali e sui tipi di informazioni con priorità più alta che richiedono una gestione più formale.</span><span class="sxs-lookup"><span data-stu-id="e1773-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="e1773-140">Esempi sono i contratti legali, i rendiconti finanziari e la documentazione relativa alla conformità alle normative.</span><span class="sxs-lookup"><span data-stu-id="e1773-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="e1773-141">Provare a evitare di disporre di una pianificazione di conservazione separata per ogni singolo tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="e1773-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="e1773-142">Provare a utilizzare le categorie generali il più possibile, ad esempio, con le pianificazioni di conservazione di 7 anni per il contenuto aziendale generale.</span><span class="sxs-lookup"><span data-stu-id="e1773-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="e1773-143">Una volta che i tipi di informazioni personali nel proprio ambiente sono più noti, stabilire le pianificazioni di conservazione ed eliminazione per questo tipo di contenuto e modificare l'architettura delle informazioni per semplificare la governance di questo tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="e1773-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="e1773-144">Ad esempio, isolare le informazioni personali in siti, raccolte o cartelle separate con accesso controllato.</span><span class="sxs-lookup"><span data-stu-id="e1773-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="e1773-145">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="e1773-145">Retention policies</span></span>

<span data-ttu-id="e1773-146">Creare e distribuire i [criteri di conservazione](../compliance/retention-policies.md) per il contenuto nei siti applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e1773-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="e1773-147">Per la privacy dei dati per i siti che contengono o dovrebbero contenere dati personali, specificare le regole di conservazione o eliminazione per soddisfare gli standard organizzativi.</span><span class="sxs-lookup"><span data-stu-id="e1773-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="e1773-148">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="e1773-148">Retention labels</span></span>

<span data-ttu-id="e1773-149">Creare e distribuire [etichette di conservazione](../compliance/labels.md) per contenuti e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e1773-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="e1773-150">Per la privacy dei dati per siti, raccolte, cartelle e messaggi di posta elettronica che contengono o dovrebbero contenere dati personali, specificare regole di conservazione o eliminazione automatica per soddisfare gli standard organizzativi.</span><span class="sxs-lookup"><span data-stu-id="e1773-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="e1773-151">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="e1773-151">Records management</span></span>

<span data-ttu-id="e1773-152">Creare e distribuire etichette di conservazione per la gestione dei record in base a una pianificazione di conservazione dei record e al piano di file.</span><span class="sxs-lookup"><span data-stu-id="e1773-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="e1773-153">Per la privacy dei dati, le richieste del soggetto dei dati (richieste DSR) ricevute dal reparto legale vengono dichiarate come record e memorizzate a tempo indeterminato per conformarsi alle specifiche di conservazione delle attività normative.</span><span class="sxs-lookup"><span data-stu-id="e1773-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="e1773-154">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1773-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="e1773-155">Gestione record</span><span class="sxs-lookup"><span data-stu-id="e1773-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="e1773-156">Gestione del piano di archiviazione</span><span class="sxs-lookup"><span data-stu-id="e1773-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="e1773-157">Conservazione basata su eventi per la gestione dei record</span><span class="sxs-lookup"><span data-stu-id="e1773-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="e1773-158">Disposizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="e1773-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)