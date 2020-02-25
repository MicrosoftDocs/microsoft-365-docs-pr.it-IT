---
title: Creare record DNS su Google Domains per Office 365
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Lync e altri servizi in Google domains per Office 365.
ms.openlocfilehash: c59a3d63797f20b0d3a42647eb68d7699ed63450
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244817"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="2b225-103">Creare record DNS su Google Domains per Office 365</span><span class="sxs-lookup"><span data-stu-id="2b225-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="2b225-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="2b225-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2b225-105">Se il proprio provider di hosting DNS è Google Domains, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.</span><span class="sxs-lookup"><span data-stu-id="2b225-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="2b225-106">Dopo aver aggiunto questi record in Google Domains, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b225-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="2b225-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="2b225-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b225-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b225-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2b225-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="2b225-111">Add a TXT record for verification</span></span>
<span data-ttu-id="2b225-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2b225-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2b225-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="2b225-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b225-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="2b225-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2b225-p104">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="2b225-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="2b225-120">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="2b225-121">Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="2b225-122">Nella pagina **My Domains** trovare il dominio che si desidera utilizzare con Office 365 e selezionare il collegamento **Gestisci** accanto a esso.</span><span class="sxs-lookup"><span data-stu-id="2b225-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="2b225-123">Nel riquadro di spostamento a sinistra, selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2b225-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="2b225-124">Nelle caselle del nuovo record nella sezione \* \* Custom Resource Records \* \* digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2b225-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2b225-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="2b225-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="2b225-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2b225-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2b225-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2b225-127">**Name**</span></span> <br/> |<span data-ttu-id="2b225-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b225-128">**Type**</span></span> <br/> |<span data-ttu-id="2b225-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2b225-129">**TTL**</span></span> <br/> |<span data-ttu-id="2b225-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="2b225-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="2b225-131">TXT</span><span class="sxs-lookup"><span data-stu-id="2b225-131">TXT</span></span>  <br/> |<span data-ttu-id="2b225-132">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-132">1H</span></span>  <br/> |<span data-ttu-id="2b225-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2b225-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2b225-134">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="2b225-134">**Note:** This is an example.</span></span> <span data-ttu-id="2b225-135">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b225-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="2b225-136">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2b225-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="2b225-137">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="2b225-138">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="2b225-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2b225-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="2b225-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="2b225-140">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="2b225-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2b225-141">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="2b225-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2b225-142">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="2b225-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="2b225-143">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="2b225-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="2b225-144">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="2b225-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b225-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b225-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="2b225-148">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="2b225-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="2b225-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2b225-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2b225-p108">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="2b225-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="2b225-153">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="2b225-154">Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="2b225-155">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2b225-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2b225-p109">Con un account di posta elettronica di G Suite, prima di tutto è necessario eliminare i record MX associati all'account. I record MX di G Suite impediscono l'aggiunta di altri record, tra cui quelli necessari per Office 365. Si noti che l'eliminazione di record di G Suite non comporta l'eliminazione dell'account di G Suite. Per eliminare i record MX di G Suite, seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2b225-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="2b225-160">Nell'area **G Suite** della sezione **Synthetic Records** selezionare **Delete**.</span><span class="sxs-lookup"><span data-stu-id="2b225-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="2b225-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="2b225-161">(You may have to scroll down.)</span></span>
    
    ![Selezionare Elimina nella sezione sintetico Records](../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="2b225-163">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2b225-163">Select **Delete**.</span></span>
    
    ![Seleziona Elimina](../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="2b225-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2b225-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2b225-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="2b225-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="2b225-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2b225-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2b225-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2b225-168">**Name**</span></span>|<span data-ttu-id="2b225-169">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b225-169">**Type**</span></span>|<span data-ttu-id="2b225-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2b225-170">**TTL**</span></span>|<span data-ttu-id="2b225-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="2b225-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2b225-172">MX</span><span class="sxs-lookup"><span data-stu-id="2b225-172">MX</span></span>  <br/> |<span data-ttu-id="2b225-173">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-173">1H</span></span>  <br/> |<span data-ttu-id="2b225-174">0  *\<chiave-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="2b225-175">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="2b225-p110">**0** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  </span><span class="sxs-lookup"><span data-stu-id="2b225-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="2b225-178">**Nota:** Ottenere la \<propria *chiave* \> di dominio dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b225-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="2b225-179">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="2b225-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="2b225-180">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b225-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="2b225-182">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-182">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="2b225-184">Se sono presenti altri record MX personalizzati, rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="2b225-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="2b225-185">Selezionare **modifica** nella riga MX record.</span><span class="sxs-lookup"><span data-stu-id="2b225-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Selezionare modifica nella riga MX record](../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="2b225-187">Per ognuno degli altri record MX personalizzati, selezionare la voce nella casella **dati** e quindi premere **Canc** sulla tastiera per eliminare il record.</span><span class="sxs-lookup"><span data-stu-id="2b225-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="2b225-188">Continuare fino a eliminare la voce **Data** per tutti gli altri record MX.</span><span class="sxs-lookup"><span data-stu-id="2b225-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="2b225-190">Quando è stata eliminata la voce di **dati** per ognuno degli altri record MX, selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2b225-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Seleziona Salva](../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="2b225-192">Aggiungere i cinque record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="2b225-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="2b225-193">Per iniziare, passare alla propria [pagina Google Domains] (https://domains.google.com/registrar) e accedere.</span><span class="sxs-lookup"><span data-stu-id="2b225-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="2b225-194">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2b225-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="2b225-195">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b225-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="2b225-196">Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2b225-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="2b225-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="2b225-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="2b225-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2b225-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2b225-199">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2b225-199">**Name**</span></span>|<span data-ttu-id="2b225-200">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b225-200">**Type**</span></span>|<span data-ttu-id="2b225-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2b225-201">**TTL**</span></span>|<span data-ttu-id="2b225-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="2b225-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2b225-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2b225-203">autodiscover</span></span>  <br/> |<span data-ttu-id="2b225-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b225-204">CNAME</span></span>  <br/> |<span data-ttu-id="2b225-205">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-205">1H</span></span>  <br/> |<span data-ttu-id="2b225-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="2b225-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b225-208">sip</span><span class="sxs-lookup"><span data-stu-id="2b225-208">sip</span></span>  <br/> |<span data-ttu-id="2b225-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b225-209">CNAME</span></span>  <br/> |<span data-ttu-id="2b225-210">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-210">1H</span></span>  <br/> |<span data-ttu-id="2b225-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b225-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b225-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2b225-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2b225-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b225-214">CNAME</span></span>  <br/> |<span data-ttu-id="2b225-215">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-215">1H</span></span>  <br/> |<span data-ttu-id="2b225-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b225-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b225-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2b225-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2b225-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b225-219">CNAME</span></span>  <br/> |<span data-ttu-id="2b225-220">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-220">1H</span></span>  <br/> |<span data-ttu-id="2b225-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="2b225-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="2b225-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b225-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2b225-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2b225-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b225-224">CNAME</span></span>  <br/> |<span data-ttu-id="2b225-225">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-225">1H</span></span>  <br/> |<span data-ttu-id="2b225-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="2b225-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="2b225-229">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-229">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="2b225-231">Aggiungere gli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b225-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="2b225-232">Nella sezione **Custom Resource Records** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="2b225-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="2b225-233">Ripetere questa procedura fino a creare tutti i record CNAME necessari.</span><span class="sxs-lookup"><span data-stu-id="2b225-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2b225-234">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="2b225-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b225-235">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="2b225-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2b225-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="2b225-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2b225-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b225-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="2b225-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="2b225-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="2b225-239">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="2b225-239">Need examples?</span></span> <span data-ttu-id="2b225-240">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="2b225-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="2b225-241">Per convalidare il record SPF, è possibile usare uno di questi [strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="2b225-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="2b225-p113">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="2b225-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="2b225-245">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="2b225-246">Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="2b225-247">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2b225-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="2b225-248">Nella sezione **record di risorse personalizzate** fare clic su **modifica**nella riga TXT record.</span><span class="sxs-lookup"><span data-stu-id="2b225-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2b225-p114">Google Domains archivia i record TXT come un set che potrebbe contenere più record. Quando si ha almeno un altro record TXT, ad esempio il record TXT usato per verificare il dominio, è necessario aggiungere nuovi record TXT a tale set di record. Quando si tenta immettere altri record TXT come voci separate, viene generato il messaggio di errore **Duplicate record**.</span><span class="sxs-lookup"><span data-stu-id="2b225-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selezionare modifica nella riga TXT record](../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="2b225-253">Selezionare il controllo **(+)** .</span><span class="sxs-lookup"><span data-stu-id="2b225-253">Select the **(+)** control.</span></span> 
    
    ![Selezionare il controllo più](../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="2b225-255">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2b225-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="2b225-256">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2b225-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2b225-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="2b225-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="2b225-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2b225-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="2b225-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="2b225-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitare o incollare i valori nella sezione Custom Resource Records](../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="2b225-261">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b225-261">Select **Save**.</span></span>
    
    ![Seleziona Salva](../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2b225-263">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="2b225-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="2b225-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2b225-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2b225-p115">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="2b225-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="2b225-268">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="2b225-269">Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="2b225-270">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2b225-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="2b225-271">Aggiungere il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="2b225-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="2b225-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2b225-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2b225-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="2b225-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="2b225-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="2b225-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="2b225-275">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2b225-275">**Name**</span></span>|<span data-ttu-id="2b225-276">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b225-276">**Type**</span></span>|<span data-ttu-id="2b225-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2b225-277">**TTL**</span></span>|<span data-ttu-id="2b225-278">**Dati**</span><span class="sxs-lookup"><span data-stu-id="2b225-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2b225-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="2b225-279">_sip._tls</span></span>|<span data-ttu-id="2b225-280">SRV</span><span class="sxs-lookup"><span data-stu-id="2b225-280">SRV</span></span>|<span data-ttu-id="2b225-281">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-281">1H</span></span>|<span data-ttu-id="2b225-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="2b225-283">**Questo valore deve terminare con un punto (.).** **Nota:** È consigliabile copiare e incollare questa voce, in modo che tutti gli spazi siano corretti.</span><span class="sxs-lookup"><span data-stu-id="2b225-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="2b225-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="2b225-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="2b225-285">SRV</span><span class="sxs-lookup"><span data-stu-id="2b225-285">SRV</span></span>|<span data-ttu-id="2b225-286">1H</span><span class="sxs-lookup"><span data-stu-id="2b225-286">1H</span></span>|<span data-ttu-id="2b225-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b225-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="2b225-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b225-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="2b225-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="2b225-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="2b225-291">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2b225-291">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi](../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="2b225-293">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="2b225-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="2b225-294">Nella sezione **Custom Resource Records** creare un record usando i valori della seconda riga della tabella e quindi fare di nuovo clic su **Aggiungi** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="2b225-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2b225-p118">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b225-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
