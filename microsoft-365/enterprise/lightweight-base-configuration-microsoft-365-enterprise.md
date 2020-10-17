---
title: Configurazione di base
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Utilizzare questa guida del laboratorio di testing per creare un ambiente di testing semplificato per il testing di Microsoft 365 per Enterprise.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487389"
---
# <a name="the-lightweight-base-configuration"></a>La configurazione di base

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

In questo articolo viene descritto come creare un ambiente semplificato con un abbonamento a Microsoft 365 E5 e un computer che esegue Windows 10 Enterprise.

![Ambiente di testing semplificato di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

La creazione di un ambiente di testing leggero comporta cinque fasi:
- [Fase 1: creare la sottoscrizione Microsoft 365 E5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: configurare l'abbonamento di valutazione a Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: creare un computer con Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: aggiungere il proprio computer con Windows 10 ad Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Utilizzare l'ambiente risultante per testare le funzionalità e le funzionalità di [Microsoft 365 per Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 per l'organizzazione, vedere [microsoft 365 for Enterprise Test Lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Si consiglia di stampare questo articolo per registrare le informazioni specifiche necessarie per questo ambiente nei 30 giorni dell'abbonamento di valutazione a Office 365. È possibile estendere l'abbonamento di prova per altri 30 giorni. Per un ambiente di testing permanente, creare un nuovo abbonamento a pagamento con un tenant di Azure AD separato e un numero limitato di licenze.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: creare la sottoscrizione Microsoft 365 E5

Si inizia con una sottoscrizione di valutazione di Microsoft 365 E5 e quindi si aggiunge la sottoscrizione Microsoft 365 E5.

>[!NOTE]
>Si consiglia di creare una sottoscrizione di valutazione di Office 365 in modo che l'ambiente di testing disponga di un tenant di Azure AD separato da qualsiasi sottoscrizione a pagamento attualmente in uso. Questa separazione significa che è possibile aggiungere e rimuovere utenti e gruppi nel tenant di test senza influire sugli abbonamenti di produzione.

Per avviare l'abbonamento di valutazione a Microsoft 365 E5, è necessario innanzitutto un nome di società fittizia e un nuovo account Microsoft.
  
1. Si consiglia di utilizzare una variante del nome aziendale Contoso per il nome dell'azienda, che è un nome aziendale fittizio utilizzato nel contenuto di esempio di Microsoft, ma non è obbligatorio. Registrare il nome della società fittizia qui: ![Riga](../media/Common-Images/TableLine.png)
    
2. Per registrare un nuovo account Microsoft, andare su [https://outlook.com](https://outlook.com) e creare un account con un nuovo account di posta elettronica e indirizzo. Utilizzare questo account per iscriversi a Office 365.
    
    - Registrare il nome e cognome del nuovo account qui: ![Riga](../media/Common-Images/TableLine.png)
    
    - Registrare l'indirizzo di posta elettronica del nuovo account qui: ![Riga](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrare un abbonamento di valutazione di Office 365 E5

1. Nel browser, vai a [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. Nel passaggio 1 della pagina di **ringraziamento per aver scelto Office 365 E5** , immettere il nuovo indirizzo dell'account di posta elettronica.
3. Nel passaggio 2 del processo di sottoscrizione Trail, immettere le informazioni richieste e quindi eseguire la verifica.
4. Nel passaggio 3, immettere un nome di organizzazione e quindi un nome di account che sarà l'amministratore globale per la sottoscrizione.
5. Per il passaggio 4, registrare la pagina di accesso qui (selezionare e copiare): ![Riga](../media/Common-Images/TableLine.png)
6. Registrare l'ID utente qui: ![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Registrare la password immessa in una posizione sicura.
   Questo valore verrà chiamato **Nome amministratore globale**.
7. Selezionare **Vai a installazione**.
8. Nel programma di installazione di Office 365 E5, selezionare **continuare a utilizzare *l'organizzazione*. onmicrosoft.com per la posta elettronica e l'accesso**e quindi selezionare **Esci e continua in seguito**.

Dovrebbe essere visualizzata l'interfaccia di amministrazione di Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurare l'abbonamento di valutazione a Office 365

In questa fase è possibile configurare l'abbonamento con altri utenti e assegnare questi ultimi le licenze di Office 365 E5.
  
Per connettersi all'abbonamento con il modulo Azure Active Directory PowerShell per Graph dal computer, utilizzare le istruzioni riportate in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
    
Nella finestra di dialogo **richiesta credenziali di Windows PowerShell** , immettere il nome di amministratore globale (ad esempio, *jdoe@contosotoycompany.onmicrosoft.com*) e la password.
  
Inserire il nome dell'organizzazione (ad esempio, *contosotoycompany*), il codice paese a due caratteri per la posizione, una password di account comune, quindi eseguire i comandi seguenti dal prompt di PowerShell:

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

Se i valori non sono stati già registrati, registrarli subito:
  
- Nome amministratore globale: ![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com (dal passaggio 6 della fase 1)
    
    Annotare anche la password di questo account in una posizione sicura.
    
- Nome dell'organizzazione dell'abbonamento di valutazione: ![Riga](../media/Common-Images/TableLine.png) (dal passaggio 4 della fase 1)
    
- Per elencare gli account di User 2, User 3, User 4, e User 5, eseguire i comandi seguenti dal modulo di Microsoft Azure Active Directory per il prompt di Windows PowerShell:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Registrare i nomi degli account qui:
    
  - Nome account utente 2: user2@![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente 3: user3@![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente 4: user4@![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome account utente 5: user5@![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Registrare anche la password comune degli account in un posto sicuro.
   
### <a name="using-an-office-365-test-environment"></a>Uso di un ambiente di testing di Office 365

Se è necessario solo un ambiente di testing di Office 365, non è necessario leggere il resto di questo articolo.

Per le guide di laboratorio di testing aggiuntive che si applicano sia a Office 365 che a Microsoft 365, vedere [microsoft 365 for Enterprise Test Lab guide](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5

In questa fase è possibile sottoscrivere un abbonamento di valutazione a Microsoft 365 E5 e aggiungerlo alla stessa organizzazione dell'abbonamento di valutazione a Office 365 E5.
  
Prima di tutto, aggiungere l'abbonamento di valutazione a Microsoft 365 E5 e assegnare la nuova licenza di Microsoft 365 all'account di amministratore globale.
  
1. In una finestra privata del browser Internet, utilizzare le credenziali dell'account di amministratore globale per accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. Nella pagina interfaccia di **amministrazione di Microsoft 365** , nel riquadro di spostamento a sinistra, selezionare **fatturazione > acquisto servizi**.
    
3. Nella pagina **acquisto servizi** selezionare **Microsoft 365 E5**e quindi fare clic su **Ottieni versione di valutazione gratuita**.

4. Nella pagina **Microsoft 365 E5 Trial** decidere se ricevere un messaggio di testo o una telefonata, immettere il proprio numero di telefono, quindi selezionare **Text me** or **Call me**. Eseguire la verifica.

5. Nella pagina **conferma l'ordine** , fare clic su **prova adesso**.

6. Nella pagina **ricevuta ordine** selezionare **continua**.

7. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **utenti > utenti attivi**.

8. In **utenti attivi**selezionare l'account di amministratore.

9. Selezionare **licenze e app**.

10. Disabilitare la licenza per Office 365 Enterprise E5 e abilitare la licenza per Microsoft 365 E5.

11. Selezionare **Salva modifiche**e quindi chiudere il riquadro delle informazioni dell'account utente.

Successivamente, ripetere i passaggi da 8 a 11 della procedura precedente per tutti gli altri account (Utente 2, Utente 3, Utente 4 e Utente 5).
  
> [!NOTE]
> La lunghezza della sottoscrizione di valutazione di Microsoft 365 E5 è di 30 giorni. Per un ambiente di testing permanente, convertire questo abbonamento di valutazione in uno a pagamento con un numero limitato di licenze.
  
A questo punto, l'ambiente di test dispone di:
  
- Un abbonamento di valutazione a Microsoft 365 E5.
- Tutti gli account utente appropriati (solo l'amministratore globale o tutti e cinque gli account utente) sono abilitati per l'uso di Microsoft 365 E5.
    
La configurazione risultante, che aggiunge Microsoft 365 E5, è simile alla seguente:
  
![Fase 3 dell'ambiente di testing di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: creare un computer con Windows 10 Enterprise

In questa fase è necessario creare un computer autonomo con sistema operativo Windows 10 Enterprise, come un computer fisico, una macchina virtuale o una macchina virtuale di Azure.
  
### <a name="physical-computer"></a>Computer fisico

In un computer personale, installare Windows 10 Enterprise. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Macchina virtuale

Utilizzare l'hypervisor di vostra scelta per creare una macchina virtuale e quindi installare Windows 10 Enterprise su di esso. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Macchina virtuale in Azure

Per creare una macchina virtuale con Windows 10 in Microsoft Azure, ***è necessario disporre di una sottoscrizione basata su Visual Studio***, che abbia accesso all'immagine per Windows 10 Enterprise. Altri tipi di sottoscrizioni di Azure, ad esempio le sottoscrizioni di valutazione e quelle a pagamento, non hanno accesso a tale immagine. Per le informazioni più aggiornate, vedere [Utilizzare un client Windows in Azure per gli scenari di sviluppo/test](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Questi set di comandi creano una macchina virtuale con Windows 10 Enterprise denominata WIN10 e tutte le infrastrutture relative necessarie, tra cui un gruppo di risorse, un account di archiviazione e una rete virtuale. Se si ha già familiarità con i servizi di infrastruttura di Azure, adattare queste istruzioni in base all'infrastruttura correntemente distribuita.
  
Innanzitutto, avviare un prompt di Microsoft PowerShell.
  
Accedere al proprio account di Azure con questo comando.
  
```powershell
Connect-AzAccount
```

Ottenere il nome dell'abbonamento usando questo comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Impostare la sottoscrizione di Azure. Sostituire tutti gli elementi racchiusi tra virgolette, compresi i \< and > caratteri, con il nome corretto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Quindi, creare un nuovo gruppo di risorse. Per definire un nome del gruppo di risorse univoco, utilizzare questo comando per creare un elenco di gruppi di risorse esistenti.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Creare il nuovo gruppo di risorse con questi comandi. Sostituire tutti gli elementi racchiusi tra virgolette, compresi i \< and > caratteri, con i nomi corretti.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Successivamente, creare una nuova rete virtuale e la macchina virtuale WIN10 con questi comandi. Quando richiesto, fornire il nome e la password dell'account Administrator locale per WIN10 e archiviare questi elementi in un luogo sicuro.
  
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
> Per una macchina virtuale in Azure, utilizzare  [queste istruzioni](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) per connettersi.
  
Successivamente, aggiungere il computer WIN10 al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
  
1. Sul desktop del computer WIN10, selezionare **Start > Settings > accounts > Access Work o school > Connect**.
    
2. Nella finestra di dialogo **configura un account aziendale o dell'Istituto di istruzione** selezionare **Unisci questo dispositivo ad Azure Active Directory**.
    
3. In **account aziendale o dell'Istituto di istruzione**, immettere il nome dell'account di amministratore globale della sottoscrizione Microsoft 365 E5 e quindi fare clic su **Avanti**.
    
4. In **immettere**la password, immettere la password per l'account di amministratore globale, quindi selezionare **Accedi**.
    
5. Quando viene richiesto di verificare che si tratta dell'organizzazione, selezionare **join**e quindi fare clic su **fine**.
    
6. Chiudere la finestra delle impostazioni.
    
Successivamente, installare Microsoft 365 Apps for Enterprise nel computer WIN10:
  
1. Aprire il browser Microsoft Edge e accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) con le credenziali dell'account di amministratore globale.
    
2. Nella scheda **Microsoft Office Home** , selezionare **installa Office**.
    
3. Quando viene richiesto di eseguire la ricerca, selezionare **Esegui**, quindi fare clic su **Sì** per **controllo account utente**.
    
4. Attendere che l’installazione di Office venga completata. Quando si vede **che sei tutto pronto**, seleziona **Chiudi** due volte.
    
L'ambiente risultante ha un aspetto simile al seguente:

![Fase 5 dell'ambiente di testing di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Comprende il computer WIN10 che:

- È stato aggiunto al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
- È stato registrato come dispositivo Azure AD in Microsoft Intune (EMS).
- Microsoft 365 Apps for Enterprise installato.
  
Ora è possibile sperimentare le funzionalità aggiuntive di [Microsoft 365 per Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Passaggi successivi

Esplorare questi altri insiemi di guide al lab test:
  
- [Identità](m365-enterprise-test-lab-guides.md#identity)
- [Gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
