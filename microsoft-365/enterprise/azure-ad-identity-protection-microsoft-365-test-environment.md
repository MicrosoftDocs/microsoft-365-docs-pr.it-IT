---
title: Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068493"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f2030-103">Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f2030-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f2030-104">*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f2030-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f2030-105">Azure Active Directory (Azure AD) Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione, configurare le risposte automatiche e indagare gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="f2030-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="f2030-106">In questo articolo viene descritto come utilizzare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="f2030-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="f2030-107">Sono disponibili due fasi per la configurazione di Azure AD Identity Protection nell'ambiente di testing Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="f2030-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="f2030-108">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f2030-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f2030-109">Utilizzo di Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="f2030-109">Use Azure AD Identity Protection.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f2030-111">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f2030-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f2030-112">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f2030-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f2030-113">Se si desidera semplicemente testare Azure AD Identity Protection in modo leggero con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f2030-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f2030-114">Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f2030-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2030-115">Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f2030-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f2030-116">Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="f2030-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="f2030-117">Fase 2: utilizzare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f2030-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="f2030-118">Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f2030-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f2030-119">Nel portale di Azure, digitare **Identity Protection** nella casella di ricerca e quindi fare clic su **Azure ad Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="f2030-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="f2030-120">Nel Blade **panoramica sulla protezione delle identità** , fare clic su ciascuno dei rapporti per vedere cosa stanno segnalando.</span><span class="sxs-lookup"><span data-stu-id="f2030-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="f2030-121">In **notifica**fare clic su **utenti a rischio avvisi rilevati**.</span><span class="sxs-lookup"><span data-stu-id="f2030-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="f2030-122">Nel riquadro **utenti a rischio individuati** selezionare **media**.</span><span class="sxs-lookup"><span data-stu-id="f2030-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="f2030-123">Per **i messaggi di posta elettronica vengono inviati agli utenti seguenti**, fare clic su **incluso** e verificare che l'account di amministratore globale sia presente nell'elenco dei membri selezionati.</span><span class="sxs-lookup"><span data-stu-id="f2030-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="f2030-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2030-124">Click **Save**.</span></span>

<span data-ttu-id="f2030-125">Fare clic sui diversi criteri in **Protect** per vedere come configurarli.</span><span class="sxs-lookup"><span data-stu-id="f2030-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="f2030-126">Se si crea e si attiva un criterio, assicurarsi che non sia bloccato l'accesso per un ambito troppo ampio di condizioni oppure che potrebbe non essere possibile accedere, anche come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f2030-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="f2030-127">Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="f2030-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="f2030-128">Per informazioni e collegamenti per la distribuzione di Azure AD Identity Protection in produzione, vedere il passaggio di compromesso relativo alla protezione da [credenziali](identity-secure-user-sign-ins.md#identity-ident-prot) nella fase Identity.</span><span class="sxs-lookup"><span data-stu-id="f2030-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f2030-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f2030-129">Next step</span></span>

<span data-ttu-id="f2030-130">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="f2030-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2030-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2030-131">See also</span></span>

[<span data-ttu-id="f2030-132">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="f2030-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f2030-133">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f2030-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="f2030-134">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f2030-134">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="f2030-135">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f2030-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
