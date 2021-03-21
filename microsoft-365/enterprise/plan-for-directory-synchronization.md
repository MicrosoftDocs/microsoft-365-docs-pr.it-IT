---
title: Identità ibrida e sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Descrive la sincronizzazione della directory con Microsoft 365, pulizia di Servizi di dominio Active Directory e lo strumento Azure Active Directory Connect.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927545"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Identità ibrida e sincronizzazione della directory per Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

A seconda delle esigenze aziendali e dei requisiti tecnici, il modello di identità ibrido e la sincronizzazione della directory sono la scelta più comune per i clienti aziendali che adottano Microsoft 365. La sincronizzazione della directory consente di gestire le identità in Servizi di dominio Active Directory e tutti gli aggiornamenti ad account utente, gruppi e contatti vengono sincronizzati con il tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365.

>[!Note]
>Quando gli account utente di Servizi di dominio Active Directory vengono sincronizzati per la prima volta, non vengono assegnati automaticamente una licenza di Microsoft 365 e non possono accedere ai servizi di Microsoft 365, ad esempio la posta elettronica. È innanzitutto necessario assegnare loro una posizione di utilizzo. Assegnare quindi una licenza a questi account utente, singolarmente o dinamicamente tramite l'appartenenza al gruppo.
>

## <a name="authentication-for-hybrid-identity"></a>Autenticazione per l'identità ibrida

Quando si utilizza il modello di identità ibrido, esistono due tipi di autenticazione:

- Autenticazione gestita

  Azure AD gestisce il processo di autenticazione utilizzando una versione con hash archiviata localmente della password o invia le credenziali a un agente software locale per essere autenticato da Servizi di dominio Active Directory locale.

- Autenticazione federata

  Azure AD reindirizza il computer client che richiede l'autenticazione a un altro provider di identità.

### <a name="managed-authentication"></a>Autenticazione gestita

Esistono due tipi di autenticazione gestita:

- Sincronizzazione dell'hash delle password (PHS)

  L'autenticazione viene eseguita direttamente da Azure AD.

- Autenticazione pass-through (PTA)

  L'autenticazione di Azure AD viene eseguita da AD DS.


#### <a name="password-hash-synchronization-phs"></a>Sincronizzazione dell'hash delle password (PHS)

Con PHS, sincronizzare gli account utente di Servizi di dominio Active Directory con Microsoft 365 e gestire gli utenti in locale. Gli hash delle password utente vengono sincronizzati da Servizi di dominio Active Directory ad Azure AD in modo che gli utenti hanno la stessa password in locale e nel cloud. Questo è il modo più semplice per abilitare l'autenticazione per le identità di Servizi di dominio Active Directory in Azure AD. 

