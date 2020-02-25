---
title: Modificare i server dei nomi per configurare Office 365 con Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Informazioni su come configurare il dominio personalizzato di Office 365 con namecheap se si desidera che Office 365 gestisca i record DNS. '
ms.openlocfilehash: caf0a484b82ecf10f2835ae8fd5dea98c16e61c3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242660"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="e4253-103">Modificare i server dei nomi per configurare Office 365 con Namecheap</span><span class="sxs-lookup"><span data-stu-id="e4253-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="e4253-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e4253-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="e4253-p101">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365. Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 su Namecheap](create-dns-records-at-namecheap.md).</span><span class="sxs-lookup"><span data-stu-id="e4253-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e4253-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="e4253-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="e4253-p102">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="e4253-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e4253-111">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e4253-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e4253-113">Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="e4253-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e4253-115">Selezionare **DNS avanzato**.</span><span class="sxs-lookup"><span data-stu-id="e4253-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e4253-117">Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="e4253-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="e4253-119">Nell'elenco a discesa **Type** selezionare **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="e4253-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4253-120">L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="e4253-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="e4253-122">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e4253-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e4253-123">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e4253-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="e4253-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e4253-124">**Type**</span></span>|<span data-ttu-id="e4253-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="e4253-125">**Host**</span></span>|<span data-ttu-id="e4253-126">**Valore**</span><span class="sxs-lookup"><span data-stu-id="e4253-126">**Value**</span></span>|<span data-ttu-id="e4253-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e4253-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4253-128">TXT</span><span class="sxs-lookup"><span data-stu-id="e4253-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e4253-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e4253-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e4253-130">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="e4253-130">**Note**: This is an example.</span></span> <span data-ttu-id="e4253-131">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4253-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="e4253-132">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="e4253-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e4253-133">30 min</span><span class="sxs-lookup"><span data-stu-id="e4253-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="e4253-135">Selezionare il controllo **Salva modifiche** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="e4253-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="e4253-137">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="e4253-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e4253-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="e4253-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e4253-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="e4253-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e4253-140">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="e4253-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e4253-141">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="e4253-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e4253-142">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="e4253-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e4253-143">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="e4253-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e4253-p104">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e4253-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e4253-147">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="e4253-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="e4253-p105">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="e4253-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e4253-p106">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio. Ad esempio, dopo questa modifica tutta la posta elettronica inviata al dominio (come roberto@ *nome_dominio*  .com) inizierà a essere recapitata a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4253-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="e4253-153">Una volta completata la procedura descritta in questa sezione, dovrebbero essere elencati  *solo*  questi quattro server dei nomi: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  La seguente procedura illustra come eliminare eventuali altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi  *corretti*  se non sono presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e4253-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="e4253-p107">Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.</span><span class="sxs-lookup"><span data-stu-id="e4253-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e4253-157">Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e4253-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e4253-159">Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="e4253-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e4253-161">Selezionare **dominio**.</span><span class="sxs-lookup"><span data-stu-id="e4253-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="e4253-163">Trovare la sezione **NAMESERVERS** e quindi selezionare **Custom** dall'elenco a discesa **Namecheap Default**.</span><span class="sxs-lookup"><span data-stu-id="e4253-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="e4253-165">A seconda del fatto che siano già presenti o meno i server dei nomi elencati nella pagina visualizzata, continuare con una delle due procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="e4253-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="e4253-166">Se NON sono già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="e4253-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="e4253-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="e4253-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="e4253-168">Fare doppio clic su **Aggiungi server dei nomi** per aggiungere due nuove righe.</span><span class="sxs-lookup"><span data-stu-id="e4253-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="e4253-170">Nelle caselle **Nameserver** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e4253-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="e4253-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="e4253-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="e4253-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="e4253-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="e4253-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="e4253-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="e4253-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="e4253-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="e4253-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="e4253-180">Selezionare il controllo **Salva** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="e4253-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="e4253-p108">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="e4253-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="e4253-184">Se SONO già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="e4253-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="e4253-p109">Seguire questa procedura  *solo*  se sono presenti server dei nomi diversi dai quattro server dei nomi  *corretti*  . In altre parole, eliminare  *solo*  eventuali server dei nomi  *diversi*  da **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="e4253-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="e4253-187">Se sono già elencati altri server dei nomi nelle caselle **Nameserver**, eliminarli selezionando ogni server e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="e4253-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="e4253-189">Fare doppio clic su **Aggiungi server dei nomi** per aggiungere due nuove righe.</span><span class="sxs-lookup"><span data-stu-id="e4253-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="e4253-191">Nelle caselle **Nameserver** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e4253-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="e4253-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="e4253-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="e4253-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="e4253-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="e4253-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="e4253-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="e4253-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e4253-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="e4253-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="e4253-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e4253-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="e4253-201">Selezionare il controllo **Salva** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="e4253-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="e4253-p110">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="e4253-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>