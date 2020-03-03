---
title: Creare record DNS in 1&1 IONOS per Office 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi a 1&1 IONOS per Office 365.
ms.openlocfilehash: d4ff6bea0d96402c34b1d1ae302510a6e718c38d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352057"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="e9ea9-103">Creare record DNS in 1&1 IONOS per Office 365</span><span class="sxs-lookup"><span data-stu-id="e9ea9-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="e9ea9-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e9ea9-105">Si noti che 1&1 IONOS non consente a un dominio di disporre sia di un record MX che di un record CNAME di individuazione automatica di primo livello.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="e9ea9-106">Di conseguenza, esistono dei limiti per il modo in cui è possibile configurare Exchange Online per Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="e9ea9-107">Si tratta di una soluzione alternativa, ma è consigliabile utilizzarla **solo** se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="e9ea9-108">> se nonostante questa [limitazione del servizio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) si sceglie di gestire i propri record DNS di Office 365 a 1&1 IONOS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="e9ea9-109">Dopo aver aggiunto questi record a 1&1 IONOS, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="e9ea9-110">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-p102">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e9ea9-114">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="e9ea9-114">Add a TXT record for verification</span></span>

<span data-ttu-id="e9ea9-p103">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e9ea9-119">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e9ea9-120">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9ea9-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9ea9-122">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9ea9-123">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9ea9-124">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9ea9-125">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e9ea9-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9ea9-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e9ea9-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-128">**Type**</span></span> <br/> |<span data-ttu-id="e9ea9-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-129">**Prefix**</span></span> <br/> |<span data-ttu-id="e9ea9-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="e9ea9-131">TXT</span><span class="sxs-lookup"><span data-stu-id="e9ea9-131">TXT</span></span>  <br/> |<span data-ttu-id="e9ea9-132">(Lasciare vuoto questo campo)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="e9ea9-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e9ea9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e9ea9-134">Nota: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-134">NOTE: This is an example.</span></span> <span data-ttu-id="e9ea9-135">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="e9ea9-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="e9ea9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e9ea9-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="e9ea9-138">Selezionare **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="e9ea9-139">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e9ea9-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e9ea9-141">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e9ea9-142">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e9ea9-143">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e9ea9-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e9ea9-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e9ea9-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e9ea9-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e9ea9-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="e9ea9-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e9ea9-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ea9-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e9ea9-152">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-153">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9ea9-154">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9ea9-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9ea9-156">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9ea9-157">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9ea9-158">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9ea9-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="e9ea9-160">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e9ea9-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="e9ea9-162">Se sono già presenti record MX, eliminarli selezionandone ognuno e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="e9ea9-163">Se l'elenco non include record MX, continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="e9ea9-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="e9ea9-165">Nelle caselle del record **MX 1** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e9ea9-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-166">**MX 1**</span></span>|<span data-ttu-id="e9ea9-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="e9ea9-168">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="e9ea9-169">Nota: ottenere la \<propria chiave\> di dominio dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="e9ea9-170">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="e9ea9-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e9ea9-171">10 </span><span class="sxs-lookup"><span data-stu-id="e9ea9-171">10</span></span>  <br/> <span data-ttu-id="e9ea9-172">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 e 1-Configure 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="e9ea9-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-174">Select **Save**.</span></span><br/><span data-ttu-id="e9ea9-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e9ea9-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="e9ea9-177">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e9ea9-178">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e9ea9-179">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="e9ea9-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e9ea9-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ea9-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e9ea9-181">1&1 IONOS richiede una soluzione alternativa in modo che sia possibile utilizzare un record MX insieme ai record CNAME necessari per i servizi di posta elettronica di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="e9ea9-182">In questa soluzione è necessario creare un set di sottodomini a 1&1 IONOS e assegnarli ai record CNAME.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e9ea9-183">Assicurarsi di avere almeno due sottodomini disponibili prima di avviare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="e9ea9-184">Questa soluzione è consigliata solo se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="e9ea9-185">Record CNAME di base</span><span class="sxs-lookup"><span data-stu-id="e9ea9-185">Basic CNAME records</span></span>

