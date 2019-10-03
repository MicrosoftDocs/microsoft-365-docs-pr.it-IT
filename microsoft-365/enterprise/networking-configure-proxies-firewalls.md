---
title: 'Passaggio 4: configurare il bypass di traffico'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare Web browser e dispositivi periferici per il bypass di traffico a posizioni di Office 365 attendibili.
ms.openlocfilehash: 32aa2216856d5a519fddb55701be745a9dacbd87
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370143"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="dcad2-103">Passaggio 4: configurare il bypass di traffico</span><span class="sxs-lookup"><span data-stu-id="dcad2-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="dcad2-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="dcad2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 - Rete](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="dcad2-106">Poiché il traffico su Internet può essere rischioso, le organizzazioni rafforzano la sicurezza delle proprie reti con dispositivi periferici come server proxy, dispositivi di decrittografia e ispezione SSL, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="dcad2-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span> <span data-ttu-id="dcad2-107">Alcuni dei problemi con i dispositivi di intercettazione delle reti sono descritti nell'articolo [Utilizzo di soluzioni o dispositivi di rete o di terze parti sul traffico di Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="dcad2-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="dcad2-p102">Tuttavia, i nomi di dominio DNS e gli indirizzi IP usati dai servizi basati sul cloud di Microsoft 365 sono noti. Inoltre, il traffico e i servizi stessi sono protetti da numerose funzionalità di sicurezza. Poiché queste misure di sicurezza e protezione sono già presenti, non è necessario che vengano duplicate dai dispositivi periferici. L'elaborazione di misure di sicurezza duplicate e destinazioni intermedie per il traffico di Microsoft 365 può ridurre notevolmente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="dcad2-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="dcad2-p103">Il primo passaggio nell'eliminazione dell'elaborazione di misure di sicurezza duplicate e destinazioni intermedie consiste nell'identificazione del traffico di Microsoft 365. Microsoft ha definito i seguenti tipi di nomi di dominio DNS e intervalli di indirizzi IP, noti come endpoint:</span><span class="sxs-lookup"><span data-stu-id="dcad2-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="dcad2-114">**Ottimizzazione**: obbligatori per la connessione a tutti i servizi di Office 365 e rappresentano più del 75% della larghezza di banda, delle connessioni e del volume di dati di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dcad2-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="dcad2-115">Questi endpoint rappresentano gli scenari di Microsoft 365 più sensibili alle prestazioni, alla latenza e alla disponibilità di rete.</span><span class="sxs-lookup"><span data-stu-id="dcad2-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="dcad2-116">**Consenti**: obbligatori per la connessione a funzionalità e servizi specifici di Microsoft 365, ma che non sono sensibili alle prestazioni e alla latenza di rete come quelli della categoria Ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="dcad2-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="dcad2-117">**Predefinita**: rappresentano i servizi e le dipendenze di Microsoft 365 che non richiedono l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="dcad2-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="dcad2-118">È possibile considerare gli endpoint di questa categoria come traffico su Internet normale.</span><span class="sxs-lookup"><span data-stu-id="dcad2-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="dcad2-119">I nomi di dominio DNS e gli intervalli di indirizzi IP sono disponibili all'indirizzo [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="dcad2-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="dcad2-120">Consigli di Microsoft:</span><span class="sxs-lookup"><span data-stu-id="dcad2-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="dcad2-121">Usare gli script Proxy Automatic Configuration (PAC) sui browser Internet dei computer locali per eseguire il bypass dei server proxy per i nomi di dominio DNS dei servizi basati sul cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dcad2-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span> <span data-ttu-id="dcad2-122">Per gli script PAC di Microsoft 365 più recenti, vedere [Script Get-Pacfile di PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="dcad2-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="dcad2-p107">Analizzare i dispositivi periferici in uso per determinare l'elaborazione di duplicati e quindi configurarli per inoltrare il traffico agli endpoint delle categorie Ottimizzazione e Consenti senza elaborazione. Questa procedura è nota come bypass di traffico.</span><span class="sxs-lookup"><span data-stu-id="dcad2-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="dcad2-125">Ecco questi suggerimenti nell'infrastruttura di rete.</span><span class="sxs-lookup"><span data-stu-id="dcad2-125">Here are these recommendations in your network infrastructure.</span></span>

![Consigli per ottimizzare il traffico locale](./media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="dcad2-127">I dispositivi perimetrali includono firewall, dispositivi di decrittografia e ispezione SSL, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="dcad2-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="dcad2-128">Per configurare e aggiornare le configurazioni dei dispositivi perimetrali, è possibile usare uno script o una chiamata REST per usare un elenco strutturato di endpoint dal servizio Web degli endpoint di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcad2-128">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see Office 365 IP Address and URL Web service.</span></span> <span data-ttu-id="dcad2-129">Per altre informazioni, vedere [Servizio Web per URL e indirizzi IP di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="dcad2-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="dcad2-p109">Tenere presente che questa procedura consente di eseguire il bypass solo per l'elaborazione dei dati di protezione di rete e proxy normale per il traffico agli endpoint delle categorie Ottimizzazione e Consenti di Microsoft 365. Tutto il resto del traffico su Internet verrà trasmesso tramite proxy e sarà soggetto all'elaborazione dei dati di protezione di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="dcad2-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="dcad2-132">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step4) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="dcad2-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="dcad2-133">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="dcad2-133">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 5](./media/stepnumbers/Step5.png)|[<span data-ttu-id="dcad2-135">Ottimizzare prestazioni di client e del servizio di Office 365</span><span class="sxs-lookup"><span data-stu-id="dcad2-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



