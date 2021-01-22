---
title: Autenticazione a più fattori per Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'autenticazione a più fattori in Microsoft 365.
ms.openlocfilehash: 7d62d88acb5137bd0674de7a42b44103bc9fc5f0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926547"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="06f73-103">Autenticazione a più fattori per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06f73-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="06f73-104">Le password sono il metodo più comune per autenticare un accesso a un computer o a un servizio online, ma sono anche i più vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="06f73-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="06f73-105">Gli utenti possono scegliere password semplici e usare le stesse password per più accesso a computer e servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="06f73-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="06f73-106">Per fornire un ulteriore livello di sicurezza per gli accesso, è necessario utilizzare l'autenticazione a più fattori (MFA), che usa sia una password, che dovrebbe essere complessa, sia un metodo di verifica aggiuntivo basato su:</span><span class="sxs-lookup"><span data-stu-id="06f73-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="06f73-107">Qualcosa che non è facilmente duplicato, ad esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="06f73-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="06f73-108">Qualcosa che hai in modo univoco e in modo biologico, ad esempio le impronte digitali, il volto o altri attributi biometrici.</span><span class="sxs-lookup"><span data-stu-id="06f73-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="06f73-109">Il metodo di verifica aggiuntivo viene utilizzato solo dopo la verifica della password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="06f73-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="06f73-110">Con l'autenticazione a più fattori, anche se una password utente complessa è compromessa, l'autore dell'attacco non ha lo smartphone o l'impronta digitale per completare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="06f73-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="06f73-111">Supporto MFA in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06f73-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="06f73-112">Per impostazione predefinita, Sia Microsoft 365 che Office 365 supportano l'autenticazione a più fattori per gli account utente tramite:</span><span class="sxs-lookup"><span data-stu-id="06f73-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="06f73-113">UN SMS inviato a un telefono che richiede all'utente di digitare un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="06f73-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="06f73-114">Una telefonata.</span><span class="sxs-lookup"><span data-stu-id="06f73-114">A phone call.</span></span>
- <span data-ttu-id="06f73-115">App Microsoft Authenticator per smart phone.</span><span class="sxs-lookup"><span data-stu-id="06f73-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="06f73-116">In entrambi i casi, l'accesso all'autenticazione a più fattori usa il metodo "qualcosa che non è facilmente duplicato" per la verifica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="06f73-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="06f73-117">Esistono diversi modi in cui è possibile abilitare l'autenticazione a più fattori per Microsoft 365 e Office 365:</span><span class="sxs-lookup"><span data-stu-id="06f73-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="06f73-118">Con le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="06f73-118">With security defaults</span></span>
- <span data-ttu-id="06f73-119">Con i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-119">With Conditional Access policies</span></span>
- <span data-ttu-id="06f73-120">Per ogni singolo account utente (scelta non consigliata)</span><span class="sxs-lookup"><span data-stu-id="06f73-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="06f73-121">Questi modi si basano sul piano di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06f73-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="06f73-122">Piano</span><span class="sxs-lookup"><span data-stu-id="06f73-122">Plan</span></span>|<span data-ttu-id="06f73-123">Consiglio</span><span class="sxs-lookup"><span data-stu-id="06f73-123">Recommendation</span></span>|<span data-ttu-id="06f73-124">Tipo di cliente</span><span class="sxs-lookup"><span data-stu-id="06f73-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="06f73-125">Tutti i piani di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06f73-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="06f73-126">Usa le impostazioni predefinite di sicurezza, che richiedono l'autenticazione a più fattori per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="06f73-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="06f73-127">È anche possibile configurare l'autenticazione a più fattori per utente nei singoli account utente, ma questa operazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="06f73-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="06f73-128">Azienda di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="06f73-128">Small business</span></span>|
|<span data-ttu-id="06f73-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="06f73-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="06f73-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="06f73-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="06f73-131">Licenze di Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="06f73-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="06f73-132">Usa i criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account utente in base all'appartenenza ai gruppi, alle app o ad altri criteri.</span><span class="sxs-lookup"><span data-stu-id="06f73-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="06f73-133">Da piccole imprese a imprese</span><span class="sxs-lookup"><span data-stu-id="06f73-133">Small business to enterprise</span></span>|
|<span data-ttu-id="06f73-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="06f73-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="06f73-135">Licenze di Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="06f73-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="06f73-136">Usare Azure AD Identity Protection per richiedere l'autenticazione a più fattori in base ai criteri di rischio di accesso.</span><span class="sxs-lookup"><span data-stu-id="06f73-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="06f73-137">Grandi aziende</span><span class="sxs-lookup"><span data-stu-id="06f73-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="06f73-138">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="06f73-138">Security defaults</span></span>

