---
title: Identità federata per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: "Sintesi: configurare l'autenticazione federata per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: efe2e196b95feff2aab1577f8e5d3ee29b5e39ba
ms.sourcegitcommit: 330e9baf02b5bc220d61f777c2338814459626ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44385058"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Identità federata per l'ambiente di testing di Microsoft 365

*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*

Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.
  
In questo articolo viene descritto come configurare l'autenticazione federata per l'ambiente di testing di Microsoft 365 o Office 365, determinando la configurazione seguente:

![Autenticazione federata per l'ambiente di testing di Office 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
Questa configurazione è costituita da: 
  
- Un abbonamento di valutazione o produzione a Microsoft 365 E5 o a Office 365 E5.
    
- A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1). Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Office 365. PROXY1 receives the incoming authentication requests. ADFS1 validates credentials with DC1 and issues security tokens.
    
La configurazione dell'ambiente di testing prevede cinque fasi:
  
1. Creare l'ambiente di testing aziendale simulato con la sincronizzazione dell'hash delle password.
    
2. Creare il server ADFS (ADFS1).
    
3. Creare il server proxy Web (PROXY1).
    
4. Creare un certificato autofirmato e configurare ADFS1 e PROXY1.
    
5. Configurare Microsoft 365 per l'identità federativa.
    
> [!NOTE]
> Non è possibile configurare l'ambiente di testing con un abbonamento di valutazione di Azure. 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
Questa configurazione è costituita da: 
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD degli abbonamenti a Microsoft 365.

## <a name="phase-2-create-the-ad-fs-server"></a>Fase 2: creare il server AD FS

Un server AD FS fornisce l'autenticazione federata tra Microsoft 365 e gli account nel dominio corp.contoso.com ospitato su DC1.
  
Per creare una macchina virtuale Azure per ADFS1, inserire il nome della sottoscrizione, il gruppo di risorse e la posizione di Azure per la configurazione di base, quindi eseguire questi comandi al prompt dei comandi di Azure PowerShell nel computer locale.
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Successivamente, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale ADFS1 usando il nome e la password dell'account Administrator locale di ADFS1, quindi aprire un prompt dei comandi di Windows PowerShell.
  
Per controllare la risoluzione del nome e la comunicazione della rete tra ADFS1 e DC1, eseguire il comando **ping dc1.corp.contoso.com** e verificare che siano presenti quattro risposte.
  
Unire quindi la macchina virtuale ADFS1 al dominio CORP immettendo questi comandi nel prompt dei comandi di Windows PowerShell in ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Questa è la configurazione risultante.
  
