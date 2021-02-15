---
title: Installare il portale aziendale intune nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale nei dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939285"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="94684-104">Installare il portale aziendale intune nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="94684-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="94684-105">Microsoft Managed Desktop richiede agli amministratori IT di installare il portale aziendale intune per gli utenti con i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="94684-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="94684-106">Ecco alcuni vantaggi per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="94684-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="94684-107">Gli utenti hanno un'unica posizione in cui esplorare e installare le applicazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="94684-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="94684-108">Gli amministratori IT possono organizzare le applicazioni per categorie per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="94684-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="94684-109">Alcune applicazioni, ad esempio Microsoft Project e Microsoft Visio, richiedono la distribuzione del portale aziendale con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="94684-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="94684-110">Gli amministratori IT possono personalizzare il portale aziendale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94684-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="94684-111">Ciò include la creazione di immagini del marchio, l'aggiunta di contatti di supporto locale e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="94684-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="94684-112">Per altre informazioni, vedere [Come configurare l'app](https://docs.microsoft.com/intune/company-portal-app)Portale aziendale di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="94684-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="94684-113">In questo argomento viene documentato il processo di distribuzione del portale aziendale intune agli utenti di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="94684-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="94684-114">Il processo generale è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="94684-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="94684-115">Acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune</span><span class="sxs-lookup"><span data-stu-id="94684-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="94684-116">Assegnare il portale aziendale agli utenti</span><span class="sxs-lookup"><span data-stu-id="94684-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="94684-117">Comunicare le modifiche agli utenti</span><span class="sxs-lookup"><span data-stu-id="94684-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="94684-118">Passaggio 1: acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune</span><span class="sxs-lookup"><span data-stu-id="94684-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="94684-119">Per informazioni su come acquistare le app e sincronizzare con Intune, vedi App di [Microsoft Store per le aziende](deploy-apps.md#msfb-apps) in Distribuire app nei dispositivi Microsoft Managed *Desktop.*</span><span class="sxs-lookup"><span data-stu-id="94684-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="94684-120">Questo argomento fornisce informazioni su come:</span><span class="sxs-lookup"><span data-stu-id="94684-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="94684-121">Acquistare il portale aziendale da Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="94684-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="94684-122">Forzare la sincronizzazione tra Intune e Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="94684-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="94684-123">Verificare la sincronizzazione attiva tra Intune e Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="94684-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="94684-124">Passaggio 2- Assegnare il portale aziendale agli utenti</span><span class="sxs-lookup"><span data-stu-id="94684-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="94684-125">Dopo la registrazione in Microsoft Managed Desktop, Microsoft Managed Desktop Operations distribuirà automaticamente Il portale aziendale nel tenant e installerà l'app nei dispositivi Microsoft Managed Desktop nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94684-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="94684-126">Passaggio 3: comunicare le modifiche agli utenti</span><span class="sxs-lookup"><span data-stu-id="94684-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="94684-127">In quanto amministratore IT dell'organizzazione, è importante che gli utenti sappiano come usare portale aziendale nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94684-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="94684-128">Microsoft Managed Desktop consiglia:</span><span class="sxs-lookup"><span data-stu-id="94684-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="94684-129">Passaggi per l'installazione delle applicazioni dal portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="94684-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="94684-130">Per altre informazioni, vedi [Installare e condividere app nel dispositivo.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="94684-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="94684-131">Come inviare richieste agli amministratori IT per le applicazioni attualmente non disponibili.</span><span class="sxs-lookup"><span data-stu-id="94684-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="94684-132">Per altre informazioni, vedi [Richiedere un'app per lavoro o istituto di istruzione.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="94684-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="94684-133">Procedura per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="94684-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="94684-134">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="94684-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="94684-135">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="94684-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="94684-136">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="94684-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="94684-137">Distribuire il portale aziendale di Intune (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="94684-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="94684-138">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="94684-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="94684-139">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="94684-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="94684-140">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="94684-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="94684-141">Distribuire le app</span><span class="sxs-lookup"><span data-stu-id="94684-141">Deploy apps</span></span>](deploy-apps.md)
