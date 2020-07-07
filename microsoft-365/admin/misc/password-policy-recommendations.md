---
title: Suggerimenti sui criteri delle password
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Informazioni su come rendere più sicura l'organizzazione da attacchi alle password e perché è necessario bloccare le password comuni e abilitare l'autenticazione a più fattori basata sul rischio.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015924"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="b7130-103">Suggerimenti sui criteri delle password</span><span class="sxs-lookup"><span data-stu-id="b7130-103">Password policy recommendations</span></span>
 
<span data-ttu-id="b7130-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="b7130-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="b7130-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span><span class="sxs-lookup"><span data-stu-id="b7130-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="b7130-106">Per determinare la frequenza di scadenza delle password di Microsoft 365 nella propria organizzazione, vedere [Impostare i criteri di scadenza delle password per Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b7130-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="b7130-107">Per altre informazioni sulle password per Microsoft 365, vedere gli [articoli correlati](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="b7130-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="b7130-108">Informazioni sui suggerimenti per la scelta della password</span><span class="sxs-lookup"><span data-stu-id="b7130-108">Understanding password recommendations</span></span>

<span data-ttu-id="b7130-109">I criteri per l'impostazione di password efficaci rientrano in tre ampie categorie:</span><span class="sxs-lookup"><span data-stu-id="b7130-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="b7130-110">**Resistenza agli attacchi più comuni** Questo criterio implica la scelta della posizione in cui gli utenti immettono le password (dispositivi noti e attendibili con un buon sistema di rilevamento del malware e siti convalidati) e la scelta della password stessa (lunghezza e univocità).</span><span class="sxs-lookup"><span data-stu-id="b7130-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="b7130-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span><span class="sxs-lookup"><span data-stu-id="b7130-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="b7130-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span><span class="sxs-lookup"><span data-stu-id="b7130-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="b7130-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span><span class="sxs-lookup"><span data-stu-id="b7130-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="b7130-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span><span class="sxs-lookup"><span data-stu-id="b7130-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="b7130-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span><span class="sxs-lookup"><span data-stu-id="b7130-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="b7130-116">Linee guida per le password per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="b7130-116">Password guidelines for administrators</span></span>

<span data-ttu-id="b7130-117">The primary goal of a more secure password system is password diversity.</span><span class="sxs-lookup"><span data-stu-id="b7130-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="b7130-118">You want your password policy to contain lots of different and hard to guess passwords.</span><span class="sxs-lookup"><span data-stu-id="b7130-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="b7130-119">Here are a few recommendations for keeping your organization as secure as possible.</span><span class="sxs-lookup"><span data-stu-id="b7130-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="b7130-120">Mantenere il requisito di lunghezza minima di 8 caratteri (una password più lunga non è necessariamente migliore)</span><span class="sxs-lookup"><span data-stu-id="b7130-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="b7130-121">Don't require character composition requirements.</span><span class="sxs-lookup"><span data-stu-id="b7130-121">Don't require character composition requirements.</span></span> <span data-ttu-id="b7130-122">For example, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="b7130-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="b7130-123">Non richiedere la reimpostazione periodica obbligatoria delle password degli account utente</span><span class="sxs-lookup"><span data-stu-id="b7130-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="b7130-124">Vietare le password comuni per tenere fuori dal sistema le password più vulnerabili</span><span class="sxs-lookup"><span data-stu-id="b7130-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="b7130-125">Educare gli utenti a non riutilizzare la password aziendale per scopi non correlati al lavoro</span><span class="sxs-lookup"><span data-stu-id="b7130-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="b7130-126">Attivare la registrazione per l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="b7130-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="b7130-127">Abilitare le richieste di autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="b7130-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="b7130-128">Linee guida per le password per gli utenti</span><span class="sxs-lookup"><span data-stu-id="b7130-128">Password guidance for your users</span></span>

<span data-ttu-id="b7130-129">Here's some password guidance for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="b7130-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="b7130-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span><span class="sxs-lookup"><span data-stu-id="b7130-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="b7130-131">Non usare una password uguale o simile a una password usata in un altro sito Web</span><span class="sxs-lookup"><span data-stu-id="b7130-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="b7130-132">Non usare una sola parola, ad esempio **password**, o una frase di uso comune, come **Iloveyou**</span><span class="sxs-lookup"><span data-stu-id="b7130-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="b7130-133">Creare password difficili da indovinare anche da parte di persone molto intime, evitando ad esempio nomi e compleanni di amici e familiari, il gruppo musicale preferito e frasi usate spesso</span><span class="sxs-lookup"><span data-stu-id="b7130-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="b7130-134">Alcuni approcci comuni e impatti negativi</span><span class="sxs-lookup"><span data-stu-id="b7130-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="b7130-135">Di seguito sono descritte alcune delle procedure di gestione delle password più usate, tuttavia le ricerche condotte hanno portato alla luce alcuni impatti negativi.</span><span class="sxs-lookup"><span data-stu-id="b7130-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="b7130-136">Requisiti per la scadenza delle password degli utenti</span><span class="sxs-lookup"><span data-stu-id="b7130-136">Password expiration requirements for users</span></span>

<span data-ttu-id="b7130-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span><span class="sxs-lookup"><span data-stu-id="b7130-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="b7130-138">In these cases, the next password can be predicted based on the previous password.</span><span class="sxs-lookup"><span data-stu-id="b7130-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="b7130-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span><span class="sxs-lookup"><span data-stu-id="b7130-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="b7130-140">Requisiti di lunghezza delle password</span><span class="sxs-lookup"><span data-stu-id="b7130-140">Requiring long passwords</span></span>

<span data-ttu-id="b7130-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span><span class="sxs-lookup"><span data-stu-id="b7130-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="b7130-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span><span class="sxs-lookup"><span data-stu-id="b7130-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="b7130-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span><span class="sxs-lookup"><span data-stu-id="b7130-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="b7130-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span><span class="sxs-lookup"><span data-stu-id="b7130-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="b7130-145">Requisiti di complessità delle password (uso di più set di caratteri)</span><span class="sxs-lookup"><span data-stu-id="b7130-145">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="b7130-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span><span class="sxs-lookup"><span data-stu-id="b7130-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="b7130-147">Most systems enforce some level of password complexity requirements.</span><span class="sxs-lookup"><span data-stu-id="b7130-147">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="b7130-148">For example, passwords need characters from all three of the following categories:</span><span class="sxs-lookup"><span data-stu-id="b7130-148">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="b7130-149">caratteri maiuscoli</span><span class="sxs-lookup"><span data-stu-id="b7130-149">uppercase characters</span></span>

- <span data-ttu-id="b7130-150">caratteri minuscoli</span><span class="sxs-lookup"><span data-stu-id="b7130-150">lowercase characters</span></span>

- <span data-ttu-id="b7130-151">caratteri non alfanumerici</span><span class="sxs-lookup"><span data-stu-id="b7130-151">non-alphanumeric characters</span></span>

<span data-ttu-id="b7130-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span><span class="sxs-lookup"><span data-stu-id="b7130-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="b7130-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span><span class="sxs-lookup"><span data-stu-id="b7130-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="b7130-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span><span class="sxs-lookup"><span data-stu-id="b7130-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="b7130-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span><span class="sxs-lookup"><span data-stu-id="b7130-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="b7130-156">Criteri efficaci</span><span class="sxs-lookup"><span data-stu-id="b7130-156">Successful Patterns</span></span>

<span data-ttu-id="b7130-157">Ecco alcuni suggerimenti volti a incoraggiare la diversità delle password.</span><span class="sxs-lookup"><span data-stu-id="b7130-157">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="b7130-158">Vietare le password comuni</span><span class="sxs-lookup"><span data-stu-id="b7130-158">Ban common passwords</span></span>

<span data-ttu-id="b7130-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span><span class="sxs-lookup"><span data-stu-id="b7130-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="b7130-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span><span class="sxs-lookup"><span data-stu-id="b7130-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="b7130-161">Educare gli utenti a non riutilizzare le password aziendali in altre posizioni</span><span class="sxs-lookup"><span data-stu-id="b7130-161">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="b7130-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span><span class="sxs-lookup"><span data-stu-id="b7130-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="b7130-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span><span class="sxs-lookup"><span data-stu-id="b7130-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="b7130-164">Attivare la registrazione dell'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="b7130-164">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="b7130-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span><span class="sxs-lookup"><span data-stu-id="b7130-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="b7130-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span><span class="sxs-lookup"><span data-stu-id="b7130-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="b7130-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span><span class="sxs-lookup"><span data-stu-id="b7130-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="b7130-168">Per altre informazioni, vedere [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b7130-168">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="b7130-169">Abilitare l'autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="b7130-169">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="b7130-170">Con l'autenticazione a più fattori basata sul rischio, quando il sistema rileva un'attività sospetta richiede all'utente di provare di essere il legittimo proprietario dell'account.</span><span class="sxs-lookup"><span data-stu-id="b7130-170">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="b7130-171">Servono altre informazioni?</span><span class="sxs-lookup"><span data-stu-id="b7130-171">Want to know more?</span></span> <span data-ttu-id="b7130-172">Letture consigliate (in inglese)</span><span class="sxs-lookup"><span data-stu-id="b7130-172">Recommended reading</span></span>

- [<span data-ttu-id="b7130-173">Le password Web complesse sono davvero utili?</span><span class="sxs-lookup"><span data-stu-id="b7130-173">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="b7130-174">Gestire un portfolio di password e semplificare la vita agli utenti</span><span class="sxs-lookup"><span data-stu-id="b7130-174">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="b7130-175">Evitare l'uso di password vulnerabili studiando il comportamento degli utenti</span><span class="sxs-lookup"><span data-stu-id="b7130-175">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="b7130-176">Scelta di password sicure</span><span class="sxs-lookup"><span data-stu-id="b7130-176">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="b7130-177">Discussione sulla modifica obbligatoria della password</span><span class="sxs-lookup"><span data-stu-id="b7130-177">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="b7130-178">Le peggiori password del 2015</span><span class="sxs-lookup"><span data-stu-id="b7130-178">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [<span data-ttu-id="b7130-179">Scaricare file dal Web</span><span class="sxs-lookup"><span data-stu-id="b7130-179">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a><span data-ttu-id="b7130-180">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b7130-180">Related articles</span></span>

[<span data-ttu-id="b7130-181">Reimpostare password</span><span class="sxs-lookup"><span data-stu-id="b7130-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="b7130-182">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="b7130-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="b7130-183">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="b7130-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="b7130-184">Inviare nuovamente la password utente - Guida per amministratori</span><span class="sxs-lookup"><span data-stu-id="b7130-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
