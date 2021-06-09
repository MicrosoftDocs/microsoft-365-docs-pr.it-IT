---
title: Installare Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="2ee9d-104">Installare Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi</span><span class="sxs-lookup"><span data-stu-id="2ee9d-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="2ee9d-105">Microsoft Project e Microsoft Visio devono essere installati in dispositivi Microsoft Managed Desktop specifici.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2ee9d-106">In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ee9d-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2ee9d-107">Prerequisites</span></span>

<span data-ttu-id="2ee9d-108">Gli amministratori devono verificare che soddisfino questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="2ee9d-109">**Quantità di** licenze: la quantità corretta di Microsoft Project e microsoft Visio deve essere disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="2ee9d-110">Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="2ee9d-111">**Nomi delle licenze:** i nomi di licenza appropriati per queste applicazioni sono:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="2ee9d-112">**Microsoft Project** - Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="2ee9d-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="2ee9d-113">**Microsoft Visio** - Visio Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="2ee9d-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="2ee9d-114">**Portale aziendale-** Il Portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="2ee9d-115">Se il Portale aziendale non è distribuito nel tenant, vedere [Portale aziendale](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="2ee9d-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="2ee9d-116">Distribuire Project e Visio per Microsoft Managed Desktop dispositivi</span><span class="sxs-lookup"><span data-stu-id="2ee9d-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2ee9d-117">Microsoft Managed Desktop aggiungerà Microsoft Project e Microsoft Visio come due applicazioni Win32 in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="2ee9d-118">Verranno inoltre creati due gruppi in Azure Active Directory che verranno assegnati all'applicazione corrispondente con lo scopo "Disponibile".</span><span class="sxs-lookup"><span data-stu-id="2ee9d-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="2ee9d-119">**Per distribuire Project e Visio** Aggiungi l'utente al gruppo appropriato e l'applicazione diventerà disponibile nella Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="2ee9d-120">La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app da Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="2ee9d-121">Nome del gruppo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ee9d-121">Azure AD Group name</span></span> | <span data-ttu-id="2ee9d-122">Quali utenti assegnare?</span><span class="sxs-lookup"><span data-stu-id="2ee9d-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="2ee9d-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="2ee9d-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="2ee9d-124">Utenti che necessitano di Project</span><span class="sxs-lookup"><span data-stu-id="2ee9d-124">Users needing Project</span></span>
<span data-ttu-id="2ee9d-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="2ee9d-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="2ee9d-126">Utenti che necessitano Visio</span><span class="sxs-lookup"><span data-stu-id="2ee9d-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="2ee9d-127">Comunicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="2ee9d-127">Communicate changes</span></span>
<span data-ttu-id="2ee9d-128">È importante che gli amministratori IT sappiano come installare Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="2ee9d-129">Tra questi vi sono anche:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-129">This includes:</span></span> 
- <span data-ttu-id="2ee9d-130">Notifica agli utenti quando queste applicazioni sono disponibili per loro.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="2ee9d-131">Istruzioni su come installare queste applicazioni dal Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-131">Instructions on how to install these applications from the Company Portal.</span></span>
