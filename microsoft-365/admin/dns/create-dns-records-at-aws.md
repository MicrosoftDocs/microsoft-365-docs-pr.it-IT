---
title: Creare record DNS su Amazon Web Services (AWS) per Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi su Amazon Web Services (AWS) per Microsoft.
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629732"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="71132-103">Creare record DNS su Amazon Web Services (AWS) per Microsoft</span><span class="sxs-lookup"><span data-stu-id="71132-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="71132-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="71132-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="71132-105">Se AWS è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype online per le aziende e così via.</span><span class="sxs-lookup"><span data-stu-id="71132-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="71132-106">Dopo aver aggiunto questi record in AWS, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71132-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="71132-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsfot, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="71132-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="71132-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="71132-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="71132-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="71132-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="71132-110">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71132-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="71132-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="71132-111">Add a TXT record for verification</span></span>
<span data-ttu-id="71132-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="71132-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="71132-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="71132-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="71132-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="71132-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71132-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="71132-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="71132-p104">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71132-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71132-119">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="71132-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="71132-120">Nella pagina \* \* aree ospitate \* \*, nella colonna **nome dominio** , selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="71132-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="71132-121">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="71132-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="71132-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="71132-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="71132-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="71132-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="71132-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71132-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="71132-126">**Name**</span></span> <br/> |<span data-ttu-id="71132-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71132-127">**Type**</span></span> <br/> |<span data-ttu-id="71132-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="71132-128">**Alias**</span></span> <br/> |<span data-ttu-id="71132-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="71132-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="71132-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="71132-130">**Value**</span></span> <br/> |<span data-ttu-id="71132-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="71132-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="71132-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="71132-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="71132-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="71132-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="71132-134">No</span><span class="sxs-lookup"><span data-stu-id="71132-134">No</span></span>  <br/> |<span data-ttu-id="71132-135">300</span><span class="sxs-lookup"><span data-stu-id="71132-135">300</span></span>  <br/> |<span data-ttu-id="71132-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="71132-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="71132-137">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="71132-137">**Note:** This is an example.</span></span> <span data-ttu-id="71132-138">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71132-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="71132-139">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="71132-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="71132-140">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="71132-141">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="71132-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="71132-142">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="71132-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="71132-143">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="71132-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="71132-144">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="71132-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="71132-145">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="71132-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="71132-146">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="71132-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="71132-147">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="71132-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="71132-148">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="71132-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="71132-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="71132-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="71132-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="71132-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="71132-151">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71132-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="71132-152">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71132-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="71132-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="71132-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="71132-154">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="71132-154">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="71132-155">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71132-155">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71132-156">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="71132-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="71132-157">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="71132-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="71132-158">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="71132-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="71132-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="71132-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="71132-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="71132-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="71132-161">**Name**</span></span>|<span data-ttu-id="71132-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71132-162">**Type**</span></span>|<span data-ttu-id="71132-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="71132-163">**Alias**</span></span>|<span data-ttu-id="71132-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="71132-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="71132-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="71132-165">**Value**</span></span>|<span data-ttu-id="71132-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="71132-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71132-167">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="71132-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="71132-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="71132-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="71132-169">No</span><span class="sxs-lookup"><span data-stu-id="71132-169">No</span></span>  <br/> |<span data-ttu-id="71132-170">300</span><span class="sxs-lookup"><span data-stu-id="71132-170">300</span></span>  <br/> |<span data-ttu-id="71132-171">0  *\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="71132-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="71132-p109">0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="71132-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="71132-174">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="71132-175">**Nota:** Ottenere la \<propria *chiave* \> di dominio dall'account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71132-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="71132-176">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="71132-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="71132-177">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="71132-179">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="71132-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="71132-181">Se ci sono altri record MX, rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="71132-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="71132-182">AWS archivia i record MX come un set che potrebbe contenere più record.</span><span class="sxs-lookup"><span data-stu-id="71132-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="71132-183">**Non selezionare** **Elimina set di record**, in quanto verranno eliminati tutti i record MX, incluso quello appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="71132-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="71132-184">Seguire invece queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="71132-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="71132-185">Per prima cosa, seleziona il set di record MX.</span><span class="sxs-lookup"><span data-stu-id="71132-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configurazione-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="71132-187">Poi, nell'area **Edit Record Set**, eliminare ogni record MX obsoleto selezionando la voce nella casella **Value** e quindi premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="71132-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configurazione-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="71132-189">Selezionare **Salva set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configurazione-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="71132-191">Aggiungere i cinque record CNAME necessari per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71132-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="71132-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="71132-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="71132-193">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="71132-193">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="71132-194">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71132-194">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71132-195">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="71132-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="71132-196">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="71132-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="71132-197">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="71132-198">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="71132-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="71132-199">Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="71132-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="71132-200">Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="71132-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="71132-201">**Nome**</span><span class="sxs-lookup"><span data-stu-id="71132-201">**Name**</span></span>|<span data-ttu-id="71132-202">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71132-202">**Type**</span></span>|<span data-ttu-id="71132-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="71132-203">**Alias**</span></span>|<span data-ttu-id="71132-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="71132-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="71132-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="71132-205">**Value**</span></span>|<span data-ttu-id="71132-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="71132-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71132-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="71132-207">autodiscover</span></span>  <br/> |<span data-ttu-id="71132-208">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="71132-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="71132-209">No</span><span class="sxs-lookup"><span data-stu-id="71132-209">No</span></span>  <br/> |<span data-ttu-id="71132-210">300</span><span class="sxs-lookup"><span data-stu-id="71132-210">300</span></span>  <br/> |<span data-ttu-id="71132-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="71132-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="71132-212">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="71132-213">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="71132-214">sip</span><span class="sxs-lookup"><span data-stu-id="71132-214">sip</span></span>  <br/> |<span data-ttu-id="71132-215">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="71132-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="71132-216">No</span><span class="sxs-lookup"><span data-stu-id="71132-216">No</span></span>  <br/> |<span data-ttu-id="71132-217">300</span><span class="sxs-lookup"><span data-stu-id="71132-217">300</span></span>  <br/> |<span data-ttu-id="71132-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="71132-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="71132-219">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="71132-220">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="71132-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="71132-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="71132-222">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="71132-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="71132-223">No</span><span class="sxs-lookup"><span data-stu-id="71132-223">No</span></span>  <br/> |<span data-ttu-id="71132-224">300</span><span class="sxs-lookup"><span data-stu-id="71132-224">300</span></span>  <br/> |<span data-ttu-id="71132-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="71132-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="71132-226">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="71132-227">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="71132-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="71132-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="71132-229">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="71132-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="71132-230">No</span><span class="sxs-lookup"><span data-stu-id="71132-230">No</span></span>  <br/> |<span data-ttu-id="71132-231">300</span><span class="sxs-lookup"><span data-stu-id="71132-231">300</span></span>  <br/> |<span data-ttu-id="71132-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="71132-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="71132-233">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="71132-234">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="71132-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="71132-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="71132-236">CNAME - Canonical Name</span><span class="sxs-lookup"><span data-stu-id="71132-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="71132-237">No</span><span class="sxs-lookup"><span data-stu-id="71132-237">No</span></span>  <br/> |<span data-ttu-id="71132-238">300</span><span class="sxs-lookup"><span data-stu-id="71132-238">300</span></span>  <br/> |<span data-ttu-id="71132-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="71132-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="71132-240">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="71132-241">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="71132-243">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="71132-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="71132-245">Aggiungere gli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="71132-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="71132-246">Nella pagina **aree ospitate** , selezionare **Crea record set**, creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Crea** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="71132-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="71132-247">Ripetere questa procedura fino a creare tutti e cinque i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="71132-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="71132-248">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="71132-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="71132-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="71132-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="71132-250">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="71132-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="71132-251">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="71132-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="71132-252">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71132-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="71132-253">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="71132-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="71132-254">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="71132-254">Need examples?</span></span> <span data-ttu-id="71132-255">Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="71132-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="71132-256">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="71132-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="71132-257">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="71132-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="71132-258">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71132-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71132-259">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="71132-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="71132-260">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="71132-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="71132-261">Selezionare il set di record **txt** .</span><span class="sxs-lookup"><span data-stu-id="71132-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configurazione-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="71132-p115">Nell'area **Edit Record Set**, alla fine della voce corrente nella casella **Value** per il record esistente, premere INVIO per creare una nuova riga. Quindi, in questa nuova riga, sotto il valore esistente, digitare o incollare il valore della tabella seguente. Per un esempio, vedere la figura sotto la tabella.</span><span class="sxs-lookup"><span data-stu-id="71132-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="71132-265">**Value:**</span><span class="sxs-lookup"><span data-stu-id="71132-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="71132-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="71132-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="71132-p116">Le virgolette richieste dalle istruzioni visualizzate vengono specificate automaticamente. Non è necessario digitarle manualmente.  </span><span class="sxs-lookup"><span data-stu-id="71132-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="71132-269">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="71132-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="71132-271">Selezionare **Salva set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configurazione-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="71132-273">Aggiungere i due record SRV necessari per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71132-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="71132-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="71132-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="71132-275">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="71132-275">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="71132-276">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71132-276">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71132-277">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="71132-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="71132-278">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="71132-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="71132-279">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="71132-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="71132-280">Aggiungere il primo record SRV:</span><span class="sxs-lookup"><span data-stu-id="71132-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="71132-281">Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="71132-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="71132-282">Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="71132-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="71132-283">**Nome**</span><span class="sxs-lookup"><span data-stu-id="71132-283">**Name**</span></span>|<span data-ttu-id="71132-284">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71132-284">**Type**</span></span>|<span data-ttu-id="71132-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="71132-285">**Alias**</span></span>|<span data-ttu-id="71132-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="71132-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="71132-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="71132-287">**Value**</span></span>|<span data-ttu-id="71132-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="71132-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71132-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="71132-289">_sip._tls</span></span>|<span data-ttu-id="71132-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="71132-290">SRV - Service locator</span></span>|<span data-ttu-id="71132-291">No</span><span class="sxs-lookup"><span data-stu-id="71132-291">No</span></span>|<span data-ttu-id="71132-292">300</span><span class="sxs-lookup"><span data-stu-id="71132-292">300</span></span>|<span data-ttu-id="71132-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="71132-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="71132-294">**Questo valore deve terminare con un punto (.).**></span><span class="sxs-lookup"><span data-stu-id="71132-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="71132-295">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="71132-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="71132-296">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-296">Simple</span></span>|
    |<span data-ttu-id="71132-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="71132-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="71132-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="71132-298">SRV - Service locator</span></span>|<span data-ttu-id="71132-299">No</span><span class="sxs-lookup"><span data-stu-id="71132-299">No</span></span>|<span data-ttu-id="71132-300">300</span><span class="sxs-lookup"><span data-stu-id="71132-300">300</span></span>|<span data-ttu-id="71132-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="71132-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="71132-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="71132-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="71132-303">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="71132-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="71132-304">Semplice</span><span class="sxs-lookup"><span data-stu-id="71132-304">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="71132-306">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="71132-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configurazione-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="71132-308">Per aggiungere l'altro record SRV:</span><span class="sxs-lookup"><span data-stu-id="71132-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="71132-309">Nella pagina **aree ospitate** , selezionare **Crea record set**, creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Crea** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="71132-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="71132-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="71132-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="71132-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="71132-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="71132-312">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71132-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
