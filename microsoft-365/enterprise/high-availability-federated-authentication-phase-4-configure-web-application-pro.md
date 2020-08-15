---
title: Fase 4 dell'autenticazione federata a disponibilità elevata configurare i proxy dell'applicazione Web
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
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691339"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>Fase 4 dell'autenticazione federata a disponibilità elevata: configurare i proxy applicazione Web

In questa fase di distribuzione della disponibilità elevata per l'autenticazione federata di Microsoft 365 nei servizi di infrastruttura di Azure, è possibile creare un servizio di bilanciamento del carico interno e due server AD FS.
  
È necessario completare questa fase prima di passare alla [fase 5: configurare l'autenticazione federata per Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Vedere [deploy High Availability Federated Authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) per tutte le fasi.
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>Creare il bilanciatore di carico per traffico Internet in Azure

È necessario creare un bilanciatore di carico per traffico Internet affinché Azure distribuisca il traffico di autenticazione del client in arrivo da Internet uniformemente tra i due server proxy dell'applicazione Web.
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Introduzione a PowerShell di Azure](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Una volta forniti i valori per i gruppi di risorse e il percorso, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.
  
> [!TIP]
> Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa [cartella di lavoro di configurazione di Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

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

Per visualizzare l'indirizzo IP pubblico assegnato al bilanciatore di carico per traffico Internet, eseguire questi comandi nel prompt dei comandi di Azure PowerShell nel computer locale:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>Determinare il nome di dominio completo del servizio federativo e creare record DNS

È necessario determinare il nome DNS per identificare il nome del servizio federativo su Internet. Azure AD Connect configurerà Microsoft 365 con questo nome nella fase 5, che diventerà parte dell'URL inviato da Microsoft 365 alla connessione dei client per ottenere un token di sicurezza. Un esempio è fs.contoso.com (dove fs è l'acronimo di federation service, cioè servizio federativo).
  
Una volta ottenuto il nome di dominio completo del servizio federativo, creare un record di tipo A del dominio DNS pubblico per il nome di dominio completo che consente di determinare l'indirizzo IP pubblico del bilanciatore di carico per traffico Internet di Azure.
  
|**Nome**|**Type**|**TTL**|**Valore**|
|:-----|:-----|:-----|:-----|
|Nome di dominio completo del servizio federativo  <br/> |A  <br/> |3600  <br/> |Indirizzo IP pubblico del bilanciatore di carico per traffico Internet di Azure (visualizzato dal comando **Write-Host** nella sezione precedente) <br/> |
   
Ecco un esempio:
  
|**Nome**|**Type**|**TTL**|**Valore**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
Successivamente, aggiungere un record di indirizzo DNS allo spazio dei nomi DNS privato aziendale che consente di determinare il nome di dominio completo del servizio federativo per l'indirizzo IP privato assegnato al bilanciamento del carico interno per i server AD FS (tabella I, voce 4, colonna Valore).
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>Creare macchine virtuali per i server proxy delle applicazioni Web in Azure

Utilizzare il seguente blocco di comandi di Azure PowerShell per creare le macchine virtuali per i due server proxy delle applicazioni Web.  
  
Si noti che i seguenti set di comandi di Azure PowerShell utilizzano i valori indicati nelle tabelle riportate di seguito:
  
- Tabella M, per le macchine virtuali
    
- Tabella R, per i gruppi di risorse
    
- Tabella V, per le impostazioni della rete virtuale
    
- Tabella S, per le subnet
    
- Tabella I, per gli indirizzi IP statici
    
- Tabella A, per i set di disponibilità
    
Ricordare che è stata definita la tabella M nella [fase 2: configurare i controller di dominio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) e le tabelle R, V, S, i e a nella [fase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
Una volta forniti tutti i valori opportuni, eseguire il blocco risultante nel prompt dei comandi di Azure PowerShell o in PowerShell ISE.
  
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
> Poiché queste macchine virtuali sono per un'applicazione Intranet, non sono assegnate a un indirizzo IP pubblico o a un'etichetta del nome di dominio DNS ed esposte a Internet. Tuttavia, ciò significa anche che non è possibile connettersi a tali macchine virtuali dal portale di Azure. L'opzione **Connetti** non è disponibile quando si visualizzano le proprietà della macchina virtuale. Usare l'accessorio Connessione desktop remoto o un altro strumento Desktop remoto per connettersi alla macchina virtuale usando il relativo indirizzo IP privato o il nome DNS Intranet e le credenziali dell'account di amministratore locale.
  
Di seguito è riportata la configurazione risultante dal completamento corretto di questa fase, con i nomi computer segnaposto.
  
**Fase 4: il bilanciatore di carico per traffico Internet e i server proxy delle applicazioni Web per l'infrastruttura di autenticazione federata a disponibilità elevata in Azure**

![Fase 4 dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure con i server proxy dell'applicazione Web](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>Passaggio successivo

Utilizzare la [fase 5: configurare l'autenticazione federata per Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) per continuare a configurare il carico di lavoro.
  
## <a name="see-also"></a>Vedere anche

[Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identità federata per l'ambiente di sviluppo/test di Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 Solution and Architecture Center](../solutions/solution-architecture-center.md)

