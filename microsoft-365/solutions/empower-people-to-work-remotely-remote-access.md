---
title: Passaggio 2. Fornire l'accesso remoto alle app e ai servizi locali.
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Assicurarsi che i lavoratori remoti possano accedere alle risorse locali e ottimizzare l'accesso ai servizi cloud di Microsoft 365.
ms.openlocfilehash: 43000ce27fc24dbc6c2db3782b0ed40aa66b7fd2
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055532"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="d180e-104">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d180e-104">Step 2.</span></span> <span data-ttu-id="d180e-105">Fornire l'accesso remoto alle app e ai servizi locali.</span><span class="sxs-lookup"><span data-stu-id="d180e-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="d180e-106">Se l'organizzazione usa una VPN di accesso remoto, in genere con server VPN nel perimetro della rete e dei client VPN installati nei dispositivi degli utenti, gli utenti possono usare connessioni VPN di accesso remoto per accedere alle app e ai server locali.</span><span class="sxs-lookup"><span data-stu-id="d180e-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="d180e-107">Tuttavia, potrebbe essere necessario ottimizzare il traffico verso i servizi basati nel cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d180e-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="d180e-108">Se gli utenti non scelgono una soluzione VPN, è possibile usare il proxy di applicazione di Azure Active Directory (Azure AD) e la VPN da punto a sito (point-to-site) di Azure per fornire l'accesso, nel caso in cui tutte le app siano basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="d180e-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="d180e-109">Ecco le configurazioni principali di accesso remoto:</span><span class="sxs-lookup"><span data-stu-id="d180e-109">Here are the primary configurations for remote access:</span></span>

- <span data-ttu-id="d180e-110">Configurazione con soluzione VPN di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="d180e-110">You are already using a remote access VPN solution.</span></span>
- <span data-ttu-id="d180e-111">Configurazione senza soluzione VPN di accesso remoto e uso del computer personale da parte dei lavoratori remoti.</span><span class="sxs-lookup"><span data-stu-id="d180e-111">You are not using a remote access VPN solution and you want your remote workers to use their personal computers.</span></span>
- <span data-ttu-id="d180e-112">Configurazione senza soluzione VPN di accesso remoto, bensì con identità ibrida e accesso remoto necessario solo alle app locali basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="d180e-112">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
- <span data-ttu-id="d180e-113">Configurazione senza soluzione VPN di accesso remoto e accesso necessario alle app locali, alcuni delle quali non basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="d180e-113">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="d180e-114">Vedere questo diagramma di flusso per le opzioni di configurazione di accesso remoto descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d180e-114">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Diagramma di flusso della configurazione di accesso remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="d180e-116">Grazie alle connessioni di accesso remoto, è anche possibile usare il [Desktop remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) per connettere gli utenti a un PC locale.</span><span class="sxs-lookup"><span data-stu-id="d180e-116">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="d180e-117">Ad esempio, un lavoratore remoto può usare il Desktop remoto per connettersi al PC dell'ufficio dal proprio dispositivo Windows, iOS o Android.</span><span class="sxs-lookup"><span data-stu-id="d180e-117">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS, or Android device.</span></span> <span data-ttu-id="d180e-118">Una volta che il lavoratore si sarà connesso in remoto, sarà come lavorare davanti al proprio PC in ufficio.</span><span class="sxs-lookup"><span data-stu-id="d180e-118">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="d180e-119">Ottimizzare le prestazioni per i client VPN di accesso remoto verso i servizi basati nel cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d180e-119">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="d180e-120">Se i lavoratori remoti usano un client VPN tradizionale per ottenere l'accesso remoto alla rete dell'organizzazione, verificare che nel client VPN vi sia la modalità split tunneling.</span><span class="sxs-lookup"><span data-stu-id="d180e-120">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="d180e-121">Senza split tunneling, tutto il traffico di lavoro remoto viene inviato attraverso la connessione VPN, tramite la quale viene poi inoltrato ai dispositivi perimetrali dell'organizzazione per essere quindi elaborato e inviato su Internet.</span><span class="sxs-lookup"><span data-stu-id="d180e-121">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Traffico di rete dai client VPN senza tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="d180e-123">Il traffico di Microsoft 365 deve avere un percorso indiretto nell'organizzazione, che potrebbe essere inoltrato a un punto di ingresso di rete Microsoft lontano dalla posizione fisica del client VPN.</span><span class="sxs-lookup"><span data-stu-id="d180e-123">Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="d180e-124">Questo percorso indiretto aggiunge latenza al traffico di rete e riduce le prestazioni complessive.</span><span class="sxs-lookup"><span data-stu-id="d180e-124">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="d180e-125">Grazie alla modalità split tunneling, è possibile configurare il client VPN per escludere tipi specifici di traffico da inviare tramite la connessione VPN alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d180e-125">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="d180e-126">Per ottimizzare l'accesso alle risorse cloud di Microsoft 365, configurare i client VPN di split tunneling per escludere il traffico agli endpoint di Microsoft 365 di categoria **Ottimizzazione** tramite connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="d180e-126">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="d180e-127">Per altre informazioni, vedere [Categorie di endpoint di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="d180e-127">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="d180e-128">Consultare l'[elenco](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) degli endpoint di categoria Ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="d180e-128">See [this list](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) of Optimize category endpoints.</span></span>

