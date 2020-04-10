---
title: Creare record DNS su name.com per Office 365
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in name.com per Office 365.
ms.openlocfilehash: f39cf9f241851e555ea23ca7b63453796a5f471b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211656"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="7f176-103">Creare record DNS su name.com per Office 365</span><span class="sxs-lookup"><span data-stu-id="7f176-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="7f176-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7f176-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7f176-105">Se il proprio provider di hosting DNS è name.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="7f176-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7f176-106">Dopo aver aggiunto questi record in name.com, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f176-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="7f176-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="7f176-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f176-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f176-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7f176-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="7f176-111">Add a TXT record for verification</span></span>
<span data-ttu-id="7f176-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7f176-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7f176-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="7f176-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f176-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="7f176-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7f176-p104">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7f176-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="7f176-120">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="7f176-122">Nella colonna **Details** selezionare \* \* DNS Records \* \*.</span><span class="sxs-lookup"><span data-stu-id="7f176-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="7f176-124">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f176-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7f176-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7f176-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f176-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f176-126">**Type**</span></span> <br/> |<span data-ttu-id="7f176-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f176-127">**Host**</span></span> <br/> |<span data-ttu-id="7f176-128">**Answer**</span><span class="sxs-lookup"><span data-stu-id="7f176-128">**Answer**</span></span> <br/> |<span data-ttu-id="7f176-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f176-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="7f176-130">TXT</span><span class="sxs-lookup"><span data-stu-id="7f176-130">TXT</span></span>  <br/> |<span data-ttu-id="7f176-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7f176-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7f176-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7f176-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7f176-p105">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="7f176-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="7f176-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-136">Use the default value (300).</span></span>  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="7f176-138">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="7f176-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="7f176-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="7f176-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7f176-141">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="7f176-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="7f176-142">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="7f176-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7f176-143">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="7f176-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7f176-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7f176-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="7f176-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7f176-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="7f176-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="7f176-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f176-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7f176-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="7f176-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7f176-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7f176-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7f176-p107">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7f176-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="7f176-155">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="7f176-157">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="7f176-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="7f176-159">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f176-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7f176-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7f176-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f176-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f176-161">**Type**</span></span>|<span data-ttu-id="7f176-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f176-162">**Host**</span></span>|<span data-ttu-id="7f176-163">**Answer**</span><span class="sxs-lookup"><span data-stu-id="7f176-163">**Answer**</span></span>|<span data-ttu-id="7f176-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f176-164">**TTL**</span></span>|<span data-ttu-id="7f176-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="7f176-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f176-166">MX</span><span class="sxs-lookup"><span data-stu-id="7f176-166">MX</span></span>  <br/> |<span data-ttu-id="7f176-167">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="7f176-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="7f176-168">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f176-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7f176-169">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f176-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="7f176-170">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="7f176-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7f176-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="7f176-172">0</span><span class="sxs-lookup"><span data-stu-id="7f176-172">0</span></span>  <br/> <span data-ttu-id="7f176-173">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="7f176-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Nome-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="7f176-175">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="7f176-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configurazione-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="7f176-177">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="7f176-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="7f176-178">Per ogni altro record MX, selezionare **Elimina** nella colonna **azioni** .</span><span class="sxs-lookup"><span data-stu-id="7f176-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configurazione-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="7f176-180">Per confermare ogni eliminazione, selezionare di nuovo **Delete** nella colonna **Actions** .</span><span class="sxs-lookup"><span data-stu-id="7f176-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="7f176-182">Ripetere questa procedura in due passaggi fino a eliminare ogni altro record MX.</span><span class="sxs-lookup"><span data-stu-id="7f176-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7f176-183">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="7f176-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7f176-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7f176-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7f176-p109">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7f176-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="7f176-188">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="7f176-190">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="7f176-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="7f176-192">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f176-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="7f176-193">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f176-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="7f176-194">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f176-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f176-195">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f176-195">**Type**</span></span>|<span data-ttu-id="7f176-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f176-196">**Host**</span></span>|<span data-ttu-id="7f176-197">**Answer**</span><span class="sxs-lookup"><span data-stu-id="7f176-197">**Answer**</span></span>|<span data-ttu-id="7f176-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f176-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f176-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f176-199">CNAME</span></span>  <br/> |<span data-ttu-id="7f176-200">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="7f176-200">autodiscover</span></span>  <br/> |<span data-ttu-id="7f176-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f176-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="7f176-202">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="7f176-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f176-203">CNAME</span></span>  <br/> |<span data-ttu-id="7f176-204">sip</span><span class="sxs-lookup"><span data-stu-id="7f176-204">sip</span></span>  <br/> |<span data-ttu-id="7f176-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f176-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f176-206">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="7f176-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f176-207">CNAME</span></span>  <br/> |<span data-ttu-id="7f176-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7f176-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7f176-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f176-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f176-210">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="7f176-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f176-211">CNAME</span></span>  <br/> |<span data-ttu-id="7f176-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7f176-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7f176-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7f176-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="7f176-214">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="7f176-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f176-215">CNAME</span></span>  <br/> |<span data-ttu-id="7f176-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7f176-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7f176-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7f176-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="7f176-218">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-218">Use the default value (300).</span></span>  <br/> |
   
   ![Nome-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="7f176-220">Selezionare **Aggiungi record** per aggiungere il primo record.</span><span class="sxs-lookup"><span data-stu-id="7f176-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="7f176-222">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="7f176-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="7f176-223">Utilizzare i valori della seconda riga della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="7f176-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="7f176-224">Aggiungere i record rimanenti allo stesso modo, usando i valori dalla terza, quarta, quinta e sesta riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="7f176-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7f176-225">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7f176-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7f176-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7f176-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f176-227">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="7f176-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7f176-228">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7f176-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7f176-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f176-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7f176-230">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="7f176-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="7f176-p111">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7f176-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="7f176-234">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="7f176-236">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="7f176-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="7f176-238">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f176-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7f176-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7f176-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f176-240">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f176-240">**Type**</span></span>|<span data-ttu-id="7f176-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f176-241">**Host**</span></span>|<span data-ttu-id="7f176-242">**Answer**</span><span class="sxs-lookup"><span data-stu-id="7f176-242">**Answer**</span></span>|<span data-ttu-id="7f176-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f176-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f176-244">TXT</span><span class="sxs-lookup"><span data-stu-id="7f176-244">TXT</span></span>  <br/> |<span data-ttu-id="7f176-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7f176-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7f176-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7f176-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7f176-247">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="7f176-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7f176-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-248">Use the default value (300).</span></span>  <br/> |
   
   ![Nome-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="7f176-250">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="7f176-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7f176-252">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="7f176-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7f176-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7f176-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7f176-p112">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7f176-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="7f176-257">In **My Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7f176-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="7f176-259">Nella colonna **Details** selezionare **DNS Records +**.</span><span class="sxs-lookup"><span data-stu-id="7f176-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="7f176-261">Aggiungere il primo record SRV:</span><span class="sxs-lookup"><span data-stu-id="7f176-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="7f176-262">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f176-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="7f176-263">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f176-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7f176-264">**Type**</span><span class="sxs-lookup"><span data-stu-id="7f176-264">**Type**</span></span>|<span data-ttu-id="7f176-265">**Service**</span><span class="sxs-lookup"><span data-stu-id="7f176-265">**Service**</span></span>|<span data-ttu-id="7f176-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="7f176-266">**Weight**</span></span>|<span data-ttu-id="7f176-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f176-267">**TTL**</span></span>|<span data-ttu-id="7f176-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="7f176-268">**Prio**</span></span>|<span data-ttu-id="7f176-269">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="7f176-269">**Protocol**</span></span>|<span data-ttu-id="7f176-270">**Port**</span><span class="sxs-lookup"><span data-stu-id="7f176-270">**Port**</span></span>|<span data-ttu-id="7f176-271">**Target**</span><span class="sxs-lookup"><span data-stu-id="7f176-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f176-272">SRV</span><span class="sxs-lookup"><span data-stu-id="7f176-272">SRV</span></span>|<span data-ttu-id="7f176-273">sip</span><span class="sxs-lookup"><span data-stu-id="7f176-273">sip</span></span>|<span data-ttu-id="7f176-274">1 </span><span class="sxs-lookup"><span data-stu-id="7f176-274">1</span></span>|<span data-ttu-id="7f176-275">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-275">Use the default value (300).</span></span>|<span data-ttu-id="7f176-276">100</span><span class="sxs-lookup"><span data-stu-id="7f176-276">100</span></span>|<span data-ttu-id="7f176-277">tls</span><span class="sxs-lookup"><span data-stu-id="7f176-277">tls</span></span>|<span data-ttu-id="7f176-278">443</span><span class="sxs-lookup"><span data-stu-id="7f176-278">443</span></span>|<span data-ttu-id="7f176-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f176-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="7f176-280">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="7f176-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="7f176-281">SRV</span><span class="sxs-lookup"><span data-stu-id="7f176-281">SRV</span></span>|<span data-ttu-id="7f176-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7f176-282">sipfederationtls</span></span>|<span data-ttu-id="7f176-283">1 </span><span class="sxs-lookup"><span data-stu-id="7f176-283">1</span></span>|<span data-ttu-id="7f176-284">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="7f176-284">Use the default value (300).</span></span>|<span data-ttu-id="7f176-285">100</span><span class="sxs-lookup"><span data-stu-id="7f176-285">100</span></span>|<span data-ttu-id="7f176-286">tcp</span><span class="sxs-lookup"><span data-stu-id="7f176-286">tcp</span></span>|<span data-ttu-id="7f176-287">5061</span><span class="sxs-lookup"><span data-stu-id="7f176-287">5061</span></span>|<span data-ttu-id="7f176-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7f176-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="7f176-289">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="7f176-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Nome-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="7f176-291">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="7f176-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="7f176-293">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="7f176-293">Add the second SRV record:</span></span>

<span data-ttu-id="7f176-294">Utilizzare i valori della riga successiva della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="7f176-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="7f176-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7f176-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
