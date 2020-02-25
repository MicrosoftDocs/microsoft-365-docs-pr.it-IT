---
title: Configurare il dominio (istruzioni specifiche per l’host)
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
- Adm_TOC
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Informazioni su come gestire i propri record DNS o su come gestire i record DNS da parte di Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 2313aa6c629c76a852e38b4da9093576a3b75d6e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252914"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="1ffea-103">Configurare il dominio (istruzioni specifiche per l’host)</span><span class="sxs-lookup"><span data-stu-id="1ffea-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="1ffea-104">Per iniziare a utilizzare un dominio personalizzato (contoso.com) con Office 365, è necessario verificare il dominio e configurare i record DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="1ffea-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="1ffea-105">È possibile aggiungere e gestire i record DNS utilizzando gli strumenti di amministrazione nell'host di dominio oppure assegnare a Office 365 il controllo dei record di dominio e verranno configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1ffea-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="1ffea-106">Selezionare l'host di dominio seguente per i passaggi esatti.</span><span class="sxs-lookup"><span data-stu-id="1ffea-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="1ffea-107">Se non si è sicuri di chi sia l'host, vedere [Find Your Domain Registrar](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="1ffea-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="1ffea-108">Gestione dei record DNS da parte di Office 365</span><span class="sxs-lookup"><span data-stu-id="1ffea-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="1ffea-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="1ffea-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="1ffea-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="1ffea-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="1ffea-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="1ffea-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="1ffea-112">Domini di Google</span><span class="sxs-lookup"><span data-stu-id="1ffea-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="1ffea-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="1ffea-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="1ffea-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="1ffea-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="1ffea-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="1ffea-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="1ffea-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="1ffea-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="1ffea-117">In alternativa, informazioni su come [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="1ffea-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="1ffea-118">Gestire i propri record DNS</span><span class="sxs-lookup"><span data-stu-id="1ffea-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="1ffea-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="1ffea-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="1ffea-120">Hover</span><span class="sxs-lookup"><span data-stu-id="1ffea-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="1ffea-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="1ffea-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="1ffea-122">Gestito da Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="1ffea-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="1ffea-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="1ffea-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="1ffea-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="1ffea-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="1ffea-125">Zone DNS di Azure</span><span class="sxs-lookup"><span data-stu-id="1ffea-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="1ffea-126">name.com</span><span class="sxs-lookup"><span data-stu-id="1ffea-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="1ffea-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="1ffea-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="1ffea-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="1ffea-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="1ffea-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="1ffea-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="1ffea-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="1ffea-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="1ffea-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="1ffea-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="1ffea-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="1ffea-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="1ffea-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="1ffea-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="1ffea-134">Soluzioni di rete</span><span class="sxs-lookup"><span data-stu-id="1ffea-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="1ffea-135">DreamHost</span><span class="sxs-lookup"><span data-stu-id="1ffea-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="1ffea-136">OVH</span><span class="sxs-lookup"><span data-stu-id="1ffea-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="1ffea-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="1ffea-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="1ffea-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="1ffea-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="1ffea-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="1ffea-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="1ffea-140">Register365 per Office 365</span><span class="sxs-lookup"><span data-stu-id="1ffea-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="1ffea-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="1ffea-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="1ffea-142">web.com</span><span class="sxs-lookup"><span data-stu-id="1ffea-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="1ffea-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="1ffea-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="1ffea-144">DNS basato su Windows</span><span class="sxs-lookup"><span data-stu-id="1ffea-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="1ffea-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="1ffea-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="1ffea-146">WiX</span><span class="sxs-lookup"><span data-stu-id="1ffea-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="1ffea-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="1ffea-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="1ffea-148">Yahoo!   Small Business</span><span class="sxs-lookup"><span data-stu-id="1ffea-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="1ffea-149">Ho bisogno di istruzioni generali, perché l'host del dominio non è presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1ffea-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   