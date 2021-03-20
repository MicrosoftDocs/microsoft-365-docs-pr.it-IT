---
title: Ottimizzare le prestazioni di Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che illustrano come migliorare le prestazioni di Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909443"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="ac3e7-103">Ottimizzare le prestazioni di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac3e7-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="ac3e7-104">In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che illustrano come migliorare le prestazioni di Exchange Online, in particolare prima di una migrazione.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="ac3e7-105">Questo articolo fa parte del progetto Pianificazione della rete e ottimizzazione delle prestazioni [per Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="ac3e7-106">Aspetti da considerare per migliorare le prestazioni di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac3e7-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="ac3e7-107">Per migliorare la velocità della migrazione e ridurre i vincoli di larghezza di banda dell'organizzazione per Exchange Online, considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ac3e7-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="ac3e7-108">**Ridurre le dimensioni delle cassette postali.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="ac3e7-109">Le dimensioni ridotte delle cassette postali migliorano la velocità di migrazione.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="ac3e7-110">**Utilizzare le funzionalità di spostamento delle cassette postali con una distribuzione ibrida di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="ac3e7-111">Con una distribuzione ibrida di Exchange, la posta offline (sotto forma di . FILE OST) non richiede un nuovo download durante la migrazione a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="ac3e7-112">In questo modo vengono ridotti in modo significativo i requisiti di larghezza di banda per il download.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="ac3e7-113">**Pianificare gli spostamenti delle cassette postali in modo che si verifichino durante i periodi di basso traffico Internet e basso utilizzo locale di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="ac3e7-114">Durante la pianificazione degli spostamenti, le richieste di migrazione vengono inviate al proxy di replica delle cassette postali e potrebbero non essere effettuate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="ac3e7-115">**Utilizzare popup snelli per Outlook sul Web.**</span><span class="sxs-lookup"><span data-stu-id="ac3e7-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="ac3e7-116">I popup snelli offrono versioni più piccole e con un utilizzo minore della memoria di determinati messaggi di posta elettronica in Microsoft Edge o Internet Explorer tramite il rendering di alcuni componenti nel server.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="ac3e7-117">Per ulteriori informazioni, vedere [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="ac3e7-118">Consigli generali</span><span class="sxs-lookup"><span data-stu-id="ac3e7-118">General advice</span></span>

- <span data-ttu-id="ac3e7-119">Assicurarsi che la ricerca DNS per outlook.office.com il centro dati MS in una posizione di immissione logica per la posizione.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="ac3e7-120">Ricercare la memorizzazione nella cache delle cassette postali e scegliere le opzioni appropriate (re.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="ac3e7-121">periodo di memorizzazione nella cache, memorizzazione nella cache delle cassette postali condivise e così via).</span><span class="sxs-lookup"><span data-stu-id="ac3e7-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="ac3e7-122">Evitare che i dati di Outlook superino le connessioni VPN (a un ufficio centrale) prima di passare attraverso Internet.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="ac3e7-123">Assicurarsi che i dati della cassetta postale rispettino le limitazioni relative alla cartella e agli importi degli elementi.</span><span class="sxs-lookup"><span data-stu-id="ac3e7-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="ac3e7-124">Per ulteriori informazioni sulle prestazioni della migrazione di Exchange, vedere Prestazioni e procedure consigliate per la migrazione di [Office 365.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="ac3e7-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
