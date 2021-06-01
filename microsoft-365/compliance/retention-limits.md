---
title: Limiti per i criteri di conservazione e i criteri per le etichette di conservazione
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Comprendere il numero massimo di criteri ed elementi per criterio in relazione ai criteri di conservazione e ai criteri per le etichette di conservazione
ms.openlocfilehash: 1ee2d07a42aaf4dff45ae22e9dfc005b3c4593d9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698965"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="62e1f-103">Limiti per i criteri di conservazione e i criteri per le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="62e1f-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="62e1f-104">*[Indicazioni per la sicurezza e conformità dell'assegnazione di licenze Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="62e1f-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="62e1f-105">Quando si utilizzano [criteri di conservazione e criteri per le etichette di conservazione](retention.md#retention-policies-and-retention-labels) per conservare o eliminare automaticamente i dati dell’organizzazione, vi sono alcuni limiti massimi da tenere in considerazione.</span><span class="sxs-lookup"><span data-stu-id="62e1f-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="62e1f-106">Numero massimo di criteri nel tenant</span><span class="sxs-lookup"><span data-stu-id="62e1f-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="62e1f-107">Un tenant singolo può avere al massimo 10.000 criteri (con qualsiasi configurazione). </span><span class="sxs-lookup"><span data-stu-id="62e1f-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="62e1f-108">Il numero massimo include i diversi criteri per la conservazione e altri criteri per la conformità, come i criteri per prevenzione della perdita dei dati, barriere informative, blocchi di eDiscovery ed etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="62e1f-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="62e1f-109">Nel limite di 10.000 criteri, sono presente anche alcuni limiti al numero massimo di criteri di conservazione per carico di lavoro:</span><span class="sxs-lookup"><span data-stu-id="62e1f-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="62e1f-110">Exchange Online (con qualsiasi configurazione): 1.800</span><span class="sxs-lookup"><span data-stu-id="62e1f-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="62e1f-111">SharePoint o OneDrive (tutti i siti inclusi automaticamente): 13</span><span class="sxs-lookup"><span data-stu-id="62e1f-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="62e1f-112">SharePoint o OneDrive (specifici percorsi inclusi o esclusi): 2.600</span><span class="sxs-lookup"><span data-stu-id="62e1f-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="62e1f-113">Sebbene i criteri di conservazione per Microsoft Teams e Yammer usino le cassette postali per archiviare i dati a scopo di conservazione, il numero massimo di criteri per Exchange Online esclude i criteri di conservazione per Teams e Yammer.</span><span class="sxs-lookup"><span data-stu-id="62e1f-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="62e1f-114">Numero massimo di elementi per criterio</span><span class="sxs-lookup"><span data-stu-id="62e1f-114">Maximum number of items per policy</span></span>

<span data-ttu-id="62e1f-115">Se si utilizza la configurazione facoltativa per restringere l'ambito delle impostazioni di conservazione a utenti specifici, gruppi di Microsoft 365 specifici o siti specifici, vi sono alcuni limiti per ciascun criterio da tenere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="62e1f-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="62e1f-116">Numero massimo di elementi per criterio di conservazione:</span><span class="sxs-lookup"><span data-stu-id="62e1f-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="62e1f-117">1.000 cassette postali (degli utenti o di gruppo)</span><span class="sxs-lookup"><span data-stu-id="62e1f-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="62e1f-118">1.000 gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62e1f-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="62e1f-119">1.000 utenti per le chat private di Teams</span><span class="sxs-lookup"><span data-stu-id="62e1f-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="62e1f-120">100 siti (OneDrive o SharePoint)</span><span class="sxs-lookup"><span data-stu-id="62e1f-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="62e1f-121">Poiché queste limitazioni sono stabilite per criterio, se è necessario usare specifiche inclusioni o esclusioni che determinano un superamento di tali limiti, è possibile creare altri criteri con le stesse impostazioni di conservazione.</span><span class="sxs-lookup"><span data-stu-id="62e1f-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="62e1f-122">Vedere la sezione successiva per alcuni[scenari e soluzioni di esempio](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) che usano più criteri di conservazione per tale ragione.</span><span class="sxs-lookup"><span data-stu-id="62e1f-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="62e1f-123">Tuttavia, l’uso di più criteri determina costi amministrativi superiori, perciò occorre verificare sempre se le inclusioni e le esclusioni siano davvero necessarie.</span><span class="sxs-lookup"><span data-stu-id="62e1f-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="62e1f-124">Tenere presente che la configurazione predefinita che si applica all'intero percorso non ha alcuna limitazione, e che questa configurazione potrebbe essere una soluzione migliore rispetto alla creazione e alla gestione di più criteri.</span><span class="sxs-lookup"><span data-stu-id="62e1f-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="62e1f-125">Se è necessario creare e gestire più criteri per questo scenario, si consiglia di usare di usare [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) per una configurazione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="62e1f-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="62e1f-126">Esempi di utilizzo di più criteri per evitare il superamento dei limiti massimi</span><span class="sxs-lookup"><span data-stu-id="62e1f-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="62e1f-127">Gli esempi seguenti forniscono alcune soluzioni per i casi in cui non è possibile specificare semplicemente il percorso di un criterio di conservazione ed è necessario tenere in considerazione il numero massimo di elementi indicato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="62e1f-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="62e1f-128">Esempio di Exchange:</span><span class="sxs-lookup"><span data-stu-id="62e1f-128">Exchange example:</span></span>

- <span data-ttu-id="62e1f-129">**Requisito**: in una organizzazione che ha più di 40.000 cassette postali degli utenti, la posta elettronica deve essere conservata per sette anni per gran parte degli utenti, ma un sottoinsieme di utenti identificati (425) deve conservare la posta elettronica solo per 5 anni. </span><span class="sxs-lookup"><span data-stu-id="62e1f-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="62e1f-130">**Soluzione**: creare un criterio di conservazione per la posta elettronica di Exchange con un periodo di conservazione di sette anni, ed escludere il sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="62e1f-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="62e1f-131">Creare poi un secondo criterio di conservazione per la posta elettronica di Exchange, con un periodo di conservazione di cinque anni, e includere il sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="62e1f-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="62e1f-132">In entrambi casi, il numero incluso ed escluso è inferiore a un numero massimo di cassette postali specificate per un singolo criterio, e il sottoinsieme di utenti deve essere escluso esplicitamente dalla primo criterio perché ha [periodo di conservazione più lungo](retention.md#the-principles-of-retention-or-what-takes-precedence) del secondo criterio.</span><span class="sxs-lookup"><span data-stu-id="62e1f-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="62e1f-133">Se il sottoinsieme di utenti richiede un periodo di conservazione più lungo, non è necessario escluderli dal primo criterio.</span><span class="sxs-lookup"><span data-stu-id="62e1f-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="62e1f-134">Con questa soluzione, se un nuovo dipendente entra nell'organizzazione, la sua cassetta postale viene automaticamente inclusa nel primo criterio per sette anni, e non ci sono conseguenze per il numero massimo supportato.</span><span class="sxs-lookup"><span data-stu-id="62e1f-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="62e1f-135">Tuttavia, i nuovi utenti che richiedono il periodo di conservazione di 5 anni si sommano ai numeri da includere ed escludere e questo limite viene raggiunto a 1.000.</span><span class="sxs-lookup"><span data-stu-id="62e1f-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="62e1f-136">Esempio di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="62e1f-136">SharePoint example:</span></span>

- <span data-ttu-id="62e1f-137">**Requisito**: l'organizzazione ha diverse migliaia di siti di SharePoint, ma soltanto 2000 siti richiedono un periodo di conservazione da 10 anni, e 8000 siti richiedono un periodo di conservazione da quattro anni.</span><span class="sxs-lookup"><span data-stu-id="62e1f-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="62e1f-138">**Soluzione**: creare 20 criteri di conservazione per SharePoint con un periodo di conservazione da 10 anni che includa 100 siti specifici, e creare 80 criteri di conservazione per SharePoint con un periodo di conservazione da quattro anni che includa 100 siti specifici.</span><span class="sxs-lookup"><span data-stu-id="62e1f-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="62e1f-139">Poiché non è necessario conservare tutti i siti di SharePoint, bisogna creare criteri di conservazione che specificano i siti.</span><span class="sxs-lookup"><span data-stu-id="62e1f-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="62e1f-140">Dato che i criteri di conservazione non supportano più di 100 siti specifici, è necessario creare criteri specifici per i due periodi di conservazione.</span><span class="sxs-lookup"><span data-stu-id="62e1f-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="62e1f-141">Questo criterio di conservazione hanno il numero massimo di siti inclusi, perciò un nuovo criterio di conservazione deve essere creato per il prossimo nuovo sito che richiede la conservazione, indipendentemente dal periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="62e1f-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>