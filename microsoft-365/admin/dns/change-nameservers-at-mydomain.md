---
title: Modificare i server dei nomi per configurare Microsoft con il dominio
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Informazioni su come è possibile configurare Microsoft per gestire i record DNS del dominio personalizzato in dominio.
ms.openlocfilehash: 8f4a72aa0ece24ed09c4d036239a2a13c196be6c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629792"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="10043-103">Modificare i server dei nomi per configurare Microsoft con il dominio</span><span class="sxs-lookup"><span data-stu-id="10043-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="10043-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="10043-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="10043-105">Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="10043-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="10043-106">Se si preferisce, è possibile [gestire tutti i record Microsoft DNS nel dominio](create-dns-records-at-mydomain.md).</span><span class="sxs-lookup"><span data-stu-id="10043-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10043-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="10043-107">Add a TXT record for verification</span></span>

<span data-ttu-id="10043-108">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="10043-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="10043-109">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="10043-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10043-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="10043-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="10043-p104">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="10043-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="10043-114">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="10043-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="10043-115">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="10043-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="10043-116">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10043-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="10043-117">Nell'elenco a discesa **Modifica** selezionare **Record TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="10043-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="10043-118">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="10043-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="10043-119">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="10043-119">**Content**</span></span> <br/> |
|<span data-ttu-id="10043-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10043-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10043-121">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="10043-121">**Note**: This is an example.</span></span> <span data-ttu-id="10043-122">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="10043-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="10043-123">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="10043-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="10043-124">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="10043-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="10043-125">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="10043-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10043-126">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft 365 e richiedere a Microsoft 365 di cercare il record.</span><span class="sxs-lookup"><span data-stu-id="10043-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="10043-127">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="10043-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10043-128">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="10043-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="10043-129">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="10043-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="10043-130">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="10043-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="10043-131">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="10043-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="10043-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="10043-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="10043-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="10043-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="10043-134">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10043-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="10043-135">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="10043-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="10043-136">Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10043-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="10043-137">Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="10043-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="10043-138">Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="10043-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="10043-139">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="10043-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="10043-140">Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (come rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="10043-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="10043-141">com) inizierà a essere Microsoft dopo aver apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="10043-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="10043-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="10043-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="10043-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="10043-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="10043-p110">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="10043-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="10043-146">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="10043-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="10043-147">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="10043-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="10043-148">Nella riga **Panoramica** selezionare Server dei **nomi**.</span><span class="sxs-lookup"><span data-stu-id="10043-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Dominio-BP-redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="10043-150">Nella sezione **Update Name Servers** selezionare **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="10043-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Dominio-BP-redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="10043-152">A seconda del fatto che siano già presenti o meno i server dei nomi elencati nella pagina visualizzata, continuare con una delle due procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="10043-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="10043-153">Se i server dei nomi corretti SONO già elencati</span><span class="sxs-lookup"><span data-stu-id="10043-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="10043-154">Se i server dei nomi corretti sono già elencati, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="10043-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Dominio-BP-redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="10043-156">Se i server dei nomi corretti NON sono ancora elencati</span><span class="sxs-lookup"><span data-stu-id="10043-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="10043-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="10043-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="10043-158">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="10043-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="10043-159">Eliminare i server dei nomi esistenti selezionando le singole voci nel campo **Nameserver**, quindi premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="10043-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dominio-BP-redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="10043-161">Per aggiungere due nuove righe dei server dei nomi, fare clic su **Aggiungi** due volte.</span><span class="sxs-lookup"><span data-stu-id="10043-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Dominio-BP-redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="10043-163">Nelle caselle dei record digitare oppure copiare e incollare i valori del server dei nomi dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="10043-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="10043-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="10043-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="10043-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10043-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10043-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="10043-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="10043-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10043-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10043-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="10043-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="10043-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10043-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10043-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="10043-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="10043-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10043-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Dominio-BP-redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="10043-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="10043-173">Select **Save**.</span></span>
    
    ![Dominio-BP-redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="10043-175">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="10043-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="10043-176">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="10043-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
