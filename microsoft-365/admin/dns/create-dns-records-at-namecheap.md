---
title: Creare record DNS in Namecheap per Microsoft
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Namecheap per Microsoft.
ms.openlocfilehash: 2b55e529ab4a66dbada95914f213807884b4b6c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629336"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="0851a-103">Creare record DNS in Namecheap per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0851a-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="0851a-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0851a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0851a-105">Se il proprio provider di hosting DNS è Namecheap, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="0851a-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0851a-106">Dopo aver aggiunto questi record in Namecheap, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0851a-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0851a-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0851a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0851a-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="0851a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0851a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0851a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0851a-112">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="0851a-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="0851a-113">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="0851a-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0851a-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="0851a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0851a-116">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0851a-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="0851a-p104">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="0851a-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="0851a-120">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="0851a-122">Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0851a-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="0851a-124">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0851a-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="0851a-126">Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="0851a-128">Nell'elenco a discesa **Type** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0851a-129">L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="0851a-131">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0851a-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0851a-132">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0851a-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0851a-133">**Type**</span></span>|<span data-ttu-id="0851a-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="0851a-134">**Host**</span></span>|<span data-ttu-id="0851a-135">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0851a-135">**Value**</span></span>|<span data-ttu-id="0851a-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0851a-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0851a-137">TXT</span><span class="sxs-lookup"><span data-stu-id="0851a-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="0851a-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0851a-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="0851a-139">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="0851a-139">**Note:** This is an example.</span></span> <span data-ttu-id="0851a-140">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="0851a-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="0851a-141">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="0851a-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0851a-142">30 min</span><span class="sxs-lookup"><span data-stu-id="0851a-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="0851a-144">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="0851a-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="0851a-146">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="0851a-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0851a-147">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="0851a-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0851a-148">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="0851a-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0851a-149">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="0851a-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0851a-150">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="0851a-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0851a-151">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="0851a-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0851a-152">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="0851a-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="0851a-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0851a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0851a-156">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0851a-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0851a-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0851a-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0851a-158">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0851a-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="0851a-p107">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="0851a-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="0851a-162">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="0851a-164">Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0851a-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="0851a-166">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0851a-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="0851a-168">Nella sezione **MAIL SETTINGS** selezionare **Custom MX** dall'elenco a discesa **Email Forwarding**.</span><span class="sxs-lookup"><span data-stu-id="0851a-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="0851a-169">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0851a-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="0851a-171">Selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="0851a-173">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente</span><span class="sxs-lookup"><span data-stu-id="0851a-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="0851a-174">(la casella **Priority** è quella senza nome accanto alla casella **Value**.</span><span class="sxs-lookup"><span data-stu-id="0851a-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="0851a-175">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0851a-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0851a-176">**Type**</span></span>|<span data-ttu-id="0851a-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="0851a-177">**Host**</span></span>|<span data-ttu-id="0851a-178">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0851a-178">**Value**</span></span>|<span data-ttu-id="0851a-179">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="0851a-179">**Priority**</span></span>|<span data-ttu-id="0851a-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0851a-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0851a-181">Record MX</span><span class="sxs-lookup"><span data-stu-id="0851a-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="0851a-182">\<*Domain-Key*\>. mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0851a-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0851a-184">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0851a-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="0851a-185">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="0851a-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0851a-186">0</span><span class="sxs-lookup"><span data-stu-id="0851a-186">0</span></span>  <br/> <span data-ttu-id="0851a-187">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="0851a-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="0851a-188">30 min</span><span class="sxs-lookup"><span data-stu-id="0851a-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="0851a-190">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="0851a-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="0851a-192">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="0851a-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="0851a-193">In primo luogo, selezionare l' **icona di eliminazione** (Cestino) per il record che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="0851a-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="0851a-195">In secondo luogo, selezionare **Sì** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="0851a-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="0851a-197">Rimuovere tutti i record MX, ad eccezione di quello aggiunto in precedenza in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0851a-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0851a-198">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0851a-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0851a-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0851a-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0851a-200">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0851a-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="0851a-p110">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="0851a-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="0851a-204">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="0851a-206">Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0851a-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="0851a-208">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0851a-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="0851a-210">Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="0851a-212">Nell'elenco a discesa **Type** selezionare **CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0851a-213">L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="0851a-215">Nelle caselle vuote del nuovo record selezionare **CNAME** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0851a-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="0851a-216">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0851a-216">**Type**</span></span>|<span data-ttu-id="0851a-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="0851a-217">**Host**</span></span>|<span data-ttu-id="0851a-218">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0851a-218">**Value**</span></span>|<span data-ttu-id="0851a-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0851a-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0851a-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="0851a-220">CNAME</span></span>  <br/> |<span data-ttu-id="0851a-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0851a-221">autodiscover</span></span>  <br/> |<span data-ttu-id="0851a-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0851a-223">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-224">3600</span><span class="sxs-lookup"><span data-stu-id="0851a-224">3600</span></span>  <br/> |
    |<span data-ttu-id="0851a-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="0851a-225">CNAME</span></span>  <br/> |<span data-ttu-id="0851a-226">sip</span><span class="sxs-lookup"><span data-stu-id="0851a-226">sip</span></span>  <br/> |<span data-ttu-id="0851a-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0851a-228">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-229">3600</span><span class="sxs-lookup"><span data-stu-id="0851a-229">3600</span></span>  <br/> |
    |<span data-ttu-id="0851a-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="0851a-230">CNAME</span></span>  <br/> |<span data-ttu-id="0851a-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0851a-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0851a-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0851a-233">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-234">3600</span><span class="sxs-lookup"><span data-stu-id="0851a-234">3600</span></span>  <br/> |
    |<span data-ttu-id="0851a-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="0851a-235">CNAME</span></span>  <br/> |<span data-ttu-id="0851a-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0851a-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0851a-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0851a-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0851a-238">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-239">3600</span><span class="sxs-lookup"><span data-stu-id="0851a-239">3600</span></span>  <br/> |
    |<span data-ttu-id="0851a-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="0851a-240">CNAME</span></span>  <br/> |<span data-ttu-id="0851a-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0851a-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0851a-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0851a-243">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-244">3600</span><span class="sxs-lookup"><span data-stu-id="0851a-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="0851a-246">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="0851a-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="0851a-248">Utilizzando i quattro passaggi precedenti e i valori delle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="0851a-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0851a-249">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="0851a-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0851a-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0851a-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0851a-251">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="0851a-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0851a-252">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0851a-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0851a-253">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0851a-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0851a-254">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="0851a-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="0851a-255">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0851a-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="0851a-p112">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="0851a-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="0851a-258">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="0851a-260">Nella pagina **elenco dei domini** individuare il nome del dominio che si desidera modificare e quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0851a-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="0851a-262">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0851a-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="0851a-264">Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="0851a-266">Nell'elenco a discesa **Type** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0851a-267">L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="0851a-269">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0851a-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="0851a-270">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0851a-271">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0851a-271">**Type**</span></span>|<span data-ttu-id="0851a-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="0851a-272">**Host**</span></span>|<span data-ttu-id="0851a-273">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0851a-273">**Value**</span></span>|<span data-ttu-id="0851a-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0851a-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0851a-275">TXT</span><span class="sxs-lookup"><span data-stu-id="0851a-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="0851a-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0851a-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0851a-277">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="0851a-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="0851a-278">30 min</span><span class="sxs-lookup"><span data-stu-id="0851a-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="0851a-280">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="0851a-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0851a-282">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0851a-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0851a-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0851a-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0851a-p113">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0851a-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="0851a-287">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0851a-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="0851a-289">Nella pagina **elenco dei domini** individuare il nome del dominio che si desidera modificare e quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0851a-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="0851a-291">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0851a-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="0851a-293">Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="0851a-295">Nell'elenco a discesa **Type** selezionare **SRV Record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0851a-296">L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="0851a-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="0851a-298">Nelle caselle vuote dei nuovi record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0851a-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="0851a-299">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="0851a-299">**Service**</span></span>|<span data-ttu-id="0851a-300">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="0851a-300">**Protocol**</span></span>|<span data-ttu-id="0851a-301">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="0851a-301">**Priority**</span></span>|<span data-ttu-id="0851a-302">**Peso**</span><span class="sxs-lookup"><span data-stu-id="0851a-302">**Weight**</span></span>|<span data-ttu-id="0851a-303">**Porta**</span><span class="sxs-lookup"><span data-stu-id="0851a-303">**Port**</span></span>|<span data-ttu-id="0851a-304">**Target**</span><span class="sxs-lookup"><span data-stu-id="0851a-304">**Target**</span></span>|<span data-ttu-id="0851a-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0851a-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0851a-306">_sip</span><span class="sxs-lookup"><span data-stu-id="0851a-306">_sip</span></span>  <br/> |<span data-ttu-id="0851a-307">_tls</span><span class="sxs-lookup"><span data-stu-id="0851a-307">_tls</span></span>  <br/> |<span data-ttu-id="0851a-308">100</span><span class="sxs-lookup"><span data-stu-id="0851a-308">100</span></span>  <br/> |<span data-ttu-id="0851a-309">1 </span><span class="sxs-lookup"><span data-stu-id="0851a-309">1</span></span>  <br/> |<span data-ttu-id="0851a-310">443</span><span class="sxs-lookup"><span data-stu-id="0851a-310">443</span></span>  <br/> |<span data-ttu-id="0851a-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0851a-312">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-313">30 min</span><span class="sxs-lookup"><span data-stu-id="0851a-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="0851a-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0851a-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="0851a-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="0851a-315">_tcp</span></span>  <br/> |<span data-ttu-id="0851a-316">100</span><span class="sxs-lookup"><span data-stu-id="0851a-316">100</span></span>  <br/> |<span data-ttu-id="0851a-317">1 </span><span class="sxs-lookup"><span data-stu-id="0851a-317">1</span></span>  <br/> |<span data-ttu-id="0851a-318">5061</span><span class="sxs-lookup"><span data-stu-id="0851a-318">5061</span></span>  <br/> |<span data-ttu-id="0851a-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0851a-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="0851a-320">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0851a-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0851a-321">30 min</span><span class="sxs-lookup"><span data-stu-id="0851a-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="0851a-323">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="0851a-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="0851a-325">Usando i quattro passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="0851a-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0851a-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0851a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
