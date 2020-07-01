---
title: Configurazione di SPF per evitare lo spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come aggiornare un record DNS (Domain Name Service) per usare un Sender Policy Framework (SPF) con il dominio personalizzato in Office 365.
ms.openlocfilehash: 93356799967932813252e7db27e7ac796e46cbc6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936938"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configurazione di SPF per evitare lo spoofing

 **Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.

In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.

For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.

Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.

If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:

- Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".

- Se si dispone di un ambiente ibrido con Office 365 ed Exchange in locale.

- Si intende configurare DKIM e DMARC (scelta consigliata).

## <a name="updating-your-spf-txt-record-for-office-365"></a>Aggiornamento del record TXT SPF per Office 365

Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Raccogliere le seguenti informazioni:

- The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).

- External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.

- Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.

- Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>Per aggiungere o aggiornare il record TXT SPF

1. Assicurarsi di avere familiarità con la sintassi SFP nella tabella seguente.

   ||**Se si sta utilizzando...**|**Comune per i clienti?**|**Aggiungere...**|
   |:-----|:-----|:-----|:-----|
   |1|Qualsiasi sistema di posta elettronica (obbligatorio)|Common. All SPF TXT records start with this value|v=spf1|
   |2|Exchange Online|Comune|include:spf.protection.outlook.com|
   |3|Solo per Exchange Online|Non comune|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|Office 365 Germania, solo Microsoft Cloud Germania|Non comune|include:spf.protection.outlook.de|
   |5|Un sistema di posta elettronica di terze parti|Non comune|Includere:\<domain name\>  <br/> Dove il nome di dominio è il nome di dominio del sistema di posta elettronica di terze parti.|
   |6|On-premises mail system. For example, Exchange Online Protection plus another mail system|Non comune| Utilizzarne uno per ogni sistema di posta elettronica aggiuntivo: <br> ip4:\<_IP address_\>  <br/>  ip6:\<_IP address_\>  <br/>  Includere:\<_domain name_\>  <br/>  Dove il valore per \<_IP address_\> è l'indirizzo IP del sistema di posta elettronica e \<_domain name_\> è il nome di dominio dell'altro sistema di posta elettronica che invia un messaggio per conto del dominio.|
   |7|Qualsiasi sistema di posta elettronica (obbligatorio)|Common. All SPF TXT records end with this value|\<_enforcement rule_\>  <br/> This can be one of several values. We recommend that you use **-all**.|

2. Se non è già stato fatto, costituire il record TXT SPF utilizzando la sintassi della tabella:

   Ad esempio, se l'utente è completamente ospitato in Office 365, che significa che non sono presenti server di posta elettronica locali, il record TXT SPF includerà le righe 1, 2 e 7 e si otterrà un risultato simile al seguente:

   `v=spf1 include:spf.protection.outlook.com -all`

   Questo è il record TXT SPF più comune. Questo record funziona praticamente per tutti, indipendentemente dal fatto che il datacenter di Microsoft si trovi negli Stati Uniti, in Europa (Germania inclusa) o in un'altra area geografica.

   However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:

   `v=spf1 include:spf.protection.outlook.de -all`

   Se l'utente è già distribuito in Office 365, dispone di record TXT SPF configurati per il dominio personalizzato e sta eseguendo la migrazione a Office 365 Germania, è necessario aggiornare il record TXT SPF. A tale scopo, modificare **include:spf.protection.outlook.com** in **include:spf.protection.outlook.de**.

3. Dopo aver creato il record TXT SPF, è necessario aggiornare il record in DNS. È possibile avere un solo record TXT SPF per un dominio. Se esiste un record TXT SPF, anziché aggiungere un nuovo record, è necessario aggiornare quello esistente. Passare a [Creare record DNS per Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) e fare clic sul collegamento relativo al proprio host DNS.

4. Verificare il record TXT SPF.

## <a name="more-information-about-spf"></a>Per ulteriori informazioni su SPF

Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, dello spoofing, della risoluzione dei problemi e di come Office 365 supporta SPF, vedere [Come funziona SPF per impedire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Passaggi successivi: Dopo aver configurato SPF per Office 365

Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).
