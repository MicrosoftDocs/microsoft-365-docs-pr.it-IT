---
title: Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487709"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="072ec-103">Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="072ec-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="072ec-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="072ec-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="072ec-105">È possibile utilizzare la protezione delle identità di Azure Active Directory (Azure AD) per individuare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione, configurare le risposte automatiche e esaminare gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="072ec-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="072ec-106">In questo articolo viene descritto come utilizzare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="072ec-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="072ec-107">La configurazione di Azure AD Identity Protection nell'ambiente di testing di Microsoft 365 per l'organizzazione prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="072ec-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="072ec-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="072ec-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="072ec-109">Fase 2: utilizzare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="072ec-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="072ec-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="072ec-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="072ec-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="072ec-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="072ec-113">Se si desidera testare la protezione delle identità di Azure AD solo con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="072ec-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="072ec-114">Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="072ec-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="072ec-115">Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="072ec-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="072ec-116">Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="072ec-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="072ec-117">Fase 2: utilizzare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="072ec-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="072ec-118">Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="072ec-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="072ec-119">Nel portale di Azure, digitare **Identity Protection** nella casella di ricerca e quindi selezionare **Azure ad Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="072ec-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="072ec-120">Nel Blade **panoramica sulla protezione delle identità** , selezionare ogni rapporto per vedere cosa segnala.</span><span class="sxs-lookup"><span data-stu-id="072ec-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="072ec-121">In **notifica**selezionare **utenti a rischio avvisi rilevati**.</span><span class="sxs-lookup"><span data-stu-id="072ec-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="072ec-122">Nel riquadro **utenti a rischio individuati** selezionare **media**.</span><span class="sxs-lookup"><span data-stu-id="072ec-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="072ec-123">Per **i messaggi di posta elettronica vengono inviati agli utenti seguenti**, selezionare incluso e verificare che l'account di amministratore globale sia **presente** nell'elenco dei membri selezionati.</span><span class="sxs-lookup"><span data-stu-id="072ec-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="072ec-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="072ec-124">Select **Save**.</span></span>

<span data-ttu-id="072ec-125">In **Proteggi**selezionare vari criteri di polizia per vedere come configurarli.</span><span class="sxs-lookup"><span data-stu-id="072ec-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="072ec-126">Se si crea e si attiva un criterio, assicurarsi che non venga bloccato l'accesso per tutti gli utenti oppure che potrebbe non essere possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="072ec-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="072ec-127">Per evitare questo, escludere gli account utente specifici, ad esempio gli amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="072ec-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="072ec-128">Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="072ec-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="072ec-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="072ec-129">Next step</span></span>

<span data-ttu-id="072ec-130">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="072ec-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="072ec-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="072ec-131">See also</span></span>

[<span data-ttu-id="072ec-132">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="072ec-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="072ec-133">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="072ec-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="072ec-134">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="072ec-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="072ec-135">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="072ec-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
