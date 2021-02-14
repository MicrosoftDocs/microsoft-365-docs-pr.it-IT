---
title: Record DNS per Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Riepilogo: record DNS per Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691167"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="bd152-103">Record DNS per Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="bd152-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="bd152-104">*Questo articolo si applica a Office 365 DoD e Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="bd152-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="bd152-105">Come parte dell'onboarding in Office 365 DoD, è necessario aggiungere i domini SMTP e SIP al tenant dei Servizi online.</span><span class="sxs-lookup"><span data-stu-id="bd152-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="bd152-106">A tale scopo, puoi usare il cmdlet New-MsolDomain in Azure AD PowerShell o usare il portale azure [per](https://portal.azure.us) enti pubblici per avviare il processo di aggiunta del dominio e dimostrare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="bd152-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="bd152-107">Dopo aver aggiunto i domini al tenant e convalidato, utilizzare le indicazioni seguenti per aggiungere i record DNS appropriati per i servizi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="bd152-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="bd152-108">Potrebbe essere necessario modificare la tabella seguente in base alle esigenze dell'organizzazione in relazione ai record MX in ingresso e ai record di individuazione automatica di Exchange esistenti.</span><span class="sxs-lookup"><span data-stu-id="bd152-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="bd152-109">È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bd152-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="bd152-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bd152-110">Exchange Online</span></span>

| <span data-ttu-id="bd152-111">Type</span><span class="sxs-lookup"><span data-stu-id="bd152-111">Type</span></span> | <span data-ttu-id="bd152-112">Priority</span><span class="sxs-lookup"><span data-stu-id="bd152-112">Priority</span></span> | <span data-ttu-id="bd152-113">Nome host</span><span class="sxs-lookup"><span data-stu-id="bd152-113">Host name</span></span> | <span data-ttu-id="bd152-114">Indirizzo o valore di puntamento</span><span class="sxs-lookup"><span data-stu-id="bd152-114">Points to address or value</span></span> | <span data-ttu-id="bd152-115">TTL</span><span class="sxs-lookup"><span data-stu-id="bd152-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="bd152-116">MX</span><span class="sxs-lookup"><span data-stu-id="bd152-116">MX</span></span> | <span data-ttu-id="bd152-117">0</span><span class="sxs-lookup"><span data-stu-id="bd152-117">0</span></span> | @ | <span data-ttu-id="bd152-118">*tenant*.mail.protection.office365.us (vedere di seguito per ulteriori dettagli)</span><span class="sxs-lookup"><span data-stu-id="bd152-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="bd152-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bd152-119">1 Hour</span></span> |
| <span data-ttu-id="bd152-120">TXT</span><span class="sxs-lookup"><span data-stu-id="bd152-120">TXT</span></span> | - | @ | <span data-ttu-id="bd152-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="bd152-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="bd152-122">1 ora</span><span class="sxs-lookup"><span data-stu-id="bd152-122">1 Hour</span></span> |
| <span data-ttu-id="bd152-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="bd152-123">CNAME</span></span> | - | <span data-ttu-id="bd152-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bd152-124">autodiscover</span></span> | <span data-ttu-id="bd152-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="bd152-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="bd152-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bd152-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="bd152-127">Record di individuazione automatica di Exchange</span><span class="sxs-lookup"><span data-stu-id="bd152-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="bd152-128">Se si dispone Exchange Server locale, è consigliabile lasciare il record esistente sul posto durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione.</span><span class="sxs-lookup"><span data-stu-id="bd152-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="bd152-129">Exchange Online MX Record</span><span class="sxs-lookup"><span data-stu-id="bd152-129">Exchange Online MX Record</span></span>

<span data-ttu-id="bd152-130">Il valore del record MX per i domini accettati segue un formato standard come indicato in precedenza: *tenant*.mail.protection.office365.us, sostituendo *il tenant* con la prima parte del nome del tenant predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd152-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="bd152-131">Ad esempio, se il nome del tenant è contoso.onmicrosoft.us, è necessario utilizzare contoso.mail.protection.office365.us **come** valore per il record MX.</span><span class="sxs-lookup"><span data-stu-id="bd152-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="bd152-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd152-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="bd152-133">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="bd152-133">CNAME records</span></span>

| <span data-ttu-id="bd152-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd152-134">Type</span></span> | <span data-ttu-id="bd152-135">Nome host</span><span class="sxs-lookup"><span data-stu-id="bd152-135">Host name</span></span> | <span data-ttu-id="bd152-136">Indirizzo o valore di puntamento</span><span class="sxs-lookup"><span data-stu-id="bd152-136">Points to address or value</span></span> | <span data-ttu-id="bd152-137">TTL</span><span class="sxs-lookup"><span data-stu-id="bd152-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="bd152-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="bd152-138">CNAME</span></span> | <span data-ttu-id="bd152-139">sip</span><span class="sxs-lookup"><span data-stu-id="bd152-139">sip</span></span> | <span data-ttu-id="bd152-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bd152-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="bd152-141">1 ora</span><span class="sxs-lookup"><span data-stu-id="bd152-141">1 Hour</span></span> |
| <span data-ttu-id="bd152-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="bd152-142">CNAME</span></span> | <span data-ttu-id="bd152-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bd152-143">lyncdiscover</span></span> | <span data-ttu-id="bd152-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bd152-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="bd152-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bd152-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="bd152-146">Record SRV</span><span class="sxs-lookup"><span data-stu-id="bd152-146">SRV records</span></span>

| <span data-ttu-id="bd152-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd152-147">Type</span></span> | <span data-ttu-id="bd152-148">Servizio</span><span class="sxs-lookup"><span data-stu-id="bd152-148">Service</span></span> | <span data-ttu-id="bd152-149">Protocollo</span><span class="sxs-lookup"><span data-stu-id="bd152-149">Protocol</span></span> | <span data-ttu-id="bd152-150">Porta</span><span class="sxs-lookup"><span data-stu-id="bd152-150">Port</span></span> | <span data-ttu-id="bd152-151">Peso</span><span class="sxs-lookup"><span data-stu-id="bd152-151">Weight</span></span> | <span data-ttu-id="bd152-152">Priority</span><span class="sxs-lookup"><span data-stu-id="bd152-152">Priority</span></span> | <span data-ttu-id="bd152-153">Nome</span><span class="sxs-lookup"><span data-stu-id="bd152-153">Name</span></span> | <span data-ttu-id="bd152-154">Destinazione</span><span class="sxs-lookup"><span data-stu-id="bd152-154">Target</span></span> | <span data-ttu-id="bd152-155">TTL</span><span class="sxs-lookup"><span data-stu-id="bd152-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="bd152-156">SRV</span><span class="sxs-lookup"><span data-stu-id="bd152-156">SRV</span></span> | <span data-ttu-id="bd152-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="bd152-157">\_sip</span></span> | <span data-ttu-id="bd152-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="bd152-158">\_tls</span></span> | <span data-ttu-id="bd152-159">443</span><span class="sxs-lookup"><span data-stu-id="bd152-159">443</span></span> | <span data-ttu-id="bd152-160">1 </span><span class="sxs-lookup"><span data-stu-id="bd152-160">1</span></span> | <span data-ttu-id="bd152-161">100</span><span class="sxs-lookup"><span data-stu-id="bd152-161">100</span></span> | @ | <span data-ttu-id="bd152-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bd152-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="bd152-163">1 ora</span><span class="sxs-lookup"><span data-stu-id="bd152-163">1 Hour</span></span> |
| <span data-ttu-id="bd152-164">SRV</span><span class="sxs-lookup"><span data-stu-id="bd152-164">SRV</span></span> | <span data-ttu-id="bd152-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bd152-165">\_sipfederationtls</span></span> | <span data-ttu-id="bd152-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="bd152-166">\_tcp</span></span> | <span data-ttu-id="bd152-167">5061</span><span class="sxs-lookup"><span data-stu-id="bd152-167">5061</span></span> | <span data-ttu-id="bd152-168">1 </span><span class="sxs-lookup"><span data-stu-id="bd152-168">1</span></span> | <span data-ttu-id="bd152-169">100</span><span class="sxs-lookup"><span data-stu-id="bd152-169">100</span></span> | @ | <span data-ttu-id="bd152-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bd152-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="bd152-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bd152-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="bd152-172">Record DNS aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="bd152-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd152-173">Se nella zona DNS è presente un record CNAME *msoid* esistente, è necessario **rimuovere** il record dal DNS in questo momento.</span><span class="sxs-lookup"><span data-stu-id="bd152-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="bd152-174">Il record msoid non è compatibile con Microsoft 365 Enterprise Apps (in precedenza *Office 365 ProPlus)* e impedirà il successo dell'attivazione.</span><span class="sxs-lookup"><span data-stu-id="bd152-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