<span data-ttu-id="e9ea9-186">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-187">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9ea9-188">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9ea9-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9ea9-190">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9ea9-191">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="e9ea9-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="e9ea9-193">Ora creare due sottodomini e impostare un valore **Alias** per ognuno.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="e9ea9-194">(Necessario perché 1&1 IONOS supporta solo un record CNAME di primo livello, ma Office 365 richiede diversi record CNAME).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="e9ea9-195">Creare prima di tutto il sottodominio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="e9ea9-196">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="e9ea9-p113">Nella casella **Crea sottodominio** del nuovo sottodominio digitare oppure copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** viene aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="e9ea9-200">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-200">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-202">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="e9ea9-202">autodiscover</span></span>  <br/> |<span data-ttu-id="e9ea9-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="e9ea9-205">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="e9ea9-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="e9ea9-207">Nella sezione **Panoramica sottodominio** individuare il sottodominio di **individuazione automatica** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9ea9-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="e9ea9-209">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="e9ea9-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="e9ea9-211">Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="e9ea9-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="e9ea9-213">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="e9ea9-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="e9ea9-214">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-214">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-216">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="e9ea9-216">autodiscover</span></span>  <br/> |<span data-ttu-id="e9ea9-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="e9ea9-219">Selezionare la casella di controllo accanto alla dichiarazione di non responsabilità **Sono consapevole**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="e9ea9-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="e9ea9-221">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-221">Select **Save**.</span></span><br/><span data-ttu-id="e9ea9-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="e9ea9-223">Record CNAME facoltativi</span><span class="sxs-lookup"><span data-stu-id="e9ea9-223">Additional CNAME records</span></span>

