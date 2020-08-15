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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: "Riepilogo: configurare e illustrare la sincronizzazione hash delle password e l'accesso per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 2930d147e2ae3277b0af4d2aa81a602c73128439
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686549"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Molte organizzazioni usano Azure AD Connect e la sincronizzazione hash delle password per sincronizzare il set di account della foresta Active Directory Domain Services (AD DS) locale con il set di account nel tenant di Azure AD dell'abbonamento a Microsoft 365. In questo articolo viene illustrato come aggiungere la sincronizzazione hash delle password nell'ambiente di testing di Microsoft 365, determinando la configurazione seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Le fasi principali della configurazione dell'ambiente di testing sono tre:
  
1. Creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.
2. Installare e configurare Azure AD Connect su APP1.
    
> [!TIP]
> Passare a [microsoft 365 for Enterprise Test Lab guide stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 per Enterprise.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.

Seguire le istruzioni riportate in [configurazione di base per l'organizzazione simulata per Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Questa è la configurazione risultante.
  
![La configurazione di base per l'organizzazione simulata](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una rete Intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una rete virtuale di Azure. DC1 è un controller di dominio per il dominio AD DS\<your public domain name> testlab.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: creare e registrare il dominio per il test lab

In questa fase si aggiunge un dominio pubblico DNS che viene aggiunto all'abbonamento.

Per prima cosa, rivolgersi al proprio provider di registrazione del DNS pubblico per creare un nuovo nome di dominio DNS pubblico basato sul proprio nome di dominio corrente, e aggiungerlo alla sottoscrizione. Raccomandiamo di usare il nome **testlab.**\<your public domain>. Ad esempio, se il nome di dominio è **<span>contoso</span>.com**, aggiungere il nome di dominio pubblico **<span>testlab</span>.contoso.com**.
  
In seguito, aggiungere il dominio **testlab.**\<your public domain> dominio alla sottoscrizione di valutazione di Microsoft 365 o a pagamento tramite il processo di registrazione del dominio. Tale procedura consiste nell’aggiungere altri record DNS al dominio **testlab.**\<your public domain> . Per ulteriori informazioni, vedere [aggiungere un dominio a Microsoft 365](../admin/setup/add-domain.md). 

Questa è la configurazione risultante.
  
![La registrazione del nome di dominio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Questa configurazione è costituita da:

- Un abbonamento a pagamento o di valutazione di Microsoft 365 E5 con il dominio DNS testlab.\<your public domain name> registrato.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.

Notare come il dominio testlab.\<your public domain name> è ora:

- Ospitato da record DNS pubblici.
- Registrato negli abbonamenti a Microsoft 365.
- Il dominio di AD DS nella rete Intranet simulata.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: installare Azure AD Connect su APP1

In questa fase, installare e configurare lo strumento Azure AD Connect su APP1 e verificarne il funzionamento.
  
In primo luogo, installare e configurare Azure AD Connect su APP1.

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\\User1.
    
2. Dal desktop di APP1, aprire un prompt dei comandi di Windows PowerShell a livello di amministratore ed eseguire questi comandi per disabilitare Sicurezza avanzata di Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Dalla barra delle applicazioni, fare clic su **Internet Explorer** e accedere a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. Nella pagina Microsoft Azure Active Directory Connect, fare clic su **Download** e quindi su **Esegui**.
    
5. Nella pagina di **Benvenuto in Azure Active Directory Connect**, fare clic su **Accetto** e quindi su **Continua**.
    
6. Nella pagina **Impostazioni rapide**, fare clic su **Usa impostazioni rapide**.
    
7. Nella pagina **Connessione ad Azure AD**, digitare il nome dell'account amministratore globale in **Nome utente**, digitare la password in **Password** e fare clic su **Avanti**.
    
8. Nella pagina **Connessione ad AD DS**, digitare **TESTLAB\\User1** in **Nome utente**, digitare la relativa password in **Password** e fare clic su **Avanti**.
    
9. Nella pagina **Pronto per la configurazione** fare clic su **Installa**.
    
10. Nella pagina **Configurazione completata**, fare clic su **Esci**.
    
11. In Internet Explorer, passare all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.
    
    Si noti l'account denominato **User1**. Questo account deriva dal dominio TESTLAB AD DS ed è la prova che la sincronizzazione della directory ha funzionato.
    
13. Fare clic sull'account **User1** e quindi fare clic su **Licenze e app**.
    
14. In **Licenze di prodotto** selezionare la posizione, se necessario, disabilitare la licenza di **Office 365 E5** e abilitare la licenza di **Microsoft 365 E5**. 

15. Fare clic su **Salva** nella parte inferiore della pagina e selezionare **Chiudi**.
    
In seguito, verificare la possibilità di accedere alla sottoscrizione con il nome utente <strong>user1@testlab.</strong>\<your domain name> per l’account User1.

1. Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.

2. Quando vengono richiesti nome utente e password, specificare <strong>user1@testlab.</strong>\<your domain name> e la password User1. Dovrebbe essere possibile accedere come User1. 
 
Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale. Di conseguenza, l'icona **Amministratore** non sarà visibile. 

Questa è la configurazione risultante.

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Questa configurazione è costituita da: 
  
- Sottoscrizioni di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5 con il dominio DNS TESTLAB.\<your domain name> registrato.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.
- L'account User1 nel dominio TESTLAB AD DS è stato sincronizzato con il tenant Azure AD.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)


