---
title: Modificare i server dei nomi per configurare Microsoft con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Informazioni su come è possibile configurare Microsoft per gestire i record DNS del dominio personalizzato in Hostgator.
ms.openlocfilehash: 09f0409ed2a5f81b450c9aae7bb3699373ce6f22
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629888"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="1bdcb-103">Modificare i server dei nomi per configurare Microsoft 365 con Hostgator</span><span class="sxs-lookup"><span data-stu-id="1bdcb-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="1bdcb-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="1bdcb-105">Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="1bdcb-106">Se si preferisce, è possibile [gestire tutti i record Microsoft DNS su Hostgator](create-dns-records-at-hostgator.md).</span><span class="sxs-lookup"><span data-stu-id="1bdcb-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="1bdcb-107">Associare il dominio all'account di hosting.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bdcb-108">È necessario eseguire questa procedura prima di quella illustrata nella sezione seguente, **Aggiungere un record TXT a scopo di verifica**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="1bdcb-109">Seguire questa procedura per associare il dominio e gli account di hosting.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="1bdcb-p102">Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="1bdcb-113">Selezionare la scheda **domini** .</span><span class="sxs-lookup"><span data-stu-id="1bdcb-113">Select the **Domains** tab.</span></span>
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="1bdcb-115">Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="1bdcb-117">Nell'area **Name Servers** della pagina **Domains Overview** selezionare **Change**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="1bdcb-119">Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="1bdcb-121">Selezionare **Save Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1bdcb-123">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="1bdcb-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bdcb-124">Prima di eseguire questa procedura, è necessario prima eseguire la procedura nella prima sezione di questo articolo, [puntare il dominio all'account di hosting.](#point-your-domain-to-your-hosting-account)</span><span class="sxs-lookup"><span data-stu-id="1bdcb-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="1bdcb-125">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-125">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="1bdcb-126">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-126">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bdcb-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="1bdcb-p105">Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="1bdcb-p106">A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Tale indirizzo sarà specificato nel messaggio di posta elettronica di iscrizione ricevuto da Hostgator.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1bdcb-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="1bdcb-135">Per iniziare, è possibile acquistare un account di hosting da Hostgator o [modificare i record del server dei nomi del dominio](#change-your-domains-nameserver-ns-records) in modo che puntino a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="1bdcb-136">Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced DNS zone editor**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="1bdcb-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1bdcb-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="1bdcb-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1bdcb-139">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bdcb-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-140">**Name**</span></span> <br/> |<span data-ttu-id="1bdcb-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-141">**TTL**</span></span> <br/> |<span data-ttu-id="1bdcb-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-142">**Type**</span></span> <br/> |<span data-ttu-id="1bdcb-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="1bdcb-p108">Usare il proprio  *nome_dominio*  , ad esempio fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="1bdcb-146">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1bdcb-147">1 </span><span class="sxs-lookup"><span data-stu-id="1bdcb-147">1</span></span>  <br/> |<span data-ttu-id="1bdcb-148">TXT</span><span class="sxs-lookup"><span data-stu-id="1bdcb-148">TXT</span></span>  <br/> |<span data-ttu-id="1bdcb-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1bdcb-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1bdcb-150">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-150">**Note:** This is an example.</span></span> <span data-ttu-id="1bdcb-151">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1bdcb-152">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1bdcb-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="1bdcb-153">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="1bdcb-154">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1bdcb-155">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="1bdcb-156">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1bdcb-157">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1bdcb-158">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1bdcb-159">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1bdcb-160">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1bdcb-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1bdcb-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1bdcb-163">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1bdcb-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="1bdcb-164">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="1bdcb-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="1bdcb-165">Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="1bdcb-166">Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="1bdcb-167">Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1bdcb-168">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="1bdcb-169">Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain* . com) inizierà a venire a Microsoft dopo aver apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1bdcb-170">Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="1bdcb-171">Dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi che devono essere elencati sono questi quattro: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**e **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="1bdcb-p114">Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="1bdcb-175">Selezionare la scheda **domini** .</span><span class="sxs-lookup"><span data-stu-id="1bdcb-175">Select the **Domains** tab.</span></span> 
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="1bdcb-177">Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="1bdcb-179">Nell'area **Name Servers** della pagina **Domain Overview** selezionare **Change**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="1bdcb-181">Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="1bdcb-183">Selezionare **imposta manualmente i server My Name**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="1bdcb-185">**Attenzione**: attenersi alla seguente procedura solo se sono presenti server dei nomi diversi dai quattro nameserver corretti.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="1bdcb-186">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="1bdcb-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="1bdcb-187">Sempre nella pagina **Name Servers** del dominio, eliminare ognuno dei server dei nomi presenti nell'elenco selezionandolo e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![O365_proceduraguidata_Aggiungidominio_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="1bdcb-189">Sempre nell'elenco dei server dei nomi, digitare oppure copiare e incollare i primi due valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="1bdcb-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="1bdcb-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1bdcb-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1bdcb-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="1bdcb-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1bdcb-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1bdcb-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="1bdcb-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1bdcb-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1bdcb-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="1bdcb-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="1bdcb-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1bdcb-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="1bdcb-199">Aggiungere gli altri valori dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="1bdcb-200">Selezionare **(+)** Aggiungi, quindi digitare oppure copiare e incollare il valore della riga successiva della tabella nella casella relativa al record.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="1bdcb-201">Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="1bdcb-203">Selezionare **Save Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="1bdcb-205">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="1bdcb-206">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdcb-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
