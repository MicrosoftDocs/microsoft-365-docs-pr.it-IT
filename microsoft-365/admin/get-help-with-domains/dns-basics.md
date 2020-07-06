---
title: Informazioni di base sul DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Informazioni sui domini e sui record DNS associati per gestire più facilmente i propri domini.
ms.openlocfilehash: c9fee3488f7de3c0cc4b93be15ff49bd01469495
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035610"
---
# <a name="dns-basics"></a>Informazioni di base sul DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

I nomi di dominio, ad esempio contoso.com, vengono gestiti mediante un sistema internazionale di registrar e database. Il Domain Name System (DNS) fornisce un mapping tra i nomi host dei computer leggibili e gli indirizzi IP usati dalle apparecchiature di rete. La comprensione dei concetti fondamentali relativi al DNS e ai registrar faciliterà la gestione dei domini.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Che cosa sono i nomi di dominio?

Domain names are used in URLs and email addresses, and they have different levels. For example, mail.contoso.com is a domain name with the following three levels:
  
- **.com** è il dominio di primo livello 
    
- **contoso** è il dominio di secondo livello 
    
- **mail** è il dominio di terzo livello 
    
Why use a third-level domain? You might want to have different domain names for marketing or a blog. For example, blog.contoso.com. You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.
  
Per altre informazioni su cosa è possibile fare con i domini per ogni tipo di offerta, vedere la [descrizione dei servizi delle piattaforme Microsoft 365 e Office 365](https://go.microsoft.com/fwlink/?LinkId=402693).
  
## <a name="understand-dns-record-types"></a>Comprendere i tipi di record DNS

DNS records stored at a DNS host for your domain are used to direct traffic for your domain. The following table describes frequently used DNS records and how they're used.
  
|**Record del server dei nomi (NS)**|**Identifica i server dei nomi autorevoli per un dominio. Se si cambiano i server dei nomi per il dominio, cambia anche la posizione in cui vengono gestiti i record DNS e in cui il sistema DNS cerca le informazioni sui server della posta e altro. Microsoft ha i propri server dei nomi, ma si può decidere di continuare a usare quelli già configurati con il proprio dominio.**|
|:-----|:-----|
|Un record (record dell'indirizzo)  <br/> |Associa un nome di dominio a un indirizzo IP.  <br/> |
|Record CNAME (alias o canonico)  <br/> |Redirects one domain to another in the DNS system. When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.  <br/> |
|Record MX (Mail Exchanger)  <br/> |Points to where your email should be sent. It also has a priority field so that you can send mail to different servers in a priority order.  <br/> |
|Record SPF (sender policy framework)  <br/> |Un record TXT che consente di prevenire spoofing e phishing di posta elettronica.  <br/> |
|Record SRV (service)  <br/> |Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services. For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.  <br/> |
|TTL (Time-To-Live)  <br/> |Il periodo di tempo in cui un server dei nomi mantiene un record DNS prima di cercarne una versione aggiornata.  <br/> |
   
## <a name="how-does-dns-work"></a>Come funziona il sistema DNS?

Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain. These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites. 
  
The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses. IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.
  
So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name. When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.
  
A domain's DNS records can be helpful in other ways, too. For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>I record DNS consentono a Internet di indirizzare correttamente la posta elettronica

As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses. One DNS record, called the MX record, is specifically for sending email to the right host.
  
DNS records are like a database of information about your domain. The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is. Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file. And that's where you update the MX record for your domain, to send email messages to Microsoft 365.
  
 *When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*  If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people. 
  
Sound complicated? Well, it can be, but we walk you through each step in the Microsoft domain setup.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>Il DNS indica a Internet dove cercare i siti Web

When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com. The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain. There are lots of DNS servers, all connected to each other. The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.
  
::: moniker range="o365-worldwide"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-germany"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-21vianet"

Si supponga che il record NS di contoso.com sia "hichina.com". Internet riconosce che deve cercare in hichina.com il file di zona che elenca tutti gli altri record DNS per contoso.com. I record DNS includono il record MX che indica dove inviare i messaggi di posta elettronica per contoso.com e altri record. Se il valore del record MX è "invia la posta elettronica a Microsoft 365" (anche se lo indica in termini tecnici), è qui che verranno recapitati tutti i messaggi inviati a un indirizzo di posta elettronica di contoso.com, ad esempio luca@contoso.com. Quindi, purché in questa posizione ci sia una cassetta postale con questo nome, il messaggio verrà recapitato.

::: moniker-end

The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps. If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.
  
::: moniker range="o365-worldwide"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-germany"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-21vianet"

Il file di zona del dominio può infatti essere archiviato in una posizione diversa dal registrar. Ad esempio, si può registrare il proprio dominio presso un registrar come HiChina e affidare la gestione dei record DNS a un altro provider di hosting DNS o di hosting Web. I record NS del dominio archiviano tali informazioni in modo che tutti i server DNS sappiano dove cercare.

::: moniker-end

> [!NOTE]
> Se si configura il dominio in Microsoft 365 in modo che i [record DNS vengano configurati e gestiti automaticamente da Microsoft](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records), nell'ambito della configurazione è necessario [spostare la gestione del DNS su Microsoft 365](../setup/domains-faq.md#change-dns-management-to-office-365). 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>Perché aggiungere un dominio in Office 365?


Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email. 
  
> [!NOTE]
> Se si vogliono solo scaricare e usare le app di Microsoft, come Outlook o Word, non è necessario aggiungere il dominio. Vedere [Installare Office nel PC o nel Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
È possibile usare il nome di dominio in Microsoft 365 con la posta elettronica, il sito Web pubblico e l'indirizzo di messaggistica istantanea.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com. 
    
- **Sito Web:** se il proprio abbonamento a Microsoft 365 include un sito Web pubblico di SharePoint Online (non più disponibile per l'acquisto), il sito Web pubblico è associato a un indirizzo iniziale simile a contoso-public.sharepoint.com. Se si configura il sito Web per la propria attività commerciale, è possibile usare un nome di dominio personalizzato per rinominare l'indirizzo del sito Web, ad esempio in www.contoso.com. 
    
- **Messaggistica istantanea:** anche l'indirizzo di Skype for Business online può essere personalizzato in modo da usare il nome di dominio, per consentire agli utenti dell'organizzazione di comunicare su Skype for Business online usando un indirizzo più breve e più facile da ricordare (come luca@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Perché aggiungere un dominio in Microsoft 365?


Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email. 
  
> [!NOTE]
> Se si vogliono solo scaricare e usare le app di Microsoft 365, come Outlook o Word, non è necessario aggiungere il dominio. Vedere [Installare Office nel PC o nel Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
È possibile usare il nome di dominio in Microsoft 365 con la posta elettronica, il sito Web pubblico e l'indirizzo di messaggistica istantanea.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com. 
    
- **Sito Web:** se il proprio abbonamento include un sito Web pubblico di SharePoint Online (non più disponibile per l'acquisto), il sito Web pubblico è associato a un indirizzo iniziale simile a contoso-public.sharepoint.com. Se si configura il sito Web per la propria attività commerciale, è possibile usare un nome di dominio personalizzato per rinominare l'indirizzo del sito Web, ad esempio in www.contoso.com. 
    
- **Messaggistica istantanea:** anche l'indirizzo di Skype for Business online può essere personalizzato in modo da usare il nome di dominio, per consentire agli utenti dell'organizzazione di comunicare su Skype for Business online usando un indirizzo più breve e più facile da ricordare (come luca@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Record DNS necessari per Microsoft 365

There are a number of DNS records required for Microsoft 365 to work with your domain. In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.
  
You can [find a list of values](information-for-dns-records.md) to set up your domain. They're included right in the Microsoft 365 admin center. 
  
In alternativa, se si prevede una distribuzione, è consigliabile rivedere un elenco di tutti i record DNS necessari per Microsoft 365, con la relativa funzione ed esempi di valori. Vedere [Record DNS (Domain Name System) esterni per Microsoft 365](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).
  
## <a name="how-can-i-learn-more"></a>Altre informazioni

Vedere una delle opzioni seguenti: 
  
- Non si conosce dov'è registrato il dominio? [Ottenere assistenza per conoscere il registrar.](find-your-domain-registrar.md)
- Scoprire [perché occorre completare i passaggi della procedura guidata](../setup/add-domain.md) prima di usare il dominio con Microsoft 365.
