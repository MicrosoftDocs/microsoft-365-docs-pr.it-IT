---
title: Utilizzare DMARC per convalidare la posta elettronica in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare l'autenticazione dei messaggi, la creazione di report e la conformità di un dominio (DMARC) per convalidare i messaggi inviati dall'organizzazione di Office 365.
ms.openlocfilehash: 24196139d46df8de7813e827e57d04c4bf9146b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084588"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a><span data-ttu-id="94ef9-103">Utilizzare DMARC per convalidare la posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-103">Use DMARC to validate email in Office 365</span></span>

<span data-ttu-id="94ef9-104">Autenticazione dei messaggi, la creazione di report e la conformità di un dominio ([DMARC](https://dmarc.org)) funziona con Sender Policy Framework (SPF) e DKIM (DomainKeys Identified Mail) per l'autenticazione dei mittenti di posta e garantire che i sistemi di posta elettronica di destinazione considerino attendibili i messaggi inviati dal dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="94ef9-104">[Domain-based Message Authentication, Reporting, and Conformance (DMARC)](https://dmarc.org) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="94ef9-105">L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing.</span><span class="sxs-lookup"><span data-stu-id="94ef9-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="94ef9-106">DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="94ef9-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a><span data-ttu-id="94ef9-107">In che modo SPF e DMARC collaborano per proteggere la posta elettronica in Office 365?</span><span class="sxs-lookup"><span data-stu-id="94ef9-107">How do SPF and DMARC work together to protect email in Office 365?</span></span>
<span data-ttu-id="94ef9-108"><a name="SPFandDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-108"></span></span>

 <span data-ttu-id="94ef9-p102">Un messaggio di posta elettronica potrebbe contenere più originatori o mittenti, indirizzi. Questi indirizzi sono utilizzati per scopi differenti. Ad esempio, si consideri quanto segue:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p102">An email message may contain multiple originator, or sender, addresses. These addresses are used for different purposes. For example, consider these addresses:</span></span> 
  
- <span data-ttu-id="94ef9-112">**Indirizzo "Mail From" (Posta da)** Identifica il mittente e consente di specificare dove inviare notifiche di ritorno se si verificano problemi con la consegna del messaggio, ad esempio notifiche di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="94ef9-112">**"Mail From" address** Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="94ef9-113">Ciò verrà visualizzato nella parte della busta di un messaggio di posta elettronica e, generalmente, non viene visualizzato dall'applicazione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="94ef9-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="94ef9-114">Ciò a volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path.</span><span class="sxs-lookup"><span data-stu-id="94ef9-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>
    
- <span data-ttu-id="94ef9-115">**Indirizzo "From" (Da)** L'indirizzo visualizzato come indirizzo From dall'applicazione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="94ef9-115">**"From" address** The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="94ef9-116">Questo indirizzo identifica l'autore del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="94ef9-116">This address identifies the author of the email.</span></span> <span data-ttu-id="94ef9-117">Vale a dire, la cassetta postale dell'utente o del sistema responsabile della creazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="94ef9-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="94ef9-118">Questo a volte viene chiamato indirizzo 5322.From.</span><span class="sxs-lookup"><span data-stu-id="94ef9-118">This is sometimes called the 5322.From address.</span></span>
    
<span data-ttu-id="94ef9-p105">SPF Usa un record TXT DNS per fornire un elenco di indirizzi IP di invio autorizzati per un determinato dominio. Normalmente, i controlli SPF vengono eseguiti solo in base all'indirizzo 5321.MailFrom. Ciò significa che l'indirizzo 5322.From non è autenticato quando si usa SPF. Ciò consente uno scenario in cui un utente può ricevere un messaggio che supera un controllo SPF, ma presenta un indirizzo mittente 5322.From falsificato. Si consideri, ad esempio, la seguente trascrizione SMTP:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p105">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:</span></span>
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

<span data-ttu-id="94ef9-124">In questa trascrizione, gli indirizzi mittente sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="94ef9-124">In this transcript, the sender addresses are as follows:</span></span>
  
- <span data-ttu-id="94ef9-125">Indirizzo Mail from (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94ef9-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>
    
- <span data-ttu-id="94ef9-126">Indirizzo From (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="94ef9-126">From address (5322.From): security@woodgrovebank.com</span></span>
    
<span data-ttu-id="94ef9-p106">Se è stato configurato SPF, il server di ricezione esegue un controllo sull'indirizzo Mail from phish@phishing.contoso.com. Se il messaggio proviene da un'origine valida per il dominio phishing.contoso.com, allora supera il controllo SPF. Poiché il client di posta elettronica mostra solo l'indirizzo From, l'utente visualizza che il messaggio proviene da security@woodgrovebank.com. Solo con SPF, la validità di woodgrovebank.com non era mai stata autenticata.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p106">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>
  
<span data-ttu-id="94ef9-p107">Quando si utilizza DMARC, anche il server di ricezione esegue un controllo sull'indirizzo From. Nell'esempio precedente, se esiste un record TXT DMARC per woodgrovebank.com, allora il controllo sull'indirizzo From avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p107">When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>
  
## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="94ef9-133">Che cos'è un record TXT DMARC?</span><span class="sxs-lookup"><span data-stu-id="94ef9-133">What is a DMARC TXT record?</span></span>
<span data-ttu-id="94ef9-134"><a name="WhatisDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-134"></span></span>

<span data-ttu-id="94ef9-p108">Come i record DNS per SPF, il record per DMARC è un record di testo DNS che consente di prevenire spoofing e phishing. Viene pubblicato i record TXT DMARC in DNS. I record TXT DMARC consentono di convalidare l'origine dei messaggi di posta elettronica verificando l'indirizzo IP dell'autore della posta elettronica in base al proprietario del dominio del mittente. I record TXT DMARC identificano i server di posta elettronica in uscita autorizzati. I sistemi di posta elettronica di destinazione possono quindi verificare che l'origine dei messaggi ricevuti sia un server di posta elettronica in uscita autorizzato.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p108">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>
  
<span data-ttu-id="94ef9-140">Il record TXT DMARC di Microsoft è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="94ef9-140">Microsoft's DMARC TXT record looks something like this:</span></span>
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

<span data-ttu-id="94ef9-p109">Microsoft invia i suoi report DMARC a [Agari](https://agari.com), una terza parte. Agari raccoglie e analizza i report DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p109">Microsoft sends its DMARC reports to [Agari](https://agari.com), a 3rd party. Agari collects and analyzes DMARC reports.</span></span>
  
## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="94ef9-143">Implementare DMARC per la posta in ingresso</span><span class="sxs-lookup"><span data-stu-id="94ef9-143">Implement DMARC for inbound mail</span></span>
<span data-ttu-id="94ef9-144"><a name="implementDMARCinbound"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-144"></span></span>

<span data-ttu-id="94ef9-p110">Non serve fare nulla per configurare DMARC per la posta ricevuta in Office 365. Microsoft si occupa di tutto. Per sapere cosa succede alla posta che non supera i controlli DMARC, vedere [Modalità di gestione della posta elettronica in ingresso che non supera DMARC da parte di Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail).</span><span class="sxs-lookup"><span data-stu-id="94ef9-p110">You don't have to do a thing to set up DMARC for mail that you receive in Office 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span></span>
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a><span data-ttu-id="94ef9-148">Implementare DMARC per la posta in uscita da Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-148">Implement DMARC for outbound mail from Office 365</span></span>
<span data-ttu-id="94ef9-149"><a name="implementDMARCoutbound"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-149"></span></span>

<span data-ttu-id="94ef9-p111">Se si usa Office 365, ma non si utilizza un dominio personalizzato, vale a dire, si usa onmicrosoft.com, non è necessario eseguire altre operazioni per configurare o implementare DMARC per l'organizzazione. SPF è già configurato e Office 365 genera automaticamente una firma DKIM per la posta in uscita. Per ulteriori informazioni sulla firma, vedere [Comportamento predefinito per DKIM e Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="94ef9-p111">If you use Office 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Office 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
 <span data-ttu-id="94ef9-p112">Se si dispone di un dominio personalizzato o si utilizzano i server Exchange locali oltre a Office 365, è necessario implementare manualmente DMAR per la posta in uscita. L'implementazione DMARC per il dominio personalizzato include questa procedura:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p112">If you have a custom domain or you are using on-premises Exchange servers in addition to Office 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:</span></span> 
  
- [<span data-ttu-id="94ef9-155">Passaggio 1: identificare le origini valide della posta del dominio</span><span class="sxs-lookup"><span data-stu-id="94ef9-155">Step 1: Identify valid sources of mail for your domain</span></span>](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [<span data-ttu-id="94ef9-156">Passaggio 2: configurare SPF per il dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-156">Step 2: Set up SPF for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [<span data-ttu-id="94ef9-157">Passaggio 3: configurare DKIM per il dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-157">Step 3: Set up DKIM for your custom domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [<span data-ttu-id="94ef9-158">Passaggio 4: formare il record TXT DMARC del dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-158">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="94ef9-159">Passaggio 1: identificare le origini valide della posta del dominio</span><span class="sxs-lookup"><span data-stu-id="94ef9-159">Step 1: Identify valid sources of mail for your domain</span></span>
<span data-ttu-id="94ef9-160"><a name="IdentifyValidSources"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-160"></span></span>

<span data-ttu-id="94ef9-p113">Se SPF è già stato configurato, allora questo esercizio è già stato completato. Tuttavia, per DMARC, occorre fare altre considerazioni. Quando si identificano origini di posta per il dominio, occorre rispondere a due domande:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p113">If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:</span></span>
  
- <span data-ttu-id="94ef9-164">Quali indirizzi IP inviano messaggi da qualsiasi dominio?</span><span class="sxs-lookup"><span data-stu-id="94ef9-164">What IP addresses send messages from my domain?</span></span>
    
- <span data-ttu-id="94ef9-165">Per i messaggi inviati da terze parti per conto dell'utente, i domini 5321.MailFrom e 5322.From corrisponderanno?</span><span class="sxs-lookup"><span data-stu-id="94ef9-165">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a><span data-ttu-id="94ef9-166">Passaggio 2: configurare SPF per il dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-166">Step 2: Set up SPF for your domain in Office 365</span></span>
<span data-ttu-id="94ef9-167"><a name="ConfigSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-167"></span></span>

<span data-ttu-id="94ef9-168">Ora che si dispone di un elenco di mittenti validi, è possibile seguire la procedura per [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="94ef9-168">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>
  
<span data-ttu-id="94ef9-169">Ad esempio, presupponendo che contoso.com invia un messaggio da Exchange Online, un server Exchange locale il cui indirizzo IP è 192.168.0.1 e un'applicazione Web il cui indirizzo IP è 192.168.100.100, il record TXT SPFsarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="94ef9-169">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="94ef9-170">Come procedura consigliata, assicurarsi che il record TXT SPF tenga in considerazione mittenti di terze parti.</span><span class="sxs-lookup"><span data-stu-id="94ef9-170">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a><span data-ttu-id="94ef9-171">Passaggio 3: configurare DKIM per il dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-171">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="94ef9-172"><a name="ConfigDKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-172"></span></span>

<span data-ttu-id="94ef9-p114">Dopo aver configurato SPF, è necessario configurare DKIM. DKIM consente di aggiungere una firma digitale ai messaggi di posta elettronica nell'intestazione del messaggio. Se non si configura DKIM e si consente invece a Office 365 di usare la configurazione DKIM predefinita per il dominio, DMARC potrebbe non riuscire. Questo perché la configurazione DKIM predefinita utilizza il dominio onmicrosoft.com iniziale come indirizzo 5322.From, non il dominio personalizzato. Ciò forza una mancata corrispondenza tra gli indirizzi 5321.MailFrom e 5322.From in tutta la posta elettronica inviata dal dominio.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p114">Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Office 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>
  
<span data-ttu-id="94ef9-p115">Se si dispone di mittenti di terze parti che inviano posta per conto dell'utente e la posta inviata presenta indirizzi 5321.MailFrom e 5322.From non corrispondenti, DMARC non riuscirà per tale posta elettronica. Per evitare il problema, è necessario configurare DKIM per il dominio in modo specifico con tale mittente di terze parti. In questo modo Office 365 potrà autenticare la posta elettronica dal servizio di terze parti. Tuttavia, inoltre consente ad altri, ad esempio, Yahoo, Gmail e Comcast, di verificare la posta elettronica inviata a loro da terze parti come se la posta elettronica fosse stata inviata dall'utente. Ciò è utile perché consente ai clienti di creare fiducia nel dominio indipendentemente da dove si trova la loro cassetta postale e, contemporaneamente, Office 365 non contrassegnerà un messaggio come posta indesiderata a causa dello spoofing perché supera i controlli di autenticazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p115">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Office 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Office 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>
  
<span data-ttu-id="94ef9-183">Per istruzioni sulla configurazione di DKIM del dominio e su come configurare DKIM per mittenti di terze parti affinché possano effettuare lo spoofing del dominio, vedere [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="94ef9-183">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a><span data-ttu-id="94ef9-184">Passaggio 4: formare il record TXT DMARC del dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-184">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>
<span data-ttu-id="94ef9-185"><a name="CreateDMARCRecord"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-185"></span></span>

<span data-ttu-id="94ef9-p116">Anche se sono disponibili altre opzioni di sintassi non menzionate qui, queste sono le opzioni più comunemente utilizzate per Office 365. Formare il record TXT DMARC per il dominio nel formato:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p116">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Office 365. Form the DMARC TXT record for your domain in the format:</span></span>
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

<span data-ttu-id="94ef9-188">dove:</span><span class="sxs-lookup"><span data-stu-id="94ef9-188">where:</span></span>
  
- <span data-ttu-id="94ef9-189">*domain* è il dominio da proteggere.</span><span class="sxs-lookup"><span data-stu-id="94ef9-189">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="94ef9-190">Per impostazione predefinita, il record protegge la posta elettronica dal dominio e da tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="94ef9-190">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="94ef9-191">Ad esempio, se si specifica \_dmarc.contoso.com, DMARC protegge la posta del dominio e da tutti i sottodomini, ad esempio housewares.contoso.com o plumbing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94ef9-191">For example, if you specify _dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span> 
    
- <span data-ttu-id="94ef9-p118">*TTL* deve essere sempre l'equivalente di un'ora. L'unità utilizzata per TTL, ore (1 ora), minuti (60 minuti) o secondi (3600 secondi) varia a seconda del registrar del dominio.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p118">*TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span> 
    
- <span data-ttu-id="94ef9-194">*pct=100* indica che questa regola deve essere utilizzata per il 100% della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="94ef9-194">pct=100 indicates that this rule should be used for 100% of email.</span></span>
    
- <span data-ttu-id="94ef9-p119">*policy* specifica quale criterio deve eseguire il server di ricezione se DMARC ha esito negativo. È possibile impostare il criterio su none, quarantine o reject.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p119">*policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.</span></span> 
    
<span data-ttu-id="94ef9-197">Per informazioni sulle opzioni da usare, acquisire familiarità con i concetti illustrati in [Procedure consigliate per l'implementazione di DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span><span class="sxs-lookup"><span data-stu-id="94ef9-197">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span></span>
  
<span data-ttu-id="94ef9-198">Esempi:</span><span class="sxs-lookup"><span data-stu-id="94ef9-198">Examples:</span></span>
  
- <span data-ttu-id="94ef9-199">Criterio impostato su none</span><span class="sxs-lookup"><span data-stu-id="94ef9-199">Policy set to none</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="94ef9-200">Criterio impostato su quarantine</span><span class="sxs-lookup"><span data-stu-id="94ef9-200">Policy set to quarantine</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="94ef9-201">Criterio impostato su reject</span><span class="sxs-lookup"><span data-stu-id="94ef9-201">Policy set to reject</span></span>
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="94ef9-p120">Dopo aver creato il record, è necessario aggiornare il record nel registrar del dominio. Per istruzioni sull'aggiunta del record TXT DMARC ai record DNS di Office 365, vedere [Creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span><span class="sxs-lookup"><span data-stu-id="94ef9-p120">Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Office 365, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a><span data-ttu-id="94ef9-204">Procedure consigliate per l'implementazione di DMARC in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-204">Best practices for implementing DMARC in Office 365</span></span>
<span data-ttu-id="94ef9-205"><a name="DMARCbestpractices"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-205"></span></span>

<span data-ttu-id="94ef9-p121">È possibile implementare DMARC gradualmente senza influire sul resto del flusso di posta. Creare e implementare un piano di implementazione che segue questi passaggi. Eseguire ognuna di queste operazioni prima con un sottodominio, poi con gli altri sottodomini e infine con il dominio di primo livello nell'organizzazione prima di passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p121">You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>
  
1. <span data-ttu-id="94ef9-209">Monitorare l'effetto dell'implementazione DMARC</span><span class="sxs-lookup"><span data-stu-id="94ef9-209">Monitor the impact of implementing DMARC</span></span>
    
    <span data-ttu-id="94ef9-p122">Iniziare con un semplice record in modalità monitoraggio per un sottodominio o dominio che richiede che i destinatari DMARC inviino statistiche sui messaggi visualizzati utilizzando tale dominio. Un record in modalità monitoraggio è un record TXT DMARC con i criteri impostati su none (p=none). Molte aziende pubblicano un record TXT DMARC con p=nessuno perché non sono sicuri su quanta posta elettronica potrebbero perdere pubblicando un criterio DMARC più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p122">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span> 
    
    <span data-ttu-id="94ef9-p123">È possibile farlo anche prima di aver implementato SPF o DKIM nell'infrastruttura di messaggistica. Tuttavia, non sarà possibile mettere in quarantena o rifiutare in modo efficace la posta tramite DMARCA finché non verranno implementati anche SPF e DKIM. Introducendo SPF e DKIM, i report generati tramite DMARC forniranno i numeri e le origini dei messaggi che superano i controlli e quelli che non li superano. È possibile individuare facilmente la quantità di traffico legittimo coperto o non coperto da questi e risolvere eventuali problemi. Si inizierà anche visualizzare il numero di messaggi fraudolenti inviati e da dove.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p123">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>
    
2. <span data-ttu-id="94ef9-218">Richiedere che i sistemi di posta esterni mettano in quarantena la posta che non supera DMARC</span><span class="sxs-lookup"><span data-stu-id="94ef9-218">Request that external mail systems quarantine mail that fails DMARC</span></span>
    
    <span data-ttu-id="94ef9-p124">Quando si pensa che tutto o la maggior parte del traffico legittimo sia protetto da SPF e DKIM e si comprende l'impatto dell'implementazione DMARC, è possibile implementare un criterio di quarantena. Un criterio di quarantena è un record TXT DMARC il cui criterio è impostato su quarantine (p=quarantine). In questo modo viene, si chiede ai destinatari DMARC di mettere i messaggi dal dominio che non superano DMARC nell'equivalente locale di una cartella di posta indesiderata invece che nella Posta in arrivo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p124">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>
    
3. <span data-ttu-id="94ef9-222">Richiedere che i sistemi di posta esterni non accettino messaggi che non superano DMARC</span><span class="sxs-lookup"><span data-stu-id="94ef9-222">Request that external mail systems not accept messages that fail DMARC</span></span>
    
    <span data-ttu-id="94ef9-p125">Il passaggio finale consiste nell'implementare un criterio reject. Un criterio reject è un record TXT DMARC il cui criterio è impostato su reject (p=reject). Quando si esegue questa operazione, si chiede ai destinatari DMARC di non accettare messaggi che non superano i controlli DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p125">The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span> 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="94ef9-226">Modalità di gestione della posta elettronica in uscita che non supera DMARC da parte di Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-226">How Office 365 handles outbound email that fails DMARC</span></span>
<span data-ttu-id="94ef9-227"><a name="outbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-227"></span></span>

<span data-ttu-id="94ef9-228">Se un messaggio è in uscita da Office 365 e non supera DMARC e il criterio è stato impostato su p=quarantine o p=reject, il messaggio viene instradato attraverso il [Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94ef9-228">If a message is outbound from Office 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [Higher Risk Delivery Pool for Outbound Messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="94ef9-229">Non viene eseguito override della posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="94ef9-229">There is no override for outbound email.</span></span>
  
<span data-ttu-id="94ef9-p127">Se si pubblica un criterio reject DMARC (p=reject), nessun altro cliente in Office 365 può eseguire lo spoofing del dominio perché i messaggi non potranno superare SPF o DKIM per il dominio quando si affidano a un messaggio in uscita attraverso il servizio. Tuttavia, se si pubblica un criterio reject di DMAR, ma non tutta la posta elettronica viene autenticata attraverso Office 365, una parte di questa potrebbe essere contrassegnata come posta indesiderata per la posta elettronica in ingresso (come descritto sopra) oppure sarà rifiutata se non si pubblica SPF e si prova ad inoltrarla in uscita attraverso il servizio. Ciò accade, ad esempio, se si dimentica di includere alcuni degli indirizzi IP per server e app che inviano posta per conto del dominio quando si crea il record TXT DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p127">If you publish a DMARC reject policy (p=reject), no other customer in Office 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Office 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="94ef9-233">Modalità di gestione della posta elettronica in ingresso che non supera DMARC da parte di Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-233">How Office 365 handles inbound email that fails DMARC</span></span>
<span data-ttu-id="94ef9-234"><a name="inbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-234"></span></span>

<span data-ttu-id="94ef9-p128">Se il criterio DMARC del server di invio è p=reject, EOP contrassegna il messaggio come posta indesiderata invece di rifiutarlo. In altre parole, per la posta elettronica in ingresso, Office 365 considera p=reject e p=quarantine allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p128">If the DMARC policy of the sending server is p=reject, EOP marks the message as spam instead of rejecting it. In other words, for inbound email, Office 365 treats p=reject and p=quarantine the same way.</span></span>
  
<span data-ttu-id="94ef9-p129">Office 365 è configurato in questo modo perché una parte di posta elettronica legittima potrebbe non superare DMARC. Ad esempio, un messaggio potrebbe non superare DMARC se viene inviato a una lista di distribuzione che poi inoltre il messaggio a tutti i partecipanti della lista. Se Office 365 ha rifiutato questi messaggi, le persone potrebbero perdere posta elettronica legittima e non ci sarà modo di recuperarla. Al contrario, questi messaggi continueranno a non superare DMARC ma verranno contrassegnati come posta indesiderata e non rifiutati. Se si desidera, gli utenti possono comunque ricevere questi messaggi nella propria posta in arrivo attraverso i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p129">Office 365 is configured like this because some legitimate email may fail DMARC. For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants. If Office 365 rejected these messages, people could lose legitimate email and have no way to retrieve it. Instead, these messages will still fail DMARC but they will be marked as spam and not rejected. If desired, users can still get these messages in their inbox through these methods:</span></span>
  
- <span data-ttu-id="94ef9-242">Gli utenti aggiungono mittenti sicuri singolarmente mediante il loro client di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="94ef9-242">Users add safe senders individually by using their email client</span></span>
    
- <span data-ttu-id="94ef9-243">Gli amministratori creano una regola di flusso di posta di Exchange, nota anche come regola di trasporto, per tutti gli utenti che consentono messaggi di questi mittenti specifici.</span><span class="sxs-lookup"><span data-stu-id="94ef9-243">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span> 
    
## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="94ef9-244">Risoluzione dei problemi relativi all'implementazione di DMARC</span><span class="sxs-lookup"><span data-stu-id="94ef9-244">Troubleshooting your DMARC implementation</span></span>
<span data-ttu-id="94ef9-245"><a name="dmarctroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-245"></span></span>

<span data-ttu-id="94ef9-246">Se sono stati configurati i record MX del dominio in cui EOP non è la prima voce, gli errori DMARC non verranno applicati nel dominio.</span><span class="sxs-lookup"><span data-stu-id="94ef9-246">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span> 
  
<span data-ttu-id="94ef9-p130">Se si è clienti di Office 365 e il proprio record MX principale del dominio non si riferisce a Exchange Online Protection, non si trarranno vantaggi da DMARC. Ad esempio, DMARC non funzionerà se si punta il record MX al server di posta locale e si indirizza quindi la posta elettronica a EOP utilizzando un connettore. In questo scenario, il dominio di destinazione è uno dei domini accettati ma EOP non è il principale MX. Ad esempio, si supponga che contoso.com punti il relativo MX a se stesso e utilizzi EOP come un record MX secondario, il record MX di contoso.com avrà il seguente aspetto:</span><span class="sxs-lookup"><span data-stu-id="94ef9-p130">If you're an Office 365 customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC. For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector. In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX. For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="94ef9-251">Tutta la posta elettronica, o gran parte, verrà prima indirizzata a mail.contoso.com poiché è l'MX principale e poi la posta verrà instradata a EOP.</span><span class="sxs-lookup"><span data-stu-id="94ef9-251">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="94ef9-252">In alcuni casi, potrebbe non essere neanche necessario EOP come record MX, ma potrebbe essere semplicemente sufficiente collegare connettori per instradare la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="94ef9-252">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="94ef9-253">EOP non deve necessariamente essere la prima voce per la convalida di DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-253">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="94ef9-254">Garantisce solo la convalida, perché non è possibile essere certi che tutti i server locali o non Office 365 eseguano controlli di DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-254">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="94ef9-255">DMARC è idoneo per essere applicato al dominio di un cliente (non al server) durante la configurazione del record TXT DMARC, ma l'applicazione dipende dal server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="94ef9-255">DMARC is eligible to be enforced for a customer’s domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="94ef9-256">Se si configura EOP come server di ricezione, EOP esegue l'applicazione di DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-256">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="94ef9-257">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="94ef9-257">For more information</span></span>
<span data-ttu-id="94ef9-258"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-258"></span></span>

<span data-ttu-id="94ef9-p132">Per ulteriori informazioni su DMARC le risorse che seguono possono essere di aiuto.</span><span class="sxs-lookup"><span data-stu-id="94ef9-p132">Want more information about DMARC? These resources can help.</span></span>
  
- <span data-ttu-id="94ef9-261">[Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include i campi di intestazione e di sintassi usati da Office 365 per i controlli DMARC.</span><span class="sxs-lookup"><span data-stu-id="94ef9-261">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
    
- <span data-ttu-id="94ef9-262">Seguire la [serie di formazione su DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) da M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span><span class="sxs-lookup"><span data-stu-id="94ef9-262">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>
    
- <span data-ttu-id="94ef9-263">Utilizzare l'elenco di controllo in [dmarcian](https://space.dmarcian.com/deployment/).</span><span class="sxs-lookup"><span data-stu-id="94ef9-263">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>
    
- <span data-ttu-id="94ef9-264">Passare direttamente all'origine in [DMARC.org](https://dmarc.org).</span><span class="sxs-lookup"><span data-stu-id="94ef9-264">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="94ef9-265">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ef9-265">See also</span></span>
<span data-ttu-id="94ef9-266"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="94ef9-266"></span></span>

[<span data-ttu-id="94ef9-267">Utilizzo di Sender Policy Framework (SPF) in Office 365 per impedire lo spoofing</span><span class="sxs-lookup"><span data-stu-id="94ef9-267">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[<span data-ttu-id="94ef9-268">Configurazione di SPF in Office 365 per evitare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="94ef9-268">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[<span data-ttu-id="94ef9-269">Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="94ef9-269">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

