---
title: Fase 4 dell'autenticazione federata a disponibilità elevata Configurare i proxy delle applicazioni Web
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
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: "Riepilogo: configurare i server proxy dell'applicazione Web per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Microsoft Azure."
ms.openlocfilehash: 95d73d05f2eef087e606df14db180b24c69d5932
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929073"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="fbc9d-103">Fase 4 dell'autenticazione federata a disponibilità elevata: configurare i proxy applicazione Web</span><span class="sxs-lookup"><span data-stu-id="fbc9d-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="fbc9d-104">In questa fase di distribuzione della disponibilità elevata per l'autenticazione federata di Microsoft 365 nei servizi infrastruttura di Azure, si crea un servizio di bilanciamento del carico interno e due server AD FS.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="fbc9d-105">È necessario completare questa fase prima di passare alla [fase 5: configurare l'autenticazione federata per Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="fbc9d-106">Per tutte le fasi, vedere Distribuire l'autenticazione federata a disponibilità elevata per [Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="fbc9d-107">Creare il bilanciatore di carico per traffico Internet in Azure</span><span class="sxs-lookup"><span data-stu-id="fbc9d-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="fbc9d-108">È necessario creare un bilanciatore di carico per traffico Internet affinché Azure distribuisca il traffico di autenticazione del client in arrivo da Internet uniformemente tra i due server proxy dell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbc9d-109">[!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="fbc9d-110">Vedere [Introduzione ad Azure PowerShell.](/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-110">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="fbc9d-111">Una volta forniti i valori per i gruppi di risorse e il percorso, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="fbc9d-112">Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di lavoro di configurazione [di Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="fbc9d-113">Per visualizzare l'indirizzo IP pubblico assegnato al bilanciatore di carico per traffico Internet, eseguire questi comandi nel prompt dei comandi di Azure PowerShell nel computer locale:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="fbc9d-114">Determinare il nome di dominio completo del servizio federativo e creare record DNS</span><span class="sxs-lookup"><span data-stu-id="fbc9d-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="fbc9d-115">È necessario determinare il nome DNS per identificare il nome del servizio federativo su Internet.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="fbc9d-116">Azure AD Connect configurerà Microsoft 365 con questo nome nella fase 5, che diventerà parte dell'URL inviato da Microsoft 365 ai client che si connettono per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="fbc9d-117">Un esempio è fs.contoso.com (dove fs è l'acronimo di federation service, cioè servizio federativo).</span><span class="sxs-lookup"><span data-stu-id="fbc9d-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="fbc9d-118">Una volta ottenuto il nome di dominio completo del servizio federativo, creare un record di tipo A del dominio DNS pubblico per il nome di dominio completo che consente di determinare l'indirizzo IP pubblico del bilanciatore di carico per traffico Internet di Azure.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="fbc9d-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-119">**Name**</span></span>|<span data-ttu-id="fbc9d-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-120">**Type**</span></span>|<span data-ttu-id="fbc9d-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-121">**TTL**</span></span>|<span data-ttu-id="fbc9d-122">**Valore**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbc9d-123">Nome di dominio completo del servizio federativo</span><span class="sxs-lookup"><span data-stu-id="fbc9d-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="fbc9d-124">A</span><span class="sxs-lookup"><span data-stu-id="fbc9d-124">A</span></span>  <br/> |<span data-ttu-id="fbc9d-125">3600</span><span class="sxs-lookup"><span data-stu-id="fbc9d-125">3600</span></span>  <br/> |<span data-ttu-id="fbc9d-126">Indirizzo IP pubblico del bilanciatore di carico per traffico Internet di Azure (visualizzato dal comando **Write-Host** nella sezione precedente)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="fbc9d-127">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-127">Here is an example:</span></span>
  
