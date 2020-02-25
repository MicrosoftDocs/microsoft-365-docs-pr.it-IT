---
title: Modificare i server dei nomi per configurare Office 365 con un registrar
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Informazioni su come aggiungere e configurare il dominio in Office 365 in modo che i servizi come la posta elettronica e Skype for business online utilizzino il proprio nome di dominio.
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252968"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="730ea-103">Modificare i server dei nomi per configurare Office 365 con un registrar</span><span class="sxs-lookup"><span data-stu-id="730ea-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="730ea-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="730ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="730ea-105">Controllare [la configurazione del dominio (istruzioni specifiche per l'host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) per vedere se sono disponibili istruzioni per il registrar.</span><span class="sxs-lookup"><span data-stu-id="730ea-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="730ea-106">Seguire queste istruzioni per aggiungere e configurare il dominio in Office 365 in modo che il nome del dominio venga usato da servizi come la posta elettronica e Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="730ea-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="730ea-107">A tale scopo è necessario verificare il dominio e quindi impostare i server dei nomi del dominio su Office 365, in modo che i record DNS corretti vengano configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="730ea-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="730ea-108">Attenersi alla seguente procedura se le istruzioni seguenti descrivono la propria situazione:</span><span class="sxs-lookup"><span data-stu-id="730ea-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="730ea-109">Si dispone di un dominio e si desidera configurarlo per l'uso con Office 365.</span><span class="sxs-lookup"><span data-stu-id="730ea-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="730ea-p102">Si desidera che Office 365 gestisca automaticamente i record DNS. Se si preferisce, è possibile [gestire personalmente i propri record DNS](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="730ea-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="730ea-112">Aggiungere un record TXT o MX a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="730ea-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="730ea-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="730ea-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="730ea-p103">È necessario creare solo uno di questi record. Il record TXT è solitamente il tipo preferito, ma non è supportato da alcuni provider di hosting DNS. In questi casi è possibile creare un record MX.</span><span class="sxs-lookup"><span data-stu-id="730ea-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="730ea-p104">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="730ea-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="730ea-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="730ea-120">Individuare l'area del sito Web del provider di hosting DNS in cui è possibile creare un nuovo record</span><span class="sxs-lookup"><span data-stu-id="730ea-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="730ea-121">Accedere al sito del provider del servizio di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="730ea-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="730ea-122">Scegliere il dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="730ea-123">Trovare la pagina in cui è possibile modificare i record DNS del proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="730ea-124">Creare il record</span><span class="sxs-lookup"><span data-stu-id="730ea-124">Create the record</span></span>

<span data-ttu-id="730ea-125">Eseguire una delle operazioni seguenti in base al record da creare, ossia TXT o MX:</span><span class="sxs-lookup"><span data-stu-id="730ea-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="730ea-126">**Se si crea un record TXT, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="730ea-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="730ea-127">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="730ea-127">**Record Type**</span></span> <br/> |<span data-ttu-id="730ea-128">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="730ea-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="730ea-129">**Valore**</span><span class="sxs-lookup"><span data-stu-id="730ea-129">**Value**</span></span> <br/> |<span data-ttu-id="730ea-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="730ea-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="730ea-131">TXT</span><span class="sxs-lookup"><span data-stu-id="730ea-131">TXT</span></span>  <br/> |<span data-ttu-id="730ea-132">Eseguire una delle operazioni seguenti: Digitare **@**, lasciare vuoto il campo o immettere il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="730ea-133">> [!NOTE]> I requisiti di questo campo variano a seconda dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="730ea-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="730ea-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="730ea-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="730ea-p106">> [!NOTE]> Questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="730ea-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="730ea-138">Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.</span><span class="sxs-lookup"><span data-stu-id="730ea-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="730ea-139">**Se si crea un record MX, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="730ea-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="730ea-140">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="730ea-140">**Record Type**</span></span>|<span data-ttu-id="730ea-141">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="730ea-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="730ea-142">**Valore**</span><span class="sxs-lookup"><span data-stu-id="730ea-142">**Value**</span></span>|<span data-ttu-id="730ea-143">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="730ea-143">**Priority**</span></span>|<span data-ttu-id="730ea-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="730ea-144">**TTL**</span></span>|
|<span data-ttu-id="730ea-145">MX</span><span class="sxs-lookup"><span data-stu-id="730ea-145">MX</span></span>|<span data-ttu-id="730ea-146">Digitare **@** o il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="730ea-p107">MS=ms *XXXXXXXX* > [!NOTE]> Questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="730ea-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="730ea-150">Per **priorità**, per evitare conflitti con il record MX utilizzato per il flusso di posta, usare una priorità più bassa rispetto alla priorità per tutti i record MX esistenti.</span><span class="sxs-lookup"><span data-stu-id="730ea-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="730ea-151">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](../setup/domains-faq.md#what-is-mx-priority).</span><span class="sxs-lookup"><span data-stu-id="730ea-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="730ea-152">Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.</span><span class="sxs-lookup"><span data-stu-id="730ea-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="730ea-153">Salvare il record</span><span class="sxs-lookup"><span data-stu-id="730ea-153">Save the record</span></span>

<span data-ttu-id="730ea-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="730ea-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="730ea-155">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="730ea-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="730ea-156">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="730ea-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="730ea-157">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="730ea-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="730ea-158">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="730ea-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="730ea-159">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="730ea-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="730ea-p109">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="730ea-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="730ea-163">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="730ea-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="730ea-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="730ea-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="730ea-p110">Quando si arriva all'ultimo passaggio della configurazione del dominio in Office 365, rimane da eseguire una sola attività. Per configurare il dominio con i servizi di Office 365, come la posta elettronica, occorre modificare i record dei server dei nomi (NS) del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Poiché quindi Office 365 ospita il DNS, i record DNS necessari per i servizi vengono configurati automaticamente. È possibile aggiornare i record dei server dei nomi manualmente seguendo i passaggi eventualmente disponibili nella Guida del sito Web del registrar. Se non si ha familiarità con il DNS, contattare il supporto del registrar.</span><span class="sxs-lookup"><span data-stu-id="730ea-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="730ea-170">Per modificare i server dei nomi del dominio presso il sito Web del registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="730ea-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="730ea-171">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="730ea-172">Creare due record dei server dei nomi o modificare quelli esistenti, in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="730ea-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="730ea-173">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="730ea-173">First nameserver</span></span>  <br/> |<span data-ttu-id="730ea-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="730ea-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="730ea-175">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="730ea-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="730ea-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="730ea-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="730ea-177">È consigliabile utilizzare almeno due record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="730ea-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="730ea-178">Se sono elencati altri server dei nomi, è possibile eliminarli o modificarli in **NS3.BDM.microsoftonline.com** e **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="730ea-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="730ea-179">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="730ea-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="730ea-p112">La modifica dei record NS del dominio in modo che puntino ai server dei nomi di Office 365 ha effetto su tutti i servizi attualmente associati al dominio. Se si saltano alcuni passaggi della procedura guidata, come l'aggiunta degli indirizzi di posta elettronica, oppure se il dominio viene usato per blog, carrelli acquisti o altri servizi, è necessario completare altri passaggi, per evitare che questa modifica comporti tempi di inattività per i servizi, ad esempio l'impossibilità di accedere alla posta elettronica o al sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="730ea-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="730ea-183">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="730ea-184">Creare due record dei server dei nomi o modificare quelli esistenti, in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="730ea-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="730ea-185">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="730ea-185">First nameserver</span></span>  <br/> |<span data-ttu-id="730ea-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="730ea-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="730ea-187">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="730ea-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="730ea-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="730ea-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="730ea-189">È consigliabile utilizzare almeno due record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="730ea-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="730ea-190">Se sono elencati altri server dei nomi, è possibile eliminarli o modificarli in **NS3.DNS.partner.microsoftonline.cn** e **NS4.DNS.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="730ea-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="730ea-191">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="730ea-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="730ea-192">Quando si modificano i record NS del dominio in modo che puntino a Office 365 gestito da server dei nomi di 21Vianet, tutti i servizi attualmente associati al dominio sono intaccati.</span><span class="sxs-lookup"><span data-stu-id="730ea-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="730ea-193">Se sono stati ignorati tutti i passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si utilizza il dominio per i Blog, i carrelli o altri servizi, sono necessari ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="730ea-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="730ea-194">In caso contrario, questa modifica potrebbe causare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o il sito Web corrente inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="730ea-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="730ea-195">Ecco, ad esempio, alcune altre operazioni aggiuntive che potrebbero essere necessarie per l'hosting della posta elettronica e dei siti Web:</span><span class="sxs-lookup"><span data-stu-id="730ea-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="730ea-196">Spostare tutti gli indirizzi di posta elettronica che usano il dominio in Office 365 prima di modificare i record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="730ea-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="730ea-197">Si desidera aggiungere un dominio attualmente utilizzato con un indirizzo del sito Web, ad esempio www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="730ea-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="730ea-198">È possibile eseguire i passaggi seguenti quando si aggiunge il dominio per mantenere ospitato il sito Web in cui è ospitato il sito, per consentire agli utenti di accedere al sito Web dopo aver modificato i record NS del dominio in modo che puntino a Office 365.</span><span class="sxs-lookup"><span data-stu-id="730ea-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="730ea-199">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="730ea-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="730ea-200">Nella pagina Domini selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="730ea-201">In **impostazioni DNS**selezionare **record personalizzati**e quindi fare clic **su nuovo record personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="730ea-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="730ea-202">Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="730ea-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="730ea-203">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="730ea-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="730ea-p116">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="730ea-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

