---
title: Criteri di identità e di accesso ai dispositivi per consentire l'accesso B2B degli utenti guest ed esterni - Microsoft 365 per le aziende | Documenti Microsoft
description: Descrive l'accesso condizionale consigliato e i criteri correlati per la protezione dell'accesso di utenti guest e utenti esterni.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
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
ms.openlocfilehash: 0baefab441b17aa4a9527536cead181bae8f8948
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599996"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="13c60-103">Criteri per consentire l'accesso guest e l'accesso degli utenti esterni B2B</span><span class="sxs-lookup"><span data-stu-id="13c60-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="13c60-104">In questo articolo viene illustrata la modifica dei criteri di accesso alle identità e ai dispositivi consigliati per consentire l'accesso a utenti guest ed esterni con un account Business-to-Business (B2B) di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="13c60-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="13c60-105">Queste indicazioni si basano sui [criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="13c60-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="13c60-106">Questi suggerimenti sono progettati per essere applicati al livello **di protezione** di base.</span><span class="sxs-lookup"><span data-stu-id="13c60-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="13c60-107">Tuttavia, puoi anche modificare i suggerimenti in base alle tue esigenze specifiche per una **protezione sensibile** **e altamente regolamentata.**</span><span class="sxs-lookup"><span data-stu-id="13c60-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="13c60-108">Fornire un percorso per gli account B2B per l'autenticazione con il tenant di Azure AD non consente a questi account di accedere all'intero ambiente.</span><span class="sxs-lookup"><span data-stu-id="13c60-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="13c60-109">Gli utenti B2B e i loro account hanno accesso a servizi e risorse, come i file, condivisi con loro dai criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="13c60-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="13c60-110">Aggiornamento dei criteri comuni per consentire e proteggere gli utenti guest e gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="13c60-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="13c60-111">Questo diagramma mostra quali criteri aggiungere o aggiornare tra i criteri comuni di identità e accesso ai dispositivi, per l'accesso degli utenti guest ed esterni B2B.</span><span class="sxs-lookup"><span data-stu-id="13c60-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="13c60-112">[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="13c60-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="13c60-113">Nella tabella seguente sono elencati i criteri che è necessario creare e aggiornare.</span><span class="sxs-lookup"><span data-stu-id="13c60-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="13c60-114">I criteri comuni sono link alle istruzioni di configurazione associate [nell'articolo Criteri di identità](identity-access-policies.md) e accesso ai dispositivi comuni.</span><span class="sxs-lookup"><span data-stu-id="13c60-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="13c60-115">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="13c60-115">Protection level</span></span>|<span data-ttu-id="13c60-116">Criteri</span><span class="sxs-lookup"><span data-stu-id="13c60-116">Policies</span></span>|<span data-ttu-id="13c60-117">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="13c60-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="13c60-118">**Protezione di base**</span><span class="sxs-lookup"><span data-stu-id="13c60-118">**Baseline**</span></span>|[<span data-ttu-id="13c60-119">Richiedi MFA sempre per utenti guest ed esterni</span><span class="sxs-lookup"><span data-stu-id="13c60-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="13c60-120">Creare questo nuovo criterio e configurare:</span><span class="sxs-lookup"><span data-stu-id="13c60-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="13c60-121">Per **Assegnazioni > utenti** e gruppi > Includi , scegliere **Seleziona** utenti e gruppi e quindi selezionare Tutti gli utenti guest **ed esterni**.</span><span class="sxs-lookup"><span data-stu-id="13c60-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="13c60-122">Per **Assegnazioni > condizioni >** accesso , lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (MFA).</span><span class="sxs-lookup"><span data-stu-id="13c60-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="13c60-123">Richiedi autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="13c60-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="13c60-124">Modificare questo criterio per escludere utenti guest ed utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="13c60-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="13c60-125">Richiedere computer conformi</span><span class="sxs-lookup"><span data-stu-id="13c60-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="13c60-126">Modificare questo criterio per escludere utenti guest ed utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="13c60-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="13c60-127">Per includere o escludere utenti guest ed esterni nei criteri di accesso condizionale, per Assegnazioni **> Utenti** e gruppi > Includi o Escludi , selezionare Tutti gli utenti guest ed **esterni.** </span><span class="sxs-lookup"><span data-stu-id="13c60-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![acquisizione dello schermo dei controlli per l'esclusione di utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="13c60-129">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="13c60-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="13c60-130">Accesso guest e utente esterno con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c60-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="13c60-131">Microsoft Teams definisce gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="13c60-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="13c60-132">**L'accesso** guest usa un account B2B di Azure AD che può essere aggiunto come membro di un team e avere accesso alle comunicazioni e alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="13c60-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="13c60-133">**L'accesso** esterno è per un utente esterno che non dispone di un account B2B.</span><span class="sxs-lookup"><span data-stu-id="13c60-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="13c60-134">L'accesso degli utenti esterni include inviti, chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.</span><span class="sxs-lookup"><span data-stu-id="13c60-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="13c60-135">Per ulteriori informazioni, vedere il confronto [tra gli utenti guest e l'accesso degli utenti esterni per i team.](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="13c60-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="13c60-136">Per ulteriori informazioni sulla protezione di identità e criteri di accesso ai dispositivi per Teams, vedere Suggerimenti per i criteri per la protezione di chat, gruppi [e file di Teams.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="13c60-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="13c60-137">Richiedi MFA sempre per utenti guest ed esterni</span><span class="sxs-lookup"><span data-stu-id="13c60-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="13c60-138">Questo criterio richiede agli utenti guest di registrarsi per la MFA nel tenant, indipendentemente dal fatto che siano registrati per la MFA nel tenant principale.</span><span class="sxs-lookup"><span data-stu-id="13c60-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="13c60-139">Quando si accede alle risorse nel tenant, gli utenti guest e esterni devono utilizzare la MFA per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="13c60-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="13c60-140">Esclusione di utenti guest ed utenti esterni dall'autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="13c60-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="13c60-141">Sebbene le organizzazioni possano applicare criteri basati sul rischio per gli utenti B2B che usano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory delle risorse a causa della loro identità esistente nella home directory.</span><span class="sxs-lookup"><span data-stu-id="13c60-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="13c60-142">A causa di queste limitazioni, Microsoft consiglia di escludere gli utenti guest dai criteri MFA basati sul rischio e richiedere a questi utenti di utilizzare sempre la MFA.</span><span class="sxs-lookup"><span data-stu-id="13c60-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="13c60-143">Per ulteriori informazioni, vedere [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="13c60-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="13c60-144">Esclusione di utenti guest ed esterni dalla gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="13c60-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="13c60-145">Solo un'organizzazione può gestire un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="13c60-145">Only one organization can manage a device.</span></span> <span data-ttu-id="13c60-146">Se non escludi guest ed utenti esterni dai criteri che richiedono la conformità dei dispositivi, questi criteri bloccheranno questi utenti.</span><span class="sxs-lookup"><span data-stu-id="13c60-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="13c60-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="13c60-147">Next step</span></span>

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="13c60-149">Configurare i criteri di accesso condizionale per:</span><span class="sxs-lookup"><span data-stu-id="13c60-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="13c60-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c60-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="13c60-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="13c60-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="13c60-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="13c60-152">SharePoint</span></span>](sharepoint-file-access-policies.md)