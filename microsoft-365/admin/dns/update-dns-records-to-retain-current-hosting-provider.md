---
title: Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Informazioni su come instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, se è stato impostato Microsoft per la gestione dei record DNS per il dominio personalizzato.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572142"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="2b617-103">Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting</span><span class="sxs-lookup"><span data-stu-id="2b617-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="2b617-104">**Se si gestiscono i record Microsoft** del dominio presso il provider di hosting DNS, non è necessario preoccuparsi dei passaggi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2b617-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="2b617-105">Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi.</span><span class="sxs-lookup"><span data-stu-id="2b617-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="2b617-106">**Se Microsoft gestisce i** record DNS, per instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, dopo aver aggiunto il dominio a Microsoft, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b617-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2b617-107">Aggiornare i record DNS nell'Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="2b617-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="2b617-108">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="2b617-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="2b617-109">Nella pagina **Domini** selezionare il dominio e quindi scegliere **Record DNS**.</span><span class="sxs-lookup"><span data-stu-id="2b617-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="2b617-110">Selezionare **+ Aggiungi record** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2b617-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2b617-111">Per **digitare** enter: **A (Address)**</span><span class="sxs-lookup"><span data-stu-id="2b617-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="2b617-112">Per **Nome host o alias** digitare **@**</span><span class="sxs-lookup"><span data-stu-id="2b617-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="2b617-113">Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="2b617-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="2b617-p102">Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="2b617-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="2b617-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b617-116">Select **Save**.</span></span> 
    
<span data-ttu-id="2b617-117">È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="2b617-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="2b617-118">Selezionare **+ Aggiungi record** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2b617-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2b617-119">Per **digitare** enter: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="2b617-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="2b617-120">Per **Nome host o alias** digitare **www**</span><span class="sxs-lookup"><span data-stu-id="2b617-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="2b617-121">Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2b617-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="2b617-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b617-122">Select **Save**.</span></span> 
    
<span data-ttu-id="2b617-123">Eseguire infine le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b617-123">Finally, do the following:</span></span>
  
<span data-ttu-id="2b617-124">[Aggiornare i record NS](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) del dominio in modo che puntino a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b617-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="2b617-125">Quando i record NS sono stati aggiornati in modo che puntino a Microsoft, il dominio è tutto configurato.</span><span class="sxs-lookup"><span data-stu-id="2b617-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="2b617-126">La posta elettronica verrà instradata a Microsoft e il traffico verso l'indirizzo del sito Web continuerà ad andare all'host del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="2b617-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
