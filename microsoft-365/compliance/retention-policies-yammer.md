---
title: Informazioni sulla conservazione per Yammer
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
description: Informazioni sui criteri di conservazione applicabili a Yammer.
ms.openlocfilehash: 3e4cfd5c9e5ef8c28ecd069f3474764b966d6c9a
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795001"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="3e248-103">Informazioni sulla conservazione per Yammer</span><span class="sxs-lookup"><span data-stu-id="3e248-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="3e248-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3e248-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3e248-105">Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per Yammer.</span><span class="sxs-lookup"><span data-stu-id="3e248-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="3e248-106">Per altri carichi di lavoro, vedere:</span><span class="sxs-lookup"><span data-stu-id="3e248-106">For other workloads, see:</span></span>

- [<span data-ttu-id="3e248-107">Informazioni sulla conservazione per SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="3e248-107">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="3e248-108">Informazioni sulla conservazione per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e248-108">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="3e248-109">Informazioni sulla conservazione per Exchange</span><span class="sxs-lookup"><span data-stu-id="3e248-109">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="3e248-110">Cosa è incluso per la conservazione e l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="3e248-110">What's included for retention and deletion</span></span>

<span data-ttu-id="3e248-111">Usando i criteri di conservazione per Yammer è possibile conservare ed eliminare gli elementi di Yammer seguenti: messaggi della community e messaggi privati.</span><span class="sxs-lookup"><span data-stu-id="3e248-111">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="3e248-112">Le reazioni degli altri utenti sotto forma di emoticon non sono incluse in questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="3e248-112">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="3e248-113">Funzionamento della conservazione per Yammer</span><span class="sxs-lookup"><span data-stu-id="3e248-113">How retention works with Yammer</span></span>

<span data-ttu-id="3e248-114">È possibile usare i criteri di conservazione per conservare ed eliminare i messaggi della community e i messaggi privati di Yammer.</span><span class="sxs-lookup"><span data-stu-id="3e248-114">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="3e248-115">I messaggi privati sono archiviati in una cartella nascosta all'interno della cassetta postale di ogni utente incluso nel messaggio, e i messaggi della community sono archiviati in un'analoga cartella nascosta all'interno della cassetta postale di gruppo della community.</span><span class="sxs-lookup"><span data-stu-id="3e248-115">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="3e248-116">I messaggi di Yammer non sono interessati dai criteri di conservazione configurati per le cassette postali di utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="3e248-116">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="3e248-117">Benché i messaggi di Yammer siano archiviati in Exchange, questi dati di Yammer vengono inclusi solo da un criterio di conservazione configurato per le posizioni **Messaggi della community di Yammer** e **Messaggi privati di Yammer** .</span><span class="sxs-lookup"><span data-stu-id="3e248-117">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="3e248-118">Se un utente è incluso in un criterio di conservazione attivo che conserva i dati di Yammer e si eliminata una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Yammer la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3e248-118">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="3e248-119">Se non è necessario conservare i dati di Yammer per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3e248-119">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="3e248-120">Dopo che i criteri di conservazione sono stati configurati per messaggi di Yammer, un processo timer del servizio Exchange valuterà periodicamente gli elementi nella cartella nascosta in cui vengono archiviati i messaggi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="3e248-120">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="3e248-121">Il processo timer richiede fino a sette giorni per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3e248-121">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="3e248-122">Quando il periodo di conservazione degli elementi scade, questi vengono spostati nella cartella SubstrateHolds, una cartella nascosta presente in ogni cassetta postale utente o di gruppo in cui vengono archiviati gli elementi "eliminati temporaneamente" prima che vengano eliminati definitivamente.</span><span class="sxs-lookup"><span data-stu-id="3e248-122">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="3e248-123">Dopo la configurazione di un criterio di conservazione per i messaggi di Yammer, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia impostato per conservare e poi eliminare, conservare solo o eliminare solo.</span><span class="sxs-lookup"><span data-stu-id="3e248-123">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="3e248-124">Se il criterio di conservazione conserva e poi elimina:</span><span class="sxs-lookup"><span data-stu-id="3e248-124">When the retention policy is to retain and then delete:</span></span>

![Diagramma del flusso di conservazione dei messaggi di Yammer](../media/yammerretentionlifecycle.png)

<span data-ttu-id="3e248-126">Per i due percorsi nel diagramma:</span><span class="sxs-lookup"><span data-stu-id="3e248-126">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="3e248-127">**Se un messaggio di Yammer viene modificato o eliminato** dall’utente durante il periodo di conservazione, il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) nella cartella SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="3e248-127">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="3e248-128">Il messaggio viene archiviato in questa posizione fino alla scadenza del periodo di conservazione, quindi viene eliminato immediatamente in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="3e248-128">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="3e248-129">**Se il messaggio di Yammer non viene eliminato** , così come per i messaggi correnti dopo essere stati modificati, il messaggio viene spostato nella cartella SubstrateHolds alla scadenza del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="3e248-129">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="3e248-130">Questa azione richiede fino a sette giorni dalla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="3e248-130">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="3e248-131">Dopo che il messaggio è stato spostato nella cartella SubstrateHolds, viene eliminato immediatamente in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="3e248-131">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="3e248-132">I messaggi nella cartella SubstrateHolds sono disponibili per la ricerca tramite gli strumenti di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3e248-132">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="3e248-133">Finché i messaggi non vengono eliminati definitivamente (nella cartella SubstrateHolds), rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3e248-133">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="3e248-134">Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed Elimina.</span><span class="sxs-lookup"><span data-stu-id="3e248-134">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="3e248-135">Percorsi di contenuto per il criterio di conservazione Conserva solo</span><span class="sxs-lookup"><span data-stu-id="3e248-135">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="3e248-136">**Se un messaggio di Yammer viene modificato o eliminato** : una copia del messaggio originale viene creata nella cartella SubstrateHolds e conservata in tale posizione fino alla scadenza del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="3e248-136">**If a Yammer message is edited or deleted** : A copy of the original message is created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="3e248-137">Quindi il messaggio viene eliminato immediatamente in modo definitivo dalla cartella SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="3e248-137">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="3e248-138">**Se il messaggio di Yammer non viene modificato o eliminato** , così come per i messaggi correnti dopo essere stati modificati durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L'elemento rimane nella posizione originale.</span><span class="sxs-lookup"><span data-stu-id="3e248-138">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="3e248-139">Percorsi di contenuto per il criterio di conservazione Elimina solo</span><span class="sxs-lookup"><span data-stu-id="3e248-139">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="3e248-140">**Se il messaggio di Yammer non viene eliminato** durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="3e248-140">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="3e248-141">Questa azione richiede fino a sette giorni dalla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="3e248-141">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="3e248-142">Quindi il messaggio viene eliminato immediatamente in modo definitivo dalla cartella SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="3e248-142">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="3e248-143">**Se il messaggio di Yammer viene eliminato dall'utente** durante il periodo, verrà spostato nella cartella SubstrateHolds da dove verrà immediatamente eliminato in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="3e248-143">**If the Yammer message is deleted by the user** during the period, the item is moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="3e248-144">Messaggi e utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3e248-144">Messages and external users</span></span>

