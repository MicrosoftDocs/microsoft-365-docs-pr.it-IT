---
title: Modificare i server dei nomi per configurare Office 365 con MyDomain
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
description: Informazioni su come è possibile configurare Office 365 per gestire i record DNS del dominio personalizzato in dominio.
ms.openlocfilehash: f88f0528caf2229441fd3e5364b53864b923099f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212046"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="4c840-103">Modificare i server dei nomi per configurare Office 365 con MyDomain</span><span class="sxs-lookup"><span data-stu-id="4c840-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="4c840-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4c840-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="4c840-p101">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365. Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 su MyDomain](create-dns-records-at-mydomain.md).</span><span class="sxs-lookup"><span data-stu-id="4c840-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4c840-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="4c840-107">Add a TXT record for verification</span></span>

<span data-ttu-id="4c840-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="4c840-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c840-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="4c840-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4c840-p104">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4c840-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4c840-114">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="4c840-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4c840-115">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="4c840-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4c840-116">Nella riga **Panoramica** scegliere **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4c840-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="4c840-117">Nell'elenco a discesa **Modifica** selezionare **Record TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="4c840-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="4c840-118">Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4c840-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="4c840-119">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="4c840-119">**Content**</span></span> <br/> |
|<span data-ttu-id="4c840-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4c840-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4c840-121">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="4c840-121">**Note**: This is an example.</span></span> <span data-ttu-id="4c840-122">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c840-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="4c840-123">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="4c840-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="4c840-124">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4c840-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="4c840-125">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="4c840-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4c840-126">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="4c840-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4c840-127">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="4c840-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4c840-128">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="4c840-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4c840-129">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="4c840-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4c840-130">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="4c840-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4c840-131">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="4c840-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4c840-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4c840-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4c840-135">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="4c840-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4c840-p107">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="4c840-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4c840-139">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="4c840-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4c840-140">Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (come rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="4c840-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="4c840-141">com) inizierà a essere disponibile in Office 365 dopo aver apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="4c840-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4c840-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="4c840-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="4c840-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="4c840-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="4c840-p110">Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4c840-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4c840-146">Nella sezione **Preferiti** selezionare **Dominio centrale**.</span><span class="sxs-lookup"><span data-stu-id="4c840-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4c840-147">In **Dominio** selezionare il nome del dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="4c840-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4c840-148">Nella riga **Panoramica** selezionare Server dei **nomi**.</span><span class="sxs-lookup"><span data-stu-id="4c840-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Dominio-BP-redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="4c840-150">Nella sezione **Update Name Servers** selezionare **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="4c840-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Dominio-BP-redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="4c840-152">A seconda del fatto che siano già presenti o meno i server dei nomi elencati nella pagina visualizzata, continuare con una delle due procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="4c840-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="4c840-153">Se i server dei nomi corretti SONO già elencati</span><span class="sxs-lookup"><span data-stu-id="4c840-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="4c840-154">Se i server dei nomi corretti sono già elencati, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4c840-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Dominio-BP-redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="4c840-156">Se i server dei nomi corretti NON sono ancora elencati</span><span class="sxs-lookup"><span data-stu-id="4c840-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="4c840-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="4c840-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="4c840-158">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="4c840-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="4c840-159">Eliminare i server dei nomi esistenti selezionando le singole voci nel campo **Nameserver**, quindi premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="4c840-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dominio-BP-redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="4c840-161">Per aggiungere due nuove righe dei server dei nomi, fare clic su **Aggiungi** due volte.</span><span class="sxs-lookup"><span data-stu-id="4c840-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Dominio-BP-redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="4c840-163">Nelle caselle dei record digitare oppure copiare e incollare i valori del server dei nomi dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4c840-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4c840-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="4c840-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="4c840-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4c840-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4c840-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="4c840-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="4c840-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4c840-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4c840-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="4c840-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="4c840-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4c840-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4c840-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="4c840-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="4c840-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4c840-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Dominio-BP-redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="4c840-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c840-173">Select **Save**.</span></span>
    
    ![Dominio-BP-redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="4c840-p112">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="4c840-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
