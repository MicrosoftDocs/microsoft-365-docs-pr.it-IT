---
title: Record DNS necessari per Office 365 GCC High
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
description: 'Riepilogo: record DNS per Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691156"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="eb756-103">Record DNS necessari per Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="eb756-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="eb756-104">*Questo articolo si applica a Office 365 GCC High e Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="eb756-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="eb756-105">Come parte dell'onboarding di Office 365 GCC High, sarà necessario aggiungere i domini SMTP e SIP al tenant dei servizi online.</span><span class="sxs-lookup"><span data-stu-id="eb756-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="eb756-106">Per eseguire questa operazione, utilizzare il cmdlet New-MsolDomain in Azure AD PowerShell o utilizzare il [portale di amministrazione di Azure](https://portal.azure.us) per iniziare il processo di aggiunta del dominio e la proprietà di prova.</span><span class="sxs-lookup"><span data-stu-id="eb756-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="eb756-107">Dopo aver aggiunto i domini al tenant e convalidati, utilizzare le linee guida seguenti per aggiungere i record DNS corretti per i servizi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb756-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="eb756-108">Potrebbe essere necessario modificare la tabella seguente per adattare le esigenze dell'organizzazione in relazione ai record MX in ingresso e a qualsiasi record di individuazione automatica di Exchange esistente.</span><span class="sxs-lookup"><span data-stu-id="eb756-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="eb756-109">È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="eb756-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="eb756-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eb756-110">Exchange Online</span></span>

| <span data-ttu-id="eb756-111">Type</span><span class="sxs-lookup"><span data-stu-id="eb756-111">Type</span></span> | <span data-ttu-id="eb756-112">Priority</span><span class="sxs-lookup"><span data-stu-id="eb756-112">Priority</span></span> | <span data-ttu-id="eb756-113">Nome host</span><span class="sxs-lookup"><span data-stu-id="eb756-113">Host name</span></span> | <span data-ttu-id="eb756-114">Punta all'indirizzo o al valore</span><span class="sxs-lookup"><span data-stu-id="eb756-114">Points to address or value</span></span> | <span data-ttu-id="eb756-115">TTL</span><span class="sxs-lookup"><span data-stu-id="eb756-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="eb756-116">MX</span><span class="sxs-lookup"><span data-stu-id="eb756-116">MX</span></span> | <span data-ttu-id="eb756-117">0</span><span class="sxs-lookup"><span data-stu-id="eb756-117">0</span></span> | @ | <span data-ttu-id="eb756-118">*tenant*. mail.Protection.office365.US (vedere di seguito per ulteriori informazioni)</span><span class="sxs-lookup"><span data-stu-id="eb756-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="eb756-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="eb756-119">1 Hour</span></span> |
| <span data-ttu-id="eb756-120">TXT</span><span class="sxs-lookup"><span data-stu-id="eb756-120">TXT</span></span> | - | @ | <span data-ttu-id="eb756-121">v = spf1 include: SPF. Protection. office365. us-all</span><span class="sxs-lookup"><span data-stu-id="eb756-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="eb756-122">1 ora</span><span class="sxs-lookup"><span data-stu-id="eb756-122">1 Hour</span></span> |
| <span data-ttu-id="eb756-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="eb756-123">CNAME</span></span> | - | <span data-ttu-id="eb756-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eb756-124">autodiscover</span></span> | <span data-ttu-id="eb756-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="eb756-125">autodiscover.office365.us</span></span> | <span data-ttu-id="eb756-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="eb756-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="eb756-127">Record di individuazione automatica di Exchange</span><span class="sxs-lookup"><span data-stu-id="eb756-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="eb756-128">Se si dispone di Exchange Server locale, è consigliabile lasciare il record esistente durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione.</span><span class="sxs-lookup"><span data-stu-id="eb756-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="eb756-129">Record MX di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eb756-129">Exchange Online MX Record</span></span>

<span data-ttu-id="eb756-130">Il valore del record MX per i domini accettati segue un formato standard, come indicato in alto: *tenant*. mail.Protection.office365.US, sostituendo *tenant* con la prima parte del nome predefinito del tenant.</span><span class="sxs-lookup"><span data-stu-id="eb756-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="eb756-131">Ad esempio, se il nome del tenant è contoso.onmicrosoft.us, è necessario utilizzare **contoso.mail.Protection.office365.US** come valore per il record MX.</span><span class="sxs-lookup"><span data-stu-id="eb756-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="eb756-132">Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="eb756-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="eb756-133">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="eb756-133">CNAME records</span></span>

