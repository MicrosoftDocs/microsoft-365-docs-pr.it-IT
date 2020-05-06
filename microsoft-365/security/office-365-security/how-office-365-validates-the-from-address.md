---
title: Come viene convalidato l'indirizzo da Microsoft 365 per impedire il phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Per evitare il phishing, Microsoft 365 e Outlook.com ora richiedono la conformità RFC per gli indirizzi da:.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef361c7009cc8903ab2721d299412b7d44a4f87c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034083"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="4efdb-103">Come viene convalidato l'indirizzo da Microsoft 365 per impedire il phishing</span><span class="sxs-lookup"><span data-stu-id="4efdb-103">How Microsoft 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="4efdb-104">Gli account di posta elettronica di Microsoft 365 ricevono un numero sempre più elevato di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="4efdb-104">Microsoft 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="4efdb-105">Oltre a utilizzare [gli indirizzi di posta elettronica del mittente falsificati (falsificati)](anti-spoofing-protection.md), gli utenti malintenzionati utilizzano spesso valori nell'indirizzo from che violano gli standard di Internet.</span><span class="sxs-lookup"><span data-stu-id="4efdb-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="4efdb-106">Per evitare questo tipo di phishing, Microsoft 365 e Outlook.com ora richiedono che i messaggi in ingresso includano un indirizzo conforme a RFC, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4efdb-106">To help prevent this type of phishing, Microsoft 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="4efdb-107">Questo Enforcement è stato abilitato nel novembre 2017.</span><span class="sxs-lookup"><span data-stu-id="4efdb-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="4efdb-108">**Note**:</span><span class="sxs-lookup"><span data-stu-id="4efdb-108">**Notes**:</span></span>

