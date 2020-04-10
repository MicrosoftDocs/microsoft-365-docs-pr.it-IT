---
title: Creare record DNS in 123-reg.co.uk per Office 365
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in 123-reg.co.uk per Office 365.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211860"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="afe68-103">Creare record DNS in 123-reg.co.uk per Office 365</span><span class="sxs-lookup"><span data-stu-id="afe68-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="afe68-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="afe68-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="afe68-105">Se il provider di hosting DNS è 123-reg.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="afe68-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="afe68-106">Dopo aver aggiunto questi record in 123-reg.co.uk, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="afe68-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="afe68-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="afe68-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afe68-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe68-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="afe68-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="afe68-111">Add a TXT record for verification</span></span>
<span data-ttu-id="afe68-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="afe68-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="afe68-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="afe68-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afe68-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="afe68-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="afe68-p104">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="afe68-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="afe68-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="afe68-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="afe68-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="afe68-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="afe68-121">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="afe68-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="afe68-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="afe68-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="afe68-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="afe68-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="afe68-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="afe68-124">**Hostname**</span></span> <br/> |<span data-ttu-id="afe68-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="afe68-125">**Type**</span></span> <br/> |<span data-ttu-id="afe68-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="afe68-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="afe68-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="afe68-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="afe68-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="afe68-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="afe68-129">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="afe68-129">**Note:** This is an example.</span></span> <span data-ttu-id="afe68-130">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="afe68-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="afe68-131">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="afe68-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="afe68-132">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afe68-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="afe68-133">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="afe68-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="afe68-134">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="afe68-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="afe68-135">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="afe68-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="afe68-136">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="afe68-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="afe68-137">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="afe68-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="afe68-138">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="afe68-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="afe68-139">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="afe68-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="afe68-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe68-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="afe68-143">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="afe68-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="afe68-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="afe68-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="afe68-145">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="afe68-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="afe68-146">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="afe68-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="afe68-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="afe68-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="afe68-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="afe68-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="afe68-149">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="afe68-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="afe68-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="afe68-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="afe68-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="afe68-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="afe68-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="afe68-152">**Hostname**</span></span>|<span data-ttu-id="afe68-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="afe68-153">**Type**</span></span>|<span data-ttu-id="afe68-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="afe68-154">**Priority**</span></span>|<span data-ttu-id="afe68-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="afe68-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="afe68-156">MX</span><span class="sxs-lookup"><span data-stu-id="afe68-156">MX</span></span>  <br/> |<span data-ttu-id="afe68-157">1 </span><span class="sxs-lookup"><span data-stu-id="afe68-157">1</span></span>  <br/> <span data-ttu-id="afe68-158">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="afe68-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="afe68-159">*\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="afe68-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="afe68-161">**Nota:** ottenere il valore \<domain-key\> dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="afe68-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="afe68-162">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="afe68-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare i valori dalla tabella](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="afe68-164">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afe68-164">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="afe68-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="afe68-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Seleziona Elimina (l'icona del cestino)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="afe68-168">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="afe68-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="afe68-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="afe68-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="afe68-170">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="afe68-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="afe68-171">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="afe68-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="afe68-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="afe68-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="afe68-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="afe68-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="afe68-174">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="afe68-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="afe68-175">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="afe68-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="afe68-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="afe68-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="afe68-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="afe68-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="afe68-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="afe68-178">**Hostname**</span></span>|<span data-ttu-id="afe68-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="afe68-179">**Type**</span></span>|<span data-ttu-id="afe68-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="afe68-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="afe68-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="afe68-181">autodiscover</span></span>  <br/> |<span data-ttu-id="afe68-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="afe68-182">CNAME</span></span>  <br/> |<span data-ttu-id="afe68-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="afe68-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afe68-185">sip</span><span class="sxs-lookup"><span data-stu-id="afe68-185">sip</span></span>  <br/> |<span data-ttu-id="afe68-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="afe68-186">CNAME</span></span>  <br/> |<span data-ttu-id="afe68-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="afe68-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afe68-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="afe68-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="afe68-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="afe68-190">CNAME</span></span>  <br/> |<span data-ttu-id="afe68-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="afe68-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afe68-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="afe68-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="afe68-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="afe68-194">CNAME</span></span>  <br/> |<span data-ttu-id="afe68-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="afe68-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="afe68-196">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afe68-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="afe68-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="afe68-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="afe68-198">CNAME</span></span>  <br/> |<span data-ttu-id="afe68-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="afe68-200">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="afe68-202">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afe68-202">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="afe68-204">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="afe68-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="afe68-205">Nella sezione **Advanced DNS** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **Add** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="afe68-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="afe68-206">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="afe68-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="afe68-207">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="afe68-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="afe68-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="afe68-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afe68-209">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="afe68-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="afe68-210">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="afe68-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="afe68-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="afe68-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="afe68-212">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="afe68-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="afe68-213">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="afe68-213">Need examples?</span></span> <span data-ttu-id="afe68-214">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="afe68-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="afe68-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="afe68-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="afe68-216">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="afe68-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="afe68-217">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="afe68-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="afe68-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="afe68-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="afe68-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="afe68-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="afe68-220">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="afe68-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="afe68-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="afe68-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="afe68-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="afe68-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="afe68-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="afe68-223">**Hostname**</span></span>|<span data-ttu-id="afe68-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="afe68-224">**Type**</span></span>|<span data-ttu-id="afe68-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="afe68-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="afe68-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="afe68-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="afe68-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="afe68-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="afe68-228">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="afe68-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="afe68-230">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afe68-230">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="afe68-232">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="afe68-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="afe68-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="afe68-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="afe68-234">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="afe68-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="afe68-235">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="afe68-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="afe68-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="afe68-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="afe68-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="afe68-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="afe68-238">Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** .</span><span class="sxs-lookup"><span data-stu-id="afe68-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="afe68-239">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="afe68-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="afe68-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="afe68-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="afe68-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="afe68-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afe68-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="afe68-242">Hostname</span></span>|<span data-ttu-id="afe68-243">Type</span><span class="sxs-lookup"><span data-stu-id="afe68-243">Type</span></span>|<span data-ttu-id="afe68-244">Priority</span><span class="sxs-lookup"><span data-stu-id="afe68-244">Priority</span></span>|<span data-ttu-id="afe68-245">TTL</span><span class="sxs-lookup"><span data-stu-id="afe68-245">TTL</span></span>|<span data-ttu-id="afe68-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="afe68-246">Destination SRV</span></span>|
    |<span data-ttu-id="afe68-247">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="afe68-247">_sip._tls</span></span>|<span data-ttu-id="afe68-248">SRV</span><span class="sxs-lookup"><span data-stu-id="afe68-248">SRV</span></span>|<span data-ttu-id="afe68-249">100</span><span class="sxs-lookup"><span data-stu-id="afe68-249">100</span></span>|<span data-ttu-id="afe68-250">3600</span><span class="sxs-lookup"><span data-stu-id="afe68-250">3600</span></span>|<span data-ttu-id="afe68-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="afe68-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="afe68-253">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="afe68-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="afe68-254">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="afe68-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="afe68-255">SRV</span><span class="sxs-lookup"><span data-stu-id="afe68-255">SRV</span></span>|<span data-ttu-id="afe68-256">100</span><span class="sxs-lookup"><span data-stu-id="afe68-256">100</span></span>|<span data-ttu-id="afe68-257">3600</span><span class="sxs-lookup"><span data-stu-id="afe68-257">3600</span></span>|<span data-ttu-id="afe68-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="afe68-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="afe68-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afe68-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="afe68-260">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="afe68-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare e incollare i valori della tabella](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="afe68-262">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afe68-262">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="afe68-264">Per aggiungere l'altro record SRV:</span><span class="sxs-lookup"><span data-stu-id="afe68-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="afe68-265">Nella sezione **Advanced DNS** creare un record usando i valori della seconda riga della tabella e quindi fare di nuovo clic su **Aggiungi** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="afe68-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="afe68-p115">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="afe68-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
