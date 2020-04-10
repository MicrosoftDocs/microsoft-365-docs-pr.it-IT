---
title: Modificare i server dei nomi per configurare Office 365 con 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Informazioni su come è possibile configurare Office 365 gestito da 21Vianet per gestire i record DNS, quando 1&1 Internet è il provider di hosting DNS.
ms.openlocfilehash: bda6a19ba7bfca20bc1764187f429e13900d8460
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212366"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a><span data-ttu-id="79074-103">Modificare i server dei nomi per configurare Office 365 con 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="79074-103">Change nameservers to set up Office 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="79074-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="79074-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79074-105">Seguire queste istruzioni se si vuole che Office 365 gestisca automaticamente i record DNS di Office 365.</span><span class="sxs-lookup"><span data-stu-id="79074-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="79074-106">Se si preferisce, è possibile [gestire tutti i record DNS di Office 365 a 1&1 IONOS](create-dns-records-at-1-1-internet.md).</span><span class="sxs-lookup"><span data-stu-id="79074-106">(If you prefer, you can [manage all your Office 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="79074-107">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="79074-107">Add a TXT record for verification</span></span>


<span data-ttu-id="79074-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79074-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="79074-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="79074-112">Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="79074-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="79074-113">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS tramite [questo collegamento](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="79074-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="79074-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="79074-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="79074-115">In **My Domains**selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="79074-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="79074-116">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare. Selezionare quindi il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="79074-117">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="79074-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="79074-118">Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="79074-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="79074-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79074-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="79074-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79074-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="79074-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="79074-121">**Type**</span></span> <br/> |<span data-ttu-id="79074-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="79074-122">**Prefix**</span></span> <br/> |<span data-ttu-id="79074-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="79074-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="79074-124">TXT</span><span class="sxs-lookup"><span data-stu-id="79074-124">TXT</span></span>  <br/> |<span data-ttu-id="79074-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="79074-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79074-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="79074-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="79074-127">**Nota**: questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="79074-127">**Note**: This is an example.</span></span> <span data-ttu-id="79074-128">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="79074-128">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="79074-129">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="79074-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="79074-130">Fare clic su **Salva**e quindi su **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="79074-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="79074-131">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="79074-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="79074-132">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="79074-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="79074-133">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="79074-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="79074-134">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="79074-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="79074-135">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="79074-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="79074-136">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="79074-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="79074-137">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="79074-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="79074-138">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="79074-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79074-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79074-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="79074-142">Modificare i record del server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="79074-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="79074-p107">Per completare la configurazione del dominio con Office 365, modificare i record del server dei nomi del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Office 365. Office 365 viene così configurato in modo da aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="79074-p108">Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi di Office 365, questa modifica interessa tutti i servizi attualmente associati al dominio. Ad esempio, dopo questa modifica tutta la posta elettronica inviata al dominio (come roberto@ *nome_dominio*  .com) inizierà a essere recapitata a Office 365.</span><span class="sxs-lookup"><span data-stu-id="79074-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
<span data-ttu-id="79074-p109">Modificare i record NS per consentire a Office 365 di configurare il dominio Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="79074-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="79074-150">Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati.</span><span class="sxs-lookup"><span data-stu-id="79074-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="79074-151">> dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="79074-152">Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="79074-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="79074-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="79074-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="79074-154">In **My Domains**selezionare **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="79074-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="79074-155">Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="79074-156">Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.</span><span class="sxs-lookup"><span data-stu-id="79074-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="79074-157">Nella sezione **Name Server Settings** selezionare **Other name servers**.</span><span class="sxs-lookup"><span data-stu-id="79074-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="79074-158">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="79074-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="79074-159">A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="79074-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="79074-160">Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="79074-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="79074-161">Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="79074-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="79074-162">Se NON sono già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="79074-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="79074-163">Nella seconda casella **Name server 1** digitare o copiare e incollare il valore dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="79074-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="79074-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="79074-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="79074-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Immissione di un valore nella casella Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="79074-167">Nell'elenco a discesa **Additional name servers** scegliere **My secondary name servers**.</span><span class="sxs-lookup"><span data-stu-id="79074-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="79074-169">Nelle caselle **Name server 2, 3 e 4** digitare o copiare e incollare il valore dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="79074-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="79074-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="79074-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="79074-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79074-172">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="79074-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="79074-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79074-174">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="79074-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="79074-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="79074-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79074-176">Select **Save**.</span></span>
    
    ![Selezione di Save nella pagina Impostazioni server dei nomi](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="79074-178">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="79074-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selezionare Salva nella finestra di dialogo Modifica impostazioni DNS.](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="79074-p112">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="79074-182">Se SONO già elencati server dei nomi</span><span class="sxs-lookup"><span data-stu-id="79074-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="79074-p113">Seguire questa procedura  *solo*  se sono presenti server dei nomi diversi dai quattro server dei nomi  *corretti*  . In altre parole, eliminare  *solo*  eventuali server dei nomi  *diversi*  da **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="79074-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="79074-185">Se sono già elencati altri server dei nomi nelle caselle **Name server**, eliminarli uno alla volta selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="79074-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="79074-187">Nelle caselle **Name server 1, 2, 3 e 4** digitare o copiare e incollare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="79074-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="79074-188">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="79074-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="79074-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79074-190">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="79074-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="79074-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79074-192">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="79074-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="79074-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79074-194">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="79074-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="79074-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79074-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Immissione di valori del server dei nomi](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="79074-197">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79074-197">Select **Save**.</span></span>
    
    ![Selezione di Save nella pagina Impostazioni server dei nomi](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="79074-199">Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="79074-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selezionare Salva nella finestra di dialogo Modifica impostazioni DNS.](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="79074-p114">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="79074-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  


