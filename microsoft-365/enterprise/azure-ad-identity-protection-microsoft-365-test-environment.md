---
title: Azure AD Identity Protection per l'ambiente di testing Microsoft 365 per le aziende
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
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905345"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="68fa6-103">Azure AD Identity Protection per l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="68fa6-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="68fa6-104">*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*</span><span class="sxs-lookup"><span data-stu-id="68fa6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="68fa6-105">È possibile usare Azure Active Directory (Azure AD) Identity Protection per rilevare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione, configurare risposte automatizzate e analizzare gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="68fa6-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="68fa6-106">Questo articolo descrive come usare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="68fa6-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="68fa6-107">La configurazione di Azure AD Identity Protection nell'ambiente di testing Microsoft 365 per le aziende prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="68fa6-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="68fa6-108">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="68fa6-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="68fa6-109">Fase 2: usare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="68fa6-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="68fa6-111">Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="68fa6-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="68fa6-112">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="68fa6-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="68fa6-113">Se si desidera testare Azure AD Identity Protection solo in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="68fa6-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="68fa6-114">Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="68fa6-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="68fa6-115">Il testing di Azure AD Identity Protection non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68fa6-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="68fa6-116">Viene fornito qui come opzione in modo da poter testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="68fa6-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="68fa6-117">Fase 2: usare Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="68fa6-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="68fa6-118">Apri un'istanza privata del browser e accedi al portale di Azure all'indirizzo con l'account amministratore globale dell'ambiente di testing [https://portal.azure.com](https://portal.azure.com) Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="68fa6-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="68fa6-119">Nel portale di Azure digitare **Identity Protection** nella casella di ricerca e quindi selezionare Azure AD **Identity Protection.**</span><span class="sxs-lookup"><span data-stu-id="68fa6-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="68fa6-120">Nel pannello **Identity Protection - Overview** selezionare ogni report per visualizzare i report.</span><span class="sxs-lookup"><span data-stu-id="68fa6-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="68fa6-121">In **Notifica** selezionare **Utenti a rischio avvisi rilevati**.</span><span class="sxs-lookup"><span data-stu-id="68fa6-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="68fa6-122">Nel riquadro **Avvisi rilevati dagli** utenti a rischio selezionare **Medio.**</span><span class="sxs-lookup"><span data-stu-id="68fa6-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="68fa6-123">Per **I messaggi di posta elettronica vengono inviati agli** utenti seguenti, selezionare **Incluso** e verificare che l'account amministratore globale sia incluso nell'elenco dei membri selezionati.</span><span class="sxs-lookup"><span data-stu-id="68fa6-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="68fa6-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="68fa6-124">Select **Save**.</span></span>

<span data-ttu-id="68fa6-125">In **Proteggi** seleziona vari criteri per vedere come configurarli.</span><span class="sxs-lookup"><span data-stu-id="68fa6-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="68fa6-126">Se si crea e si attiva un criterio, assicurarsi che non blocchi l'accesso per tutti gli utenti o che non sia possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="68fa6-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="68fa6-127">Per evitare questo problema, escludere account utente specifici, ad esempio amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="68fa6-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="68fa6-128">Per ulteriori test e sperimentazioni, vedere [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="68fa6-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="68fa6-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="68fa6-129">Next step</span></span>

<span data-ttu-id="68fa6-130">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="68fa6-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="68fa6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68fa6-131">See also</span></span>

[<span data-ttu-id="68fa6-132">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="68fa6-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="68fa6-133">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="68fa6-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="68fa6-134">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="68fa6-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="68fa6-135">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="68fa6-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)