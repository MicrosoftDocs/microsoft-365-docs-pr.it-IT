---
title: Risoluzione dei problemi di posta elettronica inviata a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni per la risoluzione dei problemi relativi all'invio di posta elettronica alle cassette postali in Microsoft 365 & procedure consigliate per la posta in blocco ai clienti di Microsoft 365.
ms.openlocfilehash: 0d9c1646aa7491b3da458c7cb0ddeb908873153a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208598"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="c9793-103">Risoluzione dei problemi di posta elettronica inviata a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9793-103">Troubleshooting mail sent to Microsoft 365</span></span>

<span data-ttu-id="c9793-104">In questo articolo vengono fornite informazioni per la risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cassette postali in Microsoft 365 e le procedure consigliate per la posta in blocco ai clienti</span><span class="sxs-lookup"><span data-stu-id="c9793-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="c9793-105">Si sta gestendo la reputazione di invio di IP e domini?</span><span class="sxs-lookup"><span data-stu-id="c9793-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="c9793-106">Le tecnologie di filtro EOP sono progettate per fornire la protezione da posta indesiderata per Microsoft 365 e altri prodotti Microsoft come Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c9793-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="c9793-107">È inoltre possibile utilizzare SPF, DKIM e DMARC; tecnologie di autenticazione della posta elettronica che consentono di risolvere il problema dello spoofing e del phishing verificando che il dominio che invia il messaggio di posta elettronica sia autorizzato a farlo.</span><span class="sxs-lookup"><span data-stu-id="c9793-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="c9793-108">Il filtro EOP è influenzato da una serie di fattori correlati all'IP di invio, al dominio, all'autenticazione, all'accuratezza degli elenchi, alle tariffe dei reclami, al contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="c9793-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="c9793-109">Tra questi, uno dei fattori principali per abbassare la reputazione del mittente e la possibilità di inviare messaggi di posta elettronica è la frequenza dei reclami per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c9793-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="c9793-110">Si sta inviando messaggi di posta elettronica da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="c9793-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="c9793-111">Gli indirizzi IP non utilizzati in precedenza per inviare messaggi di posta elettronica in genere non dispongono di una reputazione integrata nei sistemi.</span><span class="sxs-lookup"><span data-stu-id="c9793-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="c9793-112">Di conseguenza, è più probabile che i messaggi di posta elettronica provenienti da nuovi IP sperimentino problemi di recapito.</span><span class="sxs-lookup"><span data-stu-id="c9793-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="c9793-113">Una volta che l'IP ha creato una reputazione per l'invio di posta indesiderata, EOP consentirà una migliore esperienza di recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c9793-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="c9793-114">I nuovi indirizzi IP aggiunti per i domini autenticati con i record SPF esistenti in genere avvertono l'ulteriore vantaggio di ereditare una parte della reputazione di invio del dominio.</span><span class="sxs-lookup"><span data-stu-id="c9793-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="c9793-115">Se il dominio ha una buona reputazione di invio, è possibile che i nuovi IP possano riscontrare tempi di rampa più veloci.</span><span class="sxs-lookup"><span data-stu-id="c9793-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="c9793-116">Un nuovo IP può pretendere di essere completamente rampante entro un paio di settimane o prima a seconda del volume, dell'accuratezza degli elenchi e delle tariffe di reclamo per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c9793-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="c9793-117">Verificare che il DNS sia configurato correttamente</span><span class="sxs-lookup"><span data-stu-id="c9793-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="c9793-118">Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, sarà necessario contattare il provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="c9793-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="c9793-119">Assicurarsi di non essere pubblicizzati come IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="c9793-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="c9793-120">Non è possibile accettare messaggi di posta elettronica provenienti da mittenti che non eseguono una ricerca DNS inversa.</span><span class="sxs-lookup"><span data-stu-id="c9793-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="c9793-121">In alcuni casi, i mittenti legittimi si annunciano in modo errato come IP instradabile non Internet quando si tenta di aprire una connessione a EOP.</span><span class="sxs-lookup"><span data-stu-id="c9793-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="c9793-122">Gli indirizzi IP riservati per la rete privata (non instradabile) includono:</span><span class="sxs-lookup"><span data-stu-id="c9793-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="c9793-123">192.168.0.0/16 (o 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="c9793-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="c9793-124">10.0.0.0/8 (o 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="c9793-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="c9793-125">172.16.0.0/11 (o 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="c9793-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="c9793-126">Si è ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="c9793-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="c9793-127">Alcuni problemi di recapito sono il risultato dell'indirizzo IP del mittente che è stato bloccato da Microsoft o perché l'account utente è stato identificato come mittente vietato a causa di precedenti attività di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c9793-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="c9793-128">Se si ritiene di aver ricevuto il rapporto di mancato recapito in caso di errore, seguire le istruzioni riportate nel messaggio di mancato recapito per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c9793-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="c9793-129">Per ulteriori informazioni sull'errore ricevuto, vedere l'elenco dei codici di errore nei [rapporti di mancato recapito della posta elettronica in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="c9793-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="c9793-130">Ad esempio, se si riceve il rapporto di mancato recapito seguente, indica che l'indirizzo IP di invio è stato bloccato da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c9793-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="c9793-131">Per richiedere la rimozione da questo elenco, è possibile [utilizzare il portale di delist per rimuovere se stessi dall'elenco dei mittenti bloccati](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="c9793-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="c9793-132">La posta elettronica è atterrata nella cartella posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="c9793-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="c9793-133">Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile collaborare con il destinatario per inviare questo messaggio falso positivo al team di analisi di posta indesiderata di Microsoft, che valuterà e analizzerà il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c9793-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="c9793-134">Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c9793-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="c9793-135">Il traffico proveniente dall'indirizzo IP è limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="c9793-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="c9793-136">Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP è sottoposto a limitazione da EOP, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9793-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="c9793-137">È stato ricevuto il rapporto di mancato recapito perché l'attività sospetta è stata rilevata dall'indirizzo IP ed è stata temporaneamente limitata durante la valutazione.</span><span class="sxs-lookup"><span data-stu-id="c9793-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="c9793-138">Se il sospetto è deselezionato tramite valutazione, questa restrizione verrà revocata a breve.</span><span class="sxs-lookup"><span data-stu-id="c9793-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="c9793-139">Non è possibile ricevere messaggi di posta elettronica da mittenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9793-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="c9793-140">Per ricevere i messaggi dagli utenti, verificare che la rete consenta le connessioni dagli indirizzi IP utilizzati da EOP nei data center.</span><span class="sxs-lookup"><span data-stu-id="c9793-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="c9793-141">Per ulteriori informazioni, vedere [indirizzi IP di Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="c9793-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="c9793-142">Procedure consigliate per l'invio di messaggi di posta elettronica agli utenti di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9793-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="c9793-143">Se si eseguono spesso campagne di posta elettronica in blocco per gli utenti di Microsoft 365 e si vuole garantire che i messaggi vengano verificati in modo sicuro e tempestivo, seguire i suggerimenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c9793-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="c9793-144">Verificare che il nome del mittente rispecchi chi sta inviando il messaggio</span><span class="sxs-lookup"><span data-stu-id="c9793-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="c9793-145">L'oggetto dovrebbe essere un breve riepilogo del messaggio e il corpo del messaggio deve indicare in modo chiaro e conciso cosa significa l'offerta, il servizio o il prodotto.</span><span class="sxs-lookup"><span data-stu-id="c9793-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="c9793-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9793-146">For example:</span></span>

<span data-ttu-id="c9793-147">Impostazione corretta:</span><span class="sxs-lookup"><span data-stu-id="c9793-147">Correct:</span></span>

> <span data-ttu-id="c9793-148">Da: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="c9793-148">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="c9793-149">Oggetto: aggiornamento del catalogo per la stagione natalizia.</span><span class="sxs-lookup"><span data-stu-id="c9793-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="c9793-150">Impostazione non corretta:</span><span class="sxs-lookup"><span data-stu-id="c9793-150">Incorrect:</span></span>

> <span data-ttu-id="c9793-151">Da: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9793-151">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="c9793-152">Oggetto: Cataloghi</span><span class="sxs-lookup"><span data-stu-id="c9793-152">Subject: Catalogs</span></span>

<span data-ttu-id="c9793-153">Più è facile per gli utenti sapere chi è e cosa si sta facendo, minore sarà la difficoltà con la maggior parte dei filtri per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c9793-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="c9793-154">Includi sempre un'opzione di annullamento della sottoscrizione nei messaggi di posta elettronica della campagna</span><span class="sxs-lookup"><span data-stu-id="c9793-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="c9793-155">I messaggi di posta elettronica di marketing, in particolare le newsletter, dovrebbero includere sempre un modo di annullamento della sottoscrizione da messaggi di posta elettronica futuri.</span><span class="sxs-lookup"><span data-stu-id="c9793-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="c9793-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9793-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="c9793-157">Alcuni mittenti includono questa opzione richiedendo ai destinatari di inviare un messaggio di posta elettronica a un determinato alias con "Annulla sottoscrizione" nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c9793-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="c9793-158">Questo non è preferibile all'esempio di un clic sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="c9793-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="c9793-159">Se si sceglie di richiedere ai destinatari di inviare un messaggio di posta elettronica, verificare che quando si fa clic sul collegamento, tutti i campi richiesti siano precompilati.</span><span class="sxs-lookup"><span data-stu-id="c9793-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="c9793-160">Utilizzare l'opzione double opt-in per la registrazione della posta elettronica o della newsletter di marketing</span><span class="sxs-lookup"><span data-stu-id="c9793-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="c9793-161">Questa procedura consigliata per il settore è consigliabile se la propria azienda richiede o incoraggia gli utenti a registrare le proprie informazioni di contatto per accedere al prodotto o ai servizi.</span><span class="sxs-lookup"><span data-stu-id="c9793-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="c9793-162">Alcune aziende hanno la consuetudine di iscrivere automaticamente gli utenti per i messaggi di posta elettronica di marketing o di e-newsletter durante il processo di registrazione, ma questa è considerata una pratica di marketing discutibile nel mondo del filtraggio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c9793-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="c9793-163">Durante il processo di registrazione, se la casella di controllo "Sì, Inviami la tua newsletter" o "Sì, Inviami offerte speciali" è selezionata per impostazione predefinita, gli utenti che non prestano molta attenzione possono involontariamente iscriversi per la posta elettronica di marketing o le newsletter che non desiderano ricevere.</span><span class="sxs-lookup"><span data-stu-id="c9793-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="c9793-164">È consigliabile invece l'opzione double opt-in, il che significa che la casella di controllo per i messaggi di posta elettronica di marketing o le newsletter è deselezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9793-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="c9793-165">Inoltre, una volta che il modulo di registrazione è stato inviato, un messaggio di posta elettronica di verifica viene inviato all'utente con un URL che consente di confermare la decisione di ricevere messaggi di posta elettronica di marketing.</span><span class="sxs-lookup"><span data-stu-id="c9793-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="c9793-166">In questo modo si garantisce che solo gli utenti che desiderano ricevere la posta elettronica di marketing siano iscritti per la posta elettronica, successivamente deselezionando la società di invio di eventuali pratiche di marketing della posta elettronica discutibili.</span><span class="sxs-lookup"><span data-stu-id="c9793-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="c9793-167">Verificare che il contenuto del messaggio di posta elettronica sia trasparente e tracciabile</span><span class="sxs-lookup"><span data-stu-id="c9793-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="c9793-168">Altrettanto importante del modo in cui vengono inviati i messaggi di posta elettronica è il contenuto che contengono.</span><span class="sxs-lookup"><span data-stu-id="c9793-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="c9793-169">Quando si crea il contenuto della posta elettronica, utilizzare le procedure consigliate seguenti per garantire che i messaggi di posta elettronica non vengano contrassegnati tramite i servizi di filtraggio delle e-mail:</span><span class="sxs-lookup"><span data-stu-id="c9793-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="c9793-170">Quando il messaggio di posta elettronica richiede che i destinatari aggiungono il mittente alla Rubrica, è necessario indicare chiaramente che tale azione non è una garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="c9793-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="c9793-171">I reindirizzamenti inclusi nel corpo del messaggio devono essere simili e coerenti e non multipli e diversificati.</span><span class="sxs-lookup"><span data-stu-id="c9793-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="c9793-172">Un reindirizzamento in questo contesto è qualsiasi elemento che punti al di fuori del messaggio, ad esempio collegamenti e documenti.</span><span class="sxs-lookup"><span data-stu-id="c9793-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="c9793-173">Se si dispone di numerosi collegamenti pubblicitari o di annullamento della sottoscrizione oppure si aggiornano i collegamenti dei profili, tutti gli utenti devono puntare allo stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="c9793-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="c9793-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9793-174">For example:</span></span>

  <span data-ttu-id="c9793-175">Impostazione corretta:</span><span class="sxs-lookup"><span data-stu-id="c9793-175">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="c9793-176">Impostazione non corretta:</span><span class="sxs-lookup"><span data-stu-id="c9793-176">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="c9793-177">Evitare contenuti con immagini e allegati di grandi dimensioni o messaggi composti unicamente da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="c9793-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="c9793-178">La privacy pubblica o le impostazioni di P3P devono indicare chiaramente la presenza di pixel di rilevamento (bug Web o beacon).</span><span class="sxs-lookup"><span data-stu-id="c9793-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="c9793-179">Rimuovere gli alias di posta elettronica non corretti dai database</span><span class="sxs-lookup"><span data-stu-id="c9793-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="c9793-180">Qualsiasi alias di posta elettronica nel database che consente di creare un rimbalzo non è necessario e pone i messaggi di posta elettronica in uscita a rischio per un ulteriore controllo tramite i servizi di filtraggio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c9793-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="c9793-181">Verificare che il database di posta elettronica sia aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c9793-181">Ensure that your email database is up-to-date.</span></span>
