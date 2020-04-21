---
title: Creare record DNS in 1&1 IONOS per Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi a 1&1 IONOS per Microsoft.
ms.openlocfilehash: 9e6994b1906293cb249bf64101deaeb94a033c81
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629768"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="1fd9a-103">Creare record DNS in 1&1 IONOS per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fd9a-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="1fd9a-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1fd9a-105">Si noti che 1&1 IONOS non consente a un dominio di disporre sia di un record MX che di un record CNAME di individuazione automatica di primo livello.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="1fd9a-106">Questo consente di limitare i modi in cui è possibile configurare Exchange Online per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="1fd9a-107">Si tratta di una soluzione alternativa, ma è consigliabile utilizzarla **solo** se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="1fd9a-108">> se nonostante questa [limitazione del servizio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) si sceglie di gestire i propri record Microsoft DNS a 1&1 IONOS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="1fd9a-109">Dopo aver aggiunto questi record a 1&1 IONOS, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="1fd9a-110">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-110">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fd9a-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fd9a-113">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1fd9a-114">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="1fd9a-114">Add a TXT record for verification</span></span>

<span data-ttu-id="1fd9a-115">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-115">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="1fd9a-116">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-116">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1fd9a-119">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1fd9a-120">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1fd9a-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1fd9a-122">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1fd9a-123">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1fd9a-124">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1fd9a-125">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1fd9a-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1fd9a-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1fd9a-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-128">**Type**</span></span> <br/> |<span data-ttu-id="1fd9a-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-129">**Prefix**</span></span> <br/> |<span data-ttu-id="1fd9a-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="1fd9a-131">TXT</span><span class="sxs-lookup"><span data-stu-id="1fd9a-131">TXT</span></span>  <br/> |<span data-ttu-id="1fd9a-132">(Lasciare vuoto questo campo)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="1fd9a-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1fd9a-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1fd9a-134">Nota: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-134">NOTE: This is an example.</span></span> <span data-ttu-id="1fd9a-135">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1fd9a-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1fd9a-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="1fd9a-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="1fd9a-138">Selezionare **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="1fd9a-139">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1fd9a-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1fd9a-141">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft 365 e richiedere a Microsoft 365 di cercare il record.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="1fd9a-142">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1fd9a-143">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="1fd9a-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1fd9a-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1fd9a-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1fd9a-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1fd9a-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fd9a-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fd9a-149">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1fd9a-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fd9a-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1fd9a-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1fd9a-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1fd9a-152">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-153">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1fd9a-154">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1fd9a-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1fd9a-156">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1fd9a-157">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1fd9a-158">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1fd9a-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="1fd9a-160">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1fd9a-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="1fd9a-162">Se sono già presenti record MX, eliminarli selezionandone ognuno e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="1fd9a-163">Se l'elenco non include record MX, continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="1fd9a-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="1fd9a-165">Nelle caselle del record **MX 1** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1fd9a-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-166">**MX 1**</span></span>|<span data-ttu-id="1fd9a-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="1fd9a-168">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="1fd9a-169">Nota: ottenere la \<propria chiave\> di dominio dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-169">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="1fd9a-170">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1fd9a-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1fd9a-171">10 </span><span class="sxs-lookup"><span data-stu-id="1fd9a-171">10</span></span>  <br/> <span data-ttu-id="1fd9a-172">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 e 1-Configure 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="1fd9a-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-174">Select **Save**.</span></span><br/><span data-ttu-id="1fd9a-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1fd9a-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="1fd9a-177">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1fd9a-178">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1fd9a-179">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fd9a-179">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1fd9a-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1fd9a-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1fd9a-181">1&1 IONOS richiede una soluzione alternativa in modo che sia possibile utilizzare un record MX insieme ai record CNAME necessari per i servizi di posta elettronica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="1fd9a-182">In questa soluzione è necessario creare un set di sottodomini a 1&1 IONOS e assegnarli ai record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fd9a-183">Assicurarsi di avere almeno due sottodomini disponibili prima di avviare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="1fd9a-184">Questa soluzione è consigliata solo se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="1fd9a-185">Record CNAME di base</span><span class="sxs-lookup"><span data-stu-id="1fd9a-185">Basic CNAME records</span></span>

