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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'autenticazione a più fattori in Microsoft 365.
ms.openlocfilehash: cb425f3fd3d97dc0cd8815699bd22cb2540aed46
ms.sourcegitcommit: 09518b7c9146cda7fd42839ee644ad418d48491a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "49001514"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="3cb59-103">Autenticazione a più fattori per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb59-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="3cb59-104">Le password sono il metodo più comune per l'autenticazione di un accesso a un computer o a un servizio online, ma sono anche le più vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="3cb59-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="3cb59-105">Gli utenti possono scegliere password facili e utilizzare le stesse password per accedere a più accessi a computer e servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="3cb59-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="3cb59-106">Per fornire un ulteriore livello di sicurezza per gli accessi, è necessario utilizzare l'autenticazione a più fattori (AMF), che utilizza sia una password, che deve essere forte, sia un ulteriore metodo di verifica basato sui seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3cb59-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="3cb59-107">Qualcosa che si ha con voi che non è facilmente duplicato, ad esempio uno Smart Phone.</span><span class="sxs-lookup"><span data-stu-id="3cb59-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="3cb59-108">Qualcosa che si ha in modo univoco e biologicamente, ad esempio le impronte digitali, la faccia o altri attributi biometrici.</span><span class="sxs-lookup"><span data-stu-id="3cb59-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="3cb59-109">Il metodo di verifica aggiuntivo non viene utilizzato fino a quando la password dell'utente non è stata verificata.</span><span class="sxs-lookup"><span data-stu-id="3cb59-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="3cb59-110">Con AMF, anche se una password utente complessa è danneggiata, l'aggressore non ha lo Smart Phone o l'impronta digitale per completare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3cb59-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="3cb59-111">Supporto dell'AMF in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb59-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="3cb59-112">Per impostazione predefinita, sia Microsoft 365 che Office 365 supportano AMF per gli account utente utilizzando:</span><span class="sxs-lookup"><span data-stu-id="3cb59-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="3cb59-113">Un messaggio di testo inviato a un telefono che richiede all'utente di immettere un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="3cb59-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="3cb59-114">Una telefonata.</span><span class="sxs-lookup"><span data-stu-id="3cb59-114">A phone call.</span></span>
- <span data-ttu-id="3cb59-115">App Smart Phone Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3cb59-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="3cb59-116">In entrambi i casi, l'accesso dell'AMF utilizza il metodo "something you have with you that is not facilmente Duplicated" per la verifica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="3cb59-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="3cb59-117">Esistono diversi modi in cui è possibile abilitare l'AMF per Microsoft 365 e Office 365:</span><span class="sxs-lookup"><span data-stu-id="3cb59-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="3cb59-118">Con le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-118">With security defaults</span></span>
- <span data-ttu-id="3cb59-119">Con i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="3cb59-119">With Conditional Access policies</span></span>
- <span data-ttu-id="3cb59-120">Per ogni singolo account utente (non consigliato)</span><span class="sxs-lookup"><span data-stu-id="3cb59-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="3cb59-121">Questi modi si basano sul piano Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cb59-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="3cb59-122">Piano</span><span class="sxs-lookup"><span data-stu-id="3cb59-122">Plan</span></span>|<span data-ttu-id="3cb59-123">Consiglio</span><span class="sxs-lookup"><span data-stu-id="3cb59-123">Recommendation</span></span>|<span data-ttu-id="3cb59-124">Tipo di cliente</span><span class="sxs-lookup"><span data-stu-id="3cb59-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="3cb59-125">Tutti i piani di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb59-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="3cb59-126">Utilizzare le impostazioni predefinite per la sicurezza, che richiedono l'AMF per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="3cb59-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="3cb59-127">È inoltre possibile configurare l'autenticazione per utente su singoli account utente, ma non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="3cb59-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="3cb59-128">Azienda di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="3cb59-128">Small business</span></span>|
|<span data-ttu-id="3cb59-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3cb59-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="3cb59-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="3cb59-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="3cb59-131">Licenze P1 di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3cb59-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="3cb59-132">Utilizzare i criteri di accesso condizionale per richiedere l'utilizzo dell'AMF per gli account utente in base all'appartenenza ai gruppi, alle app o ad altri criteri.</span><span class="sxs-lookup"><span data-stu-id="3cb59-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="3cb59-133">Small Business to Enterprise</span><span class="sxs-lookup"><span data-stu-id="3cb59-133">Small business to enterprise</span></span>|
|<span data-ttu-id="3cb59-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3cb59-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="3cb59-135">Licenze P2 di Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="3cb59-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="3cb59-136">Usare Azure AD Identity Protection per richiedere l'utilizzo dell'AMF in base ai criteri di rischio di accesso.</span><span class="sxs-lookup"><span data-stu-id="3cb59-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="3cb59-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="3cb59-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="3cb59-138">Impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-138">Security defaults</span></span>

