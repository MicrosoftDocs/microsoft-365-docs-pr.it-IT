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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi al passaggio del mouse per Microsoft.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780350"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="7e6e5-103">Creare record DNS al passaggio del mouse per Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e6e5-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="7e6e5-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7e6e5-105">Se il proprio provider di hosting DNS è Hover, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="7e6e5-106">Dopo aver aggiunto questi record al passaggio del mouse, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="7e6e5-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e6e5-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e6e5-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7e6e5-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="7e6e5-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7e6e5-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7e6e5-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7e6e5-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="7e6e5-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e6e5-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="7e6e5-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="7e6e5-116">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-116">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="7e6e5-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="7e6e5-118">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-118">You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="7e6e5-120">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="7e6e5-122">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="7e6e5-122">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="7e6e5-124">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-124">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="7e6e5-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e6e5-127">Nome host</span><span class="sxs-lookup"><span data-stu-id="7e6e5-127">Hostname</span></span>  <br/> |<span data-ttu-id="7e6e5-128">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="7e6e5-128">Record Type</span></span>  <br/> |<span data-ttu-id="7e6e5-129">Valore</span><span class="sxs-lookup"><span data-stu-id="7e6e5-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="7e6e5-130">TXT</span><span class="sxs-lookup"><span data-stu-id="7e6e5-130">TXT</span></span>  <br/> |<span data-ttu-id="7e6e5-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7e6e5-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7e6e5-132">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-132">**Note:** This is an example.</span></span> <span data-ttu-id="7e6e5-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7e6e5-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="7e6e5-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="7e6e5-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-136">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="7e6e5-138">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7e6e5-139">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="7e6e5-140">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7e6e5-141">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7e6e5-142">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7e6e5-143">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7e6e5-144">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7e6e5-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e6e5-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e6e5-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7e6e5-148">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e6e5-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7e6e5-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7e6e5-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7e6e5-150">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-150">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="7e6e5-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="7e6e5-152">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-152">You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="7e6e5-154">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="7e6e5-156">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="7e6e5-156">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="7e6e5-158">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-158">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="7e6e5-160">Nelle caselle del nuovo record selezionare **MX** per **Record Type** e quindi digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7e6e5-161">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-161">**Hostname**</span></span>|<span data-ttu-id="7e6e5-162">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-162">**Record Type**</span></span>|<span data-ttu-id="7e6e5-163">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-163">**Priority**</span></span>|<span data-ttu-id="7e6e5-164">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7e6e5-165">MX</span><span class="sxs-lookup"><span data-stu-id="7e6e5-165">MX</span></span>  <br/> |<span data-ttu-id="7e6e5-166">0</span><span class="sxs-lookup"><span data-stu-id="7e6e5-166">0</span></span>  <br/> <span data-ttu-id="7e6e5-167">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="7e6e5-168">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7e6e5-169">**Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7e6e5-170">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="7e6e5-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="7e6e5-172">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-172">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="7e6e5-174">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="7e6e5-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="7e6e5-175">In primo luogo, mouse su un record che si desidera rimuovere, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passare il mouse e selezionare Elimina](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="7e6e5-177">In secondo luogo, selezionare **Sì** per confermare ogni eliminazione.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selezionare Sì per confermare l'eliminazione](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="7e6e5-179">Ripetere quest'operazione fino a eliminare tutti i record MX, ad eccezione di quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e6e5-180">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e6e5-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7e6e5-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7e6e5-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7e6e5-182">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-182">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="7e6e5-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="7e6e5-184">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-184">You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="7e6e5-186">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="7e6e5-188">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="7e6e5-188">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="7e6e5-190">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7e6e5-191">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-191">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="7e6e5-193">Nelle caselle vuote del nuovo record selezionare **CNAME** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="7e6e5-194">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-194">**Hostname**</span></span>|<span data-ttu-id="7e6e5-195">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-195">**Record Type**</span></span>|<span data-ttu-id="7e6e5-196">**Target Host**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e6e5-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7e6e5-197">autodiscover</span></span>  <br/> |<span data-ttu-id="7e6e5-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e6e5-198">CNAME</span></span>  <br/> |<span data-ttu-id="7e6e5-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="7e6e5-200">sip</span><span class="sxs-lookup"><span data-stu-id="7e6e5-200">sip</span></span>  <br/> |<span data-ttu-id="7e6e5-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e6e5-201">CNAME</span></span>  <br/> |<span data-ttu-id="7e6e5-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e6e5-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7e6e5-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7e6e5-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e6e5-204">CNAME</span></span>  <br/> |<span data-ttu-id="7e6e5-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e6e5-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7e6e5-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7e6e5-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e6e5-207">CNAME</span></span>  <br/> |<span data-ttu-id="7e6e5-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7e6e5-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="7e6e5-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7e6e5-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7e6e5-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e6e5-210">CNAME</span></span>  <br/> |<span data-ttu-id="7e6e5-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="7e6e5-213">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-213">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="7e6e5-215">Usando i tre passaggi descritti in precedenza e i valori dalle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7e6e5-216">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7e6e5-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7e6e5-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7e6e5-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e6e5-218">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7e6e5-219">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7e6e5-220">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7e6e5-221">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="7e6e5-222">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-222">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="7e6e5-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="7e6e5-224">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-224">You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="7e6e5-226">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="7e6e5-228">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="7e6e5-228">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="7e6e5-230">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-230">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="7e6e5-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7e6e5-233">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-233">**Hostname**</span></span>|<span data-ttu-id="7e6e5-234">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-234">**Record Type**</span></span>|<span data-ttu-id="7e6e5-235">**Valore**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7e6e5-236">TXT</span><span class="sxs-lookup"><span data-stu-id="7e6e5-236">TXT</span></span>  <br/> |<span data-ttu-id="7e6e5-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7e6e5-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="7e6e5-238">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="7e6e5-240">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-240">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e6e5-242">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e6e5-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7e6e5-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7e6e5-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7e6e5-244">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-244">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="7e6e5-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="7e6e5-246">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-246">You'll be prompted to sign in.</span></span>
    
    ![Accedi](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="7e6e5-248">In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selezionare un dominio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="7e6e5-250">Selezionare la scheda **DNS** .</span><span class="sxs-lookup"><span data-stu-id="7e6e5-250">Select the **DNS** tab.</span></span> 
    
    ![Selezionare la scheda DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="7e6e5-252">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7e6e5-253">Selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-253">Select **Add New**.</span></span>
    
    ![Selezionare Aggiungi nuovo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="7e6e5-255">Nelle caselle vuote del nuovo record selezionare **SRV** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="7e6e5-256">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-256">**Hostname**</span></span>|<span data-ttu-id="7e6e5-257">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-257">**Record Type**</span></span>|<span data-ttu-id="7e6e5-258">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-258">**Priority**</span></span>|<span data-ttu-id="7e6e5-259">**Peso**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-259">**Weight**</span></span>|<span data-ttu-id="7e6e5-260">**Porta**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-260">**Port**</span></span>|<span data-ttu-id="7e6e5-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="7e6e5-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e6e5-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="7e6e5-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="7e6e5-263">SRV</span><span class="sxs-lookup"><span data-stu-id="7e6e5-263">SRV</span></span>  <br/> |<span data-ttu-id="7e6e5-264">100</span><span class="sxs-lookup"><span data-stu-id="7e6e5-264">100</span></span>  <br/> |<span data-ttu-id="7e6e5-265">1 </span><span class="sxs-lookup"><span data-stu-id="7e6e5-265">1</span></span>  <br/> |<span data-ttu-id="7e6e5-266">443</span><span class="sxs-lookup"><span data-stu-id="7e6e5-266">443</span></span>  <br/> |<span data-ttu-id="7e6e5-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e6e5-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="7e6e5-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7e6e5-269">SRV</span><span class="sxs-lookup"><span data-stu-id="7e6e5-269">SRV</span></span>  <br/> |<span data-ttu-id="7e6e5-270">100</span><span class="sxs-lookup"><span data-stu-id="7e6e5-270">100</span></span>  <br/> |<span data-ttu-id="7e6e5-271">1 </span><span class="sxs-lookup"><span data-stu-id="7e6e5-271">1</span></span>  <br/> |<span data-ttu-id="7e6e5-272">5061</span><span class="sxs-lookup"><span data-stu-id="7e6e5-272">5061</span></span>  <br/> |<span data-ttu-id="7e6e5-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e6e5-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="7e6e5-275">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-275">Select **Save**.</span></span>
    
    ![Seleziona Salva](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="7e6e5-277">Usando i tre passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7e6e5-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7e6e5-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e6e5-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e6e5-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
