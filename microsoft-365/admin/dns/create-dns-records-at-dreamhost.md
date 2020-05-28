---
title: Creare record DNS in DreamHost per Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DreamHost per Microsoft.
ms.openlocfilehash: 4b321138892cb4a7b5f67c37ed66f3baf0f6c45a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400510"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="6c265-103">Creare record DNS in DreamHost per Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c265-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="6c265-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6c265-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6c265-105">Se il proprio provider di hosting DNS è DreamHost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.</span><span class="sxs-lookup"><span data-stu-id="6c265-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="6c265-106">Dopo aver aggiunto questi record in DreamHost, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c265-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="6c265-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c265-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6c265-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="6c265-110">Add a TXT record for verification</span></span>
<span data-ttu-id="6c265-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6c265-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6c265-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6c265-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c265-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="6c265-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6c265-p104">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c265-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6c265-119">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c265-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6c265-121">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6c265-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6c265-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6c265-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6c265-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6c265-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6c265-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6c265-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6c265-126">**Name**</span></span>|<span data-ttu-id="6c265-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6c265-127">**Type**</span></span>|<span data-ttu-id="6c265-128">**Valore**</span><span class="sxs-lookup"><span data-stu-id="6c265-128">**Value**</span></span>|<span data-ttu-id="6c265-129">**Commento**</span><span class="sxs-lookup"><span data-stu-id="6c265-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c265-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6c265-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6c265-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6c265-131">TXT</span></span>  <br/> |<span data-ttu-id="6c265-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6c265-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6c265-133">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="6c265-133">**Note:** This is an example.</span></span> <span data-ttu-id="6c265-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6c265-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6c265-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="6c265-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6c265-136">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-136">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="6c265-138">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="6c265-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="6c265-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="6c265-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6c265-141">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="6c265-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6c265-142">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="6c265-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6c265-143">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="6c265-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6c265-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6c265-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="6c265-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6c265-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="6c265-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6c265-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c265-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6c265-150">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c265-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6c265-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6c265-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6c265-152">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6c265-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6c265-p107">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c265-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6c265-156">Nella pagina **Dashboard** selezionare **mail**e quindi **MX personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="6c265-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="6c265-158">Nella colonna **azioni** della sezione **Gestisci recapito della posta** selezionare **modifica** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="6c265-160">Nelle caselle del nuovo record nella sezione **Custom MX Record** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c265-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="6c265-161">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6c265-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6c265-162">Se sono presenti altri record MX esistenti, contrassegnarli come da eliminare.</span><span class="sxs-lookup"><span data-stu-id="6c265-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="6c265-163">**Record MX (obbligatorio)**</span><span class="sxs-lookup"><span data-stu-id="6c265-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="6c265-164">0 *\<domain-key\>* . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6c265-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="6c265-p108">0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="6c265-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="6c265-168">**Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c265-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="6c265-169">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="6c265-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DreamHost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="6c265-171">Selezionare **modifica questo dominio per utilizzare i record MX personalizzati subito.**</span><span class="sxs-lookup"><span data-stu-id="6c265-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="6c265-173">Se sono presenti altri record MX, eliminarli selezionandone ognuno e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="6c265-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="6c265-175">Se sono stati eliminati tutti i record, selezionare **Aggiorna i record MX personalizzati subito.**</span><span class="sxs-lookup"><span data-stu-id="6c265-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6c265-177">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c265-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6c265-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6c265-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6c265-179">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6c265-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6c265-p110">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c265-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6c265-183">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c265-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6c265-185">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6c265-187">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c265-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6c265-188">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6c265-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6c265-189">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6c265-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6c265-190">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6c265-190">**Name**</span></span>|<span data-ttu-id="6c265-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6c265-191">**Type**</span></span>|<span data-ttu-id="6c265-192">**Valore**</span><span class="sxs-lookup"><span data-stu-id="6c265-192">**Value**</span></span>|<span data-ttu-id="6c265-193">**Commento**</span><span class="sxs-lookup"><span data-stu-id="6c265-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c265-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6c265-194">autodiscover</span></span>  <br/> |<span data-ttu-id="6c265-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c265-195">CNAME</span></span>  <br/> |<span data-ttu-id="6c265-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="6c265-197">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-198">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6c265-199">sip</span><span class="sxs-lookup"><span data-stu-id="6c265-199">sip</span></span>  <br/> |<span data-ttu-id="6c265-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c265-200">CNAME</span></span>  <br/> |<span data-ttu-id="6c265-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6c265-202">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-203">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6c265-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6c265-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6c265-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c265-205">CNAME</span></span>  <br/> |<span data-ttu-id="6c265-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6c265-207">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-208">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6c265-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6c265-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6c265-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c265-210">CNAME</span></span>  <br/> |<span data-ttu-id="6c265-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="6c265-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="6c265-212">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-213">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6c265-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6c265-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6c265-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="6c265-215">CNAME</span></span>  <br/> |<span data-ttu-id="6c265-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="6c265-217">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-218">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-218">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="6c265-220">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="6c265-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="6c265-222">Se si utilizzano i due passaggi precedenti e i valori delle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="6c265-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6c265-223">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="6c265-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6c265-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6c265-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c265-225">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="6c265-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6c265-226">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6c265-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6c265-227">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c265-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6c265-228">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="6c265-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="6c265-229">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6c265-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6c265-p112">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c265-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6c265-233">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c265-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6c265-235">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6c265-237">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c265-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6c265-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6c265-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6c265-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6c265-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6c265-240">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6c265-240">**Name**</span></span>|<span data-ttu-id="6c265-241">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6c265-241">**Type**</span></span>|<span data-ttu-id="6c265-242">**Valore**</span><span class="sxs-lookup"><span data-stu-id="6c265-242">**Value**</span></span>|<span data-ttu-id="6c265-243">**Commento**</span><span class="sxs-lookup"><span data-stu-id="6c265-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c265-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6c265-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6c265-245">TXT</span><span class="sxs-lookup"><span data-stu-id="6c265-245">TXT</span></span>  <br/> |<span data-ttu-id="6c265-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6c265-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6c265-247">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="6c265-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6c265-248">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-248">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="6c265-250">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="6c265-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="6c265-252">Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="6c265-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6c265-253">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c265-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6c265-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6c265-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6c265-255">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6c265-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6c265-p113">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c265-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6c265-259">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c265-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6c265-261">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6c265-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6c265-263">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c265-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6c265-264">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6c265-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6c265-265">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6c265-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6c265-266">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6c265-266">**Name**</span></span>|<span data-ttu-id="6c265-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6c265-267">**Type**</span></span>|<span data-ttu-id="6c265-268">**Valore**</span><span class="sxs-lookup"><span data-stu-id="6c265-268">**Value**</span></span>|<span data-ttu-id="6c265-269">**Commento**</span><span class="sxs-lookup"><span data-stu-id="6c265-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c265-270">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="6c265-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="6c265-271">SRV</span><span class="sxs-lookup"><span data-stu-id="6c265-271">SRV</span></span>  <br/> |<span data-ttu-id="6c265-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="6c265-272">100 1 443</span></span>  <br/> <span data-ttu-id="6c265-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6c265-274">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-275">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6c265-276">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="6c265-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6c265-277">SRV</span><span class="sxs-lookup"><span data-stu-id="6c265-277">SRV</span></span>  <br/> |<span data-ttu-id="6c265-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="6c265-278">100 1 5061</span></span>  <br/> <span data-ttu-id="6c265-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6c265-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="6c265-280">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="6c265-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6c265-281">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6c265-281">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="6c265-283">Selezionare **Aggiungi record adesso!**.</span><span class="sxs-lookup"><span data-stu-id="6c265-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="6c265-285">Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="6c265-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6c265-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c265-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
