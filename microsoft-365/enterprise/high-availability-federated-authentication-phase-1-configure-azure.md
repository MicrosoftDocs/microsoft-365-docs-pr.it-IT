---
title: Fase 1 dell'autenticazione federata a disponibilità elevata Configurare Azure
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
ms.openlocfilehash: 7f9a935648fedd2c6235c443f7398f97c0a06e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929109"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="cf315-103">Fase 1 dell'autenticazione federata a disponibilità elevata: configurare Azure</span><span class="sxs-lookup"><span data-stu-id="cf315-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="cf315-104">In questa fase vengono creati i gruppi di risorse, la rete virtuale (VNet) e i set di disponibilità in Azure che ospiteranno le macchine virtuali nelle fasi 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="cf315-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="cf315-105">È necessario completare questa fase prima di passare a [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="cf315-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="cf315-106">Per [tutte le fasi, vedere Deploy high availability federated authentication for Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="cf315-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="cf315-107">È necessario eseguire il provisioning di Azure con questi componenti di base:</span><span class="sxs-lookup"><span data-stu-id="cf315-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="cf315-108">Gruppi di risorse</span><span class="sxs-lookup"><span data-stu-id="cf315-108">Resource groups</span></span>
    
- <span data-ttu-id="cf315-109">Una rete virtuale (VNet) Azure cross-premise con subnet per ospitare le macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="cf315-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="cf315-110">Gruppi di sicurezza di rete per l'esecuzione dell'isolamento delle subnet</span><span class="sxs-lookup"><span data-stu-id="cf315-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="cf315-111">Set di disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf315-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="cf315-112">Configurare i componenti di Azure</span><span class="sxs-lookup"><span data-stu-id="cf315-112">Configure Azure components</span></span>

<span data-ttu-id="cf315-113">Prima di iniziare la configurazione dei componenti di Azure, compilare le tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf315-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="cf315-114">Per facilitare le procedure per la configurazione di Azure, stampare questa sezione e annotare le informazioni necessarie o copiare questa sezione in un documento e compilarla.</span><span class="sxs-lookup"><span data-stu-id="cf315-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="cf315-115">Per le impostazioni della VNet, compilare la tabella V.</span><span class="sxs-lookup"><span data-stu-id="cf315-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="cf315-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-116">**Item**</span></span>|<span data-ttu-id="cf315-117">**Impostazione di configurazione**</span><span class="sxs-lookup"><span data-stu-id="cf315-117">**Configuration setting**</span></span>|<span data-ttu-id="cf315-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cf315-118">**Description**</span></span>|<span data-ttu-id="cf315-119">**Valore**</span><span class="sxs-lookup"><span data-stu-id="cf315-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf315-120">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-120">1.</span></span>  <br/> |<span data-ttu-id="cf315-121">Nome VNet</span><span class="sxs-lookup"><span data-stu-id="cf315-121">VNet name</span></span>  <br/> |<span data-ttu-id="cf315-122">Un nome da assegnare alla VNet (ad esempio, FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="cf315-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-124">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-124">2.</span></span>  <br/> |<span data-ttu-id="cf315-125">Percorso VNet</span><span class="sxs-lookup"><span data-stu-id="cf315-125">VNet location</span></span>  <br/> |<span data-ttu-id="cf315-126">Data center di Azure regionale che conterrà la rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="cf315-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-128">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-128">3.</span></span>  <br/> |<span data-ttu-id="cf315-129">Indirizzo IP del dispositivo VPN</span><span class="sxs-lookup"><span data-stu-id="cf315-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="cf315-130">L'indirizzo IPv4 pubblico dell'interfaccia del dispositivo VPN su Internet.</span><span class="sxs-lookup"><span data-stu-id="cf315-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-132">4.</span><span class="sxs-lookup"><span data-stu-id="cf315-132">4.</span></span>  <br/> |<span data-ttu-id="cf315-133">Spazio di indirizzi della VNet</span><span class="sxs-lookup"><span data-stu-id="cf315-133">VNet address space</span></span>  <br/> |<span data-ttu-id="cf315-p103">Lo spazio di indirizzi della rete virtuale. Consultare il proprio reparto IT per determinare tale spazio di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="cf315-p103">The address space for the virtual network. Work with your IT department to determine this address space.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-137">5.</span><span class="sxs-lookup"><span data-stu-id="cf315-137">5.</span></span>  <br/> |<span data-ttu-id="cf315-138">Chiave condivisa IPsec</span><span class="sxs-lookup"><span data-stu-id="cf315-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="cf315-p104">Una stringa con 32 caratteri alfanumerici casuali che verrà utilizzata per autenticare entrambi i lati della connessione VPN da sito a sito. Consultare il reparto IT o della sicurezza per determinare tale valore chiave. In alternativa, vedere [Creare una stringa casuale per una chiave già condivisa IPsec ](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span><span class="sxs-lookup"><span data-stu-id="cf315-p104">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="cf315-143">**Tabella V: configurazione di una rete virtuale cross-premise**</span><span class="sxs-lookup"><span data-stu-id="cf315-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="cf315-p105">Successivamente, compilare la tabella S per le subnet della soluzione. Tutti gli spazi di indirizzi devono essere in formato CIDR (Classless Interdomain Routing), noto anche come formato del prefisso di rete. Ad esempio, 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="cf315-p105">Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="cf315-p106">Per le prime tre subnet, specificare un nome e un singolo spazio di indirizzi IP in base allo spazio di indirizzi di rete virtuale. Per la prima subnet del gateway, determinare lo spazio di indirizzi a 27 bit (con una lunghezza del prefisso di /27) per la subnet del gateway di Azure con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf315-p106">For the first three subnets, specify a name and a single IP address space based on the virtual network address space. For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="cf315-149">Impostare i bit variabili nello spazio di indirizzi della VNet su 1, fino ai bit utilizzati dalla subnet del gateway, quindi impostare i bit rimanenti su 0.</span><span class="sxs-lookup"><span data-stu-id="cf315-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="cf315-150">Convertire i bit risultanti in formato decimale ed esprimerli come spazio di indirizzi con la lunghezza del prefisso impostata sulle dimensioni della subnet del gateway.</span><span class="sxs-lookup"><span data-stu-id="cf315-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="cf315-151">Vedi [Strumento di calcolo dello spazio degli](address-space-calculator-for-azure-gateway-subnets.md) indirizzi per le subnet gateway di Azure per un blocco di comandi di PowerShell C# o un'applicazione console Python che esegue automaticamente questo calcolo.</span><span class="sxs-lookup"><span data-stu-id="cf315-151">See [Address space calculator for Azure gateway subnets](address-space-calculator-for-azure-gateway-subnets.md) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="cf315-152">Consultare il reparto IT per determinare tali spazi di indirizzi in base allo spazio di indirizzi della rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="cf315-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="cf315-153">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-153">**Item**</span></span>|<span data-ttu-id="cf315-154">**Nome della subnet**</span><span class="sxs-lookup"><span data-stu-id="cf315-154">**Subnet name**</span></span>|<span data-ttu-id="cf315-155">**Spazio di indirizzi della subnet**</span><span class="sxs-lookup"><span data-stu-id="cf315-155">**Subnet address space**</span></span>|<span data-ttu-id="cf315-156">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="cf315-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf315-157">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-157">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-160">Subnet utilizzata dal controller di dominio Servizi di dominio Active Directory e dalle macchine virtuali del server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="cf315-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="cf315-161">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-161">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-164">La subnet utilizzata dalle macchine virtuali di AD FS.</span><span class="sxs-lookup"><span data-stu-id="cf315-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="cf315-165">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-165">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-168">La subnet utilizzata dalle macchine virtuali del proxy di applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="cf315-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="cf315-169">4.</span><span class="sxs-lookup"><span data-stu-id="cf315-169">4.</span></span>  <br/> |<span data-ttu-id="cf315-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="cf315-170">GatewaySubnet</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-172">La subnet utilizzata dalle macchine virtuali del gateway di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf315-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="cf315-173">**Tabella S: subnet nella rete virtuale**</span><span class="sxs-lookup"><span data-stu-id="cf315-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="cf315-174">Successivamente, compilare la tabella I per gli indirizzi IP statici assegnati alle macchine virtuali e alle istanze del bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="cf315-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="cf315-175">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-175">**Item**</span></span>|<span data-ttu-id="cf315-176">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="cf315-176">**Purpose**</span></span>|<span data-ttu-id="cf315-177">**Indirizzo IP sulla subnet**</span><span class="sxs-lookup"><span data-stu-id="cf315-177">**IP address on the subnet**</span></span>|<span data-ttu-id="cf315-178">**Valore**</span><span class="sxs-lookup"><span data-stu-id="cf315-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf315-179">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-179">1.</span></span>  <br/> |<span data-ttu-id="cf315-180">Indirizzo IP statico del primo controller di dominio</span><span class="sxs-lookup"><span data-stu-id="cf315-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="cf315-181">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-183">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-183">2.</span></span>  <br/> |<span data-ttu-id="cf315-184">Indirizzo IP statico del secondo controller di dominio</span><span class="sxs-lookup"><span data-stu-id="cf315-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="cf315-185">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-187">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-187">3.</span></span>  <br/> |<span data-ttu-id="cf315-188">Indirizzo IP statico del server di sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="cf315-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="cf315-189">Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S. </span><span class="sxs-lookup"><span data-stu-id="cf315-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-191">4.</span><span class="sxs-lookup"><span data-stu-id="cf315-191">4.</span></span>  <br/> |<span data-ttu-id="cf315-192">Indirizzo IP statico del bilanciamento del carico interno per i server AD FS</span><span class="sxs-lookup"><span data-stu-id="cf315-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="cf315-193">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-195">5.</span><span class="sxs-lookup"><span data-stu-id="cf315-195">5.</span></span>  <br/> |<span data-ttu-id="cf315-196">Indirizzo IP statico del primo server AD FS</span><span class="sxs-lookup"><span data-stu-id="cf315-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="cf315-197">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-199">6.</span><span class="sxs-lookup"><span data-stu-id="cf315-199">6.</span></span>  <br/> |<span data-ttu-id="cf315-200">Indirizzo IP statico del secondo server AD FS</span><span class="sxs-lookup"><span data-stu-id="cf315-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="cf315-201">Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-203">7.</span><span class="sxs-lookup"><span data-stu-id="cf315-203">7.</span></span>  <br/> |<span data-ttu-id="cf315-204">Indirizzo IP statico del primo server proxy dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="cf315-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="cf315-205">Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-207">8.</span><span class="sxs-lookup"><span data-stu-id="cf315-207">8.</span></span>  <br/> |<span data-ttu-id="cf315-208">Indirizzo IP statico del secondo server proxy dell'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="cf315-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="cf315-209">Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.</span><span class="sxs-lookup"><span data-stu-id="cf315-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="cf315-211">**Tabella I: Indirizzi IP statici nella rete virtuale**</span><span class="sxs-lookup"><span data-stu-id="cf315-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="cf315-212">Per due server DNS (Domain Name System) nella rete locale che si desidera utilizzare durante la configurazione iniziale dei controller di dominio nella rete virtuale, compilare la tabella D. Consultare il reparto IT per determinare questo elenco.</span><span class="sxs-lookup"><span data-stu-id="cf315-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="cf315-213">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-213">**Item**</span></span>|<span data-ttu-id="cf315-214">**Nome descrittivo del server DNS**</span><span class="sxs-lookup"><span data-stu-id="cf315-214">**DNS server friendly name**</span></span>|<span data-ttu-id="cf315-215">**Indirizzo IP del server DNS**</span><span class="sxs-lookup"><span data-stu-id="cf315-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf315-216">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-216">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-219">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-219">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="cf315-222">**Tabella D: server DNS locali**</span><span class="sxs-lookup"><span data-stu-id="cf315-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="cf315-223">Per instradare i pacchetti dalla rete cross-premise alla rete dell'organizzazione attraverso la connessione VPN da sito a sito, è necessario configurare la rete virtuale con una rete locale con un elenco degli spazi indirizzo (in notazione CIDR) per tutte le posizioni raggiungibili nella rete locale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf315-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="cf315-224">L'elenco degli spazi di indirizzi che definiscono la rete locale deve essere univoco e non deve sovrapporsi con lo spazio di indirizzi utilizzato per altre reti virtuali o per altre reti locali.</span><span class="sxs-lookup"><span data-stu-id="cf315-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="cf315-p108">Per l'insieme degli spazi di indirizzi della rete locale, compilare la tabella L. Sono elencate tre voci vuote, ma sarà necessario aggiungerne altre. Consultare il proprio reparto IT per determinare questo elenco di spazi di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="cf315-p108">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="cf315-227">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-227">**Item**</span></span>|<span data-ttu-id="cf315-228">**Spazio di indirizzi della rete locale**</span><span class="sxs-lookup"><span data-stu-id="cf315-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf315-229">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-229">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-231">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-231">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-233">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-233">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="cf315-235">**Tabella L: prefissi degli indirizzi per la rete locale**</span><span class="sxs-lookup"><span data-stu-id="cf315-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="cf315-236">Iniziamo ora a creare l'infrastruttura di Azure per ospitare l'autenticazione federata per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf315-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf315-237">[!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf315-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="cf315-238">Vedi [Introduzione a Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="cf315-238">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="cf315-239">Avviare un prompt dei comandi di Azure PowerShell e accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="cf315-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="cf315-240">Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di [Microsoft Excel di configurazione.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="cf315-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="cf315-241">Ottenere il nome della sottoscrizione utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="cf315-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="cf315-242">Per le versioni precedenti di Azure PowerShell, usa invece questo comando.</span><span class="sxs-lookup"><span data-stu-id="cf315-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="cf315-p110">Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< and >, con il nome corretto.</span><span class="sxs-lookup"><span data-stu-id="cf315-p110">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="cf315-p111">Successivamente, creare i nuovi gruppi di risorse. Per determinare un set di nomi dei gruppi di risorse univoci, utilizzare questo comando per creare un elenco dei gruppi di risorse esistenti.</span><span class="sxs-lookup"><span data-stu-id="cf315-p111">Next, create the new resource groups. To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="cf315-247">Compilare la tabella seguente per il set di nomi dei gruppi di risorse univoci.</span><span class="sxs-lookup"><span data-stu-id="cf315-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="cf315-248">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-248">**Item**</span></span>|<span data-ttu-id="cf315-249">**Nome dei gruppi di risorse**</span><span class="sxs-lookup"><span data-stu-id="cf315-249">**Resource group name**</span></span>|<span data-ttu-id="cf315-250">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="cf315-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf315-251">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-251">1.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-253">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="cf315-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="cf315-254">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-254">2.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-256">Server AD FS</span><span class="sxs-lookup"><span data-stu-id="cf315-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="cf315-257">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-257">3.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-259">Server proxy di applicazione Web</span><span class="sxs-lookup"><span data-stu-id="cf315-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="cf315-260">4.</span><span class="sxs-lookup"><span data-stu-id="cf315-260">4.</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="cf315-262&quot;>Elementi dell'infrastruttura</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cf315-262&quot;>Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id=&quot;cf315-263&quot;>**Tabella R: gruppi di risorse**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cf315-263&quot;>**Table R: Resource groups**</span></span>
  
<span data-ttu-id=&quot;cf315-264&quot;>Creare i nuovi gruppi di risorse con questi comandi.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cf315-264&quot;>Create your new resource groups with these commands.</span></span>
  
```powershell
$locName=&quot;<an Azure location, such as West US>&quot;
$rgName=&quot;<Table R - Item 1 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 2 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 3 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 4 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id=&quot;cf315-265&quot;>Successivamente, creare la rete virtuale di Azure e le relative subnet.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cf315-265&quot;>Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName=&quot;<Table R - Item 4 - Resource group name column>&quot;
$locName=&quot;<your Azure location>&quot;
$vnetName=&quot;<Table V - Item 1 - Value column>&quot;
$vnetAddrPrefix=&quot;<Table V - Item 4 - Value column>&quot;
$dnsServers=@( &quot;<Table D - Item 1 - DNS server IP address column>&quot;, &quot;<Table D - Item 2 - DNS server IP address column>" )
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

<span data-ttu-id="cf315-266">Successivamente, creare gruppi di sicurezza di rete per ogni subnet con macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="cf315-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="cf315-267">Per eseguire l'isolamento della subnet, è possibile aggiungere regole per i tipi specifici di traffico concesso o negato per il gruppo di sicurezza di rete di una subnet.</span><span class="sxs-lookup"><span data-stu-id="cf315-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
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

<span data-ttu-id="cf315-268">Successivamente, utilizzare questi comandi per creare i gateway per la connessione VPN da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="cf315-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
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
> <span data-ttu-id="cf315-269">L'autenticazione federata di singoli utenti non fa affidamento ad alcuna risorsa locale.</span><span class="sxs-lookup"><span data-stu-id="cf315-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="cf315-270">Tuttavia, se questa connessione VPN da sito a sito non è più disponibile, i controller di dominio nella rete virtuale non riceveranno aggiornamenti per gli account utente e i gruppi effettuati in Servizi di dominio Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="cf315-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="cf315-271">Per assicurarsi che ciò non avvenga, è possibile configurare la disponibilità elevata per la connessione VPN da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="cf315-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="cf315-272">Per maggiori informazioni, vedere [Connettività cross-premise e da rete virtuale a rete virtuale a disponibilità elevata](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="cf315-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="cf315-273">Successivamente, registrare l'indirizzo IPv4 pubblico del gateway VPN di Azure per la rete virtuale visualizzato con questo comando:</span><span class="sxs-lookup"><span data-stu-id="cf315-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="cf315-p114">Successivamente, configurare il dispositivo VPN locale per stabilire una connessione con il gateway VPN di Azure. Per ulteriori informazioni, vedere [Configurare il dispositivo VPN](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="cf315-p114">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="cf315-276">Per configurare il dispositivo VPN locale, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf315-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="cf315-277">L'indirizzo IPv4 pubblico del gateway VPN di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf315-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="cf315-278">La chiave già condivisa IPsec per la connessione VPN da sito a sito (Tabella V- Elemento 5 - Colonna Valore).</span><span class="sxs-lookup"><span data-stu-id="cf315-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="cf315-p115">Successivamente, assicurarsi che lo spazio di indirizzi della rete virtuale sia raggiungibile dalla rete locale. In genere è possibile aggiungere una route corrispondente allo spazio di indirizzi di rete virtuali al dispositivo VPN e quindi distribuire tale route al resto dell'infrastruttura di routing della rete dell'organizzazione. A tale scopo, consultare il proprio reparto IT.</span><span class="sxs-lookup"><span data-stu-id="cf315-p115">Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="cf315-p116">Successivamente, definire i nomi di tre set di disponibilità. Compilare la tabella A. </span><span class="sxs-lookup"><span data-stu-id="cf315-p116">Next, define the names of three availability sets. Fill out Table A.</span></span> 
  
|<span data-ttu-id="cf315-284">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cf315-284">**Item**</span></span>|<span data-ttu-id="cf315-285">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="cf315-285">**Purpose**</span></span>|<span data-ttu-id="cf315-286">**Nome set di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="cf315-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf315-287">1.</span><span class="sxs-lookup"><span data-stu-id="cf315-287">1.</span></span>  <br/> |<span data-ttu-id="cf315-288">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="cf315-288">Domain controllers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-290">2.</span><span class="sxs-lookup"><span data-stu-id="cf315-290">2.</span></span>  <br/> |<span data-ttu-id="cf315-291">Server AD FS</span><span class="sxs-lookup"><span data-stu-id="cf315-291">AD FS servers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="cf315-293">3.</span><span class="sxs-lookup"><span data-stu-id="cf315-293">3.</span></span>  <br/> |<span data-ttu-id="cf315-294">Server proxy di applicazione Web</span><span class="sxs-lookup"><span data-stu-id="cf315-294">Web application proxy servers</span></span>  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="cf315-296">**Tabella A: set di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="cf315-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="cf315-297">Questi nomi sono necessari quando si creano le macchine virtuali nelle fasi 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="cf315-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="cf315-298">Creare i nuovi set di disponibilità con questi comandi di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf315-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
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

<span data-ttu-id="cf315-299">Questa è la configurazione risultante dal completamento corretto di questa fase.</span><span class="sxs-lookup"><span data-stu-id="cf315-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="cf315-300">**Fase 1: infrastruttura di Azure per l'autenticazione federata a disponibilità elevata per Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="cf315-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fase 1 dell'autenticazione federata Microsoft 365 a disponibilità elevata in Azure con l'infrastruttura di Azure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="cf315-302">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cf315-302">Next step</span></span>

<span data-ttu-id="cf315-303">Utilizzare [la fase 2: configurare i controller di](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) dominio per continuare con la configurazione di questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf315-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf315-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf315-304">See Also</span></span>

[<span data-ttu-id="cf315-305">Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="cf315-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="cf315-306">Identità federata per l'Microsoft 365 di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="cf315-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="cf315-307">Centro soluzioni e architetture di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf315-307">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="cf315-308">Informazioni Microsoft 365 identità e Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cf315-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)