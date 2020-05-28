---
title: Creare record DNS in easyDNS per Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in easyDNS per Microsoft.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400233"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="d4fa5-103">Creare record DNS in easyDNS per Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4fa5-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="d4fa5-104">Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d4fa5-105">È necessario aggiungere tutti i seguenti record DNS al sito Web del registrar per instradare la posta a Microsoft, utilizzare il dominio per i team e Skype for business e così via.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="d4fa5-106">Nota: i record SRV non sono attualmente disponibili in tutti i pacchetti di servizi di easyDNS.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="d4fa5-107">Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV necessari per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="d4fa5-108">Verificare di essere proprietari del dominio con un record TXT</span><span class="sxs-lookup"><span data-stu-id="d4fa5-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="d4fa5-109">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="d4fa5-110">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="d4fa5-111">Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="d4fa5-112">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4fa5-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="d4fa5-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-113">**Host**</span></span>|<span data-ttu-id="d4fa5-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="d4fa5-115">MS = msXXXXXXXX (utilizzare il valore specificato nella pagina Domains dell'interfaccia di amministrazione)</span><span class="sxs-lookup"><span data-stu-id="d4fa5-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="d4fa5-116">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="d4fa5-117">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="d4fa5-118">Attendere alcuni minuti prima di continuare, in modo che il record appena creato sia in grado di propagarsi su Internet e venga rilevato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="d4fa5-119">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="d4fa5-120">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="d4fa5-121">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="d4fa5-122">Nella pagina **configurazione** , selezionare **Avvia installazione.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="d4fa5-123">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="d4fa5-124">Aggiungere un record MX per instradare la posta elettronica a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4fa5-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="d4fa5-125">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="d4fa5-126">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="d4fa5-127">Sotto l'intestazione **MX Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="d4fa5-128">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4fa5-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="d4fa5-129">**POSTA ELETTRONICA PER L'AREA**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="d4fa5-130">**SERVER DI POSTA ELETTRONICA**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-130">**MAIL SERVER**</span></span>|<span data-ttu-id="d4fa5-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d4fa5-132">\<domain-key\>. mail.protection.outlook.com (ottenere il \<domain-key\> valore dalla pagina Domains dell'interfaccia di amministrazione)</span><span class="sxs-lookup"><span data-stu-id="d4fa5-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="d4fa5-133">0</span><span class="sxs-lookup"><span data-stu-id="d4fa5-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="d4fa5-134">Se si desidera salvare gli altri record MX per scopi di backup, copiarli in un punto qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="d4fa5-135">Prima di procedere, rimuovere tutti gli altri record MX qui.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="d4fa5-136">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="d4fa5-137">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="d4fa5-138">Aggiungere i record CNAME necessari</span><span class="sxs-lookup"><span data-stu-id="d4fa5-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="d4fa5-139">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="d4fa5-140">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="d4fa5-141">Nella sezione **CNAME/alias Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="d4fa5-142">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4fa5-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="d4fa5-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-143">**HOST**</span></span>|<span data-ttu-id="d4fa5-144">**Indirizzo (deve terminare con un ".")**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d4fa5-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d4fa5-145">autodiscover</span></span>  <br/> |<span data-ttu-id="d4fa5-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="d4fa5-147">sip</span><span class="sxs-lookup"><span data-stu-id="d4fa5-147">sip</span></span>  <br/> |<span data-ttu-id="d4fa5-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="d4fa5-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d4fa5-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d4fa5-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="d4fa5-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d4fa5-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d4fa5-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="d4fa5-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d4fa5-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d4fa5-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="d4fa5-155">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="d4fa5-156">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d4fa5-157">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="d4fa5-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="d4fa5-158">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="d4fa5-159">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="d4fa5-160">Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="d4fa5-161">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4fa5-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="d4fa5-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-162">**Host**</span></span>|<span data-ttu-id="d4fa5-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="d4fa5-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d4fa5-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="d4fa5-165">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="d4fa5-166">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d4fa5-167">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4fa5-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="d4fa5-168">Nota: i record SRV non sono attualmente disponibili in easyDNS ' Domain Plus Service Level.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="d4fa5-169">Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV</span><span class="sxs-lookup"><span data-stu-id="d4fa5-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="d4fa5-170">Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="d4fa5-171">Nell'intestazione **tutti i domini** selezionare **DNS.**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="d4fa5-172">Nell'intestazione **SRV Records** selezionare il pulsante modifica (icona della chiave inglese).</span><span class="sxs-lookup"><span data-stu-id="d4fa5-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="d4fa5-173">Inserire nei campi di testo i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4fa5-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="d4fa5-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-174">**SERVICE**</span></span>|<span data-ttu-id="d4fa5-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-175">**PROTO**</span></span>|<span data-ttu-id="d4fa5-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-176">**HOST**</span></span>|<span data-ttu-id="d4fa5-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-177">**PRI**</span></span>|<span data-ttu-id="d4fa5-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-178">**WGT**</span></span>|<span data-ttu-id="d4fa5-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-179">**PORT**</span></span>|<span data-ttu-id="d4fa5-180">**DESTINAZIONE (deve terminare con un ".")**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="d4fa5-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d4fa5-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d4fa5-182">_sip</span><span class="sxs-lookup"><span data-stu-id="d4fa5-182">_sip</span></span>  <br/> |<span data-ttu-id="d4fa5-183">TLS</span><span class="sxs-lookup"><span data-stu-id="d4fa5-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="d4fa5-184">100</span><span class="sxs-lookup"><span data-stu-id="d4fa5-184">100</span></span>  <br/> |<span data-ttu-id="d4fa5-185">1 </span><span class="sxs-lookup"><span data-stu-id="d4fa5-185">1</span></span>  <br/> |<span data-ttu-id="d4fa5-186">443</span><span class="sxs-lookup"><span data-stu-id="d4fa5-186">443</span></span>  <br/> |<span data-ttu-id="d4fa5-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="d4fa5-188">1800</span><span class="sxs-lookup"><span data-stu-id="d4fa5-188">1800</span></span>  <br/> |
    |<span data-ttu-id="d4fa5-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d4fa5-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="d4fa5-190">TCP</span><span class="sxs-lookup"><span data-stu-id="d4fa5-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="d4fa5-191">100</span><span class="sxs-lookup"><span data-stu-id="d4fa5-191">100</span></span>  <br/> |<span data-ttu-id="d4fa5-192">1 </span><span class="sxs-lookup"><span data-stu-id="d4fa5-192">1</span></span>  <br/> |<span data-ttu-id="d4fa5-193">5061</span><span class="sxs-lookup"><span data-stu-id="d4fa5-193">5061</span></span>  <br/> |<span data-ttu-id="d4fa5-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="d4fa5-195">1800</span><span class="sxs-lookup"><span data-stu-id="d4fa5-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="d4fa5-196">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="d4fa5-197">Verificare che il record sia corretto e quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="d4fa5-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