<span data-ttu-id="e9ea9-p114">Gli altri record CNAME creati con la procedura seguente abilitano i servizi di Skype for Business online. Sarà necessario eseguire gli stessi passaggi completati per creare i due record CNAME in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="e9ea9-226">Creare il terzo sottodominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="e9ea9-227">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="e9ea9-p115">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="e9ea9-230">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-230">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9ea9-232">lyncdiscover</span></span>   |<span data-ttu-id="e9ea9-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="e9ea9-234">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="e9ea9-235">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="e9ea9-236">Nella sezione **Panoramica sottodominio** individuare il sottodominio **Lyncdiscover** appena creato e quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9ea9-237">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="e9ea9-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="e9ea9-239">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="e9ea9-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="e9ea9-240">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-240">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9ea9-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e9ea9-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="e9ea9-244">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="e9ea9-245">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e9ea9-246">Creare il quarto sottodominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="e9ea9-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="e9ea9-247">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="e9ea9-p116">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="e9ea9-250">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-250">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-252">sip</span><span class="sxs-lookup"><span data-stu-id="e9ea9-252">sip</span></span>  <br/> |<span data-ttu-id="e9ea9-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="e9ea9-254">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="e9ea9-255">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="e9ea9-256">Nella sezione **Panoramica sottodominio** individuare il sottodominio **SIP** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e9ea9-257">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="e9ea9-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="e9ea9-259">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="e9ea9-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="e9ea9-260">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-260">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e9ea9-262">sip</span><span class="sxs-lookup"><span data-stu-id="e9ea9-262">sip</span></span>  <br/> |<span data-ttu-id="e9ea9-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="e9ea9-264">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="e9ea9-265">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="e9ea9-266">Record CNAME necessari per MDM</span><span class="sxs-lookup"><span data-stu-id="e9ea9-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9ea9-267">Seguire la procedura usata per gli altri record CNAME, specificando però i valori disponibili nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="e9ea9-268">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-268">**Create Subdomain**</span></span>|<span data-ttu-id="e9ea9-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9ea9-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e9ea9-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e9ea9-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e9ea9-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e9ea9-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e9ea9-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e9ea9-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e9ea9-274">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e9ea9-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9ea9-275">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e9ea9-276">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e9ea9-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e9ea9-278">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e9ea9-279">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="e9ea9-279">Need examples?</span></span> <span data-ttu-id="e9ea9-280">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="e9ea9-281">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="e9ea9-282">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-283">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9ea9-284">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9ea9-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9ea9-286">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9ea9-287">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** (**v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9ea9-288">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9ea9-289">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e9ea9-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="e9ea9-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="e9ea9-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="e9ea9-293">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-293">**Type**</span></span>|<span data-ttu-id="e9ea9-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-294">**Prefix**</span></span>|<span data-ttu-id="e9ea9-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e9ea9-296">TXT</span><span class="sxs-lookup"><span data-stu-id="e9ea9-296">TXT</span></span>  <br/> |<span data-ttu-id="e9ea9-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9ea9-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e9ea9-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e9ea9-299">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Record TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="e9ea9-301">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-301">Select **Save**.</span></span><br/><span data-ttu-id="e9ea9-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="e9ea9-303">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-303">Select **Save**.</span></span><br/><span data-ttu-id="e9ea9-304">![Passaggio 2: Modificare la descrizione della regola contrassegnata con priorità alta in Outlook 2007](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="e9ea9-305">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e9ea9-306">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e9ea9-307">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="e9ea9-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="e9ea9-308">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9ea9-309">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e9ea9-310">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e9ea9-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e9ea9-312">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e9ea9-313">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e9ea9-314">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e9ea9-315">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e9ea9-316">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="e9ea9-317">Nelle caselle del nuovo record nell'area **Aggiungi record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="e9ea9-318">Scegliere i valori **Type** e **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9ea9-319">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-319">**Type**</span></span>|<span data-ttu-id="e9ea9-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-320">**Service**</span></span>|<span data-ttu-id="e9ea9-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-321">**Protocol**</span></span>|<span data-ttu-id="e9ea9-322">**Name**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-322">**Name**</span></span>|<span data-ttu-id="e9ea9-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-323">**Host**</span></span>|<span data-ttu-id="e9ea9-324">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-324">**Priority**</span></span>|<span data-ttu-id="e9ea9-325">**Peso**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-325">**Weight**</span></span>|<span data-ttu-id="e9ea9-326">**Porta**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-326">**Port**</span></span>|<span data-ttu-id="e9ea9-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9ea9-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9ea9-328">SRV</span><span class="sxs-lookup"><span data-stu-id="e9ea9-328">SRV</span></span>  <br/> |<span data-ttu-id="e9ea9-329">sip</span><span class="sxs-lookup"><span data-stu-id="e9ea9-329">sip</span></span>  <br/> |<span data-ttu-id="e9ea9-330">tls</span><span class="sxs-lookup"><span data-stu-id="e9ea9-330">tls</span></span>  <br/> |<span data-ttu-id="e9ea9-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9ea9-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e9ea9-333">100</span><span class="sxs-lookup"><span data-stu-id="e9ea9-333">100</span></span>  <br/> |<span data-ttu-id="e9ea9-334">1</span><span class="sxs-lookup"><span data-stu-id="e9ea9-334">1</span></span>  <br/> |<span data-ttu-id="e9ea9-335">443</span><span class="sxs-lookup"><span data-stu-id="e9ea9-335">443</span></span>  <br/> |<span data-ttu-id="e9ea9-336">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="e9ea9-337">SRV</span><span class="sxs-lookup"><span data-stu-id="e9ea9-337">SRV</span></span>  <br/> |<span data-ttu-id="e9ea9-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e9ea9-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="e9ea9-339">tcp</span><span class="sxs-lookup"><span data-stu-id="e9ea9-339">tcp</span></span>  <br/> |<span data-ttu-id="e9ea9-340">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e9ea9-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9ea9-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e9ea9-342">100</span><span class="sxs-lookup"><span data-stu-id="e9ea9-342">100</span></span>  <br/> |<span data-ttu-id="e9ea9-343">1</span><span class="sxs-lookup"><span data-stu-id="e9ea9-343">1</span></span>  <br/> |<span data-ttu-id="e9ea9-344">5061</span><span class="sxs-lookup"><span data-stu-id="e9ea9-344">5061</span></span>  <br/> |<span data-ttu-id="e9ea9-345">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="e9ea9-347">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-347">Select **Save**.</span></span> <br/><span data-ttu-id="e9ea9-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="e9ea9-349">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-349">Select **Save**.</span></span> <br/><span data-ttu-id="e9ea9-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="e9ea9-351">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="e9ea9-352">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e9ea9-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="e9ea9-353">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="e9ea9-354">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e9ea9-355">Nell'area **Aggiungi record** creare un record usando i valori dell'altra riga nella tabella, quindi selezionare di nuovo **Aggiungi**, **Salva**e **Sì** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="e9ea9-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e9ea9-p120">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9ea9-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
