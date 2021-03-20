---
title: Creare record DNS per le zone DNS di Azure
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi nelle zone DNS di Azure per Microsoft.
ms.openlocfilehash: be4baa80d0f96e92dc9dd9004054f29f12f6415b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916143"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="05bc6-103">Creare record DNS per le zone DNS di Azure</span><span class="sxs-lookup"><span data-stu-id="05bc6-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="05bc6-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="05bc6-105">Se Azure è il provider di hosting DNS, seguire i passaggi descritti in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="05bc6-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="05bc6-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="05bc6-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="05bc6-107">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="05bc6-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="05bc6-108">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="05bc6-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="05bc6-109">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="05bc6-110">Aggiungere i quattro record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="05bc6-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="05bc6-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="05bc6-112">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="05bc6-113">Dopo aver aggiunto questi record in Azure, il dominio verrà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05bc6-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05bc6-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="05bc6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="05bc6-117">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="05bc6-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="05bc6-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="05bc6-119">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="05bc6-120">Quando ti sei connesso ad Azure, hai creato un gruppo di risorse all'interno di una zona DNS e quindi hai assegnato il nome di dominio a tale gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="05bc6-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="05bc6-121">Tale nome di dominio è registrato in un registrar esterno. Azure non offre servizi di registrazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="05bc6-122">Per verificare e creare record DNS per il dominio in Microsoft, è innanzitutto necessario modificare i server dei nomi presso il registrar in modo che utilizzino i server dei nomi di Azure assegnati al gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="05bc6-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="05bc6-123">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="05bc6-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="05bc6-124">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="05bc6-125">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="05bc6-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="05bc6-126">Di seguito è riportato un esempio di server dei nomi assegnati ad Azure.</span><span class="sxs-lookup"><span data-stu-id="05bc6-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="05bc6-127">**First nameserver:** Usa il valore del server dei nomi assegnato da Azure.</span><span class="sxs-lookup"><span data-stu-id="05bc6-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="05bc6-128">**Secondo server dei nomi:** Usa il valore del server dei nomi assegnato da Azure.</span><span class="sxs-lookup"><span data-stu-id="05bc6-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="05bc6-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="05bc6-130">You should use at least two name server records.</span></span> <span data-ttu-id="05bc6-131">Se nel sito Web del registrar sono elencati altri server dei nomi, è consigliabile eliminarli.</span><span class="sxs-lookup"><span data-stu-id="05bc6-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="05bc6-132">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="05bc6-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05bc6-133">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="05bc6-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="05bc6-134">Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="05bc6-135">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="05bc6-135">Add a TXT record for verification</span></span>
<span data-ttu-id="05bc6-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="05bc6-p106">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05bc6-p107">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="05bc6-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="05bc6-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="05bc6-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="05bc6-142">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="05bc6-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="05bc6-144">Utilizzando la **barra di** ricerca nella **pagina Dashboard,** digitare zone **DNS**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="05bc6-145">Nella visualizzazione dei risultati, selezionare **zone DNS nella** **sezione** Servizi.</span><span class="sxs-lookup"><span data-stu-id="05bc6-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="05bc6-146">Dopo il reindirizzamento, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="05bc6-148">**Nell'area** Zona **DNS** della pagina Impostazioni del dominio selezionare **+ Set di record**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="05bc6-150">Nelle **caselle** del nuovo set di record nell'area Aggiungi set di record selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05bc6-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="05bc6-151">Scegliere i **valori di unità Type** e **TTL** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="05bc6-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="05bc6-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-152">**Name**</span></span>|<span data-ttu-id="05bc6-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-153">**Type**</span></span>|<span data-ttu-id="05bc6-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-154">**TTL**</span></span>|<span data-ttu-id="05bc6-155">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-155">**TTL unit**</span></span>|<span data-ttu-id="05bc6-156">**Valore**</span><span class="sxs-lookup"><span data-stu-id="05bc6-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="05bc6-157">TXT</span><span class="sxs-lookup"><span data-stu-id="05bc6-157">TXT</span></span>  <br/> |<span data-ttu-id="05bc6-158">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-158">1</span></span>  <br/> |<span data-ttu-id="05bc6-159">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-159">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="05bc6-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="05bc6-161">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-161">**Note:** This is an example.</span></span> <span data-ttu-id="05bc6-162">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="05bc6-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="05bc6-163">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="05bc6-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="05bc6-165">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="05bc6-166">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="05bc6-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="05bc6-167">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="05bc6-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="05bc6-168">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="05bc6-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="05bc6-169">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="05bc6-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="05bc6-170">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="05bc6-171">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="05bc6-172">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="05bc6-p111">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="05bc6-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="05bc6-176">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="05bc6-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="05bc6-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="05bc6-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="05bc6-179">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="05bc6-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="05bc6-181">Nell'area **Tutte le** risorse della pagina **Dashboard** selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="05bc6-183">**Nell'area** Zona **DNS** della pagina Impostazioni del dominio selezionare **+ Set di record**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="05bc6-185">Nelle **caselle** del nuovo set di record nell'area Aggiungi set di record selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05bc6-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="05bc6-186">Scegliere i **valori di unità Type** e **TTL** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="05bc6-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="05bc6-187">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-187">**Name**</span></span>|<span data-ttu-id="05bc6-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-188">**Type**</span></span>|<span data-ttu-id="05bc6-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-189">**TTL**</span></span>|<span data-ttu-id="05bc6-190">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-190">**TTL unit**</span></span>|<span data-ttu-id="05bc6-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="05bc6-191">**Preference**</span></span>|<span data-ttu-id="05bc6-192">**Mail Exchange**</span><span class="sxs-lookup"><span data-stu-id="05bc6-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="05bc6-193">MX</span><span class="sxs-lookup"><span data-stu-id="05bc6-193">MX</span></span>  <br/> |<span data-ttu-id="05bc6-194">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-194">1</span></span>  <br/> |<span data-ttu-id="05bc6-195">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-195">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-196">10  </span><span class="sxs-lookup"><span data-stu-id="05bc6-196">10</span></span>  <br/> <span data-ttu-id="05bc6-197">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="05bc6-197">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="05bc6-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="05bc6-199">**Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05bc6-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="05bc6-200">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="05bc6-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="05bc6-202">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="05bc6-204">Se nella sezione MX Records sono elencati altri record **MX,** è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="05bc6-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="05bc6-205">Innanzitutto, nell'area **della zona DNS,** selezionare il **set di record MX**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="05bc6-207">Selezionare quindi il record MX che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="05bc6-209">Selezionare il **menu di scelta rapida (...)** e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="05bc6-211">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="05bc6-213">Aggiungere i quattro record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="05bc6-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="05bc6-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="05bc6-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="05bc6-216">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="05bc6-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="05bc6-218">Nell'area **Tutte le** risorse della pagina **Dashboard** selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="05bc6-220">**Nell'area** Zona **DNS** della pagina Impostazioni del dominio selezionare **+ Set di record**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="05bc6-222">Aggiungere il primo dei quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="05bc6-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="05bc6-223">Nelle **caselle** del nuovo set di record nell'area Aggiungi set di record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05bc6-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="05bc6-224">Scegliere i **valori di unità Type** e **TTL** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="05bc6-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="05bc6-225">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-225">**Name**</span></span>|<span data-ttu-id="05bc6-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-226">**Type**</span></span>|<span data-ttu-id="05bc6-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-227">**TTL**</span></span>|<span data-ttu-id="05bc6-228">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-228">**TTL unit**</span></span>|<span data-ttu-id="05bc6-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="05bc6-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="05bc6-230">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="05bc6-230">autodiscover</span></span>  <br/> |<span data-ttu-id="05bc6-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="05bc6-231">CNAME</span></span>  <br/> |<span data-ttu-id="05bc6-232">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-232">1</span></span>  <br/> |<span data-ttu-id="05bc6-233">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-233">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="05bc6-235">sip</span><span class="sxs-lookup"><span data-stu-id="05bc6-235">sip</span></span>  <br/> |<span data-ttu-id="05bc6-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="05bc6-236">CNAME</span></span>  <br/> |<span data-ttu-id="05bc6-237">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-237">1</span></span>  <br/> |<span data-ttu-id="05bc6-238">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-238">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="05bc6-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="05bc6-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="05bc6-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="05bc6-241">CNAME</span></span>  <br/> |<span data-ttu-id="05bc6-242">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-242">1</span></span>  <br/> |<span data-ttu-id="05bc6-243">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-243">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="05bc6-246">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="05bc6-248">Aggiungere gli altri tre record CNAME.</span><span class="sxs-lookup"><span data-stu-id="05bc6-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="05bc6-249">Nell'area **zona DNS** selezionare **+ Set di record**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="05bc6-250">Nel set di record vuoto creare quindi un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo **OK** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="05bc6-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="05bc6-251">Ripetere questa procedura fino a creare tutti e quattro i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="05bc6-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="05bc6-252">(Facoltativo) Aggiungere 2 record CNAME per MDM.</span><span class="sxs-lookup"><span data-stu-id="05bc6-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05bc6-253">Se si dispone di Gestione di dispositivi mobili (MDM) per Microsoft, è necessario creare due record CNAME aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="05bc6-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="05bc6-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="05bc6-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="05bc6-255">Se non si dispone di MDM, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="05bc6-256">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-256">**Name**</span></span>|<span data-ttu-id="05bc6-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-257">**Type**</span></span>|<span data-ttu-id="05bc6-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-258">**TTL**</span></span>|<span data-ttu-id="05bc6-259">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-259">**TTL unit**</span></span>|<span data-ttu-id="05bc6-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="05bc6-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05bc6-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="05bc6-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="05bc6-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="05bc6-262">CNAME</span></span>  <br/> |<span data-ttu-id="05bc6-263">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-263">1</span></span>  <br/> |<span data-ttu-id="05bc6-264">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-264">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="05bc6-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="05bc6-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="05bc6-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="05bc6-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="05bc6-267">CNAME</span></span>  <br/> |<span data-ttu-id="05bc6-268">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-268">1</span></span>  <br/> |<span data-ttu-id="05bc6-269">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-269">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="05bc6-271">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="05bc6-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="05bc6-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="05bc6-273">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="05bc6-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="05bc6-274">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="05bc6-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="05bc6-275">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05bc6-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="05bc6-276">Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="05bc6-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="05bc6-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="05bc6-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="05bc6-278">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="05bc6-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="05bc6-280">Nell'area **Tutte le** risorse della pagina **Dashboard** selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="05bc6-282">Nell'area **della zona DNS** selezionare il set di record **TXT**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="05bc6-284">Nelle **caselle del** nuovo set di record nell'area Proprietà set di record selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05bc6-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="05bc6-285">Scegliere i **valori di unità Type** e **TTL** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="05bc6-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="05bc6-286">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-286">**Name**</span></span>|<span data-ttu-id="05bc6-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-287">**Type**</span></span>|<span data-ttu-id="05bc6-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-288">**TTL**</span></span>|<span data-ttu-id="05bc6-289">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-289">**TTL unit**</span></span>|<span data-ttu-id="05bc6-290">**Valore**</span><span class="sxs-lookup"><span data-stu-id="05bc6-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="05bc6-291">TXT</span><span class="sxs-lookup"><span data-stu-id="05bc6-291">TXT</span></span>  <br/> |<span data-ttu-id="05bc6-292">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-292">1</span></span>  <br/> |<span data-ttu-id="05bc6-293">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-293">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="05bc6-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="05bc6-295">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="05bc6-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="05bc6-297">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="05bc6-299">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="05bc6-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="05bc6-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="05bc6-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="05bc6-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="05bc6-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="05bc6-302">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="05bc6-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="05bc6-304">Nell'area **Tutte le** risorse della pagina **Dashboard** selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="05bc6-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="05bc6-306">**Nell'area** Zona **DNS** della pagina Impostazioni del dominio selezionare **+ Set di record**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="05bc6-308">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="05bc6-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="05bc6-309">Nelle **caselle** del nuovo set di record nell'area Aggiungi set di record selezionare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05bc6-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="05bc6-310">Scegliere i **valori di unità Type** e **TTL** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="05bc6-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="05bc6-311">**Nome**</span><span class="sxs-lookup"><span data-stu-id="05bc6-311">**Name**</span></span>|<span data-ttu-id="05bc6-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="05bc6-312">**Type**</span></span>|<span data-ttu-id="05bc6-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-313">**TTL**</span></span>|<span data-ttu-id="05bc6-314">**Unità TTL**</span><span class="sxs-lookup"><span data-stu-id="05bc6-314">**TTL unit**</span></span>|<span data-ttu-id="05bc6-315">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="05bc6-315">**Priority**</span></span>|<span data-ttu-id="05bc6-316">**Peso**</span><span class="sxs-lookup"><span data-stu-id="05bc6-316">**Weight**</span></span>|<span data-ttu-id="05bc6-317">**Porta**</span><span class="sxs-lookup"><span data-stu-id="05bc6-317">**Port**</span></span>|<span data-ttu-id="05bc6-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="05bc6-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="05bc6-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="05bc6-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="05bc6-320">SRV</span><span class="sxs-lookup"><span data-stu-id="05bc6-320">SRV</span></span>  <br/> |<span data-ttu-id="05bc6-321">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-321">1</span></span>  <br/> |<span data-ttu-id="05bc6-322">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-322">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-323">100</span><span class="sxs-lookup"><span data-stu-id="05bc6-323">100</span></span>  <br/> |<span data-ttu-id="05bc6-324">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-324">1</span></span>  <br/> |<span data-ttu-id="05bc6-325">443</span><span class="sxs-lookup"><span data-stu-id="05bc6-325">443</span></span>  <br/> |<span data-ttu-id="05bc6-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="05bc6-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="05bc6-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="05bc6-328">SRV</span><span class="sxs-lookup"><span data-stu-id="05bc6-328">SRV</span></span>  <br/> |<span data-ttu-id="05bc6-329">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-329">1</span></span>  <br/> |<span data-ttu-id="05bc6-330">Ore</span><span class="sxs-lookup"><span data-stu-id="05bc6-330">Hours</span></span>  <br/> |<span data-ttu-id="05bc6-331">100</span><span class="sxs-lookup"><span data-stu-id="05bc6-331">100</span></span>  <br/> |<span data-ttu-id="05bc6-332">1</span><span class="sxs-lookup"><span data-stu-id="05bc6-332">1</span></span>  <br/> |<span data-ttu-id="05bc6-333">5061</span><span class="sxs-lookup"><span data-stu-id="05bc6-333">5061</span></span>  <br/> |<span data-ttu-id="05bc6-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="05bc6-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="05bc6-336">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="05bc6-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="05bc6-338">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="05bc6-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="05bc6-339">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="05bc6-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05bc6-p120">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="05bc6-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
