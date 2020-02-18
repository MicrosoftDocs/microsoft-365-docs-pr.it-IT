---
title: Rete virtuale cross-premise simulata in un ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
description: 'Riepilogo: creare una rete virtuale cross-premise simulata in Microsoft Azure come ambiente di testing di Microsoft 365.'
ms.openlocfilehash: 52ba80d8613f44b252389da87891359eadae752a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084171"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="97a1d-103">Rete virtuale cross-premise simulata in un ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97a1d-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="97a1d-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="97a1d-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="97a1d-p101">In questo articolo viene mostrato come creare un ambiente basato su cloud con Microsoft Azure usando due reti virtuali Azure. Di seguito è riportata la configurazione risultante.  </span><span class="sxs-lookup"><span data-stu-id="97a1d-p101">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks. Here is the resulting configuration.</span></span> 
  
![Fase 3 dell'ambiente di testing della rete virtuale cross-premise simulata, con la macchina virtuale DC2 nella rete virtuale XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="97a1d-108">Questa simula un ambiente di produzione cloud ibrido in IaaS di Azure ed è costituita da:</span><span class="sxs-lookup"><span data-stu-id="97a1d-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="97a1d-109">Una rete locale simulata e semplificata, ospitata in una rete virtuale di Azure (la rete virtuale TestLab).</span><span class="sxs-lookup"><span data-stu-id="97a1d-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="97a1d-110">Una rete virtuale cross-premise simulata ospitata in Azure (XPrem).</span><span class="sxs-lookup"><span data-stu-id="97a1d-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="97a1d-111">Una relazione peering di rete virtuale tra le due reti virtuali.</span><span class="sxs-lookup"><span data-stu-id="97a1d-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="97a1d-112">Un controller di dominio secondario nella rete virtuale XPrem.</span><span class="sxs-lookup"><span data-stu-id="97a1d-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="97a1d-113">Tale configurazione fornisce una base e un punto di partenza comune da cui è possibile:</span><span class="sxs-lookup"><span data-stu-id="97a1d-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="97a1d-114">Sviluppare e testare applicazioni in un ambiente cloud ibrido simulato in IaaS di Azure.</span><span class="sxs-lookup"><span data-stu-id="97a1d-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="97a1d-115">Creare configurazioni di test dei computer, alcune all'interno della rete virtuale TestLab e alcune all'interno della rete virtuale XPrem, per simulare carichi di lavoro IT basati su cloud ibridi.</span><span class="sxs-lookup"><span data-stu-id="97a1d-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="97a1d-116">Le fasi principali della configurazione dell'ambiente di testing sono tre:</span><span class="sxs-lookup"><span data-stu-id="97a1d-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="97a1d-117">Configurare la rete virtuale TestLab.</span><span class="sxs-lookup"><span data-stu-id="97a1d-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="97a1d-118">Creare la rete virtuale cross-premise.</span><span class="sxs-lookup"><span data-stu-id="97a1d-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="97a1d-119">Configurare DC2.</span><span class="sxs-lookup"><span data-stu-id="97a1d-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97a1d-120">Questa configurazione richiede una sottoscrizione a pagamento di Azure.</span><span class="sxs-lookup"><span data-stu-id="97a1d-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="97a1d-121">È possibile utilizzare l'ambiente risultante per testare le funzionalità di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise), con altre [guide al lab di test](m365-enterprise-test-lab-guides.md) o quelle disponibili.</span><span class="sxs-lookup"><span data-stu-id="97a1d-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="97a1d-123">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="97a1d-123">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="97a1d-124">Fase 1: configurare la rete virtuale TestLab</span><span class="sxs-lookup"><span data-stu-id="97a1d-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="97a1d-125">Usare le istruzioni presenti nella **Fase 1** della [configurazione di base per l'organizzazione simulata](simulated-ent-base-configuration-microsoft-365-enterprise.md) per configurare i computer DC1, APP1 e CLIENT1 nella rete virtuale di Azure denominata TestLab.</span><span class="sxs-lookup"><span data-stu-id="97a1d-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="97a1d-126">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="97a1d-126">This is your current configuration.</span></span> 
  