<span data-ttu-id="d180e-129">Ecco il conseguente flusso di traffico, in cui la maggior parte del traffico per le app cloud di Microsoft 365 evita la connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="d180e-129">Here is the resulting traffic flow, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![Traffico di rete dai client VPN con tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="d180e-131">Ciò consente al client VPN di inviare e ricevere il traffico di servizi cloud Microsoft 365 rilevanti direttamente tramite Internet e verso il punto di ingresso più vicino alla rete Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d180e-131">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="d180e-132">Per informazioni dettagliate e per materiale sussidiario, consultare [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling per VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span><span class="sxs-lookup"><span data-stu-id="d180e-132">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="d180e-133">Distribuire l'accesso remoto quando si dispone solo di app Web e di un'identità ibrida</span><span class="sxs-lookup"><span data-stu-id="d180e-133">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="d180e-134">Se i lavoratori remoti non usano un client VPN tradizionale e gli account utente e i gruppi locali sono sincronizzati con Azure AD, è possibile usare il proxy di applicazione di Azure AD per fornire accesso remoto sicuro alle applicazioni basate sul Web ospitate nei server locali.</span><span class="sxs-lookup"><span data-stu-id="d180e-134">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on on-premises servers.</span></span> <span data-ttu-id="d180e-135">Le applicazioni basate sul Web includono i siti di SharePoint Server, i server di Outlook Web Access o qualsiasi altra applicazione aziendale basata sul Web.</span><span class="sxs-lookup"><span data-stu-id="d180e-135">Web-based applications include SharePoint Server sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="d180e-136">Di seguito sono elencati i componenti del proxy di applicazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d180e-136">Here are the components of Azure AD Application Proxy.</span></span>

![Componenti del proxy di applicazione di Azure AD](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="d180e-138">Per altre informazioni, vedere la [panoramica sul proxy di applicazione di Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="d180e-138">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

>[!Note]
><span data-ttu-id="d180e-139">Il proxy di applicazione di Azure AD non è incluso in un abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d180e-139">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="d180e-140">È necessario pagare per l'uso con un abbonamento di Azure diverso.</span><span class="sxs-lookup"><span data-stu-id="d180e-140">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="d180e-141">Distribuire l'accesso remoto quando le app non sono solo app Web</span><span class="sxs-lookup"><span data-stu-id="d180e-141">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="d180e-142">Se i lavoratori remoti non usano un client VPN tradizionale e le app non sono basate sul Web, è possibile usare una VPN da punto a sito (point-to-site) P2S di Azure.</span><span class="sxs-lookup"><span data-stu-id="d180e-142">If your remote workers are not using a traditional VPN client and you have apps that are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="d180e-143">Una VPN da punto a sito stabilisce una connessione sicura dal dispositivo di un lavoratore remoto alla rete dell'organizzazione tramite una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="d180e-143">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Componenti della VPN da punto a sito di Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="d180e-145">Per altre informazioni, vedere la [panoramica su VPN da punto a sito](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="d180e-145">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="d180e-146">VPN de punto a sito di Azure non è incluso in un abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d180e-146">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="d180e-147">È necessario pagare per l'uso con un abbonamento di Azure diverso.</span><span class="sxs-lookup"><span data-stu-id="d180e-147">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="d180e-148">Distribuire il Desktop virtuale Windows per fornire l'accesso remoto ai lavoratori remoti che usano dispositivi personali</span><span class="sxs-lookup"><span data-stu-id="d180e-148">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="d180e-149">Per assistere i lavoratori remoti che possono usare solo i propri dispositivi personali e non gestiti, usare il Desktop virtuale Windows in Azure con lo scopo di creare e assegnare i desktop virtuali che gli utenti possono usare da casa.</span><span class="sxs-lookup"><span data-stu-id="d180e-149">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="d180e-150">I PC virtualizzati possono agire esattamente come i PC connessi alla rete dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d180e-150">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Componenti di Azure Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="d180e-152">Per altre informazioni, vedere la [panoramica sul Desktop virtuale Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="d180e-152">For more information, see this [overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span> 

>[!Note]
><span data-ttu-id="d180e-153">Windows Virtual Desktop non è incluso in un abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d180e-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="d180e-154">È necessario pagare per l'uso con un abbonamento di Azure diverso.</span><span class="sxs-lookup"><span data-stu-id="d180e-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="d180e-155">Proteggere le connessioni dei servizi del desktop remoto con il gateway Servizi del desktop remoto</span><span class="sxs-lookup"><span data-stu-id="d180e-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="d180e-156">Se si usa Servizi del desktop remoto (SDR) per consentire ai dipendenti di entrare in un computer con Windows in una rete locale, è consigliabile usare un gateway di Servizi del desktop remoto di Microsoft nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d180e-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="d180e-157">Il gateway usa il protocollo (TLS) Transport Layer Security per crittografare le comunicazioni, ed evita che il computer locale che ospita i RDS sia direttamente connesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="d180e-157">The gateway uses Transport Layer Security (TLS) to encrypt traffic and prevents the on-premises computer hosting RDS from being directly exposed to the Internet.</span></span>

![Proteggere le connessioni dei Servizi del desktop remoto con il gateway Servizi del desktop remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="d180e-159">Per altre informazioni, vedere [questo articolo](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/).</span><span class="sxs-lookup"><span data-stu-id="d180e-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="d180e-160">Risorse tecniche e amministrative per l’accesso remoto</span><span class="sxs-lookup"><span data-stu-id="d180e-160">Admin technical resources for remote access</span></span>

- <span data-ttu-id="d180e-161">[Come ottimizzare rapidamente il traffico di Office 365 per il personale remoto riducendo il carico nell'infrastruttura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).</span><span class="sxs-lookup"><span data-stu-id="d180e-161">[How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)</span></span>
- [<span data-ttu-id="d180e-162">Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling VPN</span><span class="sxs-lookup"><span data-stu-id="d180e-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?)

## <a name="results-of-step-2"></a><span data-ttu-id="d180e-163">Risultati del passaggio 2</span><span class="sxs-lookup"><span data-stu-id="d180e-163">Results of Step 2</span></span>

<span data-ttu-id="d180e-164">Dopo la distribuzione di una soluzione di accesso remoto per i lavoratori remoti:</span><span class="sxs-lookup"><span data-stu-id="d180e-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="d180e-165">Configurazione di accesso remoto</span><span class="sxs-lookup"><span data-stu-id="d180e-165">Remote access configuration</span></span> | <span data-ttu-id="d180e-166">Risultati</span><span class="sxs-lookup"><span data-stu-id="d180e-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="d180e-167">È disponibile una soluzione VPN di accesso remoto</span><span class="sxs-lookup"><span data-stu-id="d180e-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="d180e-168">Il client VPN di accesso remoto è stato configurato per la modalità split tunneling e per la categoria Ottimizzazione degli endpoint di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d180e-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="d180e-169">La soluzione VPN di accesso remoto non è disponibile ed è necessario l'accesso remoto solo alle app locali basate sul Web</span><span class="sxs-lookup"><span data-stu-id="d180e-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="d180e-170">Il proxy di applicazione di Azure è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="d180e-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="d180e-171">La soluzione VPN di accesso remoto non è disponibile ed è necessario l’accesso alle app locali, alcune delle quali non basate sul Web</span><span class="sxs-lookup"><span data-stu-id="d180e-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="d180e-172">La rete VPN da punto a sito di Azure è stata configurata.</span><span class="sxs-lookup"><span data-stu-id="d180e-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="d180e-173">I lavoratori remoti usano i propri dispositivi personali da casa</span><span class="sxs-lookup"><span data-stu-id="d180e-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="d180e-174">Il Desktop virtuale Windows è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="d180e-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="d180e-175">I lavoratori remoti usano connessioni di SDR per sistemi locali</span><span class="sxs-lookup"><span data-stu-id="d180e-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="d180e-176">Il gateway di Servizi del desktop remoto è stato distribuito nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d180e-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="d180e-177">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d180e-177">Next step</span></span>

<span data-ttu-id="d180e-178">[![Passaggio 3: distribuire i servizi di sicurezza e conformità di Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="d180e-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="d180e-179">Proseguire con il [passaggio 3](empower-people-to-work-remotely-security-compliance.md) per distribuire i servizi di sicurezza e conformità di Microsoft 365 per proteggere le app, i dati e i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d180e-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>

