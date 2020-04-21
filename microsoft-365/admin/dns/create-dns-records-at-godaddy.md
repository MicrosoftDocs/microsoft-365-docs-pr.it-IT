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
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629552"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="803c5-103">Creare record DNS su GoDaddy per Microsoft</span><span class="sxs-lookup"><span data-stu-id="803c5-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="803c5-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="803c5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="803c5-105">Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="803c5-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="803c5-106">Dopo aver aggiunto questi record in GoDaddy, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="803c5-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="803c5-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="803c5-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="803c5-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="803c5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="803c5-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="803c5-111">Add a TXT record for verification</span></span>
<span data-ttu-id="803c5-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="803c5-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="803c5-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="803c5-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="803c5-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="803c5-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="803c5-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="803c5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="803c5-117">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-117">Follow the steps below.</span></span>

1. <span data-ttu-id="803c5-p104">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="803c5-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="803c5-121">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="803c5-123">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="803c5-123">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="803c5-125">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="803c5-126">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="803c5-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="803c5-127">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="803c5-127">**Record type**</span></span> |<span data-ttu-id="803c5-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="803c5-128">**Host**</span></span>|<span data-ttu-id="803c5-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="803c5-129">**TXT Value**</span></span>|<span data-ttu-id="803c5-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="803c5-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="803c5-131">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="803c5-131">TXT (Text)</span></span>|@|<span data-ttu-id="803c5-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="803c5-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="803c5-133">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="803c5-133">**Note**: This is an example.</span></span> <span data-ttu-id="803c5-134">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="803c5-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="803c5-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="803c5-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="803c5-136">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-136">1 hour</span></span>  <br><span data-ttu-id="803c5-137">Selezionare un valore nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="803c5-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="803c5-139">Select **Save**.</span></span>

6. <span data-ttu-id="803c5-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="803c5-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="803c5-141">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="803c5-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="803c5-142">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="803c5-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="803c5-143">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="803c5-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="803c5-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="803c5-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="803c5-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="803c5-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="803c5-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="803c5-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="803c5-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="803c5-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="803c5-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="803c5-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="803c5-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="803c5-152">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-152">Follow the steps below.</span></span>

1. <span data-ttu-id="803c5-p108">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="803c5-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="803c5-156">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="803c5-158">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="803c5-158">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="803c5-160">Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="803c5-162">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="803c5-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="803c5-163">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="803c5-164">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="803c5-164">**Record type**</span></span>|<span data-ttu-id="803c5-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="803c5-165">**Host**</span></span>|<span data-ttu-id="803c5-166">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="803c5-166">**Points to**</span></span>|<span data-ttu-id="803c5-167">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="803c5-167">**Priority**</span></span>|<span data-ttu-id="803c5-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="803c5-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="803c5-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="803c5-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="803c5-170">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="803c5-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="803c5-171">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="803c5-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="803c5-172">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="803c5-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="803c5-173">10 </span><span class="sxs-lookup"><span data-stu-id="803c5-173">10</span></span>  <br/> <span data-ttu-id="803c5-174">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="803c5-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="803c5-175">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="803c5-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="803c5-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="803c5-177">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="803c5-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="803c5-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="803c5-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="803c5-179">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-179">Follow the steps below.</span></span>

1. <span data-ttu-id="803c5-p110">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="803c5-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="803c5-183">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="803c5-185">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="803c5-185">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="803c5-187">Scegliere **CNAME (Alias)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="803c5-189">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="803c5-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="803c5-190">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="803c5-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="803c5-191">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="803c5-192">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="803c5-192">**Record type**</span></span>|<span data-ttu-id="803c5-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="803c5-193">**Host**</span></span>|<span data-ttu-id="803c5-194">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="803c5-194">**Points to**</span></span>|<span data-ttu-id="803c5-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="803c5-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="803c5-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="803c5-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="803c5-197">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="803c5-197">autodiscover</span></span>  <br/> |<span data-ttu-id="803c5-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="803c5-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="803c5-199">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="803c5-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="803c5-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="803c5-201">sip</span><span class="sxs-lookup"><span data-stu-id="803c5-201">sip</span></span>  <br/> |<span data-ttu-id="803c5-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="803c5-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="803c5-203">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="803c5-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="803c5-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="803c5-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="803c5-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="803c5-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="803c5-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="803c5-207">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="803c5-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="803c5-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="803c5-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="803c5-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="803c5-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="803c5-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="803c5-211">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="803c5-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="803c5-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="803c5-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="803c5-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="803c5-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="803c5-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="803c5-215">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="803c5-216">Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="803c5-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="803c5-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="803c5-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="803c5-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="803c5-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="803c5-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="803c5-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="803c5-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="803c5-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="803c5-221">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="803c5-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="803c5-222">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="803c5-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="803c5-223">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-223">Follow the steps below.</span></span>

