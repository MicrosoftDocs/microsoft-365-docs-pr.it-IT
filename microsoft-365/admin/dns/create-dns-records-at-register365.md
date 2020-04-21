---
title: Creare record DNS in Register365 per Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register365 per Microsoft.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629264"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="99e23-103">Creare record DNS in Register365 per Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="99e23-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="99e23-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="99e23-105">Se il proprio provider di hosting DNS è Register365, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="99e23-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="99e23-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="99e23-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="99e23-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="99e23-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="99e23-108">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="99e23-109">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="99e23-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="99e23-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="99e23-111">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="99e23-112">Dopo aver aggiunto questi record in Microsoft, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99e23-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="99e23-113">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="99e23-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="99e23-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99e23-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="99e23-117">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="99e23-117">Add a TXT record for verification</span></span>
<span data-ttu-id="99e23-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="99e23-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="99e23-119">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="99e23-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="99e23-120">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="99e23-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99e23-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="99e23-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="99e23-p104">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99e23-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="99e23-126">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="99e23-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="99e23-127">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-127">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="99e23-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="99e23-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99e23-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99e23-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="99e23-131">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="99e23-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="99e23-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="99e23-133">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="99e23-133">**Host name**</span></span>|<span data-ttu-id="99e23-134">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="99e23-134">**Type**</span></span>|<span data-ttu-id="99e23-135">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="99e23-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="99e23-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="99e23-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99e23-137">TXT</span><span class="sxs-lookup"><span data-stu-id="99e23-137">TXT</span></span>  <br/> |<span data-ttu-id="99e23-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="99e23-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="99e23-139">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="99e23-139">**Note:** This is an example.</span></span> <span data-ttu-id="99e23-140">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="99e23-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="99e23-141">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="99e23-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="99e23-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-143">Select **Save**.</span></span>
    
    <span data-ttu-id="99e23-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-144">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="99e23-146">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="99e23-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="99e23-147">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="99e23-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="99e23-148">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="99e23-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="99e23-149">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="99e23-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="99e23-150">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="99e23-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="99e23-151">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="99e23-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="99e23-152">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="99e23-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="99e23-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99e23-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="99e23-156">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="99e23-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="99e23-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="99e23-p107">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99e23-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="99e23-161">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="99e23-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="99e23-162">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-162">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="99e23-164">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Mail exchange records**.</span><span class="sxs-lookup"><span data-stu-id="99e23-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99e23-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="99e23-166">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="99e23-166">**Host name**</span></span>|<span data-ttu-id="99e23-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="99e23-167">**Priority**</span></span>|<span data-ttu-id="99e23-168">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="99e23-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="99e23-169">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="99e23-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99e23-170">1 </span><span class="sxs-lookup"><span data-stu-id="99e23-170">1</span></span>  <br/> <span data-ttu-id="99e23-171">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="99e23-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="99e23-172">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="99e23-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="99e23-173">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99e23-173">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="99e23-174">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="99e23-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="99e23-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-176">Select **Save**.</span></span>
    
    <span data-ttu-id="99e23-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-177">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="99e23-179">Se sono presenti altri record MX nella sezione **Mail exchange records**, eliminarli uno alla volta selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="99e23-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="99e23-181">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-181">Select **Save**.</span></span>
    
    <span data-ttu-id="99e23-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-182">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="99e23-184">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-184">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="99e23-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="99e23-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="99e23-p109">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99e23-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="99e23-189">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="99e23-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="99e23-190">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-190">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="99e23-192">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **A, CNAME, AAAA, TXT and NS records**.</span><span class="sxs-lookup"><span data-stu-id="99e23-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99e23-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99e23-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="99e23-194">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="99e23-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="99e23-195">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="99e23-196">\*\*\*\*Host name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="99e23-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="99e23-197">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="99e23-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="99e23-198">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="99e23-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="99e23-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="99e23-199">autodiscover</span></span>  <br/> |<span data-ttu-id="99e23-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="99e23-200">CNAME</span></span>  <br/> |<span data-ttu-id="99e23-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="99e23-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="99e23-202">sip</span><span class="sxs-lookup"><span data-stu-id="99e23-202">sip</span></span>  <br/> |<span data-ttu-id="99e23-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="99e23-203">CNAME</span></span>  <br/> |<span data-ttu-id="99e23-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99e23-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="99e23-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="99e23-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="99e23-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="99e23-206">CNAME</span></span>  <br/> |<span data-ttu-id="99e23-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99e23-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="99e23-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="99e23-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="99e23-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="99e23-209">CNAME</span></span>  <br/> |<span data-ttu-id="99e23-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="99e23-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="99e23-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="99e23-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="99e23-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="99e23-212">CNAME</span></span>  <br/> |<span data-ttu-id="99e23-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="99e23-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="99e23-215">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-215">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="99e23-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="99e23-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="99e23-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="99e23-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="99e23-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="99e23-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="99e23-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="99e23-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="99e23-221">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99e23-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="99e23-222">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="99e23-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="99e23-p111">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99e23-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="99e23-226">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="99e23-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="99e23-227">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-227">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="99e23-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="99e23-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99e23-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99e23-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="99e23-231">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="99e23-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="99e23-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="99e23-233">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="99e23-233">**Host name**</span></span>|<span data-ttu-id="99e23-234">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="99e23-234">**Type**</span></span>|<span data-ttu-id="99e23-235">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="99e23-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="99e23-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="99e23-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99e23-237">TXT</span><span class="sxs-lookup"><span data-stu-id="99e23-237">TXT</span></span>  <br/> |<span data-ttu-id="99e23-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="99e23-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="99e23-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="99e23-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="99e23-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-241">Select **Save**.</span></span>
    
    <span data-ttu-id="99e23-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-242">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="99e23-244">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="99e23-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="99e23-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="99e23-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="99e23-p112">Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99e23-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="99e23-249">Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="99e23-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="99e23-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-250">(You may have to scroll down.)</span></span>
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="99e23-252">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **Service records**.</span><span class="sxs-lookup"><span data-stu-id="99e23-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99e23-253">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99e23-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="99e23-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="99e23-254">**Name**</span></span>|<span data-ttu-id="99e23-255">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="99e23-255">**Priority**</span></span>|<span data-ttu-id="99e23-256">**Peso**</span><span class="sxs-lookup"><span data-stu-id="99e23-256">**Weight**</span></span>|<span data-ttu-id="99e23-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="99e23-257">**Port**</span></span>|<span data-ttu-id="99e23-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="99e23-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99e23-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="99e23-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="99e23-260">100</span><span class="sxs-lookup"><span data-stu-id="99e23-260">100</span></span>  <br/> |<span data-ttu-id="99e23-261">1 </span><span class="sxs-lookup"><span data-stu-id="99e23-261">1</span></span>  <br/> |<span data-ttu-id="99e23-262">443</span><span class="sxs-lookup"><span data-stu-id="99e23-262">443</span></span>  <br/> |<span data-ttu-id="99e23-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99e23-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="99e23-264">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="99e23-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="99e23-265">100</span><span class="sxs-lookup"><span data-stu-id="99e23-265">100</span></span>  <br/> |<span data-ttu-id="99e23-266">1 </span><span class="sxs-lookup"><span data-stu-id="99e23-266">1</span></span>  <br/> |<span data-ttu-id="99e23-267">5061</span><span class="sxs-lookup"><span data-stu-id="99e23-267">5061</span></span>  <br/> |<span data-ttu-id="99e23-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99e23-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Immissione di valori nella sezione Service Records](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="99e23-270">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99e23-270">Select **Save**.</span></span>
    
    <span data-ttu-id="99e23-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="99e23-271">(You may have to scroll down.)</span></span>
    
    ![Seleziona Salva](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="99e23-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99e23-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
