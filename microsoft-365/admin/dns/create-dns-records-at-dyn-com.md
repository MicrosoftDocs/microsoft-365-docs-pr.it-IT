---
title: Creare record DNS in Dyn.com per Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi in Dyn.com per Microsoft.
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910331"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="048e2-103">Creare record DNS in Dyn.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="048e2-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="048e2-104">**Se non si trova ciò che si sta cercando, vedere le [domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="048e2-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="048e2-105">Se il proprio provider di hosting DNS è Dyn.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="048e2-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="048e2-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="048e2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="048e2-109">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="048e2-109">Add a TXT record for verification</span></span>
<span data-ttu-id="048e2-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="048e2-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="048e2-p102">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="048e2-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="048e2-114">Nella pagina **Zone Level Services** selezionare **Dyn Standard DNS Service** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="048e2-115">Nella pagina **DNS** del dominio selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="048e2-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="048e2-116">Selezionare **Abilita interfaccia esperta.**</span><span class="sxs-lookup"><span data-stu-id="048e2-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="048e2-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="048e2-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="048e2-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="048e2-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="048e2-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="048e2-119">**Host**</span></span>|<span data-ttu-id="048e2-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="048e2-120">**TTL**</span></span>|<span data-ttu-id="048e2-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="048e2-121">**Type**</span></span>|<span data-ttu-id="048e2-122">**Dati**</span><span class="sxs-lookup"><span data-stu-id="048e2-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="048e2-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="048e2-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="048e2-124">600</span><span class="sxs-lookup"><span data-stu-id="048e2-124">600</span></span>  <br/> |<span data-ttu-id="048e2-125">TXT</span><span class="sxs-lookup"><span data-stu-id="048e2-125">TXT</span></span>  <br/> |<span data-ttu-id="048e2-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="048e2-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="048e2-127">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="048e2-127">**Note:** This is an example.</span></span> <span data-ttu-id="048e2-128">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="048e2-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="048e2-129">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="048e2-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="048e2-131">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="048e2-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="048e2-133">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="048e2-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="048e2-134">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="048e2-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="048e2-135">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="048e2-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="048e2-136">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="048e2-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="048e2-137">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="048e2-138">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="048e2-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="048e2-139">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="048e2-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="048e2-p104">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="048e2-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="048e2-143">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="048e2-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="048e2-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="048e2-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="048e2-p105">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="048e2-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="048e2-148">Nella pagina **Zone Level Services** selezionare **Dyn Standard DNS Service** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="048e2-149">Nella pagina DNS del dominio selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="048e2-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="048e2-150">Selezionare **Abilita interfaccia esperta.**</span><span class="sxs-lookup"><span data-stu-id="048e2-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="048e2-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="048e2-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="048e2-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="048e2-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="048e2-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="048e2-153">**Host**</span></span>|<span data-ttu-id="048e2-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="048e2-154">**TTL**</span></span>|<span data-ttu-id="048e2-155">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="048e2-155">**Type**</span></span>|<span data-ttu-id="048e2-156">**Dati**</span><span class="sxs-lookup"><span data-stu-id="048e2-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="048e2-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="048e2-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="048e2-158">600</span><span class="sxs-lookup"><span data-stu-id="048e2-158">600</span></span>  <br/> |<span data-ttu-id="048e2-159">MX</span><span class="sxs-lookup"><span data-stu-id="048e2-159">MX</span></span>  <br/> |<span data-ttu-id="048e2-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="048e2-161">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="048e2-p106">**10** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="048e2-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="048e2-164">**Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="048e2-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="048e2-165">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="048e2-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="048e2-166">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="048e2-166">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="048e2-168">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="048e2-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="048e2-170">Se sono presenti altri record MX, rimuoverli selezionando la casella di controllo per ognuno di essi nella colonna **Delete**.</span><span class="sxs-lookup"><span data-stu-id="048e2-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Fiori e testo](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="048e2-172">Selezionare **Applica modifiche.**</span><span class="sxs-lookup"><span data-stu-id="048e2-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="048e2-174">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="048e2-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="048e2-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="048e2-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="048e2-p108">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="048e2-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="048e2-179">Nella pagina **Zone Level Services** selezionare **Dyn Standard DNS Service** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="048e2-180">Nella pagina **DNS** del dominio selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="048e2-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="048e2-181">Selezionare **Abilita interfaccia esperta.**</span><span class="sxs-lookup"><span data-stu-id="048e2-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="048e2-182">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="048e2-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="048e2-183">Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="048e2-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="048e2-184">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="048e2-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="048e2-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="048e2-185">**Host**</span></span>|<span data-ttu-id="048e2-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="048e2-186">**TTL**</span></span>|<span data-ttu-id="048e2-187">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="048e2-187">**Type**</span></span>|<span data-ttu-id="048e2-188">**Dati**</span><span class="sxs-lookup"><span data-stu-id="048e2-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="048e2-189">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="048e2-189">autodiscover</span></span>  <br/> |<span data-ttu-id="048e2-190">600</span><span class="sxs-lookup"><span data-stu-id="048e2-190">600</span></span>  <br/> |<span data-ttu-id="048e2-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="048e2-191">CNAME</span></span>  <br/> |<span data-ttu-id="048e2-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="048e2-193">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="048e2-194">sip</span><span class="sxs-lookup"><span data-stu-id="048e2-194">sip</span></span>  <br/> |<span data-ttu-id="048e2-195">600</span><span class="sxs-lookup"><span data-stu-id="048e2-195">600</span></span>  <br/> |<span data-ttu-id="048e2-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="048e2-196">CNAME</span></span>  <br/> |<span data-ttu-id="048e2-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="048e2-198">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="048e2-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="048e2-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="048e2-200">600</span><span class="sxs-lookup"><span data-stu-id="048e2-200">600</span></span>  <br/> |<span data-ttu-id="048e2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="048e2-201">CNAME</span></span>  <br/> |<span data-ttu-id="048e2-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="048e2-203">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="048e2-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="048e2-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="048e2-205">600</span><span class="sxs-lookup"><span data-stu-id="048e2-205">600</span></span>  <br/> |<span data-ttu-id="048e2-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="048e2-206">CNAME</span></span>  <br/> |<span data-ttu-id="048e2-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="048e2-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="048e2-208">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="048e2-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="048e2-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="048e2-210">600</span><span class="sxs-lookup"><span data-stu-id="048e2-210">600</span></span>  <br/> |<span data-ttu-id="048e2-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="048e2-211">CNAME</span></span>  <br/> |<span data-ttu-id="048e2-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="048e2-213">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="048e2-215">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="048e2-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="048e2-217">Aggiungere i cinque record CNAME restanti.</span><span class="sxs-lookup"><span data-stu-id="048e2-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="048e2-218">Nella sezione **Add DNS Record** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo Create **Record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="048e2-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="048e2-219">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="048e2-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="048e2-220">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="048e2-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="048e2-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="048e2-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="048e2-222">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="048e2-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="048e2-223">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="048e2-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="048e2-224">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="048e2-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="048e2-225">Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="048e2-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="048e2-p110">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="048e2-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="048e2-229">Nella pagina **Zone Level Services** selezionare **Dyn Standard DNS Service** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="048e2-230">Nella pagina **DNS** del dominio selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="048e2-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="048e2-231">Selezionare **Abilita interfaccia esperta.**</span><span class="sxs-lookup"><span data-stu-id="048e2-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="048e2-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="048e2-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="048e2-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="048e2-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="048e2-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="048e2-234">**Host**</span></span>|<span data-ttu-id="048e2-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="048e2-235">**TTL**</span></span>|<span data-ttu-id="048e2-236">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="048e2-236">**Type**</span></span>|<span data-ttu-id="048e2-237">**Dati**</span><span class="sxs-lookup"><span data-stu-id="048e2-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="048e2-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="048e2-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="048e2-239">600</span><span class="sxs-lookup"><span data-stu-id="048e2-239">600</span></span>  <br/> |<span data-ttu-id="048e2-240">TXT</span><span class="sxs-lookup"><span data-stu-id="048e2-240">TXT</span></span>  <br/> |<span data-ttu-id="048e2-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="048e2-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="048e2-242">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="048e2-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="048e2-244">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="048e2-244">Select **Create Record**.</span></span>
    
    ![Campi multivalore](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="048e2-246">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="048e2-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="048e2-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="048e2-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="048e2-248">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="048e2-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="048e2-249">Verrà richiesto di eseguire prima l'accesso</span><span class="sxs-lookup"><span data-stu-id="048e2-249">You'll be prompted to login first</span></span> 
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="048e2-251">Nella pagina **Zone Level Services** selezionare **Dyn Standard DNS Service** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="048e2-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="048e2-252">Nella pagina **DNS** del dominio selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="048e2-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="048e2-253">Selezionare **Abilita interfaccia esperta.**</span><span class="sxs-lookup"><span data-stu-id="048e2-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="048e2-254">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="048e2-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="048e2-255">Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="048e2-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="048e2-256">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="048e2-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="048e2-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="048e2-257">**Host**</span></span>|<span data-ttu-id="048e2-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="048e2-258">**TTL**</span></span>|<span data-ttu-id="048e2-259">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="048e2-259">**Type**</span></span>|<span data-ttu-id="048e2-260">**Dati**</span><span class="sxs-lookup"><span data-stu-id="048e2-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="048e2-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="048e2-261">_sip._tls</span></span>|<span data-ttu-id="048e2-262">600</span><span class="sxs-lookup"><span data-stu-id="048e2-262">600</span></span>|<span data-ttu-id="048e2-263">SRV</span><span class="sxs-lookup"><span data-stu-id="048e2-263">SRV</span></span>|<span data-ttu-id="048e2-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="048e2-265">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="048e2-266">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="048e2-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="048e2-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="048e2-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="048e2-268">600</span><span class="sxs-lookup"><span data-stu-id="048e2-268">600</span></span>|<span data-ttu-id="048e2-269">SRV</span><span class="sxs-lookup"><span data-stu-id="048e2-269">SRV</span></span>|<span data-ttu-id="048e2-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="048e2-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="048e2-271">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="048e2-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="048e2-272">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="048e2-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="048e2-274">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="048e2-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="048e2-276">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="048e2-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="048e2-277">Nella sezione **Add DNS Record** creare un record utilizzando i valori della seconda riga della tabella e quindi selezionare di nuovo Create **Record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="048e2-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="048e2-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="048e2-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
