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
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="220e7-103">Record DNS per Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="220e7-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="220e7-104">*Questo articolo si applica Office 365 DoD e Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="220e7-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="220e7-105">Come parte dell'onboarding Office 365 DoD, sarà necessario aggiungere i domini SMTP e SIP al tenant dei Servizi online.</span><span class="sxs-lookup"><span data-stu-id="220e7-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="220e7-106">A tale scopo, usare il cmdlet New-MsolDomain in Azure AD PowerShell o usare [Azure Government Portal](https://portal.azure.us) per avviare il processo di aggiunta del dominio e dimostrazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="220e7-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="220e7-107">Dopo aver aggiunto i domini al tenant e aver convalidato, usare le indicazioni seguenti per aggiungere i record DNS appropriati per i servizi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="220e7-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="220e7-108">Potrebbe essere necessario modificare la tabella seguente in base alle esigenze dell'organizzazione in relazione ai record MX in ingresso e a qualsiasi record di individuazione automatica Exchange esistente.</span><span class="sxs-lookup"><span data-stu-id="220e7-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="220e7-109">È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="220e7-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="220e7-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="220e7-110">Exchange Online</span></span>

| <span data-ttu-id="220e7-111">Type</span><span class="sxs-lookup"><span data-stu-id="220e7-111">Type</span></span> | <span data-ttu-id="220e7-112">Priority</span><span class="sxs-lookup"><span data-stu-id="220e7-112">Priority</span></span> | <span data-ttu-id="220e7-113">Nome host</span><span class="sxs-lookup"><span data-stu-id="220e7-113">Host name</span></span> | <span data-ttu-id="220e7-114">Indirizzo o valore di puntamento</span><span class="sxs-lookup"><span data-stu-id="220e7-114">Points to address or value</span></span> | <span data-ttu-id="220e7-115">TTL</span><span class="sxs-lookup"><span data-stu-id="220e7-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="220e7-116">MX</span><span class="sxs-lookup"><span data-stu-id="220e7-116">MX</span></span> | <span data-ttu-id="220e7-117">0</span><span class="sxs-lookup"><span data-stu-id="220e7-117">0</span></span> | @ | <span data-ttu-id="220e7-118">*tenant*.mail.protection.office365.us (vedere di seguito per ulteriori dettagli)</span><span class="sxs-lookup"><span data-stu-id="220e7-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="220e7-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="220e7-119">1 Hour</span></span> |
| <span data-ttu-id="220e7-120">TXT</span><span class="sxs-lookup"><span data-stu-id="220e7-120">TXT</span></span> | - | @ | <span data-ttu-id="220e7-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="220e7-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="220e7-122">1 ora</span><span class="sxs-lookup"><span data-stu-id="220e7-122">1 Hour</span></span> |
| <span data-ttu-id="220e7-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="220e7-123">CNAME</span></span> | - | <span data-ttu-id="220e7-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="220e7-124">autodiscover</span></span> | <span data-ttu-id="220e7-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="220e7-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="220e7-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="220e7-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="220e7-127">Exchange Record di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="220e7-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="220e7-128">Se si dispone Exchange Server locale, è consigliabile lasciare il record esistente in posizione durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione.</span><span class="sxs-lookup"><span data-stu-id="220e7-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="220e7-129">Exchange Online MX Record</span><span class="sxs-lookup"><span data-stu-id="220e7-129">Exchange Online MX Record</span></span>

<span data-ttu-id="220e7-130">Il valore del record MX per i domini accettati segue un formato standard come indicato in precedenza: *tenant*.mail.protection.office365.us, sostituendo *tenant* con la prima parte del nome tenant predefinito.</span><span class="sxs-lookup"><span data-stu-id="220e7-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="220e7-131">Ad esempio, se il nome del tenant contoso.onmicrosoft.us, devi usare **contoso.mail.protection.office365.us** come valore per il record MX.</span><span class="sxs-lookup"><span data-stu-id="220e7-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="220e7-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="220e7-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="220e7-133">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="220e7-133">CNAME records</span></span>