<span data-ttu-id="06f73-139">Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="06f73-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="06f73-140">Per queste sottoscrizioni sono attivate le impostazioni predefinite di sicurezza, che:</span><span class="sxs-lookup"><span data-stu-id="06f73-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="06f73-141">Richiede a tutti gli utenti di usare l'autenticazione a più fattori con l'app Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="06f73-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="06f73-142">Blocca l'autenticazione legacy.</span><span class="sxs-lookup"><span data-stu-id="06f73-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="06f73-143">Per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, gli utenti hanno a disposizione 14 giorni dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="06f73-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="06f73-144">Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.</span><span class="sxs-lookup"><span data-stu-id="06f73-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="06f73-145">Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="06f73-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="06f73-146">Puoi disabilitare le impostazioni predefinite di sicurezza a favore dell'autenticazione a più fattori con i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="06f73-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="06f73-147">Le impostazioni predefinite di sicurezza vengono abilitate o disabilitate **dal** riquadro Proprietà di Azure AD nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="06f73-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Immagine della pagina delle proprietà della directory.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="06f73-149">È possibile usare le impostazioni predefinite di sicurezza con qualsiasi piano di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06f73-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="06f73-150">Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="06f73-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="06f73-151">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-151">Conditional Access policies</span></span>

<span data-ttu-id="06f73-152">I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti.</span><span class="sxs-lookup"><span data-stu-id="06f73-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="06f73-153">Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:</span><span class="sxs-lookup"><span data-stu-id="06f73-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="06f73-154">Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="06f73-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="06f73-155">Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="06f73-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="06f73-156">Puoi anche usare i criteri di accesso condizionale per funzionalità più avanzate, ad esempio la richiesta dell'autenticazione a più fattori per app specifiche o che l'accesso viene eseguito da un dispositivo conforme, ad esempio il portatile che esegue Windows 10.</span><span class="sxs-lookup"><span data-stu-id="06f73-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="06f73-157">È possibile configurare i criteri di accesso condizionale **dal** riquadro Sicurezza per Azure AD nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="06f73-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Immagine dell'opzione di menu per l'accesso condizionale](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="06f73-159">È possibile utilizzare i criteri di accesso condizionale con:</span><span class="sxs-lookup"><span data-stu-id="06f73-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="06f73-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="06f73-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="06f73-161">Microsoft 365 E3 e E5</span><span class="sxs-lookup"><span data-stu-id="06f73-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="06f73-162">Licenze di Azure AD Premium P1 e Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="06f73-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="06f73-163">Per le piccole imprese con Microsoft 365 Business Premium, è possibile usare facilmente i criteri di accesso condizionale con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="06f73-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="06f73-164">Creare un gruppo per contenere gli account utente che richiedono l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="06f73-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="06f73-165">Abilitare il **criterio Richiedi MFA per gli amministratori** globali.</span><span class="sxs-lookup"><span data-stu-id="06f73-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="06f73-166">Creare un criterio di accesso condizionale basato su gruppo con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="06f73-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="06f73-167">Assegnazioni > utenti e gruppi: nome del gruppo dal passaggio 1 precedente.</span><span class="sxs-lookup"><span data-stu-id="06f73-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="06f73-168">Assegnazioni > app cloud o azioni: tutte le app cloud.</span><span class="sxs-lookup"><span data-stu-id="06f73-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="06f73-169">I controlli di > concedi > l'accesso > richiedere l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="06f73-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="06f73-170">Abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="06f73-170">Enable the policy.</span></span>
5. <span data-ttu-id="06f73-171">Aggiungere un account utente al gruppo creato nel passaggio 1 precedente e testare.</span><span class="sxs-lookup"><span data-stu-id="06f73-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="06f73-172">Per richiedere l'autenticazione a più fattori per altri account utente, aggiungerli al gruppo creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="06f73-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="06f73-173">Questo criterio di accesso condizionale consente di implementare il requisito MFA per gli utenti al proprio ritmo.</span><span class="sxs-lookup"><span data-stu-id="06f73-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="06f73-174">Le aziende devono utilizzare [i criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) comuni per configurare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="06f73-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="06f73-175">Richiedere la MFA per amministratori</span><span class="sxs-lookup"><span data-stu-id="06f73-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="06f73-176">Richiedere la MFA per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="06f73-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="06f73-177">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="06f73-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="06f73-178">Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="06f73-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="06f73-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="06f73-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="06f73-180">Con Azure AD Identity Protection, è possibile creare un criterio di accesso condizionale aggiuntivo per richiedere l'autenticazione a più fattori quando il rischio di accesso [è medio o alto.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="06f73-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="06f73-181">È possibile usare Azure AD Identity Protection e i criteri di accesso condizionale basati sul rischio con:</span><span class="sxs-lookup"><span data-stu-id="06f73-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="06f73-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="06f73-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="06f73-183">Licenze di Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="06f73-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="06f73-184">Per ulteriori informazioni, vedere questa [panoramica di Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="06f73-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="06f73-185">MFA legacy per utente (scelta non consigliata)</span><span class="sxs-lookup"><span data-stu-id="06f73-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="06f73-186">Dovresti usare le impostazioni predefinite di sicurezza o i criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli accessi all'account utente. Tuttavia, se uno di questi non può essere utilizzato, Microsoft consiglia vivamente l'autenticazione a più fattori per gli account utente con ruoli di amministratore, in particolare il ruolo di amministratore globale, per qualsiasi sottoscrizione di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="06f73-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="06f73-187">L'autenticazione a più fattori viene abilitata per i singoli account utente dal riquadro **Utenti** attivi dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06f73-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Immagine dell'opzione Autenticazione a più fattori nella pagina Utenti attivi](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="06f73-189">Dopo essere stato abilitato, al successivo accesso dell'utente verrà richiesto di registrarsi per l'autenticazione a più fattori e di scegliere e testare il metodo di verifica aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="06f73-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="06f73-190">Usare questi metodi insieme</span><span class="sxs-lookup"><span data-stu-id="06f73-190">Using these methods together</span></span>

<span data-ttu-id="06f73-191">Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza, criteri di accesso condizionale e impostazioni dell'account per utente.</span><span class="sxs-lookup"><span data-stu-id="06f73-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="06f73-192">Abilitato</span><span class="sxs-lookup"><span data-stu-id="06f73-192">Enabled</span></span>|<span data-ttu-id="06f73-193">Disattivato</span><span class="sxs-lookup"><span data-stu-id="06f73-193">Disabled</span></span>|<span data-ttu-id="06f73-194">Metodo di autenticazione secondario</span><span class="sxs-lookup"><span data-stu-id="06f73-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="06f73-195">**Impostazioni predefinite per la sicurezza**</span><span class="sxs-lookup"><span data-stu-id="06f73-195">**Security defaults**</span></span>|<span data-ttu-id="06f73-196">Non è possibile utilizzare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="06f73-197">È possibile utilizzare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="06f73-198">App Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="06f73-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="06f73-199">**Criteri di accesso condizionale**</span><span class="sxs-lookup"><span data-stu-id="06f73-199">**Conditional Access policies**</span></span>|<span data-ttu-id="06f73-200">Se sono abilitate, non è possibile abilitare le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="06f73-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="06f73-201">Se sono tutti disabilitati, è possibile abilitare le impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="06f73-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="06f73-202">Specificato dall'utente durante la registrazione della MFA</span><span class="sxs-lookup"><span data-stu-id="06f73-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="06f73-203">**MFA legacy per utente (scelta non consigliata)**</span><span class="sxs-lookup"><span data-stu-id="06f73-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="06f73-204">Sostituisce le impostazioni predefinite di sicurezza e i criteri di accesso condizionale che richiedono l'autenticazione a più fattori a ogni accesso</span><span class="sxs-lookup"><span data-stu-id="06f73-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="06f73-205">Ignorato dalle impostazioni predefinite di sicurezza e dai criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="06f73-206">Specificato dall'utente durante la registrazione della MFA</span><span class="sxs-lookup"><span data-stu-id="06f73-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="06f73-207">Se le impostazioni predefinite di sicurezza sono abilitate, a tutti i nuovi utenti viene richiesta la registrazione dell'autenticazione a più fattori e l'uso dell'app Microsoft Authenticator al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="06f73-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="06f73-208">Modalità di gestione delle impostazioni MFA</span><span class="sxs-lookup"><span data-stu-id="06f73-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="06f73-209">Esistono due modi per gestire le impostazioni MFA.</span><span class="sxs-lookup"><span data-stu-id="06f73-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="06f73-210">Nel portale di Azure è possibile:</span><span class="sxs-lookup"><span data-stu-id="06f73-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="06f73-211">Abilitare e disabilitare le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="06f73-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="06f73-212">Configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="06f73-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="06f73-213">Nell'interfaccia di amministrazione di Microsoft 365, è possibile configurare le impostazioni MFA per utente e servizio.</span><span class="sxs-lookup"><span data-stu-id="06f73-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="06f73-214">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="06f73-214">Your next step</span></span>

[<span data-ttu-id="06f73-215">Configurare l'autenticazione a più fattori per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06f73-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
