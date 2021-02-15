---
title: Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Informazioni su come aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come la posta elettronica e Skype for Business online usino il proprio nome di dominio.
ms.openlocfilehash: 492bc5d2a5f3fd9810f045e7effda1ea20fa15ed
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688250"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="8fd11-103">Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar</span><span class="sxs-lookup"><span data-stu-id="8fd11-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="8fd11-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8fd11-105">Controllare [Prima di tutto Configurare il dominio (istruzioni](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) specifiche dell'host) per vedere se sono disponibili istruzioni per il registrar.</span><span class="sxs-lookup"><span data-stu-id="8fd11-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="8fd11-106">Seguire queste istruzioni per aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come la posta elettronica e Teams usino il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="8fd11-107">A tale scopo, verificare il dominio e quindi modificare i server dei nomi del dominio in Microsoft 365 in modo che i record DNS corretti possano essere impostati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8fd11-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="8fd11-108">Seguire questa procedura se le seguenti istruzioni descrivono la propria situazione:</span><span class="sxs-lookup"><span data-stu-id="8fd11-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="8fd11-109">Si dispone di un proprio dominio e si desidera configurarlo per l'utilizzo con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fd11-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="8fd11-110">Si desidera che Microsoft 365 gesti i record DNS.</span><span class="sxs-lookup"><span data-stu-id="8fd11-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="8fd11-111">Se si preferisce, è possibile [gestire personalmente i propri record DNS](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="8fd11-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="8fd11-112">Aggiungere un record TXT o MX a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="8fd11-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="8fd11-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd11-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="8fd11-p103">È necessario creare solo uno di questi record. Il record TXT è solitamente il tipo preferito, ma non è supportato da alcuni provider di hosting DNS. In questi casi è possibile creare un record MX.</span><span class="sxs-lookup"><span data-stu-id="8fd11-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="8fd11-p104">Prima di usare il proprio dominio con Microsoft 365, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft 365 che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8fd11-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="8fd11-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="8fd11-120">Trovare l'area nel sito Web del provider di hosting DNS in cui è possibile creare un nuovo record</span><span class="sxs-lookup"><span data-stu-id="8fd11-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="8fd11-121">Accedere al sito del provider del servizio di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="8fd11-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="8fd11-122">Scegliere il dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="8fd11-123">Individuare la pagina in cui è possibile modificare i record DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="8fd11-124">Creare il record</span><span class="sxs-lookup"><span data-stu-id="8fd11-124">Create the record</span></span>

<span data-ttu-id="8fd11-125">Eseguire una delle operazioni seguenti in base al record da creare, ossia TXT o MX:</span><span class="sxs-lookup"><span data-stu-id="8fd11-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="8fd11-126">**Se si crea un record TXT, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="8fd11-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8fd11-127">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="8fd11-127">**Record Type**</span></span> <br/> |<span data-ttu-id="8fd11-128">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="8fd11-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="8fd11-129">**Valore**</span><span class="sxs-lookup"><span data-stu-id="8fd11-129">**Value**</span></span> <br/> |<span data-ttu-id="8fd11-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8fd11-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="8fd11-131">TXT</span><span class="sxs-lookup"><span data-stu-id="8fd11-131">TXT</span></span>  <br/> |<span data-ttu-id="8fd11-132">Eseguire una delle operazioni seguenti: Digitare **@**, lasciare vuoto il campo o immettere il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="8fd11-133">> [!NOTE]> I requisiti di questo campo variano a seconda dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="8fd11-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="8fd11-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8fd11-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8fd11-135">> [!NOTE]> Questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="8fd11-136">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fd11-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="8fd11-137">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8fd11-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8fd11-138">Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.</span><span class="sxs-lookup"><span data-stu-id="8fd11-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="8fd11-139">**Se si crea un record MX, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="8fd11-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8fd11-140">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="8fd11-140">**Record Type**</span></span>|<span data-ttu-id="8fd11-141">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="8fd11-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="8fd11-142">**Valore**</span><span class="sxs-lookup"><span data-stu-id="8fd11-142">**Value**</span></span>|<span data-ttu-id="8fd11-143">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="8fd11-143">**Priority**</span></span>|<span data-ttu-id="8fd11-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8fd11-144">**TTL**</span></span>|
|<span data-ttu-id="8fd11-145">MX</span><span class="sxs-lookup"><span data-stu-id="8fd11-145">MX</span></span>|<span data-ttu-id="8fd11-146">Digitare **@** o il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="8fd11-147">MS=ms *XXXXXXXX* > [!NOTE]> Questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="8fd11-148">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fd11-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="8fd11-149">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8fd11-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8fd11-150">Per **Priorità** usare una priorità più bassa rispetto a quella di qualsiasi altro record MX esistente, per impedire un conflitto con il record MX mediante il quale viene instradata la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8fd11-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="8fd11-151">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="8fd11-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="8fd11-152">Impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via.</span><span class="sxs-lookup"><span data-stu-id="8fd11-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="8fd11-153">Salvare il record</span><span class="sxs-lookup"><span data-stu-id="8fd11-153">Save the record</span></span>

<span data-ttu-id="8fd11-154">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="8fd11-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8fd11-155">Quando Microsoft 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="8fd11-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="8fd11-156">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="8fd11-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8fd11-157">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="8fd11-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="8fd11-158">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="8fd11-159">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8fd11-p109">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8fd11-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8fd11-163">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="8fd11-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="8fd11-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd11-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="8fd11-165">Quando si arriva all'ultimo passaggio della configurazione guidata dei domini in Microsoft 365, rimane un'attività.</span><span class="sxs-lookup"><span data-stu-id="8fd11-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="8fd11-166">Per configurare il dominio con i servizi di Microsoft 365, ad esempio la posta elettronica, è necessario modificare i record dei server dei nomi del dominio nel registrar in modo che puntino ai server dei nomi primario e secondario di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fd11-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="8fd11-167">Quindi, poiché Microsoft 365 ospita il DNS, i record DNS necessari per i servizi vengono impostati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8fd11-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="8fd11-168">È possibile aggiornare i record dei server dei nomi manualmente seguendo i passaggi eventualmente disponibili nella Guida del sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="8fd11-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="8fd11-169">Se non si ha familiarità con il DNS, contattare il supporto del registrar.</span><span class="sxs-lookup"><span data-stu-id="8fd11-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="8fd11-170">Per modificare i server dei nomi del dominio presso il sito Web del registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8fd11-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="8fd11-171">Individuare l'area nel sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio o un'area in cui è possibile utilizzare server dei nomi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8fd11-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="8fd11-172">Creare record del server dei nomi o modificare i record dei server dei nomi esistenti in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fd11-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8fd11-173">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-173">First nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8fd11-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8fd11-175">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8fd11-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8fd11-177">Terzo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8fd11-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8fd11-179">Quarto server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8fd11-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="8fd11-181">È meglio aggiungere tutti e quattro i record, ma se il registrar ne supporta solo **due,** aggiungere ns1.bdm.microsoftonline.com e **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="8fd11-182">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8fd11-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="8fd11-183">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Microsoft 365, vengono interessati tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8fd11-184">Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si usa il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="8fd11-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="8fd11-185">In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="8fd11-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="8fd11-186">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="8fd11-187">Creare due record dei server dei nomi o modificare quelli esistenti, in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fd11-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8fd11-188">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-188">First nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="8fd11-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="8fd11-190">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8fd11-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="8fd11-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="8fd11-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="8fd11-192">È consigliabile utilizzare almeno due record del server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8fd11-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="8fd11-193">Se sono elencati altri server dei nomi, è possibile eliminarli o modificarli in ns3.dns.partner.microsoftonline.cn **e** **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="8fd11-194">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8fd11-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="8fd11-195">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365 gestiti da 21Vianet, vengono interessati tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8fd11-196">Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si usa il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="8fd11-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="8fd11-197">In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="8fd11-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="8fd11-198">Ecco, ad esempio, alcune altre operazioni aggiuntive che potrebbero essere necessarie per l'hosting della posta elettronica e dei siti Web:</span><span class="sxs-lookup"><span data-stu-id="8fd11-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="8fd11-199">Spostare tutti gli indirizzi di posta elettronica che usano il dominio in Microsoft 365 prima di modificare i record NS.</span><span class="sxs-lookup"><span data-stu-id="8fd11-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="8fd11-200">Vuoi aggiungere un dominio attualmente usato con un indirizzo di un sito Web, ad esempio www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="8fd11-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="8fd11-201">È possibile eseguire i passaggi seguenti mentre si aggiunge il dominio per mantenere il sito Web ospitato dove il sito è ospitato ora, in modo che gli utenti possano comunque accedere al sito Web dopo aver modificato i record NS del dominio in modo che puntino a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fd11-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="8fd11-202">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="8fd11-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="8fd11-203">Nella pagina **Domini** selezionare il dominio e quindi scegliere **Record DNS.**</span><span class="sxs-lookup"><span data-stu-id="8fd11-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="8fd11-204">In **Manage DNS** selezionare Custom **Records** e quindi scegliere New **custom record.**</span><span class="sxs-lookup"><span data-stu-id="8fd11-204">Under **Manage DNS**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="8fd11-205">Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="8fd11-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="8fd11-206">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8fd11-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8fd11-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="8fd11-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8fd11-208">Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="8fd11-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
