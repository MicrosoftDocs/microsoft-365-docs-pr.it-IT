---
title: Creare record DNS in 123-reg.co.uk per Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in 123-reg.co.uk per Microsoft.
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629744"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="2db10-103">Creare record DNS in 123-reg.co.uk per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2db10-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="2db10-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2db10-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2db10-105">Se il provider di hosting DNS è 123-reg.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="2db10-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2db10-106">Dopo aver aggiunto questi record in 123-reg.co.uk, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2db10-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="2db10-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="2db10-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2db10-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2db10-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2db10-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2db10-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2db10-110">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2db10-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2db10-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="2db10-111">Add a TXT record for verification</span></span>
<span data-ttu-id="2db10-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2db10-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2db10-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="2db10-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="2db10-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="2db10-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2db10-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="2db10-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2db10-p104">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2db10-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2db10-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="2db10-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2db10-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="2db10-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="2db10-121">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="2db10-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="2db10-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2db10-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2db10-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2db10-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2db10-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="2db10-124">**Hostname**</span></span> <br/> |<span data-ttu-id="2db10-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="2db10-125">**Type**</span></span> <br/> |<span data-ttu-id="2db10-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="2db10-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="2db10-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="2db10-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="2db10-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2db10-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2db10-129">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="2db10-129">**Note:** This is an example.</span></span> <span data-ttu-id="2db10-130">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2db10-130">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2db10-131">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2db10-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="2db10-132">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2db10-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="2db10-133">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="2db10-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2db10-134">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="2db10-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="2db10-135">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="2db10-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2db10-136">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="2db10-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2db10-137">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="2db10-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="2db10-138">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="2db10-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="2db10-139">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="2db10-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2db10-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2db10-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2db10-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2db10-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2db10-142">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2db10-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2db10-143">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2db10-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2db10-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2db10-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2db10-145">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="2db10-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="2db10-146">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2db10-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2db10-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="2db10-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2db10-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="2db10-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="2db10-149">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="2db10-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="2db10-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2db10-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2db10-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2db10-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2db10-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="2db10-152">**Hostname**</span></span>|<span data-ttu-id="2db10-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="2db10-153">**Type**</span></span>|<span data-ttu-id="2db10-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2db10-154">**Priority**</span></span>|<span data-ttu-id="2db10-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="2db10-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2db10-156">MX</span><span class="sxs-lookup"><span data-stu-id="2db10-156">MX</span></span>  <br/> |<span data-ttu-id="2db10-157">1 </span><span class="sxs-lookup"><span data-stu-id="2db10-157">1</span></span>  <br/> <span data-ttu-id="2db10-158">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="2db10-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="2db10-159">*\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="2db10-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="2db10-161">**Nota:** Ottenere la \<propria chiave\> di dominio dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2db10-161">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="2db10-162">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2db10-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare i valori dalla tabella](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="2db10-164">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2db10-164">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="2db10-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="2db10-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Seleziona Elimina (l'icona del cestino)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2db10-168">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2db10-168">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2db10-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2db10-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="2db10-170">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="2db10-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="2db10-171">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2db10-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2db10-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="2db10-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2db10-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="2db10-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="2db10-174">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="2db10-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="2db10-175">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="2db10-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="2db10-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2db10-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2db10-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2db10-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2db10-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="2db10-178">**Hostname**</span></span>|<span data-ttu-id="2db10-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="2db10-179">**Type**</span></span>|<span data-ttu-id="2db10-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="2db10-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2db10-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2db10-181">autodiscover</span></span>  <br/> |<span data-ttu-id="2db10-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="2db10-182">CNAME</span></span>  <br/> |<span data-ttu-id="2db10-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="2db10-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2db10-185">sip</span><span class="sxs-lookup"><span data-stu-id="2db10-185">sip</span></span>  <br/> |<span data-ttu-id="2db10-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="2db10-186">CNAME</span></span>  <br/> |<span data-ttu-id="2db10-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2db10-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2db10-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2db10-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2db10-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="2db10-190">CNAME</span></span>  <br/> |<span data-ttu-id="2db10-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2db10-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2db10-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2db10-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2db10-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="2db10-194">CNAME</span></span>  <br/> |<span data-ttu-id="2db10-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="2db10-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="2db10-196">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2db10-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2db10-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2db10-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="2db10-198">CNAME</span></span>  <br/> |<span data-ttu-id="2db10-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="2db10-200">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="2db10-202">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2db10-202">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="2db10-204">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="2db10-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="2db10-205">Nella sezione **Advanced DNS** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **Add** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="2db10-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="2db10-206">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="2db10-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2db10-207">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="2db10-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2db10-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2db10-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2db10-209">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="2db10-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2db10-210">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2db10-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2db10-211">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsfot.</span><span class="sxs-lookup"><span data-stu-id="2db10-211">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="2db10-212">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="2db10-212">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="2db10-213">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="2db10-213">Need examples?</span></span> <span data-ttu-id="2db10-214">Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="2db10-214">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="2db10-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="2db10-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="2db10-216">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="2db10-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="2db10-217">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2db10-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2db10-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="2db10-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2db10-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="2db10-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="2db10-220">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="2db10-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="2db10-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2db10-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2db10-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2db10-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2db10-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="2db10-223">**Hostname**</span></span>|<span data-ttu-id="2db10-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="2db10-224">**Type**</span></span>|<span data-ttu-id="2db10-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="2db10-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2db10-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="2db10-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="2db10-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2db10-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2db10-228">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="2db10-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="2db10-230">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2db10-230">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2db10-232">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2db10-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2db10-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2db10-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2db10-234">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="2db10-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="2db10-235">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2db10-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2db10-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="2db10-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2db10-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="2db10-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="2db10-238">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="2db10-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="2db10-239">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="2db10-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="2db10-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2db10-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2db10-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2db10-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2db10-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="2db10-242">Hostname</span></span>|<span data-ttu-id="2db10-243">Type</span><span class="sxs-lookup"><span data-stu-id="2db10-243">Type</span></span>|<span data-ttu-id="2db10-244">Priority</span><span class="sxs-lookup"><span data-stu-id="2db10-244">Priority</span></span>|<span data-ttu-id="2db10-245">TTL</span><span class="sxs-lookup"><span data-stu-id="2db10-245">TTL</span></span>|<span data-ttu-id="2db10-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="2db10-246">Destination SRV</span></span>|
    |<span data-ttu-id="2db10-247">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="2db10-247">_sip._tls</span></span>|<span data-ttu-id="2db10-248">SRV</span><span class="sxs-lookup"><span data-stu-id="2db10-248">SRV</span></span>|<span data-ttu-id="2db10-249">100</span><span class="sxs-lookup"><span data-stu-id="2db10-249">100</span></span>|<span data-ttu-id="2db10-250">3600</span><span class="sxs-lookup"><span data-stu-id="2db10-250">3600</span></span>|<span data-ttu-id="2db10-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="2db10-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="2db10-253">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="2db10-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="2db10-254">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="2db10-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="2db10-255">SRV</span><span class="sxs-lookup"><span data-stu-id="2db10-255">SRV</span></span>|<span data-ttu-id="2db10-256">100</span><span class="sxs-lookup"><span data-stu-id="2db10-256">100</span></span>|<span data-ttu-id="2db10-257">3600</span><span class="sxs-lookup"><span data-stu-id="2db10-257">3600</span></span>|<span data-ttu-id="2db10-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2db10-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="2db10-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2db10-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="2db10-260">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="2db10-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare e incollare i valori della tabella](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="2db10-262">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2db10-262">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="2db10-264">Per aggiungere l'altro record SRV:</span><span class="sxs-lookup"><span data-stu-id="2db10-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="2db10-265">Nella sezione **Advanced DNS** creare un record usando i valori della seconda riga della tabella e quindi fare di nuovo clic su **Aggiungi** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="2db10-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="2db10-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2db10-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2db10-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2db10-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2db10-268">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2db10-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
