---
title: Microsoft 365 client e servizi di supporto app
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In questo articolo troverai informazioni dettagliate sul supporto Microsoft 365 app client e servizi.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905009"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 client e servizi di supporto app

Microsoft supporta un'ampia gamma di funzionalità di sicurezza, autenticazione e conformità per mantenere al sicuro i dati dei clienti e consente agli amministratori IT di personalizzare i criteri nell'interfaccia di amministrazione di Microsoft 365 per gli utenti. Le funzionalità seguenti sono solo un sottoinsieme delle numerose funzionalità aziendali che è possibile configurare a seconda dell'Microsoft 365 abbonamento.

## <a name="client-and-service-support"></a>Supporto per client e servizi

### <a name="continuous-access-evaluation-preview"></a>Valutazione dell'accesso continuo (anteprima)

La valutazione dell'accesso continuo viene implementata consentendo ai servizi, come Exchange Online, SharePoint Online e Teams, di sottoscrivere eventi critici in Azure Active Directory in modo che tali eventi possano essere valutati e applicati quasi in tempo reale. La valutazione degli eventi critici non si basa sui criteri di accesso condizionale, pertanto è disponibile in qualsiasi tenant.

Attualmente vengono valutati gli eventi seguenti:

- Un account utente viene eliminato o disabilitato
- La password di un utente viene modificata o reimpostata
- L'autenticazione a più fattori è abilitata per l'utente
- L'amministratore revoca esplicitamente tutti i token di aggiornamento per un utente
- Rischio utente elevato rilevato da Azure AD Identity Protection

Per altre informazioni sulla valutazione dell'accesso continuo per il supporto delle app client e servizi, vedi [Valutazione dell'accesso continuo (anteprima).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Supporto client

### <a name="certificate-based-authentication"></a>Autenticazione basata sui certificati

L'autenticazione basata su certificato è l'utilizzo di un certificato digitale per identificare un utente, un computer o un dispositivo prima di concedere l'accesso a una risorsa, una rete, un'applicazione o un servizio. Nell'autenticazione utente, viene spesso distribuito in coordinamento con i metodi tradizionali, ad esempio nomi utente e password.

Alcune soluzioni tradizionali funzionano solo per gli utenti, ad esempio biometria e password una sola volta (OTP). Con l'autenticazione basata su certificato, è possibile utilizzare la stessa soluzione per tutti gli endpoint. utenti, dispositivi e l'Internet delle cose (IoT) in crescita.

Per altre informazioni sull'autenticazione basata su certificati per il supporto delle app client e servizi, vedi Microsoft 365 [Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).

### <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è lo strumento utilizzato da Azure Active Directory per riunire i segnali, prendere decisioni e applicare i criteri di accesso dell'organizzazione. L'accesso condizionale è alla base del nuovo modello di controllo basato sull'identità.

I criteri di accesso condizionale sono istruzioni if-then per concedere l'accesso alle risorse. Se un utente desidera accedere a una risorsa, l'utente deve completare un'azione. I segnali comuni che l'accesso condizionale può usare per prendere una decisione di accesso ai criteri includono:

- Appartenenza a utenti o gruppi
- Informazioni sulla posizione IP
- Informazioni sul dispositivo
- Informazioni sull'applicazione
- Rilevamento dei rischi in tempo reale e calcolato
- Microsoft Cloud App Security (MCAS)

Quando si prendono queste decisioni di accesso, i criteri possono eseguire azioni diverse:

- Il criterio può bloccare l'accesso: questa configurazione è l'azione più restrittiva e impedisce all'utente di accedere alla risorsa.
- Il criterio può concedere l'accesso: questa configurazione è una decisione meno restrittiva e potrebbe comunque richiedere una o più delle opzioni seguenti:

    - Autenticazione a più fattori
    - Dispositivo da contrassegnato come conforme
    - Il dispositivo è aggiunto ad Azure AD ibrido
    - App client approvata
    - Criteri di protezione delle app configurati (anteprima)

Per altre informazioni sull'accesso condizionale per il supporto delle app client e servizi, vedi:

- [Microsoft 365 Supporto app client: accesso condizionale basato su dispositivo](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Mobile Application Management

Gli utenti spesso accedono sia ai documenti personali che all'organizzazione, alla posta elettronica e ai dati dallo stesso dispositivo mobile. Questi dispositivi sono spesso di proprietà personale e devono essere configurati per proteggere sia i dati dell'organizzazione che la privacy personale dell'utente.

Quando un utente accede ai dati dell'organizzazione, l'organizzazione deve essere sicura che i criteri dell'organizzazione, ad esempio i criteri di configurazione e i criteri di protezione, siano applicati per proteggere i dati dell'organizzazione nel dispositivo. Inoltre, il contenuto personale dell'utente nel dispositivo deve rimanere al di fuori del controllo dell'organizzazione.

Per il contenuto gestito dall'organizzazione, è possibile applicare criteri di gestione delle applicazioni per controllare la modalità di accesso, condivisione e utilizzo dei dati tramite Microsoft Intune. Ad esempio, sono supportate le azioni seguenti:

- Cancellazione remota del contenuto dell'organizzazione gestita (noto anche come dati dell'organizzazione)
- Impedire l'incollamento del contenuto dell'organizzazione in posizioni non dell'organizzazione
- Richiedere un PIN per accedere al contenuto dell'organizzazione
- Impedire l'esecuzione delle app gestite nei dispositivi jailbroken o rooted
- Impedire il salvataggio del contenuto dell'organizzazione nei provider di archiviazione cloud non approvati
- Impedire il trasferimento di contenuto non approvato in applicazioni gestite
- Consentire l'accesso al contenuto dell'organizzazione solo dopo l'applicazione dei criteri
- Distribuire la configurazione dell'applicazione per gestire il comportamento e le impostazioni dell'applicazione
- Limitare l'applicazione gestita a un'identità definita disabilitando le funzionalità con più identità o l'utilizzo personale

