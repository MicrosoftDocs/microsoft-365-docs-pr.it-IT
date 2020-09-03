---
title: Fase 1 di autenticazione federata a disponibilità elevata configurare Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: "Riepilogo: configurare l'infrastruttura Microsoft Azure per ospitare l'autenticazione federata a disponibilità elevata per Microsoft 365."
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332341"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="af162-103">Fase 1 dell'autenticazione federata a disponibilità elevata: configurare Azure</span><span class="sxs-lookup"><span data-stu-id="af162-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="af162-104">In questa fase, vengono creati i gruppi di risorse, la rete virtuale (rete virtuale) e i set di disponibilità in Azure che ospiteranno le macchine virtuali nelle fasi 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="af162-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="af162-105">È necessario completare questa fase prima di passare a [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="af162-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="af162-106">Vedere [deploy High Availability Federated Authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) per tutte le fasi.</span><span class="sxs-lookup"><span data-stu-id="af162-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="af162-107">È necessario eseguire il provisioning di Azure con i componenti di base seguenti:</span><span class="sxs-lookup"><span data-stu-id="af162-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="af162-108">Gruppi di risorse</span><span class="sxs-lookup"><span data-stu-id="af162-108">Resource groups</span></span>
    
- <span data-ttu-id="af162-109">Una rete virtuale (VNet) Azure cross-premise con subnet per ospitare le macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="af162-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="af162-110">Gruppi di sicurezza di rete per l'esecuzione dell'isolamento delle subnet</span><span class="sxs-lookup"><span data-stu-id="af162-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="af162-111">Set di disponibilità</span><span class="sxs-lookup"><span data-stu-id="af162-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="af162-112">Configurare i componenti di Azure</span><span class="sxs-lookup"><span data-stu-id="af162-112">Configure Azure components</span></span>