| <span data-ttu-id="eb756-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb756-134">Type</span></span> | <span data-ttu-id="eb756-135">Nome host</span><span class="sxs-lookup"><span data-stu-id="eb756-135">Host name</span></span> | <span data-ttu-id="eb756-136">Punta all'indirizzo o al valore</span><span class="sxs-lookup"><span data-stu-id="eb756-136">Points to address or value</span></span> | <span data-ttu-id="eb756-137">TTL</span><span class="sxs-lookup"><span data-stu-id="eb756-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="eb756-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="eb756-138">CNAME</span></span> | <span data-ttu-id="eb756-139">sip</span><span class="sxs-lookup"><span data-stu-id="eb756-139">sip</span></span> | <span data-ttu-id="eb756-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="eb756-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="eb756-141">1 ora</span><span class="sxs-lookup"><span data-stu-id="eb756-141">1 Hour</span></span> |
| <span data-ttu-id="eb756-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="eb756-142">CNAME</span></span> | <span data-ttu-id="eb756-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eb756-143">lyncdiscover</span></span> | <span data-ttu-id="eb756-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="eb756-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="eb756-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="eb756-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="eb756-146">Record SRV</span><span class="sxs-lookup"><span data-stu-id="eb756-146">SRV records</span></span>

| <span data-ttu-id="eb756-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb756-147">Type</span></span> | <span data-ttu-id="eb756-148">Servizio</span><span class="sxs-lookup"><span data-stu-id="eb756-148">Service</span></span> | <span data-ttu-id="eb756-149">Protocollo</span><span class="sxs-lookup"><span data-stu-id="eb756-149">Protocol</span></span> | <span data-ttu-id="eb756-150">Porta</span><span class="sxs-lookup"><span data-stu-id="eb756-150">Port</span></span> | <span data-ttu-id="eb756-151">Peso</span><span class="sxs-lookup"><span data-stu-id="eb756-151">Weight</span></span> | <span data-ttu-id="eb756-152">Priority</span><span class="sxs-lookup"><span data-stu-id="eb756-152">Priority</span></span> | <span data-ttu-id="eb756-153">Nome</span><span class="sxs-lookup"><span data-stu-id="eb756-153">Name</span></span> | <span data-ttu-id="eb756-154">Destinazione</span><span class="sxs-lookup"><span data-stu-id="eb756-154">Target</span></span> | <span data-ttu-id="eb756-155">TTL</span><span class="sxs-lookup"><span data-stu-id="eb756-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="eb756-156">SRV</span><span class="sxs-lookup"><span data-stu-id="eb756-156">SRV</span></span> | <span data-ttu-id="eb756-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="eb756-157">\_sip</span></span> | <span data-ttu-id="eb756-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="eb756-158">\_tls</span></span> | <span data-ttu-id="eb756-159">443</span><span class="sxs-lookup"><span data-stu-id="eb756-159">443</span></span> | <span data-ttu-id="eb756-160">1</span><span class="sxs-lookup"><span data-stu-id="eb756-160">1</span></span> | <span data-ttu-id="eb756-161">100</span><span class="sxs-lookup"><span data-stu-id="eb756-161">100</span></span> | @ | <span data-ttu-id="eb756-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="eb756-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="eb756-163">1 ora</span><span class="sxs-lookup"><span data-stu-id="eb756-163">1 Hour</span></span> |
| <span data-ttu-id="eb756-164">SRV</span><span class="sxs-lookup"><span data-stu-id="eb756-164">SRV</span></span> | <span data-ttu-id="eb756-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="eb756-165">\_sipfederationtls</span></span> | <span data-ttu-id="eb756-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="eb756-166">\_tcp</span></span> | <span data-ttu-id="eb756-167">5061</span><span class="sxs-lookup"><span data-stu-id="eb756-167">5061</span></span> | <span data-ttu-id="eb756-168">1</span><span class="sxs-lookup"><span data-stu-id="eb756-168">1</span></span> | <span data-ttu-id="eb756-169">100</span><span class="sxs-lookup"><span data-stu-id="eb756-169">100</span></span> | @ | <span data-ttu-id="eb756-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="eb756-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="eb756-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="eb756-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="eb756-172">Record DNS aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="eb756-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb756-173">Se si dispone di un record CNAME di *msoID* esistente nella propria area DNS, è necessario **rimuovere** il record da DNS in questo momento.</span><span class="sxs-lookup"><span data-stu-id="eb756-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="eb756-174">Il record msoID non è compatibile con le app di Microsoft 365 Enterprise *(in precedenza Office 365 ProPlus)* e impedirà l'attivazione.</span><span class="sxs-lookup"><span data-stu-id="eb756-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
