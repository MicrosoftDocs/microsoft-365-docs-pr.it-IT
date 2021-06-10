---
title: Fase 3 dell'autenticazione federata a disponibilità elevata Configurare i server AD FS
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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Informazioni su come creare e configurare i server AD FS per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Microsoft Azure.
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909799"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a><span data-ttu-id="2cab6-103">Fase 3 dell'autenticazione federata a disponibilità elevata: configurare i server AD FS</span><span class="sxs-lookup"><span data-stu-id="2cab6-103">High availability federated authentication Phase 3: Configure AD FS servers</span></span>

<span data-ttu-id="2cab6-104">In questa fase di distribuzione della disponibilità elevata Microsoft 365'autenticazione federata nei servizi di infrastruttura di Azure, si crea un servizio di bilanciamento del carico interno e due server AD FS.</span><span class="sxs-lookup"><span data-stu-id="2cab6-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="2cab6-105">È necessario completare questa fase prima di passare alla [fase 4: configurare i proxy dell'applicazione Web.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)</span><span class="sxs-lookup"><span data-stu-id="2cab6-105">You must complete this phase before moving on to [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="2cab6-106">Per [tutte le fasi, vedere Deploy high availability federated authentication for Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="2cab6-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a><span data-ttu-id="2cab6-107">Creare le macchine virtuali dei server AD FS in Azure</span><span class="sxs-lookup"><span data-stu-id="2cab6-107">Create the AD FS server virtual machines in Azure</span></span>

<span data-ttu-id="2cab6-p102">Utilizzare il seguente blocco di comandi di PowerShell per creare le macchine virtuali per i due server AD FS. Il set di comandi di PowerShell utilizza i valori indicati nelle tabelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="2cab6-p102">Use the following block of PowerShell commands to create the virtual machines for the two AD FS servers. This PowerShell command set uses values from the following tables:</span></span>
  
- <span data-ttu-id="2cab6-110">Tabella M, per le macchine virtuali</span><span class="sxs-lookup"><span data-stu-id="2cab6-110">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="2cab6-111">Tabella R, per i gruppi di risorse</span><span class="sxs-lookup"><span data-stu-id="2cab6-111">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="2cab6-112">Tabella V, per le impostazioni della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="2cab6-112">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="2cab6-113">Tabella S, per le subnet</span><span class="sxs-lookup"><span data-stu-id="2cab6-113">Table S, for your subnets</span></span>
    
- <span data-ttu-id="2cab6-114">Tabella I, per gli indirizzi IP statici</span><span class="sxs-lookup"><span data-stu-id="2cab6-114">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="2cab6-115">Tabella A, per i set di disponibilità</span><span class="sxs-lookup"><span data-stu-id="2cab6-115">Table A, for your availability sets</span></span>
    
<span data-ttu-id="2cab6-116">Tenere presente che è stata definita la tabella M nella [fase 2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) configurare i controller di dominio e le tabelle R, V, S, I e A nella [fase 1: configurare Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="2cab6-116">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2cab6-117">[!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cab6-117">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2cab6-118">Vedi [Introduzione a Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="2cab6-118">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="2cab6-119">Per prima cosa, creare un bilanciamento del carico interno di Azure per i due server AD FS.</span><span class="sxs-lookup"><span data-stu-id="2cab6-119">First, you create an Azure internal load balancer for the two AD FS servers.</span></span> <span data-ttu-id="2cab6-120">Specificare i valori per le variabili, rimuovendo i \< and > caratteri.</span><span class="sxs-lookup"><span data-stu-id="2cab6-120">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="2cab6-121">Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="2cab6-121">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="2cab6-122">Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di [Microsoft Excel di configurazione.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="2cab6-122">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="2cab6-123">Successivamente, creare le macchine virtuali dei server AD FS.</span><span class="sxs-lookup"><span data-stu-id="2cab6-123">Next, create the AD FS server virtual machines.</span></span>
  
<span data-ttu-id="2cab6-124">Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="2cab6-124">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> <span data-ttu-id="2cab6-p105">Poiché queste macchine virtuali sono per un'applicazione Intranet, non sono assegnate a un indirizzo IP pubblico o a un'etichetta del nome di dominio DNS ed esposte a Internet. Tuttavia, ciò significa anche che non è possibile connettersi a tali macchine virtuali dal portale di Azure. L'opzione **Connetti** non è disponibile quando si visualizzano le proprietà della macchina virtuale. Usare l'accessorio Connessione desktop remoto o un altro strumento Desktop remoto per connettersi alla macchina virtuale usando il relativo indirizzo IP privato o il nome DNS Intranet.</span><span class="sxs-lookup"><span data-stu-id="2cab6-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
<span data-ttu-id="2cab6-p106">Per ogni macchina virtuale, usare il client desktop remoto di propria scelta e creare una connessione desktop remoto. Usare il nome DNS Intranet o il nome computer e le credenziali dell'account di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="2cab6-p106">For each virtual machine, use the remote desktop client of your choice and create a remote desktop connection. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="2cab6-131">Per ogni macchina virtuale, aggiungerli al dominio di Servizi di dominio Active Directory appropriato con questi comandi al prompt Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cab6-131">For each virtual machine, join them to the appropriate Active Directory Domain Services (AD DS) domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="2cab6-132">Di seguito è riportata la configurazione risultante dal completamento corretto di questa fase, con i nomi computer segnaposto.</span><span class="sxs-lookup"><span data-stu-id="2cab6-132">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="2cab6-133">**Fase 3: i server AD FS e il bilanciamento del carico interno per l'infrastruttura dell'autenticazione federata a disponibilità elevata in Azure**</span><span class="sxs-lookup"><span data-stu-id="2cab6-133">**Phase 3: The AD FS servers and internal load balancer for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 3 dell'infrastruttura di Microsoft 365 di autenticazione federata in Azure con i server AD FS](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a><span data-ttu-id="2cab6-135">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="2cab6-135">Next step</span></span>

<span data-ttu-id="2cab6-136">Utilizzare [La fase 4: configurare i proxy delle applicazioni Web](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) per continuare a configurare questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cab6-136">Use [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2cab6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cab6-137">See Also</span></span>

[<span data-ttu-id="2cab6-138">Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="2cab6-138">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="2cab6-139">Identità federata per l'Microsoft 365 di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="2cab6-139">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)