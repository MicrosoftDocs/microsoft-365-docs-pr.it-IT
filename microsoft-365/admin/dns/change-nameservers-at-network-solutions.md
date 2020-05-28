---
title: Modificare i server dei nomi per configurare Microsoft con le soluzioni di rete
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Informazioni su come configurare il dominio personalizzato Microsoft con le soluzioni di rete se si desidera che Microsoft gestisca i record DNS. '
ms.openlocfilehash: 4a7c1eaab132b0ab41a62ba62d87956ccfafc014
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400606"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="62959-103">Modificare i server dei nomi per configurare Microsoft con le soluzioni di rete</span><span class="sxs-lookup"><span data-stu-id="62959-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="62959-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="62959-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="62959-105">Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="62959-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="62959-106">Se si preferisce, è possibile [gestire tutti i record Microsoft DNS in Network Solutions](create-dns-records-at-network-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="62959-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="62959-107">Aggiungere un record TXT su Network Solutions per verificare che si è proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="62959-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="62959-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="62959-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62959-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="62959-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="62959-112">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="62959-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="62959-p104">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="62959-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="62959-115">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="62959-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="62959-117">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="62959-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="62959-119">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="62959-119">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="62959-121">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="62959-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="62959-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="62959-122">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="62959-124">Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.</span><span class="sxs-lookup"><span data-stu-id="62959-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selezionare Modifica record TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="62959-126">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="62959-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="62959-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="62959-127">**Host**</span></span>|<span data-ttu-id="62959-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62959-128">**TTL**</span></span>|<span data-ttu-id="62959-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="62959-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="62959-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="62959-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="62959-131">3600</span><span class="sxs-lookup"><span data-stu-id="62959-131">3600</span></span>  <br/> |<span data-ttu-id="62959-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="62959-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="62959-133">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="62959-133">**Note**: This is an example.</span></span> <span data-ttu-id="62959-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62959-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="62959-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="62959-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="62959-137">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="62959-137">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="62959-139">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="62959-139">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="62959-141">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="62959-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="62959-142">Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="62959-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="62959-143">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="62959-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="62959-144">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="62959-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="62959-145">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="62959-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="62959-146">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="62959-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="62959-147">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="62959-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="62959-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="62959-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="62959-151">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="62959-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="62959-152">Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62959-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="62959-153">Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="62959-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="62959-154">Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="62959-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="62959-155">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="62959-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="62959-156">Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain* . com) inizierà a venire a Microsoft dopo aver apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="62959-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="62959-157">Pronto per modificare i record NS in modo che Microsoft possa configurare il dominio?</span><span class="sxs-lookup"><span data-stu-id="62959-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="62959-158">Seguire le istruzioni riportate di seguito o [guardare il video (iniziare da 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="62959-158">Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="62959-159">Dopo aver completato la procedura descritta in questa sezione, gli *unici* server dei nomi che devono essere elencati sono questi quattro: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**e **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="62959-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="62959-160">La seguente procedura illustra come eliminare eventuali altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi  *corretti*  se non sono presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="62959-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="62959-161">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="62959-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="62959-162">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="62959-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="62959-163">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="62959-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="62959-165">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="62959-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="62959-167">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="62959-167">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="62959-169">Selezionare **Sposta DNS**.</span><span class="sxs-lookup"><span data-stu-id="62959-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="62959-171">A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="62959-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="62959-172">Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="62959-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="62959-173">Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="62959-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="62959-174">Se NON sono già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="62959-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="62959-175">Nella sezione **specificare Domain Name Servers** della pagina **Domains** selezionare **Add more name servers**.</span><span class="sxs-lookup"><span data-stu-id="62959-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="62959-177">Nella pagina **Domain Names** digitare o copiare e incollare i valori del server dei nomi dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="62959-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="62959-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="62959-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="62959-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="62959-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="62959-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="62959-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="62959-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="62959-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="62959-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="62959-187">Selezionare **Sposta DNS**.</span><span class="sxs-lookup"><span data-stu-id="62959-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="62959-189">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="62959-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="62959-191">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="62959-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="62959-192">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="62959-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="62959-193">Se SONO già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="62959-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="62959-p113">Seguire questa procedura  *solo*  se sono presenti server dei nomi diversi dai quattro server dei nomi  *corretti*  . In altre parole, eliminare  *solo*  eventuali server dei nomi  *diversi*  da **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="62959-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="62959-196">Se sono già presenti server dei nomi, eliminarli selezionando ogni server e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="62959-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="62959-198">Selezionare **Add more name servers**.</span><span class="sxs-lookup"><span data-stu-id="62959-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="62959-200">Nella pagina **Domain Names** digitare o copiare e incollare i valori del server dei nomi dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="62959-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="62959-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="62959-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="62959-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="62959-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="62959-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="62959-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="62959-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="62959-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="62959-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="62959-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="62959-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="62959-210">Selezionare **Sposta DNS**.</span><span class="sxs-lookup"><span data-stu-id="62959-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="62959-212">Selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="62959-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="62959-214">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="62959-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="62959-215">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="62959-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
