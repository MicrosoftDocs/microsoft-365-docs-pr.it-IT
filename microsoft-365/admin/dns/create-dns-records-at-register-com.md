---
title: Creare record DNS in Register.com per Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register.com per Microsoft.
ms.openlocfilehash: 7d1293368a9a7ab94a5556ca266c716280ae85f5
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939120"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="2a393-103">Creare record DNS in Register.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="2a393-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2a393-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2a393-105">Se il proprio provider di hosting DNS è Register.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="2a393-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2a393-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2a393-106">These are the main records to add.</span></span> <span data-ttu-id="2a393-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="2a393-108">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="2a393-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="2a393-109">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="2a393-110">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="2a393-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="2a393-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="2a393-112">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="2a393-113">Dopo aver aggiunto questi record in Register.com, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a393-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="2a393-p102">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2a393-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="2a393-117">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="2a393-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="2a393-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2a393-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2a393-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="2a393-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a393-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="2a393-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="2a393-123">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2a393-124">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="2a393-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="2a393-125">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a393-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="2a393-126">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="2a393-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="2a393-127">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="2a393-128">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="2a393-129">Scorrere verso il basso fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="2a393-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="2a393-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2a393-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="2a393-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2a393-131">**Host Name**</span></span> <br/> |<span data-ttu-id="2a393-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="2a393-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="2a393-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2a393-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2a393-134">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="2a393-134">**Note:** This is an example.</span></span> <span data-ttu-id="2a393-135">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2a393-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2a393-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2a393-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="2a393-137">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="2a393-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="2a393-138">Nella pagina successiva, selezionare **continua** di nuovo per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a393-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="2a393-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="2a393-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2a393-140">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="2a393-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="2a393-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="2a393-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2a393-142">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="2a393-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2a393-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="2a393-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="2a393-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="2a393-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="2a393-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="2a393-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a393-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2a393-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2a393-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2a393-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2a393-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2a393-151">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2a393-152">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="2a393-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="2a393-153">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a393-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="2a393-154">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="2a393-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="2a393-155">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="2a393-156">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="2a393-157">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Mail Exchanger Records**.</span><span class="sxs-lookup"><span data-stu-id="2a393-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selezionare Modifica record di Mail Exchanger](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="2a393-159">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2a393-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="2a393-160">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2a393-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2a393-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="2a393-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="2a393-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2a393-164">Alto</span><span class="sxs-lookup"><span data-stu-id="2a393-164">High</span></span>  <br/> <span data-ttu-id="2a393-165">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a393-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="2a393-166">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2a393-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="2a393-167">**Nota:** ottenere il valore \<*domain-key*\> dall'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a393-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="2a393-168">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2a393-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare il valore dalla tabella](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="2a393-170">Se nell'elenco sono presenti altri record MX, selezionare ognuno di essi per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2a393-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="2a393-172">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="2a393-172">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="2a393-174">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a393-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2a393-176">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2a393-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2a393-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2a393-178">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2a393-179">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="2a393-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="2a393-180">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a393-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="2a393-181">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="2a393-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="2a393-182">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="2a393-183">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="2a393-184">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Domain Aliases Records**.</span><span class="sxs-lookup"><span data-stu-id="2a393-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selezionare Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="2a393-186">Selezionare **Aggiungi altri alias di dominio**.</span><span class="sxs-lookup"><span data-stu-id="2a393-186">Select **Add more domain aliases**.</span></span>
    
    ![Selezionare Aggiungi altri alias per i domini](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="2a393-188">Aggiungere i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="2a393-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="2a393-189">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2a393-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="2a393-190">\*\*\*\*Primo campo (senza etichetta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="2a393-191">\*\*\*\*Punta a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="2a393-192">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="2a393-192">autodiscover</span></span>  <br/> |<span data-ttu-id="2a393-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2a393-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="2a393-194">sip</span><span class="sxs-lookup"><span data-stu-id="2a393-194">sip</span></span>  <br/> |<span data-ttu-id="2a393-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2a393-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="2a393-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2a393-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2a393-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2a393-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="2a393-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2a393-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2a393-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2a393-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="2a393-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2a393-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2a393-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2a393-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiare e incollare i valori DNS dalla tabella](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="2a393-203">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="2a393-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="2a393-205">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a393-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2a393-207">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="2a393-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2a393-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2a393-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a393-209">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="2a393-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2a393-210">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2a393-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2a393-211">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a393-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2a393-212">Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="2a393-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="2a393-213">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2a393-214">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="2a393-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="2a393-215">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a393-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="2a393-216">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="2a393-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="2a393-217">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="2a393-218">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="2a393-219">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="2a393-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selezionare Modifica record TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="2a393-221">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2a393-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2a393-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="2a393-223">\*\*\*\*Record TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="2a393-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2a393-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2a393-225">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="2a393-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiare e incollare i valori della tabella](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="2a393-227">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="2a393-227">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="2a393-229">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a393-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2a393-231">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a393-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2a393-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2a393-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2a393-233">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="2a393-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="2a393-p112">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a393-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="2a393-236">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="2a393-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="2a393-237">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="2a393-238">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="2a393-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="2a393-239">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="2a393-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="2a393-241">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="2a393-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="2a393-242">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2a393-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="2a393-243">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2a393-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2a393-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="2a393-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="2a393-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="2a393-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="2a393-248">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="2a393-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="2a393-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a393-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2a393-251">_sip</span><span class="sxs-lookup"><span data-stu-id="2a393-251">_sip</span></span>  <br/> |<span data-ttu-id="2a393-252">_tls</span><span class="sxs-lookup"><span data-stu-id="2a393-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="2a393-253">High</span><span class="sxs-lookup"><span data-stu-id="2a393-253">High</span></span>  <br/> |<span data-ttu-id="2a393-254">1</span><span class="sxs-lookup"><span data-stu-id="2a393-254">1</span></span>  <br/> |<span data-ttu-id="2a393-255">443</span><span class="sxs-lookup"><span data-stu-id="2a393-255">443</span></span>  <br/> |<span data-ttu-id="2a393-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2a393-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="2a393-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2a393-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="2a393-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="2a393-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="2a393-259">High</span><span class="sxs-lookup"><span data-stu-id="2a393-259">High</span></span>  <br/> |<span data-ttu-id="2a393-260">1</span><span class="sxs-lookup"><span data-stu-id="2a393-260">1</span></span>  <br/> |<span data-ttu-id="2a393-261">5061</span><span class="sxs-lookup"><span data-stu-id="2a393-261">5061</span></span>  <br/> |<span data-ttu-id="2a393-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2a393-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="2a393-264">Selezionare **Aggiungi altri record SRV**.</span><span class="sxs-lookup"><span data-stu-id="2a393-264">Select **Add more SRV records**.</span></span>
    
    ![Selezionare Aggiungi altri record SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="2a393-266">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="2a393-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="2a393-267">Digitare o copiare e incollare i valori della seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="2a393-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="2a393-268">Dopo aver aggiunto entrambi i record SRV, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="2a393-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="2a393-270">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2a393-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="2a393-p113">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2a393-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
