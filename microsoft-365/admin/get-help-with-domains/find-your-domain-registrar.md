---
title: Trovare il registrar
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Informazioni su come trovare il registrar e il provider di hosting DNS usando la ricerca di InterNIC.
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706395"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="94689-103">Trovare il registrar</span><span class="sxs-lookup"><span data-stu-id="94689-103">Find your domain registrar</span></span>

 <span data-ttu-id="94689-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="94689-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="94689-105">Registrar per i domini</span><span class="sxs-lookup"><span data-stu-id="94689-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="94689-106">Trovare il proprio registrar</span><span class="sxs-lookup"><span data-stu-id="94689-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="94689-107">Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="94689-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="94689-p101">Nella [pagina di ricerca di InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio, ad esempio  *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="94689-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="94689-110">Selezionare l'opzione **Domain**, quindi selezionare **Submit**.</span><span class="sxs-lookup"><span data-stu-id="94689-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="94689-p102">Nella pagina **Whois Search Results** individuare la prima voce **Registrar**. In questa voce è indicata l'organizzazione che fornisce il servizio di registrar per il dominio.</span><span class="sxs-lookup"><span data-stu-id="94689-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="94689-113">Provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="94689-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="94689-114">Trovare il provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="94689-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="94689-115">Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="94689-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="94689-p103">Nella [pagina di ricerca di InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94689-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="94689-118">Selezionare l'opzione **Domain**, quindi selezionare **Submit**.</span><span class="sxs-lookup"><span data-stu-id="94689-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="94689-119">Nella pagina **Whois Search Results** individuare la prima voce **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="94689-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="94689-p104">Copiare le informazioni relative al server dei nomi che vengono visualizzate dopo i due punti (:), quindi incollarle nella casella **Search** nella parte superiore della pagina. Selezionare **Nameserver**, quindi fare clic su **Submit**.</span><span class="sxs-lookup"><span data-stu-id="94689-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="94689-p105">Nella pagina **Whois Search Results** individuare la voce **Registrar**. In questa voce è indicato il provider di hosting DNS, ovvero il provider DNS proprietario del server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="94689-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

