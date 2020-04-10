---
title: Creare record DNS in Crazy Domains per Office 365
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Crazy domains per Office 365.
ms.openlocfilehash: 74c9a940f8d6f52c31712357557ea8cfda76e6bb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211824"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="6c530-103">Creare record DNS in Crazy Domains per Office 365</span><span class="sxs-lookup"><span data-stu-id="6c530-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="6c530-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6c530-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6c530-105">Se il proprio provider di hosting DNS è Crazy Domains, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="6c530-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6c530-106">Dopo aver aggiunto questi record in Crazy Domains, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c530-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6c530-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6c530-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c530-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c530-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6c530-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="6c530-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6c530-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6c530-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6c530-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="6c530-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c530-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="6c530-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6c530-p104">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c530-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6c530-120">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c530-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6c530-122">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c530-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6c530-124">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6c530-126">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6c530-128">Nell'elenco a discesa **Add Record** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="6c530-130">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c530-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="6c530-132">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c530-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6c530-133">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="6c530-133">**Sub Domain**</span></span>|<span data-ttu-id="6c530-134">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="6c530-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6c530-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6c530-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6c530-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6c530-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6c530-p105">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6c530-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="6c530-141">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="6c530-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="6c530-143">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="6c530-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6c530-144">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="6c530-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6c530-145">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="6c530-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6c530-146">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="6c530-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6c530-147">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="6c530-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6c530-148">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="6c530-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6c530-149">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="6c530-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6c530-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c530-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6c530-153">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="6c530-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6c530-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6c530-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6c530-p107">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c530-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6c530-158">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c530-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6c530-160">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c530-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6c530-162">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6c530-164">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6c530-166">Nell'elenco a discesa **Add Record:** selezionare **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="6c530-168">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c530-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="6c530-170">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c530-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6c530-171">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6c530-172">**Posta per area**</span><span class="sxs-lookup"><span data-stu-id="6c530-172">**Mail For Zone**</span></span>|<span data-ttu-id="6c530-173">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="6c530-173">**Priority**</span></span>|<span data-ttu-id="6c530-174">**Assegnato al server**</span><span class="sxs-lookup"><span data-stu-id="6c530-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6c530-175">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="6c530-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6c530-176">1 </span><span class="sxs-lookup"><span data-stu-id="6c530-176">1</span></span>  <br/> <span data-ttu-id="6c530-177">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="6c530-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="6c530-178">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6c530-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6c530-179">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c530-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="6c530-180">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="6c530-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="6c530-182">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="6c530-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="6c530-184">Se nella sezione **MX record** sono presenti altri record MX, selezionare **Modify** per uno di questi record.</span><span class="sxs-lookup"><span data-stu-id="6c530-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="6c530-186">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6c530-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="6c530-188">Selezionare **Aggiorna** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="6c530-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="6c530-190">Seguire la stessa procedura per eliminare tutti gli altri record MX nell'elenco, finché non rimane solo quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="6c530-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6c530-191">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="6c530-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6c530-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6c530-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6c530-p109">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c530-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6c530-196">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c530-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6c530-198">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c530-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6c530-200">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6c530-202">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6c530-204">Nell'elenco a discesa **Add Record:** selezionare **CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="6c530-206">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c530-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="6c530-208">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="6c530-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="6c530-209">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c530-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6c530-210">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="6c530-210">**Sub Domain**</span></span>|<span data-ttu-id="6c530-211">**Alias per**</span><span class="sxs-lookup"><span data-stu-id="6c530-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6c530-212">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="6c530-212">autodiscover</span></span>  <br/> |<span data-ttu-id="6c530-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6c530-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6c530-214">sip</span><span class="sxs-lookup"><span data-stu-id="6c530-214">sip</span></span>  <br/> |<span data-ttu-id="6c530-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c530-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6c530-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6c530-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6c530-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c530-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6c530-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6c530-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6c530-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6c530-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6c530-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6c530-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6c530-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6c530-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="6c530-223">Selezionare **Aggiungi record CNAME**.</span><span class="sxs-lookup"><span data-stu-id="6c530-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="6c530-225">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="6c530-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="6c530-226">Nelle caselle del nuovo record, utilizzare i valori della riga successiva della tabella e quindi selezionare di nuovo **Aggiungi record CNAME**.</span><span class="sxs-lookup"><span data-stu-id="6c530-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="6c530-227">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="6c530-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="6c530-228">Selezionare **Update** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c530-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6c530-230">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="6c530-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6c530-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6c530-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c530-232">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="6c530-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6c530-233">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6c530-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6c530-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c530-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6c530-235">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="6c530-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6c530-p111">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c530-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6c530-239">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c530-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6c530-241">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c530-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6c530-243">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6c530-245">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6c530-247">Nell'elenco a discesa **Add Record:** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="6c530-249">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c530-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="6c530-251">Nelle caselle del nuovo record digitare oppure incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c530-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6c530-252">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="6c530-252">**Sub Domain**</span></span>|<span data-ttu-id="6c530-253">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="6c530-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6c530-254">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="6c530-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6c530-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6c530-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6c530-256">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="6c530-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="6c530-258">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="6c530-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6c530-260">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="6c530-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6c530-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6c530-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6c530-p112">Per iniziare, passare alla propria pagina dei domini su Crazy Domains usando [questo collegamento](https://manage.crazydomains.com/members/domains/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c530-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6c530-265">Nella sezione **My account** selezionare **Domains**.</span><span class="sxs-lookup"><span data-stu-id="6c530-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6c530-267">Nella sezione **Domain** della pagina Domain **names** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="6c530-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6c530-269">Nella sezione **impostazioni DNS** selezionare l'icona dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c530-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6c530-271">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6c530-273">Nell'elenco a discesa **Add Record:** selezionare **SRV Record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="6c530-275">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c530-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="6c530-277">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="6c530-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="6c530-278">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6c530-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6c530-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6c530-279">**Record Type**</span></span>|<span data-ttu-id="6c530-280">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="6c530-280">**Sub Domain**</span></span>|<span data-ttu-id="6c530-281">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="6c530-281">**Priority**</span></span>|<span data-ttu-id="6c530-282">**Peso**</span><span class="sxs-lookup"><span data-stu-id="6c530-282">**Weight**</span></span>|<span data-ttu-id="6c530-283">**Porta**</span><span class="sxs-lookup"><span data-stu-id="6c530-283">**Port**</span></span>|<span data-ttu-id="6c530-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="6c530-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6c530-285">Record SRV</span><span class="sxs-lookup"><span data-stu-id="6c530-285">SRV Record</span></span>  <br/> |<span data-ttu-id="6c530-286">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="6c530-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="6c530-287">100</span><span class="sxs-lookup"><span data-stu-id="6c530-287">100</span></span>  <br/> |<span data-ttu-id="6c530-288">1 </span><span class="sxs-lookup"><span data-stu-id="6c530-288">1</span></span>  <br/> |<span data-ttu-id="6c530-289">443</span><span class="sxs-lookup"><span data-stu-id="6c530-289">443</span></span>  <br/> |<span data-ttu-id="6c530-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c530-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6c530-291">Record SRV</span><span class="sxs-lookup"><span data-stu-id="6c530-291">SRV Record</span></span>  <br/> |<span data-ttu-id="6c530-292">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="6c530-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6c530-293">100</span><span class="sxs-lookup"><span data-stu-id="6c530-293">100</span></span>  <br/> |<span data-ttu-id="6c530-294">1 </span><span class="sxs-lookup"><span data-stu-id="6c530-294">1</span></span>  <br/> |<span data-ttu-id="6c530-295">5061</span><span class="sxs-lookup"><span data-stu-id="6c530-295">5061</span></span>  <br/> |<span data-ttu-id="6c530-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6c530-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="6c530-298">Selezionare **Add SRV record**.</span><span class="sxs-lookup"><span data-stu-id="6c530-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="6c530-300">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="6c530-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="6c530-301">Nelle caselle del nuovo record usare i valori della seconda riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6c530-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="6c530-302">Selezionare **Update** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c530-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="6c530-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6c530-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