<span data-ttu-id="1fd9a-186">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-187">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1fd9a-188">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1fd9a-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1fd9a-190">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1fd9a-191">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="1fd9a-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="1fd9a-193">Ora creare due sottodomini e impostare un valore **Alias** per ognuno.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="1fd9a-194">(Necessario perché 1&1 IONOS supporta solo un record CNAME di primo livello, ma Microsoft richiede diversi record CNAME).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="1fd9a-195">Creare prima di tutto il sottodominio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="1fd9a-196">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="1fd9a-p113">Nella casella **Crea sottodominio** del nuovo sottodominio digitare oppure copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** viene aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="1fd9a-200">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-200">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-202">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="1fd9a-202">autodiscover</span></span>  <br/> |<span data-ttu-id="1fd9a-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="1fd9a-205">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="1fd9a-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="1fd9a-207">Nella sezione **Panoramica sottodominio** individuare il sottodominio di **individuazione automatica** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1fd9a-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="1fd9a-209">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="1fd9a-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="1fd9a-211">Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="1fd9a-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="1fd9a-213">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1fd9a-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="1fd9a-214">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-214">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-216">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="1fd9a-216">autodiscover</span></span>  <br/> |<span data-ttu-id="1fd9a-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="1fd9a-219">Selezionare la casella di controllo accanto alla dichiarazione di non responsabilità **Sono consapevole**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="1fd9a-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="1fd9a-221">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-221">Select **Save**.</span></span><br/><span data-ttu-id="1fd9a-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="1fd9a-223">Record CNAME facoltativi</span><span class="sxs-lookup"><span data-stu-id="1fd9a-223">Additional CNAME records</span></span>

