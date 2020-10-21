---
title: Creare record DNS in Register365 per Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register365 per Microsoft.
ms.openlocfilehash: a4c66a4c16960332150a51779207defb00df3044
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645768"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="3d7e5-103">Creare record DNS in Register365 per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="3d7e5-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d7e5-105">Se il proprio provider di hosting DNS è Register365, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="3d7e5-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="3d7e5-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="3d7e5-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="3d7e5-108">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="3d7e5-109">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="3d7e5-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3d7e5-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="3d7e5-111">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="3d7e5-112">Dopo aver aggiunto questi record in Microsoft, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3d7e5-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3d7e5-116">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="3d7e5-116">Add a TXT record for verification</span></span>
<span data-ttu-id="3d7e5-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7e5-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3d7e5-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d7e5-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3d7e5-p104">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="3d7e5-125">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d7e5-126">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-126">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="3d7e5-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d7e5-129">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d7e5-130">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d7e5-131">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d7e5-132">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-132">**Host name**</span></span>|<span data-ttu-id="3d7e5-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-133">**Type**</span></span>|<span data-ttu-id="3d7e5-134">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d7e5-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d7e5-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d7e5-136">TXT</span><span class="sxs-lookup"><span data-stu-id="3d7e5-136">TXT</span></span>  <br/> |<span data-ttu-id="3d7e5-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d7e5-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d7e5-138">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-138">**Note:** This is an example.</span></span> <span data-ttu-id="3d7e5-139">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3d7e5-140">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3d7e5-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="3d7e5-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-142">Select **Save**.</span></span>
    
    <span data-ttu-id="3d7e5-143">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-143">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="3d7e5-145">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d7e5-146">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3d7e5-147">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d7e5-148">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3d7e5-149">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3d7e5-150">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3d7e5-151">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3d7e5-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3d7e5-155">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3d7e5-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7e5-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3d7e5-p107">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="3d7e5-160">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d7e5-161">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-161">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="3d7e5-163">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Mail exchange records**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d7e5-164">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d7e5-165">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-165">**Host name**</span></span>|<span data-ttu-id="3d7e5-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-166">**Priority**</span></span>|<span data-ttu-id="3d7e5-167">**Result**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d7e5-168">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d7e5-169">1 </span><span class="sxs-lookup"><span data-stu-id="3d7e5-169">1</span></span>  <br/> <span data-ttu-id="3d7e5-170">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="3d7e5-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="3d7e5-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3d7e5-172">**Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="3d7e5-173">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3d7e5-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="3d7e5-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-175">Select **Save**.</span></span>
    
    <span data-ttu-id="3d7e5-176">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-176">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="3d7e5-178">Se sono presenti altri record MX nella sezione **Mail exchange records**, eliminarli uno alla volta selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="3d7e5-180">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-180">Select **Save**.</span></span>
    
    <span data-ttu-id="3d7e5-181">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-181">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d7e5-183">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3d7e5-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7e5-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3d7e5-p109">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="3d7e5-188">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d7e5-189">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-189">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="3d7e5-191">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **A, CNAME, AAAA, TXT and NS records**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d7e5-192">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d7e5-193">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d7e5-194">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d7e5-195">\*\*\*\*Host name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3d7e5-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="3d7e5-196">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3d7e5-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="3d7e5-197">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3d7e5-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d7e5-198">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="3d7e5-198">autodiscover</span></span>  <br/> |<span data-ttu-id="3d7e5-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d7e5-199">CNAME</span></span>  <br/> |<span data-ttu-id="3d7e5-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3d7e5-201">sip</span><span class="sxs-lookup"><span data-stu-id="3d7e5-201">sip</span></span>  <br/> |<span data-ttu-id="3d7e5-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d7e5-202">CNAME</span></span>  <br/> |<span data-ttu-id="3d7e5-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d7e5-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d7e5-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d7e5-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d7e5-205">CNAME</span></span>  <br/> |<span data-ttu-id="3d7e5-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d7e5-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d7e5-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d7e5-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d7e5-208">CNAME</span></span>  <br/> |<span data-ttu-id="3d7e5-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d7e5-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3d7e5-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d7e5-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d7e5-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d7e5-211">CNAME</span></span>  <br/> |<span data-ttu-id="3d7e5-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="3d7e5-214">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-214">Select **Save**.</span></span>
    
    ![Seleziona Salva.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d7e5-216">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3d7e5-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d7e5-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7e5-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d7e5-218">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d7e5-219">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d7e5-220">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3d7e5-221">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="3d7e5-p111">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="3d7e5-225">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d7e5-226">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-226">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="3d7e5-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d7e5-229">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="3d7e5-230">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="3d7e5-231">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d7e5-232">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-232">**Host name**</span></span>|<span data-ttu-id="3d7e5-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-233">**Type**</span></span>|<span data-ttu-id="3d7e5-234">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d7e5-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d7e5-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d7e5-236">TXT</span><span class="sxs-lookup"><span data-stu-id="3d7e5-236">TXT</span></span>  <br/> |<span data-ttu-id="3d7e5-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d7e5-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="3d7e5-238">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="3d7e5-240">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-240">Select **Save**.</span></span>
    
    <span data-ttu-id="3d7e5-241">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-241">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d7e5-243">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d7e5-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3d7e5-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7e5-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3d7e5-p112">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="3d7e5-248">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="3d7e5-249">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-249">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="3d7e5-251">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **Service records**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d7e5-252">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3d7e5-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-253">**Name**</span></span>|<span data-ttu-id="3d7e5-254">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-254">**Priority**</span></span>|<span data-ttu-id="3d7e5-255">**Peso**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-255">**Weight**</span></span>|<span data-ttu-id="3d7e5-256">**Porta**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-256">**Port**</span></span>|<span data-ttu-id="3d7e5-257">**Result**</span><span class="sxs-lookup"><span data-stu-id="3d7e5-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d7e5-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3d7e5-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="3d7e5-259">100</span><span class="sxs-lookup"><span data-stu-id="3d7e5-259">100</span></span>  <br/> |<span data-ttu-id="3d7e5-260">1 </span><span class="sxs-lookup"><span data-stu-id="3d7e5-260">1</span></span>  <br/> |<span data-ttu-id="3d7e5-261">443</span><span class="sxs-lookup"><span data-stu-id="3d7e5-261">443</span></span>  <br/> |<span data-ttu-id="3d7e5-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d7e5-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3d7e5-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3d7e5-264">100</span><span class="sxs-lookup"><span data-stu-id="3d7e5-264">100</span></span>  <br/> |<span data-ttu-id="3d7e5-265">1 </span><span class="sxs-lookup"><span data-stu-id="3d7e5-265">1</span></span>  <br/> |<span data-ttu-id="3d7e5-266">5061</span><span class="sxs-lookup"><span data-stu-id="3d7e5-266">5061</span></span>  <br/> |<span data-ttu-id="3d7e5-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7e5-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Immissione di valori nella sezione Service Records](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="3d7e5-269">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-269">Select **Save**.</span></span>
    
    <span data-ttu-id="3d7e5-270">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3d7e5-270">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="3d7e5-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d7e5-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
