---
title: Creare record DNS in Dyn.com per Office 365
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Dyn.com per Office 365.
ms.openlocfilehash: d4471ec84555efb349cc1e42d5048ebf044735e5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244703"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="caee4-103">Creare record DNS in Dyn.com per Office 365</span><span class="sxs-lookup"><span data-stu-id="caee4-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="caee4-104">**Se non si trova ciò che si sta cercando, vedere le [domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="caee4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="caee4-105">Se il proprio provider di hosting DNS è Dyn.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="caee4-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="caee4-106">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="caee4-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="caee4-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="caee4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="caee4-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="caee4-110">Add a TXT record for verification</span></span>
<span data-ttu-id="caee4-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="caee4-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="caee4-p102">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="caee4-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="caee4-115">Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="caee4-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="caee4-116">Nella pagina **DNS** per il dominio, selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="caee4-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="caee4-117">Selezionare **Abilita interfaccia Expert**.</span><span class="sxs-lookup"><span data-stu-id="caee4-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="caee4-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="caee4-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="caee4-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="caee4-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="caee4-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="caee4-120">**Host**</span></span>|<span data-ttu-id="caee4-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="caee4-121">**TTL**</span></span>|<span data-ttu-id="caee4-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="caee4-122">**Type**</span></span>|<span data-ttu-id="caee4-123">**Dati**</span><span class="sxs-lookup"><span data-stu-id="caee4-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="caee4-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="caee4-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="caee4-125">600</span><span class="sxs-lookup"><span data-stu-id="caee4-125">600</span></span>  <br/> |<span data-ttu-id="caee4-126">TXT</span><span class="sxs-lookup"><span data-stu-id="caee4-126">TXT</span></span>  <br/> |<span data-ttu-id="caee4-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="caee4-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="caee4-p103">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="caee4-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Dyn-BP-Verify-1-1](../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="caee4-132">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="caee4-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="caee4-134">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="caee4-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="caee4-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="caee4-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="caee4-136">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="caee4-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="caee4-137">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="caee4-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="caee4-138">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="caee4-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="caee4-139">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="caee4-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="caee4-140">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="caee4-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="caee4-p104">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="caee4-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="caee4-144">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="caee4-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="caee4-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="caee4-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="caee4-p105">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="caee4-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="caee4-149">Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="caee4-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="caee4-150">Nella pagina DNS per il dominio, selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="caee4-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="caee4-151">Selezionare **Abilita interfaccia Expert**.</span><span class="sxs-lookup"><span data-stu-id="caee4-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="caee4-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="caee4-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="caee4-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="caee4-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="caee4-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="caee4-154">**Host**</span></span>|<span data-ttu-id="caee4-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="caee4-155">**TTL**</span></span>|<span data-ttu-id="caee4-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="caee4-156">**Type**</span></span>|<span data-ttu-id="caee4-157">**Dati**</span><span class="sxs-lookup"><span data-stu-id="caee4-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="caee4-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="caee4-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="caee4-159">600</span><span class="sxs-lookup"><span data-stu-id="caee4-159">600</span></span>  <br/> |<span data-ttu-id="caee4-160">MX</span><span class="sxs-lookup"><span data-stu-id="caee4-160">MX</span></span>  <br/> |<span data-ttu-id="caee4-161">10  *\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="caee4-162">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="caee4-p106">**10** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="caee4-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="caee4-165">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="caee4-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="caee4-166">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="caee4-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="caee4-167">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="caee4-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="caee4-169">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="caee4-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="caee4-171">Se sono presenti altri record MX, rimuoverli selezionando la casella di controllo per ognuno di essi nella colonna **Delete**.</span><span class="sxs-lookup"><span data-stu-id="caee4-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Fiori e testo](../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="caee4-173">Selezionare **Applica modifiche**.</span><span class="sxs-lookup"><span data-stu-id="caee4-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="caee4-175">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="caee4-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="caee4-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="caee4-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="caee4-p108">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="caee4-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="caee4-180">Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="caee4-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="caee4-181">Nella pagina **DNS** per il dominio, selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="caee4-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="caee4-182">Selezionare **Abilita interfaccia Expert**.</span><span class="sxs-lookup"><span data-stu-id="caee4-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="caee4-183">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="caee4-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="caee4-184">Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="caee4-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="caee4-185">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="caee4-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="caee4-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="caee4-186">**Host**</span></span>|<span data-ttu-id="caee4-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="caee4-187">**TTL**</span></span>|<span data-ttu-id="caee4-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="caee4-188">**Type**</span></span>|<span data-ttu-id="caee4-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="caee4-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="caee4-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="caee4-190">autodiscover</span></span>  <br/> |<span data-ttu-id="caee4-191">600</span><span class="sxs-lookup"><span data-stu-id="caee4-191">600</span></span>  <br/> |<span data-ttu-id="caee4-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="caee4-192">CNAME</span></span>  <br/> |<span data-ttu-id="caee4-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="caee4-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="caee4-195">sip</span><span class="sxs-lookup"><span data-stu-id="caee4-195">sip</span></span>  <br/> |<span data-ttu-id="caee4-196">600</span><span class="sxs-lookup"><span data-stu-id="caee4-196">600</span></span>  <br/> |<span data-ttu-id="caee4-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="caee4-197">CNAME</span></span>  <br/> |<span data-ttu-id="caee4-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="caee4-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="caee4-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="caee4-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="caee4-201">600</span><span class="sxs-lookup"><span data-stu-id="caee4-201">600</span></span>  <br/> |<span data-ttu-id="caee4-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="caee4-202">CNAME</span></span>  <br/> |<span data-ttu-id="caee4-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="caee4-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="caee4-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="caee4-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="caee4-206">600</span><span class="sxs-lookup"><span data-stu-id="caee4-206">600</span></span>  <br/> |<span data-ttu-id="caee4-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="caee4-207">CNAME</span></span>  <br/> |<span data-ttu-id="caee4-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="caee4-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="caee4-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="caee4-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="caee4-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="caee4-211">600</span><span class="sxs-lookup"><span data-stu-id="caee4-211">600</span></span>  <br/> |<span data-ttu-id="caee4-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="caee4-212">CNAME</span></span>  <br/> |<span data-ttu-id="caee4-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="caee4-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="caee4-216">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="caee4-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="caee4-218">Aggiungere i cinque record CNAME restanti.</span><span class="sxs-lookup"><span data-stu-id="caee4-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="caee4-219">Nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **create record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="caee4-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="caee4-220">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="caee4-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="caee4-221">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="caee4-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="caee4-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="caee4-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="caee4-223">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="caee4-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="caee4-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="caee4-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="caee4-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="caee4-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="caee4-226">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="caee4-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="caee4-p110">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="caee4-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermata della finestra Invita altre persone](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="caee4-230">Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="caee4-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="caee4-231">Nella pagina **DNS** per il dominio, selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="caee4-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="caee4-232">Selezionare **Abilita interfaccia Expert**.</span><span class="sxs-lookup"><span data-stu-id="caee4-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="caee4-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="caee4-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="caee4-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="caee4-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="caee4-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="caee4-235">**Host**</span></span>|<span data-ttu-id="caee4-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="caee4-236">**TTL**</span></span>|<span data-ttu-id="caee4-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="caee4-237">**Type**</span></span>|<span data-ttu-id="caee4-238">**Dati**</span><span class="sxs-lookup"><span data-stu-id="caee4-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="caee4-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="caee4-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="caee4-240">600</span><span class="sxs-lookup"><span data-stu-id="caee4-240">600</span></span>  <br/> |<span data-ttu-id="caee4-241">TXT</span><span class="sxs-lookup"><span data-stu-id="caee4-241">TXT</span></span>  <br/> |<span data-ttu-id="caee4-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="caee4-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="caee4-243">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="caee4-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="caee4-245">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="caee4-245">Select **Create Record**.</span></span>
    
    ![Campi multivalore](../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="caee4-247">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="caee4-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="caee4-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="caee4-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="caee4-249">Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="caee4-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="caee4-250">Verrà richiesto di eseguire l'accesso per primo</span><span class="sxs-lookup"><span data-stu-id="caee4-250">You'll be prompted to login first</span></span> 
    
    ![Schermata della finestra Invita altre persone](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="caee4-252">Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="caee4-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="caee4-253">Nella pagina **DNS** per il dominio, selezionare **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="caee4-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="caee4-254">Selezionare **Abilita interfaccia Expert**.</span><span class="sxs-lookup"><span data-stu-id="caee4-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="caee4-255">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="caee4-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="caee4-256">Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="caee4-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="caee4-257">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="caee4-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="caee4-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="caee4-258">**Host**</span></span>|<span data-ttu-id="caee4-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="caee4-259">**TTL**</span></span>|<span data-ttu-id="caee4-260">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="caee4-260">**Type**</span></span>|<span data-ttu-id="caee4-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="caee4-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="caee4-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="caee4-262">_sip._tls</span></span>|<span data-ttu-id="caee4-263">600</span><span class="sxs-lookup"><span data-stu-id="caee4-263">600</span></span>|<span data-ttu-id="caee4-264">SRV</span><span class="sxs-lookup"><span data-stu-id="caee4-264">SRV</span></span>|<span data-ttu-id="caee4-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="caee4-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="caee4-267">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="caee4-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="caee4-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="caee4-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="caee4-269">600</span><span class="sxs-lookup"><span data-stu-id="caee4-269">600</span></span>|<span data-ttu-id="caee4-270">SRV</span><span class="sxs-lookup"><span data-stu-id="caee4-270">SRV</span></span>|<span data-ttu-id="caee4-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="caee4-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="caee4-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="caee4-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="caee4-273">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="caee4-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="caee4-275">Selezionare **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="caee4-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="caee4-277">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="caee4-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="caee4-278">Nella sezione **Add DNS record** creare un record usando i valori della seconda riga della tabella e quindi selezionare di nuovo **create record** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="caee4-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="caee4-p114">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="caee4-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
