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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi a 1&1 IONOS per Microsoft.
ms.openlocfilehash: 10c135d8fdc1512f0b2c1b341f3524097d5f6494
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307152"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="13600-103">Creare record DNS in 1&1 IONOS per Microsoft</span><span class="sxs-lookup"><span data-stu-id="13600-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="13600-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="13600-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="13600-105">Si noti che 1&1 IONOS non consente a un dominio di disporre sia di un record MX che di un record CNAME di individuazione automatica di primo livello.</span><span class="sxs-lookup"><span data-stu-id="13600-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="13600-106">Questo consente di limitare i modi in cui è possibile configurare Exchange Online per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13600-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="13600-107">Si tratta di una soluzione alternativa, ma è consigliabile utilizzarla **solo** se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="13600-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="13600-108">> se nonostante questa [limitazione del servizio](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) si sceglie di gestire i propri record Microsoft DNS a 1&1 IONOS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="13600-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="13600-109">Dopo aver aggiunto questi record a 1&1 IONOS, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13600-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="13600-p102">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="13600-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="13600-113">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="13600-113">Add a TXT record for verification</span></span>

<span data-ttu-id="13600-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13600-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="13600-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="13600-118">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="13600-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="13600-119">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="13600-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="13600-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="13600-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="13600-121">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="13600-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="13600-122">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="13600-123">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="13600-124">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="13600-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="13600-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="13600-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="13600-126">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="13600-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="13600-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="13600-127">**Type**</span></span> <br/> |<span data-ttu-id="13600-128">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="13600-128">**Prefix**</span></span> <br/> |<span data-ttu-id="13600-129">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="13600-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="13600-130">TXT</span><span class="sxs-lookup"><span data-stu-id="13600-130">TXT</span></span>  <br/> |<span data-ttu-id="13600-131">(Lasciare vuoto questo campo)</span><span class="sxs-lookup"><span data-stu-id="13600-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="13600-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="13600-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="13600-133">Nota: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="13600-133">NOTE: This is an example.</span></span> <span data-ttu-id="13600-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="13600-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="13600-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="13600-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="13600-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="13600-137">Selezionare **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="13600-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="13600-138">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="13600-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="13600-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="13600-140">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="13600-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="13600-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="13600-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="13600-142">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="13600-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="13600-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="13600-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="13600-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="13600-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="13600-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="13600-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="13600-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="13600-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="13600-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="13600-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="13600-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="13600-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="13600-151">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="13600-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13600-152">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="13600-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="13600-153">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="13600-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="13600-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="13600-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="13600-155">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="13600-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="13600-156">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="13600-157">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="13600-158">Nella sezione **MX Records** , nell'area **Mail Exchanger (MX record)** , selezionare **altro server di posta**.</span><span class="sxs-lookup"><span data-stu-id="13600-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="13600-159">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="13600-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="13600-160">![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="13600-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="13600-161">Se sono già presenti record MX, eliminarli selezionandone ognuno e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="13600-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="13600-162">Se l'elenco non include record MX, continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="13600-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="13600-163">![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="13600-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="13600-164">Nelle caselle del record **MX 1** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="13600-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="13600-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="13600-165">**MX 1**</span></span>|<span data-ttu-id="13600-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="13600-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="13600-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="13600-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="13600-168">Nota: ottenere il proprio \<domain-key\> account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13600-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="13600-169">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="13600-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="13600-170">10 </span><span class="sxs-lookup"><span data-stu-id="13600-170">10</span></span>  <br/> <span data-ttu-id="13600-171">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="13600-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 e 1-Configure 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="13600-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-173">Select **Save**.</span></span><br/><span data-ttu-id="13600-174">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="13600-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="13600-175">![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="13600-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="13600-176">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="13600-177">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="13600-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="13600-178">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="13600-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="13600-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="13600-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="13600-180">1&1 IONOS richiede una soluzione alternativa in modo che sia possibile utilizzare un record MX insieme ai record CNAME necessari per i servizi di posta elettronica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13600-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="13600-181">In questa soluzione è necessario creare un set di sottodomini a 1&1 IONOS e assegnarli ai record CNAME.</span><span class="sxs-lookup"><span data-stu-id="13600-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="13600-182">Assicurarsi di avere almeno due sottodomini disponibili prima di avviare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="13600-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="13600-183">Questa soluzione è consigliata solo se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="13600-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="13600-184">Record CNAME di base</span><span class="sxs-lookup"><span data-stu-id="13600-184">Basic CNAME records</span></span>

<span data-ttu-id="13600-185">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="13600-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13600-186">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="13600-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="13600-187">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="13600-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="13600-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="13600-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="13600-189">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="13600-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="13600-190">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="13600-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="13600-191">![1 &amp; 1-BP-configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="13600-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="13600-192">Ora creare due sottodomini e impostare un valore **Alias** per ognuno.</span><span class="sxs-lookup"><span data-stu-id="13600-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="13600-193">(Necessario perché 1&1 IONOS supporta solo un record CNAME di primo livello, ma Microsoft richiede diversi record CNAME).</span><span class="sxs-lookup"><span data-stu-id="13600-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="13600-194">Creare prima di tutto il sottodominio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="13600-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="13600-195">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="13600-p113">Nella casella **Crea sottodominio** del nuovo sottodominio digitare oppure copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** viene aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="13600-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="13600-199">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-199">**Create Subdomain**</span></span>|<span data-ttu-id="13600-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-201">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="13600-201">autodiscover</span></span>  <br/> |<span data-ttu-id="13600-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="13600-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="13600-204">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="13600-205">![1 &amp; 1-BP-configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="13600-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="13600-206">Nella sezione **Panoramica sottodominio** individuare il sottodominio di **individuazione automatica** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="13600-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="13600-207">![1 &amp; 1-BP-configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="13600-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="13600-208">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="13600-209">![1 &amp; 1-BP-configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="13600-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="13600-210">Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="13600-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="13600-211">![1 &amp; 1-BP-configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="13600-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="13600-212">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="13600-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="13600-213">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-213">**Create Subdomain**</span></span>|<span data-ttu-id="13600-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-215">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="13600-215">autodiscover</span></span>  <br/> |<span data-ttu-id="13600-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="13600-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="13600-218">Selezionare la casella di controllo accanto alla dichiarazione di non responsabilità **Sono consapevole**.</span><span class="sxs-lookup"><span data-stu-id="13600-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="13600-219">![1 &amp; 1-BP-configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="13600-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="13600-220">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-220">Select **Save**.</span></span><br/><span data-ttu-id="13600-221">![1 &amp; 1-BP-configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="13600-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="13600-222">Record CNAME facoltativi</span><span class="sxs-lookup"><span data-stu-id="13600-222">Additional CNAME records</span></span>

<span data-ttu-id="13600-p114">Gli altri record CNAME creati con la procedura seguente abilitano i servizi di Skype for Business online. Sarà necessario eseguire gli stessi passaggi completati per creare i due record CNAME in precedenza.</span><span class="sxs-lookup"><span data-stu-id="13600-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="13600-225">Creare il terzo sottodominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="13600-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="13600-226">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="13600-p115">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="13600-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="13600-229">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-229">**Create Subdomain**</span></span>|<span data-ttu-id="13600-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="13600-231">lyncdiscover</span></span>   |<span data-ttu-id="13600-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="13600-233">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="13600-234">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="13600-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="13600-235">Nella sezione **Panoramica sottodominio** individuare il sottodominio **Lyncdiscover** appena creato e quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="13600-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="13600-236">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="13600-237">Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="13600-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="13600-238">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="13600-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="13600-239">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-239">**Create Subdomain**</span></span>|<span data-ttu-id="13600-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="13600-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="13600-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="13600-243">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="13600-244">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="13600-245">Creare il quarto sottodominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="13600-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="13600-246">Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="13600-p116">Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="13600-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="13600-249">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-249">**Create Subdomain**</span></span>|<span data-ttu-id="13600-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-251">sip</span><span class="sxs-lookup"><span data-stu-id="13600-251">sip</span></span>  <br/> |<span data-ttu-id="13600-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="13600-253">Selezionare **Crea sottodominio**.</span><span class="sxs-lookup"><span data-stu-id="13600-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="13600-254">Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.</span><span class="sxs-lookup"><span data-stu-id="13600-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="13600-255">Nella sezione **Panoramica sottodominio** individuare il sottodominio **SIP** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio.</span><span class="sxs-lookup"><span data-stu-id="13600-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="13600-256">Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="13600-257">Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="13600-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="13600-258">Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="13600-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="13600-259">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-259">**Create Subdomain**</span></span>|<span data-ttu-id="13600-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="13600-261">sip</span><span class="sxs-lookup"><span data-stu-id="13600-261">sip</span></span>  <br/> |<span data-ttu-id="13600-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="13600-263">Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="13600-264">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="13600-265">Record CNAME necessari per MDM</span><span class="sxs-lookup"><span data-stu-id="13600-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13600-266">Seguire la procedura usata per gli altri record CNAME, specificando però i valori disponibili nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="13600-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="13600-267">**Crea sottodominio**</span><span class="sxs-lookup"><span data-stu-id="13600-267">**Create Subdomain**</span></span>|<span data-ttu-id="13600-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="13600-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13600-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="13600-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="13600-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="13600-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="13600-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="13600-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="13600-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="13600-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="13600-273">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="13600-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13600-274">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="13600-275">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="13600-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="13600-276">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13600-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="13600-277">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="13600-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="13600-278">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="13600-278">Need examples?</span></span> <span data-ttu-id="13600-279">Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="13600-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="13600-280">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="13600-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="13600-281">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="13600-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13600-282">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="13600-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="13600-283">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="13600-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="13600-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="13600-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="13600-285">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="13600-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="13600-286">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** (**v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="13600-287">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="13600-288">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="13600-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="13600-289">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="13600-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="13600-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="13600-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="13600-291">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="13600-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="13600-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="13600-292">**Type**</span></span>|<span data-ttu-id="13600-293">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="13600-293">**Prefix**</span></span>|<span data-ttu-id="13600-294">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="13600-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="13600-295">TXT</span><span class="sxs-lookup"><span data-stu-id="13600-295">TXT</span></span>  <br/> |<span data-ttu-id="13600-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="13600-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="13600-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="13600-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="13600-298">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="13600-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Record TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="13600-300">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-300">Select **Save**.</span></span><br/><span data-ttu-id="13600-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="13600-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="13600-302">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-302">Select **Save**.</span></span><br/><span data-ttu-id="13600-303">![Passaggio 2: Modificare la descrizione della regola contrassegnata con priorità alta in Outlook 2007](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="13600-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="13600-304">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="13600-305">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="13600-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="13600-306">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="13600-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="13600-307">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="13600-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13600-308">Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="13600-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="13600-309">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="13600-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="13600-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="13600-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="13600-311">Selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="13600-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="13600-312">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="13600-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="13600-313">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="13600-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="13600-314">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="13600-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="13600-315">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="13600-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="13600-316">Nelle caselle del nuovo record nell'area **Aggiungi record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="13600-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="13600-317">Scegliere i valori **Type** e **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="13600-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="13600-318">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13600-318">**Type**</span></span>|<span data-ttu-id="13600-319">**Service**</span><span class="sxs-lookup"><span data-stu-id="13600-319">**Service**</span></span>|<span data-ttu-id="13600-320">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="13600-320">**Protocol**</span></span>|<span data-ttu-id="13600-321">**Name**</span><span class="sxs-lookup"><span data-stu-id="13600-321">**Name**</span></span>|<span data-ttu-id="13600-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="13600-322">**Host**</span></span>|<span data-ttu-id="13600-323">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="13600-323">**Priority**</span></span>|<span data-ttu-id="13600-324">**Peso**</span><span class="sxs-lookup"><span data-stu-id="13600-324">**Weight**</span></span>|<span data-ttu-id="13600-325">**Porta**</span><span class="sxs-lookup"><span data-stu-id="13600-325">**Port**</span></span>|<span data-ttu-id="13600-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="13600-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="13600-327">SRV</span><span class="sxs-lookup"><span data-stu-id="13600-327">SRV</span></span>  <br/> |<span data-ttu-id="13600-328">sip</span><span class="sxs-lookup"><span data-stu-id="13600-328">sip</span></span>  <br/> |<span data-ttu-id="13600-329">tls</span><span class="sxs-lookup"><span data-stu-id="13600-329">tls</span></span>  <br/> |<span data-ttu-id="13600-330">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="13600-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="13600-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="13600-332">100</span><span class="sxs-lookup"><span data-stu-id="13600-332">100</span></span>  <br/> |<span data-ttu-id="13600-333">1 </span><span class="sxs-lookup"><span data-stu-id="13600-333">1</span></span>  <br/> |<span data-ttu-id="13600-334">443</span><span class="sxs-lookup"><span data-stu-id="13600-334">443</span></span>  <br/> |<span data-ttu-id="13600-335">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="13600-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="13600-336">SRV</span><span class="sxs-lookup"><span data-stu-id="13600-336">SRV</span></span>  <br/> |<span data-ttu-id="13600-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="13600-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="13600-338">tcp</span><span class="sxs-lookup"><span data-stu-id="13600-338">tcp</span></span>  <br/> |<span data-ttu-id="13600-339">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="13600-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="13600-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="13600-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="13600-341">100</span><span class="sxs-lookup"><span data-stu-id="13600-341">100</span></span>  <br/> |<span data-ttu-id="13600-342">1 </span><span class="sxs-lookup"><span data-stu-id="13600-342">1</span></span>  <br/> |<span data-ttu-id="13600-343">5061</span><span class="sxs-lookup"><span data-stu-id="13600-343">5061</span></span>  <br/> |<span data-ttu-id="13600-344">3600 (1 ora)</span><span class="sxs-lookup"><span data-stu-id="13600-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="13600-346">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-346">Select **Save**.</span></span> <br/><span data-ttu-id="13600-347">![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="13600-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="13600-348">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="13600-348">Select **Save**.</span></span> <br/><span data-ttu-id="13600-349">![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="13600-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="13600-350">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="13600-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="13600-351">![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="13600-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="13600-352">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="13600-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="13600-353">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="13600-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="13600-354">Nell'area **Aggiungi record** creare un record usando i valori dell'altra riga nella tabella, quindi selezionare di nuovo **Aggiungi**, **Salva**e **Sì** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="13600-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="13600-p120">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="13600-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
