---
title: Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a uno Smart Phone nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 319f8058aa4504c52cacf5f0d97982d115c41c8a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074216"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 Enterprise

Per un ulteriore livello di sicurezza per l'accesso a Office 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure AD per l'organizzazione, è possibile abilitare l'autenticazione a più fattori di Azure, che richiede più di un semplice nome utente e una password per verificare un account. Con l'autenticazione a più fattori, agli utenti viene richiesto di riconoscere una telefonata, digitare un codice di verifica inviato in un messaggio di testo oppure specificare una password per l'app negli smartphone dopo aver inserito correttamente le password. L'accesso è consentito solo dopo che un secondo fattore di autenticazione viene soddisfatto. 
  
In questo articolo viene descritto come abilitare e testare l'autenticazione basata su messaggi di testo per un account specifico.
  
Sono disponibili due fasi per configurare l'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 Enterprise:
  
1. Creare l'ambiente di testing di Microsoft 365 Enterprise.
    
2. Abilitare e testare l'autenticazione a più fattori per l'account User 2.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera testare l'autenticazione a più fattori in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Se si verifica l'autenticazione a più fattori, non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2

Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:
  
1. Aprire un'istanza separata, privata del browser, accedere all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) e quindi accedere con l'account di amministratore globale.
    
2. Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.
    
3. Nel riquadro utenti attivi, fare clic su **altre > configurazione dell'autenticazione a più fattori**.
    
4. Nell'elenco, selezionare l'account **User 2** .
    
5. Nella sezione **User 2**, sotto **Azioni rapide**, fare clic su **Abilita**.
    
6. Nella finestra di dialogo **Informazioni sull'abilitazione dell'autenticazione più fattori** fare clic su **Abilita Multi-Factor Auth**.
    
7. Nella finestra di dialogo **aggiornamenti con esito positivo** fare clic su **Chiudi**.
    
8. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona dell'account utente in alto a destra, quindi fare clic su **Esci**.
    
9. Chiudere l'istanza del browser.
   
Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:
  
1. Aprire una nuova istanza privata del browser.
    
2. Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) ed eseguire l'accesso con il nome e la password dell'account utente 2.
    
3. Dopo aver eseguito l'accesso, viene richiesto di configurare l'account per ulteriori informazioni. Fare clic su **Avanti**.
    
4. Nella pagina **Verifica aggiuntiva di sicurezza**:
    
   - Selezionare il paese o l'area geografica.
    
   - Digitare il numero di telefono dello smartphone che riceverà i messaggi di testo.
    
   - In **Metodo**, fare clic su **Inviami un codice tramite messaggio di testo**.
    
5. Fare clic su **Avanti**.
    
6. Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone e quindi fare clic su **Verifica**.
    
7. Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti**, annotare la password dell'app visualizzata per l'account User 2 in una posizione sicura e fare clic su **Fine**.
    
8. Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Digitare la password originale e una nuova password due volte, quindi fare clic su **Aggiornare la password ed eseguire l'accesso**. Annotare nome e password in una posizione sicura.
    
    Verrà visualizzato il portale di Office per l'utente 2 nella scheda **Microsoft Office Home** del browser.


Per informazioni e collegamenti per la distribuzione dell'autenticazione a più fattori in produzione, vedere la procedura di [configurazione dell'autenticazione](identity-multi-factor-authentication.md#identity-mfa) a più fattori nella fase Identity.
    
## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
