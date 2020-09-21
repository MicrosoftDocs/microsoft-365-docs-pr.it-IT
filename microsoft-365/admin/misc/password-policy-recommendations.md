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
ms.openlocfilehash: 0ae26dc27cc698c24d999acde03f63f9cfead081
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131943"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="f47ab-103">Suggerimenti sui criteri delle password</span><span class="sxs-lookup"><span data-stu-id="f47ab-103">Password policy recommendations</span></span>

<span data-ttu-id="f47ab-p101">L'amministratore di un'organizzazione ha la responsabilità di impostare i criteri delle password per gli utenti. Questo articolo fornisce indicazioni su come eseguire questa procedura, che può essere complicata, e suggerimenti per rafforzare la protezione dell'organizzazione dagli attacchi contro le password.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p101">As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="f47ab-106">Per determinare la frequenza di scadenza delle password di Microsoft 365 nella propria organizzazione, vedere [Impostare i criteri di scadenza delle password per Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f47ab-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="f47ab-107">Per altre informazioni sulle password per Microsoft 365, vedere gli [articoli correlati](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="f47ab-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="f47ab-108">Informazioni sui suggerimenti per la scelta della password</span><span class="sxs-lookup"><span data-stu-id="f47ab-108">Understanding password recommendations</span></span>

<span data-ttu-id="f47ab-109">I criteri per l'impostazione di password efficaci rientrano in tre ampie categorie:</span><span class="sxs-lookup"><span data-stu-id="f47ab-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="f47ab-110">**Resistenza agli attacchi più comuni** Questo criterio implica la scelta della posizione in cui gli utenti immettono le password (dispositivi noti e attendibili con un buon sistema di rilevamento del malware e siti convalidati) e la scelta della password stessa (lunghezza e univocità).</span><span class="sxs-lookup"><span data-stu-id="f47ab-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="f47ab-p102">**Contenimento degli attacchi riusciti** Con contenimento degli attacchi riusciti si intende la limitazione dell'esposizione a un servizio specifico o la prevenzione totale del danno, in caso di furto della password di un utente. Significa ad esempio impedire che una violazione delle credenziali di social networking renda vulnerabile il conto corrente bancario o che un account poco sicuro accetti collegamenti di reimpostazione per un account importante.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p102">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="f47ab-p103">**Comprensione della natura umana** Molti criteri di scelta della password, per quanto validi, soccombono di fronte al comportamento delle persone. La comprensione della natura umana è fondamentale, in quanto la ricerca dimostra che quasi tutte le regole imposte agli utenti non fanno che impoverire la qualità delle password. I requisiti relativi a lunghezza, caratteri speciali e modifica della password causano tutti una normalizzazione delle password, che rende più semplice ai pirati informatici l'impresa di indovinare o violare le password.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p103">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="f47ab-116">Linee guida per le password per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="f47ab-116">Password guidelines for administrators</span></span>

<span data-ttu-id="f47ab-p104">L'obiettivo principale di un sistema di password più sicuro è la diversità delle password. I criteri per le password dovrebbero contenere moltissime password diverse e difficili da indovinare. Ecco alcuni suggerimenti per garantire la massima sicurezza possibile per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p104">The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="f47ab-120">Mantenere il requisito di lunghezza minima di 8 caratteri (una password più lunga non è necessariamente migliore)</span><span class="sxs-lookup"><span data-stu-id="f47ab-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="f47ab-p105">Non impostare requisiti di composizione dei caratteri, ad esempio \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="f47ab-p105">Don't require character composition requirements. For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="f47ab-123">Non richiedere la reimpostazione periodica obbligatoria delle password degli account utente</span><span class="sxs-lookup"><span data-stu-id="f47ab-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="f47ab-124">Vietare le password comuni per tenere fuori dal sistema le password più vulnerabili</span><span class="sxs-lookup"><span data-stu-id="f47ab-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="f47ab-125">Educare gli utenti a non riutilizzare la password aziendale per scopi non correlati al lavoro</span><span class="sxs-lookup"><span data-stu-id="f47ab-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="f47ab-126">Attivare la registrazione per l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="f47ab-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="f47ab-127">Abilitare le richieste di autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="f47ab-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="f47ab-128">Linee guida per le password per gli utenti</span><span class="sxs-lookup"><span data-stu-id="f47ab-128">Password guidance for your users</span></span>

