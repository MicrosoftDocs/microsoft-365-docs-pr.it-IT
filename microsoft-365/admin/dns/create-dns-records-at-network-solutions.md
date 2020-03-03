---
title: Creare record DNS su Network Solutions per Office 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Network Solutions per Office 365.
ms.openlocfilehash: f94ad49f443e609aa28d634d05604601c7d5e576
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348537"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="ba4f3-103">Creare record DNS su Network Solutions per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="ba4f3-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ba4f3-105">Se il proprio provider di hosting DNS è Network Solutions, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ba4f3-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-106">These are the main records to add.</span></span> <span data-ttu-id="ba4f3-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="ba4f3-108">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="ba4f3-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="ba4f3-109">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="ba4f3-110">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="ba4f3-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ba4f3-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ba4f3-112">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="ba4f3-113">Dopo aver aggiunto questi record in Network Solutions, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ba4f3-114">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ba4f3-p102">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ba4f3-118">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="ba4f3-118">Add a TXT record for verification</span></span>
<span data-ttu-id="ba4f3-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ba4f3-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ba4f3-p103">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba4f3-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ba4f3-124">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba4f3-125">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba4f3-126">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba4f3-127">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="ba4f3-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba4f3-129">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba4f3-131">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-131">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba4f3-133">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba4f3-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-134">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba4f3-136">Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selezionare Modifica record TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="ba4f3-138">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="ba4f3-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-139">**Host**</span></span>|<span data-ttu-id="ba4f3-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-140">**TTL**</span></span>|<span data-ttu-id="ba4f3-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="ba4f3-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="ba4f3-143">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-143">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ba4f3-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ba4f3-145">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-145">**Note:** This is an example.</span></span> <span data-ttu-id="ba4f3-146">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="ba4f3-147">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ba4f3-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="ba4f3-149">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-149">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="ba4f3-151">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-151">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="ba4f3-153">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ba4f3-154">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ba4f3-155">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="ba4f3-156">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ba4f3-157">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ba4f3-158">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ba4f3-159">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ba4f3-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ba4f3-163">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ba4f3-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ba4f3-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ba4f3-165">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba4f3-166">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba4f3-167">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba4f3-168">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="ba4f3-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba4f3-170">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba4f3-172">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-172">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba4f3-174">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba4f3-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-175">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba4f3-177">Scorrere verso il basso fino alla sezione **mail servers (MX Records)** e quindi selezionare **Edit MX Records**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Selezionare Modifica record MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="ba4f3-179">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ba4f3-180">\*\*Priorità \*\*</span><span class="sxs-lookup"><span data-stu-id="ba4f3-180">**Priority**</span></span>|<span data-ttu-id="ba4f3-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-181">**TTL**</span></span>|<span data-ttu-id="ba4f3-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba4f3-183">10 </span><span class="sxs-lookup"><span data-stu-id="ba4f3-183">10</span></span>  <br/> <span data-ttu-id="ba4f3-184">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="ba4f3-185">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-185">3600</span></span>  <br/> | <span data-ttu-id="ba4f3-186">*\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ba4f3-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="ba4f3-188">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="ba4f3-189">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ba4f3-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="ba4f3-191">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-191">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="ba4f3-193">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-193">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="ba4f3-195">Se ci sono altri record MX, eliminarli tutti selezionando **Delete** per ogni record.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="ba4f3-197">Quando sono tutti selezionati, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-197">When they are all selected, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="ba4f3-199">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-199">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ba4f3-201">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ba4f3-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ba4f3-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ba4f3-203">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba4f3-204">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba4f3-205">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba4f3-206">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="ba4f3-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba4f3-208">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba4f3-210">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-210">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba4f3-212">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba4f3-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-213">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba4f3-215">Scorrere verso il basso fino alla sezione **Host Aliases (CNAME Records)** e quindi selezionare **Edit CNAME Records**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Selezionare Modifica record CNAME in alias host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="ba4f3-217">Nelle caselle dei nuovi quattro record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ba4f3-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-218">**Alias**</span></span>|<span data-ttu-id="ba4f3-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-219">**TTL**</span></span>|<span data-ttu-id="ba4f3-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-220">**Refers to Host Name**</span></span>|<span data-ttu-id="ba4f3-221">**Other Host          (selezionare il pulsante di opzione **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba4f3-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ba4f3-222">autodiscover</span></span>  <br/> |<span data-ttu-id="ba4f3-223">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-223">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-224">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-224">(No setting)</span></span>  <br/> |<span data-ttu-id="ba4f3-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="ba4f3-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba4f3-227">sip</span><span class="sxs-lookup"><span data-stu-id="ba4f3-227">sip</span></span>  <br/> |<span data-ttu-id="ba4f3-228">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-228">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-229">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-229">(No setting)</span></span>  <br/> |<span data-ttu-id="ba4f3-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba4f3-231">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba4f3-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ba4f3-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ba4f3-233">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-233">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-234">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-234">(No setting)</span></span>  <br/> |<span data-ttu-id="ba4f3-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba4f3-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba4f3-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ba4f3-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ba4f3-238">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-238">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-239">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-239">(No setting)</span></span>  <br/> |<span data-ttu-id="ba4f3-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ba4f3-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="ba4f3-241">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba4f3-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ba4f3-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ba4f3-243">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-243">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-244">(Nessuna impostazione)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-244">(No setting)</span></span>  <br/> |<span data-ttu-id="ba4f3-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ba4f3-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="ba4f3-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Digitare o incollare i valori per i nuovi record](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="ba4f3-248">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="ba4f3-250">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-250">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ba4f3-252">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ba4f3-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ba4f3-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ba4f3-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba4f3-254">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ba4f3-255">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ba4f3-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ba4f3-257">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="ba4f3-258">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba4f3-259">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba4f3-260">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba4f3-261">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="ba4f3-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba4f3-263">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba4f3-265">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-265">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba4f3-267">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba4f3-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-268">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba4f3-270">Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selezionare Modifica record TXT in testo](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="ba4f3-272">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="ba4f3-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-273">**Host**</span></span>|<span data-ttu-id="ba4f3-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-274">**TTL**</span></span>|<span data-ttu-id="ba4f3-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="ba4f3-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="ba4f3-277">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-277">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ba4f3-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ba4f3-279">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Digitare o incollare i valori per il nuovo record](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="ba4f3-281">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-281">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="ba4f3-283">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-283">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ba4f3-285">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba4f3-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ba4f3-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ba4f3-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="ba4f3-287">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba4f3-p113">Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba4f3-290">Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** .</span><span class="sxs-lookup"><span data-stu-id="ba4f3-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba4f3-292">Selezionare la casella di controllo accanto al nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba4f3-294">Selezionare **modifica DNS**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-294">Select **Edit DNS**.</span></span>
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba4f3-296">Selezionare **Gestisci record DNS avanzati**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba4f3-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba4f3-297">(You may have to scroll down.)</span></span>
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba4f3-299">Scorrere verso il basso fino alla sezione **Service (SRV Records)** e quindi selezionare **Edit SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV in servizio](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="ba4f3-301">Nelle caselle dei nuovi due record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ba4f3-302">Scegliere i valori **Service** e **Protocol** dagli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ba4f3-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-303">**Service**</span></span>|<span data-ttu-id="ba4f3-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-304">**Protocol**</span></span>|<span data-ttu-id="ba4f3-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-305">**TTL**</span></span>|<span data-ttu-id="ba4f3-306">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-306">**Priority**</span></span>|<span data-ttu-id="ba4f3-307">**Peso**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-307">**Weight**</span></span>|<span data-ttu-id="ba4f3-308">**Porta**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-308">**Port**</span></span>|<span data-ttu-id="ba4f3-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba4f3-310">_sip</span><span class="sxs-lookup"><span data-stu-id="ba4f3-310">_sip</span></span>  <br/> |<span data-ttu-id="ba4f3-311">_tls</span><span class="sxs-lookup"><span data-stu-id="ba4f3-311">_tls</span></span>  <br/> |<span data-ttu-id="ba4f3-312">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-312">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-313">100</span><span class="sxs-lookup"><span data-stu-id="ba4f3-313">100</span></span>  <br/> |<span data-ttu-id="ba4f3-314">1</span><span class="sxs-lookup"><span data-stu-id="ba4f3-314">1</span></span>  <br/> |<span data-ttu-id="ba4f3-315">443</span><span class="sxs-lookup"><span data-stu-id="ba4f3-315">443</span></span>  <br/> |<span data-ttu-id="ba4f3-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba4f3-317">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba4f3-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ba4f3-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ba4f3-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="ba4f3-319">_tcp</span></span>  <br/> |<span data-ttu-id="ba4f3-320">3600</span><span class="sxs-lookup"><span data-stu-id="ba4f3-320">3600</span></span>  <br/> |<span data-ttu-id="ba4f3-321">100</span><span class="sxs-lookup"><span data-stu-id="ba4f3-321">100</span></span>  <br/> |<span data-ttu-id="ba4f3-322">1</span><span class="sxs-lookup"><span data-stu-id="ba4f3-322">1</span></span>  <br/> |<span data-ttu-id="ba4f3-323">5061</span><span class="sxs-lookup"><span data-stu-id="ba4f3-323">5061</span></span>  <br/> |<span data-ttu-id="ba4f3-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba4f3-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba4f3-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Digitare o incollare i valori per i nuovi record](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="ba4f3-327">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-327">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="ba4f3-329">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ba4f3-329">Select **Save Changes**.</span></span>
    
    ![Selezionare Salva modifiche](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="ba4f3-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba4f3-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
