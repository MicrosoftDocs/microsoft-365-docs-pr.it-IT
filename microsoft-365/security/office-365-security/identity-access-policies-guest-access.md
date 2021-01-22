---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso B2B degli utenti guest ed esterni - Microsoft 365 per le aziende | Microsoft Docs
description: Descrive l'accesso condizionale consigliato e i criteri correlati per proteggere l'accesso di utenti guest e utenti esterni.
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932611"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="777ea-103">Criteri per consentire l'accesso guest e l'accesso degli utenti esterni B2B</span><span class="sxs-lookup"><span data-stu-id="777ea-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="777ea-104">In questo articolo viene illustrata la modifica dei criteri di accesso alle identità e ai dispositivi consigliati per consentire l'accesso a utenti guest e esterni che dispongono di un account Business-to-Business (B2B) di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="777ea-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="777ea-105">Queste indicazioni si basano sui [criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="777ea-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="777ea-106">Questi suggerimenti sono progettati per essere applicati al livello **di protezione** di base.</span><span class="sxs-lookup"><span data-stu-id="777ea-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="777ea-107">Tuttavia, è anche possibile modificare i suggerimenti in base alle esigenze specifiche per la **protezione sensibile** **e altamente regolamentata.**</span><span class="sxs-lookup"><span data-stu-id="777ea-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="777ea-108">Fornire un percorso per l'autenticazione degli account B2B con il tenant di Azure AD non consente a questi account di accedere all'intero ambiente.</span><span class="sxs-lookup"><span data-stu-id="777ea-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="777ea-109">Gli utenti B2B e i relativi account hanno accesso a servizi e risorse, come i file, condivisi con loro dai criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="777ea-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="777ea-110">Aggiornamento dei criteri comuni per consentire e proteggere gli utenti guest e gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="777ea-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="777ea-111">Questo diagramma mostra quali criteri aggiungere o aggiornare tra i criteri comuni di identità e accesso ai dispositivi, per l'accesso degli utenti guest ed esterni B2B.</span><span class="sxs-lookup"><span data-stu-id="777ea-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="777ea-112">[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="777ea-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="777ea-113">Vedere una versione più grande di questa immagine</span><span class="sxs-lookup"><span data-stu-id="777ea-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="777ea-114">Nella tabella seguente sono elencati i criteri che è necessario creare e aggiornare.</span><span class="sxs-lookup"><span data-stu-id="777ea-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="777ea-115">I criteri comuni sono associati alle istruzioni di configurazione [nell'articolo Criteri comuni di](identity-access-policies.md) identità e accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="777ea-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="777ea-116">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="777ea-116">Protection level</span></span>|<span data-ttu-id="777ea-117">Criteri</span><span class="sxs-lookup"><span data-stu-id="777ea-117">Policies</span></span>|<span data-ttu-id="777ea-118">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="777ea-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="777ea-119">**Protezione di base**</span><span class="sxs-lookup"><span data-stu-id="777ea-119">**Baseline**</span></span>|[<span data-ttu-id="777ea-120">Richiedere l'autenticazione a più fattori sempre per utenti guest e esterni</span><span class="sxs-lookup"><span data-stu-id="777ea-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="777ea-121">Creare questo nuovo criterio e configurare:</span><span class="sxs-lookup"><span data-stu-id="777ea-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="777ea-122">Per **Assegnazioni > utenti** e gruppi >, scegliere Seleziona utenti e gruppi e quindi selezionare Tutti gli utenti guest ed **esterni.** </span><span class="sxs-lookup"><span data-stu-id="777ea-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="777ea-123">Per **Le assegnazioni > condizioni >** accesso , lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (MFA).</span><span class="sxs-lookup"><span data-stu-id="777ea-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="777ea-124">Richiedere l'autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="777ea-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="777ea-125">Modificare questo criterio per escludere utenti guest ed esterni.</span><span class="sxs-lookup"><span data-stu-id="777ea-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="777ea-126">Richiedere computer conformi</span><span class="sxs-lookup"><span data-stu-id="777ea-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="777ea-127">Modificare questo criterio per escludere utenti guest ed esterni.</span><span class="sxs-lookup"><span data-stu-id="777ea-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="777ea-128">Per includere o escludere utenti guest e utenti esterni nei criteri di accesso condizionale, per Assegnazioni **> Utenti** e gruppi > Includi o Escludi , selezionare Tutti gli utenti guest ed **esterni.** </span><span class="sxs-lookup"><span data-stu-id="777ea-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![acquisizione schermo di controlli per escludere utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="777ea-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="777ea-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="777ea-131">Accesso degli utenti guest e esterni con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="777ea-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="777ea-132">Microsoft Teams definisce gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="777ea-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="777ea-133">**L'accesso** guest usa un account B2B di Azure AD che può essere aggiunto come membro di un team e avere accesso alle comunicazioni e alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="777ea-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="777ea-134">**L'accesso** esterno è per un utente esterno che non dispone di un account B2B.</span><span class="sxs-lookup"><span data-stu-id="777ea-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="777ea-135">L'accesso degli utenti esterni include inviti, chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="777ea-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="777ea-136">Per ulteriori informazioni, vedere il confronto [tra gli utenti guest e l'accesso degli utenti esterni per i team.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="777ea-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="777ea-137">Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per Teams, vedere Suggerimenti sui criteri per la protezione di [chat, gruppi e file di Teams.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="777ea-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="777ea-138">Richiedere l'autenticazione a più fattori sempre per gli utenti guest ed esterni</span><span class="sxs-lookup"><span data-stu-id="777ea-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="777ea-139">Questo criterio richiede agli utenti guest di registrarsi per l'autenticazione a più fattori nel tenant, indipendentemente dal fatto che siano registrati per l'autenticazione a più fattori nel tenant principale.</span><span class="sxs-lookup"><span data-stu-id="777ea-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="777ea-140">Quando si accede alle risorse nel tenant, gli utenti guest e esterni devono usare l'autenticazione a più fattori per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="777ea-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="777ea-141">Esclusione di utenti guest ed esterni dall'autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="777ea-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="777ea-142">Anche se le organizzazioni possono applicare criteri basati sul rischio per gli utenti B2B che usano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory delle risorse a causa della loro identità esistente nella home directory.</span><span class="sxs-lookup"><span data-stu-id="777ea-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="777ea-143">A causa di queste limitazioni, Microsoft consiglia di escludere gli utenti guest dai criteri MFA basati sul rischio e di richiedere a questi utenti di usare sempre l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="777ea-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="777ea-144">Per ulteriori informazioni, vedere [Limitations of Identity Protection for B2B collaboration users.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="777ea-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="777ea-145">Esclusione di utenti guest ed esterni dalla gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="777ea-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="777ea-146">Solo un'organizzazione può gestire un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="777ea-146">Only one organization can manage a device.</span></span> <span data-ttu-id="777ea-147">Se non si escludono utenti guest e utenti esterni dai criteri che richiedono la conformità dei dispositivi, questi criteri bloccheranno questi utenti.</span><span class="sxs-lookup"><span data-stu-id="777ea-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="777ea-148">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="777ea-148">Next step</span></span>

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="777ea-150">Configurare i criteri di accesso condizionale per:</span><span class="sxs-lookup"><span data-stu-id="777ea-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="777ea-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="777ea-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="777ea-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="777ea-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="777ea-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="777ea-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
