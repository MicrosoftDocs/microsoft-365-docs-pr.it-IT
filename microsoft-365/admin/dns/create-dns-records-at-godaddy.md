---
title: Creare record DNS su GoDaddy per Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in GoDaddy per Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241276"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="d969a-103">Creare record DNS su GoDaddy per Office 365</span><span class="sxs-lookup"><span data-stu-id="d969a-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="d969a-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d969a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="d969a-105">Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="d969a-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="d969a-106">Dopo aver aggiunto questi record in GoDaddy, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d969a-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="d969a-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d969a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="d969a-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d969a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d969a-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="d969a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d969a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d969a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d969a-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="d969a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d969a-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="d969a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="d969a-117">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-117">Follow the steps below.</span></span>

1. <span data-ttu-id="d969a-p104">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d969a-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="d969a-121">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d969a-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="d969a-123">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d969a-123">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="d969a-125">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="d969a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d969a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="d969a-127">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d969a-127">**Record type**</span></span> |<span data-ttu-id="d969a-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="d969a-128">**Host**</span></span>|<span data-ttu-id="d969a-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="d969a-129">**TXT Value**</span></span>|<span data-ttu-id="d969a-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d969a-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d969a-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="d969a-131">TXT (Text)</span></span>|@|<span data-ttu-id="d969a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d969a-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="d969a-133">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="d969a-133">**Note**: This is an example.</span></span> <span data-ttu-id="d969a-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d969a-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="d969a-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="d969a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="d969a-136">1 hour</span><span class="sxs-lookup"><span data-stu-id="d969a-136">1 hour</span></span>  <br><span data-ttu-id="d969a-137">Selezionare un valore nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="d969a-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d969a-139">Select **Save**.</span></span>

6. <span data-ttu-id="d969a-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="d969a-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="d969a-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="d969a-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="d969a-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="d969a-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d969a-143">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="d969a-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d969a-144">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="d969a-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d969a-145">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="d969a-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="d969a-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="d969a-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="d969a-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d969a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="d969a-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="d969a-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="d969a-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d969a-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d969a-152">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-152">Follow the steps below.</span></span>

1. <span data-ttu-id="d969a-p108">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d969a-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="d969a-156">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d969a-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="d969a-158">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d969a-158">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="d969a-160">Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="d969a-162">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d969a-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="d969a-163">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="d969a-164">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d969a-164">**Record type**</span></span>|<span data-ttu-id="d969a-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="d969a-165">**Host**</span></span>|<span data-ttu-id="d969a-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="d969a-166">**Points to**</span></span>|<span data-ttu-id="d969a-167">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="d969a-167">**Priority**</span></span>|<span data-ttu-id="d969a-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d969a-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d969a-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="d969a-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="d969a-170">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d969a-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d969a-171">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d969a-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="d969a-172">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="d969a-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d969a-173">10 </span><span class="sxs-lookup"><span data-stu-id="d969a-173">10</span></span>  <br/> <span data-ttu-id="d969a-174">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="d969a-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="d969a-175">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="d969a-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d969a-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="d969a-177">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="d969a-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="d969a-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d969a-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d969a-179">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-179">Follow the steps below.</span></span>

1. <span data-ttu-id="d969a-p110">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d969a-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="d969a-183">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d969a-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="d969a-185">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d969a-185">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="d969a-187">Scegliere **CNAME (Alias)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="d969a-189">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="d969a-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="d969a-190">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d969a-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="d969a-191">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="d969a-192">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d969a-192">**Record type**</span></span>|<span data-ttu-id="d969a-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="d969a-193">**Host**</span></span>|<span data-ttu-id="d969a-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="d969a-194">**Points to**</span></span>|<span data-ttu-id="d969a-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d969a-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d969a-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="d969a-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d969a-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d969a-197">autodiscover</span></span>  <br/> |<span data-ttu-id="d969a-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d969a-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="d969a-199">1 hour</span><span class="sxs-lookup"><span data-stu-id="d969a-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="d969a-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="d969a-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d969a-201">sip</span><span class="sxs-lookup"><span data-stu-id="d969a-201">sip</span></span>  <br/> |<span data-ttu-id="d969a-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d969a-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d969a-203">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="d969a-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="d969a-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d969a-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d969a-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d969a-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d969a-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d969a-207">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="d969a-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="d969a-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d969a-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d969a-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d969a-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d969a-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="d969a-211">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="d969a-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="d969a-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d969a-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d969a-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d969a-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d969a-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="d969a-215">1 hour</span><span class="sxs-lookup"><span data-stu-id="d969a-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="d969a-216">Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="d969a-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d969a-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="d969a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d969a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d969a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d969a-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="d969a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d969a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="d969a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d969a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="d969a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d969a-222">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="d969a-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="d969a-223">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-223">Follow the steps below.</span></span>

