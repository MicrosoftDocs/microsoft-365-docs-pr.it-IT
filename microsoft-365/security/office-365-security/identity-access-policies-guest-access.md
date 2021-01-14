---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso degli utenti esterni e dei clienti all'utente esterno-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive l'accesso condizionale consigliato e i criteri correlati per la protezione dell'accesso degli utenti esterni e degli ospiti.
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845077"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="7a989-103">Criteri per consentire l'accesso degli utenti esterni e dell'utente esterno B2B</span><span class="sxs-lookup"><span data-stu-id="7a989-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="7a989-104">In questo articolo viene descritta la modifica dei criteri consigliati per il dispositivo e l'accesso alle identità per consentire l'accesso per gli utenti esterni e i clienti che dispongono di un account B2B di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7a989-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="7a989-105">Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7a989-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7a989-106">Tali raccomandazioni sono state progettate per essere applicate al livello di protezione di **base** .</span><span class="sxs-lookup"><span data-stu-id="7a989-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="7a989-107">Tuttavia, è anche possibile modificare le raccomandazioni in base alle proprie esigenze specifiche per una protezione **sensibile** e **altamente regolamentata** .</span><span class="sxs-lookup"><span data-stu-id="7a989-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="7a989-108">Fornire un percorso per gli account B2B per l'autenticazione con il tenant di Azure AD non consente agli account di accedere all'intero ambiente.</span><span class="sxs-lookup"><span data-stu-id="7a989-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="7a989-109">Gli utenti B2B e i loro account hanno accesso ai servizi e alle risorse, come i file, condivisi con il criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="7a989-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="7a989-110">Aggiornamento dei criteri comuni per consentire e proteggere gli ospiti e l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="7a989-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="7a989-111">In questo diagramma vengono illustrati i criteri da aggiungere o aggiornare tra i criteri di identità e accesso ai dispositivi comuni, per l'accesso degli utenti esterni e dell'utente esterno.</span><span class="sxs-lookup"><span data-stu-id="7a989-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="7a989-112">[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso Guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="7a989-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="7a989-113">Visualizzazione di una versione più grande di questa immagine</span><span class="sxs-lookup"><span data-stu-id="7a989-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="7a989-114">Nella tabella seguente sono elencati i criteri necessari per la creazione e l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7a989-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="7a989-115">I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="7a989-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7a989-116">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="7a989-116">Protection level</span></span>|<span data-ttu-id="7a989-117">Criteri</span><span class="sxs-lookup"><span data-stu-id="7a989-117">Policies</span></span>|<span data-ttu-id="7a989-118">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7a989-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="7a989-119">**Protezione di base**</span><span class="sxs-lookup"><span data-stu-id="7a989-119">**Baseline**</span></span>|[<span data-ttu-id="7a989-120">Richiedi sempre l'AMF per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="7a989-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7a989-121">Creare il nuovo criterio e configurare:</span><span class="sxs-lookup"><span data-stu-id="7a989-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="7a989-122">Per le **assegnazioni > gli utenti e i gruppi > includono**, scegliere **Seleziona utenti e gruppi**, quindi selezionare **tutti gli utenti guest ed esterni**.</span><span class="sxs-lookup"><span data-stu-id="7a989-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="7a989-123">Per le **assegnazioni > condizioni > l'accesso**, lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (AMF).</span><span class="sxs-lookup"><span data-stu-id="7a989-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="7a989-124">Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*</span><span class="sxs-lookup"><span data-stu-id="7a989-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7a989-125">Modificare questo criterio per escludere ospiti e utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7a989-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="7a989-126">Richiedere computer conformi</span><span class="sxs-lookup"><span data-stu-id="7a989-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7a989-127">Modificare questo criterio per escludere ospiti e utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7a989-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="7a989-128">Per includere o escludere ospiti e utenti esterni nei criteri di accesso condizionale, per le **assegnazioni > gli utenti e i gruppi > includere** o **escludere**, controllare **tutti gli utenti guest e esterni**.</span><span class="sxs-lookup"><span data-stu-id="7a989-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![acquisizione dello schermo dei controlli per l'esclusione di ospiti e utenti esterni](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="7a989-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7a989-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="7a989-131">Clienti e accesso utente esterno con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a989-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="7a989-132">Microsoft teams definisce gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a989-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="7a989-133">**Accesso Guest** utilizza un account di Azure ad B2B che può essere aggiunto come membro di un team e che ha accesso alle comunicazioni e alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="7a989-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="7a989-134">**L'accesso esterno** è per un utente esterno che non dispone di un account B2B.</span><span class="sxs-lookup"><span data-stu-id="7a989-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="7a989-135">L'accesso degli utenti esterni include gli inviti, le chiamate, le chat e le riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="7a989-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="7a989-136">Per ulteriori informazioni, vedere il [confronto tra gli utenti e l'accesso utente esterno per i team](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="7a989-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="7a989-137">Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per i team, vedere [Suggerimenti per i criteri per la protezione di chat, gruppi e file di Team](teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7a989-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="7a989-138">Richiedi sempre un master per utenti esterni e Guest</span><span class="sxs-lookup"><span data-stu-id="7a989-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="7a989-139">Questo criterio richiede agli utenti di registrarsi per l'AMF nel tenant, indipendentemente dal fatto che siano registrati per l'AMF nel tenant di casa.</span><span class="sxs-lookup"><span data-stu-id="7a989-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="7a989-140">Quando si accede alle risorse del tenant, è necessario che gli ospiti e gli utenti esterni utilizzino Mae per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="7a989-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="7a989-141">Esclusione degli ospiti e degli utenti esterni dall'AMF basata sui rischi</span><span class="sxs-lookup"><span data-stu-id="7a989-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="7a989-142">Sebbene le organizzazioni possano applicare criteri basati sui rischi per gli utenti B2B che utilizzano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory di risorse a causa della loro identità esistente nella Home Directory.</span><span class="sxs-lookup"><span data-stu-id="7a989-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="7a989-143">A causa di queste limitazioni, Microsoft consiglia di escludere gli ospiti dai criteri dell'AMF basati sui rischi e richiedere a questi utenti di utilizzare sempre il Mae.</span><span class="sxs-lookup"><span data-stu-id="7a989-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="7a989-144">Per ulteriori informazioni, vedere [limitazioni della protezione dell'identità per gli utenti di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="7a989-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="7a989-145">Esclusione di ospiti e utenti esterni dalla gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="7a989-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="7a989-146">Solo un'organizzazione può gestire un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a989-146">Only one organization can manage a device.</span></span> <span data-ttu-id="7a989-147">Se non si escludono gli ospiti e gli utenti esterni dai criteri che richiedono la conformità del dispositivo, questi criteri bloccherà tali utenti.</span><span class="sxs-lookup"><span data-stu-id="7a989-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="7a989-148">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7a989-148">Next step</span></span>

![Passaggio 4: criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="7a989-150">Configurare i criteri di accesso condizionale per:</span><span class="sxs-lookup"><span data-stu-id="7a989-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="7a989-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a989-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="7a989-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7a989-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="7a989-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a989-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
