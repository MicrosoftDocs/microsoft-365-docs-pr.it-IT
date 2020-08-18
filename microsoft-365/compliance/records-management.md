---
title: Gestione dei record
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la gestione dei record di Microsoft 365, è possibile applicare le pianificazioni di conservazione in un piano di archiviazione che gestisce la conservazione, la dichiarazione dei record e l’eliminazione.
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778324"
---
# <a name="learn-about-records-management"></a><span data-ttu-id="02edb-103">Informazioni sulla gestione dei record</span><span class="sxs-lookup"><span data-stu-id="02edb-103">Learn about records management</span></span>

><span data-ttu-id="02edb-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="02edb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="02edb-105">Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="02edb-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="02edb-106">La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.</span><span class="sxs-lookup"><span data-stu-id="02edb-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="02edb-107">Usa le funzionalità seguenti per supportare la soluzione di gestione dei record in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="02edb-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="02edb-108">**Etichettare il contenuto come record**.</span><span class="sxs-lookup"><span data-stu-id="02edb-108">**Label content as a record**.</span></span> <span data-ttu-id="02edb-109">Creare e configurare etichette di conservazione per contrassegnare il contenuto come [record](#records), che possono essere applicate dagli utenti o applicate automaticamente identificando informazioni, parole chiave o tipi di contenuto sensibile.</span><span class="sxs-lookup"><span data-stu-id="02edb-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="02edb-110">**Eseguire la migrazione e gestire i requisiti di conservazione con il piano di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="02edb-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="02edb-111">Con un [piano di archiviazione](file-plan-manager.md) è possibile inserire un piano di conservazione esistente in Microsoft 365 oppure crearne uno nuovo per funzionalità di gestione avanzate.</span><span class="sxs-lookup"><span data-stu-id="02edb-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="02edb-112">**Configurare le impostazioni di conservazione ed eliminazione con etichetta di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="02edb-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="02edb-113">Configurare [etichette di conservazione](retention.md#retention-labels) con i periodi e le azioni di conservazione in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.</span><span class="sxs-lookup"><span data-stu-id="02edb-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="02edb-114">**Avviare periodi di conservazione diversi quando si verifica un evento** con la[conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="02edb-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="02edb-115">\*\*Rivedere e convalidare l'eliminazione \*\* con la [revisione per l'eliminazione](disposition.md#disposition-reviews) e la prova dell'[eliminazione dei record](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="02edb-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="02edb-116">**Esportare le informazioni riguardanti tutti gli elementi eliminati** con l'[opzione di esportazione](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="02edb-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="02edb-117">**Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="02edb-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="02edb-118">Utilizzando queste funzionalità, è possibile incorporare le pianificazioni e i requisiti di conservazione dell'organizzazione in una soluzione di gestione dei record che gestisce la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.</span><span class="sxs-lookup"><span data-stu-id="02edb-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="02edb-119">Oltre alla documentazione online, potreebbe essere utile l’ascolto della [registrazione del webinar](https://aka.ms/MIPC/Video-RecordsManagementWebinar) per la gestione dei record oltre a scaricare la [raccolta correlata con le domande frequenti](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span><span class="sxs-lookup"><span data-stu-id="02edb-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="02edb-120">Record</span><span class="sxs-lookup"><span data-stu-id="02edb-120">Records</span></span>

<span data-ttu-id="02edb-121">Quando un contenuto viene contrassegnato come record:</span><span class="sxs-lookup"><span data-stu-id="02edb-121">When content is marked as a record:</span></span>

- <span data-ttu-id="02edb-122">Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="02edb-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="02edb-123">Vengono registrate altre attività relative all'elemento.</span><span class="sxs-lookup"><span data-stu-id="02edb-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="02edb-124">Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="02edb-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="02edb-125">Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="02edb-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="02edb-126">È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.</span><span class="sxs-lookup"><span data-stu-id="02edb-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="02edb-127">Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02edb-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="02edb-128">Confronto tra le restrizioni relative alle azioni consentite o bloccate</span><span class="sxs-lookup"><span data-stu-id="02edb-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="02edb-129">Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="02edb-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="02edb-130">Un'etichetta di conservazione standard include le impostazioni di conservazione e le azioni, ma non contrassegna il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="02edb-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="02edb-131">Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange.</span><span class="sxs-lookup"><span data-stu-id="02edb-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="02edb-132">Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](record-versioning.md), che non è supportato per gli elementi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="02edb-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="02edb-133">Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.</span><span class="sxs-lookup"><span data-stu-id="02edb-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="02edb-134">Azione</span><span class="sxs-lookup"><span data-stu-id="02edb-134">Action</span></span>| <span data-ttu-id="02edb-135">Etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="02edb-135">Retention label</span></span> |<span data-ttu-id="02edb-136">Record: bloccato</span><span class="sxs-lookup"><span data-stu-id="02edb-136">Record - locked</span></span>| <span data-ttu-id="02edb-137">Record: sbloccato</span><span class="sxs-lookup"><span data-stu-id="02edb-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="02edb-138">Modifica contenuti</span><span class="sxs-lookup"><span data-stu-id="02edb-138">Edit contents</span></span>|<span data-ttu-id="02edb-139">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-139">Allowed</span></span> | <span data-ttu-id="02edb-140">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="02edb-140">**Blocked**</span></span> | <span data-ttu-id="02edb-141">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-141">Allowed</span></span>|
|<span data-ttu-id="02edb-142">Modifica le proprietà, tra cui Rinomina</span><span class="sxs-lookup"><span data-stu-id="02edb-142">Edit properties, including rename</span></span>|<span data-ttu-id="02edb-143">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-143">Allowed</span></span> |<span data-ttu-id="02edb-144">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-144">Allowed</span></span> | <span data-ttu-id="02edb-145">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-145">Allowed</span></span>|
|<span data-ttu-id="02edb-146">Elimina</span><span class="sxs-lookup"><span data-stu-id="02edb-146">Delete</span></span>|<span data-ttu-id="02edb-147">Consentito <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="02edb-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="02edb-148">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="02edb-148">**Blocked**</span></span> | <span data-ttu-id="02edb-149">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="02edb-149">**Blocked**</span></span>|
|<span data-ttu-id="02edb-150">Copia</span><span class="sxs-lookup"><span data-stu-id="02edb-150">Copy</span></span>|<span data-ttu-id="02edb-151">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-151">Allowed</span></span> |<span data-ttu-id="02edb-152">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-152">Allowed</span></span> | <span data-ttu-id="02edb-153">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-153">Allowed</span></span>|
|<span data-ttu-id="02edb-154">Sposta all'interno del container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="02edb-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="02edb-155">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-155">Allowed</span></span> |<span data-ttu-id="02edb-156">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-156">Allowed</span></span> | <span data-ttu-id="02edb-157">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-157">Allowed</span></span>|
|<span data-ttu-id="02edb-158">Sposta tra container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="02edb-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="02edb-159">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-159">Allowed</span></span> |<span data-ttu-id="02edb-160">Consentito se mai sbloccato</span><span class="sxs-lookup"><span data-stu-id="02edb-160">Allowed if never unlocked</span></span> | <span data-ttu-id="02edb-161">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-161">Allowed</span></span>|
|<span data-ttu-id="02edb-162">Apri/leggi</span><span class="sxs-lookup"><span data-stu-id="02edb-162">Open/Read</span></span>|<span data-ttu-id="02edb-163">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-163">Allowed</span></span> |<span data-ttu-id="02edb-164">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-164">Allowed</span></span> | <span data-ttu-id="02edb-165">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-165">Allowed</span></span>|
|<span data-ttu-id="02edb-166">Cambia etichetta</span><span class="sxs-lookup"><span data-stu-id="02edb-166">Change label</span></span>|<span data-ttu-id="02edb-167">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-167">Allowed</span></span> |<span data-ttu-id="02edb-168">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="02edb-168">Allowed - container admin only</span></span> | <span data-ttu-id="02edb-169">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="02edb-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="02edb-170">Rimuovi etichetta</span><span class="sxs-lookup"><span data-stu-id="02edb-170">Remove label</span></span>|<span data-ttu-id="02edb-171">Consentito</span><span class="sxs-lookup"><span data-stu-id="02edb-171">Allowed</span></span> |<span data-ttu-id="02edb-172">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="02edb-172">Allowed - container admin only</span></span> | <span data-ttu-id="02edb-173">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="02edb-173">Allowed - container admin only</span></span>|

<span data-ttu-id="02edb-174">Note a piè di pagina:</span><span class="sxs-lookup"><span data-stu-id="02edb-174">Footnotes:</span></span>

<span data-ttu-id="02edb-175"><sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02edb-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="02edb-176">Messaggio che un utente vede se tenta di eliminare un documento con etichetta in SharePoint:</span><span class="sxs-lookup"><span data-stu-id="02edb-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="02edb-178"><sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.</span><span class="sxs-lookup"><span data-stu-id="02edb-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="02edb-179">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="02edb-179">Next steps</span></span>

<span data-ttu-id="02edb-180">Vedere [Introduzione alla gestione dei record](get-started-with-records-management.md).</span><span class="sxs-lookup"><span data-stu-id="02edb-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="02edb-181">Per contrassegnare i contenuti come record, vedere [Dichiarare un elemento come record tramite le etichette di conservazione](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="02edb-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
