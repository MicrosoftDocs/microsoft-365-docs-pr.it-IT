---
title: Modificare i server dei nomi per configurare Office 365 con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Informazioni su come configurare Office 365 per gestire i record DNS del dominio personalizzato in Hostgator.
ms.openlocfilehash: f0d3b495285685c3f666560816f99b07a1a5f6d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242743"
---
# <a name="change-nameservers-to-set-up-office-365-with-hostgator"></a><span data-ttu-id="8639a-103">Modificare i server dei nomi per configurare Office 365 con Hostgator</span><span class="sxs-lookup"><span data-stu-id="8639a-103">Change nameservers to set up Office 365 with Hostgator</span></span>

 <span data-ttu-id="8639a-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8639a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="8639a-p101">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365. Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 su Hostgator](create-dns-records-at-hostgator.md).</span><span class="sxs-lookup"><span data-stu-id="8639a-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="8639a-107">Associare il dominio all'account di hosting.</span><span class="sxs-lookup"><span data-stu-id="8639a-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8639a-108">È necessario eseguire questa procedura prima di quella illustrata nella sezione seguente, **Aggiungere un record TXT a scopo di verifica**.</span><span class="sxs-lookup"><span data-stu-id="8639a-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="8639a-109">Seguire questa procedura per associare il dominio e gli account di hosting.</span><span class="sxs-lookup"><span data-stu-id="8639a-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="8639a-p102">Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8639a-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Connessione dell'elenco attività a Outlook](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="8639a-113">Selezionare la scheda **domini** .</span><span class="sxs-lookup"><span data-stu-id="8639a-113">Select the **Domains** tab.</span></span>
    
    ![Barra multifunzione di Office 2010](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="8639a-115">Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="8639a-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="8639a-117">Nell'area **Name Servers** della pagina **Domains Overview** selezionare **Change**.</span><span class="sxs-lookup"><span data-stu-id="8639a-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Immagine del pulsante Imposta colore trasparente](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="8639a-119">Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio.</span><span class="sxs-lookup"><span data-stu-id="8639a-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Dashboard di Power BI](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="8639a-121">Selezionare **Save Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="8639a-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8639a-123">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="8639a-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8639a-124">Prima di eseguire questa procedura, è necessario prima eseguire la procedura nella prima sezione di questo articolo, [puntare il dominio all'account di hosting.](#point-your-domain-to-your-hosting-account)</span><span class="sxs-lookup"><span data-stu-id="8639a-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="8639a-p103">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="8639a-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8639a-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="8639a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="8639a-p105">Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8639a-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="8639a-p106">A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Tale indirizzo sarà specificato nel messaggio di posta elettronica di iscrizione ricevuto da Hostgator.</span><span class="sxs-lookup"><span data-stu-id="8639a-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8639a-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="8639a-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="8639a-135">Per iniziare a usare Office 365, è possibile acquistare un account di hosting da Hostgator o [modificare i record del server dei nomi del dominio](#change-your-domains-nameserver-ns-records) in modo che puntino a Office 365.</span><span class="sxs-lookup"><span data-stu-id="8639a-135">To get started with Office 365, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Office 365.</span></span> 
  
2. <span data-ttu-id="8639a-136">Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced DNS zone editor**.</span><span class="sxs-lookup"><span data-stu-id="8639a-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="8639a-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8639a-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="8639a-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8639a-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8639a-139">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8639a-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8639a-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="8639a-140">**Name**</span></span> <br/> |<span data-ttu-id="8639a-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8639a-141">**TTL**</span></span> <br/> |<span data-ttu-id="8639a-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="8639a-142">**Type**</span></span> <br/> |<span data-ttu-id="8639a-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="8639a-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="8639a-p108">Usare il proprio  *nome_dominio*  , ad esempio fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="8639a-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="8639a-146">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="8639a-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8639a-147">1</span><span class="sxs-lookup"><span data-stu-id="8639a-147">1</span></span>  <br/> |<span data-ttu-id="8639a-148">TXT</span><span class="sxs-lookup"><span data-stu-id="8639a-148">TXT</span></span>  <br/> |<span data-ttu-id="8639a-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8639a-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8639a-150">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="8639a-150">**Note:** This is an example.</span></span> <span data-ttu-id="8639a-151">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8639a-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="8639a-152">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8639a-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="8639a-153">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="8639a-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="8639a-154">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="8639a-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8639a-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="8639a-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8639a-156">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="8639a-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8639a-157">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="8639a-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8639a-158">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="8639a-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8639a-159">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="8639a-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8639a-160">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="8639a-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8639a-p110">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8639a-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8639a-164">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="8639a-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8639a-p111">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="8639a-p111">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8639a-p112">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio. Ad esempio, dopo questa modifica tutta la posta elettronica inviata al dominio (come roberto@ *nome_dominio*  .com) inizierà a essere recapitata a Office 365.</span><span class="sxs-lookup"><span data-stu-id="8639a-p112">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8639a-170">Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati.</span><span class="sxs-lookup"><span data-stu-id="8639a-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="8639a-171">Dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi che devono essere elencati sono questi quattro: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**e **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="8639a-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="8639a-p114">Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8639a-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Connessione dell'elenco attività a Outlook](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="8639a-175">Selezionare la scheda **domini** .</span><span class="sxs-lookup"><span data-stu-id="8639a-175">Select the **Domains** tab.</span></span> 
    
    ![Barra multifunzione di Office 2010](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="8639a-177">Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="8639a-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="8639a-179">Nell'area **Name Servers** della pagina **Domain Overview** selezionare **Change**.</span><span class="sxs-lookup"><span data-stu-id="8639a-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Immagine del pulsante Imposta colore trasparente](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="8639a-181">Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio.</span><span class="sxs-lookup"><span data-stu-id="8639a-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Dashboard di Power BI](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="8639a-183">Selezionare **imposta manualmente i server My Name**.</span><span class="sxs-lookup"><span data-stu-id="8639a-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="8639a-185">**Attenzione**: attenersi alla seguente procedura solo se sono presenti server dei nomi diversi dai quattro nameserver corretti.</span><span class="sxs-lookup"><span data-stu-id="8639a-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="8639a-186">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="8639a-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="8639a-187">Sempre nella pagina **Name Servers** del dominio, eliminare ognuno dei server dei nomi presenti nell'elenco selezionandolo e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="8639a-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![O365_proceduraguidata_Aggiungidominio_1_7a](../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="8639a-189">Sempre nell'elenco dei server dei nomi, digitare oppure copiare e incollare i primi due valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8639a-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8639a-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="8639a-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="8639a-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8639a-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8639a-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="8639a-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="8639a-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8639a-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8639a-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="8639a-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="8639a-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8639a-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8639a-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="8639a-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="8639a-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8639a-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="8639a-199">Aggiungere gli altri valori dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8639a-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="8639a-200">Selezionare **(+)** Aggiungi, quindi digitare oppure copiare e incollare il valore della riga successiva della tabella nella casella relativa al record.</span><span class="sxs-lookup"><span data-stu-id="8639a-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="8639a-201">Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8639a-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="8639a-203">Selezionare **Save Name Servers**.</span><span class="sxs-lookup"><span data-stu-id="8639a-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="8639a-p116">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="8639a-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>