![La configurazione di base per l'organizzazione simulata in Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="97a1d-128">Fase 2: creare la rete virtuale XPrem</span><span class="sxs-lookup"><span data-stu-id="97a1d-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="97a1d-129">In questa fase, viene creata e configurata la nuova rete virtuale XPrem, viene quindi eseguita la connessione alla rete virtuale TestLab con peering di rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="97a1d-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="97a1d-130">Innanzitutto, avviare un prompt dei comandi di Azure PowerShell sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="97a1d-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97a1d-p102">I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="97a1d-p102">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="97a1d-133">Accedere al proprio account di Azure con questo comando.</span><span class="sxs-lookup"><span data-stu-id="97a1d-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="97a1d-134">Ottenere il nome della sottoscrizione con questo comando.</span><span class="sxs-lookup"><span data-stu-id="97a1d-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="97a1d-p103">Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< e >, con il nome corretto.</span><span class="sxs-lookup"><span data-stu-id="97a1d-p103">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="97a1d-137">Successivamente, creare la rete virtuale XPrem e proteggerla con un gruppo di sicurezza di rete con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="97a1d-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="97a1d-138">Creare quindi la relazione peering di rete virtuale tra le reti virtuali TestLab e XPrem con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="97a1d-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="97a1d-139">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="97a1d-139">This is your current configuration.</span></span> 
  
![Fase 2 dell'ambiente di testing della rete virtuale cross-premise simulata, con la relazione di peering della rete virtuale e la rete virtuale XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="97a1d-141">Fase 3: configurare DC2</span><span class="sxs-lookup"><span data-stu-id="97a1d-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="97a1d-142">In questa fase, viene creata la macchina virtuale DC2 nella rete virtuale XPrem e viene configurata come controller di dominio di replica.</span><span class="sxs-lookup"><span data-stu-id="97a1d-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="97a1d-p104">Innanzitutto, creare una macchina virtuale per DC2. Eseguire questi comandi al prompt dei comandi di Azure PowerShell nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="97a1d-p104">First, create a virtual machine for DC2. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="97a1d-145">Successivamente, eseguire la connessione alla nuova macchina virtuale DC2 dal [portale Azure](https://portal.azure.com) tramite nome dell’account e password dell’amministratore locale. </span><span class="sxs-lookup"><span data-stu-id="97a1d-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="97a1d-p105">Configurare quindi una regola di Windows Firewall per consentire la verifica di connettività di base del traffico. Eseguire questi comandi in DC2 al prompt dei comandi di Windows PowerShell a livello di amministratore. </span><span class="sxs-lookup"><span data-stu-id="97a1d-p105">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing. From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="97a1d-p106">Il comando ping dovrebbe produrre quattro risposte dall'indirizzo IP 10.0.0.4. Si tratta di un test del traffico attraverso la relazione peering di rete virtuale. </span><span class="sxs-lookup"><span data-stu-id="97a1d-p106">The ping command should result in four successful replies from IP address 10.0.0.4. This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="97a1d-150">Successivamente, aggiungere un ulteriore disco dati come nuovo volume con lettera di unità F: con questo comando in DC2 al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97a1d-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="97a1d-p107">Configurare quindi DC2 come controller di dominio di replica per il dominio corp.contoso.com. Eseguire questi comandi dal prompt dei comandi di Windows PowerShell su DC2.</span><span class="sxs-lookup"><span data-stu-id="97a1d-p107">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain. Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="97a1d-153">Tenere presente che viene richiesto di fornire sia la password CORP\\User1 che una password per la modalità ripristino servizi directory, nonché di riavviare DC2. </span><span class="sxs-lookup"><span data-stu-id="97a1d-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="97a1d-p108">Ora che la rete virtuale XPrem dispone di un proprio server DNS (DC2), è necessario configurare la rete virtuale XPrem per utilizzarlo. Eseguire questi comandi nel computer locale al prompt dei comandi di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97a1d-p108">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server. Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="97a1d-p109">Utilizzare le credenziali CORP\\User1 per eseguire la connessione a DC1 dal portale di Azure sul computer locale. Per configurare il dominio CORP in modo che computer e utenti utilizzino il controller di dominio locale per l'autenticazione, eseguire questi comandi in DC1 al prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="97a1d-p109">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials. To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="97a1d-158">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="97a1d-158">This is your current configuration.</span></span> 
  
![Fase 3 dell'ambiente di testing della rete virtuale cross-premise simulata, con la macchina virtuale DC2 nella rete virtuale XPrem](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="97a1d-160">L’ambiente cloud ibrido di Azure simulato è ora pronto per eseguire test.</span><span class="sxs-lookup"><span data-stu-id="97a1d-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="97a1d-161">A questo punto è possibile sperimentare le funzionalità aggiuntive di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="97a1d-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="97a1d-162">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="97a1d-162">Next steps</span></span>

<span data-ttu-id="97a1d-163">Esplorare questi altri insiemi di guide al lab test:</span><span class="sxs-lookup"><span data-stu-id="97a1d-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="97a1d-164">Identità</span><span class="sxs-lookup"><span data-stu-id="97a1d-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="97a1d-165">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="97a1d-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="97a1d-166">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="97a1d-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="97a1d-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a1d-167">See also</span></span>

[<span data-ttu-id="97a1d-168">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="97a1d-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="97a1d-169">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="97a1d-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="97a1d-170">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="97a1d-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
