---
title: Creare record DNS in Crazy Domains for Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Crazy Domains for Microsoft.
ms.openlocfilehash: db8979d303e4749a2a04870d277b68e5aec2e52f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629696"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="e5567-103">Creare record DNS in Crazy Domains for Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5567-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="e5567-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e5567-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e5567-105">Se il proprio provider di hosting DNS è Crazy Domains, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="e5567-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e5567-106">Dopo aver aggiunto questi record in Crazy Domains, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5567-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="e5567-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="e5567-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5567-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e5567-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e5567-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="e5567-111">Add a TXT record for verification</span></span>
<span data-ttu-id="e5567-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e5567-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e5567-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="e5567-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="e5567-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="e5567-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5567-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="e5567-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e5567-p104">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5567-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="e5567-120">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="e5567-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="e5567-122">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e5567-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="e5567-124">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="e5567-126">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="e5567-128">Nell'elenco a discesa **Add Record** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="e5567-130">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5567-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="e5567-132">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e5567-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e5567-133">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="e5567-133">**Sub Domain**</span></span>|<span data-ttu-id="e5567-134">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="e5567-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e5567-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e5567-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e5567-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e5567-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e5567-137">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="e5567-137">**Note:** This is an example.</span></span> <span data-ttu-id="e5567-138">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e5567-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e5567-139">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="e5567-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="e5567-141">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="e5567-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="e5567-143">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="e5567-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e5567-144">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="e5567-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e5567-145">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="e5567-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e5567-146">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="e5567-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e5567-147">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="e5567-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e5567-148">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="e5567-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e5567-149">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="e5567-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e5567-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e5567-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e5567-153">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5567-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e5567-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e5567-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e5567-p107">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5567-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="e5567-158">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="e5567-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="e5567-160">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e5567-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="e5567-162">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="e5567-164">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="e5567-166">Nell'elenco a discesa **Add Record:** selezionare **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="e5567-168">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5567-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="e5567-170">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e5567-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e5567-171">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e5567-172">**Posta per area**</span><span class="sxs-lookup"><span data-stu-id="e5567-172">**Mail For Zone**</span></span>|<span data-ttu-id="e5567-173">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="e5567-173">**Priority**</span></span>|<span data-ttu-id="e5567-174">**Assegnato al server**</span><span class="sxs-lookup"><span data-stu-id="e5567-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e5567-175">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="e5567-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e5567-176">1 </span><span class="sxs-lookup"><span data-stu-id="e5567-176">1</span></span>  <br/> <span data-ttu-id="e5567-177">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5567-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="e5567-178">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5567-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e5567-179">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5567-179">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="e5567-180">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="e5567-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="e5567-182">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="e5567-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="e5567-184">Se nella sezione **MX record** sono presenti altri record MX, selezionare **Modify** per uno di questi record.</span><span class="sxs-lookup"><span data-stu-id="e5567-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="e5567-186">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e5567-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="e5567-188">Selezionare **Aggiorna** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e5567-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="e5567-190">Seguire la stessa procedura per eliminare tutti gli altri record MX nell'elenco, finché non rimane solo quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e5567-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e5567-191">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5567-191">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e5567-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e5567-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e5567-p109">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5567-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="e5567-196">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="e5567-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="e5567-198">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e5567-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="e5567-200">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="e5567-202">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="e5567-204">Nell'elenco a discesa **Add Record:** selezionare **CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="e5567-206">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5567-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="e5567-208">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="e5567-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e5567-209">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e5567-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="e5567-210">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="e5567-210">**Sub Domain**</span></span>|<span data-ttu-id="e5567-211">**Alias per**</span><span class="sxs-lookup"><span data-stu-id="e5567-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e5567-212">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="e5567-212">autodiscover</span></span>  <br/> |<span data-ttu-id="e5567-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5567-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e5567-214">sip</span><span class="sxs-lookup"><span data-stu-id="e5567-214">sip</span></span>  <br/> |<span data-ttu-id="e5567-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5567-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e5567-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e5567-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e5567-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5567-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e5567-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e5567-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e5567-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e5567-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e5567-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e5567-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e5567-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5567-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="e5567-223">Selezionare **Aggiungi record CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e5567-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="e5567-225">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="e5567-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="e5567-226">Nelle caselle del nuovo record, utilizzare i valori della riga successiva della tabella e quindi selezionare di nuovo **Aggiungi record CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e5567-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="e5567-227">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="e5567-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="e5567-228">Selezionare **Update** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e5567-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e5567-230">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e5567-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e5567-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e5567-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5567-232">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="e5567-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e5567-233">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e5567-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e5567-234">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5567-234">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e5567-235">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="e5567-235">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e5567-p111">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5567-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="e5567-239">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="e5567-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="e5567-241">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e5567-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="e5567-243">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="e5567-245">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="e5567-247">Nell'elenco a discesa **Add Record:** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="e5567-249">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5567-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="e5567-251">Nelle caselle del nuovo record digitare oppure incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e5567-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e5567-252">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="e5567-252">**Sub Domain**</span></span>|<span data-ttu-id="e5567-253">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="e5567-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e5567-254">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="e5567-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e5567-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e5567-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e5567-256">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="e5567-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="e5567-258">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="e5567-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e5567-260">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5567-260">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e5567-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e5567-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e5567-p112">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5567-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="e5567-265">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="e5567-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="e5567-267">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e5567-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="e5567-269">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5567-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="e5567-271">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="e5567-273">Nell'elenco a discesa **Add Record:** selezionare **SRV Record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="e5567-275">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5567-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="e5567-277">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="e5567-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e5567-278">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e5567-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="e5567-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="e5567-279">**Record Type**</span></span>|<span data-ttu-id="e5567-280">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="e5567-280">**Sub Domain**</span></span>|<span data-ttu-id="e5567-281">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="e5567-281">**Priority**</span></span>|<span data-ttu-id="e5567-282">**Peso**</span><span class="sxs-lookup"><span data-stu-id="e5567-282">**Weight**</span></span>|<span data-ttu-id="e5567-283">**Porta**</span><span class="sxs-lookup"><span data-stu-id="e5567-283">**Port**</span></span>|<span data-ttu-id="e5567-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="e5567-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5567-285">Record SRV</span><span class="sxs-lookup"><span data-stu-id="e5567-285">SRV Record</span></span>  <br/> |<span data-ttu-id="e5567-286">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="e5567-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="e5567-287">100</span><span class="sxs-lookup"><span data-stu-id="e5567-287">100</span></span>  <br/> |<span data-ttu-id="e5567-288">1 </span><span class="sxs-lookup"><span data-stu-id="e5567-288">1</span></span>  <br/> |<span data-ttu-id="e5567-289">443</span><span class="sxs-lookup"><span data-stu-id="e5567-289">443</span></span>  <br/> |<span data-ttu-id="e5567-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5567-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e5567-291">Record SRV</span><span class="sxs-lookup"><span data-stu-id="e5567-291">SRV Record</span></span>  <br/> |<span data-ttu-id="e5567-292">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="e5567-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e5567-293">100</span><span class="sxs-lookup"><span data-stu-id="e5567-293">100</span></span>  <br/> |<span data-ttu-id="e5567-294">1 </span><span class="sxs-lookup"><span data-stu-id="e5567-294">1</span></span>  <br/> |<span data-ttu-id="e5567-295">5061</span><span class="sxs-lookup"><span data-stu-id="e5567-295">5061</span></span>  <br/> |<span data-ttu-id="e5567-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5567-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="e5567-298">Selezionare **Add SRV record**.</span><span class="sxs-lookup"><span data-stu-id="e5567-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="e5567-300">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="e5567-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e5567-301">Nelle caselle del nuovo record usare i valori della seconda riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="e5567-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="e5567-302">Selezionare **Update** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e5567-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="e5567-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e5567-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
