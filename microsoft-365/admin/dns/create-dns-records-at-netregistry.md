---
title: Creare record DNS su Netregistry per Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi su Netregistry per Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657804"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="df643-103">Creare record DNS su Netregistry per Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="df643-104">Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="df643-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df643-105">Se il provider di hosting DNS è Netregistry, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="df643-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df643-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="df643-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="df643-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="df643-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="df643-108">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="df643-109">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="df643-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="df643-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="df643-111">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="df643-112">Dopo aver aggiunto questi record in Netregistry, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df643-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="df643-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df643-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df643-116">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="df643-116">Add a TXT record for verification</span></span>
<span data-ttu-id="df643-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="df643-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="df643-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="df643-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df643-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="df643-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="df643-122">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="df643-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df643-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df643-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="df643-125">Accanto al dominio che si desidera gestire, selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="df643-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="df643-127">Selezionare **Gestione aree.**</span><span class="sxs-lookup"><span data-stu-id="df643-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="df643-129">In **Add a zone record** scegliere TXT **Record** nell'elenco e quindi selezionare Create **new record.**</span><span class="sxs-lookup"><span data-stu-id="df643-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="df643-131">È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT.</span><span class="sxs-lookup"><span data-stu-id="df643-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="df643-132">Nella maschera **Nuovo record TXT** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df643-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="df643-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df643-133">**Name**</span></span>|<span data-ttu-id="df643-134">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="df643-134">**TTL (SEC)**</span></span>|<span data-ttu-id="df643-135">**TXT (Indirizzo o valore di puntamento)**</span><span class="sxs-lookup"><span data-stu-id="df643-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df643-136">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="df643-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="df643-137">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-138">"MS=msXXXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="df643-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="df643-139">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="df643-139">**Note:** This is an example.</span></span> <span data-ttu-id="df643-140">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="df643-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="df643-141">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="df643-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="df643-143">Selezionare **Aggiungi record.**</span><span class="sxs-lookup"><span data-stu-id="df643-143">Select **Add record**.</span></span>
    
