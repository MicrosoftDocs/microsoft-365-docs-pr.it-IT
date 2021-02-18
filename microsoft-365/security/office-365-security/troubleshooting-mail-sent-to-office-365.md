---
title: Risoluzione dei problemi della posta elettronica inviati a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sulla risoluzione dei problemi relativi all'invio di posta elettronica alle cartelle Posta in arrivo in Microsoft 365 & procedure consigliate per l'invio di posta inviata in massa ai clienti di Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286382"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="5ff34-103">Risoluzione dei problemi della posta elettronica inviati a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ff34-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ff34-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5ff34-104">**Applies to**</span></span>
- [<span data-ttu-id="5ff34-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ff34-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ff34-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5ff34-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="5ff34-107">In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cartelle Posta in arrivo in Microsoft 365 e procedure consigliate per l'invio di posta inviata in massa ai clienti.</span><span class="sxs-lookup"><span data-stu-id="5ff34-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="5ff34-108">Si sta gestendo la reputazione di invio dell'IP e del dominio?</span><span class="sxs-lookup"><span data-stu-id="5ff34-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="5ff34-109">Le tecnologie di filtro EOP sono progettate per fornire protezione dalla posta indesiderata per Microsoft 365 e altri prodotti Microsoft come Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5ff34-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="5ff34-110">Vengono inoltre sfruttati SPF, DKIM e DMARC; Tecnologie di autenticazione della posta elettronica che consentono di risolvere il problema di spoofing e phishing verificando che il dominio che invia la posta elettronica sia autorizzato a farlo.</span><span class="sxs-lookup"><span data-stu-id="5ff34-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="5ff34-111">Il filtro EOP è influenzato da una serie di fattori correlati all'INDIRIZZO IP di invio, al dominio, all'autenticazione, all'accuratezza degli elenchi, alle percentuali di reclamo, al contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5ff34-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="5ff34-112">Di questi, uno dei fattori principali per la reputazione di un mittente e la loro capacità di recapitare la posta elettronica è la frequenza di reclami per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5ff34-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="5ff34-113">Si sta inviando posta elettronica da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="5ff34-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="5ff34-114">Gli indirizzi IP non utilizzati in precedenza per inviare posta elettronica in genere non hanno alcuna reputazione creata nei nostri sistemi.</span><span class="sxs-lookup"><span data-stu-id="5ff34-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="5ff34-115">Di conseguenza, è più probabile che si verifichino problemi di recapito per i messaggi di posta elettronica provenienti da nuovi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="5ff34-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="5ff34-116">Una volta che l'IP ha creato una reputazione per non inviare posta indesiderata, EOP in genere consentirà una migliore esperienza di recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ff34-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="5ff34-117">I nuovi IP aggiunti per i domini autenticati in record SPF esistenti in genere hanno il vantaggio di ereditare parte della reputazione di invio del dominio.</span><span class="sxs-lookup"><span data-stu-id="5ff34-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="5ff34-118">Se il dominio ha una buona reputazione di invio, i nuovi IP potrebbero avere tempi di avvio più rapidi.</span><span class="sxs-lookup"><span data-stu-id="5ff34-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="5ff34-119">Un nuovo IP può prevedere di essere completamente dilagato entro un paio di settimane o prima a seconda del volume, dell'accuratezza dell'elenco e delle percentuali di reclami per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5ff34-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="5ff34-120">Verificare che il DNS sia configurato correttamente</span><span class="sxs-lookup"><span data-stu-id="5ff34-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="5ff34-121">Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, è necessario contattare il provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="5ff34-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="5ff34-122">Assicurarsi di non annunciarsi come IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="5ff34-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="5ff34-123">È possibile che non si accettino messaggi di posta elettronica provenienti da mittenti che non riescono a eseguire una ricerca DNS inversa.</span><span class="sxs-lookup"><span data-stu-id="5ff34-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="5ff34-124">In alcuni casi, i mittenti legittimi si annunciano erroneamente come IP non instradabile su Internet quando tentano di aprire una connessione a EOP.</span><span class="sxs-lookup"><span data-stu-id="5ff34-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="5ff34-125">Gli indirizzi IP riservati per la rete privata (non instradabile) includono:</span><span class="sxs-lookup"><span data-stu-id="5ff34-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="5ff34-126">192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="5ff34-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="5ff34-127">10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="5ff34-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="5ff34-128">172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="5ff34-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="5ff34-129">Si è ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="5ff34-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="5ff34-130">Alcuni problemi di recapito sono il risultato del blocco dell'indirizzo IP del mittente da parte di Microsoft o perché l'account utente viene identificato come mittente escluso a causa di attività di posta indesiderata precedente.</span><span class="sxs-lookup"><span data-stu-id="5ff34-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="5ff34-131">Se si ritiene di aver ricevuto il rapporto di mancato recapito per errore, seguire innanzitutto le istruzioni nel messaggio del rapporto di mancato recapito per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="5ff34-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="5ff34-132">Per ulteriori informazioni sull'errore ricevuto, vedere l'elenco dei codici di errore nei rapporti di mancato recapito della posta [elettronica in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="5ff34-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="5ff34-133">Ad esempio, se si riceve il seguente rapporto di mancato recapito, indica che l'indirizzo IP di invio è stato bloccato da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="5ff34-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="5ff34-134">Per richiedere la rimozione da questo elenco, è possibile utilizzare il portale di rimozione per rimuoversi [dall'elenco dei mittenti bloccati.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="5ff34-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="5ff34-135">Il messaggio di posta elettronica è atterrato nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="5ff34-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="5ff34-136">Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile collaborare con il destinatario per inviare questo messaggio falso positivo al team di analisi della posta indesiderata di Microsoft, che valuterà e analerà il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5ff34-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="5ff34-137">Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5ff34-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="5ff34-138">Il traffico proveniente dall'indirizzo IP viene limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="5ff34-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="5ff34-139">Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP viene limitato da EOP, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ff34-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="5ff34-140">Il rapporto di mancato recapito è stato ricevuto perché sono state rilevate attività sospette dall'indirizzo IP e sono state temporaneamente limitate durante un'ulteriore valutazione.</span><span class="sxs-lookup"><span data-stu-id="5ff34-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="5ff34-141">Se il sospetto viene eliminato tramite valutazione, questa restrizione verrà revocata a breve.</span><span class="sxs-lookup"><span data-stu-id="5ff34-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="5ff34-142">I can't receive email from senders in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ff34-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="5ff34-143">Per ricevere messaggi dagli utenti, assicurarsi che la rete consenta le connessioni dagli indirizzi IP utilizzati da EOP nei datacenter.</span><span class="sxs-lookup"><span data-stu-id="5ff34-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="5ff34-144">Per ulteriori informazioni, vedere [Indirizzi IP di Exchange Online Protection.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="5ff34-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="5ff34-145">Procedure consigliate per l'invio in blocco della posta elettronica agli utenti di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ff34-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="5ff34-146">Se spesso si conducono campagne di posta elettronica in blocco agli utenti di Microsoft 365 e si desidera assicurarsi che i messaggi di posta elettronica arrivino in modo sicuro e corretto, seguire i suggerimenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="5ff34-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="5ff34-147">Verificare che il nome Da rifletta chi sta inviando il messaggio</span><span class="sxs-lookup"><span data-stu-id="5ff34-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="5ff34-148">L'oggetto deve essere un breve riepilogo dell'oggetto del messaggio e il corpo del messaggio deve indicare chiaramente e in modo sintetico l'offerta, il servizio o il prodotto.</span><span class="sxs-lookup"><span data-stu-id="5ff34-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="5ff34-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ff34-149">For example:</span></span>

<span data-ttu-id="5ff34-150">Impostazione corretta:</span><span class="sxs-lookup"><span data-stu-id="5ff34-150">Correct:</span></span>

> <span data-ttu-id="5ff34-151">Da: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="5ff34-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="5ff34-152">Oggetto: Catalogo aggiornato per la festività di Natale.</span><span class="sxs-lookup"><span data-stu-id="5ff34-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="5ff34-153">Impostazione non corretta:</span><span class="sxs-lookup"><span data-stu-id="5ff34-153">Incorrect:</span></span>

> <span data-ttu-id="5ff34-154">Da: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="5ff34-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="5ff34-155">Oggetto: Cataloghi</span><span class="sxs-lookup"><span data-stu-id="5ff34-155">Subject: Catalogs</span></span>

<span data-ttu-id="5ff34-156">Maggiore è la facilità con cui gli utenti possono sapere chi si è e cosa si sta facendo, minore sarà la difficoltà di recapito attraverso la maggior parte dei filtri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5ff34-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="5ff34-157">Includi sempre un'opzione di annullamento della sottoscrizione nei messaggi di posta elettronica della campagna</span><span class="sxs-lookup"><span data-stu-id="5ff34-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="5ff34-158">I messaggi di posta elettronica di marketing, in particolare le newsletter, devono sempre includere un modo per annullare la sottoscrizione dei messaggi di posta elettronica futuri.</span><span class="sxs-lookup"><span data-stu-id="5ff34-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="5ff34-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ff34-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="5ff34-160">Alcuni mittenti includono questa opzione richiedendo ai destinatari di inviare un messaggio di posta elettronica a un determinato alias con "Annulla sottoscrizione" nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5ff34-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="5ff34-161">Non è preferibile all'esempio precedente con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="5ff34-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="5ff34-162">Se si sceglie di richiedere ai destinatari di inviare un messaggio di posta elettronica, assicurarsi che quando fanno clic sul collegamento, tutti i campi obbligatori siano precompilato.</span><span class="sxs-lookup"><span data-stu-id="5ff34-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="5ff34-163">Usare l'opzione di consenso esplicito doppio per la registrazione di messaggi di posta elettronica o newsletter di marketing</span><span class="sxs-lookup"><span data-stu-id="5ff34-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="5ff34-164">Questa procedura consigliata per il settore è consigliata se l'azienda richiede o incoraggia gli utenti a registrare le proprie informazioni di contatto per accedere al prodotto o ai servizi.</span><span class="sxs-lookup"><span data-stu-id="5ff34-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="5ff34-165">Alcune società fanno in modo che gli utenti si iscrizionino automaticamente a messaggi di posta elettronica di marketing o newsletter durante il processo di registrazione, ma questa è considerata una pratica di marketing discutibile nel mondo del filtro della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ff34-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="5ff34-166">Durante il processo di registrazione, se la casella di controllo "Sì, inviami la newsletter" o "Sì, inviami offerte speciali" è selezionata per impostazione predefinita, gli utenti che non prestano particolare attenzione potrebbero iscriversi involontariamente a messaggi di posta elettronica di marketing o newsletter che non vogliono ricevere.</span><span class="sxs-lookup"><span data-stu-id="5ff34-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="5ff34-167">Consigliamo invece l'opzione di consenso esplicito doppio, il che significa che la casella di controllo per i messaggi di posta elettronica o le newsletter di marketing è deselezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5ff34-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="5ff34-168">Inoltre, una volta inviato il modulo di registrazione, all'utente viene inviato un messaggio di posta elettronica di verifica con un URL che consente di confermare la decisione di ricevere messaggi di posta elettronica di marketing.</span><span class="sxs-lookup"><span data-stu-id="5ff34-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="5ff34-169">In questo modo si garantisce che solo gli utenti che desiderano ricevere messaggi di posta elettronica di marketing siano registrati per i messaggi di posta elettronica, cancellando successivamente la società mittente di eventuali pratiche di marketing della posta elettronica discutibile.</span><span class="sxs-lookup"><span data-stu-id="5ff34-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="5ff34-170">Verificare che il contenuto dei messaggi di posta elettronica sia trasparente e tracciabile</span><span class="sxs-lookup"><span data-stu-id="5ff34-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="5ff34-171">Tanto importante quanto il modo in cui vengono inviati i messaggi di posta elettronica è il contenuto che contengono.</span><span class="sxs-lookup"><span data-stu-id="5ff34-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="5ff34-172">Quando si crea contenuto di posta elettronica, utilizzare le procedure consigliate seguenti per assicurarsi che i messaggi di posta elettronica non siano contrassegnati dai servizi di filtro della posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="5ff34-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="5ff34-173">Quando il messaggio di posta elettronica richiede ai destinatari di aggiungere il mittente alla rubrica, deve chiaramente confermare che tale azione non è una garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="5ff34-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="5ff34-174">I reindirizzamenti inclusi nel corpo del messaggio devono essere simili e coerenti e non multipli e vari.</span><span class="sxs-lookup"><span data-stu-id="5ff34-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="5ff34-175">Un reindirizzamento in questo contesto è qualsiasi elemento che punti al messaggio, ad esempio collegamenti e documenti.</span><span class="sxs-lookup"><span data-stu-id="5ff34-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="5ff34-176">Se hai molti collegamenti per la pubblicità o l'annullamento della sottoscrizione o per aggiornare i collegamenti del profilo, questi devono puntare allo stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="5ff34-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="5ff34-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ff34-177">For example:</span></span>

  <span data-ttu-id="5ff34-178">Corretto (tutti i domini sono gli stessi):</span><span class="sxs-lookup"><span data-stu-id="5ff34-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="5ff34-179">Non corretto (tutti i domini sono diversi):</span><span class="sxs-lookup"><span data-stu-id="5ff34-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="5ff34-180">Evitare contenuti con immagini e allegati di grandi dimensioni o messaggi composti esclusivamente da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="5ff34-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="5ff34-181">La privacy pubblica o le impostazioni P3P devono segnalare chiaramente la presenza di pixel di monitoraggio (bug Web o beacon).</span><span class="sxs-lookup"><span data-stu-id="5ff34-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="5ff34-182">Rimuovere alias di posta elettronica non corretti dai database</span><span class="sxs-lookup"><span data-stu-id="5ff34-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="5ff34-183">Qualsiasi alias di posta elettronica nel database che crea un rimbalzo non è necessario e mette i messaggi di posta elettronica in uscita a rischio di ulteriore controllo da parte dei servizi di filtro della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ff34-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="5ff34-184">Verificare che il database di posta elettronica sia aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5ff34-184">Ensure that your email database is up-to-date.</span></span>
