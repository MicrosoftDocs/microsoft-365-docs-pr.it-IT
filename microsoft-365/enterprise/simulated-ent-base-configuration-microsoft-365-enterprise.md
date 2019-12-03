---
title: Configurazione di base dell'organizzazione simulata per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Utilizzare questa guida al lab di test per creare un ambiente di testing dell'organizzazione simulata per Microsoft 365 Enterprise.
ms.openlocfilehash: febfa4e9ce3fdc430cf53a9cce61a15f0a4247fb
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662811"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="5da60-103">La configurazione di base per l'organizzazione simulata</span><span class="sxs-lookup"><span data-stu-id="5da60-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="5da60-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5da60-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5da60-105">In questo articolo vengono fornite istruzioni dettagliate per creare un ambiente semplificato per Microsoft 365 Enterprise che include:</span><span class="sxs-lookup"><span data-stu-id="5da60-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="5da60-106">Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5da60-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="5da60-107">Una intranet dell’organizzazione semplificata connessa a Internet e costituita da tre macchine virtuali in una rete virtuale Azure (DC1 APP1 e CLIENT1).</span><span class="sxs-lookup"><span data-stu-id="5da60-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![La configurazione di base per l'organizzazione simulata](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="5da60-109">È possibile utilizzare l'ambiente risultante per testare le funzionalità di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise), con altre [guide al lab di test](m365-enterprise-test-lab-guides.md) o quelle disponibili.</span><span class="sxs-lookup"><span data-stu-id="5da60-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5da60-111">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5da60-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="5da60-112">Fase 1: creare una rete intranet simulata</span><span class="sxs-lookup"><span data-stu-id="5da60-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="5da60-113">In questa fase, verrà creata una rete intranet simulata nei servizi di infrastruttura di Azure che include un controller di dominio di Active Directory Domain Services, un server applicazioni e un computer client.</span><span class="sxs-lookup"><span data-stu-id="5da60-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="5da60-114">Questi computer saranno usati nelle [Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) aggiuntive per configurare e dimostrare l'identità ibrida e altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5da60-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="5da60-115">Metodo 1: creare una rete intranet simulata con un modello di Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="5da60-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="5da60-p101">Con questo metodo si utilizza un modello Azure Resource Manager (ARM) per creare la rete intranet simulata. I modelli ARM contengono tutte le istruzioni per creare l’infrastruttura di rete Azure, le macchine virtuali e la loro configurazione.</span><span class="sxs-lookup"><span data-stu-id="5da60-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="5da60-118">Prima di distribuire il modello, consultare la [pagina Leggimi del modello](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) e avere a disposizione le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5da60-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="5da60-p102">Il nome di dominio DNS pubblico dell'ambiente di test (testlab.\< dominio pubblico>). È necessario immettere questo nome nel **campo nome di dominio** della pagina **Distribuzione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="5da60-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="5da60-p103">Un prefisso etichetta DNS per gli URL degli indirizzi IP pubblici delle macchine virtuali. È necessario immettere l'etichetta nel campo **Prefisso etichetta DNS** della pagina **Distribuzione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="5da60-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="5da60-123">Dopo aver letto con le istruzioni, fare clic su **Distribuisci in Azure** nella [pagina Leggimi del modello](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) per iniziare.</span><span class="sxs-lookup"><span data-stu-id="5da60-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="5da60-124">La rete intranet simulata creata dal modello ARM richiede una sottoscrizione a pagamento ad Azure.</span><span class="sxs-lookup"><span data-stu-id="5da60-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="5da60-125">Ecco la configurazione una volta completato il modello.</span><span class="sxs-lookup"><span data-stu-id="5da60-125">Here is your configuration after the template is complete.</span></span>

