---
title: Autenticazione a più fattori dell'ambiente di testing di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Configurare l'autenticazione a più fattori utilizzando messaggi di testo inviati a uno smartphone nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558443"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per Office 365 Enterprise.*

Per un ulteriore livello di sicurezza per l'accesso a Microsoft 365 o a qualsiasi servizio o applicazione che usa il tenant di Azure AD per l'abbonamento, è possibile abilitare l'autenticazione a più fattori di Azure AD, che richiede più di un nome utente e una password per verificare un account.

Con l'autenticazione a più fattori, gli utenti devono confermare una chiamata telefonica, digitare un codice di verifica inviato in un SMS o verificare l'autenticazione con un'app sullo smartphone dopo aver immesso correttamente le password. Possono accedere solo dopo aver soddisfatto questo secondo fattore di autenticazione.
  
In questo articolo viene descritto come abilitare e testare l'autenticazione basata su SMS per un account utente specifico.
  
La configurazione dell'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi e una terza fase facoltativa:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera semplicemente testare l'autenticazione a più fattori in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se si desidera testare l'autenticazione a più fattori in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test dell'autenticazione a più fattori non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2

Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:
  
1. Aprire un'istanza privata separata del browser, passare all'interfaccia di amministrazione di Microsoft 365 ( ) e quindi accedere [https://portal.microsoft.com](https://portal.microsoft.com) con l'account amministratore globale.
    
2. Nel riquadro di spostamento sinistro selezionare **Utenti**  >  **attivi.**
    
3. Nel riquadro Utenti attivi selezionare **Autenticazione a più fattori.**
    
4. Nell'elenco, selezionare **l'account User 2.**
    
5. Nella sezione **User 2** selezionare **Enable** in **Quick steps.**
    
6. Nella finestra **di dialogo Informazioni sull'abilitazione dell'autenticazione** a più fattori selezionare Abilita autenticazione a più **fattori.**
    
7. Nella finestra **di dialogo Aggiornamenti** riusciti selezionare **Chiudi.**
    
8. Nella scheda dell'interfaccia di amministrazione di **Microsoft 365** selezionare l'icona dell'account utente in alto a destra e quindi **selezionare Disconnetto.**
    
9. Chiudere l'istanza del browser.
   
Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:
  
1. Aprire una nuova istanza privata del browser.
    
2. Passare all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) e accedere con il nome account utente 2 e la password.
    
3. Dopo l'accesso, viene richiesto di configurare l'account per ulteriori informazioni. Selezionare **Avanti**.
    
4. Nella pagina **Verifica aggiuntiva di sicurezza**:
    
   - Selezionare il paese o l'area geografica.
    
   - Immettere il numero di telefono dello smartphone che riceverà messaggi di testo.
    
   - Nel **metodo** selezionare **Invia un codice tramite messaggio di testo.**
    
5. Selezionare **Avanti**.
    
6. Immetti il codice di verifica dal messaggio di testo ricevuto sullo smartphone e quindi seleziona **Verifica.**
    
7. Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti** selezionare **Fatto.**
    
8. Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Immettere la password originale e una nuova password due volte, quindi selezionare **Aggiorna password ed eseguire l'accesso.** Annotare nome e password in una posizione sicura.
    
    Il portale di Office per User 2 dovrebbe essere visualizzato **nella Microsoft Office Home** del browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale

*Questa fase può essere usata solo per un ambiente di testing di Microsoft 365 per le aziende.*

In questa fase, si abilita l'autenticazione a più fattori per l'account User 3 utilizzando un gruppo e un criterio di accesso condizionale.

Successivamente, crea un nuovo gruppo denominato MFAUsers e aggiungi l'account User 3.

1. Nella scheda **dell'interfaccia di amministrazione di Microsoft 365** selezionare Gruppi **nel** riquadro di spostamento sinistro e quindi **selezionare Gruppi.**
2. Selezionare **Aggiungi gruppo.**
3. Nel riquadro **Scegliere un tipo di** gruppo selezionare **Sicurezza** e quindi fare clic su **Avanti.**
4. Nel riquadro **Set up the basics** selezionare **Create group** e quindi **close.**
5. Nel riquadro **Rivedere e completare l'aggiunta del** gruppo, immettere **MFAUsers** e quindi selezionare **Avanti.**
6. Nell'elenco dei gruppi, selezionare il **gruppo MFAUsers.**
7. Nel riquadro **MFAUsers** selezionare **Membri** e quindi selezionare **Visualizza tutti e gestisci membri.**
8. Nel riquadro **MFAUsers** seleziona **Aggiungi membri,** seleziona l'account **User 3** e quindi seleziona **Salva**  >  **chiudi.**  >  

Successivamente, creare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per i membri del gruppo MFAUsers.

1. In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .
2. Selezionare **Accesso condizionale per la sicurezza** di Azure Active  >    >  Directory.
3. Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**
4. Nel riquadro **Nuovo** immettere **MFA per gli account utente** nella **casella** Nome.
5. Nella sezione **Assegnazioni** selezionare **Utenti e gruppi.**
6. Nella scheda **Includi** del **riquadro** Utenti e gruppi selezionare **Seleziona** utenti e  >  **gruppi.**  >  
7. Nel riquadro **Select** selezionare il gruppo **MFAUsers** e quindi **selezionare Select**  >  **Done.**
8. Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi.**
9. Nel riquadro **Concedi** selezionare Richiedi autenticazione a **più fattori** e quindi selezionare **Seleziona.**
10. Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea.**
11. Chiudere il **portale di Azure e** le schede dell'interfaccia di amministrazione di Microsoft **365.**

Per testare questo criterio, disconnettersi e accedere con l'account User 3. Dovrebbe essere richiesto di configurare l'autenticazione a più fattori. Ciò dimostra che il criterio MFAUsers viene applicato.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
