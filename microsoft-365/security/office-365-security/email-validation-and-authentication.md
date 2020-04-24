---
title: Autenticazione della posta elettronica in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Informazioni sul modo in cui Exchange Online ed Exchange Online Protection (EOP) in Microsoft 365 usano l'autenticazione e-mail (SPF, DKIM e DMARC) per evitare lo spoofing, il phishing e la posta indesiderata.
ms.openlocfilehash: f3a3ea902cb0c4fede4fcfd919f0969765bc4a96
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637557"
---
# <a name="email-authentication-in-microsoft-365"></a><span data-ttu-id="b450a-103">Autenticazione della posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b450a-103">Email authentication in Microsoft 365</span></span>

<span data-ttu-id="b450a-104">Con la denominazione di autenticazione e-mail, nota anche come autenticazione della posta elettronica o convalida della posta elettronica, si indica un gruppo di standard che prova a bloccare lo spoofing, ossia i messaggi di posta elettronica provenienti da mittenti contraffatti.</span><span class="sxs-lookup"><span data-stu-id="b450a-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="b450a-105">Nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online e nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP usa gli standard per verificare la posta in ingresso:</span><span class="sxs-lookup"><span data-stu-id="b450a-105">In Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP useses the standards to verify inbound email:</span></span>

- [<span data-ttu-id="b450a-106">SPF</span><span class="sxs-lookup"><span data-stu-id="b450a-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="b450a-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="b450a-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="b450a-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="b450a-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="b450a-109">L'autenticazione della posta elettronica verifica che i messaggi di posta elettronica provenienti da un mittente, ad esempio laura@contoso.com, siano legittimi e provengano da fonti previste per quel dominio di posta elettronica, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b450a-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="b450a-110">Il resto di questo argomento spiega come funzionano queste tecnologie e il modo in cui vengono usate in EOP per controllare la posta elettronica in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b450a-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="b450a-111">Usare l'autenticazione della posta elettronica per evitare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="b450a-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="b450a-112">DMARC impedisce lo spoofing esaminando l'indirizzo **Da** nei messaggi, ossia l'indirizzo di posta elettronica del mittente che gli utenti vedono nel proprio client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b450a-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="b450a-113">Inoltre, le organizzazioni di posta elettronica di destinazione possono verificare che il dominio abbia superato i controlli SPF o DKIM, il che significa che è stato autenticato e pertanto non è contraffatto.</span><span class="sxs-lookup"><span data-stu-id="b450a-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="b450a-114">Il problema è tuttavia che i record SPF, DKIM e DMARC nel DNS per l'autenticazione della posta elettronica, collettivamente noti come criteri di autenticazione e-mail, sono completamente facoltativi.</span><span class="sxs-lookup"><span data-stu-id="b450a-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="b450a-115">Di conseguenza, mentre i domini con criteri di autenticazione e-mail avanzati come microsoft.com e skype.com sono protetti dallo spoofing, i domini che pubblicano criteri di autenticazione più deboli o non ne pubblicano sono obiettivi che possono essere contraffatti.</span><span class="sxs-lookup"><span data-stu-id="b450a-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="b450a-116">Al marzo 2018, solo il 9% dei domini delle aziende Fortune 500 pubblicava criteri di autenticazione e-mail avanzati.</span><span class="sxs-lookup"><span data-stu-id="b450a-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="b450a-117">Il 91% restante delle aziende è soggetto a contraffazione.</span><span class="sxs-lookup"><span data-stu-id="b450a-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="b450a-118">Se non è in uso un altro meccanismo di filtro della posta elettronica, è possibile che i messaggi provenienti da mittenti contraffatti in questi domini vengano recapitati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b450a-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Criteri DMARC delle società Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="b450a-120">La percentuale di aziende piccole e di medie dimensioni che non rientrano in Fortune 500 e che pubblicano criteri di autenticazione e-mail avanzati è esigua, ed è ancora più esigua per i domini esterni al Nord America e all'Europa occidentale.</span><span class="sxs-lookup"><span data-stu-id="b450a-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="b450a-121">Si tratta di un problema grave perché, mentre le aziende potrebbero non essere a conoscenza di come funziona l'autenticazione e-mail, gli utenti malintenzionati lo sanno perfettamente e approfittano di questa mancanza.</span><span class="sxs-lookup"><span data-stu-id="b450a-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="b450a-122">Dal momento che il phishing è un problema rilevante e a causa dell'adozione limitata di criteri di autenticazione e-mail sicuri, Microsoft usa l'*autenticazione implicita* per controllare la posta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b450a-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="b450a-123">L'autenticazione implicita della posta elettronica è basata su numerose estensioni ai normali criteri di autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="b450a-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="b450a-124">Queste estensioni includono reputazione del mittente, cronologia del mittente e del destinatario, analisi comportamentale e altre tecniche avanzate.</span><span class="sxs-lookup"><span data-stu-id="b450a-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="b450a-125">Un messaggio inviato da un dominio che non usa criteri di autenticazione e-mail sarà contrassegnato come contraffatto, a meno che non contenga altri segnali che ne attestano la legittimità.</span><span class="sxs-lookup"><span data-stu-id="b450a-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="b450a-126">Per visualizzare l'annuncio generale di Microsoft, vedere [A Sea of Phish Part 2: Enhanced Anti-spoofing technology in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) (Un mare di phishing parte 2 - Anti-spoofing avanzato in Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="b450a-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="b450a-127">Autenticazione composita</span><span class="sxs-lookup"><span data-stu-id="b450a-127">Composite authentication</span></span>

<span data-ttu-id="b450a-128">Anche se SPF, DKIM e DMARC sono tutti utili singolarmente, non comunicano un sufficiente stato di autenticazione nel caso in cui un messaggio non disponga di record di autenticazione espliciti. </span><span class="sxs-lookup"><span data-stu-id="b450a-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="b450a-129">Di conseguenza, Microsoft ha sviluppato un algoritmo per l'autenticazione implicita della posta elettronica, che combina più segnali in un singolo valore denominato _autenticazione composita_, o compauth in breve.</span><span class="sxs-lookup"><span data-stu-id="b450a-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="b450a-130">Il valore compauth viene indicato nell'intestazione **Authentication-Results** nelle intestazioni dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b450a-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="b450a-131">Authentication-Results:</span><span class="sxs-lookup"><span data-stu-id="b450a-131">Authentication-Results:</span></span><br/><span data-ttu-id="b450a-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="b450a-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="b450a-133">Questi valori sono spiegati in [Intestazione del messaggio Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="b450a-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="b450a-134">Esaminando le intestazioni dei messaggi, gli amministratori o anche gli utenti finali possono comprendere il modo in cui Microsoft 365 ha determinato che il mittente è contraffatto.</span><span class="sxs-lookup"><span data-stu-id="b450a-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="b450a-135">Perché l'autenticazione e-mail non è sempre sufficiente per bloccare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="b450a-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="b450a-136">Affidarsi solo ai record di autenticazione della posta elettronica per determinare se un messaggio in arrivo è contraffatto presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b450a-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="b450a-137">È possibile che il dominio di invio non abbia i record DNS necessari o che i record siano configurati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="b450a-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="b450a-138">Il dominio di origine ha record DNS configurati in modo corretto, ma quel dominio non corrisponde al dominio nell'indirizzo del mittente.</span><span class="sxs-lookup"><span data-stu-id="b450a-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="b450a-139">SPF e DKIM non richiedono che il dominio sia usato nell'indirizzo del mittente.</span><span class="sxs-lookup"><span data-stu-id="b450a-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="b450a-140">Utenti malintenzionati o servizi legittimi potrebbero registrare un dominio, configurare SPF e DKIM per il dominio, usare un dominio completamente diverso nell'indirizzo del mittente, e il messaggio supererà i controlli SPF e DKIM.</span><span class="sxs-lookup"><span data-stu-id="b450a-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="b450a-141">L'autenticazione composita può risolvere queste limitazioni, passando messaggi che altrimenti non supererebbero i controlli di autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="b450a-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="b450a-142">Come descritto in precedenza, l'autenticazione implicita della posta elettronica usa più segnali per determinare se un messaggio è legittimo.</span><span class="sxs-lookup"><span data-stu-id="b450a-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="b450a-143">Per semplicità, gli esempi seguenti sono incentrati sui risultati dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b450a-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="b450a-144">Altri fattori di intelligence di back-end potrebbero identificare i messaggi che superano l'autenticazione e-mail come contraffatti o i messaggi che non la superano come legittimi.</span><span class="sxs-lookup"><span data-stu-id="b450a-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="b450a-145">Il dominio fabrikam.com, ad esempio, non ha record SPF, DKIM o DMARC.</span><span class="sxs-lookup"><span data-stu-id="b450a-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="b450a-146">I messaggi provenienti da mittenti nel dominio fabrikam.com possono non superare l'autenticazione composita (notare il valore `compauth` e il motivo):</span><span class="sxs-lookup"><span data-stu-id="b450a-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="b450a-147">Se fabrikam.com configura un record SPF senza un record DKIM, il messaggio può superare l'autenticazione composita perché il dominio che ha superato SPF è allineato al dominio nell'indirizzo del mittente:</span><span class="sxs-lookup"><span data-stu-id="b450a-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="b450a-148">Se fabrikam.com configura un record DKIM senza un record SPF, il messaggio può superare l'autenticazione composita perché il dominio nella firma DKIM è allineato al dominio nell'indirizzo del mittente:</span><span class="sxs-lookup"><span data-stu-id="b450a-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="b450a-149">Se il dominio in SPF o nella firma DKIM non è allineato al dominio nell'indirizzo del mittente, il messaggio potrebbe non superare l'autenticazione composita:</span><span class="sxs-lookup"><span data-stu-id="b450a-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="b450a-150">Soluzioni per i mittenti legittimi che inviano messaggi di posta elettronica non autenticati</span><span class="sxs-lookup"><span data-stu-id="b450a-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="b450a-151">Microsoft 365 tiene traccia di chi invia messaggi di posta elettronica non autenticati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b450a-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="b450a-152">Se il servizio ritiene che il mittente non sia legittimo, lo contrassegnerà come errore di autenticazione composita.</span><span class="sxs-lookup"><span data-stu-id="b450a-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="b450a-153">Per evitarlo, è possibile usare i suggerimenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="b450a-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="b450a-154">Configurare l'autenticazione e-mail per i domini di cui si è proprietari</span><span class="sxs-lookup"><span data-stu-id="b450a-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="b450a-155">Si può usare questo metodo per risolvere lo spoofing intra-organizzazione e lo spoofing fra domini nei casi in cui si è proprietari o si interagisce con più tenant.</span><span class="sxs-lookup"><span data-stu-id="b450a-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="b450a-156">Il metodo consente anche di risolvere i problemi di spoofing fra domini in cui si invia ad altri clienti all'interno di Microsoft 365 o a terze parti ospitate da altri provider.</span><span class="sxs-lookup"><span data-stu-id="b450a-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="b450a-157">[Configurare record SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) per i propri domini.</span><span class="sxs-lookup"><span data-stu-id="b450a-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="b450a-158">[Configurare record DKIM](use-dkim-to-validate-outbound-email.md) per i propri domini primari.</span><span class="sxs-lookup"><span data-stu-id="b450a-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="b450a-159">[Valutare la possibilità di configurare record DMARC](use-dmarc-to-validate-email.md) per il dominio per determinare chi sono i mittenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="b450a-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="b450a-160">Microsoft non fornisce istruzioni dettagliate per l'implementazione dei record SPF, DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="b450a-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="b450a-161">Online, tuttavia, sono disponibili numerose informazioni.</span><span class="sxs-lookup"><span data-stu-id="b450a-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="b450a-162">Esistono anche società di terze che si occupano di aiutare le organizzazioni a configurare i record di autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="b450a-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="b450a-163">Non si conoscono tutte le origini dei propri messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b450a-163">You don't know all sources for your email</span></span>

<span data-ttu-id="b450a-164">Molti domini non pubblicano i record SPF perché non conoscono tutte le origini di posta elettronica nel proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="b450a-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="b450a-165">Iniziare con la pubblicazione di un record SPF contenente tutte le origini di posta elettronica che si conoscono, soprattutto nell'ubicazione del traffico aziendale, e pubblicare il criterio SPF neutro `?all`.</span><span class="sxs-lookup"><span data-stu-id="b450a-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="b450a-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b450a-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="b450a-167">Questo esempio significa che i messaggi di posta elettronica provenienti dall'infrastruttura aziendale supereranno l'autenticazione e-mail, ma quelli provenienti da origini sconosciute ricadranno nel criterio neutro.</span><span class="sxs-lookup"><span data-stu-id="b450a-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="b450a-168">Microsoft 365 considererà la posta in ingresso dall'infrastruttura aziendale come autenticata, ma la posta proveniente da origini non identificate potrebbe essere ancora contrassegnata come spoofing (a seconda che Microsoft 365 possa o meno autenticarla in modo implicito).</span><span class="sxs-lookup"><span data-stu-id="b450a-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="b450a-169">Tuttavia, questo rappresenta comunque un miglioramento rispetto al contrassegno di tutti i messaggi di posta elettronica come spoofing in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b450a-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="b450a-170">Dopo aver iniziato a usare un criterio di fallback SPF `?all`, è possibile individuare e includere gradualmente altre origini di posta elettronica per i messaggi e quindi aggiornare il record SPF con criteri più restrittivi.</span><span class="sxs-lookup"><span data-stu-id="b450a-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="b450a-171">Usare spoof intelligence per configurare i mittenti di posta elettronica non autenticata consentiti</span><span class="sxs-lookup"><span data-stu-id="b450a-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="b450a-172">È anche possibile usare [spoof intelligence](learn-about-spoof-intelligence.md) per consentire ai mittenti di trasmettere messaggi non autenticati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b450a-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="b450a-173">Per i domini esterni, l'utente oggetto di spoofing è il dominio dell'indirizzo del mittente, mentre l'infrastruttura di invio è l'indirizzo IP di origine, suddiviso in intervalli CIDR /24, o il dominio dell'organizzazione del record DNS inverso (PTR).</span><span class="sxs-lookup"><span data-stu-id="b450a-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="b450a-174">Nello screenshot seguente l'indirizzo IP di origine potrebbe essere 131.107.18.4 con il record PTR outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b450a-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="b450a-175">Questo sarebbe visualizzato come outlook.com per l'infrastruttura di invio.</span><span class="sxs-lookup"><span data-stu-id="b450a-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="b450a-176">Per consentire al mittente di inviare messaggi di posta elettronica non autenticati, modificare il **No** in un **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b450a-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Configurazione anti-spoofing per alcuni mittenti](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="b450a-178">Creare una voce Consenti per la coppia mittente/destinatario</span><span class="sxs-lookup"><span data-stu-id="b450a-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="b450a-179">Per ignorare il filtro della posta indesiderata, alcune parti del filtro anti-phishing, ma non il filtro antimalware per mittenti specifici, vedere [Creare elenchi di mittenti attendibili in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b450a-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="b450a-180">Chiedere al mittente di configurare l'autenticazione e-mail per i domini di cui non si è proprietari</span><span class="sxs-lookup"><span data-stu-id="b450a-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="b450a-181">A causa dei problemi generati dalla posta indesiderata e dal phishing, Microsoft consiglia a tutte le organizzazioni di posta elettronica di configurare l'autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="b450a-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="b450a-182">Anziché configurare override manuali nell'organizzazione, si può chiedere a un amministratore nel dominio di invio di configurare i propri record di autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="b450a-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="b450a-183">Anche se in passato non erano tenuti a pubblicare record di autenticazione e-mail, devono farlo se inviano messaggi di posta elettronica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b450a-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="b450a-184">Configurare SPF per pubblicare gli indirizzi IP di invio del dominio e configurare DKIM (se disponibile) per la firma digitale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b450a-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="b450a-185">Dovrebbero inoltre prendere in considerazione la configurazione dei record DMARC.</span><span class="sxs-lookup"><span data-stu-id="b450a-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="b450a-186">Se usano mittenti in blocco per inviare messaggi di posta elettronica per loro conto, assicurarsi che il dominio nell'indirizzo Da (se di loro proprietà) sia allineato al dominio che supera i controlli SPF o DMARC.</span><span class="sxs-lookup"><span data-stu-id="b450a-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="b450a-187">Verificare che le posizioni seguenti, se in uso, siano incluse nel record SPF:</span><span class="sxs-lookup"><span data-stu-id="b450a-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="b450a-188">Server di posta elettronica locali.</span><span class="sxs-lookup"><span data-stu-id="b450a-188">On-premises email servers.</span></span>
  - <span data-ttu-id="b450a-189">Messaggi di posta elettronica inviati da un provider di software come un servizio (SaaS).</span><span class="sxs-lookup"><span data-stu-id="b450a-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="b450a-190">Messaggi di posta elettronica inviati da un servizio di hosting cloud (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services e così via).</span><span class="sxs-lookup"><span data-stu-id="b450a-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="b450a-191">Per i piccoli domini ospitati da un ISP, configurare il record SPF in base alle istruzioni fornite dall'ISP.</span><span class="sxs-lookup"><span data-stu-id="b450a-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="b450a-192">Anche se in un primo momento può essere difficile ottenere l'autenticazione dei domini di invio, nel corso del tempo, poiché sempre più filtri per la posta elettronica iniziano a selezionare i loro messaggi come posta indesiderata o addirittura li rifiutano, questo li indurrà a configurare correttamente i record per garantire una migliore distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b450a-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="b450a-193">Inoltre, la loro partecipazione può essere utile per la lotta al phishing e può ridurre la possibilità di phishing interno o nelle organizzazioni a cui inviano messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b450a-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="b450a-194">Informazioni per i provider di infrastrutture (ISP, ESP o servizi di hosting cloud)</span><span class="sxs-lookup"><span data-stu-id="b450a-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="b450a-195">Se si ospita la posta elettronica di un dominio o si fornisce un'infrastruttura di hosting in grado di inviare messaggi di posta elettronica, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b450a-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="b450a-196">Verificare che i propri clienti dispongano di documentazione in cui viene spiegato in che modo devono configurare i record SPF</span><span class="sxs-lookup"><span data-stu-id="b450a-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="b450a-197">Valutare la possibilità di firmare con firme DKIM i messaggi di posta elettronica in uscita, anche se il cliente non l'ha esplicitamente configurata (firmare con un dominio predefinito).</span><span class="sxs-lookup"><span data-stu-id="b450a-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="b450a-198">È anche possibile firmare due volte il messaggio di posta elettronica con DKIM (una volta con il dominio del cliente se è stato configurato e una seconda volta con la firma DKIM della società)</span><span class="sxs-lookup"><span data-stu-id="b450a-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="b450a-199">Anche se si autentica la posta elettronica proveniente dalla propria piattaforma, il corretto recapito a Microsoft non è garantito, ma almeno questo assicura che Microsoft non la contrassegni come indesiderata perché non è autenticata.</span><span class="sxs-lookup"><span data-stu-id="b450a-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="b450a-200">Per ulteriori informazioni sulle procedure consigliate per i provider di servizi, vedere le [procedure consigliate per la messaggistica mobile di M3AAWG per i provider di servizi](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span><span class="sxs-lookup"><span data-stu-id="b450a-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
