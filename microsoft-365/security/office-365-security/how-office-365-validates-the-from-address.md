---
title: In che modo EOP convalida l'indirizzo From per impedire il phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui tipi di indirizzi di posta elettronica accettati o rifiutati da Exchange Online Protection (EOP) e Outlook.com per prevenire il phishing.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205375"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="ee331-103">In che modo EOP convalida l'indirizzo From per impedire il phishing</span><span class="sxs-lookup"><span data-stu-id="ee331-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ee331-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ee331-104">**Applies to**</span></span>
- [<span data-ttu-id="ee331-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ee331-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ee331-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="ee331-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ee331-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee331-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ee331-108">Gli attacchi di phishing sono una minaccia costante per qualsiasi organizzazione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="ee331-109">Oltre a usare indirizzi di posta elettronica mittenti [contraffatti](anti-spoofing-protection.md)(contraffatti), gli utenti malintenzionati spesso utilizzano valori nell'indirizzo mittente che violano gli standard Internet.</span><span class="sxs-lookup"><span data-stu-id="ee331-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="ee331-110">Per evitare questo tipo di phishing, Exchange Online Protection (EOP) e Outlook.com ora richiedono che i messaggi in ingresso includano un indirizzo Mittente conforme a RFC, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ee331-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="ee331-111">Questa applicazione è stata abilitata a novembre 2017.</span><span class="sxs-lookup"><span data-stu-id="ee331-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="ee331-112">**Note**:</span><span class="sxs-lookup"><span data-stu-id="ee331-112">**Notes**:</span></span>

- <span data-ttu-id="ee331-113">Se si riceve regolarmente posta elettronica da organizzazioni con indirizzi From non validi come descritto in questo articolo, incoraggiare tali organizzazioni ad aggiornare i server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.</span><span class="sxs-lookup"><span data-stu-id="ee331-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="ee331-114">Il campo Mittente correlato (utilizzato da Invia per conto di e liste di distribuzione) non è interessato da questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="ee331-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="ee331-115">Per ulteriori informazioni, vedere il post di blog seguente: Cosa si intende quando si fa riferimento al ["mittente" di un messaggio di posta elettronica?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span><span class="sxs-lookup"><span data-stu-id="ee331-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="ee331-116">Panoramica degli standard dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ee331-116">An overview of email message standards</span></span>

<span data-ttu-id="ee331-117">Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ee331-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="ee331-118">La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP.</span><span class="sxs-lookup"><span data-stu-id="ee331-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="ee331-119">Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ee331-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="ee331-120">La busta del messaggio è descritta in [RFC 5321](https://tools.ietf.org/html/rfc5321)e l'intestazione del messaggio è descritta in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="ee331-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="ee331-121">I destinatari non vedono mai la busta effettiva del messaggio perché viene generata dal processo di trasmissione del messaggio e non fa effettivamente parte del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ee331-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="ee331-122">L'indirizzo (noto anche come indirizzo `5321.MailFrom` **MAIL FROM,** mittente P1 o mittente della busta) è l'indirizzo di posta elettronica utilizzato nella trasmissione SMTP del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ee331-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="ee331-123">Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (anche se è possibile che il mittente designi un indirizzo di posta elettronica **Return-Path** diverso).</span><span class="sxs-lookup"><span data-stu-id="ee331-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="ee331-124">L'indirizzo (noto anche come indirizzo mittente o mittente P2) è l'indirizzo di posta elettronica nel campo di intestazione Da ed è l'indirizzo di posta elettronica del mittente visualizzato nei client di posta `5322.From` elettronica. </span><span class="sxs-lookup"><span data-stu-id="ee331-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="ee331-125">L'indirizzo from è al centro dei requisiti di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ee331-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="ee331-126">L'indirizzo From è definito in dettaglio in diverse RFC (ad esempio, le sezioni RFC 5322 3.2.3, 3.4 e 3.4.1 e [RFC 3696).](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="ee331-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="ee331-127">Esistono molte varianti per l'indirizzamento e ciò che viene considerato valido o non valido.</span><span class="sxs-lookup"><span data-stu-id="ee331-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="ee331-128">Per semplicità, è consigliabile utilizzare il formato e le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee331-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="ee331-129">**Nome visualizzato**: frase facoltativa che descrive il proprietario dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="ee331-130">È consigliabile racchiudere sempre il nome visualizzato tra virgolette doppie (") come illustrato.</span><span class="sxs-lookup"><span data-stu-id="ee331-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="ee331-131">Se il nome visualizzato contiene una virgola, _è_ necessario racchiudere la stringa tra virgolette doppie per RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="ee331-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="ee331-132">Se l'indirizzo From include un nome visualizzato, il valore EmailAddress deve essere racchiuso tra parentesi angolari (< >) come illustrato.</span><span class="sxs-lookup"><span data-stu-id="ee331-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="ee331-133">Microsoft consiglia vivamente di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="ee331-134">**EmailAddress**: Un indirizzo di posta elettronica utilizza il formato `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="ee331-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="ee331-135">**local-part**: stringa che identifica la cassetta postale associata all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="ee331-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="ee331-136">Questo valore è univoco all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="ee331-136">This value is unique within the domain.</span></span> <span data-ttu-id="ee331-137">Spesso viene utilizzato il nome utente o il GUID del proprietario della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ee331-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="ee331-138">**domain**: nome di dominio completo (FQDN) del server di posta elettronica che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="ee331-139">Ecco alcune considerazioni aggiuntive per il valore EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="ee331-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="ee331-140">Solo un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-140">Only one email address.</span></span>
  - <span data-ttu-id="ee331-141">È consigliabile non separare le parentesi angolari con spazi.</span><span class="sxs-lookup"><span data-stu-id="ee331-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="ee331-142">Non includere testo aggiuntivo dopo l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="ee331-143">Esempi di indirizzi From validi e non validi</span><span class="sxs-lookup"><span data-stu-id="ee331-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="ee331-144">Gli indirizzi di posta elettronica from seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="ee331-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="ee331-145">`From: < sender@contoso.com >` Non consigliato perché sono presenti spazi tra le parentesi angolari e l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="ee331-146">`From: Microsoft 365 <sender@contoso.com>` Non consigliato perché il nome visualizzato non è racchiuso tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="ee331-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="ee331-147">Gli indirizzi di posta elettronica from seguenti non sono validi:</span><span class="sxs-lookup"><span data-stu-id="ee331-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="ee331-148">**No From address**: Alcuni messaggi automatizzati non includono un indirizzo Mittente.</span><span class="sxs-lookup"><span data-stu-id="ee331-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="ee331-149">In passato, quando Microsoft 365 o Outlook.com riceveva un messaggio senza un indirizzo Mittente, il servizio aggiungeva il seguente indirizzo da predefinito: per rendere il messaggio recapitabile:</span><span class="sxs-lookup"><span data-stu-id="ee331-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="ee331-150">A questo punto, i messaggi con un indirizzo Mittente vuoto non vengono più accettati.</span><span class="sxs-lookup"><span data-stu-id="ee331-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="ee331-151">`From: Microsoft 365 sender@contoso.com` Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="ee331-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="ee331-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` Testo dopo l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="ee331-153">`From: Sender, Example <sender.example@contoso.com>` Il nome visualizzato contiene una virgola, ma non è racchiuso tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="ee331-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="ee331-154">`From: "Microsoft 365 <sender@contoso.com>"` L'intero valore è racchiuso in modo errato tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="ee331-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="ee331-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="ee331-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="ee331-156">`From: Microsoft 365<sender@contoso.com>` Nessuno spazio tra il nome visualizzato e la parentesi angolare sinistra.</span><span class="sxs-lookup"><span data-stu-id="ee331-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="ee331-157">`From: "Microsoft 365"<sender@contoso.com>` Nessuno spazio tra le virgolette doppie di chiusura e la parentesi angolare sinistra.</span><span class="sxs-lookup"><span data-stu-id="ee331-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="ee331-158">Eliminare le risposte automatiche al dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="ee331-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="ee331-159">Non è possibile utilizzare il valore `From: <>` per eliminare le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="ee331-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="ee331-160">Devi invece configurare un record MX null per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ee331-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="ee331-161">Le risposte automatiche (e tutte le risposte) vengono naturalmente soppresse perché non esiste un indirizzo pubblicato a cui il server che risponde può inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="ee331-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="ee331-162">Scegliere un dominio di posta elettronica che non può ricevere posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee331-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="ee331-163">Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ee331-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="ee331-164">Il record MX null per questo dominio è costituito da un singolo punto.</span><span class="sxs-lookup"><span data-stu-id="ee331-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="ee331-165">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee331-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="ee331-166">Per ulteriori informazioni sulla configurazione dei record MX, vedere [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ee331-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="ee331-167">Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="ee331-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="ee331-168">Eseguire l'override dell'imposizione degli indirizzi da</span><span class="sxs-lookup"><span data-stu-id="ee331-168">Override From address enforcement</span></span>

<span data-ttu-id="ee331-169">Per ignorare i requisiti dell'indirizzo mittente per la posta elettronica in ingresso, è possibile utilizzare l'elenco indirizzi IP consentiti (filtro connessioni) o le regole del flusso di posta (note anche come regole di trasporto) come descritto [in Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ee331-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="ee331-170">Non è possibile ignorare i requisiti dell'indirizzo mittente per la posta elettronica in uscita inviata da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee331-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="ee331-171">Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite il supporto.</span><span class="sxs-lookup"><span data-stu-id="ee331-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="ee331-172">Altri modi per prevenire e proteggere da crimini informatici in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee331-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="ee331-173">Per ulteriori informazioni su come rafforzare l'organizzazione contro phishing, posta indesiderata, violazioni dei dati e altre minacce, vedere [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="ee331-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>