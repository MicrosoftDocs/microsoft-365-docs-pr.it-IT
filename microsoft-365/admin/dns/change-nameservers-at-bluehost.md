---
title: Modificare i server dei nomi per configurare Office 365 con Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Informazioni su come è possibile configurare Office 365 per gestire i record DNS in Bluehost. '
ms.openlocfilehash: 27d73071a08477b0adc372d8a88db2c805fecacf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241132"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="91c24-103">Modificare i server dei nomi per configurare Office 365 con Bluehost</span><span class="sxs-lookup"><span data-stu-id="91c24-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="91c24-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="91c24-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="91c24-p101">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365. Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 su Bluehost](create-dns-records-at-bluehost.md).</span><span class="sxs-lookup"><span data-stu-id="91c24-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="91c24-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="91c24-107">Add a TXT record for verification</span></span>

<span data-ttu-id="91c24-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="91c24-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91c24-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="91c24-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="91c24-112">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="91c24-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="91c24-113">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="91c24-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="91c24-114">Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="91c24-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="91c24-115">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="91c24-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="91c24-116">Nell'area **Domain_name** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="91c24-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="91c24-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="91c24-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91c24-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="91c24-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91c24-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="91c24-119">**Host Record**</span></span> <br/> |<span data-ttu-id="91c24-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91c24-120">**TTL**</span></span> <br/> |<span data-ttu-id="91c24-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="91c24-121">**Type**</span></span> <br/> |<span data-ttu-id="91c24-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="91c24-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="91c24-123">14400</span><span class="sxs-lookup"><span data-stu-id="91c24-123">14400</span></span>  <br/> |<span data-ttu-id="91c24-124">TXT</span><span class="sxs-lookup"><span data-stu-id="91c24-124">TXT</span></span>  <br/> |<span data-ttu-id="91c24-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="91c24-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="91c24-126">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="91c24-126">**Note:** This is an example.</span></span> <span data-ttu-id="91c24-127">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="91c24-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="91c24-128">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="91c24-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="91c24-129">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="91c24-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="91c24-130">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="91c24-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="91c24-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="91c24-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="91c24-132">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="91c24-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="91c24-133">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="91c24-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="91c24-134">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="91c24-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="91c24-135">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="91c24-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="91c24-136">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="91c24-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91c24-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="91c24-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="91c24-140">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="91c24-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="91c24-p107">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="91c24-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="91c24-p108">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio. Ad esempio, dopo questa modifica tutta la posta elettronica inviata al dominio (come roberto@ *nome_dominio*  .com) inizierà a essere recapitata a Office 365.</span><span class="sxs-lookup"><span data-stu-id="91c24-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="91c24-146">Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati.</span><span class="sxs-lookup"><span data-stu-id="91c24-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="91c24-147">> dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="91c24-148">Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="91c24-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="91c24-149">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="91c24-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="91c24-150">Nell'area **Domain_name** della pagina **Domains** selezionare la casella di controllo per il dominio, quindi selezionare Server dei **nomi**.</span><span class="sxs-lookup"><span data-stu-id="91c24-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="91c24-152">Nell'area **Domain_name** selezionare **Usa server dei nomi personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="91c24-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Miglioramenti relativi al percorso animazione](../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="91c24-154">A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="91c24-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="91c24-155">Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="91c24-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="91c24-156">Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="91c24-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="91c24-157">Se NON sono già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="91c24-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="91c24-158">Nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="91c24-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="91c24-159">**Prima riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-159">**First empty row**</span></span> <br/> |<span data-ttu-id="91c24-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="91c24-161">**Seconda riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="91c24-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="91c24-164">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="91c24-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="91c24-166">Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota.</span><span class="sxs-lookup"><span data-stu-id="91c24-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="91c24-167">**Terza riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="91c24-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="91c24-169">**Quarta riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="91c24-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="91c24-171">Per aggiungere il quarto record del server dei nomi, selezionare di nuovo **Aggiungi riga** e creare un record usando i valori dell'ultima riga della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="91c24-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="91c24-172">Selezionare **Salva impostazioni server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="91c24-172">Select **save nameserver settings**.</span></span>
    
    ![Teta](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="91c24-p111">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="91c24-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="91c24-176">Se SONO già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="91c24-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="91c24-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="91c24-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="91c24-178">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="91c24-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="91c24-179">Se sono già presenti server dei nomi, eliminarli selezionando ogni server e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="91c24-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="91c24-181">Sempre nella sezione **Use Custom Nameservers**, digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="91c24-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="91c24-182">**Prima riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-182">**First empty row**</span></span> <br/> |<span data-ttu-id="91c24-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="91c24-184">**Seconda riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="91c24-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="91c24-187">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="91c24-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="91c24-189">Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota.</span><span class="sxs-lookup"><span data-stu-id="91c24-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="91c24-190">**Terza riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="91c24-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="91c24-192">**Quarta riga vuota**</span><span class="sxs-lookup"><span data-stu-id="91c24-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="91c24-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="91c24-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="91c24-195">Per aggiungere il quarto record del server dei nomi, selezionare di nuovo **Aggiungi riga** e creare un record usando i valori dell'ultima riga della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="91c24-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="91c24-196">Selezionare **Salva impostazioni server dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="91c24-196">Select **save nameserver settings**.</span></span>
    
    ![Teta](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="91c24-p113">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="91c24-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
