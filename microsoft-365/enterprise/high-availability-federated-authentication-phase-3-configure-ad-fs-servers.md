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
ms.openlocfilehash: bf8b52f4cd0dead0c264b71363fd5248397ae88d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691568"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Fase 3 dell'autenticazione federata a disponibilità elevata: configurare i server AD FS

In questa fase di distribuzione della disponibilità elevata per l'autenticazione federata di Microsoft 365 nei servizi dell'infrastruttura di Azure, viene creato un servizio di bilanciamento del carico interno e due server AD FS.
  
È necessario completare questa fase prima di passare alla [fase 4: configurare i proxy dell'applicazione Web.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) Vedere [Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) per tutte le fasi.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>Creare le macchine virtuali dei server AD FS in Azure

Utilizzare il seguente blocco di comandi di PowerShell per creare le macchine virtuali per i due server AD FS. Il set di comandi di PowerShell utilizza i valori indicati nelle tabelle riportate di seguito:
  
- Tabella M, per le macchine virtuali
    
- Tabella R, per i gruppi di risorse
    
- Tabella V, per le impostazioni della rete virtuale
    
- Tabella S, per le subnet
    
- Tabella I, per gli indirizzi IP statici
    
- Tabella A, per i set di disponibilità
    
Tenere presente che la tabella M è stata definita nella fase [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Configurare i controller di dominio e le tabelle R, V, S, I e A nella fase [1: configurare Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Introduzione ad Azure PowerShell.](https://docs.microsoft.com/powershell/azure/get-started-azureps) 
  
Per prima cosa, creare un bilanciamento del carico interno di Azure per i due server AD FS. Specificare i valori per le variabili, rimuovendo i \< and > caratteri. Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.
  
> [!TIP]
> Per generare blocchi di comandi di PowerShell pronti all'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di lavoro di configurazione [di Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

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

Successivamente, creare le macchine virtuali dei server AD FS.
  
Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.
  
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
> Poiché queste macchine virtuali sono per un'applicazione Intranet, non sono assegnate a un indirizzo IP pubblico o a un'etichetta del nome di dominio DNS ed esposte a Internet. Tuttavia, ciò significa anche che non è possibile connettersi a tali macchine virtuali dal portale di Azure. L'opzione **Connetti** non è disponibile quando si visualizzano le proprietà della macchina virtuale. Usare l'accessorio Connessione desktop remoto o un altro strumento Desktop remoto per connettersi alla macchina virtuale usando il relativo indirizzo IP privato o il nome DNS Intranet.
  
Per ogni macchina virtuale, usare il client desktop remoto di propria scelta e creare una connessione desktop remoto. Usare il nome DNS Intranet o il nome computer e le credenziali dell'account di amministratore locale.
  
Per ogni macchina virtuale, unirli al dominio di Active Directory Domain Services (AD DS) appropriato con questi comandi al prompt dei Windows PowerShell.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Di seguito è riportata la configurazione risultante dal completamento corretto di questa fase, con i nomi computer segnaposto.
  
**Fase 3: i server AD FS e il bilanciamento del carico interno per l'infrastruttura dell'autenticazione federata a disponibilità elevata in Azure**

![Fase 3 dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure con i server AD FS](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Passaggio successivo

Utilizzare [la fase 4: configurare i proxy delle applicazioni Web](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) per continuare a configurare questo carico di lavoro.
  
## <a name="see-also"></a>Vedere anche

[Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identità federata per l'ambiente di sviluppo/test di Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)