<span data-ttu-id="1fd9a-p114">Gli altri record CNAME creati con la procedura seguente abilitano i servizi di Skype for Business online. Sarà necessario eseguire gli stessi passaggi completati per creare i due record CNAME in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="1fd9a-226">Creare il terzo sottodominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="1fd9a-227">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="1fd9a-p115">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="1fd9a-230">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-230">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1fd9a-232">lyncdiscover</span></span>   |<span data-ttu-id="1fd9a-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="1fd9a-234">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="1fd9a-235">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="1fd9a-236">Nella sezione **Panoramica sottodominio** individuare il sottodominio **Lyncdiscover** appena creato e quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1fd9a-237">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="1fd9a-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="1fd9a-239">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1fd9a-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="1fd9a-240">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-240">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1fd9a-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1fd9a-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="1fd9a-244">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="1fd9a-245">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1fd9a-246">Creare il quarto sottodominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="1fd9a-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="1fd9a-247">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="1fd9a-p116">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="1fd9a-250">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-250">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-252">sip</span><span class="sxs-lookup"><span data-stu-id="1fd9a-252">sip</span></span>  <br/> |<span data-ttu-id="1fd9a-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="1fd9a-254">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="1fd9a-255">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="1fd9a-256">Nella sezione **Panoramica sottodominio** individuare il sottodominio **SIP** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1fd9a-257">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="1fd9a-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="1fd9a-259">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1fd9a-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="1fd9a-260">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-260">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1fd9a-262">sip</span><span class="sxs-lookup"><span data-stu-id="1fd9a-262">sip</span></span>  <br/> |<span data-ttu-id="1fd9a-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="1fd9a-264">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="1fd9a-265">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="1fd9a-266">Record CNAME necessari per MDM</span><span class="sxs-lookup"><span data-stu-id="1fd9a-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fd9a-267">Seguire la procedura usata per gli altri record CNAME, specificando però i valori disponibili nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="1fd9a-268">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-268">**Create Subdomain**</span></span>|<span data-ttu-id="1fd9a-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fd9a-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1fd9a-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1fd9a-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1fd9a-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="1fd9a-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1fd9a-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1fd9a-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1fd9a-274">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1fd9a-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fd9a-275">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1fd9a-276">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1fd9a-277">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-277">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1fd9a-278">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-278">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1fd9a-279">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="1fd9a-279">Need examples?</span></span> <span data-ttu-id="1fd9a-280">Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-280">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="1fd9a-281">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="1fd9a-282">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-283">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1fd9a-284">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1fd9a-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1fd9a-286">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1fd9a-287">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** (**v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1fd9a-288">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1fd9a-289">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1fd9a-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="1fd9a-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="1fd9a-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="1fd9a-293">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-293">**Type**</span></span>|<span data-ttu-id="1fd9a-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-294">**Prefix**</span></span>|<span data-ttu-id="1fd9a-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1fd9a-296">TXT</span><span class="sxs-lookup"><span data-stu-id="1fd9a-296">TXT</span></span>  <br/> |<span data-ttu-id="1fd9a-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1fd9a-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1fd9a-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1fd9a-299">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Record TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="1fd9a-301">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-301">Select **Save**.</span></span><br/><span data-ttu-id="1fd9a-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="1fd9a-303">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-303">Select **Save**.</span></span><br/><span data-ttu-id="1fd9a-304">![Passaggio 2: Modificare la descrizione della regola contrassegnata con priorità alta in Outlook 2007](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="1fd9a-305">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1fd9a-306">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1fd9a-307">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fd9a-307">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="1fd9a-308">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd9a-309">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1fd9a-310">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1fd9a-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1fd9a-312">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1fd9a-313">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1fd9a-314">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1fd9a-315">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1fd9a-316">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="1fd9a-317">Nelle caselle del nuovo record nell'area **Aggiungi record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="1fd9a-318">Scegliere i valori **Type** e **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1fd9a-319">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-319">**Type**</span></span>|<span data-ttu-id="1fd9a-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-320">**Service**</span></span>|<span data-ttu-id="1fd9a-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-321">**Protocol**</span></span>|<span data-ttu-id="1fd9a-322">**Name**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-322">**Name**</span></span>|<span data-ttu-id="1fd9a-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-323">**Host**</span></span>|<span data-ttu-id="1fd9a-324">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-324">**Priority**</span></span>|<span data-ttu-id="1fd9a-325">**Peso**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-325">**Weight**</span></span>|<span data-ttu-id="1fd9a-326">**Porta**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-326">**Port**</span></span>|<span data-ttu-id="1fd9a-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1fd9a-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1fd9a-328">SRV</span><span class="sxs-lookup"><span data-stu-id="1fd9a-328">SRV</span></span>  <br/> |<span data-ttu-id="1fd9a-329">sip</span><span class="sxs-lookup"><span data-stu-id="1fd9a-329">sip</span></span>  <br/> |<span data-ttu-id="1fd9a-330">tls</span><span class="sxs-lookup"><span data-stu-id="1fd9a-330">tls</span></span>  <br/> |<span data-ttu-id="1fd9a-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1fd9a-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1fd9a-333">100</span><span class="sxs-lookup"><span data-stu-id="1fd9a-333">100</span></span>  <br/> |<span data-ttu-id="1fd9a-334">1 </span><span class="sxs-lookup"><span data-stu-id="1fd9a-334">1</span></span>  <br/> |<span data-ttu-id="1fd9a-335">443</span><span class="sxs-lookup"><span data-stu-id="1fd9a-335">443</span></span>  <br/> |<span data-ttu-id="1fd9a-336">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="1fd9a-337">SRV</span><span class="sxs-lookup"><span data-stu-id="1fd9a-337">SRV</span></span>  <br/> |<span data-ttu-id="1fd9a-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1fd9a-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="1fd9a-339">tcp</span><span class="sxs-lookup"><span data-stu-id="1fd9a-339">tcp</span></span>  <br/> |<span data-ttu-id="1fd9a-340">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1fd9a-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1fd9a-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1fd9a-342">100</span><span class="sxs-lookup"><span data-stu-id="1fd9a-342">100</span></span>  <br/> |<span data-ttu-id="1fd9a-343">1 </span><span class="sxs-lookup"><span data-stu-id="1fd9a-343">1</span></span>  <br/> |<span data-ttu-id="1fd9a-344">5061</span><span class="sxs-lookup"><span data-stu-id="1fd9a-344">5061</span></span>  <br/> |<span data-ttu-id="1fd9a-345">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="1fd9a-347">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-347">Select **Save**.</span></span> <br/><span data-ttu-id="1fd9a-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="1fd9a-349">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-349">Select **Save**.</span></span> <br/><span data-ttu-id="1fd9a-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="1fd9a-351">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="1fd9a-352">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1fd9a-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="1fd9a-353">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="1fd9a-354">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1fd9a-355">Nell'area **Aggiungi record** creare un record usando i valori dell'altra riga nella tabella, quindi selezionare di nuovo **Aggiungi**, **Salva**e **Sì** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1fd9a-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fd9a-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fd9a-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fd9a-358">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fd9a-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
