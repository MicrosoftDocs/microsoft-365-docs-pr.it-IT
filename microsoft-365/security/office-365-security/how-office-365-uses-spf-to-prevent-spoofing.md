---
title: Utilizzo di Sender Policy Framework (SPF) in Office 365 per impedire lo spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: "Sintesi: In questo articolo viene descritto come Office 365 utilizza il record TXT Sender Policy Framework (SPF) in DNS per verificare che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato. Si applica alla posta in uscita inviata da Office 365. I messaggi inviati da Office 365 a un destinatario all'interno di Office 365 passano sempre SPF."
ms.openlocfilehash: e2863c0b8a66fa511c4ce842dc8026e880594292
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086001"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="b0182-105">Utilizzo di Sender Policy Framework (SPF) in Office 365 per impedire lo spoofing</span><span class="sxs-lookup"><span data-stu-id="b0182-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="b0182-p102">**Sintesi:** In questo articolo viene descritto come Office 365 utilizza il record TXT Sender Policy Framework (SPF) in DNS per verificare che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato. Si applica alla posta in uscita inviata da Office 365. I messaggi inviati da Office 365 a un destinatario all'interno di Office 365 passano sempre SPF.</span><span class="sxs-lookup"><span data-stu-id="b0182-p102">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain. This applies to outbound mail sent from Office 365. Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span>

<span data-ttu-id="b0182-p103">Un record TXT SPF è un record DNS che consente di impedire lo spoofing e il phishing verificando il nome del dominio da cui vengono inviati i messaggi di posta elettronica. SPF consente di convalidare l'origine dei messaggi di posta elettronica verificando l'indirizzo IP del mittente in base al proprietario del dominio del mittente.</span><span class="sxs-lookup"><span data-stu-id="b0182-p103">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b0182-p104">I tipi di record SPF sono stati deprecati dall'Internet Engineering Task Force (IETF) nel 2014. Assicurarsi quindi di utilizzare i record TXT in DNS per pubblicare le informazioni SPF. Il resto di questo articolo utilizza il termine record TXT SPF per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="b0182-p104">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="b0182-114">Gli amministratori di dominio pubblicano le informazioni SPF in record TXT in DNS.</span><span class="sxs-lookup"><span data-stu-id="b0182-114">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="b0182-115">Le informazioni SPF identificano i server di posta elettronica in uscita autorizzati.</span><span class="sxs-lookup"><span data-stu-id="b0182-115">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="b0182-116">I sistemi di posta elettronica di destinazione verificano che l'origine dei messaggi sia un server di posta elettronica in uscita autorizzato.</span><span class="sxs-lookup"><span data-stu-id="b0182-116">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="b0182-117">Se si ha già familiarità con SPF o si dispone di una distribuzione semplice e si vuole solo sapere cosa includere nel record TXT SPF in DNS per Office 365, è possibile passare a [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="b0182-117">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="b0182-118">Se non si dispone di una distribuzione completamente ospitata in Office 365 o si necessita di ulteriori informazioni sul funzionamento o sulla risoluzione dei problemi di SPF per Office 365, continuare la lettura di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b0182-118">If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="b0182-119">In precedenza, era necessario aggiungere un record SPF o TXT diverso al dominio personalizzato se si utilizzava anche SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b0182-119">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="b0182-120">Ciò non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="b0182-120">This is no longer required.</span></span> <span data-ttu-id="b0182-121">Questa modifica dovrebbe ridurre il rischio che i messaggi di notifica di SharePoint Online finiscano nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b0182-121">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="b0182-122">Non è necessario apportare modifiche immediatamente, ma se si riceve l'errore relativo al "numero eccessivo di ricerche", modificare il record TXT SPF come descritto in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="b0182-122">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="b0182-123">Funzionamento di SPF per prevenire spoofing e phishing in Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="b0182-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-124"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="b0182-p107">SPF determina se un mittente è autorizzato a inviare per conto di un dominio. Se il mittente non è autorizzato a farlo, ovvero se la posta elettronica non supera il controllo SPF nel server di ricezione, i criteri contro la posta indesiderata configurati su tale server determinano cosa fare con il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b0182-p107">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="b0182-p108">Ogni record TXT SPF è costituito da tre parti: la dichiarazione che si tratta di un record TXT SPF, gli indirizzi IP autorizzati all'invio della posta dal dominio e i domini esterni in grado di inviare per conto del dominio, e una regola di imposizione. È necessario disporre di tutti e tre gli elementi per avere un record TXT SPF valido. In questo articolo viene descritto come creare il record TXT SPF e vengono illustrate le procedure consigliate per l'utilizzo dei servizi in Office 365. Vengono inoltre forniti i collegamenti alle istruzioni sull'uso del registrar per pubblicare il record in DNS.</span><span class="sxs-lookup"><span data-stu-id="b0182-p108">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule. You need all three in a valid SPF TXT record. This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365. Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="b0182-131">Nozioni principali su SFP: Indirizzi IP autorizzati all'invio dal dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="b0182-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="b0182-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-132"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="b0182-133">Ecco la sintassi di base di una regola SPF:</span><span class="sxs-lookup"><span data-stu-id="b0182-133">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="b0182-134">v=spf1 \<IP\> \<regola di imposizione\></span><span class="sxs-lookup"><span data-stu-id="b0182-134">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="b0182-135">Si supponga, ad esempio, che sia presente la seguente regola SPF per contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b0182-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="b0182-136">v=spf1 \<indirizzo IP #1\> \<indirizzo IP #2\> \<indirizzo IP #3\> \<regola di imposizione\></span><span class="sxs-lookup"><span data-stu-id="b0182-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="b0182-137">In questo esempio la regola SPF indica al server di posta elettronica ricevente di accettare solo messaggi provenienti da questi indirizzi IP per il dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b0182-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="b0182-138">Indirizzo IP #1</span><span class="sxs-lookup"><span data-stu-id="b0182-138">IP address #1</span></span>

