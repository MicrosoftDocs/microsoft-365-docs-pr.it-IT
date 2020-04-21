---
title: Domande frequenti sui domini
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Per ulteriori informazioni sui domini, è possibile trovare le risposte alle domande più frequenti.
ms.custom: okr_smb
ms.openlocfilehash: 4ece90306f37b6f07e34ce93423a76f084d50b6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627595"
---
# <a name="domains-faq"></a><span data-ttu-id="fdb56-103">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="fdb56-103">Domains FAQ</span></span>

<span data-ttu-id="fdb56-104">Questo articolo contiene le risposte alle domande frequenti sui domini in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="fdb56-105">Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="fdb56-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="fdb56-106">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="fdb56-106">What is MX priority?</span></span>

<span data-ttu-id="fdb56-107">La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  .</span><span class="sxs-lookup"><span data-stu-id="fdb56-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="fdb56-108">Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.</span><span class="sxs-lookup"><span data-stu-id="fdb56-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="fdb56-109">Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  .</span><span class="sxs-lookup"><span data-stu-id="fdb56-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="fdb56-110">Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  .</span><span class="sxs-lookup"><span data-stu-id="fdb56-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="fdb56-111">Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.</span><span class="sxs-lookup"><span data-stu-id="fdb56-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="fdb56-112">Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="fdb56-113">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="fdb56-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="fdb56-114">È importante avere o creare **un solo record TXT per SPF**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="fdb56-115">Se si ha già un record SPF, è necessario aggiungervi i nuovi valori di Office 365, invece di crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="fdb56-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="fdb56-116">Dopo aver aggiunto o aggiornato il record SPF per il messaggio di posta elettronica Microsoft, è necessario verificare che la sintassi sia corretta con uno di questi strumenti:</span><span class="sxs-lookup"><span data-stu-id="fdb56-116">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="fdb56-117">Strumenti di test del record SPF</span><span class="sxs-lookup"><span data-stu-id="fdb56-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="fdb56-118">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="fdb56-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="fdb56-119">Interfaccia Web Dig</span><span class="sxs-lookup"><span data-stu-id="fdb56-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="fdb56-120">Come vengono gestiti i record DNS in Office 365?</span><span class="sxs-lookup"><span data-stu-id="fdb56-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="fdb56-121">Sono disponibili due opzioni per la gestione DNS con Office 365:</span><span class="sxs-lookup"><span data-stu-id="fdb56-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="fdb56-122">È possibile modificare i record del server dei nomi (NS) e quindi Microsoft si occupa di tutti i record specifici del servizio, ad esempio la configurazione del record MX per la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-122">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="fdb56-123">**Consigliato**</span><span class="sxs-lookup"><span data-stu-id="fdb56-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="fdb56-124">È possibile aggiungere i record DNS per la posta elettronica e altri servizi di Office 365 all'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="fdb56-125">**(Solo esperti)**</span><span class="sxs-lookup"><span data-stu-id="fdb56-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="fdb56-126">Office 365 crea e ospita i record DNS</span><span class="sxs-lookup"><span data-stu-id="fdb56-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="fdb56-127">**Vantaggi**</span><span class="sxs-lookup"><span data-stu-id="fdb56-127">**Advantages**</span></span> 
- <span data-ttu-id="fdb56-128">Non c'è da preoccuparsi di commettere errori nei valori immessi per i record DNS per i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="fdb56-129">Si ottiene una maggiore flessibilità nella scelta del registrar e dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="fdb56-130">Si può scegliere qualsiasi provider che consenta di cambiare i record del server dei nomi, anche se non supporta tutti i tipi di record necessari.</span><span class="sxs-lookup"><span data-stu-id="fdb56-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="fdb56-131">Quando Office 365 aggiunge nuovi record DNS, non occorre eseguire aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fdb56-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="fdb56-132">Svantaggi</span><span class="sxs-lookup"><span data-stu-id="fdb56-132">Disadvantages</span></span> 
- <span data-ttu-id="fdb56-133">Non è possibile modificare i record DNS per ospitare la posta elettronica esternamente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="fdb56-134">Se si usa già un sito Web pubblico con il proprio dominio per l'indirizzo, ad esempio www.fourthcoffee.com, è necessario reindirizzare gli utenti a quell'indirizzo da Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="fdb56-135">La configurazione del reindirizzamento richiede un indirizzo IP statico, che non è sempre prontamente disponibile per i siti Web pubblici.</span><span class="sxs-lookup"><span data-stu-id="fdb56-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="fdb56-136">-Se il registrar corrente non consente di modificare i record del server dei nomi del dominio, è necessario passare a un altro registrar per utilizzare questa opzione di gestione DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="fdb56-137">Gestire manualmente i record DNS</span><span class="sxs-lookup"><span data-stu-id="fdb56-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="fdb56-138">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="fdb56-138">Advantages</span></span>
- <span data-ttu-id="fdb56-139">Si ha il controllo dei record DNS per i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="fdb56-140">Se si usa un sito Web pubblico con il proprio dominio per l'indirizzo, ad esempio www.fourthcoffee.com, non è necessario usare il reindirizzamento per fare in modo che gli utenti possano accedere al sito Web dopo la configurazione del dominio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="fdb56-141">Si dispone della flessibilità necessaria per ospitare la posta elettronica in un'altra posizione, ad esempio su un server di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="fdb56-142">Svantaggi</span><span class="sxs-lookup"><span data-stu-id="fdb56-142">Disadvantages</span></span>
<span data-ttu-id="fdb56-143">È necessario configurare i record DNS per i servizi di Office 365 manualmente, a meno che non si abbia un dominio GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="fdb56-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="fdb56-144">Se l'host DNS corrente non supporta tutti i tipi di record necessari per Microsoft 365, alcune funzionalità non saranno disponibili e potrebbe essere necessario passare a un host DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="fdb56-144">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="fdb56-145">Quando Office 365 cambia i requisiti per i record DNS o aggiunge nuovi servizi, è necessario effettuare gli aggiornamenti manualmente nell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="fdb56-146">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="fdb56-146">What is a domain name?</span></span>