1. <span data-ttu-id="803c5-p112">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="803c5-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="803c5-227">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="803c5-229">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="803c5-229">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="803c5-231">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="803c5-233">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="803c5-234">Scegliere il valore **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="803c5-235">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="803c5-235">**Record type**</span></span>|<span data-ttu-id="803c5-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="803c5-236">**Host**</span></span>|<span data-ttu-id="803c5-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="803c5-237">**TXT Value**</span></span>|<span data-ttu-id="803c5-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="803c5-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="803c5-239">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="803c5-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="803c5-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="803c5-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="803c5-241">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="803c5-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="803c5-242">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="803c5-244">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="803c5-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="803c5-245">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="803c5-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="803c5-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="803c5-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="803c5-247">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="803c5-247">Follow the steps below.</span></span>

1. <span data-ttu-id="803c5-p113">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="803c5-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="803c5-251">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="803c5-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="803c5-253">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="803c5-253">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="803c5-255">Scegliere **SRV** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="803c5-257">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="803c5-257">Create the first SRV record.</span></span>

    <span data-ttu-id="803c5-258">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="803c5-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="803c5-259">Scegliere il **tipo di record** e i valori **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="803c5-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="803c5-260">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="803c5-260">**Record type**</span></span>|<span data-ttu-id="803c5-261">**Nome**</span><span class="sxs-lookup"><span data-stu-id="803c5-261">**Name**</span></span>|<span data-ttu-id="803c5-262">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="803c5-262">**Target**</span></span>|<span data-ttu-id="803c5-263">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="803c5-263">**Protocol**</span></span>|<span data-ttu-id="803c5-264">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="803c5-264">**Service**</span></span>|<span data-ttu-id="803c5-265">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="803c5-265">**Priority**</span></span>|<span data-ttu-id="803c5-266">**Peso**</span><span class="sxs-lookup"><span data-stu-id="803c5-266">**Weight**</span></span>|<span data-ttu-id="803c5-267">**Porta**</span><span class="sxs-lookup"><span data-stu-id="803c5-267">**Port**</span></span>|<span data-ttu-id="803c5-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="803c5-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="803c5-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="803c5-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="803c5-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="803c5-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="803c5-271">_tls</span><span class="sxs-lookup"><span data-stu-id="803c5-271">_tls</span></span>  <br/> |<span data-ttu-id="803c5-272">_sip</span><span class="sxs-lookup"><span data-stu-id="803c5-272">_sip</span></span>  <br/> |<span data-ttu-id="803c5-273">100</span><span class="sxs-lookup"><span data-stu-id="803c5-273">100</span></span>  <br/> |<span data-ttu-id="803c5-274">1 </span><span class="sxs-lookup"><span data-stu-id="803c5-274">1</span></span>  <br/> |<span data-ttu-id="803c5-275">443</span><span class="sxs-lookup"><span data-stu-id="803c5-275">443</span></span>  <br/> |<span data-ttu-id="803c5-276">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="803c5-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="803c5-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="803c5-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="803c5-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="803c5-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="803c5-279">_tcp</span></span>  <br/> |<span data-ttu-id="803c5-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="803c5-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="803c5-281">100</span><span class="sxs-lookup"><span data-stu-id="803c5-281">100</span></span>  <br/> |<span data-ttu-id="803c5-282">1 </span><span class="sxs-lookup"><span data-stu-id="803c5-282">1</span></span>  <br/> |<span data-ttu-id="803c5-283">5061</span><span class="sxs-lookup"><span data-stu-id="803c5-283">5061</span></span>  <br/> |<span data-ttu-id="803c5-284">1 ora</span><span class="sxs-lookup"><span data-stu-id="803c5-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="803c5-286">Ripetere il **passaggio 5** per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="803c5-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="803c5-287">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="803c5-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="803c5-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="803c5-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
