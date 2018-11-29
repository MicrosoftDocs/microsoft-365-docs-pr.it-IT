---
title: Ambiente di testing di autenticazione a più fattori per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a Smartphone nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868281"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente di testing di autenticazione a più fattori per la propria azienda 365 Microsoft

Per un livello aggiuntivo di protezione per l'accesso a Office 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure Active Directory per l'organizzazione, è possibile abilitare l'autenticazione multifattore Azure, che richiede più di solo un nome utente e una password per verificare un account. Con l'autenticazione a più fattori, sono necessari per confermare una telefonata, digitare un codice di verifica inviato un messaggio di testo o specificare una password di app per i telefoni smart dopo aver immesso correttamente le password degli utenti. È possibile accedere solo dopo che è state soddisfatte questo secondo fattore di autenticazione. 
  
In questo articolo viene descritto come attivare e testare l'autenticazione basata su messaggi di testo per un account specifico.
  
Esistono due fasi di configurazione dell'autenticazione a più fattori per un account nell'ambiente di test Microsoft 365 aziendale:
  
1. Creare l'ambiente di test Microsoft 365 Enterprise.
    
2. Abilitare e testare l'autenticazione a più fattori per l'account User 2.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera testare l'autenticazione a più fattori in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test dell'autenticazione a più fattori non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare l'autenticazione a più fattori e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2

Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:
  
1. Aprire un'istanza privata separata del browser, accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) e quindi accedere con l'account amministratore globale.
    
2. Dalla pagina principale del portale, fare clic su **Admin**.
    
3. Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.
    
4. Nel riquadro utenti attivi, fare clic su **più > configurazione di autenticazione a più fattori**.
    
5. Nell'elenco, selezionare l'account **utente 2** .
    
6. Nella sezione **User 2**, sotto **Azioni rapide**, fare clic su **Abilita**.
    
7. Nella finestra di dialogo **Informazioni sull'abilitazione dell'autenticazione più fattori** fare clic su **Abilita Multi-Factor Auth**.
    
8. Nella finestra di dialogo **Aggiorna completata** fare clic su **Chiudi**.
    
9. Nella scheda **Microsoft Office Home** fare clic sull'icona dell'account utente in alto a destra, quindi fare clic su **Disconnetti**.
    
10. Chiudere l'istanza del browser.
   
Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:
  
1. Aprire una nuova istanza del browser privata.
    
2. Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) e accedere con l'account utente 2 (user2 @\<nome organizzazione >. onmicrosoft.com) e una password.
    
3. Dopo l'accesso, viene chiesto di configurare l'account per ulteriori informazioni. Fare clic su **Avanti**.
    
4. Nella pagina **Verifica aggiuntiva di sicurezza**:
    
   - Selezionare il paese o l'area geografica.
    
   - Digitare il numero di telefono dello smartphone che riceverà i messaggi di testo.
    
   - Nel **metodo**, fare clic su **Invia automaticamente un codice di un messaggio**.
    
5. Fare clic su **Avanti**.
    
6. Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone e quindi fare clic su **Verifica**.
    
7. Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti**, annotare la password dell'app visualizzata per l'account User 2 in una posizione sicura e fare clic su **Fine**.
    
8. Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Digitare la password originale e una nuova password due volte, quindi fare clic su **Aggiornare la password ed eseguire l'accesso**. Annotare nome e password in una posizione sicura.
    
    È consigliabile vedere portale di Office 365 per l'utente 2 nella scheda **Home page di Microsoft Office** del browser.


Nella fase di identità per informazioni e collegamenti per distribuire l'autenticazione a più fattori nell'ambiente di produzione, vedere la sezione [configurare l'autenticazione a più fattori](identity-multi-factor-authentication.md) .
    
## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