<span data-ttu-id="df643-144">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="df643-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="df643-145">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="df643-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df643-146">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="df643-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="df643-147">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="df643-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="df643-148">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="df643-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="df643-149">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="df643-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="df643-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df643-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df643-153">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="df643-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="df643-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="df643-155">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="df643-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df643-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df643-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="df643-158">Accanto al dominio che si desidera gestire, selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="df643-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="df643-160">Selezionare **Gestione aree.**</span><span class="sxs-lookup"><span data-stu-id="df643-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="df643-162">In **Record dell'area corrente** rimuovere i record MX predefiniti selezionando **Rimuovi** accanto a ogni record MX nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df643-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="df643-164">In **Add a zone record**, choose MX **Record** from the list, and then select Create **new record**.</span><span class="sxs-lookup"><span data-stu-id="df643-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="df643-166">Nella maschera **Nuovo record MX** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df643-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="df643-167">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df643-167">**Name**</span></span>|<span data-ttu-id="df643-168">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="df643-168">**TTL (SEC)**</span></span>|<span data-ttu-id="df643-169">**Exchange (indirizzo o valore di puntamento)**</span><span class="sxs-lookup"><span data-stu-id="df643-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="df643-170">**L'host è completo?**</span><span class="sxs-lookup"><span data-stu-id="df643-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="df643-171">**Preferenza (priorità)**</span><span class="sxs-lookup"><span data-stu-id="df643-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df643-172">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="df643-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="df643-173">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="df643-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df643-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="df643-175">**Nota:** Ottenere il  *\<domain-key\>*  proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df643-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="df643-176">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="df643-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="df643-177">(selezionare la casella di controllo)</span><span class="sxs-lookup"><span data-stu-id="df643-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="df643-178">10  </span><span class="sxs-lookup"><span data-stu-id="df643-178">10</span></span>  <br/> <span data-ttu-id="df643-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="df643-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="df643-181">Selezionare **Aggiungi record.**</span><span class="sxs-lookup"><span data-stu-id="df643-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="df643-183">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="df643-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="df643-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="df643-185">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="df643-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df643-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df643-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="df643-188">Accanto al dominio che si desidera gestire, selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="df643-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="df643-190">Selezionare **Gestione aree.**</span><span class="sxs-lookup"><span data-stu-id="df643-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="df643-192">In **Add a zone record** scegliere **CNAME Record** nell'elenco e quindi selezionare Create new **record.**</span><span class="sxs-lookup"><span data-stu-id="df643-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="df643-194">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df643-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df643-195">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df643-195">**Name**</span></span>|<span data-ttu-id="df643-196">**Type**</span><span class="sxs-lookup"><span data-stu-id="df643-196">**Type**</span></span>|<span data-ttu-id="df643-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df643-197">**TTL**</span></span>|<span data-ttu-id="df643-198">**HOST (punta a o valore indirizzo)**</span><span class="sxs-lookup"><span data-stu-id="df643-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df643-199">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="df643-199">autodiscover</span></span>  <br/> |<span data-ttu-id="df643-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="df643-200">CNAME</span></span>  <br/> |<span data-ttu-id="df643-201">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df643-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="df643-203">sip</span><span class="sxs-lookup"><span data-stu-id="df643-203">sip</span></span>  <br/> |<span data-ttu-id="df643-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="df643-204">CNAME</span></span>  <br/> |<span data-ttu-id="df643-205">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df643-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df643-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df643-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df643-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="df643-208">CNAME</span></span>  <br/> |<span data-ttu-id="df643-209">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df643-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df643-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df643-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df643-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="df643-212">CNAME</span></span>  <br/> |<span data-ttu-id="df643-213">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df643-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="df643-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df643-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df643-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="df643-216">CNAME</span></span>  <br/> |<span data-ttu-id="df643-217">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df643-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="df643-220">Selezionare **Aggiungi record.**</span><span class="sxs-lookup"><span data-stu-id="df643-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="df643-222">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="df643-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="df643-223">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="df643-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df643-224">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="df643-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df643-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="df643-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df643-226">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="df643-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df643-227">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="df643-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df643-228">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df643-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="df643-229">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="df643-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="df643-230">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="df643-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df643-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df643-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="df643-233">Accanto al dominio che si desidera gestire, selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="df643-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="df643-235">Selezionare **Gestione aree.**</span><span class="sxs-lookup"><span data-stu-id="df643-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="df643-237">In **Add a zone record** scegliere TXT **Record** nell'elenco e quindi selezionare Create **new record.**</span><span class="sxs-lookup"><span data-stu-id="df643-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="df643-239">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df643-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="df643-240">È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT.</span><span class="sxs-lookup"><span data-stu-id="df643-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="df643-241">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df643-241">**Name**</span></span>|<span data-ttu-id="df643-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="df643-242">**Type**</span></span>|<span data-ttu-id="df643-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df643-243">**TTL**</span></span>|<span data-ttu-id="df643-244">**Dati TXT (destinazione)**</span><span class="sxs-lookup"><span data-stu-id="df643-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df643-245">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="df643-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="df643-246">TXT</span><span class="sxs-lookup"><span data-stu-id="df643-246">TXT</span></span>  <br/> |<span data-ttu-id="df643-247">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-248">"v=spf1 include:spf.protection.outlook.com -all"</span><span class="sxs-lookup"><span data-stu-id="df643-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="df643-249">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="df643-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="df643-251">Selezionare **Aggiungi record.**</span><span class="sxs-lookup"><span data-stu-id="df643-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="df643-253">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="df643-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="df643-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="df643-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="df643-255">Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="df643-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df643-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df643-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="df643-258">Accanto al dominio che si desidera gestire, selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="df643-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="df643-260">Selezionare **Gestione aree.**</span><span class="sxs-lookup"><span data-stu-id="df643-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="df643-262">In **Aggiungi un record di zona** scegliere Record **SRV** nell'elenco e quindi **selezionare Crea nuovo record.**</span><span class="sxs-lookup"><span data-stu-id="df643-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="df643-264">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df643-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df643-265">Il campo Nome è una combinazione di servizio (ad esempio, _sip) e protocollo (ad esempio, _tls).</span><span class="sxs-lookup"><span data-stu-id="df643-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="df643-266">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="df643-266">**Type**</span></span>|<span data-ttu-id="df643-267">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df643-267">**Name**</span></span>|<span data-ttu-id="df643-268">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="df643-268">**TTL (SEC)**</span></span>|<span data-ttu-id="df643-269">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="df643-269">**Priority**</span></span>|<span data-ttu-id="df643-270">**Peso**</span><span class="sxs-lookup"><span data-stu-id="df643-270">**Weight**</span></span>|<span data-ttu-id="df643-271">**Porta**</span><span class="sxs-lookup"><span data-stu-id="df643-271">**Port**</span></span>|<span data-ttu-id="df643-272">**Target**</span><span class="sxs-lookup"><span data-stu-id="df643-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df643-273">SRV (servizio)</span><span class="sxs-lookup"><span data-stu-id="df643-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="df643-274">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="df643-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="df643-275">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-276">100</span><span class="sxs-lookup"><span data-stu-id="df643-276">100</span></span>  <br/> |<span data-ttu-id="df643-277">1 </span><span class="sxs-lookup"><span data-stu-id="df643-277">1</span></span>  <br/> |<span data-ttu-id="df643-278">443</span><span class="sxs-lookup"><span data-stu-id="df643-278">443</span></span>  <br/> |<span data-ttu-id="df643-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df643-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df643-280">SRV (servizio)</span><span class="sxs-lookup"><span data-stu-id="df643-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="df643-281">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="df643-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="df643-282">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="df643-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df643-283">100</span><span class="sxs-lookup"><span data-stu-id="df643-283">100</span></span>  <br/> |<span data-ttu-id="df643-284">1 </span><span class="sxs-lookup"><span data-stu-id="df643-284">1</span></span>  <br/> |<span data-ttu-id="df643-285">5061</span><span class="sxs-lookup"><span data-stu-id="df643-285">5061</span></span>  <br/> |<span data-ttu-id="df643-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df643-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="df643-288">Selezionare **Aggiungi record.**</span><span class="sxs-lookup"><span data-stu-id="df643-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="df643-290">Ripetere i passaggi precedenti per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="df643-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="df643-291">Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="df643-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="df643-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df643-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

