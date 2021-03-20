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
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915975"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="6b12c-103">Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting</span><span class="sxs-lookup"><span data-stu-id="6b12c-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="6b12c-104">**Se si gestiscono i record Microsoft** del dominio presso il provider di hosting DNS, non è necessario preoccuparsi dei passaggi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6b12c-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="6b12c-105">Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi.</span><span class="sxs-lookup"><span data-stu-id="6b12c-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="6b12c-106">**Se Microsoft gestisce i** record DNS, per instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, dopo aver aggiunto il dominio a Microsoft, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b12c-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6b12c-107">Aggiornare i record DNS nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b12c-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="6b12c-108">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="6b12c-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="6b12c-109">Nella pagina **Domini** selezionare il dominio e quindi scegliere **Record DNS**.</span><span class="sxs-lookup"><span data-stu-id="6b12c-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="6b12c-110">In **Impostazioni DNS** selezionare Record **personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="6b12c-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="6b12c-111">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6b12c-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="6b12c-112">Per **Tipo di DNS** immettere: **A (Indirizzo)**</span><span class="sxs-lookup"><span data-stu-id="6b12c-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="6b12c-113">Per **Nome host o alias** digitare **@**</span><span class="sxs-lookup"><span data-stu-id="6b12c-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="6b12c-114">Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="6b12c-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="6b12c-p102">Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="6b12c-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="6b12c-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b12c-117">Select **Save**.</span></span> 
    
<span data-ttu-id="6b12c-118">È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="6b12c-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="6b12c-119">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6b12c-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="6b12c-120">Per **Tipo di DNS** immettere: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="6b12c-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="6b12c-121">Per **Nome host o alias** digitare **www**</span><span class="sxs-lookup"><span data-stu-id="6b12c-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="6b12c-122">Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6b12c-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="6b12c-123">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b12c-123">Select **Save**.</span></span> 
    
<span data-ttu-id="6b12c-124">Eseguire infine le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b12c-124">Finally, do the following:</span></span>
  
<span data-ttu-id="6b12c-125">[Aggiornare i record NS](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) del dominio in modo che puntino a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b12c-125">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="6b12c-126">Quando i record NS sono stati aggiornati in modo che puntino a Microsoft, il dominio è tutto configurato.</span><span class="sxs-lookup"><span data-stu-id="6b12c-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="6b12c-127">La posta elettronica verrà instradata a Microsoft e il traffico verso l'indirizzo del sito Web continuerà ad andare all'host del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="6b12c-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
