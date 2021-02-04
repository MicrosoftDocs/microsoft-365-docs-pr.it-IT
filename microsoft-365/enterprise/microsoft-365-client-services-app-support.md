---
title: Supporto per app client e servizi di Microsoft 365
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
description: In questo articolo sono disponibili informazioni dettagliate sul supporto delle app client e servizi di Microsoft 365.
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097477"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Supporto per app client e servizi di Microsoft 365

Microsoft supporta un'ampia gamma di funzionalità di sicurezza, autenticazione e conformità per mantenere al sicuro i dati dei clienti e consente agli amministratori IT di personalizzare i criteri nell'interfaccia di amministrazione di Microsoft 365 per gli utenti. Le funzionalità seguenti sono solo un sottoinsieme delle numerose funzionalità aziendali che è possibile configurare in base all'abbonamento a Microsoft 365.

## <a name="client-and-service-support"></a>Supporto per client e servizi

### <a name="continuous-access-evaluation-preview"></a>Valutazione dell'accesso continuo (anteprima)

La valutazione dell'accesso continuo viene implementata abilitando servizi come Exchange Online, SharePoint Online e Teams a sottoscrivere eventi critici in Azure Active Directory in modo che tali eventi possano essere valutati e applicati quasi in tempo reale. La valutazione degli eventi critici non si basa sui criteri di accesso condizionale, pertanto è disponibile in qualsiasi tenant.

Attualmente vengono valutati gli eventi seguenti:

- Un account utente viene eliminato o disabilitato
- La password di un utente viene modificata o reimpostata
- L'autenticazione a più fattori è abilitata per l'utente
- L'amministratore revoca esplicitamente tutti i token di aggiornamento per un utente
- Rischio utente con privilegi elevati rilevato da Azure AD Identity Protection

Per altre informazioni sulla valutazione dell'accesso continuo per il supporto delle app client e servizi, vedi [Valutazione dell'accesso continuo (anteprima).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Supporto client

### <a name="certificate-based-authentication"></a>Autenticazione basata sui certificati

L'autenticazione basata su certificato (CBA) è l'uso di un certificato digitale per identificare un utente, un computer o un dispositivo prima di concedere l'accesso a una risorsa, una rete, un'applicazione o un servizio. Nell'autenticazione utente, viene spesso distribuita in coordinamento con i metodi tradizionali come nomi utente e password.

Alcune soluzioni tradizionali funzionano solo per gli utenti, ad esempio la biometria e le password una sola volta (OTP). Con l'autenticazione basata su certificati, la stessa soluzione può essere usata per tutti gli endpoint; utenti, dispositivi e internet delle cose (IoT) in crescita.

Per ulteriori informazioni sull'autenticazione basata su certificati per il supporto delle app client e servizi, vedere Supporto app client [di Microsoft 365: autenticazione basata su certificati.](microsoft-365-client-support-certificate-based-authentication.md)

### <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è lo strumento usato da Azure Active Directory per riunire i segnali, prendere decisioni e applicare i criteri di accesso dell'organizzazione. L'accesso condizionale è alla base del nuovo modello di controllo basato sull'identità.

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
    - Il dispositivo da contrassegnato come conforme
    - Il dispositivo è aggiunto ad Azure AD ibrido
    - Un'app client approvata
    - Criteri di protezione delle app configurati (anteprima)

Per altre informazioni sull'accesso condizionale per il supporto delle app client e servizi, vedi:

- [Supporto app client Microsoft 365: accesso condizionale basato su dispositivo](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Gestione di applicazioni mobili

Gli utenti spesso accedono sia ai documenti personali che all'organizzazione, alla posta elettronica e ai dati dallo stesso dispositivo mobile. Questi dispositivi sono spesso di proprietà personale e devono essere configurati per proteggere sia i dati dell'organizzazione che la privacy personale dell'utente.

Quando un utente accede ai dati dell'organizzazione, l'organizzazione deve essere certo che i criteri dell'organizzazione, ad esempio i criteri di configurazione e i criteri di protezione, siano applicati per proteggere i dati dell'organizzazione nel dispositivo. Inoltre, il contenuto personale dell'utente nel dispositivo deve rimanere al di fuori del controllo dell'organizzazione.

Per i contenuti gestiti dall'organizzazione, è possibile applicare criteri di gestione delle applicazioni per controllare la modalità di accesso, condivisione e uso dei dati tramite Microsoft Intune. Ad esempio, sono supportate le azioni seguenti:

- Cancellazione remota del contenuto dell'organizzazione gestita (anche riferimento ai dati dell'organizzazione)
- Impedisci incollamento del contenuto dell'organizzazione in posizioni non dell'organizzazione
- Richiedere un PIN per accedere al contenuto dell'organizzazione
- Impedire l'esecuzione di app gestite su dispositivi jailbroken o rooted
- Impedire che il contenuto dell'organizzazione venga salvato in provider di archiviazione cloud non approvati
- Impedire il trasferimento di contenuto non approvato in applicazioni gestite
- Consentire l'accesso al contenuto dell'organizzazione solo dopo l'applicazione dei criteri
- Fornire la configurazione dell'applicazione per gestire il comportamento e le impostazioni dell'applicazione
- Limitare l'applicazione gestita a un'identità definita disabilitando le funzionalità con più identità o l'utilizzo personale

