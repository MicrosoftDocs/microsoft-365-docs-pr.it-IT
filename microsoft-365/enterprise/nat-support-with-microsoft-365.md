---
title: Supporto NAT con Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: In questo articolo vengono fornite informazioni dettagliate su come approssimare il numero di client che è possibile utilizzare per ogni indirizzo IP dell'organizzazione tramite NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690948"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="07c51-103">Supporto NAT con Office 365</span><span class="sxs-lookup"><span data-stu-id="07c51-103">NAT support with Office 365</span></span>

<span data-ttu-id="07c51-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="07c51-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="07c51-105">In precedenza, le indicazioni suggerivano che il numero massimo di client di Exchange da utilizzare per l'indirizzo IP per la connessione a Office 365 era di circa 2.000 client per porta di rete.</span><span class="sxs-lookup"><span data-stu-id="07c51-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="07c51-106">Perché utilizzare NAT?</span><span class="sxs-lookup"><span data-stu-id="07c51-106">Why use NAT?</span></span>

<span data-ttu-id="07c51-107">Utilizzando NAT, migliaia di persone in una rete aziendale possono "condividere" alcuni indirizzi IP instradabili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="07c51-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="07c51-p101">La maggior parte delle reti aziendali utilizza spazio degli indirizzi IP privato (RFC1918). Lo spazio degli indirizzi IP privato viene assegnato dalla Internet Assigned Numbers Authority (IANA) ed è destinato esclusivamente alle reti che non indirizzano direttamente a e da Internet globale.</span><span class="sxs-lookup"><span data-stu-id="07c51-p101">Most corporate networks use private (RFC1918) IP address space. Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="07c51-110">Per offrire accesso Internet ai dispositivi nello spazio degli indirizzi IP privato, le organizzazioni utilizzano tecnologie gateway come firewall e proxy che offrono servizi di conversione degli indirizzi di rete (NAT) o di porta (PAT).</span><span class="sxs-lookup"><span data-stu-id="07c51-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="07c51-111">Questi gateway fanno in modo che il traffico proveniente da dispositivi interni a Internet (incluso Office 365) venga visualizzato da uno o più indirizzi IP instradabili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="07c51-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="07c51-112">Ogni connessione esterna da un dispositivo interno traduce in una diversa porta TCP di origine nell'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="07c51-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="07c51-113">Perché è necessario disporre di un numero elevato di connessioni aperte contemporaneamente a Office 365?</span><span class="sxs-lookup"><span data-stu-id="07c51-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="07c51-114">Outlook può aprire otto o più connessioni (in situazioni in cui sono presenti componenti aggiuntivi, calendari condivisi, cassette postali e così via).</span><span class="sxs-lookup"><span data-stu-id="07c51-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="07c51-115">Poiché vi sono un massimo di 64.000 porte disponibili su un dispositivo NAT basato su Windows, può essere presente un massimo di 8.000 utenti dietro un indirizzo IP prima che le porte siano esaurite.</span><span class="sxs-lookup"><span data-stu-id="07c51-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="07c51-116">Si noti che se i clienti utilizzano dispositivi non basati su sistema operativo Windows per NAT, le porte totali disponibili dipendono dal dispositivo o dal software di NAT utilizzato.</span><span class="sxs-lookup"><span data-stu-id="07c51-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="07c51-117">In questo scenario, il numero massimo di porte potrebbe essere inferiore a 64.000.</span><span class="sxs-lookup"><span data-stu-id="07c51-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="07c51-118">La disponibilità delle porte è anche soggetta ad altri fattori, come le finestre che limitano le porte 4.000 per il proprio utilizzo, riducendo il numero totale di porte disponibili a 60.000.</span><span class="sxs-lookup"><span data-stu-id="07c51-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="07c51-119">Possono essere presenti altre applicazioni, ad esempio Internet Explorer, che possono connettersi contemporaneamente, che richiedono porte aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="07c51-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="07c51-120">Calcolo del numero massimo di dispositivi supportati dietro un unico indirizzo IP pubblico con Office 365</span><span class="sxs-lookup"><span data-stu-id="07c51-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="07c51-121">Per determinare il numero massimo di dispositivi dietro un unico indirizzo IP pubblico, è necessario monitorare il traffico di rete per determinare i picchi di consumo delle porte per client.</span><span class="sxs-lookup"><span data-stu-id="07c51-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="07c51-122">Inoltre, utilizzare un fattore di picco per l'utilizzo delle porte (minimo 4).</span><span class="sxs-lookup"><span data-stu-id="07c51-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="07c51-123">**Utilizzare la formula seguente per calcolare il numero di dispositivi supportati per ogni indirizzo IP:**</span><span class="sxs-lookup"><span data-stu-id="07c51-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="07c51-124">Numero massimo di dispositivi supportati dietro un unico indirizzo IP pubblico = (64.000-porte limitate)/(picco di consumo porta + fattore di picco)</span><span class="sxs-lookup"><span data-stu-id="07c51-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="07c51-125">**Ad esempio, se si verificano le condizioni seguenti:**</span><span class="sxs-lookup"><span data-stu-id="07c51-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="07c51-126">**Porte limitate:** 4.000 per il sistema operativo</span><span class="sxs-lookup"><span data-stu-id="07c51-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="07c51-127">**Consumi delle porte di picco:** 6 per dispositivo</span><span class="sxs-lookup"><span data-stu-id="07c51-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="07c51-128">**Fattore di picco:** 4</span><span class="sxs-lookup"><span data-stu-id="07c51-128">**Peak factor:** 4</span></span>

