---
title: Creare record DNS su Bluehost per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi di Bluehost per Microsoft.
ms.openlocfilehash: a9de709b0981c3e74eec1a3ea0e0452d068c5ad4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658148"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="ef546-103">Creare record DNS su Bluehost per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef546-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="ef546-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="ef546-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ef546-105">Se il proprio provider di hosting DNS è Bluehost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="ef546-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ef546-106">Dopo aver aggiunto questi record a Bluehost, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef546-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="ef546-p101">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef546-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ef546-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="ef546-110">Add a TXT record for verification</span></span>
<span data-ttu-id="ef546-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ef546-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ef546-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="ef546-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef546-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="ef546-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ef546-116">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="ef546-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ef546-117">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ef546-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ef546-118">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ef546-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ef546-119">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ef546-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ef546-120">Nell'area **_Domain_name_\*_ fare clic su**\* **Gestisci record DNS** nella riga _ DNS zone editor.</span><span class="sxs-lookup"><span data-stu-id="ef546-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ef546-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ef546-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ef546-122">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef546-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef546-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ef546-123">**Host Record**</span></span> <br/> |<span data-ttu-id="ef546-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef546-124">**TTL**</span></span> <br/> |<span data-ttu-id="ef546-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef546-125">**Type**</span></span> <br/> |<span data-ttu-id="ef546-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="ef546-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="ef546-127">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-127">14400</span></span>  <br/> |<span data-ttu-id="ef546-128">TXT</span><span class="sxs-lookup"><span data-stu-id="ef546-128">TXT</span></span>  <br/> |<span data-ttu-id="ef546-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ef546-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ef546-130">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="ef546-130">**Note:** This is an example.</span></span> <span data-ttu-id="ef546-131">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ef546-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ef546-132">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ef546-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="ef546-133">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="ef546-134">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="ef546-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ef546-135">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="ef546-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="ef546-136">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="ef546-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ef546-137">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="ef546-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ef546-138">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="ef546-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ef546-139">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="ef546-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ef546-140">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="ef546-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef546-p106">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef546-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ef546-144">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef546-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ef546-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ef546-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ef546-146">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="ef546-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ef546-147">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ef546-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ef546-148">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ef546-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ef546-149">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ef546-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ef546-150">Nell'area **_Domain_name_\*_ fare clic su**\* **Gestisci record DNS** nella riga _ DNS zone editor.</span><span class="sxs-lookup"><span data-stu-id="ef546-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ef546-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ef546-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ef546-152">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef546-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ef546-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ef546-153">**Host Record**</span></span>|<span data-ttu-id="ef546-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef546-154">**TTL**</span></span>|<span data-ttu-id="ef546-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef546-155">**Type**</span></span>|<span data-ttu-id="ef546-156">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ef546-156">**Points To**</span></span>|<span data-ttu-id="ef546-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ef546-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ef546-158">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-158">14400</span></span>  <br/> |<span data-ttu-id="ef546-159">MX</span><span class="sxs-lookup"><span data-stu-id="ef546-159">MX</span></span>  <br/> | <span data-ttu-id="ef546-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef546-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="ef546-161">**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef546-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="ef546-162">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ef546-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ef546-163">0</span><span class="sxs-lookup"><span data-stu-id="ef546-163">0</span></span>  <br/> <span data-ttu-id="ef546-164">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="ef546-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Scegliere tipo dall'elenco a discesa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="ef546-166">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-166">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="ef546-168">Rimuovere eventuali altri record MX presenti nella sezione **MX (Mail Exchanger)**.</span><span class="sxs-lookup"><span data-stu-id="ef546-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="ef546-169">Per uno degli altri record MX, selezionare **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="ef546-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selezionare Elimina per ogni record MX aggiuntivo](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="ef546-171">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef546-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleziona OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="ef546-173">Usare la stessa procedura per eliminare eventuali altri record MX già presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ef546-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef546-174">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef546-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ef546-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ef546-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ef546-176">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="ef546-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ef546-177">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ef546-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ef546-178">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ef546-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ef546-179">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ef546-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ef546-180">Nell'area **_Domain_name_\*_ fare clic su**\* **Gestisci record DNS** nella riga _ DNS zone editor.</span><span class="sxs-lookup"><span data-stu-id="ef546-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ef546-181">Nella sezione **a (host)** Records individuare la riga del record di **individuazione automatica** e quindi fare clic su **Elimina** per tale riga.</span><span class="sxs-lookup"><span data-stu-id="ef546-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ef546-182">È necessario eliminare il record di **individuazione automatica** esistente  *prima*  di aggiungere il record di **individuazione automatica** richiesto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef546-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="ef546-183">Bluehost non consente di mantenere due record **autodiscover** contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ef546-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selezionare Elimina](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="ef546-185">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef546-185">Select **OK**.</span></span>
    
    ![Seleziona OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="ef546-187">Creare il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef546-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="ef546-188">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ef546-189">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef546-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ef546-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ef546-190">**Host Record**</span></span>|<span data-ttu-id="ef546-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef546-191">**TTL**</span></span>|<span data-ttu-id="ef546-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef546-192">**Type**</span></span>|<span data-ttu-id="ef546-193">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ef546-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef546-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ef546-194">autodiscover</span></span>  <br/> |<span data-ttu-id="ef546-195">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-195">14400</span></span>  <br/> |<span data-ttu-id="ef546-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef546-196">CNAME</span></span>  <br/> |<span data-ttu-id="ef546-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef546-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ef546-198">sip</span><span class="sxs-lookup"><span data-stu-id="ef546-198">sip</span></span>  <br/> |<span data-ttu-id="ef546-199">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-199">14400</span></span>  <br/> |<span data-ttu-id="ef546-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef546-200">CNAME</span></span>  <br/> |<span data-ttu-id="ef546-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef546-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef546-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ef546-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ef546-203">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-203">14400</span></span>  <br/> |<span data-ttu-id="ef546-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef546-204">CNAME</span></span>  <br/> |<span data-ttu-id="ef546-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef546-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef546-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ef546-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ef546-207">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-207">14400</span></span>  <br/> |<span data-ttu-id="ef546-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef546-208">CNAME</span></span>  <br/> |<span data-ttu-id="ef546-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ef546-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ef546-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ef546-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ef546-211">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-211">14400</span></span>  <br/> |<span data-ttu-id="ef546-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef546-212">CNAME</span></span>  <br/> |<span data-ttu-id="ef546-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ef546-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Creare il primo record CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="ef546-215">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-215">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="ef546-217">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef546-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="ef546-218">Sempre nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="ef546-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="ef546-219">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef546-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ef546-220">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ef546-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ef546-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ef546-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef546-222">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="ef546-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ef546-223">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ef546-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ef546-224">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef546-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ef546-225">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="ef546-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ef546-226">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="ef546-226">Need examples?</span></span> <span data-ttu-id="ef546-227">Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="ef546-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="ef546-228">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="ef546-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="ef546-229">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="ef546-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ef546-230">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ef546-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ef546-231">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ef546-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ef546-232">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ef546-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ef546-233">Nell'area **_Domain_name_\*_ fare clic su**\* **Gestisci record DNS** nella riga _ DNS zone editor.</span><span class="sxs-lookup"><span data-stu-id="ef546-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ef546-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ef546-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ef546-235">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef546-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="ef546-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ef546-236">**Host Record**</span></span>|<span data-ttu-id="ef546-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef546-237">**TTL**</span></span>|<span data-ttu-id="ef546-238">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef546-238">**Type**</span></span>|<span data-ttu-id="ef546-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="ef546-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ef546-240">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-240">14400</span></span>  <br/> |<span data-ttu-id="ef546-241">TXT</span><span class="sxs-lookup"><span data-stu-id="ef546-241">TXT</span></span>  <br/> |<span data-ttu-id="ef546-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ef546-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="ef546-243">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="ef546-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare il valore TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="ef546-245">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-245">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef546-247">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef546-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ef546-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ef546-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ef546-249">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="ef546-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ef546-250">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ef546-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ef546-251">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ef546-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ef546-252">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ef546-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ef546-253">Nell'area **_Domain_name_\*_ fare clic su**\* **Gestisci record DNS** nella riga _ DNS zone editor.</span><span class="sxs-lookup"><span data-stu-id="ef546-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ef546-254">Creare il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="ef546-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="ef546-255">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ef546-256">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef546-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ef546-257">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="ef546-257">**Service**</span></span>|<span data-ttu-id="ef546-258">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ef546-258">**Protocol**</span></span>|<span data-ttu-id="ef546-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="ef546-259">**Host**</span></span>|<span data-ttu-id="ef546-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef546-260">**TTL**</span></span>|<span data-ttu-id="ef546-261">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef546-261">**Type**</span></span>|<span data-ttu-id="ef546-262">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="ef546-262">**Priority**</span></span>|<span data-ttu-id="ef546-263">**Peso**</span><span class="sxs-lookup"><span data-stu-id="ef546-263">**Weight**</span></span>|<span data-ttu-id="ef546-264">**Porta**</span><span class="sxs-lookup"><span data-stu-id="ef546-264">**Port**</span></span>|<span data-ttu-id="ef546-265">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ef546-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef546-266">_sip</span><span class="sxs-lookup"><span data-stu-id="ef546-266">_sip</span></span>  <br/> |<span data-ttu-id="ef546-267">_tls</span><span class="sxs-lookup"><span data-stu-id="ef546-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="ef546-268">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-268">14400</span></span>  <br/> |<span data-ttu-id="ef546-269">SRV</span><span class="sxs-lookup"><span data-stu-id="ef546-269">SRV</span></span>  <br/> |<span data-ttu-id="ef546-270">100</span><span class="sxs-lookup"><span data-stu-id="ef546-270">100</span></span>  <br/> |<span data-ttu-id="ef546-271">1 </span><span class="sxs-lookup"><span data-stu-id="ef546-271">1</span></span>  <br/> |<span data-ttu-id="ef546-272">443</span><span class="sxs-lookup"><span data-stu-id="ef546-272">443</span></span>  <br/> |<span data-ttu-id="ef546-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef546-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef546-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ef546-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ef546-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="ef546-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="ef546-276">14400</span><span class="sxs-lookup"><span data-stu-id="ef546-276">14400</span></span>  <br/> |<span data-ttu-id="ef546-277">SRV</span><span class="sxs-lookup"><span data-stu-id="ef546-277">SRV</span></span>  <br/> |<span data-ttu-id="ef546-278">100</span><span class="sxs-lookup"><span data-stu-id="ef546-278">100</span></span>  <br/> |<span data-ttu-id="ef546-279">1 </span><span class="sxs-lookup"><span data-stu-id="ef546-279">1</span></span>  <br/> |<span data-ttu-id="ef546-280">5061</span><span class="sxs-lookup"><span data-stu-id="ef546-280">5061</span></span>  <br/> |<span data-ttu-id="ef546-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef546-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiare il valore per il nuovo record.](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="ef546-283">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="ef546-283">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="ef546-285">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="ef546-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="ef546-286">Sempre nella sezione **Add DNS record** creare un record usando i valori dell'altra riga della tabella e quindi selezionare di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="ef546-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ef546-p114">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef546-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