Per altre informazioni sulla gestione delle applicazioni mobili con Microsoft Intune, vedere [Che cos'è la gestione delle app di Microsoft Intune?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Autenticazione a più fattori

[L'autenticazione a più fattori (MFA) è un metodo di controllo dell'accesso al computer in cui a un utente viene concesso l'accesso solo dopo la corretta presentazione di diverse prove separate a un meccanismo di autenticazione. Questo metodo utilizza in genere almeno due delle categorie seguenti:

- Conoscenza (qualcosa che conoscono)
- Possesso (qualcosa che hanno)
- Coerenza (qualcosa che è)

Per ulteriori informazioni sull'autenticazione a più fattori per il supporto delle app client e servizi, vedere Supporto app [client di Microsoft 365: autenticazione a più fattori.](microsoft-365-client-support-multi-factor-authentication.md)

### <a name="single-sign-on"></a>Single Sign-On

Single #A0 (SSO) aggiunge sicurezza e comodità quando gli utenti a utilizzano le applicazioni in Azure Active Directory. Con Single #A0 gli utenti accedono una sola volta con un account per accedere ai dispositivi aggiunti al dominio di Servizi di dominio Active Directory locali, alle applicazioni Software as a Service (SaaS) e alle applicazioni Web nell'organizzazione.

Per ulteriori informazioni sul servizio Single #A0 per il supporto delle app client e servizi, vedere Supporto app client [Di Microsoft 365: Single #A0](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Supporto dei servizi

### <a name="modern-authentication"></a>Autenticazione moderna

L'autenticazione moderna consente ai nuovi scenari per i clienti di eseguire l'autenticazione in Office 365 e agli amministratori tenant di applicare requisiti di autenticazione specifici per la tenancy di Office 365, ad esempio:

- Supporto dell'autenticazione a più fattori per l'interazione amministrativa con tenancy e servizi e l'interazione dell'utente finale con le applicazioni e i relativi dati
- Accesso condizionale
- Accesso al provider di identità di terze parti basato su SAML
- Accesso smart card nei personal computer
- Autenticazione basata su certificati nei dispositivi mobili
- Non è più necessaria la trasmissione delle credenziali tramite l'autenticazione di base.

Per ulteriori informazioni sul supporto dei servizi di autenticazione moderna, vedere [Autenticazione e autorizzazione.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Accesso condizionale di Azure Active Directory

Le regole di accesso condizionale di Azure Active Directory (Azure AD) consentono ai clienti di controllare l'accesso ai servizi online, in base ad attributi come la conformità del dispositivo o il percorso di rete. È possibile utilizzare le soluzioni seguenti:

- Accesso condizionale basato sull'autenticazione a più fattori di Azure AD
- Accesso condizionale basato sulla posizione di Azure AD
- Accesso condizionale basato su dispositivo di Azure AD

Le regole di accesso condizionale di Azure AD vengono applicate per ogni applicazione e sono disponibili per i clienti per controllare l'accesso in base a condizioni diverse. Con Gestione di dispositivi mobili [(MDM)](/mem/intune/fundamentals/what-is-device-management)o Intune, i clienti devono essere in grado di limitare l'accesso a Microsoft 365 solo agli utenti che usano un dispositivo dell'organizzazione o che hanno registrato il proprio dispositivo personale per la gestione. Ad esempio, i clienti possono configurare le regole di accesso condizionale per applicare controlli come:

- Consentire l'accesso solo da dispositivi aggiunti a un dominio o conformi al dominio
- Applicare l'autenticazione a più fattori per tutti gli accessi ai servizi di Exchange Online

Per ulteriori informazioni sull'accesso condizionale di Azure Active Directory, vedere [Che cos'è l'accesso condizionale?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Supporto di TLS 1.2

Per fornire la crittografia migliore ai clienti, Microsoft prevede di interrompere il supporto per transport layer security (TLS) versioni 1.0 e 1.1 in Office 365 e Office 365 GCC.

Sappiamo bene che la sicurezza dei dati è importante e facciamo tutto il possibile per garantire trasparenza in merito alle modifiche che potrebbero influire sull'uso del servizio TLS. È consigliabile che tutte le combinazioni client-server e browser-server utilizzino TLS 1.2 (o versione successiva) per mantenere la connessione ai servizi di Office 365. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server.

Per ulteriori informazioni sul supporto di TLS 1.2 e sui servizi, vedere Preparazione di [TLS 1.2 in Office 365 e Office 365 GCC.](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)
