---
title: Creare record DNS su GoDaddy per Microsoft
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi su GoDaddy per Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: b1c5539af6683bbf8f94fd15880fb870caf31342
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049024"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="b187f-103">Creare record DNS su GoDaddy per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b187f-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="b187f-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b187f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="b187f-105">Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="b187f-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="b187f-106">Dopo aver aggiunto questi record in GoDaddy, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b187f-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="b187f-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b187f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b187f-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="b187f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b187f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b187f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b187f-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="b187f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b187f-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="b187f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="b187f-116">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-116">Follow the steps below.</span></span>

1. <span data-ttu-id="b187f-p104">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b187f-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="b187f-120">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="b187f-122">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b187f-122">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="b187f-124">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="b187f-125">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b187f-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="b187f-126">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="b187f-126">**Record type**</span></span> |<span data-ttu-id="b187f-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="b187f-127">**Host**</span></span>|<span data-ttu-id="b187f-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b187f-128">**TXT Value**</span></span>|<span data-ttu-id="b187f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b187f-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b187f-130">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="b187f-130">TXT (Text)</span></span>|@|<span data-ttu-id="b187f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b187f-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="b187f-132">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="b187f-132">**Note**: This is an example.</span></span> <span data-ttu-id="b187f-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b187f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b187f-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="b187f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="b187f-135">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-135">1 hour</span></span>  <br><span data-ttu-id="b187f-136">Selezionare un valore nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="b187f-138">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b187f-138">Select **Save**.</span></span>

6. <span data-ttu-id="b187f-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="b187f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="b187f-140">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="b187f-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="b187f-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="b187f-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b187f-142">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="b187f-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b187f-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b187f-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b187f-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="b187f-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="b187f-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="b187f-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b187f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b187f-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="b187f-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b187f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b187f-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b187f-151">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-151">Follow the steps below.</span></span>

1. <span data-ttu-id="b187f-p108">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b187f-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="b187f-155">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="b187f-157">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b187f-157">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="b187f-159">Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="b187f-161">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b187f-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="b187f-162">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="b187f-163">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="b187f-163">**Record type**</span></span>|<span data-ttu-id="b187f-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="b187f-164">**Host**</span></span>|<span data-ttu-id="b187f-165">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="b187f-165">**Points to**</span></span>|<span data-ttu-id="b187f-166">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="b187f-166">**Priority**</span></span>|<span data-ttu-id="b187f-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b187f-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b187f-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="b187f-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="b187f-169">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b187f-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b187f-170">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b187f-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="b187f-171">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="b187f-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b187f-172">10  </span><span class="sxs-lookup"><span data-stu-id="b187f-172">10</span></span>  <br/> <span data-ttu-id="b187f-173">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="b187f-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="b187f-174">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="b187f-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b187f-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b187f-176">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b187f-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b187f-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b187f-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b187f-178">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-178">Follow the steps below.</span></span>

1. <span data-ttu-id="b187f-p110">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b187f-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="b187f-182">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="b187f-184">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b187f-184">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="b187f-186">Scegliere **CNAME (Alias)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="b187f-188">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="b187f-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="b187f-189">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b187f-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="b187f-190">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="b187f-191">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="b187f-191">**Record type**</span></span>|<span data-ttu-id="b187f-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="b187f-192">**Host**</span></span>|<span data-ttu-id="b187f-193">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="b187f-193">**Points to**</span></span>|<span data-ttu-id="b187f-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b187f-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b187f-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="b187f-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b187f-196">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="b187f-196">autodiscover</span></span>  <br/> |<span data-ttu-id="b187f-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b187f-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="b187f-198">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="b187f-199">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b187f-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b187f-200">sip</span><span class="sxs-lookup"><span data-stu-id="b187f-200">sip</span></span>  <br/> |<span data-ttu-id="b187f-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b187f-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b187f-202">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="b187f-203">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b187f-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b187f-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b187f-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b187f-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b187f-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b187f-206">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="b187f-207">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b187f-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b187f-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b187f-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b187f-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b187f-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="b187f-210">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="b187f-211">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="b187f-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b187f-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b187f-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b187f-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b187f-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="b187f-214">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="b187f-215">Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="b187f-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b187f-216">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="b187f-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b187f-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b187f-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b187f-218">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="b187f-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b187f-219">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b187f-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b187f-220">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b187f-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b187f-221">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="b187f-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="b187f-222">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-222">Follow the steps below.</span></span>

