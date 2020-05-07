---
title: Creare record DNS in Network Solutions per Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Network Solutions per Microsoft.
ms.openlocfilehash: fb5fd2d2bcb263a62306617d728f08b07bb6da34
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048928"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="a738a-103">Creare record DNS in Network Solutions per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="a738a-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a738a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a738a-105">Se il proprio provider di hosting DNS è Network Solutions, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="a738a-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a738a-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a738a-106">These are the main records to add.</span></span> <span data-ttu-id="a738a-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="a738a-108">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="a738a-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="a738a-109">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a738a-110">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a738a-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a738a-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a738a-112">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a738a-113">Dopo aver aggiunto questi record in Network Solutions, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a738a-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="a738a-p102">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a738a-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a738a-117">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="a738a-117">Add a TXT record for verification</span></span>
<span data-ttu-id="a738a-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a738a-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a738a-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a738a-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a738a-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="a738a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a738a-123">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a738a-124">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a738a-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a738a-125">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a738a-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a738a-126">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="a738a-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a738a-128">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a738a-130">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="a738a-130">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a738a-132">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="a738a-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a738a-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a738a-133">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a738a-135">Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.</span><span class="sxs-lookup"><span data-stu-id="a738a-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selezionare Modifica record TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="a738a-137">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a738a-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="a738a-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="a738a-138">**Host**</span></span>|<span data-ttu-id="a738a-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a738a-139">**TTL**</span></span>|<span data-ttu-id="a738a-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="a738a-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a738a-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a738a-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a738a-142">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-142">3600</span></span>  <br/> |<span data-ttu-id="a738a-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a738a-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a738a-144">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="a738a-144">**Note:** This is an example.</span></span> <span data-ttu-id="a738a-145">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a738a-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="a738a-146">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="a738a-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="a738a-148">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-148">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="a738a-150">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-150">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="a738a-152">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="a738a-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a738a-153">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="a738a-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a738a-154">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="a738a-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="a738a-155">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="a738a-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a738a-156">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a738a-157">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a738a-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a738a-158">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="a738a-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a738a-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a738a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a738a-162">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a738a-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a738a-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a738a-164">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a738a-165">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a738a-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a738a-166">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a738a-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a738a-167">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="a738a-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a738a-169">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a738a-171">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="a738a-171">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a738a-173">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="a738a-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a738a-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a738a-174">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a738a-176">Scorrere verso il basso fino alla sezione **mail servers (MX Records)** e quindi selezionare **Edit MX Records**.</span><span class="sxs-lookup"><span data-stu-id="a738a-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Selezionare Modifica record MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="a738a-178">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a738a-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a738a-179">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="a738a-179">**Priority**</span></span>|<span data-ttu-id="a738a-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a738a-180">**TTL**</span></span>|<span data-ttu-id="a738a-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="a738a-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a738a-182">10  </span><span class="sxs-lookup"><span data-stu-id="a738a-182">10</span></span>  <br/> <span data-ttu-id="a738a-183">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="a738a-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="a738a-184">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-184">3600</span></span>  <br/> | <span data-ttu-id="a738a-185">*\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a738a-186">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a738a-187">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a738a-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="a738a-188">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="a738a-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="a738a-190">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-190">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="a738a-192">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-192">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="a738a-194">Se ci sono altri record MX, eliminarli tutti selezionando **Delete** per ogni record.</span><span class="sxs-lookup"><span data-stu-id="a738a-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="a738a-196">Quando sono tutti selezionati, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-196">When they are all selected, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="a738a-198">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-198">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a738a-200">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a738a-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a738a-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a738a-202">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a738a-203">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a738a-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a738a-204">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a738a-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a738a-205">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="a738a-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a738a-207">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a738a-209">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="a738a-209">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a738a-211">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="a738a-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a738a-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a738a-212">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a738a-214">Scorrere verso il basso fino alla sezione **Host Aliases (CNAME Records)** e quindi selezionare **Edit CNAME Records**.</span><span class="sxs-lookup"><span data-stu-id="a738a-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Selezionare Modifica record CNAME in alias host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="a738a-216">Nelle caselle dei nuovi quattro record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a738a-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a738a-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a738a-217">**Alias**</span></span>|<span data-ttu-id="a738a-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a738a-218">**TTL**</span></span>|<span data-ttu-id="a738a-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="a738a-219">**Refers to Host Name**</span></span>|<span data-ttu-id="a738a-220">**Other Host          (selezionare il pulsante di opzione **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="a738a-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a738a-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a738a-221">autodiscover</span></span>  <br/> |<span data-ttu-id="a738a-222">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-222">3600</span></span>  <br/> |<span data-ttu-id="a738a-223">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="a738a-223">(No setting)</span></span>  <br/> |<span data-ttu-id="a738a-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a738a-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a738a-226">sip</span><span class="sxs-lookup"><span data-stu-id="a738a-226">sip</span></span>  <br/> |<span data-ttu-id="a738a-227">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-227">3600</span></span>  <br/> |<span data-ttu-id="a738a-228">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="a738a-228">(No setting)</span></span>  <br/> |<span data-ttu-id="a738a-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a738a-230">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a738a-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a738a-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a738a-232">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-232">3600</span></span>  <br/> |<span data-ttu-id="a738a-233">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="a738a-233">(No setting)</span></span>  <br/> |<span data-ttu-id="a738a-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a738a-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a738a-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a738a-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a738a-237">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-237">3600</span></span>  <br/> |<span data-ttu-id="a738a-238">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="a738a-238">(No setting)</span></span>  <br/> |<span data-ttu-id="a738a-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a738a-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="a738a-240">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a738a-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a738a-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a738a-242">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-242">3600</span></span>  <br/> |<span data-ttu-id="a738a-243">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="a738a-243">(No setting)</span></span>  <br/> |<span data-ttu-id="a738a-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a738a-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="a738a-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Digitare o incollare i valori per i nuovi record](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="a738a-247">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="a738a-249">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-249">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a738a-251">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a738a-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a738a-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a738a-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a738a-253">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="a738a-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a738a-254">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a738a-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a738a-255">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a738a-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a738a-256">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="a738a-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a738a-257">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a738a-258">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a738a-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a738a-259">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a738a-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a738a-260">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="a738a-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a738a-262">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a738a-264">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="a738a-264">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a738a-266">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="a738a-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a738a-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a738a-267">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a738a-269">Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.</span><span class="sxs-lookup"><span data-stu-id="a738a-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selezionare Modifica record TXT in testo](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="a738a-271">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="a738a-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="a738a-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="a738a-272">**Host**</span></span>|<span data-ttu-id="a738a-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a738a-273">**TTL**</span></span>|<span data-ttu-id="a738a-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="a738a-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a738a-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a738a-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a738a-276">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-276">3600</span></span>  <br/> |<span data-ttu-id="a738a-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a738a-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a738a-278">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="a738a-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Digitare o incollare i valori per il nuovo record](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="a738a-280">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-280">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="a738a-282">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-282">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a738a-284">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a738a-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a738a-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a738a-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a738a-286">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a738a-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a738a-p113">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a738a-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a738a-289">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="a738a-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a738a-291">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="a738a-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a738a-293">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="a738a-293">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a738a-295">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="a738a-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a738a-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a738a-296">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a738a-298">Scorrere verso il basso fino alla sezione **Service (SRV Records)** e quindi selezionare **Edit SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="a738a-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV in servizio](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="a738a-300">Nelle caselle dei nuovi due record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a738a-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a738a-301">Scegliere i valori **Service** e **Protocol** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="a738a-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a738a-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="a738a-302">**Service**</span></span>|<span data-ttu-id="a738a-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a738a-303">**Protocol**</span></span>|<span data-ttu-id="a738a-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a738a-304">**TTL**</span></span>|<span data-ttu-id="a738a-305">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="a738a-305">**Priority**</span></span>|<span data-ttu-id="a738a-306">**Peso**</span><span class="sxs-lookup"><span data-stu-id="a738a-306">**Weight**</span></span>|<span data-ttu-id="a738a-307">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a738a-307">**Port**</span></span>|<span data-ttu-id="a738a-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="a738a-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a738a-309">_sip</span><span class="sxs-lookup"><span data-stu-id="a738a-309">_sip</span></span>  <br/> |<span data-ttu-id="a738a-310">_tls</span><span class="sxs-lookup"><span data-stu-id="a738a-310">_tls</span></span>  <br/> |<span data-ttu-id="a738a-311">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-311">3600</span></span>  <br/> |<span data-ttu-id="a738a-312">100</span><span class="sxs-lookup"><span data-stu-id="a738a-312">100</span></span>  <br/> |<span data-ttu-id="a738a-313">1</span><span class="sxs-lookup"><span data-stu-id="a738a-313">1</span></span>  <br/> |<span data-ttu-id="a738a-314">443</span><span class="sxs-lookup"><span data-stu-id="a738a-314">443</span></span>  <br/> |<span data-ttu-id="a738a-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a738a-316">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a738a-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a738a-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a738a-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="a738a-318">_tcp</span></span>  <br/> |<span data-ttu-id="a738a-319">3600</span><span class="sxs-lookup"><span data-stu-id="a738a-319">3600</span></span>  <br/> |<span data-ttu-id="a738a-320">100</span><span class="sxs-lookup"><span data-stu-id="a738a-320">100</span></span>  <br/> |<span data-ttu-id="a738a-321">1</span><span class="sxs-lookup"><span data-stu-id="a738a-321">1</span></span>  <br/> |<span data-ttu-id="a738a-322">5061</span><span class="sxs-lookup"><span data-stu-id="a738a-322">5061</span></span>  <br/> |<span data-ttu-id="a738a-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a738a-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a738a-324">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a738a-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Digitare o incollare i valori per i nuovi record](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="a738a-326">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="a738a-326">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="a738a-328">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a738a-328">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="a738a-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a738a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
