---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022097"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="8d27f-104">Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="8d27f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="8d27f-105">Microsoft Project e Microsoft Visio richiedono una procedura specifica da installare sui dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8d27f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8d27f-106">In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d27f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d27f-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d27f-107">Prerequisites</span></span>

<span data-ttu-id="8d27f-108">Gli amministratori devono verificare che soddisfino questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="8d27f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="8d27f-109">**Quantità di licenza** : la quantità corretta di Microsoft Project e delle licenze di Microsoft Visio deve essere disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8d27f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="8d27f-110">Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d27f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="8d27f-111">**Nomi delle licenze** -i nomi delle licenze appropriate per queste applicazioni sono:</span><span class="sxs-lookup"><span data-stu-id="8d27f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="8d27f-112">**Microsoft Project** -Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="8d27f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="8d27f-113">**Microsoft Visio** -Visio online, piano 2</span><span class="sxs-lookup"><span data-stu-id="8d27f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="8d27f-114">**Portale aziendale** : il portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d27f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="8d27f-115">Se il portale aziendale non è distribuito nel tenant, vedere [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="8d27f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="8d27f-116">Distribuire Project e Visio per i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="8d27f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8d27f-117">Dopo aver inviato la richiesta di supporto, Microsoft Managed Desktop creerà tre gruppi di Azure AD e tre distribuzioni di applicazioni tramite Microsoft Intune per distribuire le app al tenant.</span><span class="sxs-lookup"><span data-stu-id="8d27f-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="8d27f-118">**Per distribuire Project e Visio**</span><span class="sxs-lookup"><span data-stu-id="8d27f-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="8d27f-119">**Presentare una richiesta di supporto** Gli amministratori IT devono presentare una richiesta di supporto per rendere queste applicazioni disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8d27f-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="8d27f-120">Per informazioni su come contattare Microsoft Managed Desktop, vedere [supporto di amministrazione per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="8d27f-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="8d27f-121">**Assegnare gli utenti ai nuovi gruppi di Azure ad** Microsoft Managed Desktop creerà tre gruppi di Azure AD nel tenant e 3 distribuzioni di applicazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8d27f-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="8d27f-122">Gli amministratori IT devono assegnare gli utenti ai gruppi adatti.</span><span class="sxs-lookup"><span data-stu-id="8d27f-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="8d27f-123">Assegnare gli utenti solo a uno di questi gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8d27f-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="8d27f-124">Nome del gruppo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d27f-124">Azure AD Group name</span></span> | <span data-ttu-id="8d27f-125">Quali utenti assegnare?</span><span class="sxs-lookup"><span data-stu-id="8d27f-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="8d27f-126">Ambiente di lavoro moderno-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="8d27f-126">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="8d27f-127">Utenti che necessitano di un progetto</span><span class="sxs-lookup"><span data-stu-id="8d27f-127">Users needing Project</span></span>
<span data-ttu-id="8d27f-128">Ambiente di lavoro moderno-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="8d27f-128">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="8d27f-129">Utenti che hanno bisogno di Visio</span><span class="sxs-lookup"><span data-stu-id="8d27f-129">Users needing Visio</span></span>

<span data-ttu-id="8d27f-130">Una volta assegnati a questi gruppi, le applicazioni saranno disponibili nel portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d27f-130">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="8d27f-131">La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d27f-131">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="8d27f-132">Comunicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="8d27f-132">Communicate changes</span></span>
<span data-ttu-id="8d27f-133">Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="8d27f-133">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="8d27f-134">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="8d27f-134">This includes:</span></span> 
- <span data-ttu-id="8d27f-135">Notifica agli utenti quando sono disponibili per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d27f-135">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="8d27f-136">Istruzioni su come installare queste applicazioni dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d27f-136">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="8d27f-137">Gli utenti devono chiudere tutte le applicazioni di Office prima di installare Microsoft Project o Microsoft Visio dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d27f-137">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
