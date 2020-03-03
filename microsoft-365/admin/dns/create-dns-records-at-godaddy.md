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
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349237"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="5ba35-103">Creare record DNS su GoDaddy per Office 365</span><span class="sxs-lookup"><span data-stu-id="5ba35-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="5ba35-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="5ba35-105">Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="5ba35-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="5ba35-106">Dopo aver aggiunto questi record in GoDaddy, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ba35-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="5ba35-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5ba35-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="5ba35-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ba35-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5ba35-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="5ba35-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5ba35-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5ba35-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5ba35-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="5ba35-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="5ba35-117">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-117">Follow the steps below.</span></span>

1. <span data-ttu-id="5ba35-p104">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5ba35-121">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5ba35-123">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-123">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5ba35-125">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="5ba35-126">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ba35-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="5ba35-127">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="5ba35-127">**Record type**</span></span> |<span data-ttu-id="5ba35-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="5ba35-128">**Host**</span></span>|<span data-ttu-id="5ba35-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="5ba35-129">**TXT Value**</span></span>|<span data-ttu-id="5ba35-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ba35-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ba35-131">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="5ba35-131">TXT (Text)</span></span>|@|<span data-ttu-id="5ba35-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5ba35-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="5ba35-133">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="5ba35-133">**Note**: This is an example.</span></span> <span data-ttu-id="5ba35-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ba35-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5ba35-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5ba35-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="5ba35-136">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-136">1 hour</span></span>  <br><span data-ttu-id="5ba35-137">Selezionare un valore nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="5ba35-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-139">Select **Save**.</span></span>

6. <span data-ttu-id="5ba35-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="5ba35-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="5ba35-141">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="5ba35-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="5ba35-142">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="5ba35-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5ba35-143">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="5ba35-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5ba35-144">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5ba35-145">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="5ba35-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="5ba35-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ba35-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5ba35-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="5ba35-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5ba35-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5ba35-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5ba35-152">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-152">Follow the steps below.</span></span>

1. <span data-ttu-id="5ba35-p108">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5ba35-156">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5ba35-158">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-158">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5ba35-160">Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="5ba35-162">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ba35-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="5ba35-163">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="5ba35-164">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="5ba35-164">**Record type**</span></span>|<span data-ttu-id="5ba35-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="5ba35-165">**Host**</span></span>|<span data-ttu-id="5ba35-166">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="5ba35-166">**Points to**</span></span>|<span data-ttu-id="5ba35-167">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="5ba35-167">**Priority**</span></span>|<span data-ttu-id="5ba35-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ba35-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ba35-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="5ba35-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="5ba35-170">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5ba35-171">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ba35-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="5ba35-172">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5ba35-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5ba35-173">10 </span><span class="sxs-lookup"><span data-stu-id="5ba35-173">10</span></span>  <br/> <span data-ttu-id="5ba35-174">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="5ba35-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5ba35-175">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="5ba35-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5ba35-177">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="5ba35-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5ba35-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5ba35-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5ba35-179">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-179">Follow the steps below.</span></span>

1. <span data-ttu-id="5ba35-p110">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5ba35-183">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5ba35-185">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-185">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="5ba35-187">Scegliere **CNAME (Alias)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="5ba35-189">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5ba35-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="5ba35-190">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ba35-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="5ba35-191">Scegliere il valore **TTL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="5ba35-192">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="5ba35-192">**Record type**</span></span>|<span data-ttu-id="5ba35-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="5ba35-193">**Host**</span></span>|<span data-ttu-id="5ba35-194">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="5ba35-194">**Points to**</span></span>|<span data-ttu-id="5ba35-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ba35-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ba35-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5ba35-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5ba35-197">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="5ba35-197">autodiscover</span></span>  <br/> |<span data-ttu-id="5ba35-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="5ba35-199">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5ba35-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="5ba35-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5ba35-201">sip</span><span class="sxs-lookup"><span data-stu-id="5ba35-201">sip</span></span>  <br/> |<span data-ttu-id="5ba35-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5ba35-203">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5ba35-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="5ba35-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5ba35-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5ba35-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5ba35-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5ba35-207">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5ba35-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="5ba35-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5ba35-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5ba35-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5ba35-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5ba35-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="5ba35-211">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5ba35-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="5ba35-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5ba35-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5ba35-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5ba35-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="5ba35-215">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="5ba35-216">Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5ba35-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5ba35-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="5ba35-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5ba35-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5ba35-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ba35-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba35-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5ba35-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5ba35-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5ba35-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ba35-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5ba35-222">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="5ba35-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="5ba35-223">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-223">Follow the steps below.</span></span>

