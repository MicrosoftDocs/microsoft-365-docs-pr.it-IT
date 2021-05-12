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
description: Informazioni su come aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come posta elettronica e Skype for Business Online utilizzino il proprio nome di dominio.
ms.openlocfilehash: 1348beb09fcbc5c12d01dbf197b1cb1240decded
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332643"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="10983-103">Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar</span><span class="sxs-lookup"><span data-stu-id="10983-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="10983-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="10983-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="10983-105">Seguire queste istruzioni per aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come posta elettronica e Teams utilizzino il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="10983-106">A tale scopo, verificare il dominio e quindi modificare i server dei nomi del dominio in Microsoft 365 in modo che i record DNS corretti possano essere impostati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10983-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="10983-107">Seguire questa procedura se le istruzioni seguenti descrivono la situazione:</span><span class="sxs-lookup"><span data-stu-id="10983-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="10983-108">Si dispone del proprio dominio e si desidera configurarlo per l'utilizzo con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10983-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="10983-109">Si desidera Microsoft 365 gestire i record DNS.</span><span class="sxs-lookup"><span data-stu-id="10983-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="10983-110">Se si preferisce, è possibile [gestire personalmente i propri record DNS](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="10983-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="10983-111">Aggiungere un record TXT o MX a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="10983-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="10983-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="10983-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="10983-p103">È necessario creare solo uno di questi record. Il record TXT è solitamente il tipo preferito, ma non è supportato da alcuni provider di hosting DNS. In questi casi è possibile creare un record MX.</span><span class="sxs-lookup"><span data-stu-id="10983-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="10983-p104">Prima di usare il proprio dominio con Microsoft 365, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft 365 che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10983-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="10983-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="10983-119">Individuare l'area del sito Web del provider di hosting DNS in cui è possibile creare un nuovo record</span><span class="sxs-lookup"><span data-stu-id="10983-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="10983-120">Accedere al sito del provider del servizio di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="10983-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="10983-121">Scegliere il dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="10983-122">Individuare la pagina in cui è possibile modificare i record DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="10983-123">Creare il record</span><span class="sxs-lookup"><span data-stu-id="10983-123">Create the record</span></span>

<span data-ttu-id="10983-124">Eseguire una delle operazioni seguenti in base al record da creare, ossia TXT o MX:</span><span class="sxs-lookup"><span data-stu-id="10983-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="10983-125">**Se si crea un record TXT, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="10983-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10983-126">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="10983-126">**Record Type**</span></span> <br/> |<span data-ttu-id="10983-127">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="10983-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="10983-128">**Valore**</span><span class="sxs-lookup"><span data-stu-id="10983-128">**Value**</span></span> <br/> |<span data-ttu-id="10983-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10983-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="10983-130">TXT</span><span class="sxs-lookup"><span data-stu-id="10983-130">TXT</span></span>  <br/> |<span data-ttu-id="10983-131">Eseguire una delle operazioni seguenti: Digitare **@**, lasciare vuoto il campo o immettere il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="10983-132">> [!NOTE]> I requisiti di questo campo variano a seconda dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="10983-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="10983-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10983-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10983-134">> [!NOTE]> Questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="10983-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="10983-135">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10983-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="10983-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="10983-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10983-137">Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.</span><span class="sxs-lookup"><span data-stu-id="10983-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="10983-138">**Se si crea un record MX, usare questi valori:**</span><span class="sxs-lookup"><span data-stu-id="10983-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10983-139">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="10983-139">**Record Type**</span></span>|<span data-ttu-id="10983-140">**Alias** o **nome host**</span><span class="sxs-lookup"><span data-stu-id="10983-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="10983-141">**Valore**</span><span class="sxs-lookup"><span data-stu-id="10983-141">**Value**</span></span>|<span data-ttu-id="10983-142">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="10983-142">**Priority**</span></span>|<span data-ttu-id="10983-143">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10983-143">**TTL**</span></span>|
|<span data-ttu-id="10983-144">MX</span><span class="sxs-lookup"><span data-stu-id="10983-144">MX</span></span>|<span data-ttu-id="10983-145">Digitare **@** o il proprio nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="10983-146">MS=ms *XXXXXXXX* > [!NOTE]> Questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="10983-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="10983-147">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10983-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="10983-148">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="10983-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10983-149">Per **Priorità** usare una priorità più bassa rispetto a quella di qualsiasi altro record MX esistente, per impedire un conflitto con il record MX mediante il quale viene instradata la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="10983-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="10983-150">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="10983-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="10983-151">Impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via.</span><span class="sxs-lookup"><span data-stu-id="10983-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="10983-152">Salvare il record</span><span class="sxs-lookup"><span data-stu-id="10983-152">Save the record</span></span>

<span data-ttu-id="10983-153">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="10983-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="10983-154">Quando Microsoft 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="10983-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="10983-155">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="10983-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="10983-156">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="10983-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="10983-157">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="10983-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="10983-158">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="10983-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="10983-p109">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10983-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="10983-162">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="10983-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="10983-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="10983-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="10983-164">Quando si arriva all'ultimo passaggio della configurazione guidata dei domini in Microsoft 365, è rimasta un'attività.</span><span class="sxs-lookup"><span data-stu-id="10983-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="10983-165">Per configurare il dominio con i servizi di Microsoft 365, ad esempio la posta elettronica, è necessario modificare i record del server dei nomi (o NS) del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10983-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="10983-166">Quindi, poiché Microsoft 365 dns, i record DNS necessari per i servizi vengono impostati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10983-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="10983-167">È possibile aggiornare i record dei server dei nomi manualmente seguendo i passaggi eventualmente disponibili nella Guida del sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="10983-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="10983-168">Se non si ha familiarità con il DNS, contattare il supporto del registrar.</span><span class="sxs-lookup"><span data-stu-id="10983-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="10983-169">Per modificare i server dei nomi del dominio presso il sito Web del registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="10983-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="10983-170">Individuare l'area nel sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio o un'area in cui è possibile utilizzare server dei nomi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="10983-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="10983-171">Creare record del server dei nomi o modificare i record del server dei nomi esistenti in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="10983-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="10983-172">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-172">First nameserver</span></span>  <br/> |<span data-ttu-id="10983-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10983-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10983-174">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="10983-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10983-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10983-176">Terzo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="10983-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10983-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10983-178">Quarto server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="10983-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10983-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="10983-180">È meglio aggiungere tutti e quattro i record, ma se il registrar ne supporta solo **due,** aggiungere ns1.bdm.microsoftonline.com e **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="10983-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="10983-181">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="10983-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="10983-182">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft 365, vengono interessati tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="10983-183">Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si utilizza il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="10983-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="10983-184">In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="10983-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="10983-185">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="10983-186">Creare due record dei server dei nomi o modificare quelli esistenti, in modo che corrispondano ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="10983-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="10983-187">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-187">First nameserver</span></span>  <br/> |<span data-ttu-id="10983-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="10983-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="10983-189">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="10983-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="10983-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="10983-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="10983-191">È consigliabile utilizzare almeno due record del server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="10983-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="10983-192">Se sono elencati altri server dei nomi, è possibile eliminarli o modificarli in **ns3.dns.partner.microsoftonline.cn** e **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="10983-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="10983-193">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="10983-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="10983-194">Quando si modificano i record NS del dominio in modo che puntino al Office 365 gestito da 21 server dei nomiVianet, vengono interessati tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="10983-195">Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si utilizza il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="10983-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="10983-196">In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="10983-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="10983-197">Ecco, ad esempio, alcune altre operazioni aggiuntive che potrebbero essere necessarie per l'hosting della posta elettronica e dei siti Web:</span><span class="sxs-lookup"><span data-stu-id="10983-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="10983-198">Spostare tutti gli indirizzi di posta elettronica che utilizzano il dominio Microsoft 365 prima di modificare i record NS.</span><span class="sxs-lookup"><span data-stu-id="10983-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="10983-199">Si desidera aggiungere un dominio attualmente utilizzato con un indirizzo di sito Web, ad esempio www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="10983-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="10983-200">È possibile eseguire i passaggi seguenti mentre si aggiunge il dominio per mantenere il sito Web ospitato in cui il sito è ospitato ora in modo che gli utenti possano comunque accedere al sito Web dopo aver modificato i record NS del dominio in modo che puntino a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10983-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="10983-201">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="10983-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="10983-202">Nella pagina **Domini** selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="10983-203">Nella pagina dei dettagli del dominio selezionare la **scheda Record DNS.**</span><span class="sxs-lookup"><span data-stu-id="10983-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="10983-204">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="10983-204">Select **Add record**.</span></span>

5. <span data-ttu-id="10983-205">**Nell'elenco a discesa Tipo** del  riquadro Aggiungi record DNS personalizzato selezionare A **(indirizzo).**</span><span class="sxs-lookup"><span data-stu-id="10983-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="10983-206">Nella casella **Nome host o Alias** digitare **@** .</span><span class="sxs-lookup"><span data-stu-id="10983-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="10983-207">Nella casella **Indirizzo IP** digitare l'indirizzo IP statico per il sito Web in cui è attualmente ospitato.</span><span class="sxs-lookup"><span data-stu-id="10983-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="10983-208">Ad esempio, 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="10983-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="10983-209">Deve essere un indirizzo IP _statico_ per il sito Web, non un _indirizzo_ IP dinamico.</span><span class="sxs-lookup"><span data-stu-id="10983-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="10983-210">Per assicurarsi di poter ottenere un indirizzo IP statico per il sito Web pubblico, rivolgersi al sito che ospita il sito Web.</span><span class="sxs-lookup"><span data-stu-id="10983-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="10983-211">Se si desidera modificare l'impostazione TTL per il record, selezionare un nuovo intervallo di tempo nell'elenco a discesa **TTL.**</span><span class="sxs-lookup"><span data-stu-id="10983-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="10983-212">In caso contrario, andare al passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="10983-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="10983-213">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="10983-213">Select **Save**.</span></span> 
    
<span data-ttu-id="10983-214">È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="10983-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="10983-215">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="10983-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="10983-216">**Nell'elenco a discesa Tipo** del  riquadro Aggiungi record DNS personalizzato selezionare **CNAME (Alias).**</span><span class="sxs-lookup"><span data-stu-id="10983-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="10983-217">Nella casella **Nome host o Alias** digitare **www**.</span><span class="sxs-lookup"><span data-stu-id="10983-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="10983-218">Nella casella **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web.</span><span class="sxs-lookup"><span data-stu-id="10983-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="10983-219">Ad esempio, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="10983-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="10983-220">Se si desidera modificare l'impostazione TTL per il record, selezionare un nuovo intervallo di tempo nell'elenco a discesa **TTL.**</span><span class="sxs-lookup"><span data-stu-id="10983-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="10983-221">In caso contrario, andare al passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="10983-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="10983-222">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="10983-222">Select **Save**.</span></span>

<span data-ttu-id="10983-223">Dopo l'aggiornamento dei record del server dei nomi in modo che puntino a Microsoft, la configurazione del dominio è stata completata.</span><span class="sxs-lookup"><span data-stu-id="10983-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="10983-224">La posta elettronica viene instradata a Microsoft e il traffico verso l'indirizzo del sito Web continua a passare all'host del sito Web corrente."</span><span class="sxs-lookup"><span data-stu-id="10983-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="10983-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="10983-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="10983-226">Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="10983-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