- <span data-ttu-id="4efdb-109">Se si ricevono regolarmente messaggi di posta elettronica provenienti da organizzazioni che hanno indirizzi non corretti come descritto in questo argomento, incoraggiare queste organizzazioni a aggiornare i propri server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.</span><span class="sxs-lookup"><span data-stu-id="4efdb-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="4efdb-110">Il campo mittente correlato (utilizzato da Send per conto e mailing list) non è influenzato da questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="4efdb-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="4efdb-111">Per ulteriori informazioni, vedere il post di Blog seguente: [che cosa si intende quando si fa riferimento al ' mittente ' di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="4efdb-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="4efdb-112">Panoramica degli standard dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4efdb-112">An overview of email message standards</span></span>

<span data-ttu-id="4efdb-113">Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="4efdb-114">La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP.</span><span class="sxs-lookup"><span data-stu-id="4efdb-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="4efdb-115">Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="4efdb-116">La busta del messaggio è descritta in [rfc 5321](https://tools.ietf.org/html/rfc5321)e l'intestazione del messaggio è descritta in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="4efdb-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="4efdb-117">I destinatari non vedono mai la busta reale del messaggio perché viene generata dal processo di trasmissione del messaggio e non è in realtà parte del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="4efdb-118">L' `5321.MailFrom` indirizzo (noto anche come indirizzo di **posta elettronica** , mittente P1 o mittente busta) è l'indirizzo di posta elettronica utilizzato per la trasmissione SMTP del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="4efdb-119">Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (sebbene sia possibile che il mittente designi un indirizzo di posta elettronica diverso per il **percorso restituito** ).</span><span class="sxs-lookup"><span data-stu-id="4efdb-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="4efdb-120">L' `5322.From` indirizzo di posta elettronica del mittente viene visualizzato nei client di posta elettronica (noto anche come indirizzo da o mittente P2) e è l'indirizzo di posta elettronica nel campo dell'intestazione **from** .</span><span class="sxs-lookup"><span data-stu-id="4efdb-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="4efdb-121">L'indirizzo mittente è lo stato attivo dei requisiti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4efdb-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="4efdb-122">L'indirizzo from è definito dettagliatamente in più RFC, ad esempio le sezioni di RFC 5322 3.2.3, 3,4 e 3.4.1 e [rfc 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="4efdb-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="4efdb-123">Sono presenti molte varianti sull'indirizzamento e su ciò che è considerato valido o non valido.</span><span class="sxs-lookup"><span data-stu-id="4efdb-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="4efdb-124">Per semplificare le operazioni, è consigliabile utilizzare il formato e le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4efdb-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="4efdb-125">**Nome visualizzato**: una frase facoltativa che descrive il proprietario dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="4efdb-126">È consigliabile racchiudere sempre il nome visualizzato tra virgolette doppie ("), come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="4efdb-127">Se il nome visualizzato contiene una virgola, è _necessario_ racchiudere la stringa tra virgolette doppie per RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="4efdb-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="4efdb-128">Se l'indirizzo from include un nome visualizzato, il valore EmailAddress deve essere racchiuso tra parentesi angolari (< >) come illustrato.</span><span class="sxs-lookup"><span data-stu-id="4efdb-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="4efdb-129">Microsoft consiglia vivamente di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="4efdb-130">**EmailAddress**: l'indirizzo di posta elettronica utilizza `local-part@domain`il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="4efdb-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="4efdb-131">**local-part**: una stringa che identifica la cassetta postale associata all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4efdb-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="4efdb-132">Questo valore è univoco all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="4efdb-132">This value is unique within the domain.</span></span> <span data-ttu-id="4efdb-133">Spesso, viene utilizzato il nome utente o il GUID del proprietario della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="4efdb-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="4efdb-134">**dominio**: il nome di dominio completo (FQDN) del server di posta elettronica che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="4efdb-135">Di seguito sono riportate alcune considerazioni aggiuntive relative al valore EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="4efdb-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="4efdb-136">Un solo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-136">Only one email address.</span></span>
  - <span data-ttu-id="4efdb-137">Si consiglia di non separare le parentesi angolari con gli spazi.</span><span class="sxs-lookup"><span data-stu-id="4efdb-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="4efdb-138">Non includere testo aggiuntivo dopo l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="4efdb-139">Esempi di indirizzi validi e non validi</span><span class="sxs-lookup"><span data-stu-id="4efdb-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="4efdb-140">Gli indirizzi di posta elettronica seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="4efdb-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="4efdb-141">`From: < sender@contoso.com >`(Non consigliato perché esistono spazi tra le parentesi angolari e l'indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="4efdb-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="4efdb-142">`From: Microsoft 365 <sender@contoso.com>`(Non consigliato perché il nome visualizzato non è racchiuso tra virgolette doppie).</span><span class="sxs-lookup"><span data-stu-id="4efdb-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="4efdb-143">Gli indirizzi di posta elettronica seguenti non sono validi:</span><span class="sxs-lookup"><span data-stu-id="4efdb-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="4efdb-144">**Nessun indirizzo**: alcuni messaggi automatici non includono un indirizzo mittente.</span><span class="sxs-lookup"><span data-stu-id="4efdb-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="4efdb-145">In passato, quando Microsoft 365 o Outlook.com ha ricevuto un messaggio senza indirizzo mittente, il servizio ha aggiunto l'indirizzo predefinito seguente: per rendere il messaggio risultato finale:</span><span class="sxs-lookup"><span data-stu-id="4efdb-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="4efdb-146">A questo punto, i messaggi con un indirizzo vuoto non vengono più accettati.</span><span class="sxs-lookup"><span data-stu-id="4efdb-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="4efdb-147">`From: Microsoft 365 sender@contoso.com`(Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="4efdb-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="4efdb-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Testo dopo l'indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="4efdb-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="4efdb-149">`From: Sender, Example <sender.example@contoso.com>`Il nome visualizzato contiene una virgola, ma non è racchiuso tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="4efdb-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="4efdb-150">`From: "Microsoft 365 <sender@contoso.com>"`(L'intero valore viene racchiuso in modo errato tra virgolette doppie).</span><span class="sxs-lookup"><span data-stu-id="4efdb-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="4efdb-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="4efdb-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="4efdb-152">`From: Microsoft 365<sender@contoso.com>`(Nessuna spaziatura tra il nome visualizzato e la parentesi uncinata sinistra).</span><span class="sxs-lookup"><span data-stu-id="4efdb-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="4efdb-153">`From: "Microsoft 365"<sender@contoso.com>`(Nessuna spaziatura tra le virgolette doppie di chiusura e la parentesi angolare sinistra).</span><span class="sxs-lookup"><span data-stu-id="4efdb-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="4efdb-154">Sopprimere le risposte automatiche al dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="4efdb-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="4efdb-155">Non è possibile utilizzare il `From: <>` valore per sopprimere le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="4efdb-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="4efdb-156">Al contrario, è necessario configurare un record MX null per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4efdb-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="4efdb-157">Le risposte automatiche (e tutte le risposte) sono naturalmente soppressi perché non esiste alcun indirizzo pubblicato a cui il server che risponde può inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="4efdb-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="4efdb-158">Scegliere un dominio di posta elettronica che non sia in grado di ricevere posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4efdb-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="4efdb-159">Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4efdb-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="4efdb-160">Il record MX null per questo dominio è costituito da un singolo punto.</span><span class="sxs-lookup"><span data-stu-id="4efdb-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="4efdb-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4efdb-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="4efdb-162">Per ulteriori informazioni sulla configurazione dei record MX, vedere [creare record DNS presso qualsiasi provider di hosting DNS per Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4efdb-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="4efdb-163">Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="4efdb-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="4efdb-164">Sostituzione dall'applicazione degli indirizzi</span><span class="sxs-lookup"><span data-stu-id="4efdb-164">Override From address enforcement</span></span>

<span data-ttu-id="4efdb-165">Per ignorare i requisiti di indirizzo per la posta elettronica in ingresso, è possibile utilizzare l'elenco indirizzi IP consentiti (filtro connessioni) o il flusso di posta (note anche come regole di trasporto) come descritto in [creare elenchi di mittenti attendibili in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4efdb-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="4efdb-166">Non è possibile eseguire l'override dei requisiti degli indirizzi per la posta elettronica in uscita inviata da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4efdb-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="4efdb-167">Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite supporto.</span><span class="sxs-lookup"><span data-stu-id="4efdb-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="4efdb-168">Altri modi per prevenire e proteggere i reati informatici in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4efdb-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="4efdb-169">Per ulteriori informazioni su come è possibile rafforzare la propria organizzazione contro il phishing, la posta indesiderata, le violazioni dei dati e altre minacce, vedere [Top 10 modi per proteggere i piani Microsoft 365 for business](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="4efdb-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>