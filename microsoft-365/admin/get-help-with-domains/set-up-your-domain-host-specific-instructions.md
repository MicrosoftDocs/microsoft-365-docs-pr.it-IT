---
title: Configurare il dominio (istruzioni specifiche per l'ost)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Informazioni su come gestire i propri record DNS o consentire a Microsoft di gestire i record DNS per l'utente.
ms.openlocfilehash: a22968fdfcdb6be8ecfdc9dde351de034edce4b2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645300"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="ff352-103">Configurare il dominio (istruzioni specifiche per l'ost)</span><span class="sxs-lookup"><span data-stu-id="ff352-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="ff352-104">Per iniziare a utilizzare un dominio personalizzato (contoso.com) con Microsoft 365, è necessario verificare il dominio e configurare i record DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="ff352-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="ff352-105">È possibile aggiungere e gestire i record DNS utilizzando gli strumenti di amministrazione nell'host di dominio oppure fornire il controllo Microsoft dei record di dominio e verranno configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ff352-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="ff352-106">Selezionare l'host di dominio seguente per i passaggi esatti.</span><span class="sxs-lookup"><span data-stu-id="ff352-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="ff352-107">Se non si è sicuri di chi sia l'host, vedere [Find Your Domain Registrar](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="ff352-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="ff352-108">Consenti a Microsoft 365 di gestire i record DNS</span><span class="sxs-lookup"><span data-stu-id="ff352-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="ff352-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="ff352-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="ff352-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="ff352-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="ff352-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="ff352-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="ff352-112">Domini di Google</span><span class="sxs-lookup"><span data-stu-id="ff352-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="ff352-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="ff352-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="ff352-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="ff352-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="ff352-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="ff352-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="ff352-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="ff352-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="ff352-117">In alternativa, informazioni su come [modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="ff352-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="ff352-118">Gestire i propri record DNS</span><span class="sxs-lookup"><span data-stu-id="ff352-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="ff352-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="ff352-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="ff352-120">Hover</span><span class="sxs-lookup"><span data-stu-id="ff352-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="ff352-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="ff352-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="ff352-122">Gestito da Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="ff352-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="ff352-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="ff352-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="ff352-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="ff352-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="ff352-125">Zone DNS di Azure</span><span class="sxs-lookup"><span data-stu-id="ff352-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="ff352-126">name.com</span><span class="sxs-lookup"><span data-stu-id="ff352-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="ff352-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="ff352-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="ff352-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="ff352-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="ff352-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="ff352-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="ff352-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="ff352-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="ff352-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="ff352-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="ff352-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="ff352-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="ff352-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="ff352-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="ff352-134">Soluzioni di rete</span><span class="sxs-lookup"><span data-stu-id="ff352-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="ff352-135">DreamHost</span><span class="sxs-lookup"><span data-stu-id="ff352-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="ff352-136">OVH</span><span class="sxs-lookup"><span data-stu-id="ff352-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="ff352-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="ff352-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="ff352-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="ff352-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="ff352-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="ff352-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="ff352-140">Register365 per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff352-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="ff352-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="ff352-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="ff352-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="ff352-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="ff352-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="ff352-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="ff352-144"> DNS basato su Windows</span><span class="sxs-lookup"><span data-stu-id="ff352-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="ff352-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="ff352-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="ff352-146">WiX</span><span class="sxs-lookup"><span data-stu-id="ff352-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="ff352-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="ff352-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="ff352-148">Yahoo!   Small Business</span><span class="sxs-lookup"><span data-stu-id="ff352-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="ff352-149">Ho bisogno di istruzioni generali, perché l'host del dominio non è presente nell'elenco. </span><span class="sxs-lookup"><span data-stu-id="ff352-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