<span data-ttu-id="f47ab-p106">Ecco alcune indicazioni per l'impostazione delle password per gli utenti dell'organizzazione. Assicurarsi che gli utenti conoscano questi suggerimenti e applichino i criteri di impostazione delle password consigliati nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p106">Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="f47ab-131">Non usare una password uguale o simile a una password usata in un altro sito Web</span><span class="sxs-lookup"><span data-stu-id="f47ab-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="f47ab-132">Non usare una sola parola, ad esempio **password**, o una frase di uso comune, come **Iloveyou**</span><span class="sxs-lookup"><span data-stu-id="f47ab-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="f47ab-133">Creare password difficili da indovinare anche da parte di persone molto intime, evitando ad esempio nomi e compleanni di amici e familiari, il gruppo musicale preferito e frasi usate spesso</span><span class="sxs-lookup"><span data-stu-id="f47ab-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="f47ab-134">Alcuni approcci comuni e impatti negativi</span><span class="sxs-lookup"><span data-stu-id="f47ab-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="f47ab-135">Di seguito sono descritte alcune delle procedure di gestione delle password più usate, tuttavia le ricerche condotte hanno portato alla luce alcuni impatti negativi.</span><span class="sxs-lookup"><span data-stu-id="f47ab-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="f47ab-136">Requisiti per la scadenza delle password degli utenti</span><span class="sxs-lookup"><span data-stu-id="f47ab-136">Password expiration requirements for users</span></span>

