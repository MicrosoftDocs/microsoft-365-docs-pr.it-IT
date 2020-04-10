---
title: Creare record DNS in OVH per Office 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in OVH per Office 365.
ms.openlocfilehash: 3ba4e61c875f74a0a6cf76c8b7cd82ea88e0221b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211111"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="1e69b-103">Creare record DNS in OVH per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="1e69b-104">Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="1e69b-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1e69b-105">Se OVH è il provider di hosting DNS in uso, eseguire i passaggi descritti in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="1e69b-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1e69b-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="1e69b-107">Creare record DNS in OVH per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="1e69b-108">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="1e69b-109">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="1e69b-110">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1e69b-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="1e69b-111">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="1e69b-112">Dopo aver aggiunto questi record in OVH, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e69b-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="1e69b-113">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e69b-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1e69b-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1e69b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1e69b-117">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="1e69b-117">Add a TXT record for verification</span></span>
<span data-ttu-id="1e69b-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="1e69b-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="1e69b-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e69b-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1e69b-p104">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="1e69b-126">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="1e69b-128">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="1e69b-130">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="1e69b-132">Seleziona **txt**</span><span class="sxs-lookup"><span data-stu-id="1e69b-132">Select **TXT**</span></span>
    
    ![OVH Seleziona voce TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="1e69b-134">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e69b-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="1e69b-135">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1e69b-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="1e69b-136">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1e69b-136">**Record type**</span></span>|<span data-ttu-id="1e69b-137">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1e69b-137">**Sub-domain**</span></span>|<span data-ttu-id="1e69b-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1e69b-138">**TTL**</span></span>|<span data-ttu-id="1e69b-139">**Valore**</span><span class="sxs-lookup"><span data-stu-id="1e69b-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1e69b-140">TXT</span><span class="sxs-lookup"><span data-stu-id="1e69b-140">TXT</span></span>  <br/> |<span data-ttu-id="1e69b-141">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="1e69b-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="1e69b-142">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="1e69b-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1e69b-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="1e69b-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="1e69b-p106">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="1e69b-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="1e69b-147">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="1e69b-149">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="1e69b-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1e69b-150">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="1e69b-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1e69b-151">Quando Office 365 trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="1e69b-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1e69b-152">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="1e69b-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="1e69b-153">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1e69b-154">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1e69b-155">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1e69b-p107">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1e69b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1e69b-159">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1e69b-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="1e69b-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="1e69b-p108">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="1e69b-164">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="1e69b-166">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="1e69b-168">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="1e69b-170">Selezionare **MX**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="1e69b-172">Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e69b-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="1e69b-173">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1e69b-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1e69b-174">Per impostazione predefinita, in OVH viene utilizzata la notazione relativa per la destinazione, che aggiunge il nome di dominio alla fine del record di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e69b-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="1e69b-175">Per usare invece la notazione assoluta, aggiungere un punto al record di destinazione, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e69b-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="1e69b-176">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1e69b-176">**Record type**</span></span>|<span data-ttu-id="1e69b-177">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1e69b-177">**Sub-domain**</span></span>|<span data-ttu-id="1e69b-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1e69b-178">**TTL**</span></span>|<span data-ttu-id="1e69b-179">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1e69b-179">**Priority**</span></span>|<span data-ttu-id="1e69b-180">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="1e69b-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1e69b-181">MX</span><span class="sxs-lookup"><span data-stu-id="1e69b-181">MX</span></span>  <br/> |<span data-ttu-id="1e69b-182">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="1e69b-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="1e69b-183">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="1e69b-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1e69b-184">10 </span><span class="sxs-lookup"><span data-stu-id="1e69b-184">10</span></span>  <br/> <span data-ttu-id="1e69b-185">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e69b-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="1e69b-186">\<chiave-dominio\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1e69b-187">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e69b-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="1e69b-188">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1e69b-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Record MX OVH per la posta elettronica](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="1e69b-190">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="1e69b-192">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="1e69b-194">Se sono presenti altri record MX, eliminarli tutti nella pagina **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="1e69b-195">Selezionare ogni record e quindi, nella colonna **azioni** , selezionare l'icona Cestino-Can **Delete** .</span><span class="sxs-lookup"><span data-stu-id="1e69b-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="1e69b-197">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1e69b-198">Aggiungere i record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1e69b-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="1e69b-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="1e69b-p113">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="1e69b-203">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="1e69b-205">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="1e69b-207">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="1e69b-209">Selezionare **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="1e69b-211">Creare il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1e69b-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="1e69b-212">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e69b-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="1e69b-213">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1e69b-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="1e69b-214">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1e69b-214">**Record type**</span></span>|<span data-ttu-id="1e69b-215">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1e69b-215">**Sub-domain**</span></span>|<span data-ttu-id="1e69b-216">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="1e69b-216">**Target**</span></span>|<span data-ttu-id="1e69b-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1e69b-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1e69b-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="1e69b-218">CNAME</span></span>  <br/> |<span data-ttu-id="1e69b-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1e69b-219">autodiscover</span></span>  <br/> |<span data-ttu-id="1e69b-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="1e69b-221">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="1e69b-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="1e69b-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="1e69b-222">CNAME</span></span>  <br/> |<span data-ttu-id="1e69b-223">sip</span><span class="sxs-lookup"><span data-stu-id="1e69b-223">sip</span></span>  <br/> |<span data-ttu-id="1e69b-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="1e69b-225">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="1e69b-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="1e69b-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="1e69b-226">CNAME</span></span>  <br/> |<span data-ttu-id="1e69b-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1e69b-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1e69b-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="1e69b-229">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="1e69b-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="1e69b-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="1e69b-230">CNAME</span></span>  <br/> |<span data-ttu-id="1e69b-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1e69b-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1e69b-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1e69b-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="1e69b-233">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="1e69b-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="1e69b-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="1e69b-234">CNAME</span></span>  <br/> |<span data-ttu-id="1e69b-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1e69b-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1e69b-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="1e69b-237">3600 secondi</span><span class="sxs-lookup"><span data-stu-id="1e69b-237">3600 seconds</span></span>  <br/> |
   
    ![Record CNAME di OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="1e69b-239">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="1e69b-241">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="1e69b-242">Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1e69b-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="1e69b-243">Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1e69b-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1e69b-244">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1e69b-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1e69b-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="1e69b-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e69b-246">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="1e69b-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1e69b-247">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1e69b-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1e69b-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e69b-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1e69b-249">Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="1e69b-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="1e69b-p116">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="1e69b-253">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="1e69b-255">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="1e69b-257">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="1e69b-259">Selezionare **txt**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="1e69b-260">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="1e69b-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="1e69b-261">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1e69b-261">**Record type**</span></span>|<span data-ttu-id="1e69b-262">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1e69b-262">**Sub-domain**</span></span>|<span data-ttu-id="1e69b-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1e69b-263">**TTL**</span></span>|<span data-ttu-id="1e69b-264">**Valore TXT**</span><span class="sxs-lookup"><span data-stu-id="1e69b-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1e69b-265">TXT</span><span class="sxs-lookup"><span data-stu-id="1e69b-265">TXT</span></span>  <br/> |<span data-ttu-id="1e69b-266">(lasciare vuoto)</span><span class="sxs-lookup"><span data-stu-id="1e69b-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="1e69b-267">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="1e69b-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1e69b-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1e69b-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1e69b-269">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1e69b-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH aggiungere un record TXT per SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="1e69b-271">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-271">Select **Next**.</span></span>
    
    ![OVH aggiungere un record TXT per SPF e selezionare Avanti](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="1e69b-273">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1e69b-275">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="1e69b-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1e69b-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="1e69b-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="1e69b-p117">Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="1e69b-280">In **domini**selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1e69b-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="1e69b-282">Selezionare la **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="1e69b-284">Selezionare **Aggiungi una voce**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="1e69b-286">Selezionare **SRV**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="1e69b-288">Creare il primo record SRV.</span><span class="sxs-lookup"><span data-stu-id="1e69b-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="1e69b-289">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e69b-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="1e69b-290">Per assegnare un valore TTL, scegliere **personalizzato** dall'elenco a discesa e quindi digitare il valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1e69b-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="1e69b-291">**Tipo di record**</span><span class="sxs-lookup"><span data-stu-id="1e69b-291">**Record type**</span></span>|<span data-ttu-id="1e69b-292">**Sottodominio**</span><span class="sxs-lookup"><span data-stu-id="1e69b-292">**Sub-domain**</span></span>|<span data-ttu-id="1e69b-293">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1e69b-293">**Priority**</span></span>|<span data-ttu-id="1e69b-294">**Peso**</span><span class="sxs-lookup"><span data-stu-id="1e69b-294">**Weight**</span></span>|<span data-ttu-id="1e69b-295">**Porta**</span><span class="sxs-lookup"><span data-stu-id="1e69b-295">**Port**</span></span>|<span data-ttu-id="1e69b-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1e69b-296">**TTL**</span></span>|<span data-ttu-id="1e69b-297">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="1e69b-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1e69b-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="1e69b-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="1e69b-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="1e69b-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="1e69b-300">100</span><span class="sxs-lookup"><span data-stu-id="1e69b-300">100</span></span>  <br/> |<span data-ttu-id="1e69b-301">1 </span><span class="sxs-lookup"><span data-stu-id="1e69b-301">1</span></span>  <br/> |<span data-ttu-id="1e69b-302">443</span><span class="sxs-lookup"><span data-stu-id="1e69b-302">443</span></span>  <br/> |<span data-ttu-id="1e69b-303">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="1e69b-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1e69b-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="1e69b-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="1e69b-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="1e69b-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="1e69b-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1e69b-307">100</span><span class="sxs-lookup"><span data-stu-id="1e69b-307">100</span></span>  <br/> |<span data-ttu-id="1e69b-308">1 </span><span class="sxs-lookup"><span data-stu-id="1e69b-308">1</span></span>  <br/> |<span data-ttu-id="1e69b-309">5061</span><span class="sxs-lookup"><span data-stu-id="1e69b-309">5061</span></span>  <br/> |<span data-ttu-id="1e69b-310">3600 (secondi)</span><span class="sxs-lookup"><span data-stu-id="1e69b-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1e69b-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1e69b-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Record OVH SRV](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="1e69b-313">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="1e69b-315">Selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="1e69b-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="1e69b-p119">Ripetere i passaggi precedenti per creare l'altro record SRV. Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.</span><span class="sxs-lookup"><span data-stu-id="1e69b-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="1e69b-p120">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1e69b-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
