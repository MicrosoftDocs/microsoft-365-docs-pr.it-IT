---
title: Creare record DNS in Register.com per Office 365
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register.com per Office 365.
ms.openlocfilehash: d89e1843a7c914843c7e9d5c41582878e138473a
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211099"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="90e52-103">Creare record DNS in Register.com per Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="90e52-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="90e52-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="90e52-105">Se il proprio provider di hosting DNS è Register.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="90e52-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="90e52-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="90e52-106">These are the main records to add.</span></span> <span data-ttu-id="90e52-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="90e52-108">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="90e52-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="90e52-109">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="90e52-110">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="90e52-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="90e52-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="90e52-112">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="90e52-113">Dopo aver aggiunto questi record in Register.com, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e52-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="90e52-114">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="90e52-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="90e52-p102">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90e52-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="90e52-118">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="90e52-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="90e52-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="90e52-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="90e52-p103">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="90e52-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90e52-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="90e52-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="90e52-124">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="90e52-125">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="90e52-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="90e52-126">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="90e52-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="90e52-127">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="90e52-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="90e52-128">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="90e52-129">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="90e52-130">Scorrere verso il basso fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="90e52-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="90e52-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="90e52-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="90e52-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="90e52-132">**Host Name**</span></span> <br/> |<span data-ttu-id="90e52-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="90e52-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="90e52-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="90e52-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="90e52-135">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="90e52-135">**Note:** This is an example.</span></span> <span data-ttu-id="90e52-136">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e52-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="90e52-137">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="90e52-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="90e52-138">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="90e52-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="90e52-139">Nella pagina successiva, selezionare **continua** di nuovo per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90e52-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="90e52-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="90e52-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="90e52-141">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="90e52-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="90e52-142">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="90e52-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="90e52-143">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="90e52-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="90e52-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="90e52-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="90e52-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="90e52-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="90e52-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="90e52-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="90e52-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90e52-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="90e52-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="90e52-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="90e52-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="90e52-152">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="90e52-153">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="90e52-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="90e52-154">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="90e52-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="90e52-155">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="90e52-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="90e52-156">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="90e52-157">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="90e52-158">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Mail Exchanger Records**.</span><span class="sxs-lookup"><span data-stu-id="90e52-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selezionare Modifica record di Mail Exchanger](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="90e52-160">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90e52-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="90e52-161">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="90e52-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90e52-162">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="90e52-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="90e52-164">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="90e52-165">High</span><span class="sxs-lookup"><span data-stu-id="90e52-165">High</span></span>  <br/> <span data-ttu-id="90e52-166">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="90e52-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="90e52-167">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="90e52-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="90e52-168">**Nota:** ottenere il valore \<*domain-key*\> dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e52-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="90e52-169">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="90e52-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare il valore dalla tabella](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="90e52-171">Se nell'elenco sono presenti altri record MX, selezionare ognuno di essi per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="90e52-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="90e52-173">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="90e52-173">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="90e52-175">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90e52-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="90e52-177">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="90e52-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="90e52-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="90e52-179">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="90e52-180">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="90e52-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="90e52-181">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="90e52-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="90e52-182">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="90e52-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="90e52-183">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="90e52-184">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="90e52-185">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Domain Aliases Records**.</span><span class="sxs-lookup"><span data-stu-id="90e52-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selezionare Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="90e52-187">Selezionare **Aggiungi altri alias di dominio**.</span><span class="sxs-lookup"><span data-stu-id="90e52-187">Select **Add more domain aliases**.</span></span>
    
    ![Selezionare Aggiungi altri alias per i domini](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="90e52-189">Aggiungere i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="90e52-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="90e52-190">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90e52-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="90e52-191">\*\*\*\*Primo campo (senza etichetta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="90e52-192">\*\*\*\*Punta a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="90e52-193">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="90e52-193">autodiscover</span></span>  <br/> |<span data-ttu-id="90e52-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="90e52-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="90e52-195">sip</span><span class="sxs-lookup"><span data-stu-id="90e52-195">sip</span></span>  <br/> |<span data-ttu-id="90e52-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90e52-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="90e52-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="90e52-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="90e52-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90e52-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="90e52-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="90e52-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="90e52-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="90e52-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="90e52-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="90e52-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="90e52-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90e52-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiare e incollare i valori DNS dalla tabella](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="90e52-204">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="90e52-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="90e52-206">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90e52-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="90e52-208">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="90e52-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="90e52-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="90e52-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="90e52-210">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="90e52-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="90e52-211">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="90e52-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="90e52-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e52-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="90e52-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="90e52-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="90e52-214">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="90e52-215">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="90e52-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="90e52-216">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="90e52-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="90e52-217">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="90e52-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="90e52-218">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="90e52-219">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="90e52-220">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="90e52-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selezionare Modifica record TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="90e52-222">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90e52-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="90e52-223">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="90e52-224">\*\*\*\*Record TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="90e52-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="90e52-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="90e52-226">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="90e52-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiare e incollare i valori della tabella](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="90e52-228">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="90e52-228">Select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="90e52-230">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90e52-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="90e52-232">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="90e52-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="90e52-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="90e52-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="90e52-234">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="90e52-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="90e52-p112">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="90e52-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="90e52-237">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="90e52-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="90e52-238">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="90e52-239">Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="90e52-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="90e52-240">Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit SRV Records**.</span><span class="sxs-lookup"><span data-stu-id="90e52-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="90e52-242">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="90e52-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="90e52-243">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90e52-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="90e52-244">Scegliere il valore di **priorità** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="90e52-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90e52-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="90e52-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="90e52-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="90e52-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="90e52-249">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="90e52-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="90e52-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="90e52-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90e52-252">_sip</span><span class="sxs-lookup"><span data-stu-id="90e52-252">_sip</span></span>  <br/> |<span data-ttu-id="90e52-253">_tls</span><span class="sxs-lookup"><span data-stu-id="90e52-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="90e52-254">High</span><span class="sxs-lookup"><span data-stu-id="90e52-254">High</span></span>  <br/> |<span data-ttu-id="90e52-255">1 </span><span class="sxs-lookup"><span data-stu-id="90e52-255">1</span></span>  <br/> |<span data-ttu-id="90e52-256">443</span><span class="sxs-lookup"><span data-stu-id="90e52-256">443</span></span>  <br/> |<span data-ttu-id="90e52-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90e52-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="90e52-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="90e52-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="90e52-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="90e52-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="90e52-260">High</span><span class="sxs-lookup"><span data-stu-id="90e52-260">High</span></span>  <br/> |<span data-ttu-id="90e52-261">1 </span><span class="sxs-lookup"><span data-stu-id="90e52-261">1</span></span>  <br/> |<span data-ttu-id="90e52-262">5061</span><span class="sxs-lookup"><span data-stu-id="90e52-262">5061</span></span>  <br/> |<span data-ttu-id="90e52-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90e52-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="90e52-265">Selezionare **Aggiungi altri record SRV**.</span><span class="sxs-lookup"><span data-stu-id="90e52-265">Select **Add more SRV records**.</span></span>
    
    ![Selezionare Aggiungi altri record SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="90e52-267">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="90e52-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="90e52-268">Digitare o copiare e incollare i valori della seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="90e52-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="90e52-269">Dopo aver aggiunto entrambi i record SRV, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="90e52-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleziona continua](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="90e52-271">Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="90e52-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleziona continua](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="90e52-p113">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90e52-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
