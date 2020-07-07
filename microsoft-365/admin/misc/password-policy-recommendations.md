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
# <a name="password-policy-recommendations"></a>Suggerimenti sui criteri delle password
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
Per determinare la frequenza di scadenza delle password di Microsoft 365 nella propria organizzazione, vedere [Impostare i criteri di scadenza delle password per Microsoft 365](../manage/set-password-expiration-policy.md).

Per altre informazioni sulle password per Microsoft 365, vedere gli [articoli correlati](#related-articles).
  
## <a name="understanding-password-recommendations"></a>Informazioni sui suggerimenti per la scelta della password

I criteri per l'impostazione di password efficaci rientrano in tre ampie categorie:
  
- **Resistenza agli attacchi più comuni** Questo criterio implica la scelta della posizione in cui gli utenti immettono le password (dispositivi noti e attendibili con un buon sistema di rilevamento del malware e siti convalidati) e la scelta della password stessa (lunghezza e univocità).

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>Linee guida per le password per gli amministratori

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- Mantenere il requisito di lunghezza minima di 8 caratteri (una password più lunga non è necessariamente migliore)

- Don't require character composition requirements. For example, \*&amp;(^%$

- Non richiedere la reimpostazione periodica obbligatoria delle password degli account utente

- Vietare le password comuni per tenere fuori dal sistema le password più vulnerabili

- Educare gli utenti a non riutilizzare la password aziendale per scopi non correlati al lavoro

- Attivare la registrazione per l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)

- Abilitare le richieste di autenticazione a più fattori basata sul rischio

### <a name="password-guidance-for-your-users"></a>Linee guida per le password per gli utenti

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- Non usare una password uguale o simile a una password usata in un altro sito Web

- Non usare una sola parola, ad esempio **password**, o una frase di uso comune, come **Iloveyou**

- Creare password difficili da indovinare anche da parte di persone molto intime, evitando ad esempio nomi e compleanni di amici e familiari, il gruppo musicale preferito e frasi usate spesso

## <a name="some-common-approaches-and-their-negative-impacts"></a>Alcuni approcci comuni e impatti negativi

Di seguito sono descritte alcune delle procedure di gestione delle password più usate, tuttavia le ricerche condotte hanno portato alla luce alcuni impatti negativi.
  
### <a name="password-expiration-requirements-for-users"></a>Requisiti per la scadenza delle password degli utenti

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>Requisiti di lunghezza delle password

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Requisiti di complessità delle password (uso di più set di caratteri)

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- caratteri maiuscoli

- caratteri minuscoli

- caratteri non alfanumerici

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>Criteri efficaci

Ecco alcuni suggerimenti volti a incoraggiare la diversità delle password.
  
### <a name="ban-common-passwords"></a>Vietare le password comuni

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Educare gli utenti a non riutilizzare le password aziendali in altre posizioni

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Attivare la registrazione dell'autenticazione a più fattori

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
Per altre informazioni, vedere [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Abilitare l'autenticazione a più fattori basata sul rischio

Con l'autenticazione a più fattori basata sul rischio, quando il sistema rileva un'attività sospetta richiede all'utente di provare di essere il legittimo proprietario dell'account. 
  
## <a name="want-to-know-more-recommended-reading"></a>Servono altre informazioni? Letture consigliate (in inglese)

- [Le password Web complesse sono davvero utili?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Gestire un portfolio di password e semplificare la vita agli utenti](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Evitare l'uso di password vulnerabili studiando il comportamento degli utenti](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Scelta di password sicure](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Discussione sulla modifica obbligatoria della password](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Le peggiori password del 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Scaricare file dal Web](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>Articoli correlati

[Reimpostare password](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[Impostare la password di un singolo utente in modo che non scada mai](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[Consentire agli utenti di reimpostare le loro password](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[Inviare nuovamente la password utente - Guida per amministratori](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
