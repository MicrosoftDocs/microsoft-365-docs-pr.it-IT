---
title: Creare record DNS in Freenom per Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Freenom per Microsoft.
ms.openlocfilehash: 2fc2407193d41d6e0526aacad0b2b558f1b21bdb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646188"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="d59ce-103">Creare record DNS in Freenom per Microsoft</span><span class="sxs-lookup"><span data-stu-id="d59ce-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="d59ce-104">Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d59ce-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d59ce-105">Il sito Web Freenom non supporta i record SRV, quindi diverse funzionalità di Skype for Business Online e Outlook Web App non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="d59ce-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="d59ce-106">Indipendentemente dal piano Microsoft utilizzato, sono presenti limitazioni rilevanti del servizio e potrebbe essere opportuno passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="d59ce-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="d59ce-107">Se nonostante le limitazioni del servizio, si sceglie di gestire i propri record Microsoft DNS in Freenom, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="d59ce-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="d59ce-p102">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d59ce-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d59ce-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="d59ce-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d59ce-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="d59ce-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="d59ce-p103">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="d59ce-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d59ce-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="d59ce-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d59ce-117">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="d59ce-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="d59ce-118">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="d59ce-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="d59ce-120">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="d59ce-122">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="d59ce-124">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="d59ce-126">In **Add Record** scegliere **TXT** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="d59ce-128">Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d59ce-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d59ce-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d59ce-129">**Name**</span></span>|<span data-ttu-id="d59ce-130">**Type**</span><span class="sxs-lookup"><span data-stu-id="d59ce-130">**Type**</span></span>|<span data-ttu-id="d59ce-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d59ce-131">**TTL**</span></span>|<span data-ttu-id="d59ce-132">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="d59ce-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d59ce-133">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="d59ce-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="d59ce-134">TXT</span><span class="sxs-lookup"><span data-stu-id="d59ce-134">TXT</span></span>  <br/> |<span data-ttu-id="d59ce-135">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-136">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="d59ce-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="d59ce-137">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="d59ce-137">**Note:** This is an example.</span></span> <span data-ttu-id="d59ce-138">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="d59ce-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d59ce-139">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="d59ce-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="d59ce-141">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="d59ce-143">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="d59ce-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d59ce-144">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="d59ce-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d59ce-145">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="d59ce-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d59ce-146">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="d59ce-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d59ce-147">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="d59ce-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d59ce-148">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d59ce-149">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d59ce-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d59ce-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d59ce-153">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="d59ce-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d59ce-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="d59ce-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="d59ce-155">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="d59ce-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="d59ce-156">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="d59ce-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="d59ce-158">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="d59ce-160">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="d59ce-162">Impostare il nome utilizzato per il dominio sui server dei nomi predefiniti di Freenom.</span><span class="sxs-lookup"><span data-stu-id="d59ce-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="d59ce-163">Selezionare **strumenti di gestione**e quindi fare clic su **Server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="d59ce-165">Verificare che sia selezionata l'opzione **Usa server dei nomi predefiniti** , quindi selezionare **Cambia server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="d59ce-167">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="d59ce-169">In **Add Record** scegliere **MX** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="d59ce-171">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente..</span><span class="sxs-lookup"><span data-stu-id="d59ce-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="d59ce-172">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d59ce-172">**Name**</span></span>|<span data-ttu-id="d59ce-173">**Type**</span><span class="sxs-lookup"><span data-stu-id="d59ce-173">**Type**</span></span>|<span data-ttu-id="d59ce-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d59ce-174">**TTL**</span></span>|<span data-ttu-id="d59ce-175">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="d59ce-175">**Target**</span></span>|<span data-ttu-id="d59ce-176">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="d59ce-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d59ce-177">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="d59ce-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="d59ce-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="d59ce-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="d59ce-179">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-180">\<domain-key\>. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d59ce-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d59ce-181">**Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d59ce-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="d59ce-182">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="d59ce-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d59ce-183">10  </span><span class="sxs-lookup"><span data-stu-id="d59ce-183">10</span></span>  <br/> <span data-ttu-id="d59ce-184">Per altre informazioni sulla priorità, vedere [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="d59ce-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="d59ce-186">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="d59ce-188">Se ci sono altri record MX, eliminarli.</span><span class="sxs-lookup"><span data-stu-id="d59ce-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="d59ce-189">Per ogni record, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-189">For each record, select **Delete**.</span></span> <span data-ttu-id="d59ce-190">Quando **si vuole davvero rimuovere questa voce?** viene visualizzata, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d59ce-191">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="d59ce-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d59ce-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="d59ce-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="d59ce-193">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="d59ce-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="d59ce-194">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="d59ce-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="d59ce-196">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="d59ce-198">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="d59ce-200">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="d59ce-202">In **Add Record** scegliere **CNAME** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="d59ce-p113">Creare il primo record CNAME. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d59ce-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="d59ce-206">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d59ce-206">**Name**</span></span>|<span data-ttu-id="d59ce-207">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d59ce-207">**Record type**</span></span>|<span data-ttu-id="d59ce-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d59ce-208">**TTL**</span></span>|<span data-ttu-id="d59ce-209">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="d59ce-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d59ce-210">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="d59ce-210">autodiscover</span></span>  <br/> |<span data-ttu-id="d59ce-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="d59ce-211">CNAME</span></span>  <br/> |<span data-ttu-id="d59ce-212">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d59ce-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d59ce-214">sip</span><span class="sxs-lookup"><span data-stu-id="d59ce-214">sip</span></span>  <br/> |<span data-ttu-id="d59ce-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="d59ce-215">CNAME</span></span>  <br/> |<span data-ttu-id="d59ce-216">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d59ce-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d59ce-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d59ce-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d59ce-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="d59ce-219">CNAME</span></span>  <br/> |<span data-ttu-id="d59ce-220">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d59ce-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d59ce-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d59ce-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d59ce-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="d59ce-223">CNAME</span></span>  <br/> |<span data-ttu-id="d59ce-224">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d59ce-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d59ce-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d59ce-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d59ce-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="d59ce-227">CNAME</span></span>  <br/> |<span data-ttu-id="d59ce-228">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d59ce-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="d59ce-231">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="d59ce-233">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="d59ce-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="d59ce-234">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d59ce-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d59ce-235">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="d59ce-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d59ce-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="d59ce-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d59ce-237">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="d59ce-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d59ce-238">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d59ce-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d59ce-239">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d59ce-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d59ce-240">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="d59ce-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="d59ce-241">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="d59ce-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="d59ce-242">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="d59ce-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="d59ce-244">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="d59ce-246">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="d59ce-248">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="d59ce-250">In **Add Record** scegliere **TXT** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="d59ce-252">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="d59ce-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="d59ce-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d59ce-253">**Name**</span></span>|<span data-ttu-id="d59ce-254">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d59ce-254">**Record type**</span></span>|<span data-ttu-id="d59ce-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d59ce-255">**TTL**</span></span>|<span data-ttu-id="d59ce-256">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="d59ce-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d59ce-257">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="d59ce-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="d59ce-258">TXT</span><span class="sxs-lookup"><span data-stu-id="d59ce-258">TXT</span></span>  <br/> |<span data-ttu-id="d59ce-259">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="d59ce-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d59ce-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d59ce-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="d59ce-261">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="d59ce-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="d59ce-263">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d59ce-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