<span data-ttu-id="f47ab-p107">I requisiti per la scadenza delle password danno più svantaggi che vantaggi, in quanto spingono gli utenti a selezionare password prevedibili, composte da parole e numeri in sequenza strettamente correlati fra loro. In questi casi è piuttosto facile indovinare la password successiva sulla base di quella precedente. I requisiti di scadenza delle password non offrono alcun vantaggio in termini di contenimento dei danni, perché i criminali informatici usano quasi sempre le credenziali subito dopo averle compromesse. Vedere [È il momento di ripensare alle modifiche obbligatorie delle password](https://go.microsoft.com/fwlink/p/?linkid=861018) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p107">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them. Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="f47ab-141">Requisiti di lunghezza delle password</span><span class="sxs-lookup"><span data-stu-id="f47ab-141">Requiring long passwords</span></span>

<span data-ttu-id="f47ab-p108">I requisiti di lunghezza delle password (superiori a circa 10 caratteri) possono causare negli utenti un comportamento prevedibile e indesiderato. Ad esempio, gli utenti a cui viene richiesto di usare password di 16 caratteri potrebbero scegliere schemi ripetitivi come **ottoottoottootto** o **passwordpassword**, che soddisfano il requisito della lunghezza ma non sono difficili da indovinare. Inoltre, i requisiti di lunghezza aumentano le probabilità che gli utenti sviluppino abitudini non sicure, come annotare le password, riutilizzarle o memorizzarle nei propri documenti in formato non crittografato. Per incoraggiare gli utenti ad adottare una password univoca, è consigliabile impostare un requisito di lunghezza che non superi gli 8 caratteri.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p108">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="f47ab-146">Requisiti di complessità delle password (uso di più set di caratteri)</span><span class="sxs-lookup"><span data-stu-id="f47ab-146">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="f47ab-p109">I requisiti di complessità delle password inducono gli utenti a ridurre la varietà di lettere scelte e ad adottare comportamenti prevedibili, causando più danni che vantaggi. La maggior parte dei sistemi applica un certo livello di requisiti di complessità delle password. Ad esempio, le password devono contenere caratteri di tutte e tre le categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f47ab-p109">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="f47ab-150">caratteri maiuscoli</span><span class="sxs-lookup"><span data-stu-id="f47ab-150">uppercase characters</span></span>

- <span data-ttu-id="f47ab-151">caratteri minuscoli</span><span class="sxs-lookup"><span data-stu-id="f47ab-151">lowercase characters</span></span>

- <span data-ttu-id="f47ab-152">caratteri non alfanumerici</span><span class="sxs-lookup"><span data-stu-id="f47ab-152">non-alphanumeric characters</span></span>

<span data-ttu-id="f47ab-p110">La maggior parte delle persone usa schemi simili, ad esempio una lettera maiuscola in prima posizione, un simbolo alla fine e un numero in penultima posizione. I criminali informatici conoscono questi schemi, quindi eseguono gli attacchi con dizionario usando le sostituzioni più comuni, "$" per "s", "@" per "a," "1" per "l". Obbligare gli utenti a scegliere una combinazione di lettere maiuscole e minuscole, cifre e caratteri speciali ha un effetto negativo. Alcuni requisiti di complessità impediscono addirittura agli utenti di usare password sicure e facili da ricordare, costringendoli a scegliere password meno sicure e più difficili da ricordare.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p110">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="f47ab-157">Criteri efficaci</span><span class="sxs-lookup"><span data-stu-id="f47ab-157">Successful Patterns</span></span>

<span data-ttu-id="f47ab-158">Ecco alcuni suggerimenti volti a incoraggiare la diversità delle password.</span><span class="sxs-lookup"><span data-stu-id="f47ab-158">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="f47ab-159">Vietare le password comuni</span><span class="sxs-lookup"><span data-stu-id="f47ab-159">Ban common passwords</span></span>

<span data-ttu-id="f47ab-p111">Il più importante requisito da impostare in relazione alla creazione di password da parte degli utenti consiste nel vietare l'uso di password comuni per ridurre l'esposizione dell'organizzazione ad attacchi di forza bruta volti a violare le password. Alcune delle password più usate dagli utenti sono **abdcefg**, **password**, **123456**.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p111">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="f47ab-162">Educare gli utenti a non riutilizzare le password aziendali in altre posizioni</span><span class="sxs-lookup"><span data-stu-id="f47ab-162">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="f47ab-p112">Uno dei messaggi più importanti da comunicare agli utenti dell'organizzazione è di non riutilizzare la password aziendale per altri scopi. L'uso di password aziendali in siti Web esterni aumenta notevolmente le probabilità che i criminali informatici compromettano queste password.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p112">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="f47ab-165">Attivare la registrazione dell'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="f47ab-165">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="f47ab-p113">Assicurarsi che gli utenti aggiornino le informazioni di contatto e di sicurezza, aggiungendo ad esempio un indirizzo di posta elettronica o un numero di telefono alternativo oppure un dispositivo registrato per le notifiche push, in modo che possano rispondere alle richieste di sicurezza e ricevere notifiche sugli eventi che riguardano la sicurezza. Se si mantengono aggiornate le informazioni di contatto e di sicurezza, è più facile verificare l'identità degli utenti in caso dimentichino la password o se qualcuno tenta di assumere il controllo del loro account. Si fornisce inoltre un canale di notifica fuori banda in caso di eventi di sicurezza come tentativi di accesso o password modificate.</span><span class="sxs-lookup"><span data-stu-id="f47ab-p113">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="f47ab-169">Per altre informazioni, vedere [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f47ab-169">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="f47ab-170">Abilitare l'autenticazione a più fattori basata sul rischio</span><span class="sxs-lookup"><span data-stu-id="f47ab-170">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="f47ab-171">Con l'autenticazione a più fattori basata sul rischio, quando il sistema rileva un'attività sospetta richiede all'utente di provare di essere il legittimo proprietario dell'account.</span><span class="sxs-lookup"><span data-stu-id="f47ab-171">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="f47ab-172">Servono altre informazioni?</span><span class="sxs-lookup"><span data-stu-id="f47ab-172">Want to know more?</span></span> <span data-ttu-id="f47ab-173">Letture consigliate (in inglese)</span><span class="sxs-lookup"><span data-stu-id="f47ab-173">Recommended reading</span></span>

- [<span data-ttu-id="f47ab-174">Le password Web complesse sono davvero utili?</span><span class="sxs-lookup"><span data-stu-id="f47ab-174">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="f47ab-175">Gestire un portfolio di password e semplificare la vita agli utenti</span><span class="sxs-lookup"><span data-stu-id="f47ab-175">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="f47ab-176">Evitare l'uso di password vulnerabili studiando il comportamento degli utenti</span><span class="sxs-lookup"><span data-stu-id="f47ab-176">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="f47ab-177">Scelta di password sicure</span><span class="sxs-lookup"><span data-stu-id="f47ab-177">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="f47ab-178">Discussione sulla modifica obbligatoria della password</span><span class="sxs-lookup"><span data-stu-id="f47ab-178">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="f47ab-179">Le peggiori password del 2015</span><span class="sxs-lookup"><span data-stu-id="f47ab-179">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-articles"></a><span data-ttu-id="f47ab-180">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f47ab-180">Related articles</span></span>

[<span data-ttu-id="f47ab-181">Reimpostare password</span><span class="sxs-lookup"><span data-stu-id="f47ab-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="f47ab-182">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="f47ab-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="f47ab-183">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="f47ab-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="f47ab-184">Inviare nuovamente la password utente - Guida per amministratori</span><span class="sxs-lookup"><span data-stu-id="f47ab-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
