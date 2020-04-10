---
title: Creare record DNS in easyDNS per Office 365
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in easyDNS per Office 365.
ms.openlocfilehash: 9d48896de8f841863e25929a46b2f1d2e1b3ced2
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210553"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="924c4-103">Creare record DNS in easyDNS per Office 365</span><span class="sxs-lookup"><span data-stu-id="924c4-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="924c4-104">Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="924c4-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="924c4-105">È necessario aggiungere tutti i seguenti record DNS al sito Web del registrar per instradare la posta a Office 365, utilizzare il dominio per i team e Skype for business e così via.</span><span class="sxs-lookup"><span data-stu-id="924c4-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="924c4-106">Nota: i record SRV non sono attualmente disponibili in tutti i pacchetti di servizi di easyDNS.</span><span class="sxs-lookup"><span data-stu-id="924c4-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="924c4-107">Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV necessari per Office 365 Skype for business.</span><span class="sxs-lookup"><span data-stu-id="924c4-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="924c4-108">Verificare di essere proprietari del dominio con un record TXT</span><span class="sxs-lookup"><span data-stu-id="924c4-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="924c4-109">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="924c4-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="924c4-110">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="924c4-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="924c4-111">Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="924c4-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="924c4-112">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="924c4-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="924c4-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="924c4-113">**Host**</span></span>|<span data-ttu-id="924c4-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="924c4-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="924c4-115">MS = msXXXXXXXX (utilizzare il valore specificato nella pagina Domains dell'interfaccia di amministrazione)</span><span class="sxs-lookup"><span data-stu-id="924c4-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="924c4-116">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924c4-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="924c4-117">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="924c4-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="924c4-118">Attendere alcuni minuti prima di continuare, in modo che il record appena creato sia in grado di propagarsi su Internet e venga rilevato da Office 365.</span><span class="sxs-lookup"><span data-stu-id="924c4-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="924c4-119">Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.</span><span class="sxs-lookup"><span data-stu-id="924c4-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="924c4-120">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="924c4-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="924c4-121">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="924c4-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="924c4-122">Nella pagina **configurazione** , selezionare **Avvia installazione.**</span><span class="sxs-lookup"><span data-stu-id="924c4-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="924c4-123">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="924c4-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="924c4-124">Aggiungere un record MX per instradare la posta elettronica a Office 365</span><span class="sxs-lookup"><span data-stu-id="924c4-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="924c4-125">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="924c4-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="924c4-126">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="924c4-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="924c4-127">Sotto l'intestazione **MX Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="924c4-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="924c4-128">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="924c4-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="924c4-129">**POSTA ELETTRONICA PER L'AREA**</span><span class="sxs-lookup"><span data-stu-id="924c4-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="924c4-130">**SERVER DI POSTA ELETTRONICA**</span><span class="sxs-lookup"><span data-stu-id="924c4-130">**MAIL SERVER**</span></span>|<span data-ttu-id="924c4-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="924c4-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="924c4-132">\<Domain-Key\>. mail.Protection.Outlook.com (ottenere il \<valore della chiave\> di dominio dalla pagina Domains Admin Center)</span><span class="sxs-lookup"><span data-stu-id="924c4-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="924c4-133">0</span><span class="sxs-lookup"><span data-stu-id="924c4-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="924c4-134">Se si desidera salvare gli altri record MX per scopi di backup, copiarli in un punto qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="924c4-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="924c4-135">Prima di procedere, rimuovere tutti gli altri record MX qui.</span><span class="sxs-lookup"><span data-stu-id="924c4-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="924c4-136">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924c4-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="924c4-137">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="924c4-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="924c4-138">Aggiungere i record CNAME necessari</span><span class="sxs-lookup"><span data-stu-id="924c4-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="924c4-139">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="924c4-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="924c4-140">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="924c4-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="924c4-141">Nella sezione **CNAME/alias Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="924c4-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="924c4-142">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="924c4-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="924c4-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="924c4-143">**HOST**</span></span>|<span data-ttu-id="924c4-144">**Indirizzo (deve terminare con un ".")**</span><span class="sxs-lookup"><span data-stu-id="924c4-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="924c4-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="924c4-145">autodiscover</span></span>  <br/> |<span data-ttu-id="924c4-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="924c4-147">sip</span><span class="sxs-lookup"><span data-stu-id="924c4-147">sip</span></span>  <br/> |<span data-ttu-id="924c4-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="924c4-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="924c4-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="924c4-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="924c4-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="924c4-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="924c4-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="924c4-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="924c4-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="924c4-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="924c4-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="924c4-155">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924c4-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="924c4-156">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="924c4-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="924c4-157">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="924c4-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="924c4-158">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="924c4-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="924c4-159">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="924c4-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="924c4-160">Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="924c4-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="924c4-161">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="924c4-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="924c4-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="924c4-162">**Host**</span></span>|<span data-ttu-id="924c4-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="924c4-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="924c4-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="924c4-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="924c4-165">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924c4-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="924c4-166">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="924c4-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="924c4-167">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="924c4-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="924c4-168">Nota: i record SRV non sono attualmente disponibili in easyDNS ' Domain Plus Service Level.</span><span class="sxs-lookup"><span data-stu-id="924c4-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="924c4-169">Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV</span><span class="sxs-lookup"><span data-stu-id="924c4-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="924c4-170">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="924c4-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="924c4-171">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="924c4-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="924c4-172">Nell'intestazione **SRV Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="924c4-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="924c4-173">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="924c4-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="924c4-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="924c4-174">**SERVICE**</span></span>|<span data-ttu-id="924c4-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="924c4-175">**PROTO**</span></span>|<span data-ttu-id="924c4-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="924c4-176">**HOST**</span></span>|<span data-ttu-id="924c4-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="924c4-177">**PRI**</span></span>|<span data-ttu-id="924c4-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="924c4-178">**WGT**</span></span>|<span data-ttu-id="924c4-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="924c4-179">**PORT**</span></span>|<span data-ttu-id="924c4-180">**DESTINAZIONE (deve terminare con un ".")**</span><span class="sxs-lookup"><span data-stu-id="924c4-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="924c4-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="924c4-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="924c4-182">_sip</span><span class="sxs-lookup"><span data-stu-id="924c4-182">_sip</span></span>  <br/> |<span data-ttu-id="924c4-183">TLS</span><span class="sxs-lookup"><span data-stu-id="924c4-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="924c4-184">100</span><span class="sxs-lookup"><span data-stu-id="924c4-184">100</span></span>  <br/> |<span data-ttu-id="924c4-185">1 </span><span class="sxs-lookup"><span data-stu-id="924c4-185">1</span></span>  <br/> |<span data-ttu-id="924c4-186">443</span><span class="sxs-lookup"><span data-stu-id="924c4-186">443</span></span>  <br/> |<span data-ttu-id="924c4-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="924c4-188">1800</span><span class="sxs-lookup"><span data-stu-id="924c4-188">1800</span></span>  <br/> |
    |<span data-ttu-id="924c4-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="924c4-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="924c4-190">TCP</span><span class="sxs-lookup"><span data-stu-id="924c4-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="924c4-191">100</span><span class="sxs-lookup"><span data-stu-id="924c4-191">100</span></span>  <br/> |<span data-ttu-id="924c4-192">1 </span><span class="sxs-lookup"><span data-stu-id="924c4-192">1</span></span>  <br/> |<span data-ttu-id="924c4-193">5061</span><span class="sxs-lookup"><span data-stu-id="924c4-193">5061</span></span>  <br/> |<span data-ttu-id="924c4-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="924c4-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="924c4-195">1800</span><span class="sxs-lookup"><span data-stu-id="924c4-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="924c4-196">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924c4-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="924c4-197">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="924c4-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

