---
title: Informazioni sui record
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui record utili per implementare una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685442"
---
# <a name="learn-about-records"></a><span data-ttu-id="7859a-103">Informazioni sui record</span><span class="sxs-lookup"><span data-stu-id="7859a-103">Learn about records</span></span>

><span data-ttu-id="7859a-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7859a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7859a-105">La gestione dei record in Microsoft 365 consente alle organizzazioni di conformarsi alle politiche aziendali e agli obblighi legali o normativi, riducendo inoltre i rischi e le responsabilità legali.</span><span class="sxs-lookup"><span data-stu-id="7859a-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="7859a-106">Quando un contenuto viene contrassegnato come record:</span><span class="sxs-lookup"><span data-stu-id="7859a-106">When content is marked as a record:</span></span>

- <span data-ttu-id="7859a-107">Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="7859a-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="7859a-108">Vengono registrate altre attività relative all'elemento.</span><span class="sxs-lookup"><span data-stu-id="7859a-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="7859a-109">Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7859a-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="7859a-110">Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="7859a-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="7859a-111">È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.</span><span class="sxs-lookup"><span data-stu-id="7859a-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="7859a-112">Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7859a-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="7859a-113">Confronto tra le restrizioni relative alle azioni consentite o bloccate</span><span class="sxs-lookup"><span data-stu-id="7859a-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="7859a-114">Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="7859a-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="7859a-115">Un'etichetta di conservazione standard include la configurazione per mantenere i dati senza contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="7859a-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="7859a-116">Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange.</span><span class="sxs-lookup"><span data-stu-id="7859a-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="7859a-117">Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](record-versioning.md), che non è supportato per gli elementi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7859a-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="7859a-118">Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.</span><span class="sxs-lookup"><span data-stu-id="7859a-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="7859a-119">Azione</span><span class="sxs-lookup"><span data-stu-id="7859a-119">Action</span></span>| <span data-ttu-id="7859a-120">Etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="7859a-120">Retention label</span></span> |<span data-ttu-id="7859a-121">Record: bloccato</span><span class="sxs-lookup"><span data-stu-id="7859a-121">Record - locked</span></span>| <span data-ttu-id="7859a-122">Record: sbloccato</span><span class="sxs-lookup"><span data-stu-id="7859a-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7859a-123">Modifica contenuti</span><span class="sxs-lookup"><span data-stu-id="7859a-123">Edit contents</span></span>|<span data-ttu-id="7859a-124">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-124">Allowed</span></span> | <span data-ttu-id="7859a-125">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="7859a-125">**Blocked**</span></span> | <span data-ttu-id="7859a-126">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-126">Allowed</span></span>|
|<span data-ttu-id="7859a-127">Modifica le proprietà, tra cui Rinomina</span><span class="sxs-lookup"><span data-stu-id="7859a-127">Edit properties, including rename</span></span>|<span data-ttu-id="7859a-128">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-128">Allowed</span></span> |<span data-ttu-id="7859a-129">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-129">Allowed</span></span> | <span data-ttu-id="7859a-130">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-130">Allowed</span></span>|
|<span data-ttu-id="7859a-131">Elimina</span><span class="sxs-lookup"><span data-stu-id="7859a-131">Delete</span></span>|<span data-ttu-id="7859a-132">Consentito <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7859a-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="7859a-133">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="7859a-133">**Blocked**</span></span> | <span data-ttu-id="7859a-134">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="7859a-134">**Blocked**</span></span>|
|<span data-ttu-id="7859a-135">Copia</span><span class="sxs-lookup"><span data-stu-id="7859a-135">Copy</span></span>|<span data-ttu-id="7859a-136">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-136">Allowed</span></span> |<span data-ttu-id="7859a-137">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-137">Allowed</span></span> | <span data-ttu-id="7859a-138">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-138">Allowed</span></span>|
|<span data-ttu-id="7859a-139">Sposta all'interno del container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7859a-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="7859a-140">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-140">Allowed</span></span> |<span data-ttu-id="7859a-141">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-141">Allowed</span></span> | <span data-ttu-id="7859a-142">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-142">Allowed</span></span>|
|<span data-ttu-id="7859a-143">Sposta tra container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7859a-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="7859a-144">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-144">Allowed</span></span> |<span data-ttu-id="7859a-145">Consentito se mai sbloccato</span><span class="sxs-lookup"><span data-stu-id="7859a-145">Allowed if never unlocked</span></span> | <span data-ttu-id="7859a-146">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-146">Allowed</span></span>|
|<span data-ttu-id="7859a-147">Apri/leggi</span><span class="sxs-lookup"><span data-stu-id="7859a-147">Open/Read</span></span>|<span data-ttu-id="7859a-148">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-148">Allowed</span></span> |<span data-ttu-id="7859a-149">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-149">Allowed</span></span> | <span data-ttu-id="7859a-150">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-150">Allowed</span></span>|
|<span data-ttu-id="7859a-151">Cambia etichetta</span><span class="sxs-lookup"><span data-stu-id="7859a-151">Change label</span></span>|<span data-ttu-id="7859a-152">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-152">Allowed</span></span> |<span data-ttu-id="7859a-153">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="7859a-153">Allowed - container admin only</span></span> | <span data-ttu-id="7859a-154">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="7859a-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="7859a-155">Rimuovi etichetta</span><span class="sxs-lookup"><span data-stu-id="7859a-155">Remove label</span></span>|<span data-ttu-id="7859a-156">Consentito</span><span class="sxs-lookup"><span data-stu-id="7859a-156">Allowed</span></span> |<span data-ttu-id="7859a-157">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="7859a-157">Allowed - container admin only</span></span> | <span data-ttu-id="7859a-158">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="7859a-158">Allowed - container admin only</span></span>|

<span data-ttu-id="7859a-159">Note a piè di pagina:</span><span class="sxs-lookup"><span data-stu-id="7859a-159">Footnotes:</span></span>

<span data-ttu-id="7859a-160"><sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7859a-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="7859a-161">Messaggio che un utente vede se tenta di eliminare un documento con etichetta in SharePoint:</span><span class="sxs-lookup"><span data-stu-id="7859a-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="7859a-163"><sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.</span><span class="sxs-lookup"><span data-stu-id="7859a-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7859a-164">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7859a-164">Next steps</span></span>

<span data-ttu-id="7859a-165">Se non si hanno ancora etichette di conservazione da usare per la gestione dei record, vedere [Introduzione ai criteri e alle etichette di conservazione](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="7859a-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="7859a-166">Per contrassegnare i contenuti come record, vedere [Dichiarare un elemento come record tramite le etichette di conservazione](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="7859a-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
