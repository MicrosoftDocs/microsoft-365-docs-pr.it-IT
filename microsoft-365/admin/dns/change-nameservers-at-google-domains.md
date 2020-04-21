---
title: Modificare i server dei nomi per configurare Microsoft con Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Informazioni su come è possibile configurare Microsoft per gestire i record DNS del dominio personalizzato su Google Domains.
ms.openlocfilehash: ac2f98a6ff783917d88a2bd8d28e8242e0ba41a8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629900"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="b0e2c-103">Modificare i server dei nomi per configurare Microsoft con Google Domains</span><span class="sxs-lookup"><span data-stu-id="b0e2c-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="b0e2c-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b0e2c-105">Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b0e2c-106">Se si preferisce, è possibile [gestire tutti i record DNS su Google Domains](create-dns-records-at-google-domains.md).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b0e2c-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="b0e2c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="b0e2c-108">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b0e2c-109">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b0e2c-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b0e2c-112">Per iniziare, passare alla propria pagina dei domini su Google Domains tramite [questo collegamento](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="b0e2c-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="b0e2c-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="b0e2c-114">To do so:</span></span>
    
1. <span data-ttu-id="b0e2c-115">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="b0e2c-116">Immettere le credenziali di accesso e selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="b0e2c-117">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b0e2c-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b0e2c-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b0e2c-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="b0e2c-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b0e2c-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0e2c-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-121">**Name**</span></span> <br/> |<span data-ttu-id="b0e2c-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-122">**Type**</span></span> <br/> |<span data-ttu-id="b0e2c-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-123">**TTL**</span></span> <br/> |<span data-ttu-id="b0e2c-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="b0e2c-125">TXT</span><span class="sxs-lookup"><span data-stu-id="b0e2c-125">TXT</span></span>  <br/> |<span data-ttu-id="b0e2c-126">1H</span><span class="sxs-lookup"><span data-stu-id="b0e2c-126">1H</span></span>  <br/> |<span data-ttu-id="b0e2c-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b0e2c-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="b0e2c-128">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-128">**Note:** This is an example.</span></span> <span data-ttu-id="b0e2c-129">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b0e2c-130">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="b0e2c-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="b0e2c-131">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="b0e2c-132">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b0e2c-133">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b0e2c-134">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b0e2c-135">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="b0e2c-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b0e2c-136">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b0e2c-137">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b0e2c-138">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b0e2c-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b0e2c-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b0e2c-141">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b0e2c-142">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="b0e2c-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b0e2c-143">Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="b0e2c-144">Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b0e2c-145">Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b0e2c-146">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b0e2c-147">Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (come rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="b0e2c-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="b0e2c-148">com) inizierà a essere Microsoft dopo aver apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b0e2c-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="b0e2c-150">> dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi che devono essere elencati sono i seguenti quattro:</span><span class="sxs-lookup"><span data-stu-id="b0e2c-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="b0e2c-p110">Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="b0e2c-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="b0e2c-154">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="b0e2c-155">Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="b0e2c-156">Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b0e2c-157">Nella pagina **Domains**, nella sezione **Name servers**, selezionare **Use custom name servers**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="b0e2c-159">A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e2c-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b0e2c-160">Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b0e2c-161">Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b0e2c-162">Se NON sono già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="b0e2c-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b0e2c-163">Aggiungere il primo server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="b0e2c-164">Nella casella **NAME SERVER** della sezione **Name servers** digitare oppure copiare e incollare il primo valore dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b0e2c-165">**Primo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-165">**First name server**</span></span> <br/> |<span data-ttu-id="b0e2c-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-167">**Secondo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-167">**Second name server**</span></span> <br/> |<span data-ttu-id="b0e2c-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-169">**Terzo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-169">**Third name server**</span></span> <br/> |<span data-ttu-id="b0e2c-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-171">**Quarto server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="b0e2c-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-domini-BP-redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="b0e2c-174">Selezionare il controllo **+ (Aggiungi)** per creare una riga vuota.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="b0e2c-176">Aggiungere gli altri tre record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="b0e2c-177">Nella sezione **Use Custom Name Servers** creare un record usando i valori della riga successiva della tabella e quindi selezionare il controllo **+ (Aggiungi)** per aggiungere un'altra riga.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="b0e2c-178">Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="b0e2c-179">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="b0e2c-181">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b0e2c-182">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b0e2c-183">Se SONO già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="b0e2c-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="b0e2c-184">Se sono elencati altri server dei nomi, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b0e2c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="b0e2c-186">(Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="b0e2c-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="b0e2c-188">Eliminare ciascun valore selezionandolo e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="b0e2c-190">Sempre nella sezione **Name servers**, nelle righe **NAME SERVER** digitare oppure copiare e incollare il valore dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b0e2c-191">**Primo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-191">**First name server**</span></span> <br/> |<span data-ttu-id="b0e2c-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-193">**Secondo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-193">**Second name server**</span></span> <br/> |<span data-ttu-id="b0e2c-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-195">**Terzo server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-195">**Third name server**</span></span> <br/> |<span data-ttu-id="b0e2c-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b0e2c-197">**Quarto server dei nomi**</span><span class="sxs-lookup"><span data-stu-id="b0e2c-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="b0e2c-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b0e2c-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-domini-BP-redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="b0e2c-200">Selezionare il controllo **+ (Aggiungi)** per creare una riga vuota.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="b0e2c-202">Aggiungere gli altri due record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="b0e2c-203">Nella sezione **Use Custom Name Servers** creare un record usando i valori della riga successiva della tabella e quindi selezionare il controllo **+ (Aggiungi)** per aggiungere un'altra riga.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="b0e2c-204">Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="b0e2c-205">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="b0e2c-207">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b0e2c-208">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e2c-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
