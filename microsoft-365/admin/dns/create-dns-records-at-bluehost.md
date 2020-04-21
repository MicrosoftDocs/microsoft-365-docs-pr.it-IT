---
title: Creare record DNS su Bluehost per Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi di Bluehost per Microsoft.
ms.openlocfilehash: a39e44794ad0d8c66cd0786f88642541c6978a8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629720"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="23e82-103">Creare record DNS su Bluehost per Microsoft</span><span class="sxs-lookup"><span data-stu-id="23e82-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="23e82-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="23e82-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="23e82-105">Se il proprio provider di hosting DNS è Bluehost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="23e82-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="23e82-106">Dopo aver aggiunto questi record a Bluehost, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23e82-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="23e82-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="23e82-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="23e82-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="23e82-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="23e82-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="23e82-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="23e82-110">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="23e82-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="23e82-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="23e82-111">Add a TXT record for verification</span></span>
<span data-ttu-id="23e82-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="23e82-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="23e82-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="23e82-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="23e82-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="23e82-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23e82-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="23e82-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="23e82-117">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="23e82-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="23e82-118">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23e82-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="23e82-119">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23e82-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="23e82-120">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="23e82-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="23e82-121">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="23e82-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="23e82-122">Nella pagina \* \* DNS zone editor \* \*, nell'area **Aggiungi record DNS** , nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="23e82-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="23e82-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="23e82-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="23e82-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="23e82-124">**Host Record**</span></span> <br/> |<span data-ttu-id="23e82-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23e82-125">**TTL**</span></span> <br/> |<span data-ttu-id="23e82-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="23e82-126">**Type**</span></span> <br/> |<span data-ttu-id="23e82-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="23e82-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="23e82-128">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-128">14400</span></span>  <br/> |<span data-ttu-id="23e82-129">TXT</span><span class="sxs-lookup"><span data-stu-id="23e82-129">TXT</span></span>  <br/> |<span data-ttu-id="23e82-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="23e82-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="23e82-131">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="23e82-131">**Note:** This is an example.</span></span> <span data-ttu-id="23e82-132">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="23e82-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="23e82-133">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="23e82-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="23e82-134">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="23e82-135">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="23e82-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="23e82-136">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="23e82-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="23e82-137">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="23e82-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="23e82-138">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="23e82-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="23e82-139">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="23e82-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="23e82-140">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="23e82-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="23e82-141">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="23e82-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23e82-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="23e82-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="23e82-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="23e82-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="23e82-144">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="23e82-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="23e82-145">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="23e82-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="23e82-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="23e82-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="23e82-147">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="23e82-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="23e82-148">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23e82-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="23e82-149">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23e82-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="23e82-150">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="23e82-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="23e82-151">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="23e82-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="23e82-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="23e82-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="23e82-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="23e82-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="23e82-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="23e82-154">**Host Record**</span></span>|<span data-ttu-id="23e82-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23e82-155">**TTL**</span></span>|<span data-ttu-id="23e82-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="23e82-156">**Type**</span></span>|<span data-ttu-id="23e82-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="23e82-157">**Points To**</span></span>|<span data-ttu-id="23e82-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="23e82-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="23e82-159">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-159">14400</span></span>  <br/> |<span data-ttu-id="23e82-160">MX</span><span class="sxs-lookup"><span data-stu-id="23e82-160">MX</span></span>  <br/> | <span data-ttu-id="23e82-161">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="23e82-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="23e82-162">**Nota:** Ottenere la \<propria *chiave* \> di dominio dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23e82-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="23e82-163">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="23e82-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="23e82-164">0</span><span class="sxs-lookup"><span data-stu-id="23e82-164">0</span></span>  <br/> <span data-ttu-id="23e82-165">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="23e82-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Scegliere tipo dall'elenco a discesa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="23e82-167">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-167">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="23e82-169">Rimuovere eventuali altri record MX presenti nella sezione **MX (Mail Exchanger)**.</span><span class="sxs-lookup"><span data-stu-id="23e82-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="23e82-170">Per uno degli altri record MX, selezionare **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="23e82-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selezionare Elimina per ogni record MX aggiuntivo](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="23e82-172">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23e82-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Seleziona OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="23e82-174">Usare la stessa procedura per eliminare eventuali altri record MX già presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="23e82-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="23e82-175">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="23e82-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="23e82-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="23e82-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="23e82-177">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="23e82-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="23e82-178">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23e82-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="23e82-179">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23e82-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="23e82-180">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="23e82-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="23e82-181">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="23e82-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="23e82-182">Nella sezione **a (host)** Records individuare la riga del record di **individuazione automatica** e quindi fare clic su **Elimina** per tale riga.</span><span class="sxs-lookup"><span data-stu-id="23e82-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="23e82-183">È necessario eliminare il record di **individuazione automatica** esistente *prima* di aggiungere il record di **individuazione automatica** richiesto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23e82-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="23e82-184">Bluehost non consente di mantenere due record **autodiscover** contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="23e82-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Seleziona Elimina](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="23e82-186">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="23e82-186">Select **OK**.</span></span>
    
    ![Seleziona OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="23e82-188">Creare il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="23e82-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="23e82-189">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="23e82-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="23e82-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="23e82-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="23e82-191">**Host Record**</span></span>|<span data-ttu-id="23e82-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23e82-192">**TTL**</span></span>|<span data-ttu-id="23e82-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="23e82-193">**Type**</span></span>|<span data-ttu-id="23e82-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="23e82-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="23e82-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="23e82-195">autodiscover</span></span>  <br/> |<span data-ttu-id="23e82-196">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-196">14400</span></span>  <br/> |<span data-ttu-id="23e82-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e82-197">CNAME</span></span>  <br/> |<span data-ttu-id="23e82-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="23e82-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="23e82-199">sip</span><span class="sxs-lookup"><span data-stu-id="23e82-199">sip</span></span>  <br/> |<span data-ttu-id="23e82-200">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-200">14400</span></span>  <br/> |<span data-ttu-id="23e82-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e82-201">CNAME</span></span>  <br/> |<span data-ttu-id="23e82-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="23e82-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="23e82-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="23e82-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="23e82-204">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-204">14400</span></span>  <br/> |<span data-ttu-id="23e82-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e82-205">CNAME</span></span>  <br/> |<span data-ttu-id="23e82-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="23e82-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="23e82-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="23e82-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="23e82-208">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-208">14400</span></span>  <br/> |<span data-ttu-id="23e82-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e82-209">CNAME</span></span>  <br/> |<span data-ttu-id="23e82-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="23e82-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="23e82-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="23e82-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="23e82-212">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-212">14400</span></span>  <br/> |<span data-ttu-id="23e82-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e82-213">CNAME</span></span>  <br/> |<span data-ttu-id="23e82-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="23e82-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Creare il primo record CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="23e82-216">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-216">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="23e82-218">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="23e82-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="23e82-219">Sempre nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="23e82-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="23e82-220">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="23e82-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="23e82-221">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="23e82-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="23e82-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="23e82-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="23e82-223">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="23e82-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="23e82-224">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="23e82-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="23e82-225">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23e82-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="23e82-226">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="23e82-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="23e82-227">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="23e82-227">Need examples?</span></span> <span data-ttu-id="23e82-228">Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="23e82-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="23e82-229">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="23e82-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="23e82-230">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="23e82-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="23e82-231">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23e82-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="23e82-232">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23e82-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="23e82-233">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="23e82-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="23e82-234">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="23e82-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="23e82-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="23e82-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="23e82-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="23e82-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="23e82-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="23e82-237">**Host Record**</span></span>|<span data-ttu-id="23e82-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23e82-238">**TTL**</span></span>|<span data-ttu-id="23e82-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="23e82-239">**Type**</span></span>|<span data-ttu-id="23e82-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="23e82-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="23e82-241">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-241">14400</span></span>  <br/> |<span data-ttu-id="23e82-242">TXT</span><span class="sxs-lookup"><span data-stu-id="23e82-242">TXT</span></span>  <br/> |<span data-ttu-id="23e82-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="23e82-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="23e82-244">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="23e82-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare il valore TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="23e82-246">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-246">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="23e82-248">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="23e82-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="23e82-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="23e82-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="23e82-250">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="23e82-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="23e82-251">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23e82-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="23e82-252">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23e82-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="23e82-253">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="23e82-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="23e82-254">Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="23e82-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="23e82-255">Creare il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="23e82-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="23e82-256">Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="23e82-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="23e82-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="23e82-258">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="23e82-258">**Service**</span></span>|<span data-ttu-id="23e82-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="23e82-259">**Protocol**</span></span>|<span data-ttu-id="23e82-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="23e82-260">**Host**</span></span>|<span data-ttu-id="23e82-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23e82-261">**TTL**</span></span>|<span data-ttu-id="23e82-262">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="23e82-262">**Type**</span></span>|<span data-ttu-id="23e82-263">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="23e82-263">**Priority**</span></span>|<span data-ttu-id="23e82-264">**Peso**</span><span class="sxs-lookup"><span data-stu-id="23e82-264">**Weight**</span></span>|<span data-ttu-id="23e82-265">**Porta**</span><span class="sxs-lookup"><span data-stu-id="23e82-265">**Port**</span></span>|<span data-ttu-id="23e82-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="23e82-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="23e82-267">_sip</span><span class="sxs-lookup"><span data-stu-id="23e82-267">_sip</span></span>  <br/> |<span data-ttu-id="23e82-268">_tls</span><span class="sxs-lookup"><span data-stu-id="23e82-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="23e82-269">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-269">14400</span></span>  <br/> |<span data-ttu-id="23e82-270">SRV</span><span class="sxs-lookup"><span data-stu-id="23e82-270">SRV</span></span>  <br/> |<span data-ttu-id="23e82-271">100</span><span class="sxs-lookup"><span data-stu-id="23e82-271">100</span></span>  <br/> |<span data-ttu-id="23e82-272">1 </span><span class="sxs-lookup"><span data-stu-id="23e82-272">1</span></span>  <br/> |<span data-ttu-id="23e82-273">443</span><span class="sxs-lookup"><span data-stu-id="23e82-273">443</span></span>  <br/> |<span data-ttu-id="23e82-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="23e82-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="23e82-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="23e82-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="23e82-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="23e82-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="23e82-277">14400</span><span class="sxs-lookup"><span data-stu-id="23e82-277">14400</span></span>  <br/> |<span data-ttu-id="23e82-278">SRV</span><span class="sxs-lookup"><span data-stu-id="23e82-278">SRV</span></span>  <br/> |<span data-ttu-id="23e82-279">100</span><span class="sxs-lookup"><span data-stu-id="23e82-279">100</span></span>  <br/> |<span data-ttu-id="23e82-280">1 </span><span class="sxs-lookup"><span data-stu-id="23e82-280">1</span></span>  <br/> |<span data-ttu-id="23e82-281">5061</span><span class="sxs-lookup"><span data-stu-id="23e82-281">5061</span></span>  <br/> |<span data-ttu-id="23e82-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="23e82-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiare il valore per il nuovo record.](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="23e82-284">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="23e82-284">Select **add record**.</span></span>
    
    ![Selezionare Aggiungi record](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="23e82-286">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="23e82-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="23e82-287">Sempre nella sezione **Add DNS record** creare un record usando i valori dell'altra riga della tabella e quindi selezionare di nuovo **Add record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="23e82-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="23e82-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="23e82-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="23e82-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="23e82-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="23e82-290">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="23e82-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

