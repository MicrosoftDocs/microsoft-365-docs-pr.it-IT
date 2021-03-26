---
title: Creare record DNS su MyDomain per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Informazioni su come verificare il dominio e configurare record DNS per la posta elettronica, Skype for Business Online e altri servizi su MyDomain per Microsoft.
ms.openlocfilehash: f306e84509ddbea9f2e7bba598f0f490080e9f2a
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221968"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="f78a7-103">Creare record DNS su MyDomain per Microsoft</span><span class="sxs-lookup"><span data-stu-id="f78a7-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="f78a7-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="f78a7-p101">Il sito Web MyDomain non supporta i record SRV, quindi diverse funzionalità di Skype for Business Online e Outlook Web App non funzioneranno. Indipendentemente dal piano di Microsoft in uso, se si gestiscono i record DNS su MyDomain ci saranno [significative limitazioni del servizio](../setup/domains-faq.yml), quindi è consigliabile passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="f78a7-107">Se si sceglie di gestire i propri record DNS di Microsoft in MyDomain nonostante le limitazioni del servizio, seguire i passaggi di questo articolo per configurare i record DNS per la posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="f78a7-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="f78a7-108">Dopo aver aggiunto questi record a MyDomain, il domino sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f78a7-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="f78a7-p102">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f78a7-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f78a7-112">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="f78a7-112">Add a TXT record for verification</span></span>
<span data-ttu-id="f78a7-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f78a7-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f78a7-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f78a7-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f78a7-p105">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f78a7-120">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f78a7-121">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="f78a7-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f78a7-122">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="f78a7-123">Nell'elenco a discesa **Modifica** selezionare **Record TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="f78a7-124">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f78a7-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="f78a7-125">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="f78a7-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="f78a7-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f78a7-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f78a7-127">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="f78a7-127">**Note:** This is an example.</span></span> <span data-ttu-id="f78a7-128">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="f78a7-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f78a7-129">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="f78a7-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="f78a7-130">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="f78a7-131">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="f78a7-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f78a7-132">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="f78a7-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f78a7-133">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="f78a7-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f78a7-134">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="f78a7-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f78a7-135">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="f78a7-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f78a7-136">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f78a7-137">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f78a7-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f78a7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f78a7-141">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="f78a7-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f78a7-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f78a7-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f78a7-p108">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f78a7-145">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f78a7-146">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="f78a7-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f78a7-147">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="f78a7-148">Nell'elenco a discesa **Modify** selezionare **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="f78a7-150">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f78a7-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f78a7-151">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f78a7-151">**Priority**</span></span>|<span data-ttu-id="f78a7-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="f78a7-152">**Host**</span></span>|<span data-ttu-id="f78a7-153">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="f78a7-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f78a7-154">0</span><span class="sxs-lookup"><span data-stu-id="f78a7-154">0</span></span>  <br/> <span data-ttu-id="f78a7-155">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="f78a7-155">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |@  <br/> | <span data-ttu-id="f78a7-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f78a7-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f78a7-157">**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f78a7-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="f78a7-158"> > [Come trovarlo?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f78a7-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="f78a7-160">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="f78a7-162">Se sono presenti altri record MX, selezionare **Remove** nella colonna **Action** di ogni record per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f78a7-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="f78a7-164">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f78a7-166">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="f78a7-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f78a7-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f78a7-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f78a7-p110">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f78a7-170">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f78a7-171">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="f78a7-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f78a7-172">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="f78a7-173">Nell'elenco a discesa **Modify** selezionare **CNAME Alias**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="f78a7-175">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f78a7-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="f78a7-176">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f78a7-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="f78a7-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="f78a7-177">**Host**</span></span>|<span data-ttu-id="f78a7-178">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="f78a7-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f78a7-179">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="f78a7-179">autodiscover</span></span>  <br/> |<span data-ttu-id="f78a7-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f78a7-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f78a7-181">sip</span><span class="sxs-lookup"><span data-stu-id="f78a7-181">sip</span></span>  <br/> |<span data-ttu-id="f78a7-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f78a7-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f78a7-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f78a7-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f78a7-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f78a7-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f78a7-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f78a7-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f78a7-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f78a7-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f78a7-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f78a7-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f78a7-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f78a7-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="f78a7-190">Selezionare **Aggiungi** per aggiungere il primo record.</span><span class="sxs-lookup"><span data-stu-id="f78a7-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="f78a7-192">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f78a7-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="f78a7-193">Usare i valori della seconda riga della tabella precedente e quindi selezionare **Aggiungi** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="f78a7-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="f78a7-194">Aggiungere i record rimanenti allo stesso modo, usando i valori dalla terza, quarta, quinta e sesta riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="f78a7-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f78a7-195">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f78a7-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f78a7-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f78a7-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f78a7-197">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="f78a7-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f78a7-198">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="f78a7-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f78a7-199">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f78a7-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f78a7-200">Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="f78a7-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="f78a7-201">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="f78a7-201">Need examples?</span></span> <span data-ttu-id="f78a7-202">Consultare [Record Domain Name System (DNS) esterni per Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="f78a7-202">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="f78a7-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="f78a7-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="f78a7-p112">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f78a7-206">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f78a7-207">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="f78a7-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f78a7-208">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="f78a7-209">Nell'elenco a discesa **Modify** selezionare **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="f78a7-211">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f78a7-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="f78a7-212">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="f78a7-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="f78a7-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f78a7-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f78a7-214">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f78a7-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="f78a7-216">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f78a7-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f78a7-218">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="f78a7-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f78a7-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f78a7-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="f78a7-p113">Il sito Web MyDomain non supporta i record SRV, quindi diverse funzionalità di Skype for Business Online e Outlook Web App non funzioneranno. Indipendentemente dal piano di Microsoft in uso, se si gestiscono i record DNS su MyDomain ci saranno [significative limitazioni del servizio](../setup/domains-faq.yml), quindi è consigliabile passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="f78a7-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f78a7-p114">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f78a7-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
