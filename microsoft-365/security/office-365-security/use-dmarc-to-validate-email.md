---
title: Usare DMARC per convalidare la posta elettronica
f1.keywords:
- NOCSH
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
description: Informazioni su come configurare DMARC (Domain-based Message Authentication, Reporting, and Conformance) per convalidare i messaggi inviati dall'organizzazione.
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016322"
---
# <a name="use-dmarc-to-validate-email"></a>Usare DMARC per convalidare la posta elettronica

Autenticazione dei messaggi, la creazione di report e la conformità di un dominio ([DMARC](https://dmarc.org)) funziona con Sender Policy Framework (SPF) e DKIM (DomainKeys Identified Mail) per l'autenticazione dei mittenti di posta e garantire che i sistemi di posta elettronica di destinazione considerino attendibili i messaggi inviati dal dominio dell'utente. L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM.

> [!TIP]
> Vedere il catalogo [Microsoft Intelligent Security Association](https://www.microsoft.com/misapartnercatalog) per individuare i fornitori di terze parti che offrono la creazione di report DMARC per Microsoft 365.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>In che modo SPF e DMARC collaborano per proteggere la posta elettronica in Microsoft 365?

 Un messaggio di posta elettronica potrebbe contenere più originatori o mittenti, indirizzi. Questi indirizzi sono utilizzati per scopi differenti. Ad esempio, si consideri quanto segue:

- **Indirizzo "Mail From" (Posta da)** Identifica il mittente e consente di specificare dove inviare notifiche di ritorno se si verificano problemi con la consegna del messaggio, ad esempio notifiche di mancato recapito. Ciò verrà visualizzato nella parte della busta di un messaggio di posta elettronica e, generalmente, non viene visualizzato dall'applicazione di posta elettronica. Ciò a volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path.

- **Indirizzo "From" (Da)** L'indirizzo visualizzato come indirizzo From dall'applicazione di posta elettronica. Questo indirizzo identifica l'autore del messaggio di posta elettronica. Vale a dire, la cassetta postale dell'utente o del sistema responsabile della creazione del messaggio. Questo a volte viene chiamato indirizzo 5322.From.

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
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
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

In questa trascrizione, gli indirizzi mittente sono i seguenti:

- Indirizzo Mail from (5321.MailFrom): phish@phishing.contoso.com

- Indirizzo From (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>Che cos'è un record TXT DMARC?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Il record TXT DMARC di Microsoft è simile al seguente:

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft invia i propri report DMARC a una terza parte:[Agari](https://agari.com). Agari raccoglie e analizza i report DMARC. Vedere il catalogo [Microsoft Intelligent Security Association](https://www.microsoft.com/misapartnercatalog) per individuare altri fornitori di terze parti che offrono la creazione di report DMARC per Microsoft 365.

## <a name="implement-dmarc-for-inbound-mail"></a>Implementare DMARC per la posta in ingresso

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Implementare DMARC per la posta in uscita da Microsoft 365

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [Passaggio 1: identificare le origini valide della posta del dominio](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Passaggio 2: configurare SPF per il dominio](#step-2-set-up-spf-for-your-domain)

- [Passaggio 3: configurare DKIM per il dominio personalizzato](#step-3-set-up-dkim-for-your-custom-domain)

- [Passaggio 4: formare il record TXT DMARC del dominio](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Passaggio 1: identificare le origini valide della posta del dominio

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- Quali indirizzi IP inviano messaggi da qualsiasi dominio?

- Per i messaggi inviati da terze parti per conto dell'utente, i domini 5321.MailFrom e 5322.From corrisponderanno?

### <a name="step-2-set-up-spf-for-your-domain"></a>Passaggio 2: configurare SPF per il dominio

Ora che si ha un elenco di mittenti validi, è possibile seguire la procedura per [Configurare SPF per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

Ad esempio, presupponendo che contoso.com invia un messaggio da Exchange Online, un server Exchange locale il cui indirizzo IP è 192.168.0.1 e un'applicazione Web il cui indirizzo IP è 192.168.100.100, il record TXT SPFsarà simile alla seguente:

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Come procedura consigliata, assicurarsi che il record TXT SPF tenga in considerazione mittenti di terze parti.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Passaggio 3: configurare DKIM per il dominio personalizzato

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Per istruzioni sulla configurazione di DKIM per il dominio e su come configurare DKIM per mittenti di terze parti affinché possano effettuare lo spoofing del dominio, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Passaggio 4: formare il record TXT DMARC del dominio

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

dove:

- *domain* è il dominio da proteggere. Per impostazione predefinita, il record protegge la posta elettronica dal dominio e da tutti i sottodomini. Ad esempio, se si specifica \_dmarc.contoso.com, DMARC protegge la posta del dominio e da tutti i sottodomini, ad esempio housewares.contoso.com o plumbing.contoso.com.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* indica che questa regola deve essere utilizzata per il 100% della posta elettronica.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Per informazioni sulle opzioni da usare, acquisire familiarità con i concetti illustrati in [Procedure consigliate per l'implementazione di DMARC in Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).

Esempi:

- Criterio impostato su none

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Criterio impostato su quarantine

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Criterio impostato su reject

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Procedure consigliate per l'implementazione di DMARC in Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Monitorare l'effetto dell'implementazione DMARC

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. Richiedere che i sistemi di posta esterni mettano in quarantena la posta che non supera DMARC

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. Richiedere che i sistemi di posta esterni non accettino messaggi che non superano DMARC

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Come viene gestita la posta elettronica in uscita che non supera il controllo DMARC in Microsoft 365

Se un messaggio è in uscita da Microsoft 365 e non supera DMARC e il criterio è stato impostato su p=quarantine o p=reject, il messaggio viene instradato attraverso il [Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md). Non viene eseguito override della posta elettronica in uscita.

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Come viene gestita la posta elettronica in ingresso che non supera il controllo DMARC in Microsoft 365

Se il criterio DMARC del server di invio è `p=reject`, EOP contrassegna il messaggio come spoof invece di rifiutarlo. In altre parole, per la posta elettronica in ingresso, Microsoft 365 tratta `p=reject` e `p=quarantine` allo stesso modo. Gli amministratori possono definire l'azione da eseguire per i messaggi classificati come spoof nei [criteri anti-phishing](set-up-anti-phishing-policies.md).

Microsoft 365 è configurato in questo modo perché alcuni messaggi di posta elettronica legittimi potrebbero non superare DMARC. Ad esempio, un messaggio potrebbe non superare DMARC se viene inviato a una lista di distribuzione che poi inoltre il messaggio a tutti i partecipanti della lista. Se Microsoft 365 rifiutasse questi messaggi, le persone potrebbero perdere posta elettronica legittima e non ci sarebbe modo di recuperarla. Al contrario, questi messaggi continueranno a non superare DMARC ma verranno contrassegnati come posta indesiderata e non rifiutati. Se si desidera, gli utenti possono comunque ricevere questi messaggi nella propria posta in arrivo attraverso i seguenti metodi:

- Gli utenti aggiungono mittenti sicuri singolarmente mediante il loro client di posta elettronica.

- Gli amministratori possono aggiornare la creazione di report di [spoof intelligence](learn-about-spoof-intelligence.md) per consentire lo spoofing.

- Gli amministratori creano una regola di flusso di posta di Exchange, nota anche come regola di trasporto, per tutti gli utenti che consentono messaggi di questi mittenti specifici.

Per altre informazioni, vedere [Creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Come Microsoft 365 usa lo standard ARC (Authenticated Received Chain)

Tutte le cassette postali ospitate in Microsoft 365 otterranno ora i vantaggi di ARC con un migliore recapito dei messaggi e una maggiore protezione anti-spoofing. ARC conserva i risultati dell'autenticazione della posta elettronica di tutti gli intermediari partecipanti, o hop, quando un messaggio di posta elettronica viene instradato dal server di origine alla casella di posta del destinatario. Prima dello standard ARC, le modifiche apportate dagli intermediari nel routing della posta elettronica, come le regole di inoltro o le firme automatiche, potevano causare errori DMARC nel momento in cui il messaggio di posta elettronica raggiungeva la casella di posta del destinatario. Con ARC, la conservazione crittografica dei risultati dell'autenticazione permette a Microsoft 365 di verificare l'autenticità del mittente di un messaggio di posta elettronica.

Microsoft 365 attualmente usa ARC per verificare i risultati dell'autenticazione quando Microsoft è ARC Sealer, ma prevede di aggiungere in futuro il supporto di ARC Sealer di terze parti.

## <a name="troubleshooting-your-dmarc-implementation"></a>Risoluzione dei problemi relativi all'implementazione di DMARC

Se sono stati configurati i record MX del dominio in cui EOP non è la prima voce, gli errori DMARC non verranno applicati nel dominio.

Se si è clienti e il record MX principale del proprio dominio non punta a Exchange Online Protection, non si usufruirà dei vantaggi di DMARC. Ad esempio, DMARC non funzionerà se si punta il record MX al server di posta locale e si indirizza quindi la posta elettronica a EOP utilizzando un connettore. In questo scenario, il dominio di destinazione è uno dei domini accettati ma EOP non è il principale MX. Ad esempio, si supponga che contoso.com punti il relativo MX a se stesso e utilizzi EOP come un record MX secondario, il record MX di contoso.com avrà il seguente aspetto:

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Tutta la posta elettronica, o gran parte, verrà prima indirizzata a mail.contoso.com poiché è l'MX principale e poi la posta verrà instradata a EOP. In alcuni casi, potrebbe non essere neanche necessario EOP come record MX, ma potrebbe essere semplicemente sufficiente collegare connettori per instradare la posta elettronica. EOP non deve necessariamente essere la prima voce per la convalida di DMARC. Garantisce solo la convalida, perché non è possibile essere certi che tutti i server locali o non Office 365 eseguano controlli di DMARC.  DMARC è idoneo per essere applicato al dominio di un cliente (non al server) durante la configurazione del record TXT DMARC, ma l'applicazione dipende dal server di ricezione.  Se si configura EOP come server di ricezione, EOP esegue l'applicazione di DMARC.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Grafico della risoluzione dei problemi di DMARC, per gentile concessione di Daniel Mande":::

## <a name="for-more-information"></a>Ulteriori informazioni

Want more information about DMARC? These resources can help.

- [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include la sintassi e i campi di intestazione usati da Microsoft 365 per i controlli DMARC.

- Seguire la [serie di formazione su DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) da M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Utilizzare l'elenco di controllo in [dmarcian](https://space.dmarcian.com/deployment/).

- Passare direttamente all'origine in [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Vedere anche

[Uso di Sender Policy Framework (SPF) in Microsoft 365 per impedire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)

[Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Microsoft 365](use-dkim-to-validate-outbound-email.md)
