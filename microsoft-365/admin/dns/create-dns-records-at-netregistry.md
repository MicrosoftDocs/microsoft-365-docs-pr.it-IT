---
title: Creare record DNS in Netregistry per Office 365
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Netregistry per Office 365.
ms.openlocfilehash: 91f802afccd337a97b23ca514c9d9921595abcd1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348817"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="da474-103">Creare record DNS in Netregistry per Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="da474-104">Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="da474-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="da474-105">Se Netregistry è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="da474-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="da474-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="da474-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="da474-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="da474-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="da474-108">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="da474-109">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="da474-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="da474-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="da474-111">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="da474-112">Dopo aver aggiunto questi record in Netregistry, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="da474-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="da474-113">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="da474-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da474-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da474-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="da474-117">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="da474-117">Add a TXT record for verification</span></span>
<span data-ttu-id="da474-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="da474-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="da474-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="da474-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da474-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="da474-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="da474-123">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="da474-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="da474-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="da474-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="da474-126">Accanto al dominio che si desidera gestire, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="da474-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="da474-128">Selezionare **Gestione aree**.</span><span class="sxs-lookup"><span data-stu-id="da474-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="da474-130">In **Aggiungi un record di area**scegliere **txt record** nell'elenco e quindi selezionare **Crea nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="da474-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="da474-132">È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT.</span><span class="sxs-lookup"><span data-stu-id="da474-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="da474-133">Nella maschera **nuovo record TXT** Digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da474-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="da474-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da474-134">**Name**</span></span>|<span data-ttu-id="da474-135">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="da474-135">**TTL (SEC)**</span></span>|<span data-ttu-id="da474-136">**TXT (punta all'indirizzo o al valore)**</span><span class="sxs-lookup"><span data-stu-id="da474-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="da474-137">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="da474-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="da474-138">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="da474-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="da474-140">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="da474-140">**Note:** This is an example.</span></span> <span data-ttu-id="da474-141">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="da474-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="da474-142">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="da474-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="da474-144">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="da474-144">Select **Add record**.</span></span>
    
