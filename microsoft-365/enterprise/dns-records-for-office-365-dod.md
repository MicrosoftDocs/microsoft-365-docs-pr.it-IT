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
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="8357e-103">Record DNS per Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="8357e-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="8357e-104">*Questo articolo si applica a Office 365 DoD e Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="8357e-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="8357e-105">Nell'ambito dell'onboarding to Office 365 DoD, è necessario aggiungere i domini SMTP e SIP al tenant dei servizi online.</span><span class="sxs-lookup"><span data-stu-id="8357e-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="8357e-106">Per eseguire questa operazione, utilizzare il cmdlet New-MsolDomain in Azure AD PowerShell o utilizzare il [portale di amministrazione di Azure](https://portal.azure.us) per iniziare il processo di aggiunta del dominio e la proprietà di prova.</span><span class="sxs-lookup"><span data-stu-id="8357e-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="8357e-107">Dopo aver aggiunto i domini al tenant e convalidati, utilizzare le linee guida seguenti per aggiungere i record DNS corretti per i servizi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8357e-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="8357e-108">Potrebbe essere necessario modificare la tabella seguente per adattare le esigenze dell'organizzazione in relazione ai record MX in ingresso e a qualsiasi record di individuazione automatica di Exchange esistente.</span><span class="sxs-lookup"><span data-stu-id="8357e-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="8357e-109">È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8357e-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="8357e-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8357e-110">Exchange Online</span></span>

| <span data-ttu-id="8357e-111">Type</span><span class="sxs-lookup"><span data-stu-id="8357e-111">Type</span></span> | <span data-ttu-id="8357e-112">Priority</span><span class="sxs-lookup"><span data-stu-id="8357e-112">Priority</span></span> | <span data-ttu-id="8357e-113">Nome host</span><span class="sxs-lookup"><span data-stu-id="8357e-113">Host name</span></span> | <span data-ttu-id="8357e-114">Punta all'indirizzo o al valore</span><span class="sxs-lookup"><span data-stu-id="8357e-114">Points to address or value</span></span> | <span data-ttu-id="8357e-115">TTL</span><span class="sxs-lookup"><span data-stu-id="8357e-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="8357e-116">MX</span><span class="sxs-lookup"><span data-stu-id="8357e-116">MX</span></span> | <span data-ttu-id="8357e-117">0</span><span class="sxs-lookup"><span data-stu-id="8357e-117">0</span></span> | @ | <span data-ttu-id="8357e-118">*tenant*. mail.Protection.office365.US (vedere di seguito per ulteriori informazioni)</span><span class="sxs-lookup"><span data-stu-id="8357e-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="8357e-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8357e-119">1 Hour</span></span> |
| <span data-ttu-id="8357e-120">TXT</span><span class="sxs-lookup"><span data-stu-id="8357e-120">TXT</span></span> | - | @ | <span data-ttu-id="8357e-121">v = spf1 include: SPF. Protection. office365. us-all</span><span class="sxs-lookup"><span data-stu-id="8357e-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="8357e-122">1 ora</span><span class="sxs-lookup"><span data-stu-id="8357e-122">1 Hour</span></span> |
| <span data-ttu-id="8357e-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="8357e-123">CNAME</span></span> | - | <span data-ttu-id="8357e-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8357e-124">autodiscover</span></span> | <span data-ttu-id="8357e-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="8357e-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="8357e-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8357e-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="8357e-127">Record di individuazione automatica di Exchange</span><span class="sxs-lookup"><span data-stu-id="8357e-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="8357e-128">Se si dispone di Exchange Server locale, è consigliabile lasciare il record esistente durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione.</span><span class="sxs-lookup"><span data-stu-id="8357e-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="8357e-129">Record MX di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8357e-129">Exchange Online MX Record</span></span>

<span data-ttu-id="8357e-130">Il valore del record MX per i domini accettati segue un formato standard, come indicato in alto: *tenant*. mail.Protection.office365.US, sostituendo *tenant* con la prima parte del nome predefinito del tenant.</span><span class="sxs-lookup"><span data-stu-id="8357e-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="8357e-131">Ad esempio, se il nome del tenant è contoso.onmicrosoft.us, è necessario utilizzare **contoso.mail.Protection.office365.US** come valore per il record MX.</span><span class="sxs-lookup"><span data-stu-id="8357e-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="8357e-132">Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8357e-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="8357e-133">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="8357e-133">CNAME records</span></span>