<span data-ttu-id="3e248-145">Per impostazione predefinita, i criteri di conservazione dei messaggi privati di Yammer si applicano a tutti gli utenti dell'organizzazione, ma non agli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="3e248-145">By default, a retention policy for Yammer private messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="3e248-146">Si può applicare un'etichetta di conservazione a utenti esterni selezionando **Scegli utente** e specificando il loro account.</span><span class="sxs-lookup"><span data-stu-id="3e248-146">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="3e248-147">Al momento, gli utenti guest di Azure B2B non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3e248-147">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="3e248-148">Quando un utente abbandona l’organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e248-148">When a user leaves the organization</span></span> 

<span data-ttu-id="3e248-149">Se un utente lascia l’organizzazione e il suo account di Microsoft 365 viene eliminato, i suoi messaggi di Yammer soggetti alla conservazione vengono archiviati in una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="3e248-149">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="3e248-150">I messaggi restano sottoposti ai criteri di conservazione applicati all’utente prima della disattivazione della sua cassetta postale, e sono disponibili per la ricerca eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3e248-150">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="3e248-151">Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3e248-151">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="3e248-152">Se l’utente ha archiviato dei file in Yammer, vedere la [sezione corrispondente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e248-152">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="3e248-153">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="3e248-153">Limitations</span></span>

<span data-ttu-id="3e248-154">I criteri di conservazione di Yammer sono attualmente in anteprima, e stiamo lavorando continuamente all'ottimizzazione della funzionalità di conservazione.</span><span class="sxs-lookup"><span data-stu-id="3e248-154">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="3e248-155">Nel frattempo, notare le limitazioni seguenti quando si usa la conservazione per i messaggi della community e i messaggi privati di Yammer:</span><span class="sxs-lookup"><span data-stu-id="3e248-155">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="3e248-156">Quando si seleziona **Scegli utenti** per la posizione **Messaggi privati di Yammer** , potrebbero essere visualizzati utenti non della cassetta postale e guest.</span><span class="sxs-lookup"><span data-stu-id="3e248-156">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="3e248-157">I criteri di conservazione non sono pensati per questi utenti, quindi non selezionarli.</span><span class="sxs-lookup"><span data-stu-id="3e248-157">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="3e248-158">Linee guida per la configurazione</span><span class="sxs-lookup"><span data-stu-id="3e248-158">Configuration guidance</span></span>

<span data-ttu-id="3e248-159">Se si configura per la prima volta la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3e248-159">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="3e248-160">Se si è pronti per configurare un criterio di conservazione per Yammer, vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3e248-160">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>