<span data-ttu-id="fdb56-p105">Un dominio è un nome univoco che segue il segno **@** negli indirizzi di posta elettronica e **www.** negli indirizzi Web. In genere è composto dal nome dell'organizzazione e da un suffisso Internet standard, come  *nomeazienda.com*  o  *nomeuniversità.edu*  .</span><span class="sxs-lookup"><span data-stu-id="fdb56-p105">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="fdb56-150">L'utilizzo di un dominio personalizzato come "**rob\@contoso.com**" con Office 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="fdb56-151">È possibile [acquistare un dominio in Office 365 e lasciare che venga configurato automaticamente](../get-help-with-domains/buy-a-domain-name.md) oppure acquistarne uno o trasferirne uno già esistente presso un registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="fdb56-152">È possibile trasferire un dominio acquistato da Microsoft a un altro provider?</span><span class="sxs-lookup"><span data-stu-id="fdb56-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="fdb56-153">Sì, ma non è possibile trasferire un dominio di Office 365 a un altro registrar fino a 60 giorni dopo averlo acquistato con Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="fdb56-154">Si noti che una query *Whois* mostrerà un registrar del dominio di Office 365 acquistato come Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="fdb56-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="fdb56-155">Tuttavia, è necessario contattare solo Office 365 per quanto riguarda il dominio acquistato di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="fdb56-156">Eseguire la procedura seguente per ottenere un codice da Office 365 e quindi passare al sito Web dell'altro registrar per configurare il trasferimento del dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fdb56-157">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fdb56-158">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fdb56-159">Nell'interfaccia di amministrazione, passare alla pagina **delle** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licenze</a> per le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="fdb56-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fdb56-160">**Nella pagina** Domains selezionare il dominio di Office 365 che si desidera trasferire a un altro registrar, **quindi selezionare** > trasferimento di dominio**Abilita trasferimento del dominio**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="fdb56-161">Seguire la procedura per preparare il trasferimento del dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="fdb56-162">Dopo aver ottenuto il codice, passare al sito Web del registrar in cui si vuole gestire il nome del dominio in futuro e seguire le istruzioni visualizzate per trasferirlo (cercare la Guida sul sito Web).</span><span class="sxs-lookup"><span data-stu-id="fdb56-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="fdb56-163">Se è necessario visualizzare di nuovo il codice, nella pagina **Impostazioni dominio** in Office 365 selezionare **Visualizza codice di autorizzazione per il trasferimento del dominio**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="fdb56-164">Una volta completato il trasferimento, si rinnoverà il dominio presso il nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="fdb56-165">Per completare il processo, tornare alla pagina **Domains** dell'interfaccia di amministrazione e selezionare **completa trasferimento del dominio**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="fdb56-166">*Nota: tenere presente che i domini acquistati da Office 365 non sono idonei per le modifiche al server dei nomi o per il trasferimento del dominio tra i tenant di Office 365.  Se uno di questi due requisiti è necessario, la registrazione del dominio dovrà essere trasferita a un altro registrar.*</span><span class="sxs-lookup"><span data-stu-id="fdb56-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="fdb56-167">Come si fa a cambiare il modo in cui vengono gestiti i record DNS in Office 365?</span><span class="sxs-lookup"><span data-stu-id="fdb56-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="fdb56-168">Spostare la gestione del DNS su un host DNS esterno a Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb56-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="fdb56-169">Accedere al registrar del proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="fdb56-p107">Sul sito Web del registrar trovare l'area in cui vengono aggiornati i record dei server dei nomi e aggiornare i server dei nomi in modo che puntino all'host DNS del dominio. L'host DNS corrisponde spesso al registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p107">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="fdb56-172">Seguire un collegamento per passare all'installazione guidata dei domini:</span><span class="sxs-lookup"><span data-stu-id="fdb56-172">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="fdb56-173">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="fdb56-174">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-174">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="fdb56-175">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-175">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="fdb56-176">Nella pagina **Domains** selezionare il dominio che si sta commutando e selezionare **gestione DNS**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="fdb56-177">Nella procedura guidata di configurazione dei domini, nella pagina configurazione **dei servizi online** , selezionare **gestisco i propri record DNS**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="fdb56-178">Aggiungere i record DNS suggeriti dalla procedura guidata nella pagina **Aggiorna impostazioni DNS** al sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="fdb56-179">Dopo aver aggiunto i record, tornare a Office 365 e selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="fdb56-180">Spostare la gestione del DNS su Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb56-180">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fdb56-181">Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> **delle impostazioni** \> ..</span><span class="sxs-lookup"><span data-stu-id="fdb56-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fdb56-182">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-182">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fdb56-183">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-183">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fdb56-184">Nella pagina **Domains** selezionare il dominio che si sta commutando e selezionare **gestione DNS**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="fdb56-185">Nell'installazione guidata dei domini, nella pagina configurazione **dei servizi online** , selezionare **Configura i miei servizi online. (Scelta consigliata)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="fdb56-186">Se il dominio non è ancora stato verificato, eseguire prima la procedura corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="fdb56-p108">Nella pagina **Aggiorna impostazioni DNS** sono elencati i server dei nomi per Office 365. Passare al registrar del proprio dominio e aggiornare i server dei nomi ai server dei nomi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p108">On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="fdb56-189">Dopo aver aggiornato i server dei nomi, **attendere almeno un'ora**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="fdb56-190">Quindi, di nuovo nella procedura guidata di Office 365, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="fdb56-191">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="fdb56-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="fdb56-p110">Se si gestiscono personalmente i record DNS e l'host DNS scelto non supporta tutti i record DNS necessari per Office 365, alcune caratteristiche di Office 365 non saranno disponibili. È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p110">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="fdb56-194">Provider che supportano tutti i record DNS necessari:</span><span class="sxs-lookup"><span data-stu-id="fdb56-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="fdb56-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="fdb56-195">Dynadot</span></span>
    
