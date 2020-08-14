---
title: Pianificare la governance dell'organizzazione e del ciclo di vita per gruppi Microsoft 365 e Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opzioni di Lean sulla governance del ciclo di vita per gli strumenti di collaborazione in Microsoft 365
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662677"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="d9916-103">Pianificare la governance dell'organizzazione e del ciclo di vita per gruppi Microsoft 365 e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d9916-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="d9916-104">I gruppi di Microsoft 365 dispongono di un set completo di strumenti per implementare le funzionalità di governance richieste dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9916-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="d9916-105">Nella sezione seguente vengono descritte le funzionalità, vengono consigliate le procedure consigliate e vengono fornite indicazioni per porre le domande giuste per determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="d9916-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="d9916-106">Controllare chi può creare gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9916-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="d9916-107">I gruppi possono essere creati dagli utenti finali provenienti da più punti finali, tra cui Outlook, SharePoint, teams e altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="d9916-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![immagine DESC](../media/04.png)

<span data-ttu-id="d9916-109">Si consiglia vivamente self-service per consentire ai proprietari del gruppo di aiutare gli utenti a svolgere il proprio lavoro in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="d9916-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="d9916-110">La limitazione della creazione di gruppi e team può rallentare la produttività degli utenti perché molti servizi Microsoft 365 richiedono la creazione di gruppi per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d9916-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="d9916-111">Si consideri le opzioni di governance seguenti per la creazione dei gruppi:</span><span class="sxs-lookup"><span data-stu-id="d9916-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="d9916-112">Per limitare l'espansione del gruppo, utilizzare i [criteri di scadenza dei gruppi](microsoft-365-groups-expiration-policy.md) per eliminare automaticamente i gruppi che non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="d9916-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="d9916-113">Limitare la creazione di gruppi ai membri di un gruppo di [sicurezza con appartenenza dinamica](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) contenente, ad esempio, tutti i dipendenti a tempo pieno.</span><span class="sxs-lookup"><span data-stu-id="d9916-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="d9916-114">Limitare la creazione di gruppi a un gruppo di sicurezza e richiedere agli utenti di completare l'addestramento nei criteri di utilizzo dei gruppi dell'organizzazione per diventare membri del gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d9916-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="d9916-115">Se si desidera limitare gli utenti che possono creare i gruppi, vedere [gestire gli utenti autorizzati a creare i gruppi di Microsoft 365](manage-creation-of-groups.md) per informazioni su come configurarlo.</span><span class="sxs-lookup"><span data-stu-id="d9916-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="d9916-116">Eliminazione, ripristino e archiviazione di gruppi</span><span class="sxs-lookup"><span data-stu-id="d9916-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="d9916-117">Quando un gruppo di Microsoft 365 viene eliminato, per impostazione predefinita viene conservato per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d9916-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="d9916-118">Questo periodo di 30 giorni è definito di "eliminazione temporanea", perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="d9916-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d9916-119">Dopo 30 giorni, il gruppo e i contenuti associati vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="d9916-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d9916-120">Se si dispone di criteri di conservazione sul posto per mantenere la chat, i file o la posta, tali elementi verranno mantenuti dopo l'eliminazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="d9916-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="d9916-121">Per informazioni dettagliate, vedere informazioni [sui criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .</span><span class="sxs-lookup"><span data-stu-id="d9916-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="d9916-122">Se si desidera eliminare un gruppo, ma conservare il contenuto di uno o più servizi connessi a un gruppo, vedere [Archive groups, teams e Yammer](end-life-cycle-groups-teams-sites-yammer.md) for Information.</span><span class="sxs-lookup"><span data-stu-id="d9916-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="d9916-123">Criteri di denominazione dei gruppi</span><span class="sxs-lookup"><span data-stu-id="d9916-123">Group naming policy</span></span>

<span data-ttu-id="d9916-124">I criteri di denominazione dei gruppi consentono di gestire i gruppi in due modi:</span><span class="sxs-lookup"><span data-stu-id="d9916-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="d9916-125">È possibile utilizzare i criteri di denominazione prefisso/suffisso per applicare stringhe fisse o attributi di Azure AD all'inizio o alla fine del nome di un gruppo e dell'indirizzo di posta elettronica associato.</span><span class="sxs-lookup"><span data-stu-id="d9916-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="d9916-126">In questo modo, è possibile garantire l'inclusione, ad esempio, di nomi di reparto o aree geografiche nei nomi dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="d9916-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="d9916-127">Un criterio di parole bloccate può garantire che alcune parole, ad esempio i nomi dei dirigenti, non vengano utilizzate nei nomi di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d9916-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="d9916-128">I criteri di denominazione vengono applicati quando i gruppi vengono creati da tutti i servizi connessi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="d9916-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="d9916-129">Se si decide di utilizzare i criteri di denominazione per i gruppi, vedere [criteri di denominazione dei gruppi Microsoft 365](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d9916-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="d9916-130">Criteri di scadenza del gruppo</span><span class="sxs-lookup"><span data-stu-id="d9916-130">Group expiration policy</span></span>

<span data-ttu-id="d9916-131">È possibile specificare un periodo di scadenza e qualsiasi gruppo che raggiunge la fine di quel periodo e non viene rinnovato, verrà eliminato.</span><span class="sxs-lookup"><span data-stu-id="d9916-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="d9916-132">Il periodo di scadenza inizia quando viene creato il gruppo oppure alla data in cui è stato rinnovato per ultimo.</span><span class="sxs-lookup"><span data-stu-id="d9916-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="d9916-133">Dopo aver impostato i gruppi in modo che scadano:</span><span class="sxs-lookup"><span data-stu-id="d9916-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="d9916-134">I proprietari del gruppo ricevono una notifica per il rinnovo del gruppo come scadenza vicinanze.</span><span class="sxs-lookup"><span data-stu-id="d9916-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="d9916-135">I gruppi attivi vengono rinnovati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d9916-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="d9916-136">Qualsiasi gruppo che non è stato rinnovato viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="d9916-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="d9916-137">Qualsiasi gruppo eliminato può essere ripristinato entro 30 giorni dai proprietari del gruppo o dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="d9916-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="d9916-138">I criteri di scadenza rappresentano un ottimo metodo per limitare l'espansione del gruppo, garantendo che i gruppi che non sono più in uso vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="d9916-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="d9916-139">Se si desidera creare un criterio di scadenza del gruppo, vedere [criteri di scadenza del gruppo Microsoft 365](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d9916-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