1. <span data-ttu-id="d969a-p112">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d969a-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="d969a-227">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d969a-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="d969a-229">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d969a-229">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="d969a-231">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="d969a-233">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="d969a-234">Scegliere il valore **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="d969a-235">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d969a-235">**Record type**</span></span>|<span data-ttu-id="d969a-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="d969a-236">**Host**</span></span>|<span data-ttu-id="d969a-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="d969a-237">**TXT Value**</span></span>|<span data-ttu-id="d969a-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d969a-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d969a-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="d969a-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="d969a-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d969a-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d969a-241">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="d969a-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d969a-242">1 hour</span><span class="sxs-lookup"><span data-stu-id="d969a-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="d969a-244">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d969a-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="d969a-245">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="d969a-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="d969a-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d969a-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="d969a-247">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d969a-247">Follow the steps below.</span></span>

1. <span data-ttu-id="d969a-p113">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d969a-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="d969a-251">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d969a-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="d969a-253">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d969a-253">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="d969a-255">Scegliere **SRV** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="d969a-257">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="d969a-257">Create the first SRV record.</span></span>

    <span data-ttu-id="d969a-258">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d969a-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="d969a-259">Scegliere il **tipo di record** e i valori **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="d969a-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="d969a-260">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="d969a-260">**Record type**</span></span>|<span data-ttu-id="d969a-261">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d969a-261">**Name**</span></span>|<span data-ttu-id="d969a-262">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="d969a-262">**Target**</span></span>|<span data-ttu-id="d969a-263">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="d969a-263">**Protocol**</span></span>|<span data-ttu-id="d969a-264">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="d969a-264">**Service**</span></span>|<span data-ttu-id="d969a-265">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="d969a-265">**Priority**</span></span>|<span data-ttu-id="d969a-266">**Peso**</span><span class="sxs-lookup"><span data-stu-id="d969a-266">**Weight**</span></span>|<span data-ttu-id="d969a-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="d969a-267">**Port**</span></span>|<span data-ttu-id="d969a-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d969a-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d969a-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="d969a-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="d969a-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d969a-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d969a-271">_tls</span><span class="sxs-lookup"><span data-stu-id="d969a-271">_tls</span></span>  <br/> |<span data-ttu-id="d969a-272">_sip</span><span class="sxs-lookup"><span data-stu-id="d969a-272">_sip</span></span>  <br/> |<span data-ttu-id="d969a-273">100</span><span class="sxs-lookup"><span data-stu-id="d969a-273">100</span></span>  <br/> |<span data-ttu-id="d969a-274">1</span><span class="sxs-lookup"><span data-stu-id="d969a-274">1</span></span>  <br/> |<span data-ttu-id="d969a-275">443</span><span class="sxs-lookup"><span data-stu-id="d969a-275">443</span></span>  <br/> |<span data-ttu-id="d969a-276">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="d969a-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="d969a-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="d969a-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d969a-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="d969a-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="d969a-279">_tcp</span></span>  <br/> |<span data-ttu-id="d969a-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d969a-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="d969a-281">100</span><span class="sxs-lookup"><span data-stu-id="d969a-281">100</span></span>  <br/> |<span data-ttu-id="d969a-282">1</span><span class="sxs-lookup"><span data-stu-id="d969a-282">1</span></span>  <br/> |<span data-ttu-id="d969a-283">5061</span><span class="sxs-lookup"><span data-stu-id="d969a-283">5061</span></span>  <br/> |<span data-ttu-id="d969a-284">1 ora</span><span class="sxs-lookup"><span data-stu-id="d969a-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="d969a-286">Ripetere il **passaggio 5** per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="d969a-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="d969a-287">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d969a-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d969a-p114">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d969a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
