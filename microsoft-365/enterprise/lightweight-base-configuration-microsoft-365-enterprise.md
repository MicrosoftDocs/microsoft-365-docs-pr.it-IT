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
description: Usare questa guida al laboratorio di testing per creare un ambiente di testing leggero per il testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909707"
---
# <a name="the-lightweight-base-configuration"></a>La configurazione di base

*Questa guida al laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per gli ambienti di testing di Office 365 Enterprise.*

Questo articolo descrive come creare un ambiente semplificato con una sottoscrizione a Microsoft 365 E5 e un computer che esegue Windows 10 Enterprise.

![Ambiente di testing semplificato di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

La creazione di un ambiente di testing leggero prevede cinque fasi:
- [Fase 1: creare l'abbonamento a Microsoft 365 E5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: configurare l'abbonamento di valutazione a Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: creare un computer con Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: aggiungere il proprio computer con Windows 10 ad Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Utilizzare l'ambiente risultante per testare le caratteristiche e le funzionalità di [Microsoft 365 per le aziende.](https://www.microsoft.com/microsoft-365/enterprise)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Per una mappa visiva a tutti gli articoli dello stack di Guida del laboratorio di testing di Microsoft 365 per le aziende, vedere [Microsoft 365 for enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

>[!NOTE]
>Si consiglia di stampare questo articolo per registrare le informazioni specifiche necessarie per questo ambiente nei 30 giorni dell'abbonamento di valutazione a Office 365. È possibile estendere l'abbonamento di prova per altri 30 giorni. Per un ambiente di testing permanente, creare un nuovo abbonamento a pagamento con un tenant di Azure AD separato e un numero limitato di licenze.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: creare l'abbonamento a Microsoft 365 E5

Iniziamo con una sottoscrizione di valutazione di Microsoft 365 E5 e quindi aggiungiamo l'abbonamento a Microsoft 365 E5.

>[!NOTE]
>È consigliabile creare una sottoscrizione di valutazione di Office 365 in modo che l'ambiente di testing abbia un tenant di Azure AD separato da tutte le sottoscrizioni a pagamento attualmente disponibili. Questa separazione significa che è possibile aggiungere e rimuovere utenti e gruppi nel tenant di test senza influire sulle sottoscrizioni di produzione.

Per avviare l'abbonamento di valutazione a Microsoft 365 E5, è necessario innanzitutto un nome di società fittizia e un nuovo account Microsoft.
  
1. Si consiglia di utilizzare una variante del nome aziendale Contoso per il nome dell'azienda, che è un nome aziendale fittizio utilizzato nel contenuto di esempio di Microsoft, ma non è obbligatorio. Registrare il nome della società fittizia qui: ![Riga](../media/Common-Images/TableLine.png)
    
2. Per registrare un nuovo account Microsoft, andare su [https://outlook.com](https://outlook.com) e creare un account con un nuovo account di posta elettronica e indirizzo. Utilizzare questo account per iscriversi a Office 365.
    
    - Registrare il nome e cognome del nuovo account qui: ![Riga](../media/Common-Images/TableLine.png)
    
    - Registrare l'indirizzo di posta elettronica del nuovo account qui: ![Riga](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrare un abbonamento di valutazione di Office 365 E5

1. Nel browser passare a [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. Nel passaggio 1 della pagina **Grazie per la scelta di Office 365 E5,** immettere il nuovo indirizzo dell'account di posta elettronica.
3. Nel passaggio 2 del processo di sottoscrizione trail, immettere le informazioni richieste ed eseguire la verifica.
4. Nel passaggio 3 immettere un nome di organizzazione e quindi un nome di account che sarà l'amministratore globale per la sottoscrizione.
5. Per il passaggio 4, registrare la pagina di accesso qui (selezionare e copiare): ![Riga](../media/Common-Images/TableLine.png)
6. Registrare l'ID utente qui: ![Riga](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Registrare la password immessa in un luogo sicuro.
   Questo valore verrà chiamato **Nome amministratore globale**.
7. Selezionare **Vai al programma di installazione**.
8. Nel programma di installazione di Office 365 E5 selezionare Continua a usare il **file .onmicrosoft.com** dell'organizzazione per la posta elettronica e l'accesso, quindi selezionare **Esci e continua in seguito.**

Dovrebbe essere visualizzata l'interfaccia di amministrazione di Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurare l'abbonamento di valutazione a Office 365

In questa fase è possibile configurare l'abbonamento con altri utenti e assegnare questi ultimi le licenze di Office 365 E5.
  
Per connettersi alla sottoscrizione con il modulo Azure Active Directory PowerShell per Graph dal computer, seguire le istruzioni in Connettersi a [Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
    
Nella finestra **Windows PowerShell richiesta credenziali** immettere il nome dell'amministratore globale (ad esempio, *jdoe@contosotoycompany.onmicrosoft.com*) e la password.
  
Compilare il nome dell'organizzazione (ad esempio, *contosotoycompany),* il codice paese a due caratteri per la propria posizione, una password dell'account comune e quindi eseguire i comandi seguenti dal prompt di PowerShell:

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

Se questi valori non sono già stati registrati, registrarli ora:
  
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

Per ulteriori guide ai laboratori di testing applicabili sia a Office 365 che a Microsoft 365, vedere Guide dei laboratori di testing di [Microsoft 365 per le aziende.](m365-enterprise-test-lab-guides.md)
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5

In questa fase è possibile sottoscrivere un abbonamento di valutazione a Microsoft 365 E5 e aggiungerlo alla stessa organizzazione dell'abbonamento di valutazione a Office 365 E5.
  
Prima di tutto, aggiungere l'abbonamento di valutazione a Microsoft 365 E5 e assegnare la nuova licenza di Microsoft 365 all'account di amministratore globale.
  
1. In una finestra privata del browser Internet, usare le credenziali dell'account amministratore globale per accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. Nella pagina Dell'interfaccia di amministrazione di **Microsoft 365,** nel riquadro di spostamento sinistro, selezionare **Fatturazione > Acquisto di servizi**.
    
3. Nella pagina **Acquista servizi** selezionare **Microsoft 365 E5** e quindi selezionare **Ottieni versione di valutazione gratuita.**

4. Nella pagina **Di valutazione di Microsoft 365 E5** decidi di ricevere un SMS  o una telefonata, immetti il numero di telefono e quindi seleziona Chiamami o **Chiamami.** Eseguire la verifica.

5. Nella pagina **Conferma l'ordine** selezionare **Prova ora.**

6. Nella pagina **Conferma ordine** selezionare **Continua.**

7. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Utenti > utenti attivi**.

8. In **Utenti attivi** selezionare l'account amministratore.

9. Seleziona **Licenze e app.**

10. Disabilitare la licenza per Office 365 Enterprise E5 e abilitare la licenza per Microsoft 365 E5.

11. Selezionare **Salva modifiche** e quindi chiudere il riquadro delle informazioni sull'account utente.

Successivamente, ripetere i passaggi da 8 a 11 della procedura precedente per tutti gli altri account (Utente 2, Utente 3, Utente 4 e Utente 5).
  
> [!NOTE]
> La durata della sottoscrizione di valutazione di Microsoft 365 E5 è di 30 giorni. Per un ambiente di testing permanente, convertire questo abbonamento di valutazione in uno a pagamento con un numero limitato di licenze.
  
A questo punto, l'ambiente di test dispone di:
  
- Un abbonamento di valutazione a Microsoft 365 E5.
- Tutti gli account utente appropriati (solo l'amministratore globale o tutti e cinque gli account utente) sono abilitati per l'uso di Microsoft 365 E5.
    
La configurazione risultante, che aggiunge Microsoft 365 E5, è simile alla seguente:
  
![Fase 3 dell'ambiente di testing di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: creare un computer con Windows 10 Enterprise

In questa fase è necessario creare un computer autonomo con sistema operativo Windows 10 Enterprise, come un computer fisico, una macchina virtuale o una macchina virtuale di Azure.
  
### <a name="physical-computer"></a>Computer fisico

In un personal computer installa Windows 10 Enterprise. Puoi scaricare la versione di valutazione di Windows 10 Enterprise [qui.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine"></a>Macchina virtuale

Usa l'hypervisor di tua scelta per creare una macchina virtuale e quindi installa Windows 10 Enterprise su di essa. Puoi scaricare la versione di valutazione di Windows 10 Enterprise [qui.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine-in-azure"></a>Macchina virtuale in Azure

Per creare una macchina virtuale con Windows 10 in Microsoft Azure, ***è necessario disporre di una sottoscrizione basata su Visual Studio***, che abbia accesso all'immagine per Windows 10 Enterprise. Altri tipi di sottoscrizioni di Azure, ad esempio le sottoscrizioni di valutazione e quelle a pagamento, non hanno accesso a tale immagine. Per le informazioni più aggiornate, vedere [Utilizzare un client Windows in Azure per gli scenari di sviluppo/test](/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> [!NOTA] I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](/powershell/azureps-cmdlets-docs/). Questi set di comandi creano una macchina virtuale con Windows 10 Enterprise denominata WIN10 e tutte le infrastrutture relative necessarie, tra cui un gruppo di risorse, un account di archiviazione e una rete virtuale. Se si ha già familiarità con i servizi di infrastruttura di Azure, adattare queste istruzioni in base all'infrastruttura attualmente distribuita.
  
Innanzitutto, avviare un prompt di Microsoft PowerShell.
  
Accedere al proprio account di Azure con questo comando.
  
```powershell
Connect-AzAccount
```

Ottieni il nome della sottoscrizione usando questo comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, \< and > inclusi i caratteri, con il nome corretto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Quindi, creare un nuovo gruppo di risorse. Per definire un nome del gruppo di risorse univoco, utilizzare questo comando per creare un elenco di gruppi di risorse esistenti.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Creare il nuovo gruppo di risorse con questi comandi. Sostituire tutti gli elementi racchiusi tra virgolette, \< and > inclusi i caratteri, con i nomi corretti.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Successivamente, crea una nuova rete virtuale e la macchina virtuale WIN10 con questi comandi. Quando richiesto, fornire il nome e la password dell'account Administrator locale per WIN10 e archiviare questi elementi in un luogo sicuro.
  
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
> Per una macchina virtuale in Azure, usa  [queste istruzioni](/azure/virtual-machines/windows/connect-logon) per connetterti a essa.
  
Successivamente, aggiungere il computer WIN10 al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
  
1. Sul desktop del computer WIN10 selezionare **Start > Settings > Accounts > Access work or school > Connect**.
    
2. Nella finestra di dialogo Configura un account aziendale o **dell'istituto** di istruzione selezionare **Aggiungi il dispositivo ad Azure Active Directory.**
    
3. In **Account aziendale o dell'istituto** di istruzione immettere il nome dell'account amministratore globale dell'abbonamento a Microsoft 365 E5 e quindi selezionare **Avanti**.
    
4. In **Immetti password** immettere la password per l'account amministratore globale e quindi selezionare **Accedi.**
    
5. Quando viene richiesto di verificare che si tratta dell'organizzazione, selezionare **Partecipa** e quindi fare clic su **Fine.**
    
6. Chiudere la finestra delle impostazioni.
    
Installare quindi Microsoft 365 Apps for enterprise nel computer WIN10:
  
1. Aprire il browser Microsoft Edge e accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con le credenziali dell'account amministratore globale.
    
2. Nella scheda **Microsoft Office Home** selezionare **Installa Office**.
    
3. Quando viene richiesto di eseguire l'operazione, selezionare **Esegui** e quindi Selezionare **Sì** per **Controllo account utente.**
    
4. Attendere che l’installazione di Office venga completata. Quando viene visualizzato **You're all set!**, selezionare **Close due** volte.
    
L'ambiente risultante è simile al seguente:

![Fase 5 dell'ambiente di testing di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Comprende il computer WIN10 che:

- È stato aggiunto al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.
- È stato registrato come dispositivo Azure AD in Microsoft Intune (EMS).
- Microsoft 365 Apps for enterprise installato.
  
A questo punto è possibile sperimentare funzionalità aggiuntive di [Microsoft 365 per le aziende.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Passaggi successivi

Esplorare questi altri insiemi di guide al lab test:
  
- [Identità](m365-enterprise-test-lab-guides.md#identity)
- [Gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)