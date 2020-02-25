---
title: Creare record DNS in OVH per Office 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in OVH per Office 365.
ms.openlocfilehash: 87de24fd47ce048cb88a2b7d4bcff97b1c155456
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244769"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="cddc6-103">Creare record DNS in OVH per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="cddc6-104">Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="cddc6-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cddc6-105">Se OVH è il provider di hosting DNS in uso, eseguire i passaggi descritti in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="cddc6-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cddc6-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="cddc6-107">Creare record DNS in OVH per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="cddc6-108">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="cddc6-109">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="cddc6-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="cddc6-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="cddc6-111">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="cddc6-112">Dopo aver aggiunto questi record in OVH, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cddc6-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cddc6-113">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="cddc6-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cddc6-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cddc6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cddc6-117">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="cddc6-117">Add a TXT record for verification</span></span>
<span data-ttu-id="cddc6-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="cddc6-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="cddc6-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cddc6-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cddc6-p104">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="cddc6-126">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cddc6-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="cddc6-128">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="cddc6-130">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="cddc6-132">Seleziona **txt**</span><span class="sxs-lookup"><span data-stu-id="cddc6-132">Select **TXT**</span></span>
    
    ![OVH Seleziona voce TXT](../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="cddc6-134">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cddc6-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="cddc6-135">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cddc6-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="cddc6-136">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="cddc6-136">**Record type**</span></span>|<span data-ttu-id="cddc6-137">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="cddc6-137">**Sub-domain**</span></span>|<span data-ttu-id="cddc6-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cddc6-138">**TTL**</span></span>|<span data-ttu-id="cddc6-139">**Valore**</span><span class="sxs-lookup"><span data-stu-id="cddc6-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cddc6-140">TXT</span><span class="sxs-lookup"><span data-stu-id="cddc6-140">TXT</span></span>  <br/> |<span data-ttu-id="cddc6-141">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="cddc6-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="cddc6-142">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="cddc6-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cddc6-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="cddc6-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="cddc6-p106">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="cddc6-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="cddc6-147">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="cddc6-149">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="cddc6-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cddc6-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="cddc6-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cddc6-151">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="cddc6-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cddc6-152">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="cddc6-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cddc6-153">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="cddc6-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cddc6-154">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cddc6-155">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cddc6-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cddc6-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cddc6-159">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cddc6-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="cddc6-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="cddc6-p108">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="cddc6-164">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cddc6-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="cddc6-166">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="cddc6-168">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="cddc6-170">Selezionare **MX**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="cddc6-172">Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cddc6-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="cddc6-173">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cddc6-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cddc6-174">Per impostazione predefinita, in OVH viene utilizzata la notazione relativa per la destinazione, che aggiunge il nome di dominio alla fine del record di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cddc6-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="cddc6-175">Per usare invece la notazione assoluta, aggiungere un punto al record di destinazione, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cddc6-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="cddc6-176">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="cddc6-176">**Record type**</span></span>|<span data-ttu-id="cddc6-177">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="cddc6-177">**Sub-domain**</span></span>|<span data-ttu-id="cddc6-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cddc6-178">**TTL**</span></span>|<span data-ttu-id="cddc6-179">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="cddc6-179">**Priority**</span></span>|<span data-ttu-id="cddc6-180">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="cddc6-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cddc6-181">MX</span><span class="sxs-lookup"><span data-stu-id="cddc6-181">MX</span></span>  <br/> |<span data-ttu-id="cddc6-182">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="cddc6-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="cddc6-183">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="cddc6-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cddc6-184">10 </span><span class="sxs-lookup"><span data-stu-id="cddc6-184">10</span></span>  <br/> <span data-ttu-id="cddc6-185">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="cddc6-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="cddc6-186">\<chiave-dominio\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cddc6-187">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cddc6-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="cddc6-188">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="cddc6-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Record MX OVH per la posta elettronica](../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="cddc6-190"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="cddc6-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="cddc6-192">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="cddc6-194">Se sono presenti altri record MX, eliminarli tutti nella pagina **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="cddc6-195">Selezionare ogni record e quindi, nella colonna **azioni** , selezionare l'icona Cestino-Can **Delete** .</span><span class="sxs-lookup"><span data-stu-id="cddc6-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="cddc6-197">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cddc6-198">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cddc6-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="cddc6-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="cddc6-p113">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="cddc6-203">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cddc6-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="cddc6-205">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="cddc6-207">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="cddc6-209">Selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="cddc6-211">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="cddc6-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="cddc6-212">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cddc6-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="cddc6-213">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cddc6-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="cddc6-214">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="cddc6-214">**Record type**</span></span>|<span data-ttu-id="cddc6-215">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="cddc6-215">**Sub-domain**</span></span>|<span data-ttu-id="cddc6-216">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="cddc6-216">**Target**</span></span>|<span data-ttu-id="cddc6-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cddc6-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cddc6-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="cddc6-218">CNAME</span></span>  <br/> |<span data-ttu-id="cddc6-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cddc6-219">autodiscover</span></span>  <br/> |<span data-ttu-id="cddc6-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="cddc6-221">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="cddc6-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="cddc6-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="cddc6-222">CNAME</span></span>  <br/> |<span data-ttu-id="cddc6-223">sip</span><span class="sxs-lookup"><span data-stu-id="cddc6-223">sip</span></span>  <br/> |<span data-ttu-id="cddc6-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="cddc6-225">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="cddc6-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="cddc6-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="cddc6-226">CNAME</span></span>  <br/> |<span data-ttu-id="cddc6-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cddc6-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cddc6-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="cddc6-229">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="cddc6-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="cddc6-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="cddc6-230">CNAME</span></span>  <br/> |<span data-ttu-id="cddc6-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cddc6-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cddc6-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="cddc6-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="cddc6-233">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="cddc6-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="cddc6-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="cddc6-234">CNAME</span></span>  <br/> |<span data-ttu-id="cddc6-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cddc6-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cddc6-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="cddc6-237">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="cddc6-237">3600 seconds</span></span>  <br/> |
   
    ![Record CNAME di OVH](../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="cddc6-239"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="cddc6-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="cddc6-241">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="cddc6-242">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="cddc6-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="cddc6-243">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cddc6-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cddc6-244">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="cddc6-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cddc6-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="cddc6-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cddc6-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="cddc6-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cddc6-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="cddc6-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cddc6-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cddc6-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cddc6-249">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="cddc6-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="cddc6-p116">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="cddc6-253">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cddc6-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="cddc6-255">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="cddc6-257">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="cddc6-259">Selezionare **txt**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="cddc6-260">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="cddc6-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="cddc6-261">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="cddc6-261">**Record type**</span></span>|<span data-ttu-id="cddc6-262">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="cddc6-262">**Sub-domain**</span></span>|<span data-ttu-id="cddc6-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cddc6-263">**TTL**</span></span>|<span data-ttu-id="cddc6-264">**Valore TXT**</span><span class="sxs-lookup"><span data-stu-id="cddc6-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cddc6-265">TXT</span><span class="sxs-lookup"><span data-stu-id="cddc6-265">TXT</span></span>  <br/> |<span data-ttu-id="cddc6-266">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="cddc6-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="cddc6-267">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="cddc6-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cddc6-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cddc6-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cddc6-269">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="cddc6-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH aggiungere un record TXT per SPF](../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="cddc6-271"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="cddc6-271">Select **Next**.</span></span>
    
    ![OVH aggiungere un record TXT per SPF e selezionare Avanti](../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="cddc6-273">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cddc6-275">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc6-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cddc6-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="cddc6-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="cddc6-p117">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="cddc6-280">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cddc6-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="cddc6-282">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="cddc6-284">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="cddc6-286">Selezionare **SRV**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="cddc6-288">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="cddc6-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="cddc6-289">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cddc6-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="cddc6-290">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cddc6-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="cddc6-291">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="cddc6-291">**Record type**</span></span>|<span data-ttu-id="cddc6-292">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="cddc6-292">**Sub-domain**</span></span>|<span data-ttu-id="cddc6-293">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="cddc6-293">**Priority**</span></span>|<span data-ttu-id="cddc6-294">**Peso**</span><span class="sxs-lookup"><span data-stu-id="cddc6-294">**Weight**</span></span>|<span data-ttu-id="cddc6-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="cddc6-295">**Port**</span></span>|<span data-ttu-id="cddc6-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cddc6-296">**TTL**</span></span>|<span data-ttu-id="cddc6-297">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="cddc6-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cddc6-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="cddc6-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="cddc6-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="cddc6-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="cddc6-300">100</span><span class="sxs-lookup"><span data-stu-id="cddc6-300">100</span></span>  <br/> |<span data-ttu-id="cddc6-301">1</span><span class="sxs-lookup"><span data-stu-id="cddc6-301">1</span></span>  <br/> |<span data-ttu-id="cddc6-302">443</span><span class="sxs-lookup"><span data-stu-id="cddc6-302">443</span></span>  <br/> |<span data-ttu-id="cddc6-303">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="cddc6-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cddc6-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="cddc6-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="cddc6-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="cddc6-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="cddc6-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cddc6-307">100</span><span class="sxs-lookup"><span data-stu-id="cddc6-307">100</span></span>  <br/> |<span data-ttu-id="cddc6-308">1</span><span class="sxs-lookup"><span data-stu-id="cddc6-308">1</span></span>  <br/> |<span data-ttu-id="cddc6-309">5061</span><span class="sxs-lookup"><span data-stu-id="cddc6-309">5061</span></span>  <br/> |<span data-ttu-id="cddc6-310">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="cddc6-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cddc6-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cddc6-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Record OVH SRV](../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="cddc6-313"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="cddc6-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="cddc6-315">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="cddc6-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="cddc6-p119">Ripetere i passaggi precedenti per creare l'altro record SRV. Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="cddc6-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="cddc6-p120">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cddc6-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
