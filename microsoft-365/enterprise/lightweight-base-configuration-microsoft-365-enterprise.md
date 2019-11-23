---
title: Configurazione di base
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: Utilizzare questa guida al lab di test per creare un ambiente di testing semplificato per testare Microsoft 365 Enterprise.
ms.openlocfilehash: 6f49982fe71196f3c147c1638b402ee63bb861c1
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202307"
---
# <a name="the-lightweight-base-configuration"></a>La configurazione di base

*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*

Questo articolo fornisce istruzioni dettagliate su come creare un ambiente semplificato con un abbonamento Microsoft 365 E5 e un computer che esegue Windows 10 Enterprise. 

![Ambiente di testing semplificato di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Utilizzare l'ambiente risultante per testare le funzionalità di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-create-your-office-365-e5-subscription"></a>Fase 1: creare la sottoscrizione di Office 365 E5

Si inizia con un abbonamento di valutazione a Office 365 E5 e quindi si aggiunge l'abbonamento a Microsoft 365 E5.

Per avviare la sottoscrizione di valutazione di Office 365 E5, è necessario innanzitutto un nome di società fittizia e un nuovo account Microsoft.
  
1. Si consiglia di utilizzare una variante del nome aziendale Contoso per il nome dell'azienda, che è un nome aziendale fittizio utilizzato nel contenuto di esempio di Microsoft, ma non è obbligatorio. Registrare il nome della società fittizia qui: ![](./media/Common-Images/TableLine.png)
    
2. Per registrare un nuovo account Microsoft, andare su [https://outlook.com](https://outlook.com) e creare un account con un nuovo account di posta elettronica e indirizzo. Utilizzare questo account per iscriversi a Office 365.
    
  - Registrare il nome e cognome del nuovo account qui: ![](./media/Common-Images/TableLine.png)
    
  - Registrare l'indirizzo e-mail del nuovo account qui: ![](./media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrare una sottoscrizione di valutazione di Office 365 E5

1. Aprire il browser Internet nel computer e passare a [https://aka.ms/e5trial](https://aka.ms/e5trial).
    
2. Nella pagina **Grazie per aver scelto Office 365 E5** specificare l'indirizzo e-mail del nuovo account al passaggio 1.
3. Nel passaggio 2 del processo dell'abbonamento di valutazione digitare le informazioni richieste e quindi eseguire la verifica.
4. Nel passaggio 3 digitare un nome di organizzazione e quindi il nome dell'account che sarà amministratore globale dell'abbonamento. 
5. Per il passaggio 4, registrare la pagina di accesso qui (selezionare e copiare): ![](./media/Common-Images/TableLine.png) 
6. Registrare l'ID utente qui: ![](./media/Common-Images/TableLine.png).onmicrosoft.com  
   Annotare la password in un posto sicuro.
   Questo valore verrà denominato **Nome amministratore globale di Office 365**.
8. Fare clic su **Vai alla configurazione**.
9. Nella configurazione di Office 365 E5 fare clic su **Continua a usare *nomeorganizzazione*.onmicrosoft.com per la posta elettronica e l'accesso** e quindi fare clic su **Esci e continua più tardi**.

Dovrebbe essere visualizzata l'interfaccia di amministrazione di Microsoft 365.
  
È stato creato un abbonamento di valutazione a Office 365 in modo che l'ambiente di testing includa un tenant di Azure AD separato rispetto a quelli a pagamento attualmente in uso. Questa separazione indica che è possibile aggiungere e rimuovere utenti e gruppi nel tenant di test senza influire sugli abbonamenti di produzione.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurare l'abbonamento di valutazione a Office 365

In questa fase è possibile configurare l'abbonamento a Office 365 con altri utenti e assegnare loro le licenze di Office 365 E5.
  
Seguire le istruzioni in [Connettersi a Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) per connettersi all'abbonamento a Office 365 con il modulo Azure Active Directory PowerShell for Graph dal proprio computer.
    
Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell** digitare il nome dell'amministratore globale di Office 365 (ad esempio: jdoe@contosotoycompany.onmicrosoft.com) e la password.
  
Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri, una password comune di account e quindi eseguire i comandi seguenti dal prompt di PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> L'uso di una password comune qui consente l'automazione e agevola la configurazione per un ambiente di testing. Ovviamente, questo approccio è sconsigliato per le sottoscrizioni di produzione. 

### <a name="record-key-information-for-future-reference"></a>Registrare informazioni chiave per riferimenti futuri

Si consiglia di stampare questo articolo per registrare le informazioni specifiche necessarie per questo ambiente nei 30 giorni dell'abbonamento di valutazione a Office 365. È possibile estendere l'abbonamento di prova per altri 30 giorni. Per un ambiente di testing permanente, creare un nuovo abbonamento a pagamento con un tenant di Azure AD separato e un numero limitato di licenze.

Registrare questi valori:
  
- Nome amministratore globale di Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (dal passaggio 6 della fase 1)
    
    Annotare anche la password di questo account in una posizione sicura.
    
- Nome dell'organizzazione dell'abbonamento di valutazione: ![](./media/Common-Images/TableLine.png) (dal passaggio 4 della fase 1)
    
- Per elencare gli account di User 2, User 3, User 4, e User 5, eseguire i comandi seguenti dal modulo di Microsoft Azure Active Directory per il prompt di Windows PowerShell:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Registrare i nomi degli account qui:
    
  - Nome account utente User 2: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente User 3: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente User 4: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente User 5: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    Registrare anche la password comune degli account in un posto sicuro.
   

### <a name="using-an-office-365-test-environment"></a>Uso di un ambiente di testing di Office 365

Se tutto ciò che serve è un ambiente di testing di Office 365, è possibile fermarsi qui. 

Per altre guide al lab di test valide sia per Office 365 che per Microsoft 365, vedere [Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5

In questa fase è possibile sottoscrivere un abbonamento di valutazione a Microsoft 365 E5 e aggiungerlo alla stessa organizzazione dell'abbonamento di valutazione a Office 365 E5.
  
Prima di tutto, aggiungere l'abbonamento di valutazione a Microsoft 365 E5 e assegnare la nuova licenza di Microsoft 365 all'account di amministratore globale.
  
1. Con un'istanza privata di un browser Internet, accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) con le credenziali dell'account di amministratore globale.
    
2. Nella pagina dell'**interfaccia di amministrazione di Microsoft 365** fare clic su **Fatturazione > Acquisto di servizi** nella barra di spostamento sinistra.
    
3. Nella pagina **Acquisto di servizi** fare clic su **Microsoft 365 E5** e quindi fare clic su **Ottieni una versione di prova gratuita**.

4. Nella pagina **Valutazione di Microsoft 365 E5** scegliere di ricevere una chiamata o un SMS, immettere il numero di telefono, quindi fare clic su **Inviami un SMS** o **Chiamami**. Eseguire la verifica.

5. Nella pagina **Conferma l'ordine**, fare clic su **Prova adesso**.

6. Nella pagina **Ricevuta ordine**, fare clic su **Continua**.

7. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su **Utenti > Utenti attivi**.

8. In **Utenti attivi**fare clic sull'account amministratore.

9. Fare clic su **Licenze e app**.

10. Disabilitare la licenza per Office 365 Enterprise E5 e abilitare la licenza per Microsoft 365 E5.

11. Fare clic su **Salva modifiche** e quindi chiudere il riquadro delle informazioni sull'account utente.

Successivamente, ripetere i passaggi da 8 a 11 della procedura precedente per tutti gli altri account (Utente 2, Utente 3, Utente 4 e Utente 5).
  
> [!NOTE]
> L'abbonamento di valutazione a Microsoft 365 E5 dura 30 giorni. Per un ambiente di testing permanente, convertire questo abbonamento di valutazione in uno a pagamento con un numero limitato di licenze. 
  
A questo punto, l'ambiente di test dispone di:
  
- Un abbonamento di valutazione a Microsoft 365 E5.
- Tutti gli account utente appropriati (solo l'amministratore globale o tutti e cinque gli account utente) sono abilitati per l'uso di Microsoft 365 E5.
    
Di seguito è riportata la configurazione risultante che consente di aggiungere Microsoft 365 E5 e include sia Office 365 che Enterprise Security + Management (EMS).
  
![Fase 3 dell'ambiente di testing di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: creare un computer con Windows 10 Enterprise

In questa fase è necessario creare un computer autonomo con sistema operativo Windows 10 Enterprise, come un computer fisico, una macchina virtuale o una macchina virtuale di Azure.
  
### <a name="physical-computer"></a>Computer fisico

Procurarsi un personal computer e installarvi Windows 10 Enterprise. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Macchina virtuale

Creare una macchina virtuale utilizzando l'hypervisor scelto e installarvi Windows 10 Enterprise. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Macchina virtuale in Azure

Per creare una macchina virtuale con Windows 10 in Microsoft Azure, ***è necessario disporre di una sottoscrizione basata su Visual Studio***, che abbia accesso all'immagine per Windows 10 Enterprise. Altri tipi di sottoscrizioni di Azure, ad esempio le sottoscrizioni di valutazione e quelle a pagamento, non hanno accesso a tale immagine. Per le informazioni più aggiornate, vedere [Utilizzare un client Windows in Azure per gli scenari di sviluppo/test](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Questi set di comandi creano una macchina virtuale con Windows 10 Enterprise denominata WIN10 e tutte le infrastrutture relative necessarie, tra cui un gruppo di risorse, un account di archiviazione e una rete virtuale. Se si ha già familiarità con i servizi di infrastruttura di Azure, si consiglia di adattare queste istruzioni all’infrastruttura attualmente implementata. 
  
Innanzitutto, avviare un prompt di Microsoft PowerShell.
  
Accedere al proprio account Azure con il seguente comando.
  
```powershell
Connect-AzAccount
```

Ottenere il nome della sottoscrizione utilizzando il comando seguente.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< e >, con il nome corretto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Quindi, creare un nuovo gruppo di risorse. Per definire un nome del gruppo di risorse univoco, utilizzare questo comando per creare un elenco di gruppi di risorse esistenti.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Creare il nuovo gruppo di risorse con questi comandi. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< e >, con i nomi corretti.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Successivamente, creare una nuova rete virtuale e la macchina virtuale con WIN10 con questi comandi. Quando richiesto, fornire il nome e la password dell'account Administrator locale per WIN10 e archiviare questi elementi in un luogo sicuro.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Fase 5: aggiungere il proprio computer con Windows 10 ad Azure AD

Dopo che la macchina virtuale o fisica con Windows 10 Enterprise è stata creata, accedere con un account amministratore locale.
  
> [!NOTE]
> Per una macchina virtuale in Azure, connettersi seguendo [queste istruzioni](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
  
Successivamente, aggiungere il computer WIN10 al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
  
1. Nel desktop del computer WIN10, fare clic su **Start > Impostazioni > Account > Accedi all'azienda o all'istituto di istruzione > Connetti**.
    
2. Nella finestra di dialogo **Configura un account aziendale o dell'istituto di istruzione**, fare clic su **Aggiungi il dispositivo ad Azure Active Directory**.
    
3. In **Account aziendale o dell'istituto di istruzione** digitare il nome dell'account di amministratore globale dell'abbonamento a Microsoft 365, quindi fare clic su **Avanti**.
    
4. In **Immettere la password**, digitare la password dell’account Administrator locale, quindi fare clic su **Accedi**.
    
5. Quando viene richiesto di verificare che l’organizzazione sia la propria, fare clic su **Aggiungi**, quindi fare clic su **Fatto**.
    
6. Chiudere la finestra delle impostazioni.
    
Successivamente, installare Office 365 ProPlus nel computer WIN10
  
1. Aprire il browser Microsoft Edge e accedere al portale di Office con le credenziali dell'account di amministratore globale. Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Nella scheda **Microsoft Office Home** fare clic su **Installa Office**.
    
3. Quando viene richiesto di eseguire operazioni, fare clic su **Esegui**, quindi fare clic su **Sì** per **Controllo dell'account utente**.
    
4. Attendere che l’installazione di Office venga completata. Quando viene visualizzato **La configurazione è completata**, fare clic su **Chiudi** due volte.
    
Di seguito è riportato l'ambiente risultante.

![Fase 5 dell'ambiente di testing di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Comprende il computer WIN10 che:

- È stato aggiunto al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
- È stato registrato come dispositivo Azure AD in Microsoft Intune (EMS).
- Include l'installazione di Office 365 ProPlus.
  
A questo punto è possibile sperimentare le funzionalità aggiuntive di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Passaggi successivi

Esplorare questi altri insiemi di guide al lab test:
  
- [Identità](m365-enterprise-test-lab-guides.md#identity)
- [Gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