![Sincronizzazione dell'hash delle password (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

Quando le password vengono modificate o reimpostate in locale, i nuovi hash delle password vengono sincronizzati con Azure AD in modo che gli utenti possano sempre usare la stessa password per le risorse cloud e le risorse locali. Le password utente non vengono mai inviate ad Azure AD o archiviate in Azure AD in testo non crittografato. Alcune funzionalità premium di Azure AD, ad esempio Identity Protection, richiedono PHS indipendentemente dal metodo di autenticazione selezionato.
  
Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.
  
#### <a name="pass-through-authentication-pta"></a>Autenticazione pass-through (PTA)

PTA fornisce una semplice convalida delle password per i servizi di autenticazione di Azure AD usando un agente software in esecuzione su uno o più server locali per convalidare gli utenti direttamente con Servizi di dominio Active Directory. Con PTA, sincronizzare gli account utente di Servizi di dominio Active Directory con Microsoft 365 e gestire gli utenti in locale. 

![Autenticazione pass-through (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA consente agli utenti di accedere alle risorse e alle applicazioni locali e Microsoft 365 usando l'account e la password locali. Questa configurazione convalida le password degli utenti direttamente rispetto a Servizi di dominio Active Directory locale senza archiviare gli hash delle password in Azure AD. 

PTA è anche per le organizzazioni con un requisito di sicurezza per applicare immediatamente gli stati degli account utente locali, i criteri password e le ore di accesso. 
  
Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.
  
### <a name="federated-authentication"></a>Autenticazione federata

L'autenticazione federata è principalmente per organizzazioni aziendali di grandi dimensioni con requisiti di autenticazione più complessi. Le identità di Servizi di dominio Active Directory vengono sincronizzate con Microsoft 365 e gli account utente vengono gestiti in locale. Con l'autenticazione federata, gli utenti hanno la stessa password in locale e nel cloud e non devono accedere di nuovo per usare Microsoft 365. 

L'autenticazione federata può supportare ulteriori requisiti di autenticazione, ad esempio l'autenticazione basata su smart card o un'autenticazione a più fattori di terze parti ed è in genere necessaria quando le organizzazioni hanno un requisito di autenticazione non supportato in modo nativo da Azure AD.
 
Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Provider di identità e autenticazione di terze parti

Gli oggetti directory locali possono essere sincronizzati con Microsoft 365 e l'accesso alle risorse cloud è gestito principalmente da un provider di identità di terze parti.On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP). Se l'organizzazione usa una soluzione di federazione di terze parti, è possibile configurare l'accesso con tale soluzione per Microsoft 365 purché la soluzione di federazione di terze parti sia compatibile con Azure AD.
  
Per altre informazioni, [vedi l'elenco di compatibilità](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) della federazione di Azure AD.
  
## <a name="ad-ds-preparation"></a>Preparazione di Servizi di dominio Active Directory

Per garantire una transizione senza problemi a Microsoft 365 tramite la sincronizzazione, è necessario preparare la foresta di Servizi di dominio Active Directory prima di iniziare la distribuzione della sincronizzazione della directory di Microsoft 365.
  
La preparazione della directory deve concentrarsi sulle attività seguenti:

- Rimuovere gli **attributi proxyAddress** e **userPrincipalName** duplicati.
- Aggiornare gli attributi **userPrincipalName vuoti** e non validi con **attributi userPrincipalName** validi.
- Rimuovere i caratteri non validi e discutibile negli attributi **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses,** **mailNickname** e **userPrincipalName.** Per informazioni dettagliate sulla preparazione degli attributi, vedere Elenco degli attributi sincronizzati dallo strumento di sincronizzazione [di Azure Active Directory.](https://go.microsoft.com/fwlink/p/?LinkId=396719)

    > [!NOTE]
    > Si tratta degli stessi attributi sincronizzati da Azure AD Connect. 
  
## <a name="multi-forest-deployment-considerations"></a>Considerazioni sulla distribuzione a più foreste

Per più foreste e opzioni SSO, usare [un'installazione personalizzata di Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-custom)
  
Se l'organizzazione dispone di più foreste per l'autenticazione (foreste di accesso), è consigliabile eseguire le operazioni seguenti:
  
- **Valutare la possibilità di consolidare le foreste.** In generale, è necessario un maggiore sovraccarico per la gestione di più foreste. A meno che l'organizzazione non abbia vincoli di sicurezza che impongono la necessità di foreste separate, è consigliabile semplificare l'ambiente locale.
- **Utilizzare solo nella foresta di accesso principale.** Prendere in considerazione la distribuzione di Microsoft 365 solo nella foresta di accesso principale per l'implementazione iniziale di Microsoft 365. 

Se non è possibile consolidare la distribuzione di Servizi di dominio Active Directory a più foreste o si utilizzano altri servizi directory per gestire le identità, è possibile sincronizzarli con l'aiuto di Microsoft o di un partner.
  
Per [ulteriori informazioni, vedere Topologie per Azure AD Connect.](/azure/active-directory/hybrid/plan-connect-topologies)
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Funzionalità che dipendono dalla sincronizzazione della directory
  
La sincronizzazione della directory è necessaria per le caratteristiche e le funzionalità seguenti:
  
- Azure AD Seamless Single Sign-On (SSO)
- Coesistenza skype
- Distribuzione ibrida di Exchange, tra cui:
  - Elenco indirizzi globale (GAL) completamente condiviso tra l'ambiente Exchange locale e Microsoft 365.
  - Sincronizzazione delle informazioni dell'elenco indirizzi globale da sistemi di posta diversi.
  - Possibilità di aggiungere e rimuovere utenti dalle offerte di servizi di Microsoft 365. A tale scopo, è necessario quanto segue:
  - La sincronizzazione bidirezionale deve essere configurata durante l'installazione della sincronizzazione della directory. Per impostazione predefinita, gli strumenti di sincronizzazione della directory scrivono le informazioni della directory solo nel cloud. Quando si configura la sincronizzazione bidirezionale, si abilita la funzionalità di write-back in modo che un numero limitato di attributi dell'oggetto viene copiato dal cloud e quindi li si scrive di nuovo nel Servizio di dominio Active Directory locale. Il write-back viene anche definito modalità ibrida di Exchange. 
  - Una distribuzione ibrida di Exchange locale
  - Possibilità di spostare alcune cassette postali utente in Microsoft 365 mantenendo altre cassette postali utente in locale.
  - I mittenti attendibili e i mittenti bloccati in locale vengono replicati in Microsoft 365.
  - Delega di base e funzionalità di invio per conto di posta elettronica.
  - Si dispone di una soluzione di autenticazione a più fattori o smart card locale integrata.
- Sincronizzazione di foto, anteprime, sale riunioni e gruppi di sicurezza

## <a name="next-step"></a>Passaggio successivo

Quando si è pronti per distribuire l'identità ibrida, vedere [Prepare for directory synchronization](prepare-for-directory-synchronization.md).
