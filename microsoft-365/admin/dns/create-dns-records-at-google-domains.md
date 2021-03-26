---
title: Creare record DNS su Google Domains per Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Lync e altri servizi su Google Domains per Microsoft.
ms.openlocfilehash: 48e23c180533bab2a73e06dd4a45a9c4016680ae
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221956"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="0c425-103">Creare record DNS su Google Domains per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c425-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="0c425-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0c425-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0c425-105">Se il proprio provider di hosting DNS è Google Domains, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.</span><span class="sxs-lookup"><span data-stu-id="0c425-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="0c425-106">Dopo aver aggiunto questi record in Google Domains, il domino sarà configurato per l'uso con i servizi di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c425-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="0c425-107">Solitamente, affinché le modifiche DNS diventino effettive, sono necessari circa 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="0c425-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0c425-108">A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo.</span><span class="sxs-lookup"><span data-stu-id="0c425-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0c425-109">In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c425-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0c425-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="0c425-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0c425-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0c425-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0c425-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="0c425-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c425-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="0c425-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0c425-p104">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="0c425-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="0c425-119">Scegliere **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="0c425-120">Immettere le credenziali di accesso e poi selezionare di nuovo **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="0c425-121">Nella pagina **My domains** individuare il dominio che si vuole usare con Microsoft e selezionare il collegamento **GESTISCI** accanto.</span><span class="sxs-lookup"><span data-stu-id="0c425-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="0c425-122">Nel riquadro di spostamento sinistro scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0c425-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="0c425-123">Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0c425-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0c425-124">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="0c425-125">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0c425-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c425-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c425-126">**Name**</span></span> <br/> |<span data-ttu-id="0c425-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="0c425-127">**Type**</span></span> <br/> |<span data-ttu-id="0c425-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c425-128">**TTL**</span></span> <br/> |<span data-ttu-id="0c425-129">**Dati**</span><span class="sxs-lookup"><span data-stu-id="0c425-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0c425-130">TXT</span><span class="sxs-lookup"><span data-stu-id="0c425-130">TXT</span></span>  <br/> |<span data-ttu-id="0c425-131">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-131">1H</span></span>  <br/> |<span data-ttu-id="0c425-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0c425-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0c425-133">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="0c425-133">**Note:** This is an example.</span></span> <span data-ttu-id="0c425-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0c425-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0c425-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="0c425-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="0c425-136">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="0c425-137">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="0c425-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0c425-138">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="0c425-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0c425-139">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="0c425-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0c425-140">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="0c425-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0c425-141">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="0c425-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0c425-142">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="0c425-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0c425-143">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="0c425-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c425-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c425-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0c425-147">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c425-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0c425-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0c425-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0c425-p108">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="0c425-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="0c425-152">Scegliere **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="0c425-153">Immettere le credenziali di accesso e poi selezionare di nuovo **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="0c425-154">Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="0c425-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c425-155">Con un account di posta elettronica di G Suite, prima di tutto è necessario eliminare i record MX associati all'account.</span><span class="sxs-lookup"><span data-stu-id="0c425-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="0c425-156">I record MX di G Suite impediscono l'aggiunta di altri record, tra cui quelli necessari per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c425-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="0c425-157">Si noti che l'eliminazione di record di G Suite non comporta l'eliminazione dell'account di G Suite.</span><span class="sxs-lookup"><span data-stu-id="0c425-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="0c425-158">Per eliminare i record MX di G Suite, seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0c425-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="0c425-159">Nella sezione **Synthetic records**, nell’area **G Suite**, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0c425-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="0c425-160">Potrebbe essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-160">(You may have to scroll down.)</span></span>
    
    ![Selezionare Elimina nella sezione Synthetic records](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="0c425-162">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0c425-162">Select **Delete**.</span></span>
    
    ![Selezionare Elimina](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="0c425-164">Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0c425-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0c425-165">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="0c425-166">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0c425-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0c425-167">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c425-167">**Name**</span></span>|<span data-ttu-id="0c425-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="0c425-168">**Type**</span></span>|<span data-ttu-id="0c425-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c425-169">**TTL**</span></span>|<span data-ttu-id="0c425-170">**Dati**</span><span class="sxs-lookup"><span data-stu-id="0c425-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0c425-171">MX</span><span class="sxs-lookup"><span data-stu-id="0c425-171">MX</span></span>  <br/> |<span data-ttu-id="0c425-172">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-172">1H</span></span>  <br/> |<span data-ttu-id="0c425-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0c425-174">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0c425-p110">**0** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="0c425-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="0c425-177">**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c425-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="0c425-178">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="0c425-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="0c425-179">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="0c425-179">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Digitare o copiare e incollare i valori nella sezione Custom resource records](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="0c425-181">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-181">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="0c425-183">Se sono presenti altri record MX personalizzati, rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="0c425-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="0c425-184">Fare clic su **Modifica** nella riga del record MX.</span><span class="sxs-lookup"><span data-stu-id="0c425-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Selezionare Modifica nella riga del record MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="0c425-186">Per ognuno degli altri record MX personalizzati, selezionare la voce nella casella **Dati** e premere il tasto **Elimina** sulla tastiera per eliminare il record.</span><span class="sxs-lookup"><span data-stu-id="0c425-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="0c425-187">Continuare fino a eliminare la voce **Data** per tutti gli altri record MX.</span><span class="sxs-lookup"><span data-stu-id="0c425-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="0c425-189">Dopo avere eliminato la voce **Dati** per ognuno degli altri record MX, selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0c425-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Seleziona Salva.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0c425-191">Aggiungere i cinque record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c425-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="0c425-192">Per iniziare, passare alla propria [pagina Google Domains] (https://domains.google.com/registrar) ed effettuare l’accesso.</span><span class="sxs-lookup"><span data-stu-id="0c425-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="0c425-193">Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="0c425-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0c425-194">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="0c425-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="0c425-195">Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0c425-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="0c425-196">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="0c425-197">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0c425-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0c425-198">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c425-198">**Name**</span></span>|<span data-ttu-id="0c425-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="0c425-199">**Type**</span></span>|<span data-ttu-id="0c425-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c425-200">**TTL**</span></span>|<span data-ttu-id="0c425-201">**Dati**</span><span class="sxs-lookup"><span data-stu-id="0c425-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c425-202">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="0c425-202">autodiscover</span></span>  <br/> |<span data-ttu-id="0c425-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c425-203">CNAME</span></span>  <br/> |<span data-ttu-id="0c425-204">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-204">1H</span></span>  <br/> |<span data-ttu-id="0c425-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0c425-206">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0c425-207">sip</span><span class="sxs-lookup"><span data-stu-id="0c425-207">sip</span></span>  <br/> |<span data-ttu-id="0c425-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c425-208">CNAME</span></span>  <br/> |<span data-ttu-id="0c425-209">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-209">1H</span></span>  <br/> |<span data-ttu-id="0c425-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0c425-211">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0c425-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0c425-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0c425-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c425-213">CNAME</span></span>  <br/> |<span data-ttu-id="0c425-214">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-214">1H</span></span>  <br/> |<span data-ttu-id="0c425-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0c425-216">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0c425-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0c425-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0c425-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c425-218">CNAME</span></span>  <br/> |<span data-ttu-id="0c425-219">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-219">1H</span></span>  <br/> |<span data-ttu-id="0c425-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0c425-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0c425-221">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0c425-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0c425-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0c425-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c425-223">CNAME</span></span>  <br/> |<span data-ttu-id="0c425-224">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-224">1H</span></span>  <br/> |<span data-ttu-id="0c425-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0c425-226">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitare o copiare e incollare i valori nella sezione Custom resource records](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="0c425-228">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-228">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="0c425-230">Aggiungere gli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="0c425-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="0c425-231">Nella sezione **Custom resource records** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **Aggiungi** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="0c425-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="0c425-232">Ripetere questa procedura fino a creare tutti e sei i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="0c425-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0c425-233">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="0c425-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c425-234">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="0c425-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0c425-235">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0c425-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0c425-236">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c425-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0c425-237">Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="0c425-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="0c425-238">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="0c425-238">Need examples?</span></span> <span data-ttu-id="0c425-239">Consultare [Record Domain Name System (DNS) esterni per Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="0c425-239">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="0c425-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="0c425-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="0c425-p113">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="0c425-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="0c425-244">Scegliere **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="0c425-245">Immettere le credenziali di accesso e poi selezionare di nuovo **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="0c425-246">Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="0c425-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0c425-247">Nella riga del record TXT nella sezione **Custom resource records** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0c425-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c425-p114">Google Domains archivia i record TXT come un set che potrebbe contenere più record. Quando si ha almeno un altro record TXT, ad esempio il record TXT usato per verificare il dominio, è necessario aggiungere nuovi record TXT a tale set di record. Quando si tenta immettere altri record TXT come voci separate, viene generato il messaggio di errore **Duplicate record**.</span><span class="sxs-lookup"><span data-stu-id="0c425-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selezionare Modifica nella riga del record TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="0c425-252">Selezionare il controllo **(+)**.</span><span class="sxs-lookup"><span data-stu-id="0c425-252">Select the **(+)** control.</span></span> 
    
    ![Fare clic sul tasto più.](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="0c425-254">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0c425-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0c425-255">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0c425-256">**Dati**</span><span class="sxs-lookup"><span data-stu-id="0c425-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="0c425-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0c425-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="0c425-258">È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="0c425-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitare o copiare e incollare i valori nella sezione Custom resource records](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="0c425-260">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c425-260">Select **Save**.</span></span>
    
    ![Seleziona Salva.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0c425-262">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c425-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0c425-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0c425-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0c425-p115">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="0c425-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="0c425-267">Scegliere **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="0c425-268">Immettere le credenziali di accesso e poi selezionare di nuovo **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="0c425-269">Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="0c425-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="0c425-270">Aggiungere il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="0c425-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="0c425-271">Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0c425-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0c425-272">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0c425-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="0c425-273">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0c425-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0c425-274">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c425-274">**Name**</span></span>|<span data-ttu-id="0c425-275">**Type**</span><span class="sxs-lookup"><span data-stu-id="0c425-275">**Type**</span></span>|<span data-ttu-id="0c425-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c425-276">**TTL**</span></span>|<span data-ttu-id="0c425-277">**Dati**</span><span class="sxs-lookup"><span data-stu-id="0c425-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c425-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="0c425-278">_sip._tls</span></span>|<span data-ttu-id="0c425-279">SRV</span><span class="sxs-lookup"><span data-stu-id="0c425-279">SRV</span></span>|<span data-ttu-id="0c425-280">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-280">1H</span></span>|<span data-ttu-id="0c425-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="0c425-282">**Questo valore DEVE terminare con un punto (.)** **Nota:** È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="0c425-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="0c425-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="0c425-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0c425-284">SRV</span><span class="sxs-lookup"><span data-stu-id="0c425-284">SRV</span></span>|<span data-ttu-id="0c425-285">1H</span><span class="sxs-lookup"><span data-stu-id="0c425-285">1H</span></span>|<span data-ttu-id="0c425-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0c425-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="0c425-287">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="0c425-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="0c425-288">È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="0c425-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitare o copiare e incollare i valori nella sezione Custom resource records](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="0c425-290">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c425-290">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="0c425-292">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="0c425-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="0c425-293">Nella sezione **Custom resource records** creare un record usando i valori della seconda riga della tabella e quindi scegliere di nuovo **Aggiungi** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="0c425-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0c425-p118">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c425-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
