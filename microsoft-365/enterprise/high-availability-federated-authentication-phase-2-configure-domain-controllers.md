---
title: Fase 2 dell'autenticazione federata a disponibilità elevata Configurare i controller di dominio
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: "Riepilogo: configurare i controller di dominio e il server di sincronizzazione della directory per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Microsoft Azure."
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909811"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Fase 2 dell'autenticazione federata a disponibilità elevata: configurare i controller di dominio

In questa fase di distribuzione della disponibilità elevata per Microsoft 365'autenticazione federata nei servizi infrastruttura di Azure, si configurano due controller di dominio e il server di sincronizzazione della directory nella rete virtuale di Azure. Le richieste Web client per l'autenticazione possono quindi essere autenticate nella rete virtuale di Azure, anziché inviare tale traffico di autenticazione tramite la connessione VPN da sito a sito alla rete locale.
  
> [!NOTE]
> Active Directory Federation Services (AD FS) non può usare Azure Active Directory (Azure AD) in sostituzione dei controller di dominio di Servizi di dominio Active Directory. 
  
È necessario completare questa fase prima di passare alla [fase 3: configurare i server AD FS.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) Per [tutte le fasi, vedere Deploy high availability federated authentication for Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Creare le macchine virtuali dei controller di dominio in Azure

Per prima cosa, è necessario compilare la colonna **Nome macchina virtuale** della tabella M e modificare le dimensioni della macchina virtuale secondo necessità nella colonna **Dimensioni minime**.
  
|**Elemento**|**Nome macchina virtuale**|**Immagine della raccolta**|**Tipo di archiviazione**|**Dimensioni minime**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![riga](../media/Common-Images/TableLine.png) ______________ (primo controller di dominio, ad esempio DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![riga](../media/Common-Images/TableLine.png) ______________ (secondo controller di dominio, ad esempio DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![riga](../media/Common-Images/TableLine.png) (server di sincronizzazione della directory, esempio DS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![riga](../media/Common-Images/TableLine.png) (primo server AD FS, esempio ADFS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![riga](../media/Common-Images/TableLine.png) (secondo server AD FS, esempio ADFS2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![riga](../media/Common-Images/TableLine.png) (primo server proxy dell'applicazione Web, esempio WEB1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![riga](../media/Common-Images/TableLine.png) (secondo server proxy dell'applicazione Web, esempio WEB2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabella M - Macchine virtuali per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure**
  
Per l'elenco completo delle dimensioni delle macchine virtuali, vedere [Dimensioni delle macchine virtuali](/azure/virtual-machines/virtual-machines-windows-sizes).
  
Il seguente blocco di comandi di Azure PowerShell consente di creare le macchine virtuali per i due controller di dominio. Specificare i valori per le variabili, rimuovendo i \< and > caratteri. Si noti che il blocco di comandi di Azure PowerShell utilizza i valori indicati nelle tabelle riportate di seguito:
  
- Tabella M, per le macchine virtuali
    
- Tabella R, per i gruppi di risorse
    
- Tabella V, per le impostazioni della rete virtuale
    
- Tabella S, per le subnet
    
- Tabella I, per gli indirizzi IP statici
    
- Tabella A, per i set di disponibilità
    
Tenere presente che le tabelle R, V, S, I e A sono definite nella [fase 1: configurare Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedi [Introduzione a Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Una volta forniti tutti i valori corretti, eseguire il blocco risultante nel prompt di Azure PowerShell oppure in PowerShell Integrated Script Environment (ISE) nel computer locale.
  
> [!TIP]
> Per generare blocchi di comandi di PowerShell pronti per l'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di [Microsoft Excel di configurazione.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Poiché queste macchine virtuali sono per un'applicazione Intranet, non sono assegnate a un indirizzo IP pubblico o a un'etichetta del nome di dominio DNS ed esposte a Internet. Tuttavia, ciò significa anche che non è possibile connettersi a tali macchine virtuali dal portale di Azure. L'opzione **Connetti** non è disponibile quando si visualizzano le proprietà della macchina virtuale. Usare l'accessorio Connessione desktop remoto o un altro strumento Desktop remoto per connettersi alla macchina virtuale usando il relativo indirizzo IP privato o il nome DNS Intranet.
  
## <a name="configure-the-first-domain-controller"></a>Configurare il primo controller di dominio

Usare il client desktop remoto di propria scelta e creare una connessione desktop remoto per la macchina virtuale del primo controller di dominio. Usare il nome DNS Intranet o il nome computer e le credenziali dell'account di amministratore locale.
  
Successivamente, aggiungere il disco dati aggiuntivo al primo controller di dominio con questo comando da un prompt dei comandi di Windows PowerShell nella prima macchina virtuale **controller di dominio:**
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Successivamente, verificare la connettività del primo controller di dominio per i percorsi della rete aziendale tramite il comando **ping** per i nomi di ping e gli indirizzi IP delle risorse nella rete dell'organizzazione.
  
Questa procedura assicura che la risoluzione dei nomi DNS funziona correttamente (che la macchina virtuale è configurata correttamente con i server DNS locali) e che possono essere inviati pacchetti da e verso la rete virtuale cross-premise. Se il test ha esito negativo, contattare il proprio reparto IT per risolvere i problemi relativi alla risoluzione del nome DNS e al recapito dei pacchetti.
  
Successivamente, dal prompt dei comandi di Windows PowerShell nel primo controller di dominio, eseguire i comandi seguenti:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

Verrà richiesto di fornire le credenziali di un account di amministratore del dominio. Il computer viene riavviato.
  
## <a name="configure-the-second-domain-controller"></a>Configurare il secondo controller di dominio

Usare il client desktop remoto di propria scelta e creare una connessione desktop remoto per la macchina virtuale del secondo controller di dominio. Usare il nome DNS Intranet o il nome computer e le credenziali dell'account di amministratore locale.
  
Successivamente, è necessario aggiungere il disco dati aggiuntivo al secondo controller di dominio con questo comando da un prompt dei comandi di Windows PowerShell nella seconda macchina virtuale **controller di dominio:**
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Quindi, eseguire i seguenti comandi:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

Verrà richiesto di fornire le credenziali di un account di amministratore del dominio. Il computer viene riavviato.
  
Successivamente, è necessario aggiornare i server DNS per la rete virtuale in modo che Azure assegni le macchine virtuali agli indirizzi IP dei due nuovi controller di dominio da utilizzare come server DNS. Compilare le variabili ed eseguire questi comandi da un prompt Windows PowerShell nel computer locale:
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

Si noti che i due controller di dominio vengono riavviati in modo che non siano configurati con i server DNS locali come server DNS. Trattandosi di due server DNS, sono stati configurati automaticamente con i server DNS locali come server d'inoltro quando sono stati promossi a controller di dominio.
  
Successivamente, è necessario creare un sito di replica di Active Directory per assicurarsi che i server della rete virtuale di Azure utilizzino i controller di dominio locali. Connettersi a uno dei due controller di dominio con un account di amministratore di dominio ed eseguire i comandi seguenti dal prompt dei comandi di Windows PowerShell a livello di amministratore:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>Configurare il server di sincronizzazione della directory

Utilizzare il client desktop remoto desiderato e creare una connessione desktop remoto alla macchina virtuale del server di sincronizzazione della directory. Usare il nome DNS Intranet o il nome computer e le credenziali dell'account di amministratore locale.
  
Successivamente, aggiungerlo al dominio di Servizi di dominio Active Directory appropriato con questi comandi al prompt Windows PowerShell locale.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Di seguito è riportata la configurazione risultante dal completamento corretto di questa fase, con i nomi computer segnaposto.
  
**Fase 2: i controller di dominio e il server di sincronizzazione della directory per l'infrastruttura di autenticazione federata a disponibilità elevata in Azure**

![Fase 2 dell'infrastruttura di Microsoft 365 di autenticazione federata in Azure con controller di dominio](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Passaggio successivo

Utilizzare [La fase 3: configurare i server AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) per continuare a configurare questo carico di lavoro.
  
## <a name="see-also"></a>Vedere anche

[Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identità federata per l'Microsoft 365 di sviluppo/test](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro soluzioni e architetture di Microsoft 365](../solutions/index.yml)