![La rete intranet simulata nei servizi infrastruttura di Azure.](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="5da60-127">Metodo 2: creare la rete intranet simulata con Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5da60-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="5da60-128">Con questo metodo si utilizza Windows PowerShell e il modulo di Azure PowerShell per creare l'infrastruttura di rete, le macchine virtuali e la loro configurazione.</span><span class="sxs-lookup"><span data-stu-id="5da60-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="5da60-p104">Utilizzare questo metodo per acquisire esperienza nella creazione di elementi dell'infrastruttura di Azure un passo alla volta con PowerShell. È quindi possibile personalizzare i blocchi di comandi di PowerShell per una distribuzione personalizzata delle altre macchine virtuali in Azure.</span><span class="sxs-lookup"><span data-stu-id="5da60-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="5da60-131">Passaggio 1: creare DC1</span><span class="sxs-lookup"><span data-stu-id="5da60-131">Step 1: Create DC1</span></span>

<span data-ttu-id="5da60-132">In questo passaggio viene creata una rete virtuale Azure e viene aggiunto DC1, una macchina virtuale che è un controller di dominio per un dominio di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="5da60-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="5da60-133">Innanzitutto, avviare un prompt dei comandi di Windows PowerShell sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="5da60-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5da60-p105">I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="5da60-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="5da60-136">Accedere al proprio account Azure con il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="5da60-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="5da60-137">Ottenere il nome della sottoscrizione utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="5da60-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="5da60-p106">Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri < e >, con il nome corretto.</span><span class="sxs-lookup"><span data-stu-id="5da60-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="5da60-p107">Successivamente, creare un nuovo gruppo di risorse per il lab di test dell'organizzazione simulata. Per determinare un nome del gruppo di risorse univoco, utilizzare questo comando per creare un elenco dei gruppi di risorse esistenti.</span><span class="sxs-lookup"><span data-stu-id="5da60-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="5da60-p108">Creare il nuovo gruppo di risorse con questi comandi. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri < e >, con i nomi corretti.</span><span class="sxs-lookup"><span data-stu-id="5da60-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="5da60-p109">Successivamente, creare la rete virtuale TestLa che ospiterà la sottorete Corpnet dell'ambiente dell'organizzazione simulata e proteggerla con un gruppo di sicurezza di rete. Inserire il nome del gruppo di risorse ed eseguire questi comandi al prompt dei comandi di PowerShell nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="5da60-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="5da60-146">Successivamente, creare la macchina virtuale DC1 e configurarla come controller di dominio per il dominio di AD DS **testlab.**\<dominio pubblico> e come server DNS per le macchine virtuali della rete virtuale TestLab.</span><span class="sxs-lookup"><span data-stu-id="5da60-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="5da60-147">Ad esempio, se il nome di dominio pubblico è **<span>contoso</span>.com**, la macchina virtuale DC1 sarà un controller di dominio per il dominio **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="5da60-147">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="5da60-148">Inserire il nome del gruppo di risorse ed eseguire questi comandi al prompt dei comandi di PowerShell nel computer locale per creare una macchina virtuale di Azure per DC1.</span><span class="sxs-lookup"><span data-stu-id="5da60-148">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5da60-p111">Verrà richiesto nome utente e password dell'account Administrator locale su DC1. Utilizzare una password complessa e annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="5da60-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="5da60-151">Eseguire quindi la connessione alla macchina virtuale DC1.</span><span class="sxs-lookup"><span data-stu-id="5da60-151">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="5da60-152">Nel [Portale di Azure](https://portal.azure.com), fare clic su **Gruppi di risorse >** [nome del nuovo gruppo di risorse] **> DC1 > Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5da60-152">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="5da60-p112">Nel riquadro aperto, fare clic su **Scarica file RDP**. Aprire il file DC1.rdp che viene scaricato e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5da60-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="5da60-155">Specificare il nome dell'account Administrator locale DC1:</span><span class="sxs-lookup"><span data-stu-id="5da60-155">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="5da60-156">Per Windows 7:</span><span class="sxs-lookup"><span data-stu-id="5da60-156">For Windows 7:</span></span>
    
     <span data-ttu-id="5da60-p113">Nella finestra di dialogo **Protezione di Windows**, fare clic su **Utilizza un altro account**. In **Nome utente**, digitare **DC1\\**[nome dell'account Administrator locale].</span><span class="sxs-lookup"><span data-stu-id="5da60-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="5da60-159">Per Windows 8 o Windows 10:</span><span class="sxs-lookup"><span data-stu-id="5da60-159">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="5da60-p114">Nella finestra di dialogo **Sicurezza di Windows**, fare clic su **Ulteriori scelte**, quindi fare clic su **Utilizzare un altro account**. In **Nome utente**, digitare **DC1\\**[nome dell'account Administrator locale].</span><span class="sxs-lookup"><span data-stu-id="5da60-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="5da60-162">In **Password**, digitare la password dell’account Administrator locale, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da60-162">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5da60-163">Quando viene richiesto, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5da60-163">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="5da60-164">Aggiungere un ulteriore disco dati come nuovo volume con lettera di unità F: immettendo questo comando al prompt dei comandi di Windows PowerShell a livello di amministratore in DC1.</span><span class="sxs-lookup"><span data-stu-id="5da60-164">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="5da60-p115">Successivamente, configurare DC1 come controller di dominio e i server DNS per il dominio **testlab.**\<dominio pubblico>. Specificare il nome di dominio pubblico, rimuovere \< e i caratteri >, quindi eseguire questi comandi al prompt dei comandi di Windows PowerShell a livello di amministratore nel DC1.</span><span class="sxs-lookup"><span data-stu-id="5da60-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="5da60-p116">Sarà necessario specificare una password di amministratore in modalità provvisoria. Archiviare la password in un percorso sicuro.</span><span class="sxs-lookup"><span data-stu-id="5da60-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="5da60-169">Si tenga presente che il completamento di questi comandi potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="5da60-169">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="5da60-170">Dopo il riavvio di DC1, riconnettersi al computer virtuale DC1.</span><span class="sxs-lookup"><span data-stu-id="5da60-170">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="5da60-171">Nel [Portale di Azure](https://portal.azure.com), fare clic su **Gruppi di risorse >** [nome del nuovo gruppo di risorse] **> DC1 > Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5da60-171">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="5da60-172">Eseguire il file DC1.rdp che viene scaricato e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5da60-172">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="5da60-p117">In **Sicurezza di Windows**, fare clic su **Utilizza un altro account**. In **Nome utente**, digitare **TESTLAB\\**[nome dell'account Administrator locale].</span><span class="sxs-lookup"><span data-stu-id="5da60-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="5da60-175">In **Password**, digitare la password dell’account Administrator locale, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da60-175">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5da60-176">Quando viene richiesto, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5da60-176">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="5da60-p118">Successivamente, creare un account utente in Active Directory che verrà utilizzato quando si accede a computer membri del dominio TESTLAB. Eseguire questo comando al prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="5da60-p119">Tenere presente che questo comando chiede di specificare la password dell'account User1. Poiché questo account verrà utilizzato per le connessioni desktop remote per tutti i computer membri del dominio TESTLAB, scegliere una password complessa. Registrare la password dell'account User1 e archiviarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="5da60-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="5da60-p120">Configurare quindi il nuovo account User1 come amministratore del dominio, dell'organizzazione e dello schema. Eseguire questo comando al prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="5da60-184">Chiudere la sessione Desktop remoto con DC1, quindi riconnettersi usando l'account TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="5da60-184">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="5da60-185">Successivamente, per consentire il traffico per lo strumento Ping, eseguire questo comando al prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-185">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="5da60-186">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5da60-186">This is your current configuration.</span></span>
  
![Passaggio 1 della configurazione di base per l'organizzazione simulata](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="5da60-188">Passaggio 2: configurare APP1</span><span class="sxs-lookup"><span data-stu-id="5da60-188">Step 2: Configure APP1</span></span>

<span data-ttu-id="5da60-189">In questo passaggio, creare e configurare APP1, ovvero un server applicazioni che inizialmente fornisce servizi di condivisione file e Web.</span><span class="sxs-lookup"><span data-stu-id="5da60-189">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="5da60-190">Inserire il nome del gruppo di risorse ed eseguire questi comandi al prompt dei comandi nel computer locale per creare una macchina virtuale di Azure per APP1.</span><span class="sxs-lookup"><span data-stu-id="5da60-190">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5da60-191">Successivamente, connettersi alla macchina virtuale APP1 usando il nome e la password dell'account Administrator locale di APP1, quindi aprire un prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5da60-191">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5da60-192">Per controllare la risoluzione del nome e la comunicazione della rete tra APP1 e DC1, eseguire il comando **ping dc1.testlab.**\<nome dominio pubblico> e verificare che siano presenti quattro risposte.</span><span class="sxs-lookup"><span data-stu-id="5da60-192">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="5da60-193">Unire quindi la macchina virtuale APP1 al dominio TESTLAB immettendo questi comandi nel prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5da60-193">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="5da60-194">È necessario fornire le credenziali di un account di dominio TESTLAB\\User1 dopo aver eseguito il comando **Add-Computer**.</span><span class="sxs-lookup"><span data-stu-id="5da60-194">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="5da60-195">Dopo il riavvio di APP1, connettersi utilizzando l'account TESTLAB\\User1 e quindi aprire un prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-195">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5da60-196">Successivamente, modificare APP1 in server Web con questo comando al prompt dei comandi di Windows PowerShell in APP1 a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-196">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="5da60-197">Creare quindi una cartella condivisa e un file di testo all'interno della cartella in APP1 con i comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5da60-197">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="5da60-198">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5da60-198">This is your current configuration.</span></span>
  
![Passaggio 2 della configurazione di base per l'organizzazione simulata](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="5da60-200">Passaggio 3: configurare CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="5da60-200">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="5da60-201">In questo passaggio, viene creato e configurato CLIENT1 che si comporta come un tipico portatile, tablet o computer desktop nella rete intranet.</span><span class="sxs-lookup"><span data-stu-id="5da60-201">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="5da60-p121">Il seguente set di comandi crea CLIENT1 che esegue Windows Server 2016 Data Center. Tale operazione è possibile per tutti i tipi di sottoscrizioni di Azure. Se si dispone di una sottoscrizione di Azure basata su Visual Studio, è possibile creare CLIENT1 che esegue Windows 10 con il [Portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5da60-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="5da60-204">Inserire il nome del gruppo di risorse ed eseguire questi comandi al prompt dei comandi nel computer locale per creare una macchina virtuale di Azure per CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="5da60-204">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5da60-205">Successivamente, connettersi alla macchina virtuale CLIENT1 usando il nome e la password dell'account Administrator locale di CLIENT1, quindi aprire un prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-205">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5da60-206">Per controllare la risoluzione del nome e la comunicazione della rete tra CLIENT1 e DC1, eseguire il comando **ping dc1.testlab.**\<nome dominio pubblico> al prompt dei comandi di Windows PowerShell e verificare che siano presenti quattro risposte.</span><span class="sxs-lookup"><span data-stu-id="5da60-206">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="5da60-207">Unire quindi la macchina virtuale CLIENT1 al dominio TESTLAB immettendo questi comandi nel prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5da60-207">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="5da60-208">È necessario fornire le credenziali di un account di dominio TESTLAB\\User1 dopo aver eseguito il comando **Add-Computer**.</span><span class="sxs-lookup"><span data-stu-id="5da60-208">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="5da60-209">Dopo il riavvio di CLIENT1, connettersi utilizzando nome e password dell'account TESTLAB\\User1 e quindi aprire un prompt dei comandi di Windows PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5da60-209">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5da60-210">Successivamente, verificare che sia possibile accedere alle risorse Web e di condivisione file in APP1 da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="5da60-210">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="5da60-211">In Server Manager, nel riquadro della struttura, fare clic su **Server locale**.</span><span class="sxs-lookup"><span data-stu-id="5da60-211">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="5da60-212">In **Proprietà per CLIENT1**, fare clic su **Attiva** accanto a **Configurazione sicurezza avanzata IE**.</span><span class="sxs-lookup"><span data-stu-id="5da60-212">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="5da60-213">In **Configurazione sicurezza avanzata IE**, fare clic su **Disattiva** per **Amministratori** e **Utenti**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da60-213">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5da60-214">Dalla schermata Start, fare clic su **Internet Explorer**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da60-214">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5da60-p122">Nella barra degli indirizzi digitare **http<span>://</span>app1.testab.**\<nome dominio pubblico>**/**, quindi premere INVIO. Dovrebbe essere possibile visualizzare la pagina Web predefinita di Internet Information Services per APP1.</span><span class="sxs-lookup"><span data-stu-id="5da60-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="5da60-217">Dalla barra delle applicazioni del desktop, fare clic sull'icona Esplora File.</span><span class="sxs-lookup"><span data-stu-id="5da60-217">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="5da60-p123">Nella barra degli indirizzi, digitare **\\\\app1\\Files**, quindi premere INVIO. Verrà visualizzata una finestra della cartella con il contenuto della cartella File condivisi.</span><span class="sxs-lookup"><span data-stu-id="5da60-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="5da60-p124">Nella finestra della cartella **File** condivisi, fare doppio clic sul file **Example.txt**. Verrà visualizzato il contenuto del file Example.txt.</span><span class="sxs-lookup"><span data-stu-id="5da60-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="5da60-222">Chiudere **example.txt - Blocco note** e la finestra della cartella **File** condivisi.</span><span class="sxs-lookup"><span data-stu-id="5da60-222">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="5da60-223">Questa è la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5da60-223">This is your current configuration.</span></span>
  
![Passaggio 3 della configurazione di base per l'organizzazione simulata](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="5da60-225">Fase 2: creare gli abbonamenti a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5da60-225">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="5da60-p125">In questa fase viene creato un nuovo abbonamento a Microsoft 365 E5 che usa un nuovo tenant Azure Active Directory, separato dall'abbonamento di produzione. L'operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="5da60-p125">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="5da60-228">Usare un abbonamento di valutazione a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5da60-228">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="5da60-p126">L'abbonamento di valutazione a Microsoft 365 E5 è di 30 giorni e può essere esteso facilmente a 60 giorni. Quando l'abbonamento di valutazione scade, è necessario convertirlo in un abbonamento a pagamento o creare un nuovo abbonamento di valutazione. Con la creazione di nuovi abbonamenti di valutazione, la configurazione esistente, che può contenere scenari complessi, viene abbandonata.</span><span class="sxs-lookup"><span data-stu-id="5da60-p126">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscriptions or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="5da60-232">Usare un abbonamento di produzione separato a Microsoft 365 E5 con un numero limitato di licenze.</span><span class="sxs-lookup"><span data-stu-id="5da60-232">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="5da60-p127">Questo comporta un costo aggiuntivo, ma consente di disporre di un ambiente di testing di base per provare funzioni, configurazioni e scenari senza scadenza. È possibile usare lo stesso ambiente di testing durante il lungo periodo per prove di funzionamento, dimostrazioni a colleghi, gestione, nonché sviluppo e test delle applicazioni. Questo è il metodo consigliato.</span><span class="sxs-lookup"><span data-stu-id="5da60-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="5da60-236">Registrare un abbonamento di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5da60-236">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="5da60-237">Connettersi a CLIENT1 con l'account CORP\User1 dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="5da60-237">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="5da60-238">Per creare un nuovo abbonamento di valutazione di Office 365 E5, seguire le istruzioni riportate nella [fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) della guida al lab di test sulla configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="5da60-238">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="5da60-239">Per configurare il nuovo abbonamento di valutazione di Office 365 E5, seguire le istruzioni riportate nella [fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) della guida al lab di test sulla configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="5da60-239">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="5da60-240">Uso di un ambiente di testing di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5da60-240">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="5da60-241">Se tutto ciò che serve è un ambiente di testing di Office 365, è possibile fermarsi qui.</span><span class="sxs-lookup"><span data-stu-id="5da60-241">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="5da60-242">Per altre guide al lab di test valide sia per Office 365 che per Microsoft 365, vedere [Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="5da60-242">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="5da60-243">Aggiungere un abbonamento di valutazione a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5da60-243">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="5da60-244">Per aggiungere un abbonamento di valutazione a Microsoft 365 E5 e configurare gli account utente con licenze, seguire le istruzioni riportate nella [fase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) della guida al lab di test sulla configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="5da60-244">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="5da60-245">Risultati</span><span class="sxs-lookup"><span data-stu-id="5da60-245">Results</span></span>

<span data-ttu-id="5da60-246">A questo punto, l'ambiente di test dispone di:</span><span class="sxs-lookup"><span data-stu-id="5da60-246">Your test environment now has:</span></span>
  
- <span data-ttu-id="5da60-247">Abbonamento di valutazione a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5da60-247">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="5da60-248">Tutti gli account utente appropriati sono abilitati all'uso di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5da60-248">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="5da60-249">Una intranet simulata e semplificata.</span><span class="sxs-lookup"><span data-stu-id="5da60-249">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="5da60-250">Questa è la configurazione finale.</span><span class="sxs-lookup"><span data-stu-id="5da60-250">This is your final configuration.</span></span>
  
![Fase 2 della configurazione di base per l'organizzazione simulata](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="5da60-252">A questo punto è possibile sperimentare le funzionalità aggiuntive di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="5da60-252">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="5da60-253">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5da60-253">Next steps</span></span>

<span data-ttu-id="5da60-254">Esplorare questi altri insiemi di guide al lab test:</span><span class="sxs-lookup"><span data-stu-id="5da60-254">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="5da60-255">Identità</span><span class="sxs-lookup"><span data-stu-id="5da60-255">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="5da60-256">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5da60-256">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="5da60-257">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="5da60-257">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="5da60-258">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5da60-258">See also</span></span>

[<span data-ttu-id="5da60-259">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da60-259">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5da60-260">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da60-260">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5da60-261">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da60-261">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
