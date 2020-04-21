---
title: Creare record DNS al passaggio del mouse per Microsoft
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi al passaggio del mouse per Microsoft.
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629516"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="3d351-103">Creare record DNS al passaggio del mouse per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d351-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="3d351-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3d351-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d351-105">Se il proprio provider di hosting DNS è Hover, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="3d351-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="3d351-106">Dopo aver aggiunto questi record al passaggio del mouse, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d351-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3d351-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="3d351-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3d351-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d351-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3d351-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="3d351-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3d351-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d351-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3d351-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="3d351-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="3d351-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="3d351-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d351-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="3d351-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="3d351-117">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3d351-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d351-p104">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d351-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="3d351-121">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="3d351-123">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="3d351-123">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="3d351-125">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d351-125">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="3d351-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d351-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d351-128">Nome host</span><span class="sxs-lookup"><span data-stu-id="3d351-128">Hostname</span></span>  <br/> |<span data-ttu-id="3d351-129">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="3d351-129">Record Type</span></span>  <br/> |<span data-ttu-id="3d351-130">Valore</span><span class="sxs-lookup"><span data-stu-id="3d351-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="3d351-131">TXT</span><span class="sxs-lookup"><span data-stu-id="3d351-131">TXT</span></span>  <br/> |<span data-ttu-id="3d351-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d351-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d351-133">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="3d351-133">**Note:** This is an example.</span></span> <span data-ttu-id="3d351-134">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="3d351-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3d351-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3d351-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="3d351-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d351-137">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="3d351-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="3d351-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d351-140">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft 365 e richiedere a Microsoft 365 di cercare il record.</span><span class="sxs-lookup"><span data-stu-id="3d351-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="3d351-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="3d351-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d351-142">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="3d351-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3d351-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3d351-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="3d351-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3d351-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="3d351-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3d351-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d351-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3d351-149">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d351-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3d351-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d351-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3d351-151">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3d351-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d351-p107">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d351-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="3d351-155">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="3d351-157">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="3d351-157">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="3d351-159">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d351-159">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="3d351-161">Nelle caselle del nuovo record selezionare **MX** per **Record Type** e quindi digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3d351-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3d351-162">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="3d351-162">**Hostname**</span></span>|<span data-ttu-id="3d351-163">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="3d351-163">**Record Type**</span></span>|<span data-ttu-id="3d351-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3d351-164">**Priority**</span></span>|<span data-ttu-id="3d351-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3d351-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d351-166">MX</span><span class="sxs-lookup"><span data-stu-id="3d351-166">MX</span></span>  <br/> |<span data-ttu-id="3d351-167">0</span><span class="sxs-lookup"><span data-stu-id="3d351-167">0</span></span>  <br/> <span data-ttu-id="3d351-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="3d351-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="3d351-169">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d351-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3d351-170">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d351-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3d351-171">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3d351-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="3d351-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d351-173">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="3d351-175">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="3d351-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="3d351-176">In primo luogo, mouse su un record che si desidera rimuovere, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3d351-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passare il mouse e selezionare Elimina](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="3d351-178">In secondo luogo, selezionare **Sì** per confermare ogni eliminazione.</span><span class="sxs-lookup"><span data-stu-id="3d351-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selezionare Sì per confermare l'eliminazione](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="3d351-180">Ripetere quest'operazione fino a eliminare tutti i record MX, ad eccezione di quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3d351-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d351-181">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d351-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3d351-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d351-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3d351-183">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3d351-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d351-p109">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d351-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="3d351-187">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="3d351-189">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="3d351-189">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="3d351-191">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3d351-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3d351-192">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d351-192">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="3d351-194">Nelle caselle vuote del nuovo record selezionare **CNAME** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3d351-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="3d351-195">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3d351-195">**Hostname**</span></span>|<span data-ttu-id="3d351-196">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="3d351-196">**Record Type**</span></span>|<span data-ttu-id="3d351-197">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="3d351-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3d351-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3d351-198">autodiscover</span></span>  <br/> |<span data-ttu-id="3d351-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d351-199">CNAME</span></span>  <br/> |<span data-ttu-id="3d351-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d351-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3d351-201">sip</span><span class="sxs-lookup"><span data-stu-id="3d351-201">sip</span></span>  <br/> |<span data-ttu-id="3d351-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d351-202">CNAME</span></span>  <br/> |<span data-ttu-id="3d351-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d351-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d351-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d351-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d351-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d351-205">CNAME</span></span>  <br/> |<span data-ttu-id="3d351-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d351-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d351-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d351-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d351-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d351-208">CNAME</span></span>  <br/> |<span data-ttu-id="3d351-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d351-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3d351-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d351-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d351-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d351-211">CNAME</span></span>  <br/> |<span data-ttu-id="3d351-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d351-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="3d351-214">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d351-214">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="3d351-216">Usando i tre passaggi descritti in precedenza e i valori dalle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3d351-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d351-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3d351-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d351-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d351-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d351-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="3d351-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d351-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3d351-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d351-221">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d351-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3d351-222">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="3d351-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="3d351-223">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3d351-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d351-p111">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d351-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="3d351-227">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="3d351-229">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="3d351-229">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="3d351-231">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d351-231">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="3d351-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d351-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3d351-234">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="3d351-234">**Hostname**</span></span>|<span data-ttu-id="3d351-235">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="3d351-235">**Record Type**</span></span>|<span data-ttu-id="3d351-236">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3d351-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d351-237">TXT</span><span class="sxs-lookup"><span data-stu-id="3d351-237">TXT</span></span>  <br/> |<span data-ttu-id="3d351-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d351-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="3d351-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3d351-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="3d351-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d351-241">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d351-243">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d351-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3d351-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d351-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3d351-245">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3d351-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d351-p112">Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3d351-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="3d351-249">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3d351-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="3d351-251">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="3d351-251">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="3d351-253">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="3d351-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3d351-254">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d351-254">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="3d351-256">Nelle caselle vuote del nuovo record selezionare **SRV** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3d351-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="3d351-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3d351-257">**Hostname**</span></span>|<span data-ttu-id="3d351-258">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="3d351-258">**Record Type**</span></span>|<span data-ttu-id="3d351-259">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="3d351-259">**Priority**</span></span>|<span data-ttu-id="3d351-260">**Peso**</span><span class="sxs-lookup"><span data-stu-id="3d351-260">**Weight**</span></span>|<span data-ttu-id="3d351-261">**Porta**</span><span class="sxs-lookup"><span data-stu-id="3d351-261">**Port**</span></span>|<span data-ttu-id="3d351-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="3d351-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d351-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="3d351-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="3d351-264">SRV</span><span class="sxs-lookup"><span data-stu-id="3d351-264">SRV</span></span>  <br/> |<span data-ttu-id="3d351-265">100</span><span class="sxs-lookup"><span data-stu-id="3d351-265">100</span></span>  <br/> |<span data-ttu-id="3d351-266">1 </span><span class="sxs-lookup"><span data-stu-id="3d351-266">1</span></span>  <br/> |<span data-ttu-id="3d351-267">443</span><span class="sxs-lookup"><span data-stu-id="3d351-267">443</span></span>  <br/> |<span data-ttu-id="3d351-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d351-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3d351-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="3d351-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3d351-270">SRV</span><span class="sxs-lookup"><span data-stu-id="3d351-270">SRV</span></span>  <br/> |<span data-ttu-id="3d351-271">100</span><span class="sxs-lookup"><span data-stu-id="3d351-271">100</span></span>  <br/> |<span data-ttu-id="3d351-272">1 </span><span class="sxs-lookup"><span data-stu-id="3d351-272">1</span></span>  <br/> |<span data-ttu-id="3d351-273">5061</span><span class="sxs-lookup"><span data-stu-id="3d351-273">5061</span></span>  <br/> |<span data-ttu-id="3d351-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d351-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="3d351-276">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d351-276">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="3d351-278">Usando i tre passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="3d351-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3d351-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3d351-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