1. <span data-ttu-id="5ba35-p112">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5ba35-227">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5ba35-229">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-229">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5ba35-231">Scegliere **TXT (Text)** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="5ba35-233">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="5ba35-234">Scegliere il valore **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="5ba35-235">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="5ba35-235">**Record type**</span></span>|<span data-ttu-id="5ba35-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="5ba35-236">**Host**</span></span>|<span data-ttu-id="5ba35-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="5ba35-237">**TXT Value**</span></span>|<span data-ttu-id="5ba35-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ba35-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ba35-239">TXT (testo)</span><span class="sxs-lookup"><span data-stu-id="5ba35-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5ba35-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5ba35-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5ba35-241">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5ba35-242">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="5ba35-244">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5ba35-245">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="5ba35-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5ba35-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5ba35-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="5ba35-247">Effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ba35-247">Follow the steps below.</span></span>

1. <span data-ttu-id="5ba35-p113">Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5ba35-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5ba35-251">In **domini**selezionare DNS nel dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5ba35-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5ba35-253">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-253">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5ba35-255">Scegliere **SRV** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="5ba35-257">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="5ba35-257">Create the first SRV record.</span></span>

    <span data-ttu-id="5ba35-258">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ba35-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="5ba35-259">Scegliere il **tipo di record** e i valori **TTL** negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ba35-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="5ba35-260">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="5ba35-260">**Record type**</span></span>|<span data-ttu-id="5ba35-261">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5ba35-261">**Name**</span></span>|<span data-ttu-id="5ba35-262">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="5ba35-262">**Target**</span></span>|<span data-ttu-id="5ba35-263">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="5ba35-263">**Protocol**</span></span>|<span data-ttu-id="5ba35-264">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="5ba35-264">**Service**</span></span>|<span data-ttu-id="5ba35-265">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="5ba35-265">**Priority**</span></span>|<span data-ttu-id="5ba35-266">**Peso**</span><span class="sxs-lookup"><span data-stu-id="5ba35-266">**Weight**</span></span>|<span data-ttu-id="5ba35-267">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5ba35-267">**Port**</span></span>|<span data-ttu-id="5ba35-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5ba35-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5ba35-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="5ba35-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5ba35-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5ba35-271">_tls</span><span class="sxs-lookup"><span data-stu-id="5ba35-271">_tls</span></span>  <br/> |<span data-ttu-id="5ba35-272">_sip</span><span class="sxs-lookup"><span data-stu-id="5ba35-272">_sip</span></span>  <br/> |<span data-ttu-id="5ba35-273">100</span><span class="sxs-lookup"><span data-stu-id="5ba35-273">100</span></span>  <br/> |<span data-ttu-id="5ba35-274">1</span><span class="sxs-lookup"><span data-stu-id="5ba35-274">1</span></span>  <br/> |<span data-ttu-id="5ba35-275">443</span><span class="sxs-lookup"><span data-stu-id="5ba35-275">443</span></span>  <br/> |<span data-ttu-id="5ba35-276">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5ba35-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="5ba35-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5ba35-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5ba35-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="5ba35-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="5ba35-279">_tcp</span></span>  <br/> |<span data-ttu-id="5ba35-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5ba35-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="5ba35-281">100</span><span class="sxs-lookup"><span data-stu-id="5ba35-281">100</span></span>  <br/> |<span data-ttu-id="5ba35-282">1</span><span class="sxs-lookup"><span data-stu-id="5ba35-282">1</span></span>  <br/> |<span data-ttu-id="5ba35-283">5061</span><span class="sxs-lookup"><span data-stu-id="5ba35-283">5061</span></span>  <br/> |<span data-ttu-id="5ba35-284">1 ora</span><span class="sxs-lookup"><span data-stu-id="5ba35-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="5ba35-286">Ripetere il **passaggio 5** per creare l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="5ba35-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="5ba35-287">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ba35-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5ba35-p114">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ba35-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
