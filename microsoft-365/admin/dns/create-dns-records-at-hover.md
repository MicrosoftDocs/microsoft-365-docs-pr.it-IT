---
title: Creare record DNS su Hover per Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi al passaggio del mouse per Office 365.
ms.openlocfilehash: 72df2d98f3446087a1e9796cd616293a91003ad9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350107"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="1b184-103">Creare record DNS su Hover per Office 365</span><span class="sxs-lookup"><span data-stu-id="1b184-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="1b184-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1b184-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1b184-105">Se il proprio provider di hosting DNS è Hover, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="1b184-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="1b184-106">Dopo aver aggiunto questi record in Hover, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b184-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="1b184-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="1b184-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1b184-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b184-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1b184-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="1b184-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1b184-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1b184-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1b184-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1b184-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b184-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="1b184-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1b184-117">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1b184-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1b184-p104">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1b184-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="1b184-121">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="1b184-123">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="1b184-123">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="1b184-125">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1b184-125">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="1b184-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1b184-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1b184-128">Nome host</span><span class="sxs-lookup"><span data-stu-id="1b184-128">Hostname</span></span>  <br/> |<span data-ttu-id="1b184-129">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="1b184-129">Record Type</span></span>  <br/> |<span data-ttu-id="1b184-130">Valore</span><span class="sxs-lookup"><span data-stu-id="1b184-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="1b184-131">TXT</span><span class="sxs-lookup"><span data-stu-id="1b184-131">TXT</span></span>  <br/> |<span data-ttu-id="1b184-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1b184-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1b184-p105">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="1b184-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="1b184-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1b184-137">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="1b184-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="1b184-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1b184-140">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="1b184-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1b184-141">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="1b184-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1b184-142">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="1b184-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="1b184-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1b184-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1b184-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1b184-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="1b184-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1b184-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b184-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1b184-149">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="1b184-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1b184-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1b184-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1b184-151">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1b184-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1b184-p107">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1b184-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="1b184-155">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="1b184-157">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="1b184-157">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="1b184-159">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1b184-159">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="1b184-161">Nelle caselle del nuovo record selezionare **MX** per **Record Type** e quindi digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1b184-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1b184-162">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="1b184-162">**Hostname**</span></span>|<span data-ttu-id="1b184-163">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1b184-163">**Record Type**</span></span>|<span data-ttu-id="1b184-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1b184-164">**Priority**</span></span>|<span data-ttu-id="1b184-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="1b184-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1b184-166">MX</span><span class="sxs-lookup"><span data-stu-id="1b184-166">MX</span></span>  <br/> |<span data-ttu-id="1b184-167">0</span><span class="sxs-lookup"><span data-stu-id="1b184-167">0</span></span>  <br/> <span data-ttu-id="1b184-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="1b184-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="1b184-169">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1b184-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1b184-170">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b184-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="1b184-171">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1b184-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="1b184-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1b184-173">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="1b184-175">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="1b184-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="1b184-176">In primo luogo, mouse su un record che si desidera rimuovere, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1b184-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passare il mouse e selezionare Elimina](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="1b184-178">In secondo luogo, selezionare **Sì** per confermare ogni eliminazione.</span><span class="sxs-lookup"><span data-stu-id="1b184-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selezionare Sì per confermare l'eliminazione](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="1b184-180">Ripetere quest'operazione fino a eliminare tutti i record MX, ad eccezione di quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1b184-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1b184-181">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1b184-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1b184-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1b184-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1b184-183">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1b184-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1b184-p109">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1b184-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="1b184-187">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="1b184-189">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="1b184-189">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="1b184-191">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1b184-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1b184-192">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1b184-192">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="1b184-194">Nelle caselle vuote del nuovo record selezionare **CNAME** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1b184-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="1b184-195">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="1b184-195">**Hostname**</span></span>|<span data-ttu-id="1b184-196">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1b184-196">**Record Type**</span></span>|<span data-ttu-id="1b184-197">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="1b184-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1b184-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1b184-198">autodiscover</span></span>  <br/> |<span data-ttu-id="1b184-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="1b184-199">CNAME</span></span>  <br/> |<span data-ttu-id="1b184-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1b184-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="1b184-201">sip</span><span class="sxs-lookup"><span data-stu-id="1b184-201">sip</span></span>  <br/> |<span data-ttu-id="1b184-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="1b184-202">CNAME</span></span>  <br/> |<span data-ttu-id="1b184-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b184-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b184-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1b184-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1b184-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="1b184-205">CNAME</span></span>  <br/> |<span data-ttu-id="1b184-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b184-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b184-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1b184-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1b184-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="1b184-208">CNAME</span></span>  <br/> |<span data-ttu-id="1b184-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1b184-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="1b184-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1b184-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1b184-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="1b184-211">CNAME</span></span>  <br/> |<span data-ttu-id="1b184-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1b184-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="1b184-214">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1b184-214">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="1b184-216">Usando i tre passaggi descritti in precedenza e i valori dalle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1b184-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1b184-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1b184-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1b184-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1b184-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b184-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="1b184-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1b184-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1b184-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1b184-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b184-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1b184-222">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="1b184-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="1b184-223">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1b184-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1b184-p111">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1b184-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="1b184-227">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="1b184-229">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="1b184-229">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="1b184-231">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1b184-231">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="1b184-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1b184-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1b184-234">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="1b184-234">**Hostname**</span></span>|<span data-ttu-id="1b184-235">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1b184-235">**Record Type**</span></span>|<span data-ttu-id="1b184-236">**Valore**</span><span class="sxs-lookup"><span data-stu-id="1b184-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1b184-237">TXT</span><span class="sxs-lookup"><span data-stu-id="1b184-237">TXT</span></span>  <br/> |<span data-ttu-id="1b184-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1b184-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="1b184-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1b184-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="1b184-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1b184-241">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1b184-243">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1b184-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1b184-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1b184-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1b184-245">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1b184-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1b184-p112">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1b184-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="1b184-249">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1b184-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="1b184-251">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="1b184-251">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="1b184-253">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="1b184-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1b184-254">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1b184-254">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="1b184-256">Nelle caselle vuote del nuovo record selezionare **SRV** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1b184-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="1b184-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="1b184-257">**Hostname**</span></span>|<span data-ttu-id="1b184-258">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1b184-258">**Record Type**</span></span>|<span data-ttu-id="1b184-259">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1b184-259">**Priority**</span></span>|<span data-ttu-id="1b184-260">**Peso**</span><span class="sxs-lookup"><span data-stu-id="1b184-260">**Weight**</span></span>|<span data-ttu-id="1b184-261">**Porta**</span><span class="sxs-lookup"><span data-stu-id="1b184-261">**Port**</span></span>|<span data-ttu-id="1b184-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="1b184-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1b184-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="1b184-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="1b184-264">SRV</span><span class="sxs-lookup"><span data-stu-id="1b184-264">SRV</span></span>  <br/> |<span data-ttu-id="1b184-265">100</span><span class="sxs-lookup"><span data-stu-id="1b184-265">100</span></span>  <br/> |<span data-ttu-id="1b184-266">1</span><span class="sxs-lookup"><span data-stu-id="1b184-266">1</span></span>  <br/> |<span data-ttu-id="1b184-267">443</span><span class="sxs-lookup"><span data-stu-id="1b184-267">443</span></span>  <br/> |<span data-ttu-id="1b184-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b184-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1b184-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="1b184-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1b184-270">SRV</span><span class="sxs-lookup"><span data-stu-id="1b184-270">SRV</span></span>  <br/> |<span data-ttu-id="1b184-271">100</span><span class="sxs-lookup"><span data-stu-id="1b184-271">100</span></span>  <br/> |<span data-ttu-id="1b184-272">1</span><span class="sxs-lookup"><span data-stu-id="1b184-272">1</span></span>  <br/> |<span data-ttu-id="1b184-273">5061</span><span class="sxs-lookup"><span data-stu-id="1b184-273">5061</span></span>  <br/> |<span data-ttu-id="1b184-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1b184-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="1b184-276">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1b184-276">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="1b184-278">Usando i tre passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="1b184-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1b184-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b184-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
