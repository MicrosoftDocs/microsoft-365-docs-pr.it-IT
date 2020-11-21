---
title: Risposta e supporto di Contoso COVID-19 per il lavoro remoto e onsite
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo la Contoso Corporation ha risposto alla pandemia di COVID-19 e ha ingegnerizzato l'infrastruttura di installazione e aggiornamento del software per il lavoro remoto e onsite.
ms.openlocfilehash: 8e25b399d7acd2cb3486283623d29315eac9491e
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371760"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="60b3f-103">Risposta e supporto di Contoso COVID-19 per il lavoro remoto e onsite</span><span class="sxs-lookup"><span data-stu-id="60b3f-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="60b3f-104">Contoso aveva sempre supportato i propri dipendenti remoti, che accedevano alle risorse locali tramite un server VPN centrale nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="60b3f-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="60b3f-105">Contoso aveva emesso tutti i dipendenti remoti un computer portatile gestito.</span><span class="sxs-lookup"><span data-stu-id="60b3f-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="60b3f-106">I lavoratori locali avevano una combinazione di computer desktop e laptop.</span><span class="sxs-lookup"><span data-stu-id="60b3f-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="60b3f-107">Risposta di Contoso a COVID-19</span><span class="sxs-lookup"><span data-stu-id="60b3f-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="60b3f-108">Con l'insorgenza della pandemia di COVID-19, tutti gli addetti sono stati all'improvviso operatori remoti.</span><span class="sxs-lookup"><span data-stu-id="60b3f-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="60b3f-109">Contoso ha risposto spostando la propria forza lavoro in modo da funzionare da casa e condurre le attività primarie tramite l'accesso remoto alle risorse locali e online utilizzando i servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60b3f-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="60b3f-110">Contoso disponeva di server VPN di accesso remoto nell'ufficio della sede di Parigi per supportare il 25% della sua forza lavoro già remota, ma è stato spostato rapidamente per aumentare la capacità di accesso remoto a supporto del 90% del personale.</span><span class="sxs-lookup"><span data-stu-id="60b3f-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="60b3f-111">Contoso ha distribuito i server VPN di accesso remoto in ogni ufficio satellite in modo che i dipendenti remoti utilizzino un punto di ingresso vicino a livello regionale per l'accesso alla rete Intranet contoso.</span><span class="sxs-lookup"><span data-stu-id="60b3f-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="60b3f-112">Contoso ha inoltre aggiornato la configurazione dei client VPN installati su laptop, tablet e smartphone per il tunneling suddiviso in modo che il traffico per l'insieme di endpoint di Office 365 non sia stato ignorato dalla connessione VPN ed è stato inviato direttamente su Internet.</span><span class="sxs-lookup"><span data-stu-id="60b3f-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="60b3f-113">Per ulteriori informazioni, vedere [ottimizzare la connettività di Office 365 per gli utenti remoti tramite il tunneling Split VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).</span><span class="sxs-lookup"><span data-stu-id="60b3f-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="60b3f-114">Ecco la configurazione risultante con i dispositivi VPN installati nella sede di Parigi e in ciascuno degli uffici satellite.</span><span class="sxs-lookup"><span data-stu-id="60b3f-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Infrastruttura VPN di contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="60b3f-116">Un lavoratore remoto con il client VPN installato utilizza il DNS per trovare l'ufficio più vicino regionalmente e si connette al dispositivo VPN installato.</span><span class="sxs-lookup"><span data-stu-id="60b3f-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="60b3f-117">Con split tunneling, il traffico verso Microsoft 365 Optimize endpoint viene inviato direttamente al percorso di rete Microsoft 365 più vicino a livello regionale.</span><span class="sxs-lookup"><span data-stu-id="60b3f-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="60b3f-118">Tutti gli altri traffici vengono inviati tramite la connessione VPN al dispositivo VPN.</span><span class="sxs-lookup"><span data-stu-id="60b3f-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="60b3f-119">Supporto di Contoso per il lavoro remoto e onsite</span><span class="sxs-lookup"><span data-stu-id="60b3f-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="60b3f-120">Dopo aver apportato le modifiche iniziali per supportare principalmente i lavoratori remoti durante le operazioni di blocco regionali, Contoso ha apportato modifiche all'infrastruttura per il supporto di attività remote e onsite in cui un lavoratore potrebbe essere:</span><span class="sxs-lookup"><span data-stu-id="60b3f-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="60b3f-121">Sempre a distanza.</span><span class="sxs-lookup"><span data-stu-id="60b3f-121">Always remote.</span></span>
- <span data-ttu-id="60b3f-122">Sempre in locale.</span><span class="sxs-lookup"><span data-stu-id="60b3f-122">Always on-premises.</span></span>
- <span data-ttu-id="60b3f-123">Una combinazione di Remote e locali.</span><span class="sxs-lookup"><span data-stu-id="60b3f-123">A combination of remote and on-premises.</span></span>

