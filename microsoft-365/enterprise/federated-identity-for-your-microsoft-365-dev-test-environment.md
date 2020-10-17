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
localization_priority: Normal
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
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487685"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Identità federata per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Microsoft 365 supporta l'identità federativa. Questo indica che invece di eseguire la convalida delle credenziali autonomamente, Microsoft 365 fa riferimento all'utente connesso a un server di autenticazione federata che Microsoft 365 considera attendibile. Se le credenziali dell'utente sono corrette, il server di autenticazione federata emette un token di sicurezza che il client invia quindi a Microsoft 365 come prova di autenticazione. L'identità federativa consente l'offload e la scalabilità in verticale di autenticazione per una sottoscrizione a Microsoft 365 e scenari di sicurezza e autenticazione avanzata.
  
In questo articolo viene descritto come configurare l'autenticazione federata per l'ambiente di testing di Microsoft 365, ottenendo quanto segue:

![Autenticazione federata per l'ambiente di testing di Office 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o di produzione Microsoft 365 E5.
    
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita da cinque macchine virtuali in una subnet di una rete virtuale di Azure (DC1, APP1, CLIENT1, ADFS1 e PROXY1). Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco degli account nel dominio di servizi di dominio Active Directory con Microsoft 365. PROXY1 riceve le richieste di autenticazione in arrivo. ADFS1 convalida le credenziali con DC1 e rilascia token di sicurezza.
    
La configurazione di questo ambiente di testing comporta cinque fasi:
- [Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: creare il server AD FS](#phase-2-create-the-ad-fs-server)
- [Fase 3: Creare il server proxy Web](#phase-3-create-the-web-proxy-server)
- [Fase 4: Creare un certificato autofirmato e configurare ADFS1 e PROXY1](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Fase 5: Configurare Microsoft 365 per l'identità federativa](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> Non è possibile configurare l'ambiente di testing con una sottoscrizione di valutazione di Azure.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). La configurazione risultante è simile alla seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Questa configurazione è costituita da:
  
- Una versione di valutazione di Microsoft 365 E5 o abbonamenti A pagamento.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure. Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio servizi di dominio Active Directory (AD DS) di TESTLAB con il tenant di Azure AD delle sottoscrizioni di Microsoft 365.

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

La configurazione risultante è simile alla seguente:
  
![Server AD FS aggiunto a DirSync per l'ambiente di testing di Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
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
  
Successivamente, aggiungere una regola al gruppo di sicurezza di rete per la subnet CorpNet per consentire il traffico in ingresso non richiesto da Internet all'indirizzo IP privato PROXY1's e alla porta TCP 443. Eseguire questi comandi al prompt dei comandi di Azure PowerShell nel computer locale.
  
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

Visualizzare l'indirizzo IP pubblico di PROXY1 con questi comandi di Azure PowerShell nel computer locale.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Successivamente, collaborare con il proprio provider DNS pubblico e creare un nuovo record DNS A pubblico per ** fs.testlab. **\<*your DNS domain name*> che consenta di risolvere l’indirizzo IP visualizzato dal comando ** Write-Host**. Il **fs.testlab.**\<*your DNS domain name*> verrà di seguito indicato come *nome di dominio completo del servizio federativo*.
  
Successivamente, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale DC1 usando le credenziali di CORP\\User1, quindi eseguire i comandi seguenti a un prompt dei comandi di Windows PowerShell a livello di amministratore:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Questi comandi consentono di creare un record DNS interno in modo che le macchine virtuali nella rete virtuale di Azure possano risolvere l'FQDN del servizio federativo interno con l'indirizzo IP privato di ADFS1's.
  
La configurazione risultante è simile alla seguente:
  
![Server proxy dell'applicazione Web aggiunto a DirSync per l'ambiente di testing di Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fase 4: Creare un certificato autofirmato e configurare ADFS1 e PROXY1

In questa fase, viene creato un certificato digitale autofirmato per il nome di dominio completo del servizio federativo e vengono configurati ADFS1 e PROXY1 come farm AD FS.
  
Per prima cosa, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale DC1 usando le credenziali di CORP\\CORPUser1, quindi aprire un prompt dei comandi di Windows PowerShell a livello di amministratore. 
  
Successivamente, creare un account del servizio AD FS con questo comando al prompt dei comandi di Windows PowerShell su DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Tenere presente che questo comando chiede di specificare la password dell'account. Scegliere una password complessa e annotarla in una posizione sicura. Sarà necessario per questa fase e per la fase 5.
  
Utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale ADFS1 utilizzando le credenziali di CORP\\CORPUser1. Aprire un prompt dei comandi di Windows PowerShell a livello di amministratore su ADFS1, immettere il nome di dominio completo del servizio federativo e quindi eseguire questi comandi per creare un certificato autofirmato:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Successivamente, seguire questi passaggi per salvare il nuovo certificato autofirmato come file.
  
1. Fare clic sul pulsante **Start**, immettere **mmc.exe**e quindi premere **invio**.
    
2. Selezionare **file**  >  **Aggiungi/Rimuovi snap-in**.
    
3. In **Aggiungi o Rimuovi snap-** in, fare doppio clic su **certificati** nell'elenco di snap-in disponibili, selezionare **account computer**, quindi selezionare **Avanti**.
    
4. In **Seleziona computer**selezionare **fine**e quindi fare clic su **OK**.
    
5. Nel riquadro dell'albero, aprire **Certificati (computer locali) > Personale > Certificati**.
    
6. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sul certificato con il nome di dominio completo del servizio federativo, seleziona **tutte le attività**e quindi **Esporta**.
    
7. Nella pagina **iniziale** , selezionare **Avanti**.
    
8. Nella pagina **Esporta chiave privata** selezionare **Sì**, quindi fare clic su **Avanti**.
    
9. Nella pagina **formato file di esportazione** selezionare **Esporta tutte le proprietà estese**, quindi fare clic su **Avanti**.
    
10. Nella pagina **sicurezza** selezionare **password** e immettere una **password in password** e **Conferma password.**
    
11. Nella pagina **file da esportare** selezionare **Browse**.
    
12. Passare alla cartella **C: \\ certs** , immettere **SSL** in **nome file**e quindi fare clic su **Salva.**
    
13. Nella pagina **file da esportare** fare clic su **Avanti**.
    
14. Nella pagina **completamento dell'esportazione guidata certificati** selezionare **fine**. Quando richiesto, selezionare **OK**.
    
Successivamente, installare il servizio AD FS con questo comando al prompt dei comandi di Windows PowerShell in ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Attendere che venga stabilita la connessione.
  
Successivamente, configurare il servizio AD FS seguendo questi passaggi:
  
1. Fare clic su **Start**, quindi selezionare l'icona **Server Manager** .
    
2. Nel riquadro dell'albero di Server Manager **, selezionare ADFS**.
    
3. Nella barra degli strumenti nella parte superiore, selezionare il simbolo di attenzione arancione e quindi selezionare **Configure the Federation Service on this server**.
    
4. Nella pagina di **benvenuto** della configurazione guidata di Active Directory Federation Services, selezionare **Avanti**.
    
5. Nella pagina **connessione AD ad DS** , selezionare **Avanti**.
    
6. Nella pagina **Impostazione proprietà del servizio**:
    
  - Per il **certificato SSL**, selezionare la freccia in giù, quindi selezionare il certificato con il nome FQDN del servizio federativo.
    
  - In **nome visualizzato del servizio federativo**, immettere il nome dell'organizzazione fittizia.
    
  - Selezionare **Avanti**.
    
7. Nella pagina **specificare l'account del servizio** selezionare **Seleziona** per **nome account**.
    
8. In **Seleziona account utente o di servizio**, immettere **ADFS-Service**, selezionare **Controlla nomi**e quindi fare clic su **OK**.
    
9. In **password account**immettere la password per l'account ADFS-Service e quindi fare clic su **Avanti**.
    
10. Nella pagina **impostazione database di configurazione** fare clic su **Avanti**.
    
11. Nella pagina **Opzioni di revisione** selezionare **Avanti**.
    
12. Nella pagina **controlli prerequisiti** , selezionare **Configure**.

13. Nella pagina **dei risultati** , selezionare **Chiudi**.
    
14. Fare clic su **Start**, selezionare l'icona di alimentazione, fare clic su **Riavvia**e quindi su **continua**.
    
Dal [portale Azure](https://portal.azure.com), connettersi a PROXY1 con le credenziali dell'account CORP\\User1.
  
Successivamente, seguire questi passaggi per installare il certificato autofirmato sia in **PROXY1 che in APP1**.
  
1. Fare clic sul pulsante **Start**, immettere **mmc.exe**e quindi premere **invio**.
    
2. Selezionare **File > Aggiungi/Rimuovi snap-in**.
    
3. In **Aggiungi o Rimuovi snap-** in, fare doppio clic su **certificati** nell'elenco di snap-in disponibili, selezionare **account computer**, quindi selezionare **Avanti**.
    
4. In **Seleziona computer**selezionare **fine**e quindi fare clic su **OK**.
    
5. Nel riquadro dell'albero, aprire certificati personali **(computer locale)**  >  **Personal**  >  **Certificates**.
    
6. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) su **personale**, seleziona **tutte le attività**e quindi **Importa**.
    
7. Nella pagina **iniziale** , selezionare **Avanti**.
    
8. Nella pagina **file da importare** immettere ** \\ \\ adfs1 \\ certs \\ SSL. pfx**e quindi fare clic su **Avanti**.
    
9. Nella pagina **protezione della chiave privata** immettere la password del certificato in **password**e quindi fare clic su **Avanti.**
    
10. Nella pagina **archivio certificati** selezionare **Avanti.**
    
11. Nella pagina **completamento** selezionare **fine**.
    
12. Nella pagina **archivio certificati** selezionare **Avanti**.
    
13. Quando richiesto, selezionare **OK**.
    
14. Nel riquadro dell'albero, selezionare **certificati**.
    
15. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sul certificato e quindi seleziona **copia**.
    
16. Nel riquadro dell'albero, aprire **certificati Autorità di certificazione radice attendibili**  >  **Certificates**.
    
17. Sposta il puntatore del mouse sotto l'elenco dei certificati installati, seleziona e tieni premuto (o fai clic con il pulsante destro del computer) e quindi seleziona **Incolla**.
    
Aprire un prompt dei comandi PowerShell a livello di amministratore ed eseguire il comando seguente:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Attendere che venga stabilita la connessione.
  
Seguire questi passaggi per configurare il servizio proxy dell'applicazione Web in modo da utilizzare ADFS1 come server federativo:
  
1. Selezionare **Start**e quindi **Server Manager**.
    
2. Nel riquadro dell'albero, selezionare **accesso remoto**.
    
3. Nella barra degli strumenti nella parte superiore, selezionare il simbolo di attenzione arancione e quindi selezionare **Apri la procedura guidata del proxy dell'applicazione Web**.
    
4. Nella pagina di **benvenuto** della procedura guidata di configurazione del proxy applicazione Web, selezionare **Avanti**.
    
5. Nella pagina **Server federativo**:
    
  - Nella casella **nome servizio federativo** immettere l'FQDN del servizio federativo.
    
  - Nella casella **nome utente** immettere **Corp \\ User1**.
    
  - Nella casella **password** immettere la password per l'account User1.
    
  - Selezionare **Avanti**.
    
6. Nella pagina **certificato proxy ad FS** selezionare la freccia in giù, selezionare il certificato con il nome di dominio completo del servizio federativo e quindi fare clic su **Avanti**.
    
7. Nella pagina **conferma** , selezionare **Configura**.
    
8. Nella pagina **dei risultati** , selezionare **Chiudi**.
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fase 5: Configurare Microsoft 365 per l'identità federativa

Utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale APP1 utilizzando le credenziali dell'account di CORP\\CORPUser1.
  
Attenersi a questa procedura per configurare Azure AD Connect e l'abbonamento a Microsoft 365 per l'autenticazione federata:
  
1. Dal desktop, fare doppio clic su **Azure AD Connect**.
    
2. Nella pagina **Welcome to Azure ad Connect** , selezionare **Configure**.
    
3. Nella pagina **attività aggiuntive** selezionare **Cambia accesso utente**e quindi fare clic su **Avanti**.
    
4. Nella pagina **connessione ad Azure ad** , immettere il nome e la password dell'account amministratore globale e quindi fare clic su **Avanti**.
    
5. Nella pagina di **accesso dell'utente** , selezionare **Federazione con ADFS**, quindi fare clic su **Avanti**.
    
6. Nella pagina **Farm** ADFS, selezionare **Usa una farm ad FS esistente**, immettere **ADFS1** nella casella **nome server** e quindi fare clic su **Avanti**.
    
7. Quando vengono richieste le credenziali del server, immettere le credenziali dell' \\ account Corp User1 e quindi fare clic su **OK**.
    
8. Nella pagina credenziali di **amministratore di dominio** , **immettere Corp \\ User1** nella casella **nome utente** , immettere la password dell'account nella casella **password** e quindi fare clic su **Avanti**.
    
9. Nella pagina **account del servizio** ADFS, immettere **Corp \\ ADFS-Service** nella casella **nome utente dominio** , immettere la password dell'account nella casella **password utente di dominio** e quindi fare clic su **Avanti**.
    
10. Nella pagina **dominio di Azure ad** , in **dominio**, selezionare il nome del dominio precedentemente creato e aggiunto all'abbonamento nella fase 1, quindi selezionare **Avanti**.
    
11. Nella pagina **pronto per la configurazione** , selezionare **Configure**.
    
12. Nella pagina **installazione completata** selezionare **Verifica**.
    
    Verrà visualizzato un messaggio che indica che sia la configurazione Intranet sia quella Internet sono state verificate.
    
13. Nella pagina **installazione completata** selezionare **Esci**.
    
Per verificare il funzionamento dell'autenticazione federata, eseguire le operazioni seguenti:
  
1. Aprire una nuova istanza privata del browser nel computer locale e andare a [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Per le credenziali di accesso, immettere **User1@** \<*the domain created in Phase 1*> .
    
    Ad esempio, se il dominio di prova è **testlab.contoso.com**, immettere "User1@testlab.contoso.com". Premere il tasto **Tab** o consentire a Microsoft 365 di reindirizzare automaticamente l'utente.
    
    Viene visualizzata una pagina **La connessione non è privata**. Si sta vedendo questo dato che è stato installato un certificato autofirmato su ADFS1 che il computer desktop non è in grado di convalidare. In una distribuzione di produzione di autenticazione federata, utilizzare un certificato rilasciato da un'autorità di certificazione attendibile per fare in modo che gli utenti non visualizzino questa pagina.
    
3. Nella pagina la **connessione non è privata** selezionare **Avanzate**, quindi **fare \<*your federation service FQDN*> **clic su continua. 
    
4. Nella pagina con il nome dell'organizzazione fittizia accedere con le seguenti credenziali:
    
  - **CORP\\User1** per il nome
    
  - La password per l'account User1
    
    Verrà visualizzata la **Home Page Microsoft Office**.
    
Questa procedura dimostra che l'abbonamento di valutazione è federato con il dominio corp.contoso.com di Active Directory Domain Services ospitato su DC1. Ecco i concetti di base del processo di autenticazione:
  
1. Quando si utilizza il dominio federato creato nella fase 1 all'interno del nome dell'account di accesso, Microsoft 365 reindirizza il browser al nome di dominio completo del servizio federativo e PROXY1.
    
2. PROXY1 invia al computer locale la pagina di accesso della società fittizia.
    
3. Quando si invia CORP\\CORPUser1 e la password a PROXY1, quest'ultimo li reinvia ad ADFS1.
    
4. ADFS1 convalida CORP\\CORPUser1 e la password con DC1 e invia al computer locale un token di sicurezza.
    
5. Il computer locale invia il token di sicurezza a Microsoft 365.
    
6. Microsoft 365 verifica che il token di sicurezza è stato creato da ADFS1 e consente l'accesso.
    
L'abbonamento di valutazione è ora configurato con l'autenticazione federata. È possibile usare questo ambiente di sviluppo/test per scenari di autenticazione avanzata.
  
## <a name="next-step"></a>Passaggio successivo

Quando si è pronti a distribuire l'autenticazione federata pronta per la produzione a disponibilità elevata per Microsoft 365 in Azure, vedere [deploy High Availability Federated Authentication for microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
