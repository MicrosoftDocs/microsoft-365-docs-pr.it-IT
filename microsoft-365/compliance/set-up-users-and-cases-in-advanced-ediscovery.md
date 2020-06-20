---
title: Configurare gli utenti e i casi in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informazioni su come configurare i ruoli utente, creare casi e assegnare gli utenti ai casi in Advanced eDiscovery.  '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6cfc8e313816c0c01512dd0d4b71f1dbbd6e6505
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819176"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="fa6a2-103">Configurare gli utenti e i casi in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="fa6a2-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="fa6a2-104">In questo argomento viene descritto come configurare gli utenti e i casi per Advanced eDiscovery (Classic).</span><span class="sxs-lookup"><span data-stu-id="fa6a2-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa6a2-105">Microsoft continua a investire in nuove versioni di Advanced eDiscovery e annuncia il ritiro di Advanced eDiscovery, noto anche come *Advanced eDiscovery (classico)* o *Advanced eDiscovery v1.0*.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="fa6a2-106">Se si usa ancora Advanced eDiscovery v 1.0, passare al più presto ad [Advanced eDiscovery v2.0](overview-ediscovery-20.md), noto anche come *soluzione Advanced eDiscovery in Microsoft 365*.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="fa6a2-107">Advanced eDiscovery 2.0 contiene funzionalità simili a quelle disponibili in Advanced eDiscovery v1.0, ma offre anche numerose nuove caratteristiche, come gestione dei responsabili, gestione delle comunicazioni e insiemi da rivedere.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="fa6a2-108">Per altre informazioni sul ritiro di Advanced eDiscovery v 1.0, vedere [Ritiro degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="fa6a2-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="fa6a2-109">Requisiti per la configurazione degli utenti e dei casi</span><span class="sxs-lookup"><span data-stu-id="fa6a2-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="fa6a2-110">Prima di configurare i casi e gli utenti in Advanced eDiscovery, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fa6a2-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="fa6a2-111">Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="fa6a2-112">In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="fa6a2-113">Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="fa6a2-114">È necessario essere membri del gruppo di ruoli eDiscovery Manager nel &amp; Centro sicurezza e conformità per creare un caso di eDiscovery e aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="fa6a2-115">Per aggiungersi al gruppo di ruoli eDiscovery Manager nel &amp; Centro sicurezza e conformità, è necessario essere un amministratore globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="fa6a2-116">Se non si è un amministratore globale, è necessario chiedere a un amministratore globale di aggiungerlo al gruppo di ruoli eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="fa6a2-117">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="fa6a2-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="fa6a2-118">Autorizzazioni nel centro sicurezza e conformità di Microsoft 365 &amp;</span><span class="sxs-lookup"><span data-stu-id="fa6a2-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="fa6a2-119">Assegnare le autorizzazioni di eDiscovery nel centro sicurezza e conformità di Microsoft 365 &amp;</span><span class="sxs-lookup"><span data-stu-id="fa6a2-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="fa6a2-120">Passaggio 1: assegnare autorizzazioni di eDiscovery agli utenti</span><span class="sxs-lookup"><span data-stu-id="fa6a2-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="fa6a2-121">Il primo passaggio consiste nell'assegnare agli utenti le autorizzazioni dei requisiti nel &amp; Centro sicurezza e conformità in modo che possano essere aggiunte come membri di un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="fa6a2-122">Dopo che un utente è stato aggiunto come membro di un caso nel &amp; Centro sicurezza e conformità, sarà possibile accedere al caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="fa6a2-123">Per assegnare a un utente le autorizzazioni necessarie in modo che possano essere aggiunte come membri di un caso di eDiscovery, vedere il passaggio 1 in [eDiscovery Cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="fa6a2-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="fa6a2-124">Passaggio 2: creare un caso di eDiscovery e aggiungere membri</span><span class="sxs-lookup"><span data-stu-id="fa6a2-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="fa6a2-125">Il passaggio successivo consiste nel creare un nuovo caso di eDiscovery nel centro sicurezza & compliance e aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="fa6a2-126">I membri del caso saranno quindi in grado di accedere al caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="fa6a2-127">Per creare un nuovo caso di eDiscovery, vedere Step 3 in [Get Started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span><span class="sxs-lookup"><span data-stu-id="fa6a2-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="fa6a2-128">Per aggiungere membri a un caso di eDiscovery, vedere passaggio 4 in [Get Started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span><span class="sxs-lookup"><span data-stu-id="fa6a2-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="fa6a2-129">Passaggio 3: andare a un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa6a2-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="fa6a2-130">Dopo aver creato un caso di eDiscovery e aver aggiunto membri, l'utente (o qualsiasi membro del caso) può accedere al caso corrispondente in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fa6a2-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="fa6a2-131">Per accedere a un caso in Advanced eDiscovery, vedere [accesso a un caso in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="fa6a2-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa6a2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa6a2-132">See also</span></span>

[<span data-ttu-id="fa6a2-133">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="fa6a2-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="fa6a2-134">Preparazione dei dati per Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="fa6a2-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 