<span data-ttu-id="60b3f-124">Le funzionalità di identità, sicurezza e conformità di Microsoft 365 sono progettate per la relazione di trust zero e per funzionare indipendentemente dalla posizione dell'utente e del dispositivo in uso.</span><span class="sxs-lookup"><span data-stu-id="60b3f-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="60b3f-125">Per ulteriori informazioni, vedere [zero Trust](https://www.microsoft.com/security/business/zero-trust).</span><span class="sxs-lookup"><span data-stu-id="60b3f-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="60b3f-126">Tuttavia, la gestione delle nuove installazioni e degli aggiornamenti del software dipende dalla posizione del dispositivo perché il software da installare potrebbe provenire da un'origine locale o da una rete Internet.</span><span class="sxs-lookup"><span data-stu-id="60b3f-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="60b3f-127">Gli architetti IT di Contoso hanno creato la nuova infrastruttura di installazione e aggiornamento in base alla posizione del dispositivo anziché al lavoratore.</span><span class="sxs-lookup"><span data-stu-id="60b3f-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="60b3f-128">Sono stati designati due tipi di dispositivi: dedicate in locale e in roaming.</span><span class="sxs-lookup"><span data-stu-id="60b3f-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="60b3f-129">Dedicato in locale</span><span class="sxs-lookup"><span data-stu-id="60b3f-129">Dedicated on-premises</span></span>

<span data-ttu-id="60b3f-130">Un dispositivo locale dedicato è un computer desktop o server che non lascia mai la rete Intranet Contoso e non dispone di un client VPN installato.</span><span class="sxs-lookup"><span data-stu-id="60b3f-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="60b3f-131">Questi dispositivi locali continuano a usare Microsoft endpoint Configuration Manager e i relativi punti di distribuzione per le installazioni e gli aggiornamenti di Windows 10, Microsoft 365 Apps for Enterprise e del browser perimetrale.</span><span class="sxs-lookup"><span data-stu-id="60b3f-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="60b3f-132">Roaming</span><span class="sxs-lookup"><span data-stu-id="60b3f-132">Roaming</span></span>

<span data-ttu-id="60b3f-133">Un dispositivo di roaming può lasciare la rete Intranet Contoso e include i computer portatili rilasciati a numerosi impiegati e a tutti i lavoratori remoti e ad altri dispositivi di proprietà dell'organizzazione, ad esempio smartphone e tablet con il client VPN contoso installato.</span><span class="sxs-lookup"><span data-stu-id="60b3f-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="60b3f-134">Poiché questi dispositivi possono essere connessi a Internet in qualsiasi momento, usano Intune o altri servizi basati su cloud per installazioni e aggiornamenti di Windows 10, Microsoft 365 Apps for Enterprise e Edge.</span><span class="sxs-lookup"><span data-stu-id="60b3f-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="60b3f-135">Non utilizzano i punti di distribuzione di gestione configurazione locali esistenti.</span><span class="sxs-lookup"><span data-stu-id="60b3f-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="60b3f-136">Questo significa che alcune delle installazioni e degli aggiornamenti per il dispositivo di roaming verranno eseguite su Internet mentre sono in locale e connesse alla rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="60b3f-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="60b3f-137">Ma contoso IT Architects ha deciso che la semplicità di configurazione era più importante dell'ottimizzazione della larghezza di banda Intranet su Internet, soprattutto quando la maggior parte dei worker remoti raramente sono connessi alla rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="60b3f-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="60b3f-138">Di seguito viene visualizzata l'infrastruttura risultante.</span><span class="sxs-lookup"><span data-stu-id="60b3f-138">Here is the resulting infrastructure.</span></span>

![Infrastruttura di installazione e aggiornamento di contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="60b3f-140">Il comportamento di installazione e aggiornamento viene determinato rendendo gli account computer dei dispositivi membri di uno di questi gruppi:</span><span class="sxs-lookup"><span data-stu-id="60b3f-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="60b3f-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="60b3f-141">OnPremDevices</span></span>

  <span data-ttu-id="60b3f-142">Il client Configuration Manager sul dispositivo utilizza i punti di distribuzione per le installazioni e gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="60b3f-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="60b3f-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="60b3f-143">RoamingDevices</span></span>

  <span data-ttu-id="60b3f-144">Intune e altre impostazioni del dispositivo specificano l'utilizzo della rete Microsoft 365 per le installazioni e gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="60b3f-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="60b3f-145">Nuovo processo di onboarding</span><span class="sxs-lookup"><span data-stu-id="60b3f-145">New onboarding process</span></span>

<span data-ttu-id="60b3f-146">Per un nuovo dispositivo locale dedicato emesso a un nuovo lavoratore o per un nuovo server in un datacenter, quando il lavoratore accede, il client di Configuration Manager basato sull'appartenenza del dispositivo nel gruppo OnPremDevices Scarica e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for Enterprise e Edge dai punti di distribuzione di Configuration Manager locali.</span><span class="sxs-lookup"><span data-stu-id="60b3f-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="60b3f-147">Al termine dell'operazione, il dispositivo locale dedicato è pronto per l'uso e utilizza questi punti di distribuzione per gli aggiornamenti in corso.</span><span class="sxs-lookup"><span data-stu-id="60b3f-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="60b3f-148">Per un nuovo dispositivo remoto rilasciato a un nuovo lavoratore, quando il lavoratore accede, il dispositivo, in base alla sua appartenenza al gruppo RoamingDevices, contatta il servizio cloud di Intune e altri servizi e download e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for Enterprise e Edge.</span><span class="sxs-lookup"><span data-stu-id="60b3f-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="60b3f-149">Al termine dell'operazione, il dispositivo remoto è pronto per l'uso e utilizza il client VPN installato per l'accesso alle risorse locali e la rete Microsoft 365 per gli aggiornamenti in corso.</span><span class="sxs-lookup"><span data-stu-id="60b3f-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="60b3f-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="60b3f-150">Next step</span></span>

<span data-ttu-id="60b3f-151">[Autorizzare gli utenti remoti](empower-people-to-work-remotely.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="60b3f-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>