|<span data-ttu-id="fbc9d-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-128">**Name**</span></span>|<span data-ttu-id="fbc9d-129">**Type**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-129">**Type**</span></span>|<span data-ttu-id="fbc9d-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-130">**TTL**</span></span>|<span data-ttu-id="fbc9d-131">**Valore**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbc9d-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbc9d-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="fbc9d-133">A</span><span class="sxs-lookup"><span data-stu-id="fbc9d-133">A</span></span>  <br/> |<span data-ttu-id="fbc9d-134">3600</span><span class="sxs-lookup"><span data-stu-id="fbc9d-134">3600</span></span>  <br/> |<span data-ttu-id="fbc9d-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="fbc9d-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="fbc9d-136">Successivamente, aggiungere un record di indirizzo DNS allo spazio dei nomi DNS privato aziendale che consente di determinare il nome di dominio completo del servizio federativo per l'indirizzo IP privato assegnato al bilanciamento del carico interno per i server AD FS (tabella I, voce 4, colonna Valore).</span><span class="sxs-lookup"><span data-stu-id="fbc9d-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="fbc9d-137">Creare macchine virtuali per i server proxy delle applicazioni Web in Azure</span><span class="sxs-lookup"><span data-stu-id="fbc9d-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="fbc9d-138">Utilizzare il seguente blocco di comandi di Azure PowerShell per creare le macchine virtuali per i due server proxy delle applicazioni Web. </span><span class="sxs-lookup"><span data-stu-id="fbc9d-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="fbc9d-139">Si noti che i seguenti set di comandi di Azure PowerShell utilizzano i valori indicati nelle tabelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="fbc9d-140">Tabella M, per le macchine virtuali</span><span class="sxs-lookup"><span data-stu-id="fbc9d-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="fbc9d-141">Tabella R, per i gruppi di risorse</span><span class="sxs-lookup"><span data-stu-id="fbc9d-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="fbc9d-142">Tabella V, per le impostazioni della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="fbc9d-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="fbc9d-143">Tabella S, per le subnet</span><span class="sxs-lookup"><span data-stu-id="fbc9d-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="fbc9d-144">Tabella I, per gli indirizzi IP statici</span><span class="sxs-lookup"><span data-stu-id="fbc9d-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="fbc9d-145">Tabella A, per i set di disponibilità</span><span class="sxs-lookup"><span data-stu-id="fbc9d-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="fbc9d-146">Tenere presente che è stata definita la tabella M nella [fase 2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) configurare i controller di dominio e le tabelle R, V, S, I e A nella [fase 1: configurare Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="fbc9d-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="fbc9d-147">Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="fbc9d-p104">Poiché queste macchine virtuali sono per un'applicazione Intranet, non sono assegnate a un indirizzo IP pubblico o a un'etichetta del nome di dominio DNS ed esposte a Internet. Tuttavia, ciò significa anche che non è possibile connettersi a tali macchine virtuali dal portale di Azure. L'opzione **Connetti** non è disponibile quando si visualizzano le proprietà della macchina virtuale. Usare l'accessorio Connessione desktop remoto o un altro strumento Desktop remoto per connettersi alla macchina virtuale usando il relativo indirizzo IP privato o il nome DNS Intranet e le credenziali dell'account di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-p104">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="fbc9d-152">Di seguito è riportata la configurazione risultante dal completamento corretto di questa fase, con i nomi computer segnaposto.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="fbc9d-153">**Fase 4: il bilanciatore di carico per traffico Internet e i server proxy delle applicazioni Web per l'infrastruttura di autenticazione federata a disponibilità elevata in Azure**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 4 dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure con i server proxy dell'applicazione Web](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="fbc9d-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="fbc9d-155">Next step</span></span>

<span data-ttu-id="fbc9d-156">Utilizzare [la fase 5: configurare l'autenticazione federata per Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) per continuare a configurare questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fbc9d-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbc9d-157">See Also</span></span>

[<span data-ttu-id="fbc9d-158">Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="fbc9d-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="fbc9d-159">Identità federata per l'ambiente di sviluppo/test di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fbc9d-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="fbc9d-160">Centro soluzioni e architetture di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fbc9d-160">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)