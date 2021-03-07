---
title: Autenticazione della posta elettronica in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Informazioni per amministratori sul modo in cui EOP usa l'autenticazione della posta elettronica (SPF, DKIM e DMARC) per prevenire lo spoofing, il phishing e la posta indesiderata.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87677608431446a4bdfe6e16ae1204163a4f582a
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509195"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="02b96-103">Autenticazione e-mail in EOP</span><span class="sxs-lookup"><span data-stu-id="02b96-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02b96-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="02b96-104">**Applies to**</span></span>
- [<span data-ttu-id="02b96-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="02b96-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="02b96-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="02b96-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="02b96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02b96-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="02b96-108">Con la denominazione di autenticazione e-mail, nota anche come autenticazione della posta elettronica o convalida della posta elettronica, si indica un gruppo di standard che prova a bloccare lo spoofing, ossia i messaggi di posta elettronica provenienti da mittenti contraffatti.</span><span class="sxs-lookup"><span data-stu-id="02b96-108">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="02b96-109">In tutte le organizzazioni Microsoft 365, EOP usa questi standard per verificare la posta elettronica in ingresso:</span><span class="sxs-lookup"><span data-stu-id="02b96-109">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="02b96-110">SPF</span><span class="sxs-lookup"><span data-stu-id="02b96-110">SPF</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [<span data-ttu-id="02b96-111">DKIM</span><span class="sxs-lookup"><span data-stu-id="02b96-111">DKIM</span></span>](use-dkim-to-validate-outbound-email.md)

- [<span data-ttu-id="02b96-112">DMARC</span><span class="sxs-lookup"><span data-stu-id="02b96-112">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="02b96-113">L'autenticazione della posta elettronica verifica che i messaggi di posta elettronica provenienti da un mittente, ad esempio laura@contoso.com, siano legittimi e provengano da fonti previste per quel dominio di posta elettronica, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="02b96-113">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="02b96-114">Il resto di questo articolo spiega come funzionano queste tecnologie e il modo in cui vengono usate in EOP per controllare la posta elettronica in ingresso.</span><span class="sxs-lookup"><span data-stu-id="02b96-114">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="02b96-115">Usare l'autenticazione della posta elettronica per evitare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="02b96-115">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="02b96-116">DMARC previene lo spoofing tramite l'analisi dell'indirizzo **Da** nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="02b96-116">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="02b96-117">L'indirizzo **Da** è l'indirizzo di posta elettronica del mittente che gli utenti vedono nel loro client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-117">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="02b96-118">Le organizzazioni di posta elettronica di destinazione possono anche verificare che il dominio di posta elettronica abbia superato le autenticazioni SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="02b96-118">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="02b96-119">In altre parole, il dominio è stato autenticato pertanto l’indirizzo di posta elettronica del mittente non è falsificato.</span><span class="sxs-lookup"><span data-stu-id="02b96-119">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="02b96-120">Tuttavia, i record DNS per le autenticazioni SPF, DKIM e DMARC (note collettivamente come criteri di autenticazione della posta elettronica) sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="02b96-120">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="02b96-121">I domini con criteri avanzati di autenticazione della posta elettronica, come microsoft.com e skype.com, sono protetti contro lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="02b96-121">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="02b96-122">Tuttavia, i domini con criteri di autenticazione della posta elettronica più deboli, o privi di criteri, sono obiettivi primari dei contraffattori.</span><span class="sxs-lookup"><span data-stu-id="02b96-122">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="02b96-123">Al marzo 2018, solo il 9% dei domini delle aziende Fortune 500 pubblicava criteri avanzati di autenticazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-123">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="02b96-124">Il 91% restante delle aziende è soggetto a contraffazione.</span><span class="sxs-lookup"><span data-stu-id="02b96-124">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="02b96-125">Se non è in uso un altro meccanismo di filtro della posta elettronica, è possibile che i messaggi provenienti da mittenti contraffatti in questi domini vengano recapitati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="02b96-125">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Criteri DMARC delle società Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="02b96-127">Le proporzioni delle piccole e medie imprese che pubblicano criteri avanzati di autenticazione della posta elettronica sono più piccole.</span><span class="sxs-lookup"><span data-stu-id="02b96-127">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="02b96-128">E il numero è ancora più piccolo per i domini di posta elettronica all'esterno del Nord America e dell'Europa occidentale.</span><span class="sxs-lookup"><span data-stu-id="02b96-128">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="02b96-129">L’assenza di criteri avanzati di autenticazione della posta elettronica è un problema importante.</span><span class="sxs-lookup"><span data-stu-id="02b96-129">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="02b96-130">Benché le organizzazioni possano non comprendere come funziona l'autenticazione della posta elettronica, gli aggressori lo conoscono a fondo e ne traggono vantaggio.</span><span class="sxs-lookup"><span data-stu-id="02b96-130">While organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="02b96-131">Per evitare l'esposizione al phishing e a causa dell'adozione limitata di criteri avanzati di autenticazione della posta elettronica, Microsoft usa l'*autenticazione implicita* per controllare la posta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="02b96-131">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="02b96-132">L'autenticazione implicita della posta elettronica è un'estensione dei normali criteri di autenticazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-132">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="02b96-133">Queste estensioni includono reputazione del mittente, cronologia del mittente e del destinatario, analisi comportamentale e altre tecniche avanzate.</span><span class="sxs-lookup"><span data-stu-id="02b96-133">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="02b96-134">In assenza di altri segnali inviati da queste estensioni, i messaggi inviati da domini che non usano criteri di autenticazione della posta elettronica saranno contrassegnati come contraffatti.</span><span class="sxs-lookup"><span data-stu-id="02b96-134">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="02b96-135">Per visualizzare l'annuncio generale di Microsoft, vedere [A Sea of Phish Part 2: Enhanced Anti-spoofing technology in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) (Un mare di phishing parte 2 - Anti-spoofing avanzato in Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="02b96-135">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="02b96-136">Autenticazione composita</span><span class="sxs-lookup"><span data-stu-id="02b96-136">Composite authentication</span></span>

<span data-ttu-id="02b96-137">Se un dominio non contiene record SPF, DKIM E DMARC tradizionali, tali controlli dei record non comunicano informazioni sufficienti sullo stato di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="02b96-137">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="02b96-138">Di conseguenza, Microsoft ha sviluppato un algoritmo per l'autenticazione implicita della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-138">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="02b96-139">Questo algoritmo combina più segnali in un singolo valore denominato _autenticazione composita_, o `compauth` in breve.</span><span class="sxs-lookup"><span data-stu-id="02b96-139">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="02b96-140">Il valore `compauth` viene indicato nell'intestazione **Authentication-Results** nelle intestazioni dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="02b96-140">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="02b96-141">Questi valori sono spiegati in [Intestazione del messaggio Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="02b96-141">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="02b96-142">Esaminando le intestazioni dei messaggi, gli amministratori o anche gli utenti finali possono comprendere il modo in cui Microsoft 365 ha determinato che il mittente è contraffatto.</span><span class="sxs-lookup"><span data-stu-id="02b96-142">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="02b96-143">Perché l'autenticazione e-mail non è sempre sufficiente per bloccare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="02b96-143">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="02b96-144">Affidarsi solo ai record di autenticazione della posta elettronica per determinare se un messaggio in arrivo è contraffatto presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02b96-144">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="02b96-145">È possibile che il dominio di invio non abbia i record DNS necessari o che i record siano configurati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="02b96-145">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="02b96-146">Il dominio di origine ha record DNS configurati in modo corretto, ma quel dominio non corrisponde al dominio nell'indirizzo del mittente.</span><span class="sxs-lookup"><span data-stu-id="02b96-146">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="02b96-147">SPF e DKIM non richiedono che il dominio sia usato nell'indirizzo del mittente.</span><span class="sxs-lookup"><span data-stu-id="02b96-147">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="02b96-148">Aggressori o servizi legittimi potrebbero registrare un dominio, configurare SPF e DKIM per il dominio, usare un dominio completamente diverso nell'indirizzo del mittente.</span><span class="sxs-lookup"><span data-stu-id="02b96-148">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="02b96-149">I messaggi provenienti da mittenti di questo dominio supereranno SPF e DKIM.</span><span class="sxs-lookup"><span data-stu-id="02b96-149">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="02b96-150">L'autenticazione composita può risolvere queste limitazioni, passando messaggi che altrimenti non supererebbero i controlli di autenticazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-150">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="02b96-151">Per semplicità, gli esempi seguenti sono incentrati sui risultati dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="02b96-151">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="02b96-152">Altri fattori di intelligence di back-end potrebbero identificare i messaggi che superano l'autenticazione e-mail come contraffatti o i messaggi che non la superano come legittimi.</span><span class="sxs-lookup"><span data-stu-id="02b96-152">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="02b96-153">Il dominio fabrikam.com, ad esempio, non ha record SPF, DKIM o DMARC.</span><span class="sxs-lookup"><span data-stu-id="02b96-153">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="02b96-154">I messaggi provenienti da mittenti nel dominio fabrikam.com possono non superare l'autenticazione composita (notare il valore `compauth` e il motivo):</span><span class="sxs-lookup"><span data-stu-id="02b96-154">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="02b96-155">Se fabrikam.com configura un SPF senza un record DKIM, il messaggio può superare l'autenticazione composita.</span><span class="sxs-lookup"><span data-stu-id="02b96-155">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="02b96-156">Il dominio che ha superato i controlli SPF è allineato al dominio nell'indirizzo del mittente:</span><span class="sxs-lookup"><span data-stu-id="02b96-156">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="02b96-157">Se fabrikam.com configura un DKIM senza un record SPF, il messaggio può superare l'autenticazione composita.</span><span class="sxs-lookup"><span data-stu-id="02b96-157">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="02b96-158">Il dominio che della firma DKIM è allineato al dominio nell'indirizzo del mittente:</span><span class="sxs-lookup"><span data-stu-id="02b96-158">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="02b96-159">Se il dominio in SPF o nella firma DKIM non è allineato al dominio nell'indirizzo del mittente, il messaggio potrebbe non superare l'autenticazione composita:</span><span class="sxs-lookup"><span data-stu-id="02b96-159">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="02b96-160">Soluzioni per i mittenti legittimi che inviano messaggi di posta elettronica non autenticati</span><span class="sxs-lookup"><span data-stu-id="02b96-160">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="02b96-161">Microsoft 365 tiene traccia di chi invia messaggi di posta elettronica non autenticati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02b96-161">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="02b96-162">Se il servizio ritiene che il mittente non sia legittimo, contrassegnerà i messaggi del mittente come errori di autenticazione composita.</span><span class="sxs-lookup"><span data-stu-id="02b96-162">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="02b96-163">Per evitarlo, è possibile seguire i suggerimenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="02b96-163">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="02b96-164">Configurare l'autenticazione e-mail per i domini di cui si è proprietari</span><span class="sxs-lookup"><span data-stu-id="02b96-164">Configure email authentication for domains you own</span></span>

<span data-ttu-id="02b96-165">Si può usare questo metodo per risolvere lo spoofing intra-organizzazione e lo spoofing fra domini nei casi in cui si è proprietari o si interagisce con più tenant.</span><span class="sxs-lookup"><span data-stu-id="02b96-165">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="02b96-166">Il metodo consente anche di risolvere i problemi di spoofing fra domini in cui si invia ad altri clienti all'interno di Microsoft 365 o a terze parti ospitate da altri provider.</span><span class="sxs-lookup"><span data-stu-id="02b96-166">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="02b96-167">[Configurare record SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) per i propri domini.</span><span class="sxs-lookup"><span data-stu-id="02b96-167">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="02b96-168">[Configurare record DKIM](use-dkim-to-validate-outbound-email.md) per i propri domini primari.</span><span class="sxs-lookup"><span data-stu-id="02b96-168">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="02b96-169">[Valutare la possibilità di configurare record DMARC](use-dmarc-to-validate-email.md) per il dominio per determinare chi sono i mittenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="02b96-169">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="02b96-170">Microsoft non fornisce istruzioni dettagliate per l'implementazione dei record SPF, DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="02b96-170">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="02b96-171">Online, tuttavia, sono disponibili numerose informazioni.</span><span class="sxs-lookup"><span data-stu-id="02b96-171">However, there's many information available online.</span></span> <span data-ttu-id="02b96-172">Esistono anche società terze parti che si occupano di aiutare le organizzazioni a configurare i record di autenticazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-172">There are also third party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="02b96-173">Non si conoscono tutte le origini dei propri messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="02b96-173">You don't know all sources for your email</span></span>

<span data-ttu-id="02b96-174">Molti domini non pubblicano i record SPF perché non conoscono tutte le origini di posta elettronica nel proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="02b96-174">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="02b96-175">Iniziare con la pubblicazione di un record SPF contenente tutte le origini di posta elettronica che si conoscono, soprattutto nell'ubicazione del traffico aziendale, e pubblicare il criterio SPF neutro `?all`.</span><span class="sxs-lookup"><span data-stu-id="02b96-175">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="02b96-176">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="02b96-176">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="02b96-177">Questo esempio significa che i messaggi di posta elettronica provenienti dall'infrastruttura aziendale supereranno l'autenticazione e-mail, ma quelli provenienti da origini sconosciute ricadranno nel criterio neutro.</span><span class="sxs-lookup"><span data-stu-id="02b96-177">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="02b96-178">Microsoft 365 tratterà i messaggi di posta elettronica ricevuti dall'infrastruttura aziendale come autenticati.</span><span class="sxs-lookup"><span data-stu-id="02b96-178">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="02b96-179">La posta elettronica inviata da mittenti non identificati potrebbe essere contrassegnata come contrattatta se non supera l'autenticazione implicita.</span><span class="sxs-lookup"><span data-stu-id="02b96-179">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="02b96-180">Tuttavia, questo rappresenta comunque un miglioramento rispetto al contrassegno di tutti i messaggi di posta elettronica come spoofing in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02b96-180">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="02b96-181">Dopo aver iniziato a usare un criterio di fallback SPF `?all`, è possibile individuare e includere gradualmente altre origini di posta elettronica per i messaggi e quindi aggiornare il record SPF con criteri più restrittivi.</span><span class="sxs-lookup"><span data-stu-id="02b96-181">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="02b96-182">Usare spoof intelligence per configurare i mittenti di posta elettronica non autenticata consentiti</span><span class="sxs-lookup"><span data-stu-id="02b96-182">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="02b96-183">È anche possibile usare [spoof intelligence](learn-about-spoof-intelligence.md) per consentire ai mittenti di trasmettere messaggi non autenticati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02b96-183">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="02b96-184">Per i domini esterni, l'utente oggetto di spoofing è il dominio dell'indirizzo del mittente, mentre l'infrastruttura di invio è l'indirizzo IP di origine, suddiviso in intervalli CIDR /24, o il dominio dell'organizzazione del record DNS inverso (PTR).</span><span class="sxs-lookup"><span data-stu-id="02b96-184">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="02b96-185">Nello screenshot seguente l'indirizzo IP di origine potrebbe essere 131.107.18.4 con il record PTR outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="02b96-185">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="02b96-186">Questo sarebbe visualizzato come outlook.com per l'infrastruttura di invio.</span><span class="sxs-lookup"><span data-stu-id="02b96-186">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="02b96-187">Per consentire al mittente di inviare messaggi di posta elettronica non autenticati, modificare il **No** in un **Sì**.</span><span class="sxs-lookup"><span data-stu-id="02b96-187">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Configurazione anti-spoofing per alcuni mittenti](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="02b96-189">Creare una voce Consenti per la coppia mittente/destinatario</span><span class="sxs-lookup"><span data-stu-id="02b96-189">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="02b96-190">Per ignorare il filtro della posta indesiderata, alcune parti del filtro anti-phishing ma non il filtro antimalware per mittenti specifici, vedere [Creare elenchi di mittenti attendibili in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="02b96-190">To bypass spam filtering, some parts of filtering for phishing, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="02b96-191">Chiedere al mittente di configurare l'autenticazione e-mail per i domini di cui non si è proprietari</span><span class="sxs-lookup"><span data-stu-id="02b96-191">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="02b96-192">A causa dei problemi generati dalla posta indesiderata e dal phishing, Microsoft consiglia a tutte le organizzazioni di posta elettronica di configurare l'autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="02b96-192">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="02b96-193">Anziché configurare override manuali nell'organizzazione, si può chiedere a un amministratore nel dominio di invio di configurare i propri record di autenticazione e-mail.</span><span class="sxs-lookup"><span data-stu-id="02b96-193">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="02b96-194">Anche se in passato non erano tenuti a pubblicare record di autenticazione e-mail, devono farlo se inviano messaggi di posta elettronica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="02b96-194">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="02b96-195">Configurare SPF per pubblicare gli indirizzi IP di invio del dominio e configurare DKIM (se disponibile) per la firma digitale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="02b96-195">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="02b96-196">Dovrebbero inoltre prendere in considerazione la configurazione dei record DMARC.</span><span class="sxs-lookup"><span data-stu-id="02b96-196">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="02b96-197">Se usano mittenti in blocco per inviare messaggi di posta elettronica per loro conto, assicurarsi che il dominio nell'indirizzo Da (se di loro proprietà) sia allineato al dominio che supera i controlli SPF o DMARC.</span><span class="sxs-lookup"><span data-stu-id="02b96-197">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="02b96-198">Verificare che le posizioni seguenti, se in uso, siano incluse nel record SPF:</span><span class="sxs-lookup"><span data-stu-id="02b96-198">Verify the following locations (if they use them) are included in the SPF record:</span></span>

  - <span data-ttu-id="02b96-199">Server di posta elettronica locali.</span><span class="sxs-lookup"><span data-stu-id="02b96-199">On-premises email servers.</span></span>
  - <span data-ttu-id="02b96-200">Messaggi di posta elettronica inviati da un provider di software come un servizio (SaaS).</span><span class="sxs-lookup"><span data-stu-id="02b96-200">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="02b96-201">Messaggi di posta elettronica inviati da un servizio di hosting cloud (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services e così via).</span><span class="sxs-lookup"><span data-stu-id="02b96-201">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="02b96-202">Per i piccoli domini ospitati da un ISP, configurare il record SPF in base alle istruzioni fornite dall'ISP.</span><span class="sxs-lookup"><span data-stu-id="02b96-202">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="02b96-203">Anche se in un primo momento può essere difficile ottenere l'autenticazione dei domini di invio, nel corso del tempo, poiché sempre più filtri per la posta elettronica iniziano a selezionare i loro messaggi come posta indesiderata o addirittura li rifiutano, questo li indurrà a configurare correttamente i record per garantire una migliore distribuzione.</span><span class="sxs-lookup"><span data-stu-id="02b96-203">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="02b96-204">Inoltre, la loro partecipazione può essere utile per la lotta al phishing e può ridurre la possibilità di phishing interno o nelle organizzazioni a cui inviano messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02b96-204">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="02b96-205">Informazioni per i provider di infrastrutture (ISP, ESP o servizi di hosting cloud)</span><span class="sxs-lookup"><span data-stu-id="02b96-205">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="02b96-206">Se si ospita la posta elettronica di un dominio o si fornisce un'infrastruttura di hosting in grado di inviare messaggi di posta elettronica, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02b96-206">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="02b96-207">Verificare che i propri clienti dispongano di documentazione in cui viene spiegato in che modo devono configurare i record SPF</span><span class="sxs-lookup"><span data-stu-id="02b96-207">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="02b96-208">Valutare la possibilità di firmare con firme DKIM i messaggi di posta elettronica in uscita, anche se il cliente non l'ha esplicitamente configurata (firmare con un dominio predefinito).</span><span class="sxs-lookup"><span data-stu-id="02b96-208">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="02b96-209">È anche possibile firmare due volte il messaggio di posta elettronica con DKIM (una volta con il dominio del cliente se è stato configurato e una seconda volta con la firma DKIM della società)</span><span class="sxs-lookup"><span data-stu-id="02b96-209">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="02b96-210">Anche se si autentica la posta elettronica proveniente dalla propria piattaforma, il corretto recapito a Microsoft non è garantito, ma almeno questo assicura che Microsoft non la contrassegni come indesiderata perché non è autenticata.</span><span class="sxs-lookup"><span data-stu-id="02b96-210">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="02b96-211">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="02b96-211">Related links</span></span>

<span data-ttu-id="02b96-212">Per altre informazioni sulle procedure consigliate per i provider di servizi, vedere le [procedure consigliate per la messaggistica mobile di M3AAWG per i provider di servizi](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span><span class="sxs-lookup"><span data-stu-id="02b96-212">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="02b96-213">Scopri come Office 365 usa l’SPF e supporta la convalida di DKIM:</span><span class="sxs-lookup"><span data-stu-id="02b96-213">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="02b96-214">Altre informazioni sull’SPF</span><span class="sxs-lookup"><span data-stu-id="02b96-214">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="02b96-215">Altre informazioni sul DKIM</span><span class="sxs-lookup"><span data-stu-id="02b96-215">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
