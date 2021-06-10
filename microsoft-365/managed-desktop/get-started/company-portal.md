---
title: Installare Portale aziendale Intune nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale Microsoft Managed Desktop dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, Portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086686"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="a31e2-104">Installare Portale aziendale Intune nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a31e2-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="a31e2-105">Microsoft Managed Desktop che gli amministratori IT installino Portale aziendale Intune per gli utenti con Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a31e2-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a31e2-106">Ecco alcuni vantaggi per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="a31e2-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="a31e2-107">Gli utenti hanno un'unica posizione per esplorare e installare le applicazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="a31e2-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="a31e2-108">Gli amministratori IT possono organizzare le applicazioni per categorie per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a31e2-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="a31e2-109">Alcune applicazioni (come Microsoft Project e Microsoft Visio) richiedono Portale aziendale la distribuzione con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a31e2-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="a31e2-110">Gli amministratori IT possono personalizzare Portale aziendale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a31e2-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="a31e2-111">Ciò include la creazione di immagini del marchio, l'aggiunta di contatti di supporto locale e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a31e2-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="a31e2-112">Per altre informazioni, vedi [Come configurare l'app Microsoft Intune Portale aziendale.](/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="a31e2-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="a31e2-113">In questo argomento viene documentato il processo di distribuzione del Portale aziendale Intune agli utenti Microsoft Managed Desktop utenti.</span><span class="sxs-lookup"><span data-stu-id="a31e2-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="a31e2-114">Il processo complessivo è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a31e2-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="a31e2-115">Acquistare Portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune</span><span class="sxs-lookup"><span data-stu-id="a31e2-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="a31e2-116">Assegnare Portale aziendale agli utenti</span><span class="sxs-lookup"><span data-stu-id="a31e2-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="a31e2-117">Comunicare modifiche agli utenti</span><span class="sxs-lookup"><span data-stu-id="a31e2-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="a31e2-118">Passaggio 1 - Acquistare Portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune</span><span class="sxs-lookup"><span data-stu-id="a31e2-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="a31e2-119">Per info su come acquistare le app e sincronizzare con Intune, vedi Microsoft Store per le aziende [app](deploy-apps.md#msfb-apps) in *Distribuire app* Microsoft Managed Desktop dispositivi .</span><span class="sxs-lookup"><span data-stu-id="a31e2-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="a31e2-120">Questo argomento fornisce informazioni su come:</span><span class="sxs-lookup"><span data-stu-id="a31e2-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="a31e2-121">Acquistare Portale aziendale da Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="a31e2-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="a31e2-122">Forzare la sincronizzazione tra Intune e Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="a31e2-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="a31e2-123">Verificare la sincronizzazione attiva tra Intune e Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="a31e2-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="a31e2-124">Passaggio 2 - Assegnare Portale aziendale agli utenti</span><span class="sxs-lookup"><span data-stu-id="a31e2-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="a31e2-125">Dopo la registrazione in Microsoft Managed Desktop, distribuiremo automaticamente Portale aziendale nel tenant e installeremo l'app nei dispositivi Microsoft Managed Desktop nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a31e2-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="a31e2-126">Passaggio 3 - Comunicare la modifica agli utenti</span><span class="sxs-lookup"><span data-stu-id="a31e2-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="a31e2-127">In quanto amministratore IT dell'organizzazione, è importante che gli utenti sappiano come usare Portale aziendale nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a31e2-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="a31e2-128">Microsoft Managed Desktop consiglia:</span><span class="sxs-lookup"><span data-stu-id="a31e2-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="a31e2-129">Passaggi per l'installazione delle applicazioni dal Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="a31e2-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="a31e2-130">Per altre informazioni, vedi [Installare e condividere app nel dispositivo.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="a31e2-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="a31e2-131">Come inviare richieste agli amministratori IT per le applicazioni attualmente non disponibili.</span><span class="sxs-lookup"><span data-stu-id="a31e2-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="a31e2-132">Per altre informazioni, vedi [Richiedere un'app per il lavoro o l'istituto di istruzione.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="a31e2-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="a31e2-133">Passaggi per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a31e2-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="a31e2-134">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a31e2-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="a31e2-135">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="a31e2-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="a31e2-136">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="a31e2-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="a31e2-137">Distribuire Portale aziendale Intune (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="a31e2-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="a31e2-138">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="a31e2-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="a31e2-139">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="a31e2-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="a31e2-140">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="a31e2-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="a31e2-141">Distribuire le app</span><span class="sxs-lookup"><span data-stu-id="a31e2-141">Deploy apps</span></span>](deploy-apps.md)
