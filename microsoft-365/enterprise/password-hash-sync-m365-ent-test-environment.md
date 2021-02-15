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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487459"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per Office 365 Enterprise.*

Molte organizzazioni usano Azure AD Connect e la sincronizzazione hash delle password per sincronizzare il set di account della foresta Active Directory Domain Services (AD DS) locale con il set di account nel tenant di Azure AD dell'abbonamento a Microsoft 365. 

In questo articolo viene descritto come aggiungere la sincronizzazione hash delle password all'ambiente di testing di Microsoft 365, che determina questa configurazione:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
La configurazione di questo ambiente di testing prevede tre fasi:
- [Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2: creare e registrare il dominio per il test lab](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3: installare Azure AD Connect su APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.

Seguire le istruzioni nella [configurazione di base aziendale simulata per Microsoft 365.](simulated-ent-base-configuration-microsoft-365-enterprise.md) La configurazione risultante è simile alla seguente:
  
![La configurazione di base per l'organizzazione simulata](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una rete virtuale di Azure. DC1 è un controller di dominio per testlab.<*il nome di* dominio pubblico> dominio di Servizi di dominio Active Directory.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: creare e registrare il dominio per il test lab

In questa fase, aggiungere un dominio DNS pubblico e quindi aggiungerlo alla sottoscrizione.

Innanzitutto, collaborare con il provider di registrazione DNS pubblico per creare un nuovo nome di dominio DNS pubblico basato sul nome di dominio corrente e quindi aggiungerlo all'abbonamento. È consigliabile utilizzare il nome **testlab.<*dominio pubblico.* >** Ad esempio, se il nome di dominio pubblico è **<span>contoso</span>.com,** aggiungere il nome di dominio pubblico: **<span>testlab</span>.contoso.com**.
  
Successivamente, aggiungere **testlab.< >** dominio pubblico alla sottoscrizione di valutazione o a pagamento di Microsoft 365 attraverso il processo di registrazione del dominio. Ciò consiste nell'aggiungere ulteriori record DNS al **file testlab.<*dominio pubblico.* >** Per altre informazioni, vedere [Aggiungere un dominio a Microsoft 365.](../admin/setup/add-domain.md)

La configurazione risultante è simile alla seguente:
  
![La registrazione del nome di dominio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Questa configurazione è costituita da:

- Una sottoscrizione di valutazione o a pagamento di Microsoft 365 E5 con il dominio DNS testlab.<il nome *di* dominio pubblico> registrato.
- Una intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.

Si noti come testlab.<*il nome di* dominio pubblico> ora è:

- Ospitato da record DNS pubblici.
- Registrato negli abbonamenti a Microsoft 365.
- Il dominio di AD DS nella rete Intranet simulata.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: installare Azure AD Connect su APP1

In questa fase, installare e configurare lo strumento Azure AD Connect in APP1, quindi verificare che funzioni.
  
Prima di tutto, installare e configurare Azure AD Connect su APP1.

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\\User1.
    
2. Dal desktop di APP1, aprire un prompt dei comandi di Windows PowerShell a livello di amministratore ed eseguire questi comandi per disabilitare Sicurezza avanzata di Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Dalla barra delle applicazioni seleziona **Internet Explorer** e passa a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Nella pagina Microsoft Azure Active Directory Connect selezionare **Download** e quindi **selezionare Esegui.**
    
5. Nella pagina **Iniziale di Azure AD Connect** seleziona **Accetto** e quindi **continua.**
    
6. Nella pagina **Impostazioni rapide** selezionare Usa **impostazioni rapide.**
    
7. Nella pagina **Connetti ad Azure AD** immetti il nome dell'account amministratore globale in Nome **utente,** immetti la password in **Password** e quindi seleziona **Avanti.**
    
8. Nella pagina **Connetti a Servizi di** dominio Active Directory immettere **TESTLAB \\ User1** in **Nome utente,** immettere la relativa password in **Password** e quindi selezionare **Avanti.**
    
9. Nella pagina **Pronto per la configurazione** selezionare **Installa.**
    
10. Nella pagina **Configurazione completata** selezionare **Esci.**
    
11. In Internet Explorer, passare all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Nel riquadro di spostamento sinistro selezionare **Utenti > Utenti attivi.**
    
    Si noti l'account denominato **User1**. Questo account deriva dal dominio TESTLAB AD DS ed è la prova che la sincronizzazione della directory ha funzionato.
    
13. Selezionare **l'account User1** e quindi **selezionare Licenze e app.**
    
14. In **Licenze di prodotto,** selezionare la posizione (se necessario), disabilitare la licenza di **Office 365 E5** e quindi abilitare la licenza di **Microsoft 365 E5.** 

15. Selezionare **Salva** nella parte inferiore della pagina e quindi fare clic su **Chiudi.**
    
Testare quindi la possibilità di accedere all'abbonamento con **user1@testlab.< >** nome utente del nome di dominio dell'account User1:

1. Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.

2. Quando vengono richiesto un nome utente e una password, specificare **user1@testlab.<*nome* >** di dominio e la password User1. Dovrebbe essere possibile accedere come User1.
 
Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale. Di conseguenza, l'icona **Amministratore** non sarà visibile. 

La configurazione risultante è simile alla seguente:

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Questa configurazione è costituita da: 
  
- Sottoscrizioni di valutazione o a pagamento di Microsoft 365 E5 o Office 365 E5 con il dominio DNS TESTLAB.<*il* nome di dominio> registrato.
- Una intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure. Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB AD DS con il tenant di Azure AD dell'abbonamento a Microsoft 365.
- L'account User1 nel dominio TESTLAB AD DS è stato sincronizzato con il tenant Azure AD.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
