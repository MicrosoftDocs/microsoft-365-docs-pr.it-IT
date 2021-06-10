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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Utilizzare Microsoft 365 etichette e criteri di conservazione per gestire i dati personali nell'Microsoft 365 locale.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928437"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="b9b72-103">Disciplinare le informazioni soggette alla normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="b9b72-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="b9b72-104">I controlli di governance delle informazioni possono essere utilizzati nel proprio ambiente per soddisfare le esigenze di conformità alla privacy dei dati, tra cui un numero specifico del Regolamento generale sulla protezione dei dati (GDPR), HIPAA-HITECH (legge sulla privacy dell'assistenza sanitaria degli Stati Uniti), californiano Consumer Protection Act (CCPA) e il Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="b9b72-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="b9b72-105">Questi controlli rientrano principalmente nelle aree della soluzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9b72-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="b9b72-106">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="b9b72-106">Retention policies</span></span>
- <span data-ttu-id="b9b72-107">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b9b72-107">Retention labels</span></span>
- <span data-ttu-id="b9b72-108">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b9b72-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="b9b72-109">Normative sulla privacy dei dati che influiscono sui controlli di governance delle informazioni</span><span class="sxs-lookup"><span data-stu-id="b9b72-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="b9b72-110">Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="b9b72-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="b9b72-111">Articolo GDPR (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="b9b72-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="b9b72-112">Articolo GDPR (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="b9b72-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="b9b72-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="b9b72-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="b9b72-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="b9b72-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="b9b72-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="b9b72-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="b9b72-116">Articolo LGPD 46</span><span class="sxs-lookup"><span data-stu-id="b9b72-116">LGPD Article 46</span></span>

<span data-ttu-id="b9b72-117">Per ulteriori informazioni su queste normative, vedere l'articolo valutare i rischi per la privacy dei [dati e identificare le informazioni riservate.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="b9b72-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="b9b72-118">Per la governance delle informazioni, le normative sulla privacy dei dati in genere richiedono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b9b72-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="b9b72-119">È consigliabile utilizzare uno schema tecnico per la conservazione e l'eliminazione dei dati personali archiviati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9b72-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="b9b72-120">Se si desidera archiviare i dati personali, informare l'oggetto della durata dell'archiviazione dei dati, una procedura standard ora disponibile nei sistemi Web front-end.</span><span class="sxs-lookup"><span data-stu-id="b9b72-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="b9b72-121">I dati personali devono essere protetti da trattamento, perdita o alterazione accidentali utilizzando metodi verificabili.</span><span class="sxs-lookup"><span data-stu-id="b9b72-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="b9b72-122">Qualsiasi azione eseguita sui dati personali deve essere documentata e tale documentazione deve essere conservata per un periodo specificato.</span><span class="sxs-lookup"><span data-stu-id="b9b72-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="b9b72-123">Poiché le normative sulla privacy dei dati non sono molto specifiche per quanto riguarda la conservazione e l'eliminazione dei dati, è necessario prendere in considerazione altri fattori che potrebbero dettare linee guida sulla governance delle informazioni per le informazioni personali archiviate nella sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9b72-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="b9b72-124">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="b9b72-124">Here are a few examples:</span></span>

- <span data-ttu-id="b9b72-125">Eliminare gli account utente dopo 5 anni di inattività e richiede l'eliminazione o l'anonimizzazione dei dati dell'account dopo tale punto, richiedendo l'orchestrazione tra il sistema che archivia i dati e i flussi di lavoro correlati alle notifiche e ad altre attività di automazione.</span><span class="sxs-lookup"><span data-stu-id="b9b72-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="b9b72-126">Configurazione delle regole per mantenere i criteri e le procedure correlati al GDPR per tre anni dopo che sono state sostituite, in linea con la pianificazione di conservazione dell'organizzazione per i criteri e le procedure.</span><span class="sxs-lookup"><span data-stu-id="b9b72-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="b9b72-127">Mantenere una sottoscrizione separata per comunicare con gli utenti tramite l'organizzazione di supporto.</span><span class="sxs-lookup"><span data-stu-id="b9b72-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="b9b72-128">Tutte le comunicazioni di posta elettronica sono state conservate ed eliminate dopo due settimane per ridurre l'eventuale accumulo di debiti per la privacy nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b9b72-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="b9b72-129">Una domanda chiave a cui rispondere è:</span><span class="sxs-lookup"><span data-stu-id="b9b72-129">A key question to answer is:</span></span> 

- <span data-ttu-id="b9b72-130">Per quanto tempo le informazioni contenenti dati personali devono essere conservate per motivi aziendali validi per evitare pratiche di "conservarlo per sempre"?</span><span class="sxs-lookup"><span data-stu-id="b9b72-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="b9b72-131">Questo deve essere bilanciato con le esigenze di conservazione per la continuità aziendale.</span><span class="sxs-lookup"><span data-stu-id="b9b72-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="b9b72-132">Indipendentemente dalle ragioni legali e aziendali per la conservazione o l'eliminazione delle informazioni personali, Microsoft offre diverse funzionalità per implementare lo schema di governance dei dati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9b72-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="b9b72-133">Gestione della governance delle informazioni in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9b72-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="b9b72-134">Per iniziare, vedere [Manage information governance](../compliance/manage-information-governance.md) and Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="b9b72-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="b9b72-135">Sviluppare pianificazioni di conservazione dei dati per contenitori, posta elettronica e contenuto</span><span class="sxs-lookup"><span data-stu-id="b9b72-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="b9b72-136">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b9b72-136">Keep the following in mind:</span></span>

- <span data-ttu-id="b9b72-137">La definizione di una pianificazione di conservazione dei dati per i tipi di informazioni definiti deve essere considerata un prerequisito per l'implementazione di qualsiasi schema di conservazione o eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b9b72-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="b9b72-138">Dato il numero di tipi di informazioni che la maggior parte delle organizzazioni considera importanti e le pianificazioni di conservazione dei record di grandi dimensioni corrispondenti, l'implementazione di una strategia di conservazione dei dati e gestione dei record richiede la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b9b72-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="b9b72-139">La chiave per stabilire una strategia di governance dei dati efficace di questo tipo è concentrarsi sulle funzioni aziendali e sui tipi di informazioni con priorità più alta che richiedono una gestione più formale.</span><span class="sxs-lookup"><span data-stu-id="b9b72-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="b9b72-140">Alcuni esempi sono i contratti legali, i rendiconti finanziari e la documentazione relativa alla conformità normativa.</span><span class="sxs-lookup"><span data-stu-id="b9b72-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="b9b72-141">Evitare di avere una pianificazione di conservazione separata per ogni singolo tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="b9b72-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="b9b72-142">Provare a utilizzare il più possibile le categorie generali, ad esempio con pianificazioni di conservazione di 7 anni per i contenuti aziendali generali.</span><span class="sxs-lookup"><span data-stu-id="b9b72-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="b9b72-143">Una volta che i tipi di informazioni personali nell'ambiente sono più noti, stabilire pianificazioni di conservazione ed eliminazione per questo tipo di contenuto e modificare l'architettura delle informazioni per semplificare la governance di questo tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="b9b72-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="b9b72-144">Ad esempio, isolare le informazioni personali in siti, raccolte o cartelle separati con accesso controllato.</span><span class="sxs-lookup"><span data-stu-id="b9b72-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="b9b72-145">Criteri di conservazione ed etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b9b72-145">Retention policies and retention labels</span></span>

<span data-ttu-id="b9b72-146">Utilizzare [i criteri di conservazione e le etichette](../compliance/retention.md) di conservazione per conservare o eliminare contenuto in Microsoft 365 che contiene o dovrebbe contenere dati personali.</span><span class="sxs-lookup"><span data-stu-id="b9b72-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="b9b72-147">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b9b72-147">Records management</span></span>

<span data-ttu-id="b9b72-148">Utilizzare le etichette di conservazione che dichiarano il contenuto di un record per implementare una soluzione di gestione [dei record](../compliance/records-management.md) per i dati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9b72-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="b9b72-149">Per la privacy dei dati, le richieste dell'oggetto dei dati (DSR) ricevute dall'ufficio legale sono dichiarate un record e possono essere archiviate a tempo indeterminato o smaltite con la prova, per rispettare le specifiche di conservazione delle attività normative.</span><span class="sxs-lookup"><span data-stu-id="b9b72-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>