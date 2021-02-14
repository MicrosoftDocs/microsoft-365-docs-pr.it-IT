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
description: "Riepilogo: configurare l'infrastruttura di Microsoft Azure per ospitare l'autenticazione federata a disponibilità elevata per Microsoft 365."
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332341"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Fase 1 dell'autenticazione federata a disponibilità elevata: configurare Azure

In questa fase vengono creati i gruppi di risorse, la rete virtuale (VNet) e i set di disponibilità in Azure che ospiteranno le macchine virtuali nelle fasi 2, 3 e 4. È necessario completare questa fase prima di passare a [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Vedere [Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) per tutte le fasi.
  
È necessario eseguire il provisioning di Azure con questi componenti di base:
  
- Gruppi di risorse
    
- Una rete virtuale (VNet) Azure cross-premise con subnet per ospitare le macchine virtuali di Azure
    
- Gruppi di sicurezza di rete per l'esecuzione dell'isolamento delle subnet
    
- Set di disponibilità
    
## <a name="configure-azure-components"></a>Configurare i componenti di Azure

Prima di iniziare la configurazione dei componenti di Azure, compilare le tabelle seguenti. Per facilitare le procedure per la configurazione di Azure, stampare questa sezione e annotare le informazioni necessarie o copiare questa sezione in un documento e compilarla. Per le impostazioni della VNet, compilare la tabella V.
  
|**Elemento**|**Impostazione di configurazione**|**Descrizione**|**Valore**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Nome VNet  <br/> |Un nome da assegnare alla VNet (ad esempio, FedAuthNet).  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Percorso VNet  <br/> |Data center di Azure regionale che conterrà la rete virtuale.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Indirizzo IP del dispositivo VPN  <br/> |L'indirizzo IPv4 pubblico dell'interfaccia del dispositivo VPN su Internet.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Spazio di indirizzi della VNet  <br/> |Lo spazio di indirizzi della rete virtuale. Consultare il proprio reparto IT per determinare tale spazio di indirizzi.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Chiave condivisa IPsec  <br/> |Una stringa con 32 caratteri alfanumerici casuali che verrà utilizzata per autenticare entrambi i lati della connessione VPN da sito a sito. Consultare il reparto IT o della sicurezza per determinare tale valore chiave. In alternativa, vedere [Creare una stringa casuale per una chiave già condivisa IPsec ](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabella V: configurazione di una rete virtuale cross-premise**
  
Successivamente, compilare la tabella S per le subnet della soluzione. Tutti gli spazi di indirizzi devono essere in formato CIDR (Classless Interdomain Routing), noto anche come formato del prefisso di rete. Ad esempio, 10.24.64.0/20.
  
Per le prime tre subnet, specificare un nome e un singolo spazio di indirizzi IP in base allo spazio di indirizzi di rete virtuale. Per la prima subnet del gateway, determinare lo spazio di indirizzi a 27 bit (con una lunghezza del prefisso di /27) per la subnet del gateway di Azure con quanto segue:
  
1. Impostare i bit variabili nello spazio di indirizzi della VNet su 1, fino ai bit utilizzati dalla subnet del gateway, quindi impostare i bit rimanenti su 0.
    
2. Convertire i bit risultanti in formato decimale ed esprimerli come spazio di indirizzi con la lunghezza del prefisso impostata sulle dimensioni della subnet del gateway.
    
Vedi [lo strumento di calcolo dello](address-space-calculator-for-azure-gateway-subnets.md) spazio degli indirizzi per le subnet del gateway di Azure per un blocco di comandi di PowerShell e un'applicazione console C# o Python che esegue automaticamente questo calcolo.
  
Consultare il reparto IT per determinare tali spazi di indirizzi in base allo spazio di indirizzi della rete virtuale.
  
|**Elemento**|**Nome della subnet**|**Spazio di indirizzi della subnet**|**Scopo**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |Subnet utilizzata dal controller di dominio di Servizi di dominio Active Directory e dalle macchine virtuali del server di sincronizzazione della directory.  <br/> |
|2.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |La subnet utilizzata dalle macchine virtuali di AD FS.  <br/> |
|3.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |La subnet utilizzata dalle macchine virtuali del proxy di applicazione Web.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |La subnet utilizzata dalle macchine virtuali del gateway di Azure.  <br/> |
   
 **Tabella S: subnet nella rete virtuale**
  
Successivamente, compilare la tabella I per gli indirizzi IP statici assegnati alle macchine virtuali e alle istanze del bilanciamento del carico.
  
|**Elemento**|**Scopo**|**Indirizzo IP sulla subnet**|**Valore**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Indirizzo IP statico del primo controller di dominio  <br/> |Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Indirizzo IP statico del secondo controller di dominio  <br/> |Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Indirizzo IP statico del server di sincronizzazione della directory  <br/> |Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 1 della tabella S.   <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Indirizzo IP statico del bilanciamento del carico interno per i server AD FS  <br/> |Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Indirizzo IP statico del primo server AD FS  <br/> |Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |Indirizzo IP statico del secondo server AD FS  <br/> |Il sesto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 2 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |Indirizzo IP statico del primo server proxy dell'applicazione Web  <br/> |Il quarto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |Indirizzo IP statico del secondo server proxy dell'applicazione Web  <br/> |Il quinto indirizzo IP possibile per lo spazio di indirizzi della subnet definito alla voce 3 della tabella S.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabella I: Indirizzi IP statici nella rete virtuale**
  
Per due server DNS (Domain Name System) nella rete locale che si desidera utilizzare durante la configurazione iniziale dei controller di dominio nella rete virtuale, compilare la tabella D. Consultare il reparto IT per determinare questo elenco.
  
|**Elemento**|**Nome descrittivo del server DNS**|**Indirizzo IP del server DNS**|
|:-----|:-----|:-----|
|1.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabella D: server DNS locali**
  
Per instradare i pacchetti dalla rete cross-premise alla rete dell'organizzazione attraverso la connessione VPN da sito a sito, è necessario configurare la rete virtuale con una rete locale con un elenco degli spazi indirizzo (in notazione CIDR) per tutte le posizioni raggiungibili nella rete locale dell'organizzazione. L'elenco degli spazi di indirizzi che definiscono la rete locale deve essere univoco e non deve sovrapporsi con lo spazio di indirizzi utilizzato per altre reti virtuali o per altre reti locali.
  
Per l'insieme degli spazi di indirizzi della rete locale, compilare la tabella L. Sono elencate tre voci vuote, ma sarà necessario aggiungerne altre. Consultare il proprio reparto IT per determinare questo elenco di spazi di indirizzi.
  
|**Elemento**|**Spazio di indirizzi della rete locale**|
|:-----|:-----|
|1.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabella L: prefissi degli indirizzi per la rete locale**
  
Ora iniziamo a creare l'infrastruttura di Azure per ospitare l'autenticazione federata per Microsoft 365.
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Introduzione ad Azure PowerShell.](https://docs.microsoft.com/powershell/azure/get-started-azureps) 
  
Avviare un prompt dei comandi di Azure PowerShell e accedere al proprio account.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Per generare blocchi di comandi di PowerShell pronti all'esecuzione in base alle impostazioni personalizzate, utilizzare questa cartella di lavoro di configurazione [di Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

Ottenere il nome della sottoscrizione utilizzando il comando seguente.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Per le versioni precedenti di Azure PowerShell, utilizzare questo comando.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, \< and > inclusi i caratteri, con il nome corretto.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Successivamente, creare i nuovi gruppi di risorse. Per determinare un set di nomi dei gruppi di risorse univoci, utilizzare questo comando per creare un elenco dei gruppi di risorse esistenti.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Compilare la tabella seguente per il set di nomi dei gruppi di risorse univoci.
  
|**Elemento**|**Nome dei gruppi di risorse**|**Scopo**|
|:-----|:-----|:-----|
|1.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |Controller di dominio  <br/> |
|2.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |Server AD FS  <br/> |
|3.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |Server proxy di applicazione Web  <br/> |
|4.  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |Elementi dell'infrastruttura  <br/> |
   
 **Tabella R: gruppi di risorse**
  
Creare i nuovi gruppi di risorse con questi comandi.
  
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

Successivamente, creare la rete virtuale di Azure e le relative subnet.
  
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

Successivamente, creare gruppi di sicurezza di rete per ogni subnet con macchine virtuali. Per eseguire l'isolamento della subnet, è possibile aggiungere regole per i tipi specifici di traffico concesso o negato per il gruppo di sicurezza di rete di una subnet.
  
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

Successivamente, utilizzare questi comandi per creare i gateway per la connessione VPN da sito a sito.
  
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
> L'autenticazione federata di singoli utenti non fa affidamento ad alcuna risorsa locale. Tuttavia, se questa connessione VPN da sito a sito non è più disponibile, i controller di dominio nella rete virtuale non riceveranno aggiornamenti per gli account utente e i gruppi effettuati in Servizi di dominio Active Directory locale. Per assicurarsi che ciò non avvenga, è possibile configurare la disponibilità elevata per la connessione VPN da sito a sito. Per maggiori informazioni, vedere [Connettività cross-premise e da rete virtuale a rete virtuale a disponibilità elevata](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
Successivamente, registrare l'indirizzo IPv4 pubblico del gateway VPN di Azure per la rete virtuale visualizzato con questo comando:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Successivamente, configurare il dispositivo VPN locale per stabilire una connessione con il gateway VPN di Azure. Per ulteriori informazioni, vedere [Configurare il dispositivo VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).
  
Per configurare il dispositivo VPN locale, è necessario quanto segue:
  
- L'indirizzo IPv4 pubblico del gateway VPN di Azure.
    
- La chiave già condivisa IPsec per la connessione VPN da sito a sito (Tabella V- Elemento 5 - Colonna Valore).
    
Successivamente, assicurarsi che lo spazio di indirizzi della rete virtuale sia raggiungibile dalla rete locale. In genere è possibile aggiungere una route corrispondente allo spazio di indirizzi di rete virtuali al dispositivo VPN e quindi distribuire tale route al resto dell'infrastruttura di routing della rete dell'organizzazione. A tale scopo, consultare il proprio reparto IT.
  
Successivamente, definire i nomi di tre set di disponibilità. Compilare la tabella A.  
  
|**Elemento**|**Scopo**|**Nome set di disponibilità**|
|:-----|:-----|:-----|
|1.  <br/> |Controller di dominio  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Server AD FS  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Server proxy di applicazione Web  <br/> |![riga](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabella A: set di disponibilità**
  
Questi nomi sono necessari quando si creano le macchine virtuali nelle fasi 2, 3 e 4.
  
Creare i nuovi set di disponibilità con questi comandi di Azure PowerShell.
  
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

Questa è la configurazione risultante dal completamento corretto di questa fase.
  
**Fase 1: Infrastruttura di Azure per l'autenticazione federata a disponibilità elevata per Microsoft 365**

![Fase 1 dell'autenticazione federata di Microsoft 365 a disponibilità elevata in Azure con l'infrastruttura di Azure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Passaggio successivo

Utilizzare [la fase 2: configurare i controller di](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) dominio per continuare con la configurazione di questo carico di lavoro.
  
## <a name="see-also"></a>Vedere anche

[Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identità federata per l'ambiente di sviluppo/test di Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 Solution and Architecture Center](../solutions/solution-architecture-center.md)

[Informazioni sull'identità di Microsoft 365 e Azure Active Directory](about-microsoft-365-identity.md)