Per altre informazioni sulla gestione delle applicazioni mobili con Microsoft Intune, vedi [Che cos'è](/mem/intune/apps/app-management) Microsoft Intune gestione delle app?

### <a name="multi-factor-authentication"></a>Autenticazione a più fattori

[L'autenticazione a più fattori (MFA) è un metodo di controllo dell'accesso al computer in cui a un utente viene concesso l'accesso solo dopo aver presentato correttamente diverse prove separate a un meccanismo di autenticazione. Questo metodo in genere utilizza almeno due delle categorie seguenti:

- Conoscenza (qualcosa che sanno)
- Possesso (qualcosa che hanno)
- Inerenza (qualcosa che sono)

Per altre informazioni sull'autenticazione a più fattori per il supporto delle app client e servizi, vedi Microsoft 365 [Client App Support: Multi-Factor Authentication.](microsoft-365-client-support-multi-factor-authentication.md)

### <a name="single-sign-on"></a>Single Sign-On

Single Sign-On (SSO) aggiunge sicurezza e praticità quando gli utenti a questo punto a loro volta a Azure Active Directory. Con l'accesso Single Sign-on, gli utenti accedono una sola volta con un account per accedere ai dispositivi aggiunti al dominio di Servizi di dominio Active Directory locali, alle applicazioni SaaS (Software as a Service) e alle applicazioni Web nell'organizzazione.

Per ulteriori informazioni sul servizio Single #A0 per il supporto delle app client e servizi, vedere Microsoft 365 [Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Supporto dei servizi

### <a name="modern-authentication"></a>Autenticazione moderna

L'autenticazione moderna consente ai nuovi scenari per i clienti di eseguire l'autenticazione Office 365 e per gli amministratori tenant di applicare requisiti di autenticazione specifici nella tenancy Office 365, ad esempio:

- Supporto dell'autenticazione a più fattori per l'interazione amministrativa con la tenancy e i servizi e l'interazione dell'utente finale con le applicazioni e i relativi dati
- Accesso condizionale
- Accesso al provider di identità di terze parti basato su SAML
- Registro smart card nei personal computer
- Autenticazione basata su certificati nei dispositivi mobili
- Non è più necessaria la trasmissione delle credenziali tramite l'autenticazione di base.

Per ulteriori informazioni sul supporto dei servizi di autenticazione moderni, vedere [Autenticazione e autorizzazione.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Accesso condizionale di Azure Active Directory

Azure Active Directory (Azure AD) Le regole di accesso condizionale consentono ai clienti di controllare l'accesso ai servizi online, in base ad attributi quali la conformità dei dispositivi o il percorso di rete. È possibile utilizzare le soluzioni seguenti:

- Accesso condizionale basato sull'autenticazione a più fattori di Azure AD
- Accesso condizionale basato sulla posizione di Azure AD
- Accesso condizionale basato su dispositivo di Azure AD

Le regole di accesso condizionale di Azure AD vengono applicate per applicazione e sono disponibili per i clienti per controllare l'accesso in base a condizioni diverse. Usando [Gestione dispositivi mobili (MDM)](/mem/intune/fundamentals/what-is-device-management)o Intune, i clienti devono essere in grado di limitare l'accesso a Microsoft 365 solo agli utenti che usano un dispositivo dell'organizzazione o che hanno registrato il proprio dispositivo personale per la gestione. Ad esempio, i clienti possono configurare le regole di accesso condizionale per applicare controlli quali:

- Consentire solo l'accesso da dispositivi aggiunti a un dominio o conformi al dominio
- Applicare l'autenticazione a più fattori per tutti gli accessi Exchange Online servizi

Per ulteriori informazioni sull'Azure Active Directory condizionale, vedere [Che cos'è l'accesso condizionale?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Supporto tls 1.2

Per fornire la crittografia più avanzata ai clienti, Microsoft prevede di interrompere il supporto per Transport Layer Security (TLS) versioni 1.0 e 1.1 in Office 365 e Office 365 GCC.

Sappiamo bene che la sicurezza dei dati è importante e facciamo tutto il possibile per garantire trasparenza in merito alle modifiche che potrebbero influire sull'uso del servizio TLS. È consigliabile che tutte le combinazioni client-server e browser-server utilizzino TLS 1.2 (o versione successiva) per mantenere la connessione Office 365 servizi. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server.

Per ulteriori informazioni sul supporto di TLS 1.2 e sui servizi, vedere [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).