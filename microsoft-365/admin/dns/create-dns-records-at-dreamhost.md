---
title: Creare record DNS su Dreamhost per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DreamHost per Office 365.
ms.openlocfilehash: 201452bc68f82138c08e2054452747a900ed0e6b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349487"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="3acb1-103">Creare record DNS su Dreamhost per Office 365</span><span class="sxs-lookup"><span data-stu-id="3acb1-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="3acb1-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3acb1-105">Se il proprio provider di hosting DNS è DreamHost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.</span><span class="sxs-lookup"><span data-stu-id="3acb1-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="3acb1-106">Dopo aver aggiunto questi record in DreamHost, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3acb1-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3acb1-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="3acb1-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3acb1-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acb1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3acb1-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="3acb1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3acb1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3acb1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3acb1-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3acb1-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3acb1-p104">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="3acb1-120">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="3acb1-122">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="3acb1-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3acb1-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3acb1-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3acb1-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3acb1-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3acb1-127">**Name**</span></span>|<span data-ttu-id="3acb1-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acb1-128">**Type**</span></span>|<span data-ttu-id="3acb1-129">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3acb1-129">**Value**</span></span>|<span data-ttu-id="3acb1-130">**Commento**</span><span class="sxs-lookup"><span data-stu-id="3acb1-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acb1-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3acb1-132">TXT</span><span class="sxs-lookup"><span data-stu-id="3acb1-132">TXT</span></span>  <br/> |<span data-ttu-id="3acb1-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3acb1-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3acb1-p105">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="3acb1-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="3acb1-137">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-137">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="3acb1-139">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="3acb1-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="3acb1-141">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="3acb1-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3acb1-142">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3acb1-143">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="3acb1-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3acb1-144">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="3acb1-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3acb1-145">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3acb1-146">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3acb1-147">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3acb1-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acb1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3acb1-151">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="3acb1-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3acb1-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3acb1-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3acb1-153">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3acb1-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="3acb1-p107">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="3acb1-157">Nella pagina **Dashboard** selezionare **mail**e quindi **MX personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="3acb1-159">Nella colonna **azioni** della sezione **Gestisci recapito della posta** selezionare **modifica** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="3acb1-161">Nelle caselle del nuovo record nella sezione **Custom MX Record** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3acb1-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="3acb1-162">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3acb1-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3acb1-163">Se sono presenti altri record MX esistenti, contrassegnarli come da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="3acb1-164">**Record MX (obbligatorio)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="3acb1-165">0  *\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3acb1-166">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3acb1-p108">0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="3acb1-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3acb1-169">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3acb1-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="3acb1-170">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3acb1-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DreamHost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="3acb1-172">Selezionare **modifica questo dominio per utilizzare i record MX personalizzati subito.**</span><span class="sxs-lookup"><span data-stu-id="3acb1-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="3acb1-174">Se sono presenti altri record MX, eliminarli selezionandone ognuno e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="3acb1-176">Se sono stati eliminati tutti i record, selezionare **Aggiorna i record MX personalizzati subito.**</span><span class="sxs-lookup"><span data-stu-id="3acb1-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3acb1-178">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="3acb1-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="3acb1-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3acb1-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3acb1-180">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3acb1-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="3acb1-p110">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="3acb1-184">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="3acb1-186">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="3acb1-188">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3acb1-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3acb1-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3acb1-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3acb1-191">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3acb1-191">**Name**</span></span>|<span data-ttu-id="3acb1-192">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acb1-192">**Type**</span></span>|<span data-ttu-id="3acb1-193">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3acb1-193">**Value**</span></span>|<span data-ttu-id="3acb1-194">**Commento**</span><span class="sxs-lookup"><span data-stu-id="3acb1-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acb1-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3acb1-195">autodiscover</span></span>  <br/> |<span data-ttu-id="3acb1-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acb1-196">CNAME</span></span>  <br/> |<span data-ttu-id="3acb1-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3acb1-198">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-199">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="3acb1-200">sip</span><span class="sxs-lookup"><span data-stu-id="3acb1-200">sip</span></span>  <br/> |<span data-ttu-id="3acb1-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acb1-201">CNAME</span></span>  <br/> |<span data-ttu-id="3acb1-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3acb1-203">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-204">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="3acb1-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3acb1-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3acb1-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acb1-206">CNAME</span></span>  <br/> |<span data-ttu-id="3acb1-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3acb1-208">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-209">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="3acb1-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3acb1-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3acb1-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acb1-211">CNAME</span></span>  <br/> |<span data-ttu-id="3acb1-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3acb1-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3acb1-213">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-214">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="3acb1-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3acb1-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3acb1-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="3acb1-216">CNAME</span></span>  <br/> |<span data-ttu-id="3acb1-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3acb1-218">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-219">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-219">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="3acb1-221">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="3acb1-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="3acb1-223">Se si utilizzano i due passaggi precedenti e i valori delle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3acb1-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3acb1-224">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3acb1-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3acb1-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3acb1-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3acb1-226">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="3acb1-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3acb1-227">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3acb1-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3acb1-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="3acb1-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3acb1-229">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="3acb1-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="3acb1-230">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3acb1-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="3acb1-p112">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="3acb1-234">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="3acb1-236">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="3acb1-238">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3acb1-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3acb1-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3acb1-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3acb1-241">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3acb1-241">**Name**</span></span>|<span data-ttu-id="3acb1-242">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acb1-242">**Type**</span></span>|<span data-ttu-id="3acb1-243">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3acb1-243">**Value**</span></span>|<span data-ttu-id="3acb1-244">**Commento**</span><span class="sxs-lookup"><span data-stu-id="3acb1-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acb1-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3acb1-246">TXT</span><span class="sxs-lookup"><span data-stu-id="3acb1-246">TXT</span></span>  <br/> |<span data-ttu-id="3acb1-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3acb1-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3acb1-248">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3acb1-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="3acb1-249">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-249">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="3acb1-251">Selezionare **Aggiungi record adesso.**</span><span class="sxs-lookup"><span data-stu-id="3acb1-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="3acb1-253">Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="3acb1-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3acb1-254">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="3acb1-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3acb1-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3acb1-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3acb1-256">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3acb1-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="3acb1-p113">Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3acb1-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="3acb1-260">Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="3acb1-262">Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3acb1-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="3acb1-264">Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3acb1-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="3acb1-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3acb1-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3acb1-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3acb1-267">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3acb1-267">**Name**</span></span>|<span data-ttu-id="3acb1-268">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3acb1-268">**Type**</span></span>|<span data-ttu-id="3acb1-269">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3acb1-269">**Value**</span></span>|<span data-ttu-id="3acb1-270">**Commento**</span><span class="sxs-lookup"><span data-stu-id="3acb1-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3acb1-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="3acb1-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="3acb1-272">SRV</span><span class="sxs-lookup"><span data-stu-id="3acb1-272">SRV</span></span>  <br/> |<span data-ttu-id="3acb1-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="3acb1-273">100 1 443</span></span>  <br/> <span data-ttu-id="3acb1-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3acb1-275">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-276">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="3acb1-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="3acb1-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3acb1-278">SRV</span><span class="sxs-lookup"><span data-stu-id="3acb1-278">SRV</span></span>  <br/> |<span data-ttu-id="3acb1-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="3acb1-279">100 1 5061</span></span>  <br/> <span data-ttu-id="3acb1-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3acb1-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="3acb1-281">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3acb1-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="3acb1-282">Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3acb1-282">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="3acb1-284">Selezionare **Aggiungi record adesso!**.</span><span class="sxs-lookup"><span data-stu-id="3acb1-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="3acb1-286">Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="3acb1-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3acb1-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3acb1-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
