---
title: Creare record DNS in Register.com per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi Register.com per Microsoft.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910055"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="ba7bc-103">Creare record DNS in Register.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="ba7bc-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ba7bc-105">Se il proprio provider di hosting DNS è Register.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ba7bc-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-106">These are the main records to add.</span></span> <span data-ttu-id="ba7bc-107">Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="ba7bc-108">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="ba7bc-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="ba7bc-109">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="ba7bc-110">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ba7bc-111">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ba7bc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="ba7bc-112">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ba7bc-113">Dopo aver aggiunto questi record in Register.com, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="ba7bc-p102">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="ba7bc-117">Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio</span><span class="sxs-lookup"><span data-stu-id="ba7bc-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="ba7bc-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ba7bc-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ba7bc-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba7bc-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ba7bc-123">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ba7bc-p105">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ba7bc-126">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ba7bc-127">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ba7bc-128">Individuare la riga contenente il nome del dominio che si desidera modificare. e quindi, in tale riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ba7bc-129">Scorrere verso il basso **fino alla sezione Advanced Technical Settings** e quindi selezionare Edit TXT Records **(SPF)**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="ba7bc-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="ba7bc-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-131">**Host Name**</span></span> <br/> |<span data-ttu-id="ba7bc-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="ba7bc-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ba7bc-134">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-134">**Note:** This is an example.</span></span> <span data-ttu-id="ba7bc-135">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ba7bc-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ba7bc-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ba7bc-137">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="ba7bc-138">Nella pagina successiva selezionare di **nuovo Continua** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="ba7bc-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ba7bc-140">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ba7bc-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ba7bc-142">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ba7bc-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ba7bc-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ba7bc-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ba7bc-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ba7bc-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ba7bc-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ba7bc-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ba7bc-151">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ba7bc-p108">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ba7bc-154">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ba7bc-155">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ba7bc-156">Individuare la riga contenente il nome del dominio che si desidera modificare. e quindi, in tale riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ba7bc-157">Scorrere fino alla **sezione Impostazioni tecniche avanzate** e quindi selezionare Modifica record Mail **Exchanger.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selezionare Modifica record Mail Exchanger](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="ba7bc-159">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ba7bc-160">Scegliere il **valore Priority** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ba7bc-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ba7bc-164">High</span><span class="sxs-lookup"><span data-stu-id="ba7bc-164">High</span></span>  <br/> <span data-ttu-id="ba7bc-165">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="ba7bc-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="ba7bc-167">**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="ba7bc-168">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="ba7bc-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare il valore dalla tabella](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="ba7bc-170">Se nell'elenco sono presenti altri record MX, selezionare ognuno di essi per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="ba7bc-172">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-172">Select **Continue**.</span></span>
    
    ![Selezionare Continua](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="ba7bc-174">Nella pagina successiva selezionare di nuovo **Continua** per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selezionare Continua](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba7bc-176">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ba7bc-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ba7bc-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ba7bc-178">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ba7bc-p109">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ba7bc-181">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ba7bc-182">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ba7bc-183">Individuare la riga contenente il nome del dominio che si desidera modificare. e quindi, in tale riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ba7bc-184">Scorrere fino alla **sezione Impostazioni tecniche avanzate** e quindi selezionare Modifica record alias di **dominio**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selezionare Modifica record alias di dominio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="ba7bc-186">Selezionare **Aggiungi altri alias di dominio**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-186">Select **Add more domain aliases**.</span></span>
    
    ![Selezionare Aggiungi altri alias di domini](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="ba7bc-188">Aggiungere i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="ba7bc-189">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="ba7bc-190">\*\*\*\*Primo campo (senza etichetta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-191">\*\*\*\*Punta a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ba7bc-192">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="ba7bc-192">autodiscover</span></span>  <br/> |<span data-ttu-id="ba7bc-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ba7bc-194">sip</span><span class="sxs-lookup"><span data-stu-id="ba7bc-194">sip</span></span>  <br/> |<span data-ttu-id="ba7bc-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ba7bc-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ba7bc-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ba7bc-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="ba7bc-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ba7bc-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ba7bc-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ba7bc-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ba7bc-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ba7bc-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ba7bc-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiare e incollare i valori DNS dalla tabella](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="ba7bc-203">Dopo aver aggiunto tutti i record CNAME necessari, selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selezionare Continua](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="ba7bc-205">Nella pagina successiva selezionare di nuovo **Continua** per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selezionare Continua](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ba7bc-207">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ba7bc-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ba7bc-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ba7bc-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba7bc-209">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ba7bc-210">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ba7bc-211">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ba7bc-212">Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="ba7bc-213">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ba7bc-p111">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ba7bc-216">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ba7bc-217">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ba7bc-218">Individuare la riga contenente il nome del dominio che si desidera modificare. e quindi, in tale riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ba7bc-219">Scorrere fino alla **sezione Advanced Technical Settings** e quindi selezionare Edit TXT Records **(SPF)**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selezionare Modifica record TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="ba7bc-221">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ba7bc-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-223">\*\*\*\*Record TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="ba7bc-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ba7bc-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ba7bc-225">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiare e incollare i valori dalla tabella](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="ba7bc-227">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-227">Select **Continue**.</span></span>
    
    ![Selezionare Continua](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="ba7bc-229">Nella pagina successiva selezionare di nuovo **Continua** per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selezionare Continua](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba7bc-231">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba7bc-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ba7bc-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ba7bc-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="ba7bc-233">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ba7bc-p112">Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ba7bc-236">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ba7bc-237">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ba7bc-238">Individuare la riga contenente il nome del dominio che si desidera modificare. e quindi, in tale riga, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ba7bc-239">Scorrere fino alla **sezione Impostazioni tecniche avanzate** e quindi selezionare Modifica record **SRV.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selezionare Modifica record SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="ba7bc-241">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="ba7bc-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="ba7bc-242">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="ba7bc-243">Scegliere il **valore Priority** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ba7bc-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-248">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="ba7bc-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ba7bc-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba7bc-251">_sip</span><span class="sxs-lookup"><span data-stu-id="ba7bc-251">_sip</span></span>  <br/> |<span data-ttu-id="ba7bc-252">_tls</span><span class="sxs-lookup"><span data-stu-id="ba7bc-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="ba7bc-253">High</span><span class="sxs-lookup"><span data-stu-id="ba7bc-253">High</span></span>  <br/> |<span data-ttu-id="ba7bc-254">1</span><span class="sxs-lookup"><span data-stu-id="ba7bc-254">1</span></span>  <br/> |<span data-ttu-id="ba7bc-255">443</span><span class="sxs-lookup"><span data-stu-id="ba7bc-255">443</span></span>  <br/> |<span data-ttu-id="ba7bc-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ba7bc-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ba7bc-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ba7bc-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="ba7bc-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="ba7bc-259">High</span><span class="sxs-lookup"><span data-stu-id="ba7bc-259">High</span></span>  <br/> |<span data-ttu-id="ba7bc-260">1</span><span class="sxs-lookup"><span data-stu-id="ba7bc-260">1</span></span>  <br/> |<span data-ttu-id="ba7bc-261">5061</span><span class="sxs-lookup"><span data-stu-id="ba7bc-261">5061</span></span>  <br/> |<span data-ttu-id="ba7bc-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba7bc-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiare e incollare i valori dalla tabella](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="ba7bc-264">Selezionare **Aggiungi altri record SRV.**</span><span class="sxs-lookup"><span data-stu-id="ba7bc-264">Select **Add more SRV records**.</span></span>
    
    ![Selezionare Aggiungi altri record SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="ba7bc-266">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="ba7bc-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="ba7bc-267">Digitare o copiare e incollare i valori della seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="ba7bc-268">Dopo aver aggiunto entrambi i record SRV, selezionare **Continua**.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selezionare Continua](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="ba7bc-270">Nella pagina successiva selezionare di nuovo **Continua** per confermare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ba7bc-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selezionare Continua](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="ba7bc-p113">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ba7bc-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
