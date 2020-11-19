---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso ai clienti ed esterni B2B-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive l'accesso condizionale consigliato e i criteri correlati per proteggere l'accesso di utenti esterni e Guest.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 55a84fa8ba31cfd4f981f2820811b541ae340a27
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357624"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="d3396-103">Criteri per consentire l'accesso all'ospite e all'esterno B2B</span><span class="sxs-lookup"><span data-stu-id="d3396-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="d3396-104">In questo articolo viene descritto come modificare i criteri di identità e accesso ai dispositivi comuni consigliati per consentire l'accesso per gli utenti guest e esterni che dispongono di un account B2B di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d3396-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="d3396-105">Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d3396-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="d3396-106">Tali raccomandazioni sono state progettate per essere applicate al livello di protezione di **base** .</span><span class="sxs-lookup"><span data-stu-id="d3396-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="d3396-107">Tuttavia, è anche possibile modificare le raccomandazioni in base alla granularità delle proprie esigenze per una protezione **sensibile** e **altamente regolamentata** .</span><span class="sxs-lookup"><span data-stu-id="d3396-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="d3396-108">Fornire un percorso per gli account B2B per l'autenticazione con il tenant di Azure AD non consente agli account di accedere all'intero ambiente.</span><span class="sxs-lookup"><span data-stu-id="d3396-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="d3396-109">Gli utenti B2B e i loro account hanno accesso solo alle risorse condivise con essi (ad esempio i file) all'interno dei servizi concessi nei criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="d3396-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="d3396-110">Aggiornamento dei criteri comuni per consentire e proteggere gli ospiti e l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d3396-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="d3396-111">Per proteggere l'accesso guest e esterno con gli account di Azure AD B2B, nel diagramma seguente vengono illustrati i criteri da aggiungere o aggiornare dai criteri comuni di accesso ai dispositivi e alle identità.</span><span class="sxs-lookup"><span data-stu-id="d3396-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="d3396-112">[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso Guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="d3396-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="d3396-113">Visualizzazione di una versione più grande di questa immagine</span><span class="sxs-lookup"><span data-stu-id="d3396-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="d3396-114">Nella tabella seguente sono elencati i criteri necessari per la creazione e l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d3396-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="d3396-115">I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="d3396-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="d3396-116">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="d3396-116">Protection level</span></span>|<span data-ttu-id="d3396-117">Criteri</span><span class="sxs-lookup"><span data-stu-id="d3396-117">Policies</span></span>|<span data-ttu-id="d3396-118">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d3396-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="d3396-119">**Protezione di base**</span><span class="sxs-lookup"><span data-stu-id="d3396-119">**Baseline**</span></span>|[<span data-ttu-id="d3396-120">Richiedi sempre un master per utenti esterni e Guest</span><span class="sxs-lookup"><span data-stu-id="d3396-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d3396-121">Creare il nuovo criterio e configurare:</span><span class="sxs-lookup"><span data-stu-id="d3396-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="d3396-122">Per le **assegnazioni > gli utenti e i gruppi > includono**, scegliere **Seleziona utenti e gruppi**, quindi selezionare **tutti gli utenti guest ed esterni**.</span><span class="sxs-lookup"><span data-stu-id="d3396-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="d3396-123">Per le **assegnazioni > condizioni > l'accesso**, lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (AMF).</span><span class="sxs-lookup"><span data-stu-id="d3396-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="d3396-124">Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*</span><span class="sxs-lookup"><span data-stu-id="d3396-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d3396-125">Modificare questo criterio per escludere gli utenti esterni e Guest.</span><span class="sxs-lookup"><span data-stu-id="d3396-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="d3396-126">Richiedere computer conformi</span><span class="sxs-lookup"><span data-stu-id="d3396-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="d3396-127">Modificare questo criterio per escludere gli utenti esterni e Guest.</span><span class="sxs-lookup"><span data-stu-id="d3396-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="d3396-128">Per includere o escludere gli utenti guest ed esterni nei criteri di accesso condizionale, per le **assegnazioni > gli utenti e i gruppi > includere** o **escludere**, controllare **tutti gli utenti guest e External**.</span><span class="sxs-lookup"><span data-stu-id="d3396-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![acquisizione dello schermo dei controlli per l'esclusione di utenti esterni e Guest](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="d3396-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d3396-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="d3396-131">Guest e accesso esterno con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3396-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="d3396-132">Microsoft teams definisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d3396-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="d3396-133">**L'accesso Guest** utilizza un account di Azure ad B2B che può essere aggiunto come membro di un team e dispone di tutti gli accessi autorizzati alle comunicazioni e alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="d3396-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="d3396-134">**L'accesso esterno** è per un utente esterno che non dispone di un account B2B.</span><span class="sxs-lookup"><span data-stu-id="d3396-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="d3396-135">L'accesso esterno può includere gli inviti e la partecipazione a chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="d3396-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="d3396-136">Per ulteriori informazioni, vedere il [confronto tra Guest e accesso esterno per i team](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="d3396-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="d3396-137">I criteri di accesso condizionale si applicano solo all'accesso guest nei team perché è presente un account di Azure AD B2B corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d3396-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="d3396-138">Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per i team [, vedere consigli sui criteri per la protezione delle chat, dei gruppi e dei file del team](teams-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="d3396-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="d3396-139">Richiedi sempre un master per utenti esterni e Guest</span><span class="sxs-lookup"><span data-stu-id="d3396-139">Require MFA always for guest and external users</span></span>

<span data-ttu-id="d3396-140">Questo criterio richiede agli utenti di registrarsi per l'AMF nel tenant, indipendentemente dal fatto che siano registrati per l'AMF nel tenant di casa.</span><span class="sxs-lookup"><span data-stu-id="d3396-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="d3396-141">Quando si accede alle risorse del tenant, è necessario che gli utenti guest e esterni utilizzino Mae per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="d3396-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="d3396-142">Esclusione di utenti esterni e Guest dall'AMF basata sui rischi</span><span class="sxs-lookup"><span data-stu-id="d3396-142">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="d3396-143">Sebbene le organizzazioni possano applicare criteri basati sui rischi per gli utenti B2B che utilizzano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory di risorse a causa della loro identità esistente nella Home Directory.</span><span class="sxs-lookup"><span data-stu-id="d3396-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="d3396-144">A causa di queste limitazioni, Microsoft consiglia di escludere gli utenti Guest dai criteri dell'AMF basati sui rischi e richiedere a questi utenti di utilizzare sempre il Mae.</span><span class="sxs-lookup"><span data-stu-id="d3396-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="d3396-145">Per ulteriori informazioni, vedere [limitazioni della protezione dell'identità per gli utenti di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="d3396-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="d3396-146">Esclusione di utenti esterni e Guest dalla gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="d3396-146">Excluding guest and external users from device management</span></span>

<span data-ttu-id="d3396-147">Solo un'organizzazione può gestire un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3396-147">Only one organization can manage a device.</span></span> <span data-ttu-id="d3396-148">Se non si escludono gli utenti guest e esterni dai criteri che richiedono la conformità del dispositivo, questi criteri bloccano tali utenti.</span><span class="sxs-lookup"><span data-stu-id="d3396-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="d3396-149">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d3396-149">Next step</span></span>

![Passaggio 4: criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="d3396-151">Configurare i criteri di accesso condizionale per:</span><span class="sxs-lookup"><span data-stu-id="d3396-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="d3396-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3396-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="d3396-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3396-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="d3396-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d3396-154">SharePoint</span></span>](sharepoint-file-access-policies.md)
