---
title: Modificare i server dei nomi per configurare Office 365 con Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Informazioni su come è possibile configurare Office 365 per gestire i record DNS su Amazon Web Services (AWS). '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212354"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="d0e46-103">Modificare i server dei nomi per configurare Office 365 con Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="d0e46-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="d0e46-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d0e46-p101">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365. Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 su AWS](create-dns-records-at-aws.md).</span><span class="sxs-lookup"><span data-stu-id="d0e46-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d0e46-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="d0e46-107">Add a TXT record for verification</span></span>

<span data-ttu-id="d0e46-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0e46-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d0e46-p104">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0e46-114">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0e46-115">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d0e46-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0e46-116">Selezionare **Crea set di record**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d0e46-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0e46-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0e46-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d0e46-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d0e46-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0e46-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0e46-121">**Name**</span></span> <br/> |<span data-ttu-id="d0e46-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0e46-122">**Type**</span></span> <br/> |<span data-ttu-id="d0e46-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d0e46-123">**Alias**</span></span> <br/> |<span data-ttu-id="d0e46-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="d0e46-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="d0e46-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="d0e46-125">**Value**</span></span> <br/> |<span data-ttu-id="d0e46-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="d0e46-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="d0e46-127">(Lasciare vuoto questo campo)</span><span class="sxs-lookup"><span data-stu-id="d0e46-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="d0e46-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="d0e46-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="d0e46-129">No</span><span class="sxs-lookup"><span data-stu-id="d0e46-129">No</span></span>  <br/> |<span data-ttu-id="d0e46-130">300</span><span class="sxs-lookup"><span data-stu-id="d0e46-130">300</span></span>  <br/> |<span data-ttu-id="d0e46-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d0e46-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="d0e46-132">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="d0e46-132">**Note:** This is an example.</span></span> <span data-ttu-id="d0e46-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0e46-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="d0e46-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="d0e46-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="d0e46-135">Semplice</span><span class="sxs-lookup"><span data-stu-id="d0e46-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="d0e46-136">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="d0e46-137">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="d0e46-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d0e46-138">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="d0e46-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d0e46-139">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="d0e46-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d0e46-140">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="d0e46-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d0e46-141">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="d0e46-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d0e46-142">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d0e46-143">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d0e46-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0e46-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d0e46-147">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="d0e46-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="d0e46-p108">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d0e46-p109">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio. Ad esempio, dopo questa modifica tutta la posta elettronica inviata al dominio (come roberto@ *nome_dominio*  .com) inizierà a essere recapitata a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="d0e46-153">Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati.</span><span class="sxs-lookup"><span data-stu-id="d0e46-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="d0e46-154">> dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d0e46-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="d0e46-155">Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="d0e46-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d0e46-156">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0e46-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0e46-157">Nella pagina **risorse** selezionare **aree ospitate**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0e46-158">Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d0e46-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0e46-159">Selezionare il set di record **Nameserver**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="d0e46-161">Nel set di record **NS - Name server** della casella **Valore** eliminare tutti i server dei nomi selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="d0e46-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="d0e46-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="d0e46-163">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="d0e46-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="d0e46-165">Nell'area **TTL (secondi):** selezionare **1h** (1 ora).</span><span class="sxs-lookup"><span data-stu-id="d0e46-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Selezionare 1H per un'ora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="d0e46-167">Sempre nel set di record **NS - Name server** della casella **Valore** digitare oppure copiare e incollare il valore **Prima riga** dalla tabella seguente, quindi premere **INVIO** e digitare oppure copiare e incollare il valore **Seconda riga**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0e46-168">Ogni valore per il nome dei server  *deve*  trovarsi su una riga separata nella casella **Valore**, come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d0e46-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d0e46-169">**Prima riga**</span><span class="sxs-lookup"><span data-stu-id="d0e46-169">**First line**</span></span> <br/> |<span data-ttu-id="d0e46-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d0e46-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d0e46-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d0e46-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d0e46-172">**Seconda riga**</span><span class="sxs-lookup"><span data-stu-id="d0e46-172">**Second line**</span></span> <br/> |<span data-ttu-id="d0e46-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d0e46-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d0e46-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d0e46-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d0e46-175">**Terza riga**</span><span class="sxs-lookup"><span data-stu-id="d0e46-175">**Third line**</span></span> <br/> |<span data-ttu-id="d0e46-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d0e46-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d0e46-177">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0e46-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="d0e46-178">**Quarta riga**</span><span class="sxs-lookup"><span data-stu-id="d0e46-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="d0e46-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="d0e46-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="d0e46-180">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0e46-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Digitare o incollare il valore della prima riga nella casella valore.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="d0e46-182">Selezionare **Salva set di record**.</span><span class="sxs-lookup"><span data-stu-id="d0e46-182">Select **Save Record Set**.</span></span>
    
    ![Selezionare Salva set di record](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="d0e46-p113">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="d0e46-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