<span data-ttu-id="da474-145">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="da474-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="da474-146">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="da474-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="da474-147">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="da474-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="da474-148">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="da474-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="da474-149">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="da474-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="da474-150">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="da474-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="da474-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da474-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="da474-154">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="da474-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="da474-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="da474-156">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="da474-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="da474-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="da474-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="da474-159">Accanto al dominio che si desidera gestire, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="da474-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="da474-161">Selezionare **Gestione aree**.</span><span class="sxs-lookup"><span data-stu-id="da474-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="da474-163">In **current zone Records**rimuovere i record MX predefiniti selezionando **Rimuovi** accanto a ogni record MX nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="da474-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="da474-165">In **aggiungere un record di area**scegliere **record MX** dall'elenco e quindi selezionare **Crea nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="da474-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="da474-167">Nella maschera **nuovo record MX** , digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da474-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="da474-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da474-168">**Name**</span></span>|<span data-ttu-id="da474-169">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="da474-169">**TTL (SEC)**</span></span>|<span data-ttu-id="da474-170">**Exchange (punta all'indirizzo o al valore)**</span><span class="sxs-lookup"><span data-stu-id="da474-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="da474-171">**L'host è completo?**</span><span class="sxs-lookup"><span data-stu-id="da474-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="da474-172">**Preferenza (priorità)**</span><span class="sxs-lookup"><span data-stu-id="da474-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da474-173">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="da474-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="da474-174">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="da474-175">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="da474-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="da474-176">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="da474-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="da474-177">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="da474-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="da474-178">(Seleziona la casella di controllo)</span><span class="sxs-lookup"><span data-stu-id="da474-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="da474-179">10 </span><span class="sxs-lookup"><span data-stu-id="da474-179">10</span></span>  <br/> <span data-ttu-id="da474-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="da474-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="da474-182">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="da474-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="da474-184">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="da474-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="da474-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="da474-186">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="da474-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="da474-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="da474-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="da474-189">Accanto al dominio che si desidera gestire, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="da474-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="da474-191">Selezionare **Gestione aree**.</span><span class="sxs-lookup"><span data-stu-id="da474-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="da474-193">In **Aggiungi un record di area**scegliere **CNAME record** nell'elenco, quindi selezionare **Crea nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="da474-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="da474-195">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da474-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="da474-196">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da474-196">**Name**</span></span>|<span data-ttu-id="da474-197">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da474-197">**Type**</span></span>|<span data-ttu-id="da474-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da474-198">**TTL**</span></span>|<span data-ttu-id="da474-199">**HOST (indica il valore o l'indirizzo)**</span><span class="sxs-lookup"><span data-stu-id="da474-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da474-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="da474-200">autodiscover</span></span>  <br/> |<span data-ttu-id="da474-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="da474-201">CNAME</span></span>  <br/> |<span data-ttu-id="da474-202">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="da474-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="da474-204">sip</span><span class="sxs-lookup"><span data-stu-id="da474-204">sip</span></span>  <br/> |<span data-ttu-id="da474-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="da474-205">CNAME</span></span>  <br/> |<span data-ttu-id="da474-206">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="da474-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="da474-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="da474-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="da474-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="da474-209">CNAME</span></span>  <br/> |<span data-ttu-id="da474-210">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="da474-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="da474-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="da474-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="da474-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="da474-213">CNAME</span></span>  <br/> |<span data-ttu-id="da474-214">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="da474-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="da474-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="da474-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="da474-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="da474-217">CNAME</span></span>  <br/> |<span data-ttu-id="da474-218">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="da474-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="da474-221">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="da474-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="da474-223">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="da474-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="da474-224">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="da474-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="da474-225">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="da474-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="da474-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="da474-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="da474-227">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="da474-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="da474-228">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="da474-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="da474-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="da474-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="da474-230">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="da474-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="da474-231">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="da474-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="da474-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="da474-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="da474-234">Accanto al dominio che si desidera gestire, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="da474-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="da474-236">Selezionare **Gestione aree**.</span><span class="sxs-lookup"><span data-stu-id="da474-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="da474-238">In **Aggiungi un record di area**scegliere **txt record** nell'elenco e quindi selezionare **Crea nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="da474-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="da474-240">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da474-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="da474-241">È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT.</span><span class="sxs-lookup"><span data-stu-id="da474-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="da474-242">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da474-242">**Name**</span></span>|<span data-ttu-id="da474-243">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da474-243">**Type**</span></span>|<span data-ttu-id="da474-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da474-244">**TTL**</span></span>|<span data-ttu-id="da474-245">**Dati TXT (destinazione)**</span><span class="sxs-lookup"><span data-stu-id="da474-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da474-246">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="da474-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="da474-247">TXT</span><span class="sxs-lookup"><span data-stu-id="da474-247">TXT</span></span>  <br/> |<span data-ttu-id="da474-248">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-249">"v = spf1 include: SPF. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="da474-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="da474-250">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="da474-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="da474-252">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="da474-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="da474-254">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="da474-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="da474-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="da474-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="da474-256">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="da474-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="da474-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="da474-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="da474-259">Accanto al dominio che si desidera gestire, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="da474-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="da474-261">Selezionare **Gestione aree**.</span><span class="sxs-lookup"><span data-stu-id="da474-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="da474-263">In **aggiungere un record di area**scegliere **SRV record** nell'elenco e quindi selezionare **Crea nuovo record**.</span><span class="sxs-lookup"><span data-stu-id="da474-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="da474-265">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da474-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da474-266">Il campo nome è una combinazione del servizio (ad esempio, _sip) e del protocollo, ad esempio _tls.</span><span class="sxs-lookup"><span data-stu-id="da474-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="da474-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da474-267">**Type**</span></span>|<span data-ttu-id="da474-268">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da474-268">**Name**</span></span>|<span data-ttu-id="da474-269">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="da474-269">**TTL (SEC)**</span></span>|<span data-ttu-id="da474-270">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="da474-270">**Priority**</span></span>|<span data-ttu-id="da474-271">**Peso**</span><span class="sxs-lookup"><span data-stu-id="da474-271">**Weight**</span></span>|<span data-ttu-id="da474-272">**Porta**</span><span class="sxs-lookup"><span data-stu-id="da474-272">**Port**</span></span>|<span data-ttu-id="da474-273">**Target**</span><span class="sxs-lookup"><span data-stu-id="da474-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da474-274">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="da474-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="da474-275">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="da474-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="da474-276">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-277">100</span><span class="sxs-lookup"><span data-stu-id="da474-277">100</span></span>  <br/> |<span data-ttu-id="da474-278">1</span><span class="sxs-lookup"><span data-stu-id="da474-278">1</span></span>  <br/> |<span data-ttu-id="da474-279">443</span><span class="sxs-lookup"><span data-stu-id="da474-279">443</span></span>  <br/> |<span data-ttu-id="da474-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="da474-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="da474-281">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="da474-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="da474-282">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="da474-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="da474-283">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="da474-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="da474-284">100</span><span class="sxs-lookup"><span data-stu-id="da474-284">100</span></span>  <br/> |<span data-ttu-id="da474-285">1</span><span class="sxs-lookup"><span data-stu-id="da474-285">1</span></span>  <br/> |<span data-ttu-id="da474-286">5061</span><span class="sxs-lookup"><span data-stu-id="da474-286">5061</span></span>  <br/> |<span data-ttu-id="da474-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="da474-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="da474-289">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="da474-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="da474-291">Ripetere i passaggi precedenti per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="da474-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="da474-292">Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="da474-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da474-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da474-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

