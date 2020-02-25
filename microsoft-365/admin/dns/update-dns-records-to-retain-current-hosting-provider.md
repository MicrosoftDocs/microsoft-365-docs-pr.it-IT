---
title: Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Informazioni su come instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Office 365, se è stato impostato Office 365 per gestire i record DNS per il dominio personalizzato.
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253118"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="388d6-103">Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting</span><span class="sxs-lookup"><span data-stu-id="388d6-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="388d6-p101">**Se si sceglie di gestire tutti i record di Office 365 del dominio presso il provider di hosting DNS**, non sarà necessario seguire i passaggi di questo argomento. Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi.</span><span class="sxs-lookup"><span data-stu-id="388d6-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="388d6-106">**Se la gestione dei record DNS è affidata a Office 365**, per instradare il traffico verso un sito Web pubblico esistente ospitato all'esterno di Office 365, eseguire le operazioni seguenti dopo aver aggiunto il dominio a Office 365:</span><span class="sxs-lookup"><span data-stu-id="388d6-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="388d6-107">Aggiornare i record DNS nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="388d6-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="388d6-108">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="388d6-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="388d6-109">Nell'elenco dei domini della pagina **Domini** selezionare il dominio usato per il sito Web, quindi selezionare **Impostazioni DNS** nel riquadro di gestione.</span><span class="sxs-lookup"><span data-stu-id="388d6-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="388d6-110">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="388d6-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="388d6-111">Per **Tipo di DNS** immettere: **A (Indirizzo)**</span><span class="sxs-lookup"><span data-stu-id="388d6-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="388d6-112">Per **Nome host o alias** digitare **@**</span><span class="sxs-lookup"><span data-stu-id="388d6-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="388d6-113">Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="388d6-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="388d6-p102">Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="388d6-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="388d6-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="388d6-116">Select **Save**.</span></span> 
    
<span data-ttu-id="388d6-117">È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="388d6-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="388d6-118">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="388d6-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="388d6-119">Per **Tipo di DNS** immettere: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="388d6-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="388d6-120">Per **Nome host o alias** digitare **www**</span><span class="sxs-lookup"><span data-stu-id="388d6-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="388d6-121">Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="388d6-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="388d6-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="388d6-122">Select **Save**.</span></span> 
    
<span data-ttu-id="388d6-123">Eseguire infine le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="388d6-123">Finally, do the following:</span></span>
  
<span data-ttu-id="388d6-124">[Aggiornare i record NS del dominio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) in modo che puntino a Office 365.</span><span class="sxs-lookup"><span data-stu-id="388d6-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="388d6-p103">Dopo l'aggiornamento dei record NS in modo che puntino a Office 365, la configurazione del dominio sarà completa. I messaggi di posta elettronica saranno instradati a Office 365, mentre il traffico diretto all'indirizzo del sito Web continuerà a essere indirizzato all'attuale host.</span><span class="sxs-lookup"><span data-stu-id="388d6-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 