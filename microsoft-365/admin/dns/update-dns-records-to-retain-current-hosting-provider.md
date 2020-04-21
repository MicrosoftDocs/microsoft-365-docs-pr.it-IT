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
description: Informazioni su come instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, se è stato impostato Microsoft per la gestione dei record DNS per il dominio personalizzato.
ms.openlocfilehash: 08a4e505f4e2a50b3e92cae00b62415e6d02551f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629120"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="3b18c-103">Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting</span><span class="sxs-lookup"><span data-stu-id="3b18c-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="3b18c-104">**Se si gestiscono i record Microsoft del dominio presso il provider di hosting DNS**, non è necessario preoccuparsi della procedura descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3b18c-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="3b18c-105">Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi.</span><span class="sxs-lookup"><span data-stu-id="3b18c-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="3b18c-106">**Se Microsoft gestisce i record DNS**, per instradare il traffico verso un sito Web pubblico esistente ospitato all'esterno di Microsoft, dopo aver aggiunto il dominio a Microsoft, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="3b18c-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3b18c-107">Aggiornare i record DNS nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b18c-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="3b18c-108">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="3b18c-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="3b18c-109">Nell'elenco dei domini della pagina **Domini** selezionare il dominio usato per il sito Web, quindi selezionare **Impostazioni DNS** nel riquadro di gestione.</span><span class="sxs-lookup"><span data-stu-id="3b18c-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="3b18c-110">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3b18c-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="3b18c-111">Per **Tipo di DNS** immettere: **A (Indirizzo)**</span><span class="sxs-lookup"><span data-stu-id="3b18c-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="3b18c-112">Per **Nome host o alias** digitare **@**</span><span class="sxs-lookup"><span data-stu-id="3b18c-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="3b18c-113">Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="3b18c-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="3b18c-p102">Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="3b18c-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="3b18c-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3b18c-116">Select **Save**.</span></span> 
    
<span data-ttu-id="3b18c-117">È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="3b18c-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="3b18c-118">Selezionare **+ Nuovo record personalizzato** e immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3b18c-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="3b18c-119">Per **Tipo di DNS** immettere: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="3b18c-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="3b18c-120">Per **Nome host o alias** digitare **www**</span><span class="sxs-lookup"><span data-stu-id="3b18c-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="3b18c-121">Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3b18c-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="3b18c-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3b18c-122">Select **Save**.</span></span> 
    
<span data-ttu-id="3b18c-123">Eseguire infine le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b18c-123">Finally, do the following:</span></span>
  
<span data-ttu-id="3b18c-124">[Aggiornare i record NS del dominio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) in modo che puntino a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b18c-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Microsoft.</span></span> 
  
<span data-ttu-id="3b18c-125">Quando i record NS sono stati aggiornati in modo che puntino a Microsoft, il dominio è tutto configurato.</span><span class="sxs-lookup"><span data-stu-id="3b18c-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="3b18c-126">La posta elettronica viene instradata a Microsoft e il traffico verso l'indirizzo del sito Web continuerà a passare all'host del sito Web corrente.</span><span class="sxs-lookup"><span data-stu-id="3b18c-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
