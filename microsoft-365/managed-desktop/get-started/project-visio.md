---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950533"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="d12d5-104">Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d12d5-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="d12d5-105">Microsoft Project e Microsoft Visio richiedono una procedura specifica da installare sui dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d12d5-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d12d5-106">In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d12d5-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d12d5-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d12d5-107">Prerequisites</span></span>

<span data-ttu-id="d12d5-108">Gli amministratori devono verificare che soddisfino questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="d12d5-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="d12d5-109">**Quantità di licenza** : la quantità corretta di Microsoft Project e delle licenze di Microsoft Visio deve essere disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d12d5-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="d12d5-110">Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d12d5-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="d12d5-111">**Nomi delle licenze** -i nomi delle licenze appropriate per queste applicazioni sono:</span><span class="sxs-lookup"><span data-stu-id="d12d5-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="d12d5-112">**Microsoft Project** -Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="d12d5-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="d12d5-113">**Microsoft Visio** -Visio online, piano 2</span><span class="sxs-lookup"><span data-stu-id="d12d5-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="d12d5-114">**Portale aziendale** : il portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d12d5-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="d12d5-115">Se il portale aziendale non è distribuito nel tenant, vedere [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="d12d5-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="d12d5-116">Distribuire Project e Visio per i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d12d5-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d12d5-117">Microsoft Managed Desktop aggiungerà Microsoft Project e Microsoft Visio come due applicazioni Win32 in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d12d5-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="d12d5-118">Verranno inoltre creati due gruppi in Azure Active Directory che verranno assegnati all'applicazione corrispondente con lo scopo "available".</span><span class="sxs-lookup"><span data-stu-id="d12d5-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="d12d5-119">**Per distribuire Project e Visio** Aggiungere l'utente al gruppo appropriato e l'applicazione diventerà disponibile nel portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="d12d5-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="d12d5-120">La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="d12d5-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="d12d5-121">Nome del gruppo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="d12d5-121">Azure AD Group name</span></span> | <span data-ttu-id="d12d5-122">Quali utenti assegnare?</span><span class="sxs-lookup"><span data-stu-id="d12d5-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="d12d5-123">Ambiente di lavoro moderno-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="d12d5-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="d12d5-124">Utenti che necessitano di un progetto</span><span class="sxs-lookup"><span data-stu-id="d12d5-124">Users needing Project</span></span>
<span data-ttu-id="d12d5-125">Ambiente di lavoro moderno-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="d12d5-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="d12d5-126">Utenti che hanno bisogno di Visio</span><span class="sxs-lookup"><span data-stu-id="d12d5-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="d12d5-127">Comunicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="d12d5-127">Communicate changes</span></span>
<span data-ttu-id="d12d5-128">Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="d12d5-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="d12d5-129">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="d12d5-129">This includes:</span></span> 
- <span data-ttu-id="d12d5-130">Notifica agli utenti quando sono disponibili per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d12d5-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="d12d5-131">Istruzioni su come installare queste applicazioni dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="d12d5-131">Instructions on how to install these applications from the Company Portal.</span></span>
