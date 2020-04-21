---
title: Creare record DNS in Freenom per Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Freenom per Microsoft.
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629564"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="639d2-103">Creare record DNS in Freenom per Microsoft</span><span class="sxs-lookup"><span data-stu-id="639d2-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="639d2-104">Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="639d2-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="639d2-105">Il sito Web Freenom non supporta i record SRV, quindi diverse funzionalità di Skype for Business Online e Outlook Web App non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="639d2-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="639d2-106">Indipendentemente dal piano Microsoft utilizzato, sono presenti limitazioni rilevanti del servizio e potrebbe essere opportuno passare a un provider di hosting DNS diverso.</span><span class="sxs-lookup"><span data-stu-id="639d2-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="639d2-107">Se nonostante le limitazioni del servizio, si sceglie di gestire i propri record Microsoft DNS in Freenom, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="639d2-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="639d2-108">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="639d2-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="639d2-p102">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="639d2-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="639d2-112">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="639d2-112">Add a TXT record for verification</span></span>
<span data-ttu-id="639d2-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="639d2-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="639d2-114">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="639d2-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="639d2-115">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="639d2-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="639d2-p104">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="639d2-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="639d2-118">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="639d2-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="639d2-119">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="639d2-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="639d2-121">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="639d2-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="639d2-123">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="639d2-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="639d2-125">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="639d2-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="639d2-127">In **Add Record** scegliere **TXT** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="639d2-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="639d2-129">Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="639d2-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="639d2-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="639d2-130">**Name**</span></span>|<span data-ttu-id="639d2-131">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="639d2-131">**Type**</span></span>|<span data-ttu-id="639d2-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="639d2-132">**TTL**</span></span>|<span data-ttu-id="639d2-133">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="639d2-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="639d2-134">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="639d2-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="639d2-135">TXT</span><span class="sxs-lookup"><span data-stu-id="639d2-135">TXT</span></span>  <br/> |<span data-ttu-id="639d2-136">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="639d2-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="639d2-138">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="639d2-138">**Note:** This is an example.</span></span> <span data-ttu-id="639d2-139">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="639d2-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="639d2-140">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="639d2-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="639d2-142">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="639d2-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="639d2-144">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="639d2-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="639d2-145">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="639d2-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="639d2-146">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="639d2-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="639d2-147">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="639d2-147">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="639d2-148">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="639d2-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="639d2-149">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="639d2-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="639d2-150">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="639d2-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="639d2-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="639d2-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="639d2-154">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="639d2-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="639d2-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="639d2-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="639d2-156">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="639d2-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="639d2-157">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="639d2-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="639d2-159">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="639d2-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="639d2-161">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="639d2-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="639d2-163">Impostare il nome utilizzato per il dominio sui server dei nomi predefiniti di Freenom.</span><span class="sxs-lookup"><span data-stu-id="639d2-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="639d2-164">Selezionare **strumenti di gestione**e quindi fare clic su **Server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="639d2-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="639d2-166">Verificare che sia selezionata l'opzione **Usa server dei nomi predefiniti** , quindi selezionare **Cambia server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="639d2-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="639d2-168">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="639d2-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="639d2-170">In **Add Record** scegliere **MX** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="639d2-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="639d2-172">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente..</span><span class="sxs-lookup"><span data-stu-id="639d2-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="639d2-173">**Nome**</span><span class="sxs-lookup"><span data-stu-id="639d2-173">**Name**</span></span>|<span data-ttu-id="639d2-174">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="639d2-174">**Type**</span></span>|<span data-ttu-id="639d2-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="639d2-175">**TTL**</span></span>|<span data-ttu-id="639d2-176">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="639d2-176">**Target**</span></span>|<span data-ttu-id="639d2-177">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="639d2-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="639d2-178">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="639d2-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="639d2-179">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="639d2-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="639d2-180">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-181">\<Domain-Key\>. mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="639d2-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="639d2-182">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="639d2-182">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="639d2-183">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="639d2-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="639d2-184">10 </span><span class="sxs-lookup"><span data-stu-id="639d2-184">10</span></span>  <br/> <span data-ttu-id="639d2-185">Per altre informazioni sulla priorità, vedere [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9).</span><span class="sxs-lookup"><span data-stu-id="639d2-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="639d2-187">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="639d2-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="639d2-189">Se ci sono altri record MX, eliminarli.</span><span class="sxs-lookup"><span data-stu-id="639d2-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="639d2-190">Per ogni record, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="639d2-190">For each record, select **Delete**.</span></span> <span data-ttu-id="639d2-191">Quando **si vuole davvero rimuovere questa voce?** viene visualizzata, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="639d2-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="639d2-192">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="639d2-192">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="639d2-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="639d2-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="639d2-194">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="639d2-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="639d2-195">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="639d2-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="639d2-197">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="639d2-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="639d2-199">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="639d2-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="639d2-201">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="639d2-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="639d2-203">In **Add Record** scegliere **CNAME** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="639d2-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="639d2-p113">Creare il primo record CNAME. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="639d2-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="639d2-207">**Nome**</span><span class="sxs-lookup"><span data-stu-id="639d2-207">**Name**</span></span>|<span data-ttu-id="639d2-208">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="639d2-208">**Record type**</span></span>|<span data-ttu-id="639d2-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="639d2-209">**TTL**</span></span>|<span data-ttu-id="639d2-210">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="639d2-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="639d2-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="639d2-211">autodiscover</span></span>  <br/> |<span data-ttu-id="639d2-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="639d2-212">CNAME</span></span>  <br/> |<span data-ttu-id="639d2-213">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="639d2-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="639d2-215">sip</span><span class="sxs-lookup"><span data-stu-id="639d2-215">sip</span></span>  <br/> |<span data-ttu-id="639d2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="639d2-216">CNAME</span></span>  <br/> |<span data-ttu-id="639d2-217">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="639d2-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="639d2-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="639d2-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="639d2-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="639d2-220">CNAME</span></span>  <br/> |<span data-ttu-id="639d2-221">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="639d2-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="639d2-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="639d2-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="639d2-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="639d2-224">CNAME</span></span>  <br/> |<span data-ttu-id="639d2-225">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="639d2-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="639d2-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="639d2-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="639d2-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="639d2-228">CNAME</span></span>  <br/> |<span data-ttu-id="639d2-229">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="639d2-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="639d2-232">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="639d2-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="639d2-234">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="639d2-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="639d2-235">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="639d2-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="639d2-236">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="639d2-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="639d2-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="639d2-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="639d2-238">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="639d2-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="639d2-239">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="639d2-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="639d2-240">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="639d2-240">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="639d2-241">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="639d2-241">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="639d2-242">Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="639d2-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="639d2-243">Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="639d2-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="639d2-245">Selezionare **Servizi**, quindi selezionare **domini personali**.</span><span class="sxs-lookup"><span data-stu-id="639d2-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="639d2-247">Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.</span><span class="sxs-lookup"><span data-stu-id="639d2-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="639d2-249">Selezionare **Gestisci FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="639d2-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="639d2-251">In **Add Record** scegliere **TXT** dal menu nella colonna **Type**.</span><span class="sxs-lookup"><span data-stu-id="639d2-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="639d2-253">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="639d2-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="639d2-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="639d2-254">**Name**</span></span>|<span data-ttu-id="639d2-255">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="639d2-255">**Record type**</span></span>|<span data-ttu-id="639d2-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="639d2-256">**TTL**</span></span>|<span data-ttu-id="639d2-257">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="639d2-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="639d2-258">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="639d2-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="639d2-259">TXT</span><span class="sxs-lookup"><span data-stu-id="639d2-259">TXT</span></span>  <br/> |<span data-ttu-id="639d2-260">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="639d2-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="639d2-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="639d2-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="639d2-262">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="639d2-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="639d2-264">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="639d2-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

