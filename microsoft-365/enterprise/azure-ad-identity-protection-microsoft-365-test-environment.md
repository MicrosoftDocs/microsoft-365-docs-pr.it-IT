---
title: Ambiente di testing di Azure Active Directory Identity protezione per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la protezione dell'identità di Azure Active Directory e analizzare gli account corrente nell'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868363"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="22f4a-103">Ambiente di testing di Azure Active Directory Identity protezione per la propria azienda 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="22f4a-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="22f4a-p101">Protezione Azure Active Directory Identity consente di rilevare potenziale vulnerabilità che interessano le identità dell'organizzazione, configurare risposte automatiche e analizzare i problemi. In questo articolo viene descritto come abilitare la protezione con Azure Active Directory Identity e visualizzare l'analisi dei test environment gli account di posta.</span><span class="sxs-lookup"><span data-stu-id="22f4a-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="22f4a-106">Esistono due fasi per la configurazione della protezione di identità di Azure Active Directory nell'ambiente di test Microsoft 365 aziendale:</span><span class="sxs-lookup"><span data-stu-id="22f4a-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="22f4a-107">Creare l'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="22f4a-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="22f4a-108">Abilitare e utilizzare la protezione dell'identità di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f4a-108">Enable and use Azure AD Identity Protection.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="22f4a-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="22f4a-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="22f4a-111">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22f4a-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="22f4a-112">Se si desidera testare la protezione dell'identità di Azure Active Directory in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="22f4a-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="22f4a-113">Se si desidera testare la protezione dell'identità di Azure Active Directory in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="22f4a-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="22f4a-p102">Testare la protezione dell'identità di Azure Active Directory non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo da poter testare la protezione dell'identità di Azure Active Directory e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22f4a-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="22f4a-116">Fase 2: Abilitare e utilizzare la protezione dell'identità di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="22f4a-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="22f4a-117">Aprire un'istanza privata del browser e accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con l'account amministratore globale dell'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="22f4a-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="22f4a-118">Nel portale di Azure, fare clic su **tutti i servizi > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="22f4a-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="22f4a-119">Digitare **la protezione dell'identità di Azure Active Directory** e quindi fare clic su.</span><span class="sxs-lookup"><span data-stu-id="22f4a-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="22f4a-120">Su blade **Introduzione** fare clic su **Onboard** in **Impostazioni**, fare clic su **Aggiungi a dashboard**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="22f4a-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="22f4a-121">Nel portale di Azure, fare clic su **protezione dell'identità di Azure Active Directory** nel dashboard di.</span><span class="sxs-lookup"><span data-stu-id="22f4a-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="22f4a-p103">Verrà visualizzato un blade **Azure Active Directory Identity Protection-Panoramica** con un dashboard. Si noti che determinato il numero degli account utente senza la registrazione di autenticazione a più fattori in **vulnerabilità**. Questo numero varia in base ai precedenti Microsoft 365 Enterprise Test Lab guide che deve essere stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="22f4a-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="22f4a-125">Fare clic su attraverso le categorie per **indagare** vedere se sono presenti utenti o gli eventi che sono stati rilevati.</span><span class="sxs-lookup"><span data-stu-id="22f4a-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="22f4a-126">Per altre attività di testing e la sperimentazione, vedere [Simulating rischio eventi](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="22f4a-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="22f4a-127">Vedere il passaggio di [protezione contro i credenziali compromettere](identity-azure-ad-identity-protection.md) nella fase di identità per informazioni e collegamenti per distribuire la protezione di identità di Azure Active Directory nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="22f4a-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="22f4a-128">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="22f4a-128">Next step</span></span>

<span data-ttu-id="22f4a-129">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="22f4a-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="22f4a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22f4a-130">See also</span></span>

[<span data-ttu-id="22f4a-131">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="22f4a-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="22f4a-132">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22f4a-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="22f4a-133">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22f4a-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="22f4a-134">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22f4a-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
