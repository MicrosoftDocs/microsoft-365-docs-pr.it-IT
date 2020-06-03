---
title: Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: configurare e illustrare la sincronizzazione hash delle password e l'accesso per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 7b1ba549a9ac9d3faec8b717a0f76cca1200352b
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371441"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*

Molte organizzazioni usano Azure AD Connect e la sincronizzazione hash delle password per sincronizzare il set di account della foresta Active Directory Domain Services (AD DS) locale con il set di account nel tenant di Azure AD dell'abbonamento a Microsoft 365. In questo articolo viene illustrato come aggiungere la sincronizzazione hash delle password nell'ambiente di testing di Microsoft 365, determinando la configurazione seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Le fasi principali della configurazione dell'ambiente di testing sono tre:
  
1. Creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.
2. Installare e configurare Azure AD Connect su APP1.
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.

Seguire le istruzioni riportate in [configurazione di base per l'organizzazione simulata per Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Questa è la configurazione risultante.
  
![La configurazione di base per l'organizzazione simulata](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.
- Una rete Intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una rete virtuale di Azure. DC1 è un controller di dominio del dominio testlab.\<nome di dominio pubblico> di AD DS. Fase 2: creare e registrare il dominio per il test lab

## <a name="phase-2-create-and-register-the-testlab-domain"></a>In questa fase si aggiunge un dominio pubblico DNS che viene aggiunto all'abbonamento.

First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.

Innanzitutto, usare il provider di registrazione DNS pubblico per creare un nuovo nome di dominio DNS pubblico basato sul proprio nome di dominio corrente e aggiungerlo all'abbonamento. È consigliabile usare il nome **testlab.**\<dominio pubblico>. Ad esempio, se il nome di dominio pubblico è **<span>contoso</span>.com**, aggiungere il nome di dominio pubblico **<span>testlab</span>.contoso.com**.
  
Tale procedura consiste nell'aggiungere altri record DNS al dominio **testlab.**\<dominio pubblico>. Per altre informazioni, vedere [Aggiungere un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). Questa è la configurazione risultante. La registrazione del nome di dominio testlab Questa configurazione è costituita da: 

Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5 con il dominio DNS testlab.\<nome dominio pubblico> registrato.
  
![Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Si noti come il testlab.\<nome di dominio pubblico> a questo punto è:

- Ospitato da record DNS pubblici. Registrato negli abbonamenti a Microsoft 365.
- Il dominio di AD DS nella rete Intranet simulata.

Quando vengono richiesti nome utente e password, specificare <strong>user1@testlab.</strong>\<nome dominio> e la password per User1. Dovrebbe essere possibile accedere come User1.

- In primo luogo, installare e configurare Azure AD Connect su APP1.
- Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\\User1.
- Dal desktop di APP1, aprire un prompt dei comandi di Windows PowerShell a livello di amministratore ed eseguire questi comandi per disabilitare Sicurezza avanzata di Internet Explorer:
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Dalla barra delle applicazioni, fare clic su **Internet Explorer** e accedere a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).

Nella pagina Microsoft Azure Active Directory Connect, fare clic su **Download** e quindi su **Esegui**.
  
Nella pagina di **Benvenuto in Azure Active Directory Connect**, fare clic su **Accetto** e quindi su **Continua**.

1. Nella pagina **Impostazioni rapide**, fare clic su **Usa impostazioni rapide**.
    
2. Nella pagina **Connessione ad Azure AD**, digitare il nome dell'account amministratore globale in **Nome utente**, digitare la password in **Password** e fare clic su **Avanti**.
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Nella pagina **Connessione ad AD DS**, digitare **TESTLAB\\User1** in **Nome utente**, digitare la relativa password in **Password** e fare clic su **Avanti**.
    
4. Nella pagina **Pronto per la configurazione** fare clic su **Installa**.
    
5. Nella pagina **Configurazione completata**, fare clic su **Esci**.
    
6. In Internet Explorer, passare all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
7. Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.
    
8. Si noti l'account denominato **User1**.
    
9. Questo account deriva dal dominio TESTLAB AD DS ed è la prova che la sincronizzazione della directory ha funzionato.
    
10. Fare clic sull'account **User1** e quindi fare clic su **Licenze e app**.
    
11. In **Licenze di prodotto** selezionare la posizione, se necessario, disabilitare la licenza di **Office 365 E5** e abilitare la licenza di **Microsoft 365 E5**.
    
12. Fare clic su **Salva** nella parte inferiore della pagina e selezionare **Chiudi**.
    
    Successivamente, verificare la possibilità di accedere all'abbonamento con il nome utente <strong>user1@testlab.</strong>\<nome dominio> nome utente dell'account User1. Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.
    
13. When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password.
    
14. You should successfully sign in as User1. 

15. Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale.
    
Di conseguenza, l'icona **Amministratore** non sarà visibile. Questa è la configurazione risultante.

1. L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password

2. Questa configurazione è costituita da: Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5 con il dominio DNS TESTLAB.\<nome dominio> registrato. Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
 
Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365. L'account User1 nel dominio TESTLAB AD DS è stato sincronizzato con il tenant Azure AD. 

Passaggio successivo

![Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Vedere anche 
  
- [Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) [Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)
- [Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.
- The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.

## <a name="next-step"></a>Next step

Explore additional <bpt id="p1">[</bpt>identity<ept id="p1">](m365-enterprise-test-lab-guides.md#identity)</ept> features and capabilities in your test environment.

## <a name="see-also"></a>See also

<bpt id="p1">[</bpt>Microsoft 365 Enterprise Test Lab Guides<ept id="p1">](m365-enterprise-test-lab-guides.md)</ept>

<bpt id="p1">[</bpt>Deploy Microsoft 365 Enterprise<ept id="p1">](deploy-microsoft-365-enterprise.md)</ept>

<bpt id="p1">[</bpt>Microsoft 365 Enterprise documentation<ept id="p1">](https://docs.microsoft.com/microsoft-365-enterprise/)</ept>


