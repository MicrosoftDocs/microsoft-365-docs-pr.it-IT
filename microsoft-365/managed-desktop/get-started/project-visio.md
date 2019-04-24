---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288997"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="ce3f1-104">Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ce3f1-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="ce3f1-105">Microsoft Project e Microsoft Visio richiedono una procedura specifica da installare sui dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ce3f1-106">In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce3f1-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ce3f1-107">Prerequisites</span></span>

<span data-ttu-id="ce3f1-108">Gli amministratori devono verificare che soddisfino questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="ce3f1-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="ce3f1-109">**Quantità di licenza** : la quantità corretta di Microsoft Project e delle licenze di Microsoft Visio deve essere disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="ce3f1-110">Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="ce3f1-111">**Nomi delle licenze** -i nomi delle licenze appropriate per queste applicazioni sono:</span><span class="sxs-lookup"><span data-stu-id="ce3f1-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="ce3f1-112">**Microsoft Project** -Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="ce3f1-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="ce3f1-113">**Microsoft Visio** -Visio online, piano 2</span><span class="sxs-lookup"><span data-stu-id="ce3f1-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="ce3f1-114">**Portale aziendale** : il portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="ce3f1-115">Se il portale aziendale non è distribuito nel tenant, vedere [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="ce3f1-116">Distribuire Project e Visio per i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ce3f1-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ce3f1-117">Dopo aver inviato la richiesta di supporto, Microsoft Managed Desktop creerà tre gruppi di Azure AD e tre distribuzioni di applicazioni tramite Microsoft Intune per distribuire le app al tenant.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="ce3f1-118">**Per distribuire Project e Visio**</span><span class="sxs-lookup"><span data-stu-id="ce3f1-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="ce3f1-119">**Presentare una richiesta di supporto** Gli amministratori IT devono presentare una richiesta di supporto per rendere queste applicazioni disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="ce3f1-120">Per informazioni su come contattare Microsoft Managed Desktop, vedere [supporto di amministrazione per Microsoft managEd desktop](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f1-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="ce3f1-121">**Assegnare gli utenti ai nuovi gruppi di Azure ad** Microsoft Managed Desktop creerà tre gruppi di Azure AD nel tenant e 3 distribuzioni di applicazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="ce3f1-122">Gli amministratori IT devono assegnare gli utenti ai gruppi adatti.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="ce3f1-123">Assegnare gli utenti solo a uno di questi gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="ce3f1-124">Nome del gruppo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="ce3f1-124">Azure AD Group name</span></span> | <span data-ttu-id="ce3f1-125">Quali utenti assegnare?</span><span class="sxs-lookup"><span data-stu-id="ce3f1-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="ce3f1-126">Microsoft-Office-Project-install</span><span class="sxs-lookup"><span data-stu-id="ce3f1-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="ce3f1-127">Gli utenti che hanno bisogno di solo Project</span><span class="sxs-lookup"><span data-stu-id="ce3f1-127">Users needing only Project</span></span>
<span data-ttu-id="ce3f1-128">Microsoft-Office-Visio-install</span><span class="sxs-lookup"><span data-stu-id="ce3f1-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="ce3f1-129">Gli utenti che hanno bisogno di solo Visio</span><span class="sxs-lookup"><span data-stu-id="ce3f1-129">Users needing only Visio</span></span>
<span data-ttu-id="ce3f1-130">Microsoft-Office-Project e Visio-install</span><span class="sxs-lookup"><span data-stu-id="ce3f1-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="ce3f1-131">Gli utenti che hanno bisogno sia di Project che di Visio</span><span class="sxs-lookup"><span data-stu-id="ce3f1-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="ce3f1-132">Una volta assegnati a questi gruppi, le applicazioni saranno disponibili nel portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="ce3f1-133">La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="ce3f1-134">Comunicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="ce3f1-134">Communicate changes</span></span>
<span data-ttu-id="ce3f1-135">Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="ce3f1-136">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="ce3f1-136">This includes:</span></span> 
- <span data-ttu-id="ce3f1-137">Notifica agli utenti quando sono disponibili per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="ce3f1-138">Istruzioni su come installare queste applicazioni dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="ce3f1-139">Gli utenti devono chiudere tutte le applicazioni di Office prima di installare Microsoft Project o Microsoft Visio dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce3f1-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
