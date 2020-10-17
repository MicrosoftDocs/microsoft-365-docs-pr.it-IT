---
title: Microsoft 365 per l'autenticazione a più fattori dell'ambiente di testing dell'organizzazione
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
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a uno Smart Phone nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487141"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Per un ulteriore livello di sicurezza per l'accesso a Microsoft 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure AD per l'abbonamento, è possibile abilitare l'autenticazione a più fattori di Azure, che richiede più di un semplice nome utente e una password per verificare un account.

Con l'autenticazione a più fattori, agli utenti viene richiesto di riconoscere una telefonata, digitare un codice di verifica inviato in un messaggio di testo oppure verificare l'autenticazione con un'app nei rispettivi smartphone dopo aver inserito correttamente le password. È possibile effettuare l'accesso solo dopo aver soddisfatto questo secondo fattore di autenticazione.
  
In questo articolo viene descritto come abilitare e testare l'autenticazione basata su messaggi di testo per un account utente specifico.
  
La configurazione dell'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 per l'organizzazione implica due fasi e una terza fase facoltativa:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera testare l'autenticazione a più fattori in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Se si verifica l'autenticazione a più fattori, non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2

Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:
  
1. Aprire un'istanza separata, privata del browser, accedere all'interfaccia di amministrazione di Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e quindi accedere con l'account di amministratore globale.
    
2. Nel riquadro di spostamento a sinistra **, selezionare utenti**  >  **attivi**.
    
3. Nel riquadro utenti attivi selezionare autenticazione a più **fattori**.
    
4. Nell'elenco, selezionare l'account **User 2** .
    
5. Nella sezione **User 2** fare clic su **Abilita**in **passaggi rapidi**.
    
6. Nella finestra **di dialogo informazioni sull'abilitazione dell'autenticazione** a più fattori selezionare **Abilita autenticazione**a più fattori.
    
7. Nella finestra di dialogo **aggiornamenti con esito positivo** selezionare **Chiudi**.
    
8. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare l'icona dell'account utente in alto a destra, quindi selezionare **Disconnetti**.
    
9. Chiudere l'istanza del browser.
   
Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:
  
1. Aprire una nuova istanza privata del browser.
    
2. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e accedere con il nome e la password dell'account utente 2.
    
3. Dopo aver eseguito l'accesso, viene richiesto di configurare l'account per ulteriori informazioni. Selezionare **Avanti**.
    
4. Nella pagina **Verifica aggiuntiva di sicurezza**:
    
   - Selezionare il paese o l'area geografica.
    
   - Immettere il numero di telefono dello Smart Phone che riceverà i messaggi di testo.
    
   - In **Metodo**selezionare **Invia un codice tramite messaggio di testo**.
    
5. Selezionare **Avanti**.
    
6. Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone, quindi selezionare **Verifica**.
    
7. Nella pagina **passaggio 3: mantenere le applicazioni esistenti** , selezionare **fine**.
    
8. Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Immettere due volte la password originale e una nuova password, quindi selezionare **Aggiorna password e accedi**. Annotare nome e password in una posizione sicura.
    
    Verrà visualizzato il portale di Office per l'utente 2 nella scheda **Microsoft Office Home** del browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale

*Questa fase può essere utilizzata solo per un ambiente di testing di Microsoft 365 per l'organizzazione.*

In questa fase, è possibile abilitare l'autenticazione a più fattori per l'account User 3 utilizzando un gruppo e un criterio di accesso condizionale.

Successivamente, creare un nuovo gruppo denominato MFAUsers e aggiungere l'account User 3.

1. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare **gruppi** nel riquadro di spostamento sinistro e quindi selezionare **gruppi**.
2. Selezionare **Aggiungi un gruppo**.
3. Nel riquadro **scegliere un tipo di gruppo** , selezionare **sicurezza**, quindi fare clic su **Avanti**.
4. Nel riquadro **Configura le nozioni di base** , selezionare **Crea gruppo**e quindi **Chiudi**.
5. Nel riquadro **revisione e termina aggiunta gruppo** , immettere **MFAUsers**, quindi fare clic su **Avanti**.
6. Nell'elenco dei gruppi, selezionare il gruppo **MFAUsers** .
7. Nel riquadro **MFAUsers** , selezionare **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.
8. Nel riquadro **MFAUsers** , selezionare **Aggiungi membri**, selezionare l'account **User 3** e quindi fare clic su **Salva**  >  **Chiudi**  >  **Chiudi**.

Successivamente, creare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per i membri del gruppo MFAUsers.

1. In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com) .
2. Selezionare **Azure Active Directory**  >  **Security**  >  **l'accesso condizionale**per la sicurezza di Azure Active Directory.
3. Nel riquadro **criteri di accesso condizionale** selezionare **nuovo criterio**.
4. Nel **nuovo** riquadro, immettere **AMF per gli account utente** nella casella **nome** .
5. Nella sezione **assegnazioni** selezionare **utenti e gruppi**.
6. Nella scheda **Includi** del riquadro **utenti e gruppi** Selezionare Seleziona utenti e **gruppi utenti e**  >  **gruppi**  >  **Select**.
7. Nel riquadro **Seleziona** selezionare il gruppo **MFAUsers** e **quindi selezionare**  >  **fine**.
8. Nella sezione **controlli di accesso** del **nuovo** riquadro selezionare **Concedi**.
9. Nel riquadro **Concedi** selezionare **Richiedi autenticazione**a più fattori e quindi selezionare **Seleziona**.
10. Nel **nuovo** riquadro, selezionare attivato **per** **attivare il criterio**, quindi selezionare **Crea**.
11. Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .

Per testare questo criterio, disconnettersi e accedere con l'account User 3. È necessario che venga richiesto di configurare l'autenticazione master. Questo dimostra che è in corso l'applicazione del criterio MFAUsers.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
