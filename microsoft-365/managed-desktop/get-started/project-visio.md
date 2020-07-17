---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126828"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="c5ec1-104">Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="c5ec1-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="c5ec1-105">Microsoft Project e Microsoft Visio richiedono una procedura specifica da installare sui dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5ec1-106">In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5ec1-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c5ec1-107">Prerequisites</span></span>

<span data-ttu-id="c5ec1-108">Gli amministratori devono verificare che soddisfino questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="c5ec1-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="c5ec1-109">**Quantità di licenza** : la quantità corretta di Microsoft Project e delle licenze di Microsoft Visio deve essere disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="c5ec1-110">Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="c5ec1-111">**Nomi delle licenze** -i nomi delle licenze appropriate per queste applicazioni sono:</span><span class="sxs-lookup"><span data-stu-id="c5ec1-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="c5ec1-112">**Microsoft Project** -Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="c5ec1-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="c5ec1-113">**Microsoft Visio** -Visio online, piano 2</span><span class="sxs-lookup"><span data-stu-id="c5ec1-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="c5ec1-114">**Portale aziendale** : il portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="c5ec1-115">Se il portale aziendale non è distribuito nel tenant, vedere [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="c5ec1-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="c5ec1-116">Distribuire Project e Visio per i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="c5ec1-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c5ec1-117">Microsoft Managed Desktop aggiungerà Microsoft Project e Microsoft Visio come due applicazioni Win32 in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="c5ec1-118">Verranno inoltre creati due gruppi in Azure Active Directory che verranno assegnati all'applicazione corrispondente con lo scopo "available".</span><span class="sxs-lookup"><span data-stu-id="c5ec1-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="c5ec1-119">**Per distribuire Project e Visio** Aggiungere l'utente al gruppo appropriato e l'applicazione diventerà disponibile nel portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="c5ec1-120">La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="c5ec1-121">Nome del gruppo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c5ec1-121">Azure AD Group name</span></span> | <span data-ttu-id="c5ec1-122">Quali utenti assegnare?</span><span class="sxs-lookup"><span data-stu-id="c5ec1-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="c5ec1-123">Ambiente di lavoro moderno-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="c5ec1-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="c5ec1-124">Utenti che necessitano di un progetto</span><span class="sxs-lookup"><span data-stu-id="c5ec1-124">Users needing Project</span></span>
<span data-ttu-id="c5ec1-125">Ambiente di lavoro moderno-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="c5ec1-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="c5ec1-126">Utenti che hanno bisogno di Visio</span><span class="sxs-lookup"><span data-stu-id="c5ec1-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="c5ec1-127">Comunicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="c5ec1-127">Communicate changes</span></span>
<span data-ttu-id="c5ec1-128">Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="c5ec1-129">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="c5ec1-129">This includes:</span></span> 
- <span data-ttu-id="c5ec1-130">Notifica agli utenti quando sono disponibili per queste applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="c5ec1-131">Istruzioni su come installare queste applicazioni dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c5ec1-131">Instructions on how to install these applications from the Company Portal.</span></span>