<span data-ttu-id="07c51-129">Successivamente, il numero massimo di dispositivi supportati dietro un unico indirizzo IP pubblico = (64.000-4000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="07c51-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="07c51-130">Con il rilascio di Office 365 Hosting Pack, incluso negli aggiornamenti a partire da settembre 2011 per Microsoft Office Outlook 2007 o novembre 2011 per Microsoft Outlook 2010 o un aggiornamento successivo, il numero di connessioni da Outlook (sia Office Outlook 2007 con Service Pack 2 che Outlook 2010) a Exchange può essere di almeno 2.</span><span class="sxs-lookup"><span data-stu-id="07c51-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="07c51-131">Sarà necessario fattorizzare i diversi sistemi operativi, i comportamenti degli utenti e così via per determinare il numero minimo e massimo di porte che la rete richiederà al massimo.</span><span class="sxs-lookup"><span data-stu-id="07c51-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="07c51-132">Se si desidera supportare più dispositivi dietro un unico indirizzo IP pubblico, seguire la procedura descritta per valutare il numero massimo di dispositivi che possono essere supportati:</span><span class="sxs-lookup"><span data-stu-id="07c51-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="07c51-133">Monitorare il traffico di rete per determinare il picco di consumo delle porte per client.</span><span class="sxs-lookup"><span data-stu-id="07c51-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="07c51-134">È consigliabile raccogliere i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="07c51-134">You should collect this data:</span></span>
  
- <span data-ttu-id="07c51-135">Da più posizioni</span><span class="sxs-lookup"><span data-stu-id="07c51-135">From multiple locations</span></span>
    
- <span data-ttu-id="07c51-136">Da più dispositivi</span><span class="sxs-lookup"><span data-stu-id="07c51-136">From multiple devices</span></span>
    
- <span data-ttu-id="07c51-137">In più momenti</span><span class="sxs-lookup"><span data-stu-id="07c51-137">At multiple times</span></span>
    
<span data-ttu-id="07c51-138">Utilizzare la formula precedente per calcolare il numero massimo di utenti per indirizzo IP che può essere supportato nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="07c51-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="07c51-139">Esistono diversi metodi per distribuire carico sul client attraverso ulteriori indirizzi IP pubblici.</span><span class="sxs-lookup"><span data-stu-id="07c51-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="07c51-140">Le strategie disponibili dipendono dalle funzionalità della soluzione gateway aziendale.</span><span class="sxs-lookup"><span data-stu-id="07c51-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="07c51-141">La soluzione più semplice consiste nel segmentare lo spazio degli indirizzi degli utenti e "assegnare" una serie di indirizzi IP a ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="07c51-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="07c51-142">Un'altra alternativa che molti dispositivi gateway offrono è la capacità di utilizzare un pool di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="07c51-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="07c51-143">Il vantaggio del pool di indirizzi è che è molto più dinamico e probabilmente saranno necessari minori adattamenti man mano che la base di utenti cresce.</span><span class="sxs-lookup"><span data-stu-id="07c51-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07c51-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07c51-144">See also</span></span>

[<span data-ttu-id="07c51-145">Gestione degli endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="07c51-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="07c51-146">Domande frequenti sugli endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="07c51-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
