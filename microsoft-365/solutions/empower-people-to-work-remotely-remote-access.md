---
title: Passaggio 2. Fornire l'accesso remoto alle app e ai servizi locali.
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Assicurarsi che i lavoratori remoti possano accedere alle risorse locali e ottimizzare l'accesso ai servizi cloud di Microsoft 365.
ms.openlocfilehash: daa1a04912dd83c7a53769299b3870b90dbfd33a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049559"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="e7bd2-104">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-104">Step 2.</span></span> <span data-ttu-id="e7bd2-105">Fornire l'accesso remoto alle app e ai servizi locali.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="e7bd2-106">Se l'organizzazione usa una VPN di accesso remoto, in genere con server VPN nel perimetro della rete e dei client VPN installati nei dispositivi degli utenti, gli utenti possono usare connessioni VPN di accesso remoto per accedere alle app e ai server locali.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="e7bd2-107">Tuttavia, potrebbe essere necessario ottimizzare il traffico verso i servizi basati nel cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="e7bd2-108">Se gli utenti non scelgono una soluzione VPN, è possibile usare il proxy di applicazione di Azure Active Directory (Azure AD) e la VPN da punto a sito (point-to-site) di Azure per fornire l'accesso, nel caso in cui tutte le app siano basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="e7bd2-109">Esistono tre tipi di configurazione principali:</span><span class="sxs-lookup"><span data-stu-id="e7bd2-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="e7bd2-110">Configurazione con soluzione VPN di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="e7bd2-111">Configurazione senza soluzione VPN di accesso remoto, bensì con identità ibrida e accesso remoto necessario solo alle app locali basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="e7bd2-112">Configurazione senza soluzione VPN di accesso remoto e accesso necessario alle app locali, alcuni delle quali non basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="e7bd2-113">Vedere questo diagramma di flusso per le opzioni di configurazione di accesso remoto descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Diagramma di flusso della configurazione di accesso remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="e7bd2-115">Grazie alle connessioni di accesso remoto, è anche possibile usare il [Desktop remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) per connettere gli utenti a un PC locale.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="e7bd2-116">Ad esempio, un lavoratore remoto può usare il Desktop remoto per connettersi al PC che si trova in ufficio dal proprio dispositivo Windows, iOS o Android.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="e7bd2-117">Una volta che il lavoratore si sarà connesso in remoto, sarà come lavorare davanti al proprio PC in ufficio.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="e7bd2-118">Ottimizzare le prestazioni per i client VPN di accesso remoto verso i servizi basati nel cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7bd2-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="e7bd2-119">Se i lavoratori remoti usano un client VPN tradizionale per ottenere l'accesso remoto alla rete dell'organizzazione, verificare che nel client VPN vi sia la modalità split tunneling.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="e7bd2-120">Senza split tunneling, tutto il traffico di lavoro remoto viene inviato attraverso la connessione VPN, tramite la quale viene poi inoltrato ai dispositivi perimetrali dell'organizzazione per essere quindi elaborato e inviato su Internet.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Traffico di rete dai client VPN senza tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="e7bd2-122">Il traffico di Microsoft 365 deve avere un percorso indiretto nell'organizzazione, che potrebbe essere inoltrato a un punto di ingresso di rete Microsoft lontano dalla posizione fisica del client VPN.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="e7bd2-123">Questo percorso indiretto aggiunge latenza al traffico di rete e riduce le prestazioni complessive.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="e7bd2-124">Grazie alla modalità split tunneling, è possibile configurare il client VPN per escludere tipi specifici di traffico da inviare tramite la connessione VPN alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="e7bd2-125">Per ottimizzare l'accesso alle risorse cloud di Microsoft 365, configurare i client VPN di split tunneling per escludere il traffico agli endpoint di Microsoft 365 di categoria **Ottimizzazione** tramite connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="e7bd2-126">Per altre informazioni, vedere [Categorie di endpoint di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="e7bd2-127">Vedere l'elenco degli endpoint di categoria Ottimizzazione [qui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Traffico di rete dai client VPN con tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="e7bd2-129">Ciò consente al client VPN di inviare e ricevere il traffico di servizi cloud Microsoft 365 rilevanti direttamente tramite Internet e verso il punto di ingresso più vicino alla rete Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="e7bd2-130">Per informazioni dettagliate e per materiale sussidiario, consultare [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling per VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="e7bd2-131">Distribuire l'accesso remoto quando si dispone solo di app Web e di un'identità ibrida</span><span class="sxs-lookup"><span data-stu-id="e7bd2-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="e7bd2-132">Se i lavoratori remoti non usano un client VPN tradizionale e gli account utente, nonché i gruppi locali, sono sincronizzati con Azure AD, è possibile usare il proxy di applicazione di Azure AD per fornire accesso remoto sicuro alle applicazioni basate sul Web ospitate nei server intranet.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="e7bd2-133">Le applicazioni basate sul Web includono i siti di SharePoint, i server di Outlook Web Access o qualsiasi altra applicazione aziendale basata sul Web.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="e7bd2-134">Di seguito sono elencati i componenti del proxy di applicazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-134">Here are the components of Azure AD Application Proxy.</span></span>

![Componenti del proxy di applicazione di Azure AD](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="e7bd2-136">Per altre informazioni, vedere la [panoramica sul proxy di applicazione di Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="e7bd2-137">Distribuire l'accesso remoto quando le app non sono solo app Web</span><span class="sxs-lookup"><span data-stu-id="e7bd2-137">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="e7bd2-138">Se i lavoratori remoti non usano un client VPN tradizionale e le app non sono basate sul Web, è possibile usare una VPN da punto a sito (point-to-site) di Azure.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-138">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="e7bd2-139">Una VPN da punto a sito stabilisce una connessione sicura dal dispositivo di un lavoratore remoto alla rete dell'organizzazione tramite una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-139">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Componenti della VPN da punto a sito di Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="e7bd2-141">Per altre informazioni, vedere la [panoramica su VPN da punto a sito](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-141">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="e7bd2-142">Distribuire il Desktop virtuale Windows per fornire l'accesso remoto ai lavoratori remoti che usano dispositivi personali</span><span class="sxs-lookup"><span data-stu-id="e7bd2-142">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="e7bd2-143">Per assistere i lavoratori remoti che possono usare solo i propri dispositivi personali e non gestiti, usare il Desktop virtuale Windows in Azure con lo scopo di creare e assegnare i desktop virtuali che gli utenti possono usare da casa.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-143">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="e7bd2-144">I PC virtualizzati possono agire esattamente come i PC connessi alla rete dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-144">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="e7bd2-145">Per altre informazioni, vedere la [panoramica sul Desktop virtuale Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-145">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="e7bd2-146">Risorse tecniche e amministrative per l’accesso remoto</span><span class="sxs-lookup"><span data-stu-id="e7bd2-146">Admin technical resources for remote access</span></span>

- <span data-ttu-id="e7bd2-147">[Come ottimizzare rapidamente il traffico di Office 365 per il personale remoto riducendo il carico nell'infrastruttura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).</span><span class="sxs-lookup"><span data-stu-id="e7bd2-147">[How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)</span></span>
- [<span data-ttu-id="e7bd2-148">Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling VPN</span><span class="sxs-lookup"><span data-stu-id="e7bd2-148">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="e7bd2-149">Risultati del passaggio 2</span><span class="sxs-lookup"><span data-stu-id="e7bd2-149">Results of Step 2</span></span>

<span data-ttu-id="e7bd2-150">Dopo la distribuzione di una soluzione di accesso remoto per i lavoratori remoti:</span><span class="sxs-lookup"><span data-stu-id="e7bd2-150">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="e7bd2-151">Configurazione di accesso remoto</span><span class="sxs-lookup"><span data-stu-id="e7bd2-151">Remote access configuration</span></span> | <span data-ttu-id="e7bd2-152">Risultati</span><span class="sxs-lookup"><span data-stu-id="e7bd2-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="e7bd2-153">È disponibile una soluzione VPN di accesso remoto</span><span class="sxs-lookup"><span data-stu-id="e7bd2-153">A remote access VPN solution is in place</span></span> | <span data-ttu-id="e7bd2-154">Il client VPN di accesso remoto è stato configurato per la modalità split tunneling e per la categoria Ottimizzazione degli endpoint di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-154">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="e7bd2-155">La soluzione VPN di accesso remoto non è disponibile ed è necessario l'accesso remoto solo alle app locali basate sul Web</span><span class="sxs-lookup"><span data-stu-id="e7bd2-155">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="e7bd2-156">Il proxy di applicazione di Azure è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-156">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="e7bd2-157">La soluzione VPN di accesso remoto non è disponibile ed è necessario l’accesso alle app locali, alcune delle quali non basate sul Web</span><span class="sxs-lookup"><span data-stu-id="e7bd2-157">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="e7bd2-158">La rete VPN da punto a sito di Azure è stata configurata.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-158">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="e7bd2-159">I lavoratori remoti usano i propri dispositivi personali da casa</span><span class="sxs-lookup"><span data-stu-id="e7bd2-159">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="e7bd2-160">Il Desktop virtuale Windows è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-160">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="e7bd2-161">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e7bd2-161">Next step</span></span>

<span data-ttu-id="e7bd2-162">Proseguire con il [passaggio 3](empower-people-to-work-remotely-manage-endpoints.md) per gestire dispositivi, PC e altri endpoint.</span><span class="sxs-lookup"><span data-stu-id="e7bd2-162">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