| <span data-ttu-id="220e7-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="220e7-134">Type</span></span> | <span data-ttu-id="220e7-135">Nome host</span><span class="sxs-lookup"><span data-stu-id="220e7-135">Host name</span></span> | <span data-ttu-id="220e7-136">Indirizzo o valore di puntamento</span><span class="sxs-lookup"><span data-stu-id="220e7-136">Points to address or value</span></span> | <span data-ttu-id="220e7-137">TTL</span><span class="sxs-lookup"><span data-stu-id="220e7-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="220e7-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="220e7-138">CNAME</span></span> | <span data-ttu-id="220e7-139">sip</span><span class="sxs-lookup"><span data-stu-id="220e7-139">sip</span></span> | <span data-ttu-id="220e7-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="220e7-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="220e7-141">1 ora</span><span class="sxs-lookup"><span data-stu-id="220e7-141">1 Hour</span></span> |
| <span data-ttu-id="220e7-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="220e7-142">CNAME</span></span> | <span data-ttu-id="220e7-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="220e7-143">lyncdiscover</span></span> | <span data-ttu-id="220e7-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="220e7-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="220e7-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="220e7-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="220e7-146">Record SRV</span><span class="sxs-lookup"><span data-stu-id="220e7-146">SRV records</span></span>

| <span data-ttu-id="220e7-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="220e7-147">Type</span></span> | <span data-ttu-id="220e7-148">Servizio</span><span class="sxs-lookup"><span data-stu-id="220e7-148">Service</span></span> | <span data-ttu-id="220e7-149">Protocollo</span><span class="sxs-lookup"><span data-stu-id="220e7-149">Protocol</span></span> | <span data-ttu-id="220e7-150">Porta</span><span class="sxs-lookup"><span data-stu-id="220e7-150">Port</span></span> | <span data-ttu-id="220e7-151">Peso</span><span class="sxs-lookup"><span data-stu-id="220e7-151">Weight</span></span> | <span data-ttu-id="220e7-152">Priorità</span><span class="sxs-lookup"><span data-stu-id="220e7-152">Priority</span></span> | <span data-ttu-id="220e7-153">Nome</span><span class="sxs-lookup"><span data-stu-id="220e7-153">Name</span></span> | <span data-ttu-id="220e7-154">Destinazione</span><span class="sxs-lookup"><span data-stu-id="220e7-154">Target</span></span> | <span data-ttu-id="220e7-155">TTL</span><span class="sxs-lookup"><span data-stu-id="220e7-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="220e7-156">SRV</span><span class="sxs-lookup"><span data-stu-id="220e7-156">SRV</span></span> | <span data-ttu-id="220e7-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="220e7-157">\_sip</span></span> | <span data-ttu-id="220e7-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="220e7-158">\_tls</span></span> | <span data-ttu-id="220e7-159">443</span><span class="sxs-lookup"><span data-stu-id="220e7-159">443</span></span> | <span data-ttu-id="220e7-160">1</span><span class="sxs-lookup"><span data-stu-id="220e7-160">1</span></span> | <span data-ttu-id="220e7-161">100</span><span class="sxs-lookup"><span data-stu-id="220e7-161">100</span></span> | @ | <span data-ttu-id="220e7-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="220e7-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="220e7-163">1 ora</span><span class="sxs-lookup"><span data-stu-id="220e7-163">1 Hour</span></span> |
| <span data-ttu-id="220e7-164">SRV</span><span class="sxs-lookup"><span data-stu-id="220e7-164">SRV</span></span> | <span data-ttu-id="220e7-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="220e7-165">\_sipfederationtls</span></span> | <span data-ttu-id="220e7-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="220e7-166">\_tcp</span></span> | <span data-ttu-id="220e7-167">5061</span><span class="sxs-lookup"><span data-stu-id="220e7-167">5061</span></span> | <span data-ttu-id="220e7-168">1</span><span class="sxs-lookup"><span data-stu-id="220e7-168">1</span></span> | <span data-ttu-id="220e7-169">100</span><span class="sxs-lookup"><span data-stu-id="220e7-169">100</span></span> | @ | <span data-ttu-id="220e7-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="220e7-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="220e7-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="220e7-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="220e7-172">Record DNS aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="220e7-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="220e7-173">Se nella zona DNS è presente un record CNAME *msoid* esistente, è necessario **rimuovere** il record dal DNS in questo momento.</span><span class="sxs-lookup"><span data-stu-id="220e7-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="220e7-174">Il record msoid non è compatibile con Microsoft 365 Enterprise Apps (in precedenza *Office 365 ProPlus)* e impedirà la riuscita dell'attivazione.</span><span class="sxs-lookup"><span data-stu-id="220e7-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
