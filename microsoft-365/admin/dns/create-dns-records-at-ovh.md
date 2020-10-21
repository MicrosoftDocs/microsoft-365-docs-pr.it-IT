---
title: Creare record DNS in OVH per Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in OVH per Microsoft.
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645816"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="19f04-103">Creare record DNS in OVH per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="19f04-104">Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="19f04-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="19f04-105">Se OVH è il provider di hosting DNS in uso, eseguire i passaggi descritti in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="19f04-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="19f04-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="19f04-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="19f04-107">Creare record DNS in OVH per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="19f04-108">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="19f04-109">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="19f04-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="19f04-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="19f04-111">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="19f04-112">Dopo aver aggiunto questi record in OVH, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19f04-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="19f04-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19f04-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="19f04-116">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="19f04-116">Add a TXT record for verification</span></span>
<span data-ttu-id="19f04-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="19f04-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="19f04-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="19f04-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19f04-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="19f04-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="19f04-p104">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="19f04-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="19f04-125">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="19f04-127">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="19f04-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="19f04-129">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="19f04-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="19f04-131">Seleziona **txt**</span><span class="sxs-lookup"><span data-stu-id="19f04-131">Select **TXT**</span></span>
    
    ![OVH Seleziona voce TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="19f04-133">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19f04-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="19f04-134">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="19f04-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="19f04-135">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="19f04-135">**Record type**</span></span>|<span data-ttu-id="19f04-136">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="19f04-136">**Sub-domain**</span></span>|<span data-ttu-id="19f04-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19f04-137">**TTL**</span></span>|<span data-ttu-id="19f04-138">**Valore**</span><span class="sxs-lookup"><span data-stu-id="19f04-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19f04-139">TXT</span><span class="sxs-lookup"><span data-stu-id="19f04-139">TXT</span></span>  <br/> |<span data-ttu-id="19f04-140">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="19f04-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="19f04-141">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="19f04-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="19f04-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="19f04-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="19f04-143">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="19f04-143">**Note:** This is an example.</span></span> <span data-ttu-id="19f04-144">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="19f04-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="19f04-145">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="19f04-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="19f04-146">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="19f04-148">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="19f04-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="19f04-149">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="19f04-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="19f04-150">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="19f04-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="19f04-151">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="19f04-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="19f04-152">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="19f04-153">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="19f04-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="19f04-154">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="19f04-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="19f04-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19f04-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="19f04-158">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="19f04-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="19f04-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="19f04-p108">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="19f04-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="19f04-163">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="19f04-165">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="19f04-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="19f04-167">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="19f04-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="19f04-169">Selezionare **MX**.</span><span class="sxs-lookup"><span data-stu-id="19f04-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="19f04-171">Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19f04-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="19f04-172">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="19f04-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="19f04-173">Per impostazione predefinita, in OVH viene utilizzata la notazione relativa per la destinazione, che aggiunge il nome di dominio alla fine del record di destinazione.</span><span class="sxs-lookup"><span data-stu-id="19f04-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="19f04-174">Per usare invece la notazione assoluta, aggiungere un punto al record di destinazione, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19f04-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="19f04-175">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="19f04-175">**Record type**</span></span>|<span data-ttu-id="19f04-176">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="19f04-176">**Sub-domain**</span></span>|<span data-ttu-id="19f04-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19f04-177">**TTL**</span></span>|<span data-ttu-id="19f04-178">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="19f04-178">**Priority**</span></span>|<span data-ttu-id="19f04-179">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="19f04-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19f04-180">MX</span><span class="sxs-lookup"><span data-stu-id="19f04-180">MX</span></span>  <br/> |<span data-ttu-id="19f04-181">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="19f04-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="19f04-182">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="19f04-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="19f04-183">10  </span><span class="sxs-lookup"><span data-stu-id="19f04-183">10</span></span>  <br/> <span data-ttu-id="19f04-184">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="19f04-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="19f04-185">\<domain-key\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="19f04-186">**Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19f04-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="19f04-187">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="19f04-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Record MX OVH per la posta elettronica](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="19f04-189">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="19f04-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="19f04-191">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="19f04-193">Se sono presenti altri record MX, eliminarli tutti nella pagina **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="19f04-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="19f04-194">Selezionare ogni record e quindi, nella colonna **azioni** , selezionare l'icona Cestino-Can **Delete** .</span><span class="sxs-lookup"><span data-stu-id="19f04-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="19f04-196">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="19f04-197">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="19f04-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="19f04-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="19f04-p113">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="19f04-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="19f04-202">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="19f04-204">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="19f04-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="19f04-206">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="19f04-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="19f04-208">Selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="19f04-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="19f04-210">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="19f04-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="19f04-211">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19f04-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="19f04-212">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="19f04-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="19f04-213">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="19f04-213">**Record type**</span></span>|<span data-ttu-id="19f04-214">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="19f04-214">**Sub-domain**</span></span>|<span data-ttu-id="19f04-215">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="19f04-215">**Target**</span></span>|<span data-ttu-id="19f04-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19f04-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19f04-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="19f04-217">CNAME</span></span>  <br/> |<span data-ttu-id="19f04-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="19f04-218">autodiscover</span></span>  <br/> |<span data-ttu-id="19f04-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="19f04-220">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="19f04-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="19f04-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="19f04-221">CNAME</span></span>  <br/> |<span data-ttu-id="19f04-222">sip</span><span class="sxs-lookup"><span data-stu-id="19f04-222">sip</span></span>  <br/> |<span data-ttu-id="19f04-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="19f04-224">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="19f04-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="19f04-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="19f04-225">CNAME</span></span>  <br/> |<span data-ttu-id="19f04-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="19f04-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="19f04-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="19f04-228">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="19f04-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="19f04-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="19f04-229">CNAME</span></span>  <br/> |<span data-ttu-id="19f04-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="19f04-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="19f04-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="19f04-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="19f04-232">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="19f04-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="19f04-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="19f04-233">CNAME</span></span>  <br/> |<span data-ttu-id="19f04-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="19f04-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="19f04-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="19f04-236">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="19f04-236">3600 seconds</span></span>  <br/> |
   
    ![Record CNAME di OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="19f04-238">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="19f04-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="19f04-240">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="19f04-241">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="19f04-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="19f04-242">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="19f04-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="19f04-243">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="19f04-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="19f04-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="19f04-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="19f04-245">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="19f04-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="19f04-246">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="19f04-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="19f04-247">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19f04-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="19f04-248">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="19f04-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="19f04-p116">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="19f04-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="19f04-252">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="19f04-254">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="19f04-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="19f04-256">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="19f04-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="19f04-258">Selezionare **txt**.</span><span class="sxs-lookup"><span data-stu-id="19f04-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="19f04-259">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="19f04-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="19f04-260">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="19f04-260">**Record type**</span></span>|<span data-ttu-id="19f04-261">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="19f04-261">**Sub-domain**</span></span>|<span data-ttu-id="19f04-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19f04-262">**TTL**</span></span>|<span data-ttu-id="19f04-263">**Valore TXT**</span><span class="sxs-lookup"><span data-stu-id="19f04-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19f04-264">TXT</span><span class="sxs-lookup"><span data-stu-id="19f04-264">TXT</span></span>  <br/> |<span data-ttu-id="19f04-265">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="19f04-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="19f04-266">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="19f04-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="19f04-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="19f04-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="19f04-268">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="19f04-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH aggiungere un record TXT per SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="19f04-270">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="19f04-270">Select **Next**.</span></span>
    
    ![OVH aggiungere un record TXT per SPF e selezionare Avanti](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="19f04-272">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="19f04-274">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f04-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="19f04-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="19f04-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="19f04-p117">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="19f04-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="19f04-279">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="19f04-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="19f04-281">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="19f04-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="19f04-283">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="19f04-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="19f04-285">Selezionare **SRV**.</span><span class="sxs-lookup"><span data-stu-id="19f04-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="19f04-287">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="19f04-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="19f04-288">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19f04-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="19f04-289">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="19f04-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="19f04-290">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="19f04-290">**Record type**</span></span>|<span data-ttu-id="19f04-291">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="19f04-291">**Sub-domain**</span></span>|<span data-ttu-id="19f04-292">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="19f04-292">**Priority**</span></span>|<span data-ttu-id="19f04-293">**Peso**</span><span class="sxs-lookup"><span data-stu-id="19f04-293">**Weight**</span></span>|<span data-ttu-id="19f04-294">**Porta**</span><span class="sxs-lookup"><span data-stu-id="19f04-294">**Port**</span></span>|<span data-ttu-id="19f04-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19f04-295">**TTL**</span></span>|<span data-ttu-id="19f04-296">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="19f04-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19f04-297">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="19f04-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="19f04-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="19f04-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="19f04-299">100</span><span class="sxs-lookup"><span data-stu-id="19f04-299">100</span></span>  <br/> |<span data-ttu-id="19f04-300">1 </span><span class="sxs-lookup"><span data-stu-id="19f04-300">1</span></span>  <br/> |<span data-ttu-id="19f04-301">443</span><span class="sxs-lookup"><span data-stu-id="19f04-301">443</span></span>  <br/> |<span data-ttu-id="19f04-302">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="19f04-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="19f04-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="19f04-304">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="19f04-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="19f04-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="19f04-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="19f04-306">100</span><span class="sxs-lookup"><span data-stu-id="19f04-306">100</span></span>  <br/> |<span data-ttu-id="19f04-307">1 </span><span class="sxs-lookup"><span data-stu-id="19f04-307">1</span></span>  <br/> |<span data-ttu-id="19f04-308">5061</span><span class="sxs-lookup"><span data-stu-id="19f04-308">5061</span></span>  <br/> |<span data-ttu-id="19f04-309">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="19f04-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="19f04-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="19f04-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Record OVH SRV](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="19f04-312">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="19f04-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="19f04-314">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="19f04-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="19f04-p119">Ripetere i passaggi precedenti per creare l'altro record SRV. Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="19f04-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="19f04-p120">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19f04-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
