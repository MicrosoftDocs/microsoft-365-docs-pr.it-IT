---
title: Creare record DNS in eNomCentral per Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in eNomCentral per Microsoft.
ms.openlocfilehash: 1a265f42165cd3add28b590400aa2625e098a9e6
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400486"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="b6e53-103">Creare record DNS in eNomCentral per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6e53-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="b6e53-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b6e53-105">Se il proprio provider di hosting DNS è eNomCentral, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="b6e53-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b6e53-106">Dopo aver aggiunto questi record in eNomCentral, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6e53-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="b6e53-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6e53-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b6e53-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="b6e53-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b6e53-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b6e53-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b6e53-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6e53-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b6e53-116">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6e53-116">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6e53-p104">Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b6e53-120">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b6e53-122">Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="b6e53-124">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6e53-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b6e53-125">Scegliere il valore del **tipo di record** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b6e53-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b6e53-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b6e53-126">**Host Name**</span></span> <br/> |<span data-ttu-id="b6e53-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b6e53-127">**Record Type**</span></span> <br/> |<span data-ttu-id="b6e53-128">**Indirizzo**</span><span class="sxs-lookup"><span data-stu-id="b6e53-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b6e53-129">TXT</span><span class="sxs-lookup"><span data-stu-id="b6e53-129">TXT</span></span>  <br/> |<span data-ttu-id="b6e53-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b6e53-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b6e53-131">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="b6e53-131">**Note:** This is an example.</span></span> <span data-ttu-id="b6e53-132">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b6e53-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b6e53-133">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="b6e53-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="b6e53-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-135">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="b6e53-137">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="b6e53-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b6e53-138">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="b6e53-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="b6e53-139">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="b6e53-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b6e53-140">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="b6e53-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b6e53-141">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b6e53-142">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b6e53-143">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b6e53-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6e53-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b6e53-147">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6e53-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b6e53-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b6e53-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b6e53-149">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6e53-149">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6e53-p107">Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b6e53-153">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b6e53-155">Nell'elenco a discesa **Manage Domain** scegliere **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="b6e53-157">Nell'elenco a discesa **Service Selection** scegliere **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="b6e53-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b6e53-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b6e53-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b6e53-160">**Host Name**</span></span>|<span data-ttu-id="b6e53-161">**Indirizzo**</span><span class="sxs-lookup"><span data-stu-id="b6e53-161">**Address**</span></span>|<span data-ttu-id="b6e53-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="b6e53-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="b6e53-163">*\<domain-key\>*. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b6e53-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b6e53-165">**Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6e53-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="b6e53-166">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="b6e53-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b6e53-167">10  </span><span class="sxs-lookup"><span data-stu-id="b6e53-167">10</span></span>  <br/> <span data-ttu-id="b6e53-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="b6e53-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="b6e53-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-170">Select **save**.</span></span>
    
    ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="b6e53-172">Se sono presenti altri record MX esistenti, selezionare le caselle di controllo corrispondenti per selezionarli.</span><span class="sxs-lookup"><span data-stu-id="b6e53-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="b6e53-174">Selezionare **Delete Checked**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b6e53-176">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6e53-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="b6e53-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b6e53-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b6e53-178">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6e53-178">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6e53-p109">Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b6e53-182">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b6e53-184">Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b6e53-186">Selezionare **nuova riga**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-186">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="b6e53-188">Nelle caselle dei nuovi sei record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6e53-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="b6e53-189">Scegliere il valore del **tipo di record** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b6e53-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="b6e53-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b6e53-190">**Host Name**</span></span>|<span data-ttu-id="b6e53-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b6e53-191">**Record Type**</span></span>|<span data-ttu-id="b6e53-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="b6e53-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b6e53-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b6e53-193">autodiscover</span></span>  <br/> |<span data-ttu-id="b6e53-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b6e53-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b6e53-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b6e53-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b6e53-197">sip</span><span class="sxs-lookup"><span data-stu-id="b6e53-197">sip</span></span>  <br/> |<span data-ttu-id="b6e53-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b6e53-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b6e53-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6e53-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b6e53-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b6e53-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b6e53-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b6e53-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b6e53-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6e53-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b6e53-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b6e53-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b6e53-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b6e53-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b6e53-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b6e53-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b6e53-208">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b6e53-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b6e53-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b6e53-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b6e53-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b6e53-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b6e53-212">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="b6e53-213">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-213">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b6e53-215">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="b6e53-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b6e53-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6e53-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6e53-217">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="b6e53-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b6e53-218">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b6e53-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b6e53-219">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6e53-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b6e53-220">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="b6e53-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="b6e53-221">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6e53-221">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6e53-p111">Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b6e53-225">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b6e53-227">Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b6e53-229">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6e53-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="b6e53-230">Scegliere il valore del **tipo di record** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b6e53-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="b6e53-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b6e53-231">**Host Name**</span></span>|<span data-ttu-id="b6e53-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b6e53-232">**Record Type**</span></span>|<span data-ttu-id="b6e53-233">**Indirizzo**</span><span class="sxs-lookup"><span data-stu-id="b6e53-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b6e53-234">TXT</span><span class="sxs-lookup"><span data-stu-id="b6e53-234">TXT</span></span>  <br/> |<span data-ttu-id="b6e53-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b6e53-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b6e53-236">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="b6e53-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="b6e53-238">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-238">Select **save**.</span></span>
    
    ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b6e53-240">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6e53-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b6e53-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b6e53-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b6e53-242">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b6e53-242">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6e53-p112">Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6e53-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b6e53-246">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b6e53-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b6e53-248">Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b6e53-250">A destra della **nuova riga**, selezionare **Aggiungi record SRV o SPF**.</span><span class="sxs-lookup"><span data-stu-id="b6e53-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="b6e53-252">Nelle caselle dei nuovi due record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6e53-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b6e53-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="b6e53-253">**Service**</span></span>|<span data-ttu-id="b6e53-254">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="b6e53-254">**Protocol**</span></span>|<span data-ttu-id="b6e53-255">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="b6e53-255">**Priority**</span></span>|<span data-ttu-id="b6e53-256">**Peso**</span><span class="sxs-lookup"><span data-stu-id="b6e53-256">**Weight**</span></span>|<span data-ttu-id="b6e53-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="b6e53-257">**Port**</span></span>|<span data-ttu-id="b6e53-258">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6e53-259">_sip</span><span class="sxs-lookup"><span data-stu-id="b6e53-259">_sip</span></span>  <br/> |<span data-ttu-id="b6e53-260">_tls</span><span class="sxs-lookup"><span data-stu-id="b6e53-260">_tls</span></span>  <br/> |<span data-ttu-id="b6e53-261">100</span><span class="sxs-lookup"><span data-stu-id="b6e53-261">100</span></span>  <br/> |<span data-ttu-id="b6e53-262">1 </span><span class="sxs-lookup"><span data-stu-id="b6e53-262">1</span></span>  <br/> |<span data-ttu-id="b6e53-263">443</span><span class="sxs-lookup"><span data-stu-id="b6e53-263">443</span></span>  <br/> |<span data-ttu-id="b6e53-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6e53-265">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b6e53-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b6e53-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b6e53-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="b6e53-267">_tcp</span></span>  <br/> |<span data-ttu-id="b6e53-268">100</span><span class="sxs-lookup"><span data-stu-id="b6e53-268">100</span></span>  <br/> |<span data-ttu-id="b6e53-269">1 </span><span class="sxs-lookup"><span data-stu-id="b6e53-269">1</span></span>  <br/> |<span data-ttu-id="b6e53-270">5061</span><span class="sxs-lookup"><span data-stu-id="b6e53-270">5061</span></span>  <br/> |<span data-ttu-id="b6e53-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b6e53-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6e53-272">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="b6e53-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="b6e53-274">Seleziona **Salva**</span><span class="sxs-lookup"><span data-stu-id="b6e53-274">Select **save**</span></span>
    
    ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="b6e53-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b6e53-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

