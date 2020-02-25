---
title: Creare record DNS per Office 365 quando si gestiscono i record DNS
f1.keywords:
- CSH
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
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Informazioni su come creare record DNS per Office 365 gestito da 21Vianet quando si gestiscono i record DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1f7b8330b45d6704d2d56b2c68cfcd37de84207a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257095"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="7c320-103">Creare record DNS per Office 365 quando si gestiscono i record DNS</span><span class="sxs-lookup"><span data-stu-id="7c320-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="7c320-104">Per istruzioni dettagliate su come creare record DNS per Office 365 gestito da 21Vianet, incluso il record MX necessario per il routing della posta, vedere [creare record DNS in qualsiasi provider di hosting DNS per office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7c320-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="7c320-105">Altre opzioni e alcuni aspetti da tenere presenti:</span><span class="sxs-lookup"><span data-stu-id="7c320-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="7c320-106">Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="7c320-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="7c320-107">Per le descrizioni dei record DNS, vedere [DNS Basics](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="7c320-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="7c320-108">Alcuni provider di hosting DNS non consentono di creare tutti i tipi di record necessari, che causano [limitazioni del servizio quando il provider di hosting non supporta SRV, CNAME, txt o il reindirizzamento](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="7c320-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="7c320-109">Se il provider non supporta i record SRV, TXT o CNAME, è consigliabile [trasferire il dominio](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) a un [provider che supporta tutti i tipi di record necessari](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="7c320-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="7c320-110">Per sapere quali record DNS sono necessari e trovare i valori da utilizzare per ogni record, incluso il record MX per la posta elettronica, vedere [raccogliere le informazioni necessarie per creare i record DNS di Office 365](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span><span class="sxs-lookup"><span data-stu-id="7c320-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span></span> <span data-ttu-id="7c320-111">Per le descrizioni dei record DNS, vedere [DNS Basics](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="7c320-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