- <span data-ttu-id="b0182-139">Indirizzo IP #2</span><span class="sxs-lookup"><span data-stu-id="b0182-139">IP address #2</span></span>

- <span data-ttu-id="b0182-140">Indirizzo IP #3</span><span class="sxs-lookup"><span data-stu-id="b0182-140">IP address #3</span></span>

<span data-ttu-id="b0182-p109">Questa regola SPF indica al server di posta elettronica ricevente che se un messaggio proviene da contoso.com, ma non da uno di questi tre indirizzi IP, il server di ricezione deve applicare la regola di imposizione al messaggio. La regola di imposizione è in genere una di queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="b0182-p109">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="b0182-p110">**Errore bloccante.** Contrassegnare il messaggio con "Errore bloccante" nella busta del messaggio e quindi seguire il criterio contro la posta indesiderata configurato del server di ricezione per questo tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b0182-p110">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="b0182-p111">**Errore non bloccante.** Contrassegnare il messaggio con "Errore non bloccante" nella busta del messaggio. In genere, i server di posta elettronica sono configurati per recapitare questi messaggi comunque. La maggior parte degli utenti finali non visualizza questo contrassegno.</span><span class="sxs-lookup"><span data-stu-id="b0182-p111">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="b0182-p112">**Neutro.** Non eseguire nessuna operazione, ovvero non contrassegnare la busta del messaggio. In genere è il criterio riservato a motivi di test ed è utilizzato raramente.</span><span class="sxs-lookup"><span data-stu-id="b0182-p112">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="b0182-p113">Negli esempi seguenti viene illustrato il funzionamento di SPF in diverse situazioni. In questi esempi, contoso.com è il mittente e woodgrovebank.com è il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b0182-p113">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="b0182-154">Esempio 1: Autenticazione di un messaggio di posta elettronica inviato direttamente dal mittente al destinatario</span><span class="sxs-lookup"><span data-stu-id="b0182-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="b0182-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-155"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="b0182-156">SPF è ideale quando il percorso dal mittente al destinatario è diretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0182-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![Diagramma che mostra in che modo SPF autentica la posta elettronica inviata direttamente da un server all'altro.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="b0182-158">Quando woodgrovebank.com riceve il messaggio, se l'indirizzo IP #1 è nel record TXT SPF per contoso.com, il messaggio passa il controllo SPF e viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="b0182-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="b0182-159">Esempio 2: Indirizzo del mittente falsificato non supera il controllo SPF</span><span class="sxs-lookup"><span data-stu-id="b0182-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="b0182-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-160"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="b0182-161">Si supponga che un truffatore trovi un modo per effettuare lo spoofing di contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b0182-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![Diagramma che mostra in che modo SPF autentica la posta elettronica inviata da un server falsificato.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="b0182-163">Poiché l'indirizzo IP #12 non è nel record TXT SPF di contoso.com, il messaggio non supera il controllo SPF e il destinatario può scegliere di contrassegnarlo come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b0182-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="b0182-164">Esempio 3: SPF e messaggi inoltrati</span><span class="sxs-lookup"><span data-stu-id="b0182-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="b0182-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-165"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="b0182-p114">Uno svantaggio di SPF consiste nel fatto che non funziona quando un messaggio di posta elettronica è stato inoltrato. Ad esempio, si supponga che l'utente in woodgrovebank.com abbia configurato una regola di inoltro per inviare tutta la posta elettronica a un account di outlook.com:</span><span class="sxs-lookup"><span data-stu-id="b0182-p114">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![Diagramma che mostra come SPF non sia in grado di autenticare la posta elettronica che viene inoltrata.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="b0182-p115">Il messaggio all'inizio supera il controllo SPF in woodgrovebank.com, ma poi non passa quello in outlook.com perché l'IP #25 non è nel record TXT SPF di contoso.com. Outlook.com potrebbe quindi contrassegnare il messaggio come posta indesiderata. Per risolvere il problema, utilizzare SPF insieme ad altri metodi di autenticazione di posta elettronica quali DKIM e DMARC.</span><span class="sxs-lookup"><span data-stu-id="b0182-p115">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="b0182-172">Nozioni principali su SFP: Inclusione di domini di terze parti in grado di inviare posta elettronica per conto del proprio dominio</span><span class="sxs-lookup"><span data-stu-id="b0182-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="b0182-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-173"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="b0182-p116">Oltre agli indirizzi IP, è possibile configurare il record TXT SPF anche in modo che includa domini come mittenti. Questi vengono aggiunti al record TXT SPF come istruzioni "#include". Ad esempio, contoso.com potrebbe includere tutti gli indirizzi IP dei server di posta da contoso.net e contoso.org, anch'essi di sua proprietà. A tale scopo, contoso.com pubblica un record TXT SPF simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b0182-p116">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="b0182-178">Quando il server ricevente Visualizza questo record in DNS, esegue anche una ricerca DNS nel record TXT SPF per contoso.net e quindi per contoso.org. Se viene trovata un'istruzione include aggiuntiva all'interno dei record per contoso.net o contoso.org, verranno seguiti anche quelli.</span><span class="sxs-lookup"><span data-stu-id="b0182-178">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="b0182-179">Per evitare attacchi Denial of Service, il numero massimo di ricerche DNS per un singolo messaggio di posta elettronica è 10.</span><span class="sxs-lookup"><span data-stu-id="b0182-179">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="b0182-180">Ogni istruzione #include rappresenta una ricerca DNS aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b0182-180">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="b0182-181">Se un messaggio supera il limite di 10, il messaggio non supera il controllo SPF.</span><span class="sxs-lookup"><span data-stu-id="b0182-181">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="b0182-182">Una volta che un messaggio raggiunge questo limite, a seconda del modo in cui il server di ricezione è configurato, il mittente potrebbe ottenere un messaggio che indica che il messaggio ha generato "troppe ricerche" o che il numero massimo di hop per il messaggio è stato superato (operazione che può verificarsi quando il le ricerche interessano il ciclo e superano il timeout DNS.</span><span class="sxs-lookup"><span data-stu-id="b0182-182">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="b0182-183">Per suggerimenti su come evitarlo, vedere [Risoluzione dei problemi: procedure consigliate per SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="b0182-183">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="b0182-184">Requisiti per il record TXT SPF e Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="b0182-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-185"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="b0182-p118">Se si configura la posta elettronica quando si configura Office 365, è già stato creato un record TXT SPF che identifica i server di messaggistica Microsoft come origine legittima di posta per il dominio dell'utente. Questo record probabilmente sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b0182-p118">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain. This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="b0182-188">Se il cliente è completamente ospitato su Office 365, ovvero non dispone di server di posta in locale per l'invio della posta in uscita, questo è l'unico record TXT SPF necessario per pubblicare per Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0182-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="b0182-189">Nel caso di distribuzione ibrida (ovvero nel caso di cassette postali in locale e alcune ospitate in Office 365) oppure se l'utente è un cliente di Exchange Online Protection (EOP) autonomo (ovvero l'organizzazione utilizza EOP per proteggere le cassette postali in locale), è necessario aggiungere l'indirizzo IP di uscita per ogni server di posta perimetrale in locale al record TXT SPF in DNS.</span><span class="sxs-lookup"><span data-stu-id="b0182-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="b0182-190">Creazione del record TXT SPF per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="b0182-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-191"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="b0182-p119">Utilizzare le informazioni relative alla sintassi fornite in questo articolo per formare il record TXT SPF per il dominio personalizzato. Anche se sono disponibili altre opzioni di sintassi non menzionate qui, queste sono le opzioni più comunemente utilizzate. Dopo aver creato il record, è necessario aggiornare il record nel registrar del dominio.</span><span class="sxs-lookup"><span data-stu-id="b0182-p119">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="b0182-195">Per informazioni sui domini che sarà necessario includere per Office 365, vedere [Record DNS esterni per SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="b0182-195">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="b0182-196">Utilizzare le [istruzioni dettagliate ](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) per aggiornare i record (TXT) SPF per il registrar.</span><span class="sxs-lookup"><span data-stu-id="b0182-196">Use the [step-by-step instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="b0182-197">Sintassi del record TXT SPF per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-197">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="b0182-198"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-198"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="b0182-199">Un tipico record TXT SPF per Office 365 presenta la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b0182-199">A typical SPF TXT record for Office 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="b0182-200">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0182-200">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="b0182-201">dove:</span><span class="sxs-lookup"><span data-stu-id="b0182-201">where:</span></span>

- <span data-ttu-id="b0182-p121">**v=spf1** è obbligatorio. Ciò definisce il record TXT come record TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="b0182-p121">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="b0182-p122">**ip4** indica che si utilizzano indirizzi IP in versione 4. **ip6** indica che si utilizzano indirizzi IP in versione 6. Se sono in uso indirizzi IP IPv6, sostituire **ip4** con **ip6** negli esempi forniti in questo articolo. È inoltre possibile specificare intervalli di indirizzi IP utilizzando la notazione CIDR, ad esempio **ip4:192.168.0.1/26**.</span><span class="sxs-lookup"><span data-stu-id="b0182-p122">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="b0182-p123">_IP address_ è l'indirizzo IP da aggiungere al record TXT SPF. In genere, questo è l'indirizzo IP del server di posta in uscita per l'organizzazione. È possibile elencare più server di posta in uscita. Per ulteriori informazioni, vedere [Esempio: record TXT SPF per più server di posta in uscita locali e Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span><span class="sxs-lookup"><span data-stu-id="b0182-p123">_IP address_ is the IP address that you want to add to the SPF TXT record. Usually, this is the IP address of the outbound mail server for your organization. You can list multiple outbound mail servers. For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="b0182-p124">_domain name_ è il dominio da aggiungere come mittente legittimo. Per un elenco di nomi di dominio che sarà necessario includere per Office 365, vedere [Record DNS esterni per SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="b0182-p124">_domain name_ is the domain you want to add as a legitimate sender. For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span>

- <span data-ttu-id="b0182-214">La regola di imposizione in genere è una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0182-214">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="b0182-215">-all</span><span class="sxs-lookup"><span data-stu-id="b0182-215">-all</span></span>

    <span data-ttu-id="b0182-p125">Indica un errore bloccante. Se si conoscono tutti gli indirizzi IP autorizzati per il dominio, elencarli nel record TXT SPF e utilizzare il qualificatore -all (errore bloccante). Inoltre, se si usa solo SPF, ovvero se non si utilizza DMARC o DKIM, è necessario usare il qualificatore -all. È consigliabile usare sempre questo qualificatore.</span><span class="sxs-lookup"><span data-stu-id="b0182-p125">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="b0182-220">~all</span><span class="sxs-lookup"><span data-stu-id="b0182-220">~all</span></span>

    <span data-ttu-id="b0182-p126">Indica un errore non bloccante. Se non si è certi di avere l'elenco completo degli indirizzi IP, utilizzare il qualificatore ~all (errore non bloccante). Inoltre, se si utilizza DMARC con p=quarantine o p=reject, è possibile usare ~all. In caso contrario, utilizzare -all.</span><span class="sxs-lookup"><span data-stu-id="b0182-p126">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>

  - <span data-ttu-id="b0182-225">?all</span><span class="sxs-lookup"><span data-stu-id="b0182-225">?all</span></span>

    <span data-ttu-id="b0182-p127">Indica un elemento neutro. Si usa durante il test di SPF. Non è consigliabile usare questo qualificatore nella distribuzione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b0182-p127">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="b0182-229">Esempio: Record TXT SPF da utilizzare quando tutta la posta elettronica è inviata da Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-229">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="b0182-230"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-230"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="b0182-231">Quando tutti i messaggi di posta elettronica vengono inviati da Office 365, usare questa opzione nel record TXT SPF:</span><span class="sxs-lookup"><span data-stu-id="b0182-231">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="b0182-232">Esempio: Record TXT SPF per uno scenario ibrido con un server Exchange locale e Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-232">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="b0182-233"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-233"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="b0182-234">In un ambiente ibrido, se l'indirizzo IP del server Exchange locale è 192.168.0.1, per impostare la regola di imposizione SPF sull'errore bloccante, formare il record TXT SPF come segue:</span><span class="sxs-lookup"><span data-stu-id="b0182-234">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="b0182-235">Esempio: record TXT SPF per più server di posta in uscita locali e Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-235">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="b0182-236"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-236"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="b0182-p128">Se l'utente ha più server di posta in uscita, includere l'indirizzo IP per ciascun server di posta nel record TXT SPF e separare ogni indirizzo IP con uno spazio seguito da "ip4:". Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0182-p128">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="b0182-239">Passaggi successivi: configurare SPF per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-239">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="b0182-240"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-240"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="b0182-241">Una volta formulato il record TXT SPF, seguire la procedura in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) per aggiungerlo al dominio.</span><span class="sxs-lookup"><span data-stu-id="b0182-241">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="b0182-p129">SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste tecniche, dopo aver configurato SPF, è necessario configurare anche DKIM e DMARC per Office 365. Per iniziare, vedere [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="b0182-p129">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="b0182-246">Risoluzione dei problemi: procedure consigliate per SPF in Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-246">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="b0182-247"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-247"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="b0182-p130">È possibile creare un solo record TXT SPF per il dominio personalizzato. La creazione di più record causa un round robin e SPF ha esito negativo. Per evitare questo problema, è possibile creare record distinti per ogni sottodominio. Ad esempio, creare un record per contoso.com e un altro per bulkmail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b0182-p130">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="b0182-p131">Se un messaggio di posta elettronica causa più di 10 ricerche DNS prima di essere recapitato, il server di posta di ricezione risponderà con un errore permanente, noto anche come  _permerror_, e il messaggio non supererà il controllo SPF. Il server di ricezione può rispondere anche con un rapporto di mancato recapito (NDR) che contiene un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b0182-p131">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="b0182-254">Il messaggio ha superato il numero massimo di hop.</span><span class="sxs-lookup"><span data-stu-id="b0182-254">The message exceeded the hop count.</span></span>

- <span data-ttu-id="b0182-255">Il messaggio ha richiesto un numero eccessivo di ricerche.</span><span class="sxs-lookup"><span data-stu-id="b0182-255">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="b0182-256">Evitare l'errore relativo a un "numero eccessivo di ricerche" quando sono in uso domini di terze parti con Office 365</span><span class="sxs-lookup"><span data-stu-id="b0182-256">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="b0182-257"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-257"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="b0182-p132">Alcuni record TXT SPF per i domini di terze parti passano direttamente al server di ricezione per eseguire un numero elevato di ricerche DNS. Ad esempio, al momento, Salesforce.com contiene 5 istruzioni #include nel relativo record:</span><span class="sxs-lookup"><span data-stu-id="b0182-p132">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="b0182-p133">Per evitare l'errore, è possibile implementare un criterio in cui chiunque invia posta elettronica in blocco, ad esempio, deve utilizzare un sottodominio specifico per questo scopo. È quindi possibile definire un record TXT SPF diverso per il sottodominio che include la posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="b0182-p133">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="b0182-p134">In alcuni casi, come nell'esempio di salesforce.com, è necessario utilizzare il dominio nel record TXT SPF, ma altre volte la terza parte deve avere già creato un sottodominio da utilizzare per questo scopo. Ad esempio, exacttarget.com ha creato un sottodominio che è necessario usare per il record TXT SPF:</span><span class="sxs-lookup"><span data-stu-id="b0182-p134">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="b0182-264">Quando si includono domini di terze parti nel record TXT SPF, è necessario confermare con la terza parte quale dominio o sottodominio usare per evitare di superare il limite di 10 ricerche.</span><span class="sxs-lookup"><span data-stu-id="b0182-264">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="b0182-265">Come visualizzare il record TXT SPF corrente e determinare il numero di ricerche necessarie</span><span class="sxs-lookup"><span data-stu-id="b0182-265">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="b0182-266"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-266"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="b0182-p135">È possibile utilizzare nslookup per visualizzare i record DNS, incluso il record TXT SPF. In alternativa, sono disponibili numerosi strumenti online gratuiti che consentono di visualizzare i contenuti del record TXT SPF. Osservando il record TXT SPF e seguendo la catena di istruzioni #include e reindirizzamenti, è possibile determinare il numero di ricerche DNS necessarie per il record. Alcuni strumenti online consentono anche di contare e visualizzare tali ricerche. Tenere traccia di questo numero consente di evitare che i messaggi inviati dall'organizzazione attivino un errore permanente, denominato permerror, dal server di ricezione.</span><span class="sxs-lookup"><span data-stu-id="b0182-p135">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b0182-272">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b0182-272">For more information</span></span>
<span data-ttu-id="b0182-273"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="b0182-273"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="b0182-274">Sono necessarie informazioni sull'aggiunta del record TXT SPF?</span><span class="sxs-lookup"><span data-stu-id="b0182-274">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="b0182-275">Leggere l'articolo [creare record DNS in qualsiasi provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) per informazioni dettagliate sull'utilizzo di Sender Policy Framework con il dominio personalizzato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0182-275">Read the article [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Office 365.</span></span> <span data-ttu-id="b0182-276">[Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include i campi per intestazione e sintassi utilizzati da Office 365 per i controlli SPF.</span><span class="sxs-lookup"><span data-stu-id="b0182-276">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span>


