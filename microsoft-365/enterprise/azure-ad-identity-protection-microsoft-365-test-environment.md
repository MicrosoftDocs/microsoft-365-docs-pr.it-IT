---
title: Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: a21b20f4ca774ad38990e44abc18d666426e74d5
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640405"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36478-103">Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36478-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36478-104">Azure AD Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione, la configurazione delle risposte automatiche e l'analisi degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="36478-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="36478-105">In questo articolo viene descritto come abilitare Azure AD Identity Protection e visualizzare l'analisi degli account dell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="36478-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="36478-106">Sono disponibili due fasi per la configurazione di Azure AD Identity Protection nell'ambiente di testing Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="36478-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="36478-107">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36478-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="36478-108">Abilitazione e utilizzo di Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="36478-108">Enable and use Azure AD Identity Protection.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="36478-110">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36478-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36478-111">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36478-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36478-112">Se si desidera semplicemente testare Azure AD Identity Protection in modo leggero con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="36478-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="36478-113">Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="36478-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36478-114">Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="36478-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="36478-115">Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="36478-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="36478-116">Fase 2: abilitare e utilizzare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="36478-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="36478-117">Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36478-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="36478-118">Nel portale di Azure, fare clic su **tutti i servizi > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="36478-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="36478-119">Digitare **Azure ad Identity Protection** e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="36478-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="36478-120">Nella barra **iniziale** , fare clic su **onboard** in **Impostazioni**, fare clic su **Aggiungi a Dashboard**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="36478-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="36478-121">Nel portale di Azure, fare clic su **Azure ad Identity Protection** nel dashboard.</span><span class="sxs-lookup"><span data-stu-id="36478-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="36478-122">Si dovrebbe vedere un blade di **Azure ad Identity Protection-Overview** con un dashboard.</span><span class="sxs-lookup"><span data-stu-id="36478-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="36478-123">In **vulnerabilità**, si noti che ha determinato il numero di account utente senza registrazione di autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="36478-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="36478-124">Questo numero può variare in base alle precedenti guide di laboratorio di testing di Microsoft 365 Enterprise eseguite.</span><span class="sxs-lookup"><span data-stu-id="36478-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="36478-125">Fare **clic sulle categorie per verificare** se sono presenti utenti o eventi che sono stati rilevati.</span><span class="sxs-lookup"><span data-stu-id="36478-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="36478-126">Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="36478-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="36478-127">Per informazioni e collegamenti per la distribuzione di Azure AD Identity Protection in produzione, vedere il passaggio di compromesso relativo alla protezione da [credenziali](identity-secure-user-sign-ins.md#identity-ident-prot) nella fase Identity.</span><span class="sxs-lookup"><span data-stu-id="36478-127">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="36478-128">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="36478-128">Next step</span></span>

<span data-ttu-id="36478-129">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="36478-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="36478-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36478-130">See also</span></span>

[<span data-ttu-id="36478-131">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="36478-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="36478-132">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36478-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="36478-133">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="36478-133">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="36478-134">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36478-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