- <span data-ttu-id="fdb56-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="fdb56-196">eNomCentral</span></span>
    
- <span data-ttu-id="fdb56-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="fdb56-197">Europe Registry</span></span>
    
- <span data-ttu-id="fdb56-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="fdb56-198">GoDaddy</span></span>
    
- <span data-ttu-id="fdb56-199">Hover</span><span class="sxs-lookup"><span data-stu-id="fdb56-199">Hover</span></span>
    
- <span data-ttu-id="fdb56-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="fdb56-200">MyHosting.com</span></span>
    
- <span data-ttu-id="fdb56-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="fdb56-201">Name.com</span></span>
    
- <span data-ttu-id="fdb56-202">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="fdb56-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="fdb56-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="fdb56-203">Nettica</span></span>
    
- <span data-ttu-id="fdb56-204">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="fdb56-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="fdb56-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="fdb56-205">Network Solutions</span></span>
    
- <span data-ttu-id="fdb56-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="fdb56-206">Register.com</span></span>
    
 <span data-ttu-id="fdb56-207">**Se i record SRV non sono supportati**, le caratteristiche di Office 365 seguenti non sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="fdb56-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="fdb56-208">Integrazione della messaggistica istantanea e della presenza di Skype for Business Online con Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="fdb56-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="fdb56-209">Comunicazione esterna (federazione) con gli utenti di Skype for Business Online in altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="fdb56-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="fdb56-210">Connettività Internet pubblica (PIC) con gli utenti di Skype for Business Online che hanno effettuato l'accesso con un account Microsoft (precedentemente noto come Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="fdb56-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="fdb56-211">**Se non sono supportati più record CNAME,** è necessario scegliere tra le seguenti funzionalità per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="fdb56-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="fdb56-212">Possibilità per i client di posta elettronica desktop e per dispositivi mobili di usare l'individuazione automatica per trovare automaticamente il servizio di Exchange Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="fdb56-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="fdb56-213">Possibilità per i client desktop di Skype for Business Online di usare l'individuazione automatica per trovare automaticamente il servizio di Skype for Business Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="fdb56-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="fdb56-214">Possibilità per i client di Skype for Business Online per dispositivi mobili di usare l'individuazione automatica per trovare automaticamente il servizio di Skype for Business Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="fdb56-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="fdb56-p111">**Se i record SPF/TXT non sono supportati**, altre persone potrebbero usare il dominio per inviare posta indesiderata o in altro modo dannosa. I record SPF identificano i server autorizzati a inviare posta elettronica per conto del dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p111">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="fdb56-217">Come impostare o modificare il dominio predefinito in Office 365?</span><span class="sxs-lookup"><span data-stu-id="fdb56-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="fdb56-218">Per scegliere un dominio predefinito, è necessario che sia stato aggiunto almeno un dominio personalizzato a Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fdb56-219">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fdb56-220">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-220">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fdb56-221">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fdb56-221">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fdb56-222">Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="fdb56-223">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="fdb56-224">Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="fdb56-225">Non è possibile modificare il nome del dominio iniziale *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="fdb56-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="fdb56-226">Non è possibile modificare il nome del dominio iniziale *. partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="fdb56-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="fdb56-227">È possibile aggiungere sottodomini personalizzati o più domini in Office 365?</span><span class="sxs-lookup"><span data-stu-id="fdb56-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="fdb56-228">Sì!</span><span class="sxs-lookup"><span data-stu-id="fdb56-228">Yes!</span></span> <span data-ttu-id="fdb56-229">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fdb56-230">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="fdb56-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="fdb56-231">Sì!</span><span class="sxs-lookup"><span data-stu-id="fdb56-231">Yes!</span></span> <span data-ttu-id="fdb56-232">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fdb56-233">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="fdb56-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="fdb56-234">Sì!</span><span class="sxs-lookup"><span data-stu-id="fdb56-234">Yes!</span></span> <span data-ttu-id="fdb56-235">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="fdb56-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fdb56-236">Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="fdb56-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="fdb56-237">In genere, è possibile aggiungere fino a 900 domini all'abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="fdb56-238">Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.</span><span class="sxs-lookup"><span data-stu-id="fdb56-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="fdb56-239">Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="fdb56-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="fdb56-p115">Quando si aggiungono più domini a Office 365 è possibile ospitare uno qualsiasi dei servizi (ad esempio la posta elettronica) in uno qualsiasi dei domini aggiunti.  *Quando si configura la posta elettronica per Office 365 aggiornando il record MX del dominio, TUTTI i messaggi inviati al dominio specificato inizieranno a essere recapitati a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="fdb56-p115">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="fdb56-242">Se è già stato aggiunto un dominio contoso.com a un tenant di Office 365, è anche possibile aggiungere il sottodominio xyz.contoso.com a un altro tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="fdb56-243">Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="fdb56-244">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="fdb56-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="fdb56-245">Office 365 crea un dominio per l'utente, come *contoso.onmicrosoft.com*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="fdb56-246">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="fdb56-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="fdb56-247">**Se si desidera che la posta elettronica sia simile *a\@Alan contoso.com*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Office 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="fdb56-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="fdb56-p118">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**. Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com. Per usare un dominio onmicrosoft.com diverso, si dovrà iniziare un nuovo abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p118">**You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="fdb56-251">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="fdb56-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="fdb56-252">L'URL del sito del team si basa sul nome di dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="fdb56-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="fdb56-253">Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="fdb56-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="fdb56-p120">**Non è possibile rimuovere il dominio onmicrosoft.** Office 365 ne ha bisogno perché viene usato per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p120">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="fdb56-p121">Si può continuare a usare il dominio iniziale onmicrosoft.com anche dopo l'aggiunta di quello personalizzato. È infatti sempre valido per la posta elettronica e altri servizi. La scelta spetta all'utente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p121">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="fdb56-259">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="fdb56-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="fdb56-260">Office 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="fdb56-261">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="fdb56-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="fdb56-262">**Se si desidera che la posta elettronica sia simile a *Alan@contoso.de*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Office 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="fdb56-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="fdb56-263">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="fdb56-264">Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="fdb56-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="fdb56-265">Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="fdb56-266">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="fdb56-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="fdb56-267">L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="fdb56-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="fdb56-p125">**Non è possibile rimuovere il dominio onmicrosoft.** Office 365 ne ha bisogno perché viene usato per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fdb56-p125">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="fdb56-271">È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="fdb56-272">Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.</span><span class="sxs-lookup"><span data-stu-id="fdb56-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="fdb56-273">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="fdb56-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="fdb56-274">Selezionare **installazione** nell'interfaccia di [Amministrazione](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fdb56-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="fdb56-275">(Assicurarsi di accedere a Office 365 per primo).</span><span class="sxs-lookup"><span data-stu-id="fdb56-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="fdb56-276">Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione **diventa amministratore** in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="fdb56-277">Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="fdb56-278">Perché?</span><span class="sxs-lookup"><span data-stu-id="fdb56-278">Why?</span></span> <span data-ttu-id="fdb56-279">Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Office 365 che si è proprietari del nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="fdb56-280">Dopo aver aggiunto il record, è possibile tornare al portale di Office 365 e verificare di averla aggiunta, quindi Office 365 può controllare.</span><span class="sxs-lookup"><span data-stu-id="fdb56-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="fdb56-281">Avere un no profit e desidera ottenere Office 365?</span><span class="sxs-lookup"><span data-stu-id="fdb56-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="fdb56-282">Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="fdb56-283">Vuoi saperne di più su come diventare l'amministratore per la tua scuola?</span><span class="sxs-lookup"><span data-stu-id="fdb56-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="fdb56-284">Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="fdb56-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="fdb56-285">È possibile pilotare Office 365 con solo alcuni indirizzi di posta elettronica provenienti dal dominio personalizzato?</span><span class="sxs-lookup"><span data-stu-id="fdb56-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="fdb56-286">È possibile, ma esistono limitazioni:</span><span class="sxs-lookup"><span data-stu-id="fdb56-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="fdb56-287">Il provider di posta elettronica corrente deve fornire l'inoltro della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="fdb56-288">È necessario gestire i record DNS relativi a Office 365 nel provider di hosting DNS, anziché utilizzare Office 365 per gestire questi record.</span><span class="sxs-lookup"><span data-stu-id="fdb56-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="fdb56-289">Per sapere cosa comporta, vedere Aggiungere il proprio dominio a Office 365 quando si desidera gestire i propri record DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="fdb56-290">Alcune funzionalità di Office 365 non sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="fdb56-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="fdb56-291">Gli utenti non saranno in grado di visualizzare le informazioni sulla disponibilità per gli utenti che si trovano nell'altro provider di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="fdb56-292">Gli amministratori non saranno in grado di amministrare gli account di tutti da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="fdb56-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="fdb56-293">Gli utenti potrebbero non essere in grado di utilizzare il filtro posta indesiderata di Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb56-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="fdb56-294">Come configurare un pilota di Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb56-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="fdb56-295">Accedere all'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fdb56-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="fdb56-296">Accedere a Office 365 con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="fdb56-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="fdb56-297">Andare a **Settings** \> **Domains**Settings.</span><span class="sxs-lookup"><span data-stu-id="fdb56-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="fdb56-298">Verificare di essere proprietari del dominio che si desidera utilizzare</span><span class="sxs-lookup"><span data-stu-id="fdb56-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="fdb56-299">Nella pagina **Domains** selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="fdb56-300">Nel riquadro, digitare il dominio, in questo esempio cohowinery.com, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="fdb56-301">Nella pagina **Verifica** dominio, seguire le istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="fdb56-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="fdb56-302">Nell'elenco a discesa selezionare il provider di hosting DNS e seguire le istruzioni visualizzate per indicare che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb56-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="fdb56-303">Selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-303">Select **Verify**.</span></span> <span data-ttu-id="fdb56-304">Per rendere effettive le modifiche al DNS, sono necessari tra alcuni minuti e 72 ore.</span><span class="sxs-lookup"><span data-stu-id="fdb56-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="fdb56-305">Quando la verifica ha esito positivo, verrà chiesto di modificare i record DNS.</span><span class="sxs-lookup"><span data-stu-id="fdb56-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="fdb56-306">Contrassegnare il dominio come condiviso in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fdb56-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="fdb56-307">Passare all'interfaccia di **amministrazione di Exchange** (EAC).</span><span class="sxs-lookup"><span data-stu-id="fdb56-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="fdb56-308">Nella sezione **flusso di posta** selezionare **domini accettati**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="fdb56-309">Fare doppio clic sul dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="fdb56-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="fdb56-310">Nella finestra che viene visualizzata, selezionare **Internal Relay**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="fdb56-311">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-311">Select **Save**.</span></span> <span data-ttu-id="fdb56-312">Questa impostazione può richiedere alcuni minuti per rendere effettive le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="fdb56-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="fdb56-313">Facoltativamente, sbloccare il server di posta elettronica esistente</span><span class="sxs-lookup"><span data-stu-id="fdb56-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="fdb56-314">Office 365 utilizza Exchange Online Protection (EOP) per la protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fdb56-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="fdb56-315">Se EOP rileva un elevato volume di posta indesiderata che viene inoltrata dal server di posta corrente, potrebbe bloccarla, in modo da impedire l'inoltro di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fdb56-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="fdb56-316">Se si è sicuri della protezione da posta indesiderata utilizzata dall'altro provider di posta elettronica, è possibile inserire in whitelist il server in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="fdb56-317">Tuttavia, ciò consentirà anche qualsiasi posta indesiderata che arriva attraverso il server originale per accedere alle cassette postali di Office 365 e non sarà in grado di valutare come Office 365 impedisce la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fdb56-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="fdb56-318">Accedere a interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="fdb56-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="fdb56-319">In interfaccia di amministrazione di Exchange, selezionare **protezione**, quindi selezionare **filtro connessioni**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="fdb56-320">Nell' **elenco indirizzi IP consentiti**, selezionare **+** e aggiungere l'indirizzo IP del server di posta elettronica che è possibile ottenere dal provider di posta elettronica corrente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="fdb56-321">Creare gli account utente e impostare l'indirizzo primario (Rispondi a)</span><span class="sxs-lookup"><span data-stu-id="fdb56-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="fdb56-322">Passare all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="fdb56-323">Sulla barra di spostamento sinistra **fare clic** \> su utenti **attivi**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="fdb56-324">Creare gli account utente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="fdb56-325">Per ogni account selezionare **+ (nuovo)** e compilare le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="fdb56-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="fdb56-326">Per mantenere la posta elettronica dell'utente nello stesso modo in cui si trova attualmente, il campo **nome utente** deve corrispondere esattamente a quello dell'indirizzo di posta elettronica esistente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="fdb56-327">Accanto a nome utente, selezionare il nome di dominio personalizzato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fdb56-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="fdb56-328">Selezionare **Crea** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fdb56-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="fdb56-329">Aggiornare i record DNS presso il provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="fdb56-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="fdb56-330">Accedere al sito Web del provider di hosting DNS e seguire le [istruzioni per la creazione di record DNS presso qualsiasi provider di hosting DNS per Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="fdb56-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="fdb56-331">**Eseguire le eccezioni seguenti:**</span><span class="sxs-lookup"><span data-stu-id="fdb56-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="fdb56-332">Non creare un nuovo record MX o modificare il record MX esistente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="fdb56-333">Se si dispone già di un record SPF (Sender Policy Framework) per il provider di posta elettronica precedente, invece di creare un nuovo record SPF (TXT) per Exchange Online, è sufficiente aggiungere "include: SPF. Protection. Outlook. com" al record TXT corrente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="fdb56-334">Ad esempio, "v = spf1 mx include:adatum. com include: SPF. Protection. Outlook. com ~ All".</span><span class="sxs-lookup"><span data-stu-id="fdb56-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="fdb56-335">Se non si dispone ancora di un record SPF, modificare quello consigliato da Office 365 per includere il dominio per il provider di posta elettronica corrente, più spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fdb56-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="fdb56-336">Questo autorizza i messaggi in uscita provenienti da entrambi i sistemi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="fdb56-337">Configurare l'inoltro della posta elettronica al provider corrente</span><span class="sxs-lookup"><span data-stu-id="fdb56-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="fdb56-338">Nel provider di posta elettronica corrente impostare l'inoltro per gli account di posta elettronica degli utenti nel dominio onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="fdb56-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="fdb56-339">La cassetta postale di un utente deve inoltrare a usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="fdb56-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="fdb56-340">La cassetta postale dell'utente B deve inoltrare a userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="fdb56-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="fdb56-341">Al termine di questo passaggio:</span><span class="sxs-lookup"><span data-stu-id="fdb56-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="fdb56-342">Tutti i messaggi inviati a usera@yourcompany.com e userb@yourcompany.com saranno disponibili in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="fdb56-343">Note:</span><span class="sxs-lookup"><span data-stu-id="fdb56-343">Notes:</span></span>
        
        - <span data-ttu-id="fdb56-344">Contattare il provider di posta elettronica corrente per la procedura esatta per la configurazione dell'inoltro.</span><span class="sxs-lookup"><span data-stu-id="fdb56-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="fdb56-345">Non è necessario mantenere una copia dei messaggi nel provider di posta elettronica corrente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="fdb56-346">La maggior parte dei provider inoltra la posta elettronica lasciando l'indirizzo Reply-to del mittente intatto, in modo che le risposte vadano al mittente originale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="fdb56-347">Testare il flusso di posta</span><span class="sxs-lookup"><span data-stu-id="fdb56-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="fdb56-348">Accedere a Outlook Web App utilizzando le credenziali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="fdb56-349">Eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="fdb56-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="fdb56-350">Testare il messaggio di posta elettronica Microsoft locale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-350">Test local Microsoft email.</span></span> <span data-ttu-id="fdb56-351">Ad esempio, inviare un messaggio di posta elettronica all'utente B. Questo messaggio di posta elettronica deve essere recapitato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="fdb56-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="fdb56-352">In questo scenario, il messaggio non verrà instradato alla cassetta postale dell'utente B sul server originale perché Office 365 Visualizza la cassetta postale come locale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="fdb56-353">Provare la posta elettronica a un utente che si trova nell'altro sistema di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="fdb56-354">Ad esempio, inviare un messaggio di posta elettronica all'utente C. Questo messaggio di posta elettronica deve essere recapitato alla cassetta postale dell'utente C sul server di posta originale.</span><span class="sxs-lookup"><span data-stu-id="fdb56-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="fdb56-355">Da un account esterno o da un account di posta elettronica di un dipendente nell'altro sistema di posta elettronica, verificare che l'inoltro sia configurato correttamente nell'altro sistema di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fdb56-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="fdb56-356">Ad esempio, dall'account del server origninal dell'utente o da un account Hotmail, inviare un messaggio di posta elettronica A un utente e verificare che arrivi nella cassetta postale dell'utente A Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb56-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="fdb56-357">Spostamento del contenuto della cassetta postale</span><span class="sxs-lookup"><span data-stu-id="fdb56-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="fdb56-358">Poiché vi sono solo due utenti da spostare e poiché l'utente A e l'utente B sono entrambi con Outlook già, è possibile spostare il messaggio di posta elettronica aprendo il vecchio. File PST nel nuovo profilo di Outlook e copia dei messaggi, elementi del calendario, contatti e così via, come illustrato in importare gli elementi di Outlook da un file di dati di Outlook (con estensione pst).</span><span class="sxs-lookup"><span data-stu-id="fdb56-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="fdb56-359">Una volta organizzati nelle posizioni appropriate nella cassetta postale di Office 365, è possibile accedere a tutti gli elementi da qualsiasi dispositivo e da qualsiasi luogo.</span><span class="sxs-lookup"><span data-stu-id="fdb56-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="fdb56-360">Quando sono coinvolte altre cassette postali o se i dipendenti non utilizzano già Outlook, è possibile utilizzare gli strumenti di migrazione disponibili nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fdb56-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="fdb56-361">Per iniziare, passare all'interfaccia di amministrazione di Exchange e seguire le istruzioni riportate in migrare la posta elettronica da un server IMAP alle cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fdb56-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