![Server AD FS aggiunto a DirSync per l'ambiente di testing di Microsoft 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Fase 3: Creare il server proxy Web

PROXY1 consente l'inoltro dei messaggi di autenticazione tra gli utenti e ADFS1.
  
Per creare una macchina virtuale Azure per PROXY1, inserire il nome del gruppo di risorse e la posizione di Azure, quindi eseguire questi comandi al prompt dei comandi di Azure PowerShell nel computer locale.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> A PROXY1 viene assegnato un indirizzo IP pubblico statico perché verrà creato un record DNS pubblico che punta a esso e non deve essere modificato quando si riavvia la macchina virtuale PROXY1. 
  
Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443. Run these commands at the Azure PowerShell command prompt on your local computer.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Successivamente, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale PROXY1 usando il nome e la password dell'account Administrator locale di PROXY1, quindi aprire un prompt dei comandi di Windows PowerShell in PROXY1.
  
Per controllare la risoluzione del nome e la comunicazione della rete tra PROXY1 e DC1, eseguire il comando **ping dc1.corp.contoso.com** e verificare che siano presenti quattro risposte.
  
Unire quindi la macchina virtuale PROXY1 al dominio CORP immettendo questi comandi nel prompt dei comandi di Windows PowerShell in PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Visualizzare l'indirizzo IP pubblico di PROXY1 con questi comandi PowerShell di Azure nel computer locale:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<your DNS domain name> is hereafter referred to as the  *federation service FQDN*.
  
Successivamente, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale DC1 usando le credenziali di CORP\\User1, quindi eseguire i comandi seguenti a un prompt dei comandi di Windows PowerShell a livello di amministratore:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Tali comandi consentono di creare un record DNS A interno in modo che le macchine virtuali nella rete virtuale di Azure possano risolvere il nome di dominio completo interno della federazione nell'indirizzo IP privato di ADFS1.
  
Questa è la configurazione risultante.
  
![Server proxy dell'applicazione Web aggiunto a DirSync per l'ambiente di testing di Microsoft 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fase 4: Creare un certificato autofirmato e configurare ADFS1 e PROXY1

In questa fase, viene creato un certificato digitale autofirmato per il nome di dominio completo del servizio federativo e vengono configurati ADFS1 e PROXY1 come farm AD FS.
  
Per prima cosa, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale DC1 usando le credenziali di CORP\\CORPUser1, quindi aprire un prompt dei comandi di Windows PowerShell a livello di amministratore. 
  
Successivamente, creare un account del servizio AD FS con questo comando al prompt dei comandi di Windows PowerShell in DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Note that this command prompts you to supply the account password. Choose a strong password and record it in a secured location. You will need it for this phase and Phase 5.
  
Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Successivamente, seguire questi passaggi per salvare il nuovo certificato autofirmato come file.
  
1. Fare clic sul pulsante **Start**, digitare **mmc.exe**, quindi premere **INVIO**.
    
2. Fare clic su **File > Aggiungi/Rimuovi snap-in**.
    
3. In **Aggiungi o rimuovi snap-in**, fare doppio clic su **Certificati** nell'elenco di snap-in disponibili, fare clic su **Account del computer**, quindi fare clic su **Avanti**.
    
4. In **Seleziona computer**, fare clic su **Fine** e quindi su **OK**.
    
5. Nel riquadro dell'albero, aprire **Certificati (computer locali) > Personale > Certificati**.
    
6. Fare clic con il pulsante destro del mouse sul certificato con il nome di dominio completo del servizio federativo, fare clic su **Tutte le attività**, quindi su **Esporta**.
    
7. Nella pagina **iniziale**, scegliere **Avanti**.
    
8. Nella pagina **Esportazione della chiave privata con il certificato** fare clic su **Sì**, quindi su **Avanti**.
    
9. Nella pagina **Formato file di esportazione** fare clic su **Esporta tutte le proprietà estese**, quindi su **Avanti**.
    
10. Nella pagina **Sicurezza** fare clic su **Password** e digitare una password in **Password** e **Conferma password.**
    
11. Nella pagina **File da esportare** fare clic su **Sfoglia**.
    
12. Passare alla cartella **C:\\Certs**, digitare **SSL** in **Nome file** e quindi fare clic su **Salva**.
    
13. Nella pagina **File da esportare** fare clic su **Avanti**.
    
14. On the **Completing the Certificate Export Wizard** page, click **Finish**. When prompted, click **OK**.
    
Successivamente, installare il servizio AD FS con questo comando al prompt dei comandi di Windows PowerShell in ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Attendere che venga stabilita la connessione.
  
Successivamente, configurare il servizio AD FS seguendo questi passaggi:
  
1. Fare clic sul pulsante **Start** e quindi fare clic sull'icona **Server Manager**.
    
2. Nel riquadro dell'albero di Server Manager, fare clic su **AD FS**.
    
3. Nella barra degli strumenti nella parte superiore, fare clic sul simbolo di attenzione arancione e quindi fare clic su **Configurare il servizio federativo nel server**.
    
4. Nella pagina di **benvenuto** in Configurazione guidata Active Directory Federation Services, fare clic su **Avanti**.
    
5. Nella pagina **Connessione a Servizi di dominio Active Directory** fare clic su **Avanti**.
    
6. Nella pagina **Impostazione proprietà del servizio**:
    
  - Per **Certificato SSL** fare clic sulla freccia in giù, quindi selezionare il certificato con il nome di dominio completo del servizio federativo.
    
  - In **Nome visualizzato del servizio federativo**, digitare il nome dell'organizzazione fittizia.
    
  - Fare clic su **Avanti**.
    
7. Nella pagina **Impostazione account del servizio** fare clic su **Seleziona** per **Nome account**.
    
8. In **Seleziona utente o account del servizio** digitare **Servizio ADFS**, fare clic su **Controlla nomi**, quindi su **OK**.
    
9. In **Password account** digitare la password per l'account del servizio ADFS, quindi fare clic su **Avanti**.
    
10. Nella pagina **Impostazione database di configurazione** fare clic su **Avanti**.
    
11. Nella pagina **Verifica opzioni** fare clic su **Avanti**.
    
12. Nella pagina **Controlli dei prerequisiti** fare clic su **Configura**.
    
13. Nella pagina **Risultati** fare clic su **Chiudi**.
    
14. Fare clic sul pulsante **Start**, selezionare l'icona di alimentazione, fare clic su **Riavvia** e quindi su **Continua**.
    
Dal [portale Azure](https://portal.azure.com), connettersi a PROXY1 con le credenziali dell'account CORP\\User1.
  
Successivamente, seguire questi passaggi per installare il certificato autofirmato sia in ** PROXY1 che in APP1**.
  
1. Fare clic sul pulsante **Start**, digitare **mmc.exe**, quindi premere **INVIO**.
    
2. Fare clic su **File > Aggiungi/Rimuovi snap-in**.
    
3. In **Aggiungi o rimuovi snap-in**, fare doppio clic su **Certificati** nell'elenco di snap-in disponibili, fare clic su **Account del computer**, quindi fare clic su **Avanti**.
    
4. In **Seleziona computer**, fare clic su **Fine** e quindi su **OK**.
    
5. Nel riquadro dell'albero, aprire **Certificati (computer locali) > Personale > Certificati**.
    
6. Fare clic con il pulsante destro del mouse su **Personale**, selezionare **Tutte le attività** e fare clic su **Importa**.
    
7. Nella pagina **iniziale**, scegliere **Avanti**.
    
8. Nella pagina **File da importare** digitare **\\\\adfs1\\certs\\ssl.pfx**, quindi fare clic su **Avanti**.
    
9. Nella pagina **Protezione della chiave privata** digitare la password del certificato in **Password**, quindi fare clic su **Avanti.**
    
10. Nella pagina **Archivio certificati** fare clic su **Avanti**.
    
11. Nella pagina **Completamento in corso** fare clic su **Fine**.
    
12. Nella pagina **Archivio certificati** fare clic su **Avanti**.
    
13. Quando viene richiesto, fare clic su **OK**.
    
14. Fare clic su **Certificati** nel riquadro dell'albero.
    
15. Fare clic con il pulsante destro del mouse sul certificato, quindi su **Copia**.
    
16. Nel riquadro dell'albero, aprire **Autorità di certificazione radice attendibili > Certificati**.
    
17. Spostare il puntatore del mouse sotto l'elenco di certificati installati rapida, fare clic con il pulsante destro e quindi selezionare **Incolla**.
    
Aprire un prompt dei comandi PowerShell a livello di amministratore ed eseguire il comando seguente:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Attendere che venga stabilita la connessione.
  
Seguire questi passaggi per configurare il servizio proxy dell'applicazione Web in modo da utilizzare ADFS1 come server federativo:
  
1. Fare clic sul pulsante **Start** e quindi scegliere **Server Manager**.
    
2. Nel riquadro dell'albero fare clic su **Accesso remoto**.
    
3. Nella barra degli strumenti nella parte superiore, fare clic sul simbolo di attenzione arancione e quindi fare clic su **Apre la procedura guidata per il proxy dell'applicazione Web**.
    
4. Nella pagina di **benvenuto** nella Configurazione guidata proxy applicazione Web, fare clic su **Avanti**.
    
5. Nella pagina **Server federativo**:
    
  - Digitare il nome di dominio completo del servizio federativo in **Nome servizio federativo**.
    
  - Digitare **CORP\\User1** in **Nome utente**.
    
  - Digitare la password per l'account User1 nel campo **Password**.
    
  - Fare clic su **Avanti**.
    
6. Nella pagina **Certificato proxy AD FS** fare clic sulla freccia in giù, selezionare il certificato con il nome di dominio completo del servizio federativo e fare clic su **Avanti**.
    
7. Nella pagina **Conferma** fare clic su **Configura**.
    
8. Nella pagina **Risultati** fare clic su **Chiudi**.

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fase 5: Configurare Microsoft 365 per l'identità federativa

Utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale APP1 utilizzando le credenziali dell'account di CORP\\CORPUser1.
  
Attenersi a questa procedura per configurare Azure AD Connect e l'abbonamento a Microsoft 365 per l'autenticazione federata:
  
1. Dal desktop, fare doppio clic su **Azure AD Connect**.
    
2. Nella pagina **Azure AD Connect** fare clic su **Configura**.
    
3. Nella pagina **Attività aggiuntive** fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.
    
4. Nella pagina **Connessione ad Azure AD**, digitare il nome e la password dell'account amministratore globale e fare clic su **Avanti**.
    
5. Nella pagina **Accesso utente**, fare clic su **Federazione tramite ADFS**, quindi fare clic su **Avanti**.
    
6. Nella pagina **Farm AD FS** fare clic su **Usa una farm AD FS esistente**, digitare **ADFS1** in **Nome del server** e quindi fare clic su **Avanti**.
    
7. Quando vengono richieste le credenziali del server, immettere quelle dell'account di CORP\\CORPUser1, quindi fare clic su **OK**.
    
8. Nella pagina delle credenziali dell'**amministratore di dominio** digitare **CORP\\User1** in **Nome utente** e la password dell'account in **Password**, quindi fare clic su **Avanti**.
    
9. Nella pagina **Account del servizio ADFS** digitare **CORP\\ADFS-Service** in **Nome utente di dominio** e la password dell'account in **Password utente di dominio**, quindi fare clic su **Avanti**.
    
10. Nella pagina **Dominio di Azure AD**, in **Dominio** selezionare il nome del dominio precedentemente creato e aggiunto all'abbonamento nella fase 1, quindi fare clic su **Avanti**.
    
11. Nella pagina **Pronto per la configurazione** fare clic su **Configura**.
    
12. Nella pagina **Installazione completata** fare clic su **Verifica**.
    
    Verranno visualizzati messaggi che confermano la corretta configurazione Internet e Intranet.
    
13. Nella pagina **Installazione completata**, fare clic su **Chiudi**.
    
Per verificare il funzionamento dell'autenticazione federata, eseguire le operazioni seguenti:
  
1. Aprire una nuova istanza privata del browser nel computer locale e andare a [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Per le credenziali di accesso, digitare **user1@**\<the domain created in Phase 1>. 
    
    For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com". Press TAB or allow Microsoft 365 to automatically redirect you.
    
    You should now see a **Your connection is not private** page. You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate. In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.
    
3. Nella pagina **La connessione non è privata**, fare clic su **Avanzate**, quindi su **Continua a \<your federation service FQDN>**. 
    
4. Nella pagina con il nome dell'organizzazione fittizia accedere con le seguenti credenziali:
    
  - **CORP\\User1** per il nome
    
  - La password per l'account User1
    
    Verrà visualizzata la **Home Page Microsoft Office**.
    
This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:
  
1. Quando si utilizza il dominio federato creato nella fase 1 all'interno del nome dell'account di accesso, Microsoft 365 reindirizza il browser al nome di dominio completo del servizio federativo e PROXY1.
    
2. PROXY1 invia al computer locale la pagina di accesso della società fittizia.
    
3. Quando si invia CORP\\CORPUser1 e la password a PROXY1, quest'ultimo li reinvia ad ADFS1.
    
4. ADFS1 convalida CORP\\CORPUser1 e la password con DC1 e invia al computer locale un token di sicurezza.
    
5. Il computer locale invia il token di sicurezza a Microsoft 365.
    
6. Microsoft 365 verifica che il token di sicurezza è stato creato da ADFS1 e consente l'accesso.
    
Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.
  
## <a name="next-step"></a>Passaggio successivo

Quando si intende distribuire l'autenticazione federata a disponibilità elevata pronta per la produzione per Microsoft 365 o per Office 365 in Azure, vedere [Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).
  