1. <span data-ttu-id="b187f-p112">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b187f-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="b187f-226">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="b187f-228">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b187f-228">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="b187f-230">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="b187f-232">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="b187f-233">Scegliere il valore **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="b187f-234">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="b187f-234">**Record type**</span></span>|<span data-ttu-id="b187f-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="b187f-235">**Host**</span></span>|<span data-ttu-id="b187f-236">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b187f-236">**TXT Value**</span></span>|<span data-ttu-id="b187f-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b187f-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b187f-238">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="b187f-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="b187f-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b187f-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b187f-240">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="b187f-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="b187f-241">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="b187f-243">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b187f-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b187f-244">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="b187f-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b187f-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b187f-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b187f-246">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b187f-246">Follow the steps below.</span></span>

1. <span data-ttu-id="b187f-p113">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b187f-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="b187f-250">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b187f-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="b187f-252">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b187f-252">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="b187f-254">Scegliere **SRV** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="b187f-256">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="b187f-256">Create the first SRV record.</span></span>

    <span data-ttu-id="b187f-257">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b187f-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="b187f-258">Scegliere il **tipo di record** e i valori **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="b187f-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="b187f-259">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="b187f-259">**Record type**</span></span>|<span data-ttu-id="b187f-260">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b187f-260">**Name**</span></span>|<span data-ttu-id="b187f-261">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="b187f-261">**Target**</span></span>|<span data-ttu-id="b187f-262">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="b187f-262">**Protocol**</span></span>|<span data-ttu-id="b187f-263">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="b187f-263">**Service**</span></span>|<span data-ttu-id="b187f-264">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="b187f-264">**Priority**</span></span>|<span data-ttu-id="b187f-265">**Peso**</span><span class="sxs-lookup"><span data-stu-id="b187f-265">**Weight**</span></span>|<span data-ttu-id="b187f-266">**Porta**</span><span class="sxs-lookup"><span data-stu-id="b187f-266">**Port**</span></span>|<span data-ttu-id="b187f-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b187f-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b187f-268">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="b187f-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="b187f-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b187f-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b187f-270">_tls</span><span class="sxs-lookup"><span data-stu-id="b187f-270">_tls</span></span>  <br/> |<span data-ttu-id="b187f-271">_sip</span><span class="sxs-lookup"><span data-stu-id="b187f-271">_sip</span></span>  <br/> |<span data-ttu-id="b187f-272">100</span><span class="sxs-lookup"><span data-stu-id="b187f-272">100</span></span>  <br/> |<span data-ttu-id="b187f-273">1</span><span class="sxs-lookup"><span data-stu-id="b187f-273">1</span></span>  <br/> |<span data-ttu-id="b187f-274">443</span><span class="sxs-lookup"><span data-stu-id="b187f-274">443</span></span>  <br/> |<span data-ttu-id="b187f-275">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="b187f-276">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="b187f-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="b187f-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b187f-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="b187f-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="b187f-278">_tcp</span></span>  <br/> |<span data-ttu-id="b187f-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b187f-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b187f-280">100</span><span class="sxs-lookup"><span data-stu-id="b187f-280">100</span></span>  <br/> |<span data-ttu-id="b187f-281">1</span><span class="sxs-lookup"><span data-stu-id="b187f-281">1</span></span>  <br/> |<span data-ttu-id="b187f-282">5061</span><span class="sxs-lookup"><span data-stu-id="b187f-282">5061</span></span>  <br/> |<span data-ttu-id="b187f-283">1 ora</span><span class="sxs-lookup"><span data-stu-id="b187f-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="b187f-285">Ripetere il **passaggio 5** per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="b187f-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="b187f-286">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b187f-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b187f-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b187f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