| <span data-ttu-id="8357e-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="8357e-134">Type</span></span> | <span data-ttu-id="8357e-135">Nome host</span><span class="sxs-lookup"><span data-stu-id="8357e-135">Host name</span></span> | <span data-ttu-id="8357e-136">Punta all'indirizzo o al valore</span><span class="sxs-lookup"><span data-stu-id="8357e-136">Points to address or value</span></span> | <span data-ttu-id="8357e-137">TTL</span><span class="sxs-lookup"><span data-stu-id="8357e-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="8357e-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="8357e-138">CNAME</span></span> | <span data-ttu-id="8357e-139">sip</span><span class="sxs-lookup"><span data-stu-id="8357e-139">sip</span></span> | <span data-ttu-id="8357e-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8357e-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="8357e-141">1 ora</span><span class="sxs-lookup"><span data-stu-id="8357e-141">1 Hour</span></span> |
| <span data-ttu-id="8357e-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="8357e-142">CNAME</span></span> | <span data-ttu-id="8357e-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8357e-143">lyncdiscover</span></span> | <span data-ttu-id="8357e-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8357e-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="8357e-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8357e-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="8357e-146">Record SRV</span><span class="sxs-lookup"><span data-stu-id="8357e-146">SRV records</span></span>

| <span data-ttu-id="8357e-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="8357e-147">Type</span></span> | <span data-ttu-id="8357e-148">Servizio</span><span class="sxs-lookup"><span data-stu-id="8357e-148">Service</span></span> | <span data-ttu-id="8357e-149">Protocollo</span><span class="sxs-lookup"><span data-stu-id="8357e-149">Protocol</span></span> | <span data-ttu-id="8357e-150">Porta</span><span class="sxs-lookup"><span data-stu-id="8357e-150">Port</span></span> | <span data-ttu-id="8357e-151">Peso</span><span class="sxs-lookup"><span data-stu-id="8357e-151">Weight</span></span> | <span data-ttu-id="8357e-152">Priority</span><span class="sxs-lookup"><span data-stu-id="8357e-152">Priority</span></span> | <span data-ttu-id="8357e-153">Nome</span><span class="sxs-lookup"><span data-stu-id="8357e-153">Name</span></span> | <span data-ttu-id="8357e-154">Destinazione</span><span class="sxs-lookup"><span data-stu-id="8357e-154">Target</span></span> | <span data-ttu-id="8357e-155">TTL</span><span class="sxs-lookup"><span data-stu-id="8357e-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="8357e-156">SRV</span><span class="sxs-lookup"><span data-stu-id="8357e-156">SRV</span></span> | <span data-ttu-id="8357e-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="8357e-157">\_sip</span></span> | <span data-ttu-id="8357e-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="8357e-158">\_tls</span></span> | <span data-ttu-id="8357e-159">443</span><span class="sxs-lookup"><span data-stu-id="8357e-159">443</span></span> | <span data-ttu-id="8357e-160">1</span><span class="sxs-lookup"><span data-stu-id="8357e-160">1</span></span> | <span data-ttu-id="8357e-161">100</span><span class="sxs-lookup"><span data-stu-id="8357e-161">100</span></span> | @ | <span data-ttu-id="8357e-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8357e-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="8357e-163">1 ora</span><span class="sxs-lookup"><span data-stu-id="8357e-163">1 Hour</span></span> |
| <span data-ttu-id="8357e-164">SRV</span><span class="sxs-lookup"><span data-stu-id="8357e-164">SRV</span></span> | <span data-ttu-id="8357e-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8357e-165">\_sipfederationtls</span></span> | <span data-ttu-id="8357e-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="8357e-166">\_tcp</span></span> | <span data-ttu-id="8357e-167">5061</span><span class="sxs-lookup"><span data-stu-id="8357e-167">5061</span></span> | <span data-ttu-id="8357e-168">1</span><span class="sxs-lookup"><span data-stu-id="8357e-168">1</span></span> | <span data-ttu-id="8357e-169">100</span><span class="sxs-lookup"><span data-stu-id="8357e-169">100</span></span> | @ | <span data-ttu-id="8357e-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8357e-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="8357e-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8357e-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="8357e-172">Record DNS aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="8357e-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8357e-173">Se si dispone di un record CNAME di *msoID* esistente nella propria area DNS, è necessario **rimuovere** il record da DNS in questo momento.</span><span class="sxs-lookup"><span data-stu-id="8357e-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="8357e-174">Il record msoID non è compatibile con le app di Microsoft 365 Enterprise *(in precedenza Office 365 ProPlus)* e impedirà l'attivazione.</span><span class="sxs-lookup"><span data-stu-id="8357e-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
