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
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629276"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="db63f-103">Creare record DNS in Register.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="db63f-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="db63f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="db63f-105">Se il proprio provider di hosting DNS è Register.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="db63f-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="db63f-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="db63f-106">These are the main records to add.</span></span> <span data-ttu-id="db63f-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="db63f-108">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="db63f-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="db63f-109">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="db63f-110">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="db63f-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="db63f-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="db63f-112">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="db63f-113">Dopo aver aggiunto questi record in Register.com, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db63f-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="db63f-114">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="db63f-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="db63f-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="db63f-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="db63f-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="db63f-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="db63f-117">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="db63f-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="db63f-118">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="db63f-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="db63f-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="db63f-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="db63f-120">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="db63f-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="db63f-121">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="db63f-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db63f-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="db63f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="db63f-124">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="db63f-125">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="db63f-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="db63f-126">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="db63f-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="db63f-127">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="db63f-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="db63f-128">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="db63f-129">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="db63f-130">Scorrere verso il basso fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="db63f-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="db63f-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="db63f-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="db63f-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="db63f-132">**Host Name**</span></span> <br/> |<span data-ttu-id="db63f-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="db63f-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="db63f-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="db63f-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="db63f-135">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="db63f-135">**Note:** This is an example.</span></span> <span data-ttu-id="db63f-136">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="db63f-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="db63f-137">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="db63f-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="db63f-138">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="db63f-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="db63f-139">Nella pagina successiva, selezionare **continua** di nuovo per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="db63f-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="db63f-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="db63f-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="db63f-141">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="db63f-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="db63f-142">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="db63f-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="db63f-143">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="db63f-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="db63f-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="db63f-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="db63f-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="db63f-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="db63f-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="db63f-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="db63f-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="db63f-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="db63f-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="db63f-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="db63f-149">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="db63f-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="db63f-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="db63f-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="db63f-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="db63f-152">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="db63f-153">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="db63f-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="db63f-154">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="db63f-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="db63f-155">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="db63f-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="db63f-156">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="db63f-157">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="db63f-158">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Mail Exchanger Records**.</span><span class="sxs-lookup"><span data-stu-id="db63f-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selezionare Modifica record di Mail Exchanger](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="db63f-160">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="db63f-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="db63f-161">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="db63f-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="db63f-162">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="db63f-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="db63f-164">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="db63f-165">High</span><span class="sxs-lookup"><span data-stu-id="db63f-165">High</span></span>  <br/> <span data-ttu-id="db63f-166">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="db63f-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="db63f-167">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="db63f-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="db63f-168">**Nota:** Ottenere la \<propria *chiave* \> di dominio dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db63f-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="db63f-169">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="db63f-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare il valore dalla tabella](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="db63f-171">Se nell'elenco sono presenti altri record MX, selezionare ognuno di essi per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="db63f-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="db63f-173">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="db63f-173">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="db63f-175">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="db63f-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="db63f-177">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="db63f-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="db63f-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="db63f-179">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="db63f-180">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="db63f-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="db63f-181">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="db63f-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="db63f-182">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="db63f-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="db63f-183">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="db63f-184">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="db63f-185">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Domain Aliases Records**.</span><span class="sxs-lookup"><span data-stu-id="db63f-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selezionare Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="db63f-187">Selezionare **Aggiungi altri alias di dominio**.</span><span class="sxs-lookup"><span data-stu-id="db63f-187">Select **Add more domain aliases**.</span></span>
    
    ![Selezionare Aggiungi altri alias per i domini](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="db63f-189">Aggiungere i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="db63f-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="db63f-190">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="db63f-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="db63f-191">\*\*\*\*Primo campo (senza etichetta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="db63f-192">\*\*\*\*Punta a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="db63f-193">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="db63f-193">autodiscover</span></span>  <br/> |<span data-ttu-id="db63f-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="db63f-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="db63f-195">sip</span><span class="sxs-lookup"><span data-stu-id="db63f-195">sip</span></span>  <br/> |<span data-ttu-id="db63f-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="db63f-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="db63f-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="db63f-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="db63f-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="db63f-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="db63f-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="db63f-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="db63f-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="db63f-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="db63f-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="db63f-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="db63f-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="db63f-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiare e incollare i valori DNS dalla tabella](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="db63f-204">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="db63f-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="db63f-206">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="db63f-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="db63f-208">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="db63f-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="db63f-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="db63f-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="db63f-210">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="db63f-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="db63f-211">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="db63f-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="db63f-212">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db63f-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="db63f-213">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="db63f-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="db63f-214">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="db63f-215">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="db63f-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="db63f-216">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="db63f-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="db63f-217">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="db63f-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="db63f-218">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="db63f-219">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="db63f-220">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="db63f-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selezionare Modifica record TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="db63f-222">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="db63f-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="db63f-223">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="db63f-224">\*\*\*\*Record TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="db63f-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="db63f-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="db63f-226">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="db63f-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiare e incollare i valori della tabella](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="db63f-228">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="db63f-228">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="db63f-230">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="db63f-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="db63f-232">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="db63f-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="db63f-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="db63f-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="db63f-234">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="db63f-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="db63f-p112">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="db63f-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="db63f-237">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="db63f-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="db63f-238">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="db63f-239">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="db63f-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="db63f-240">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="db63f-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="db63f-242">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="db63f-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="db63f-243">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="db63f-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="db63f-244">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="db63f-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="db63f-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="db63f-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="db63f-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="db63f-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="db63f-249">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="db63f-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="db63f-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="db63f-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="db63f-252">_sip</span><span class="sxs-lookup"><span data-stu-id="db63f-252">_sip</span></span>  <br/> |<span data-ttu-id="db63f-253">_tls</span><span class="sxs-lookup"><span data-stu-id="db63f-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="db63f-254">High</span><span class="sxs-lookup"><span data-stu-id="db63f-254">High</span></span>  <br/> |<span data-ttu-id="db63f-255">1 </span><span class="sxs-lookup"><span data-stu-id="db63f-255">1</span></span>  <br/> |<span data-ttu-id="db63f-256">443</span><span class="sxs-lookup"><span data-stu-id="db63f-256">443</span></span>  <br/> |<span data-ttu-id="db63f-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="db63f-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="db63f-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="db63f-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="db63f-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="db63f-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="db63f-260">High</span><span class="sxs-lookup"><span data-stu-id="db63f-260">High</span></span>  <br/> |<span data-ttu-id="db63f-261">1 </span><span class="sxs-lookup"><span data-stu-id="db63f-261">1</span></span>  <br/> |<span data-ttu-id="db63f-262">5061</span><span class="sxs-lookup"><span data-stu-id="db63f-262">5061</span></span>  <br/> |<span data-ttu-id="db63f-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="db63f-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="db63f-265">Selezionare **Aggiungi altri record SRV**.</span><span class="sxs-lookup"><span data-stu-id="db63f-265">Select **Add more SRV records**.</span></span>
    
    ![Selezionare Aggiungi altri record SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="db63f-267">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="db63f-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="db63f-268">Digitare o copiare e incollare i valori della seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="db63f-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="db63f-269">Dopo aver aggiunto entrambi i record SRV, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="db63f-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="db63f-271">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="db63f-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="db63f-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="db63f-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="db63f-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="db63f-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="db63f-275">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="db63f-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