<span data-ttu-id="3cb59-139">Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="3cb59-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="3cb59-140">Sono state attivate le impostazioni predefinite per la sicurezza, che sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cb59-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="3cb59-141">Richiede a tutti gli utenti di utilizzare il master con l'app Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3cb59-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="3cb59-142">Blocca l'autenticazione legacy.</span><span class="sxs-lookup"><span data-stu-id="3cb59-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="3cb59-143">Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3cb59-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="3cb59-144">Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.</span><span class="sxs-lookup"><span data-stu-id="3cb59-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="3cb59-145">Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cb59-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="3cb59-146">È possibile disabilitare le impostazioni predefinite per la sicurezza in favore dell'AMF con criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="3cb59-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="3cb59-147">È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro delle **Proprietà** di Azure ad nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cb59-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Immagine della pagina delle proprietà della directory.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="3cb59-149">È possibile utilizzare le impostazioni predefinite di sicurezza con qualsiasi piano di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cb59-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="3cb59-150">Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="3cb59-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="3cb59-151">Criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="3cb59-151">Conditional Access policies</span></span>

<span data-ttu-id="3cb59-152">I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti.</span><span class="sxs-lookup"><span data-stu-id="3cb59-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="3cb59-153">Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:</span><span class="sxs-lookup"><span data-stu-id="3cb59-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="3cb59-154">Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3cb59-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="3cb59-155">Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3cb59-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="3cb59-156">È inoltre possibile utilizzare i criteri di accesso condizionale per funzionalità più avanzate, ad esempio l'utilizzo dell'AMF per specifiche app o l'esecuzione dell'accesso da un dispositivo compatibile, ad esempio il laptop che esegue Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3cb59-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="3cb59-157">È possibile configurare i criteri di accesso condizionale dal riquadro di **sicurezza** di Azure ad nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cb59-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Immagine dell'opzione di menu per l'accesso condizionale](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="3cb59-159">È possibile utilizzare i criteri di accesso condizionale con:</span><span class="sxs-lookup"><span data-stu-id="3cb59-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="3cb59-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3cb59-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="3cb59-161">Microsoft 365 E3 e E5</span><span class="sxs-lookup"><span data-stu-id="3cb59-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="3cb59-162">Licenze di Azure AD Premium P1 e Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="3cb59-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="3cb59-163">Per le aziende di piccole dimensioni con Microsoft 365 Business Premium, è possibile utilizzare facilmente i criteri di accesso condizionale con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cb59-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="3cb59-164">Creare un gruppo che contenga gli account utente che richiedono l'utilizzo dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="3cb59-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="3cb59-165">Abilitare il criterio **per gli amministratori globali per** l'autenticazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="3cb59-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="3cb59-166">Creare un criterio di accesso condizionale basato su gruppo con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3cb59-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="3cb59-167">Assegnazioni > utenti e gruppi: il nome del gruppo al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3cb59-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="3cb59-168">Assegnazioni > app o azioni cloud: tutte le app cloud.</span><span class="sxs-lookup"><span data-stu-id="3cb59-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="3cb59-169">I controlli di accesso > Grant > Grant Access > richiedono l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="3cb59-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="3cb59-170">Abilitazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="3cb59-170">Enable the policy.</span></span>
5. <span data-ttu-id="3cb59-171">Aggiungere un account utente al gruppo creato nel passaggio 1 sopra e testare.</span><span class="sxs-lookup"><span data-stu-id="3cb59-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="3cb59-172">Per richiedere l'utilizzo dell'AMF per account utente aggiuntivi, aggiungerli al gruppo creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3cb59-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="3cb59-173">Questo criterio di accesso condizionale consente di implementare il requisito dell'AMF per gli utenti a proprio piacimento.</span><span class="sxs-lookup"><span data-stu-id="3cb59-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="3cb59-174">Le aziende devono utilizzare [criteri di accesso condizionale comuni](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cb59-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="3cb59-175">Richiedere la MFA per amministratori</span><span class="sxs-lookup"><span data-stu-id="3cb59-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="3cb59-176">Richiedere la MFA per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="3cb59-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="3cb59-177">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="3cb59-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="3cb59-178">Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="3cb59-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="3cb59-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3cb59-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="3cb59-180">Con Azure AD Identity Protection, è possibile creare un ulteriore criterio di accesso condizionale per richiedere il livello di sicurezza [dell'AMF quando il rischio di iscrizione è medio o elevato](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="3cb59-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="3cb59-181">È possibile utilizzare i criteri di accesso condizionale di Azure AD Identity Protection e Risk-based con:</span><span class="sxs-lookup"><span data-stu-id="3cb59-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="3cb59-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3cb59-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="3cb59-183">Licenze P2 di Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="3cb59-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="3cb59-184">Per ulteriori informazioni, vedere questa [panoramica di Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="3cb59-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="3cb59-185">AMF per utente legacy (scelta non consigliata)</span><span class="sxs-lookup"><span data-stu-id="3cb59-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="3cb59-186">È consigliabile utilizzare i criteri di sicurezza o di accesso condizionale per richiedere l'autenticazione per l'account utente. Tuttavia, se una di queste non può essere utilizzata, Microsoft consiglia di utilizzare l'AMF per gli account utente che dispongono di ruoli di amministratore, in particolare il ruolo di amministratore globale, per qualsiasi sottoscrizione di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3cb59-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="3cb59-187">È possibile abilitare l'AMF per singoli account utente dal riquadro **utente attivo dell'interfaccia** di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cb59-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Immagine dell'opzione autenticazione a più fattori nella pagina utenti attivi](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="3cb59-189">Dopo essere stato abilitato, la volta successiva che l'utente accede, verrà richiesto di registrarsi per l'AMF e di scegliere e testare il metodo di verifica aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="3cb59-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="3cb59-190">Usare questi metodi insieme</span><span class="sxs-lookup"><span data-stu-id="3cb59-190">Using these methods together</span></span>

<span data-ttu-id="3cb59-191">Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza, criteri di accesso condizionale e impostazioni dell'account per utente.</span><span class="sxs-lookup"><span data-stu-id="3cb59-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="3cb59-192">Abilitato</span><span class="sxs-lookup"><span data-stu-id="3cb59-192">Enabled</span></span>|<span data-ttu-id="3cb59-193">Disattivato</span><span class="sxs-lookup"><span data-stu-id="3cb59-193">Disabled</span></span>|<span data-ttu-id="3cb59-194">Metodo di autenticazione secondario</span><span class="sxs-lookup"><span data-stu-id="3cb59-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="3cb59-195">**Impostazioni predefinite per la sicurezza**</span><span class="sxs-lookup"><span data-stu-id="3cb59-195">**Security defaults**</span></span>|<span data-ttu-id="3cb59-196">Non è possibile utilizzare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="3cb59-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="3cb59-197">È possibile utilizzare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="3cb59-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="3cb59-198">App Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3cb59-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="3cb59-199">**Criteri di accesso condizionale**</span><span class="sxs-lookup"><span data-stu-id="3cb59-199">**Conditional Access policies**</span></span>|<span data-ttu-id="3cb59-200">Se sono abilitati, non è possibile abilitare le impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="3cb59-201">Se sono tutti disabilitati, è possibile abilitare le impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="3cb59-202">Specificato dall'utente durante la registrazione della MFA</span><span class="sxs-lookup"><span data-stu-id="3cb59-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="3cb59-203">**AMF per utente legacy (scelta non consigliata)**</span><span class="sxs-lookup"><span data-stu-id="3cb59-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="3cb59-204">Esegue l'override delle impostazioni predefinite per la sicurezza e i criteri di accesso condizionale che richiedono l'AMF a ogni accesso</span><span class="sxs-lookup"><span data-stu-id="3cb59-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="3cb59-205">Sottoposto a override da criteri di accesso condizionale e impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="3cb59-206">Specificato dall'utente durante la registrazione della MFA</span><span class="sxs-lookup"><span data-stu-id="3cb59-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="3cb59-207">Se le impostazioni predefinite per la sicurezza sono abilitate, tutti i nuovi utenti vengono richieste per la registrazione dell'AMF e per l'utilizzo dell'app Microsoft Authenticator all'accesso successivo.</span><span class="sxs-lookup"><span data-stu-id="3cb59-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="3cb59-208">Modalità di gestione delle impostazioni dell'AMF</span><span class="sxs-lookup"><span data-stu-id="3cb59-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="3cb59-209">Esistono due modi per gestire le impostazioni dell'AMF.</span><span class="sxs-lookup"><span data-stu-id="3cb59-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="3cb59-210">Nel portale di Azure, è possibile:</span><span class="sxs-lookup"><span data-stu-id="3cb59-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="3cb59-211">Abilitare e disabilitare le impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cb59-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="3cb59-212">Configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="3cb59-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="3cb59-213">Nell'interfaccia di amministrazione di Microsoft 365, è possibile configurare le impostazioni dell'AMF per utente e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3cb59-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="3cb59-214">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3cb59-214">Your next step</span></span>

[<span data-ttu-id="3cb59-215">Configurare l'AMF per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cb59-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