<span data-ttu-id="af162-113">Prima di iniziare la configurazione dei componenti di Azure, compilare le tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="af162-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="af162-114">Per facilitare le procedure per la configurazione di Azure, stampare questa sezione e annotare le informazioni necessarie o copiare questa sezione in un documento e compilarla.</span><span class="sxs-lookup"><span data-stu-id="af162-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="af162-115">Per le impostazioni della VNet, compilare la tabella V.</span><span class="sxs-lookup"><span data-stu-id="af162-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="af162-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-116">**Item**</span></span>|<span data-ttu-id="af162-117">**Impostazione di configurazione**</span><span class="sxs-lookup"><span data-stu-id="af162-117">**Configuration setting**</span></span>|<span data-ttu-id="af162-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="af162-118">**Description**</span></span>|<span data-ttu-id="af162-119">**Valore**</span><span class="sxs-lookup"><span data-stu-id="af162-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af162-120">1.</span><span class="sxs-lookup"><span data-stu-id="af162-120">1.</span></span>  <br/> |<span data-ttu-id="af162-121">Nome VNet</span><span class="sxs-lookup"><span data-stu-id="af162-121">VNet name</span></span>  <br/> |<span data-ttu-id="af162-122">Un nome da assegnare alla VNet (ad esempio, FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="af162-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-124">2.</span><span class="sxs-lookup"><span data-stu-id="af162-124">2.</span></span>  <br/> |<span data-ttu-id="af162-125">Percorso VNet</span><span class="sxs-lookup"><span data-stu-id="af162-125">VNet location</span></span>  <br/> |<span data-ttu-id="af162-126">Data center di Azure regionale che conterrà la rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="af162-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-128">3.</span><span class="sxs-lookup"><span data-stu-id="af162-128">3.</span></span>  <br/> |<span data-ttu-id="af162-129">Indirizzo IP del dispositivo VPN</span><span class="sxs-lookup"><span data-stu-id="af162-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="af162-130">L'indirizzo IPv4 pubblico dell'interfaccia del dispositivo VPN su Internet.</span><span class="sxs-lookup"><span data-stu-id="af162-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-132">4.</span><span class="sxs-lookup"><span data-stu-id="af162-132">4.</span></span>  <br/> |<span data-ttu-id="af162-133">Spazio di indirizzi della VNet</span><span class="sxs-lookup"><span data-stu-id="af162-133">VNet address space</span></span>  <br/> |<span data-ttu-id="af162-p103">Lo spazio di indirizzi della rete virtuale. Consultare il proprio reparto IT per determinare tale spazio di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="af162-p103">The address space for the virtual network. Work with your IT department to determine this address space.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-137">5.</span><span class="sxs-lookup"><span data-stu-id="af162-137">5.</span></span>  <br/> |<span data-ttu-id="af162-138">Chiave condivisa IPsec</span><span class="sxs-lookup"><span data-stu-id="af162-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="af162-p104">Una stringa con 32 caratteri alfanumerici casuali che verrà utilizzata per autenticare entrambi i lati della connessione VPN da sito a sito. Consultare il reparto IT o della sicurezza per determinare tale valore chiave. In alternativa, vedere [Creare una stringa casuale per una chiave già condivisa IPsec ](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span><span class="sxs-lookup"><span data-stu-id="af162-p104">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="af162-143">**Tabella V: configurazione di una rete virtuale cross-premise**</span><span class="sxs-lookup"><span data-stu-id="af162-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="af162-p105">Successivamente, compilare la tabella S per le subnet della soluzione. Tutti gli spazi di indirizzi devono essere in formato CIDR (Classless Interdomain Routing), noto anche come formato del prefisso di rete. Ad esempio, 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="af162-p105">Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="af162-p106">Per le prime tre subnet, specificare un nome e un singolo spazio di indirizzi IP in base allo spazio di indirizzi di rete virtuale. Per la prima subnet del gateway, determinare lo spazio di indirizzi a 27 bit (con una lunghezza del prefisso di /27) per la subnet del gateway di Azure con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="af162-p106">For the first three subnets, specify a name and a single IP address space based on the virtual network address space. For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="af162-149">Impostare i bit variabili nello spazio di indirizzi della VNet su 1, fino ai bit utilizzati dalla subnet del gateway, quindi impostare i bit rimanenti su 0.</span><span class="sxs-lookup"><span data-stu-id="af162-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="af162-150">Convertire i bit risultanti in formato decimale ed esprimerli come spazio di indirizzi con la lunghezza del prefisso impostata sulle dimensioni della subnet del gateway.</span><span class="sxs-lookup"><span data-stu-id="af162-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="af162-151">Per un blocco di comandi di PowerShell e un'applicazione console C# o Python che esegua questo calcolo per l'utente, vedere [Address Space Calculator for Azure gateway Subnets](address-space-calculator-for-azure-gateway-subnets.md) .</span><span class="sxs-lookup"><span data-stu-id="af162-151">See [Address space calculator for Azure gateway subnets](address-space-calculator-for-azure-gateway-subnets.md) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="af162-152">Consultare il reparto IT per determinare tali spazi di indirizzi in base allo spazio di indirizzi della rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="af162-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="af162-153">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-153">**Item**</span></span>|<span data-ttu-id="af162-154">**Nome della subnet**</span><span class="sxs-lookup"><span data-stu-id="af162-154">**Subnet name**</span></span>|<span data-ttu-id="af162-155">**Spazio di indirizzi della subnet**</span><span class="sxs-lookup"><span data-stu-id="af162-155">**Subnet address space**</span></span>|<span data-ttu-id="af162-156">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="af162-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af162-157">1.</span><span class="sxs-lookup"><span data-stu-id="af162-157">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-160">La subnet utilizzata dal controller di dominio di servizi di dominio Active Directory (AD DS) e dalle macchine virtuali del server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="af162-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="af162-161">2.</span><span class="sxs-lookup"><span data-stu-id="af162-161">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-164">La subnet utilizzata dalle macchine virtuali di AD FS.</span><span class="sxs-lookup"><span data-stu-id="af162-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="af162-165">3.</span><span class="sxs-lookup"><span data-stu-id="af162-165">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-168">La subnet utilizzata dalle macchine virtuali del proxy di applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="af162-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="af162-169">4.</span><span class="sxs-lookup"><span data-stu-id="af162-169">4.</span></span>  <br/> |<span data-ttu-id="af162-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="af162-170">GatewaySubnet</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-172">La subnet utilizzata dalle macchine virtuali del gateway di Azure.</span><span class="sxs-lookup"><span data-stu-id="af162-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="af162-173">**Tabella S: subnet nella rete virtuale**</span><span class="sxs-lookup"><span data-stu-id="af162-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="af162-174">Successivamente, compilare la tabella I per gli indirizzi IP statici assegnati alle macchine virtuali e alle istanze del bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="af162-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="af162-175">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-175">**Item**</span></span>|<span data-ttu-id="af162-176">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="af162-176">**Purpose**</span></span>|<span data-ttu-id="af162-177">**Indirizzo IP sulla subnet**</span><span class="sxs-lookup"><span data-stu-id="af162-177">**IP address on the subnet**</span></span>|<span data-ttu-id="af162-178">**Valore**</span><span class="sxs-lookup"><span data-stu-id="af162-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af162-179">1.</span><span class="sxs-lookup"><span data-stu-id="af162-179">1.</span></span>  <br/> |<span data-ttu-id="af162-180">Indirizzo IP statico del primo controller di dominio</span><span class="sxs-lookup"><span data-stu-id="af162-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="af162-181">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-183">2.</span><span class="sxs-lookup"><span data-stu-id="af162-183">2.</span></span>  <br/> |<span data-ttu-id="af162-184">Indirizzo IP statico del secondo controller di dominio</span><span class="sxs-lookup"><span data-stu-id="af162-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="af162-185">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-187">3.</span><span class="sxs-lookup"><span data-stu-id="af162-187">3.</span></span>  <br/> |<span data-ttu-id="af162-188">Indirizzo IP statico del server di sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="af162-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="af162-189">Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S. </span><span class="sxs-lookup"><span data-stu-id="af162-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-191">4.</span><span class="sxs-lookup"><span data-stu-id="af162-191">4.</span></span>  <br/> |<span data-ttu-id="af162-192">Indirizzo IP statico del bilanciamento del carico interno per i server AD FS</span><span class="sxs-lookup"><span data-stu-id="af162-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="af162-193">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-195">5.</span><span class="sxs-lookup"><span data-stu-id="af162-195">5.</span></span>  <br/> |<span data-ttu-id="af162-196">Indirizzo IP statico del primo server AD FS</span><span class="sxs-lookup"><span data-stu-id="af162-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="af162-197">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-199">6.</span><span class="sxs-lookup"><span data-stu-id="af162-199">6.</span></span>  <br/> |<span data-ttu-id="af162-200">Indirizzo IP statico del secondo server AD FS</span><span class="sxs-lookup"><span data-stu-id="af162-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="af162-201">Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-203">7.</span><span class="sxs-lookup"><span data-stu-id="af162-203">7.</span></span>  <br/> |<span data-ttu-id="af162-204">Indirizzo IP statico del primo server proxy dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="af162-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="af162-205">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-207">8.</span><span class="sxs-lookup"><span data-stu-id="af162-207">8.</span></span>  <br/> |<span data-ttu-id="af162-208">Indirizzo IP statico del secondo server proxy dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="af162-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="af162-209">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="af162-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="af162-211">**Tabella I: Indirizzi IP statici nella rete virtuale**</span><span class="sxs-lookup"><span data-stu-id="af162-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="af162-212">Per due server DNS (Domain Name System) nella rete locale che si desidera utilizzare durante la configurazione iniziale dei controller di dominio nella rete virtuale, compilare la tabella D. Consultare il reparto IT per determinare questo elenco.</span><span class="sxs-lookup"><span data-stu-id="af162-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="af162-213">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-213">**Item**</span></span>|<span data-ttu-id="af162-214">**Nome descrittivo del server DNS**</span><span class="sxs-lookup"><span data-stu-id="af162-214">**DNS server friendly name**</span></span>|<span data-ttu-id="af162-215">**Indirizzo IP del server DNS**</span><span class="sxs-lookup"><span data-stu-id="af162-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af162-216">1.</span><span class="sxs-lookup"><span data-stu-id="af162-216">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-219">2.</span><span class="sxs-lookup"><span data-stu-id="af162-219">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="af162-222">**Tabella D: server DNS locali**</span><span class="sxs-lookup"><span data-stu-id="af162-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="af162-223">Per instradare i pacchetti dalla rete cross-premise alla rete dell'organizzazione tramite la connessione VPN da sito a sito, è necessario configurare la rete virtuale con una rete locale contenente un elenco degli spazi degli indirizzi (in notazione CIDR) per tutti i percorsi raggiungibili nella rete in locale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="af162-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="af162-224">L'elenco degli spazi di indirizzi che definiscono la rete locale deve essere univoco e non deve sovrapporsi con lo spazio di indirizzi utilizzato per altre reti virtuali o per altre reti locali.</span><span class="sxs-lookup"><span data-stu-id="af162-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="af162-p108">Per l'insieme degli spazi di indirizzi della rete locale, compilare la tabella L. Sono elencate tre voci vuote, ma sarà necessario aggiungerne altre. Consultare il proprio reparto IT per determinare questo elenco di spazi di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="af162-p108">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="af162-227">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-227">**Item**</span></span>|<span data-ttu-id="af162-228">**Spazio di indirizzi della rete locale**</span><span class="sxs-lookup"><span data-stu-id="af162-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af162-229">1.</span><span class="sxs-lookup"><span data-stu-id="af162-229">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-231">2.</span><span class="sxs-lookup"><span data-stu-id="af162-231">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-233">3.</span><span class="sxs-lookup"><span data-stu-id="af162-233">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="af162-235">**Tabella L: prefissi degli indirizzi per la rete locale**</span><span class="sxs-lookup"><span data-stu-id="af162-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="af162-236">Ora iniziamo a creare l'infrastruttura di Azure per ospitare l'autenticazione federata per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af162-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af162-237">[!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af162-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="af162-238">Vedere [Introduzione a PowerShell di Azure](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="af162-238">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="af162-239">Avviare un prompt dei comandi di Azure PowerShell e accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="af162-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="af162-240">Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa [cartella di lavoro di configurazione di Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="af162-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="af162-241">Ottenere il nome della sottoscrizione utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="af162-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="af162-242">Per le versioni precedenti di Azure PowerShell, utilizzare questo comando.</span><span class="sxs-lookup"><span data-stu-id="af162-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="af162-243">Impostare la sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="af162-243">Set your Azure subscription.</span></span> <span data-ttu-id="af162-244">Sostituire tutti gli elementi racchiusi tra virgolette, compresi i \< and > caratteri, con il nome corretto.</span><span class="sxs-lookup"><span data-stu-id="af162-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="af162-p111">Successivamente, creare i nuovi gruppi di risorse. Per determinare un set di nomi dei gruppi di risorse univoci, utilizzare questo comando per creare un elenco dei gruppi di risorse esistenti.</span><span class="sxs-lookup"><span data-stu-id="af162-p111">Next, create the new resource groups. To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="af162-247">Compilare la tabella seguente per il set di nomi dei gruppi di risorse univoci.</span><span class="sxs-lookup"><span data-stu-id="af162-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="af162-248">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-248">**Item**</span></span>|<span data-ttu-id="af162-249">**Nome dei gruppi di risorse**</span><span class="sxs-lookup"><span data-stu-id="af162-249">**Resource group name**</span></span>|<span data-ttu-id="af162-250">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="af162-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af162-251">1.</span><span class="sxs-lookup"><span data-stu-id="af162-251">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-253">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="af162-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="af162-254">2.</span><span class="sxs-lookup"><span data-stu-id="af162-254">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-256">Server AD FS</span><span class="sxs-lookup"><span data-stu-id="af162-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="af162-257">3.</span><span class="sxs-lookup"><span data-stu-id="af162-257">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-259">Server proxy di applicazione Web</span><span class="sxs-lookup"><span data-stu-id="af162-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="af162-260">4.</span><span class="sxs-lookup"><span data-stu-id="af162-260">4.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="af162-262">Elementi dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="af162-262">Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id="af162-263">**Tabella R: gruppi di risorse**</span><span class="sxs-lookup"><span data-stu-id="af162-263">**Table R: Resource groups**</span></span>
  
<span data-ttu-id="af162-264">Creare i nuovi gruppi di risorse con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="af162-264">Create your new resource groups with these commands.</span></span>
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="af162-265">Successivamente, creare la rete virtuale di Azure e le relative subnet.</span><span class="sxs-lookup"><span data-stu-id="af162-265">Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="af162-266">Successivamente, è possibile creare gruppi di sicurezza di rete per ogni subnet che dispone di macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="af162-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="af162-267">Per eseguire l'isolamento della subnet, è possibile aggiungere regole per i tipi specifici di traffico concesso o negato per il gruppo di sicurezza di rete di una subnet.</span><span class="sxs-lookup"><span data-stu-id="af162-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="af162-268">Successivamente, utilizzare questi comandi per creare i gateway per la connessione VPN da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="af162-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="af162-269">L'autenticazione federata di singoli utenti non fa affidamento ad alcuna risorsa locale.</span><span class="sxs-lookup"><span data-stu-id="af162-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="af162-270">Tuttavia, se la connessione VPN da sito a sito non è disponibile, i controller di dominio in rete virtuale non riceveranno aggiornamenti per gli account utente e i gruppi effettuati nei servizi di dominio Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="af162-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="af162-271">Per evitare che ciò accada, è possibile configurare la disponibilità elevata per la connessione VPN da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="af162-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="af162-272">Per maggiori informazioni, vedere [Connettività cross-premise e da rete virtuale a rete virtuale a disponibilità elevata](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="af162-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="af162-273">Successivamente, registrare l'indirizzo IPv4 pubblico del gateway VPN di Azure per la rete virtuale visualizzato con questo comando:</span><span class="sxs-lookup"><span data-stu-id="af162-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="af162-p114">Successivamente, configurare il dispositivo VPN locale per stabilire una connessione con il gateway VPN di Azure. Per ulteriori informazioni, vedere [Configurare il dispositivo VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="af162-p114">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="af162-276">Per configurare il dispositivo VPN locale, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="af162-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="af162-277">L'indirizzo IPv4 pubblico del gateway VPN di Azure.</span><span class="sxs-lookup"><span data-stu-id="af162-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="af162-278">La chiave già condivisa IPsec per la connessione VPN da sito a sito (Tabella V- Elemento 5 - Colonna Valore).</span><span class="sxs-lookup"><span data-stu-id="af162-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="af162-p115">Successivamente, assicurarsi che lo spazio di indirizzi della rete virtuale sia raggiungibile dalla rete locale. In genere è possibile aggiungere una route corrispondente allo spazio di indirizzi di rete virtuali al dispositivo VPN e quindi distribuire tale route al resto dell'infrastruttura di routing della rete dell'organizzazione. A tale scopo, consultare il proprio reparto IT.</span><span class="sxs-lookup"><span data-stu-id="af162-p115">Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="af162-p116">Successivamente, definire i nomi di tre set di disponibilità. Compilare la tabella A. </span><span class="sxs-lookup"><span data-stu-id="af162-p116">Next, define the names of three availability sets. Fill out Table A.</span></span> 
  
|<span data-ttu-id="af162-284">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af162-284">**Item**</span></span>|<span data-ttu-id="af162-285">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="af162-285">**Purpose**</span></span>|<span data-ttu-id="af162-286">**Nome set di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="af162-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af162-287">1.</span><span class="sxs-lookup"><span data-stu-id="af162-287">1.</span></span>  <br/> |<span data-ttu-id="af162-288">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="af162-288">Domain controllers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-290">2.</span><span class="sxs-lookup"><span data-stu-id="af162-290">2.</span></span>  <br/> |<span data-ttu-id="af162-291">Server AD FS</span><span class="sxs-lookup"><span data-stu-id="af162-291">AD FS servers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="af162-293">3.</span><span class="sxs-lookup"><span data-stu-id="af162-293">3.</span></span>  <br/> |<span data-ttu-id="af162-294">Server proxy di applicazione Web</span><span class="sxs-lookup"><span data-stu-id="af162-294">Web application proxy servers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="af162-296">**Tabella A: set di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="af162-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="af162-297">Questi nomi sono necessari quando si creano le macchine virtuali nelle fasi 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="af162-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="af162-298">Creare i nuovi set di disponibilità con questi comandi di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af162-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="af162-299">Questa è la configurazione risultante dal completamento corretto di questa fase.</span><span class="sxs-lookup"><span data-stu-id="af162-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="af162-300">**Fase 1: l'infrastruttura di Azure per l'autenticazione federata a disponibilità elevata per Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="af162-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fase 1 dell'autenticazione federata Microsoft 365 a disponibilità elevata in Azure con l'infrastruttura di Azure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="af162-302">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="af162-302">Next step</span></span>

<span data-ttu-id="af162-303">Utilizzare la [fase 2: configurare i controller di dominio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) per continuare con la configurazione di questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="af162-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af162-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af162-304">See Also</span></span>

[<span data-ttu-id="af162-305">Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="af162-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="af162-306">Identità federata per l'ambiente di sviluppo/test di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af162-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="af162-307">Microsoft 365 Solution and Architecture Center</span><span class="sxs-lookup"><span data-stu-id="af162-307">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="af162-308">Informazioni su Microsoft 365 Identity e Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="af162-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)


