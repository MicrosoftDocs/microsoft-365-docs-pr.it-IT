---
title: Ulteriori informazioni su Azure Active Directory per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: informazioni aggiuntive su Azure Active Directory durante il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688802"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ulteriori informazioni su Azure Active Directory per la migrazione da Microsoft Cloud Deutschland

Per completare il passaggio dal cloud tedesco di Azure al cloud pubblico di Azure, è consigliabile che l'endpoint di autenticazione, Azure Active Directory (Azure AD) Graph e gli endpoint di MS Graph per le applicazioni siano aggiornati a quelli del cloud commerciale quando l'endpoint OpenID Connect (OIDC) inizia a segnalare gli `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` endpoint del cloud commerciale. 
 
**Quando è necessario apportare questa modifica?**

Si riceverà una notifica nel portale di Azure/Office quando il tenant completa la migrazione dal cloud tedesco al cloud commerciale. Hai 30 giorni dopo aver ricevuto questa notifica per completare questi aggiornamenti in modo che l'app continui a funzionare per i tenant migrati dal cloud di Azure Germania al cloud pubblico di Azure.
 
Esistono tre condizioni preliminari per aggiornare l'autorità di accesso:

 - L'endpoint di individuazione OIDC per il tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` restituisce gli endpoint cloud pubblici di Azure AD.

 - Se il tenant è configurato per la federazione, Active Directory Federation Services (AD FS) viene aggiornato per la sincronizzazione con Azure AD Public. Puoi seguire le istruzioni per aggiornare le impostazioni di Azure AD Connect per apportare questa modifica.

 - Le applicazioni di risorse, se presenti, usate dalle applicazioni vengono modificate in modo da accettare token firmati sia da Azure AD Germany che da Azure AD Public.
 
**Che tipo di applicazioni?**

Un'applicazione può essere una delle seguenti:

- [App a pagina singola](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [App Web che accede agli utenti](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [App Web che chiama API Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API Web protetta](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web che chiama LE API Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [App desktop](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [App Daemon](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [App per dispositivi mobili](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Quando un'applicazione passa `login.microsoftonline.com` all'uso come autorità, i token verranno firmati da questa nuova autorità. Se si ospitano applicazioni di risorse chiamate da altre app, sarà necessario consentire la convalida del token lax. Ciò significa che l'app deve consentire token firmati sia dal cloud pubblico di Azure AD Germania che da Azure AD. Questa convalida del token lax è necessaria fino a quando non viene eseguita la migrazione completa di tutte le applicazioni client che chiamano il servizio nel cloud pubblico di Azure AD. Dopo la migrazione, l'applicazione di risorse deve accettare solo token firmati dal cloud pubblico di Azure AD.

**Cosa è necessario aggiornare?**

1. Se si ospita un'applicazione in Azure Germania usata per autenticare gli utenti di Azure Germania o Office 365 Germany, assicurarsi che sia usata come autorità nel contesto `https://login.microsoftonline.com` di autenticazione.

    - Vedere Contesti di autenticazione di Azure AD.
    - Questo vale sia per l'autenticazione all'applicazione che per tutte le API che l'applicazione potrebbe chiamare (ovvero Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Aggiornare l'endpoint di Azure AD Graph in modo che sia `https://graph.windows.net` .

3. Aggiornare l'endpoint di MS Graph in modo che sia `https://graph.microsoft.com` .

4. Aggiornare gli endpoint cloud tedeschi (ad esempio quelli per Exchange Online e SharePoint Online) utilizzati dalle applicazioni per essere quelli del cloud pubblico.

5. Aggiornare i parametri dell'ambiente `AzurePublic` in modo che siano (anziché ) negli strumenti di amministrazione e negli script `AzureGermany` per:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**Quali sono le applicazioni che si pubblicano?**

Se si pubblica un'applicazione disponibile per gli utenti esterni al tenant, potrebbe essere necessario modificare la registrazione dell'applicazione per garantire la continuità. Gli altri tenant che usano l'applicazione possono essere spostati in un momento diverso da quello del tenant. Per garantire che non perdano mai l'accesso all'applicazione, dovrai acconsentire alla sincronizzazione dell'app da Azure Germania a Azure pubblica.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Ecco alcune considerazioni aggiuntive per Azure AD:

- Per l'autenticazione federata:

  - Non è necessario creare, alzare di livello o abbassare di livello un dominio federato mentre è in corso la transizione del tenant. Al termine della migrazione al servizio Azure AD (il tenant è completo), è possibile riprendere la gestione dei domini federati.

  - Se si utilizza l'autenticazione federata con Active Directory Federation Services (ADFS), non è consigliabile apportare modifiche agli URI dell'autorità emittente utilizzati per tutta l'autenticazione con Servizi di dominio Active Directory locale durante la migrazione. La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio. Gli URI dell'autorità emittente possono essere modificati direttamente in AD FS o quando un dominio viene convertito da gestito a federato e viceversa. Microsoft consiglia ai clienti di non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui viene eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati al termine della migrazione.

- Per la rete:

  - La creazione di reti con nome IPv6 non funziona nel portale di `http://portal.microsoftazure.de/` Azure. Usare il portale di Azure per creare reti con `https://portal.azure.com` nome IPv6.
 
   - Non è possibile creare intervalli di indirizzi IP attendibili per le impostazioni del servizio Azure Multi-Factor Authentication (MFA) dal portale di Microsoft Cloud Deutschland. Usare il portale di Azure AD per i servizi di Office 365 per creare intervalli di indirizzi IP attendibili di Azure MFA.


- Per l'accesso condizionale: 

  - I criteri di accesso condizionale con i controlli di concessione seguenti non sono supportati fino al completamento della migrazione ai servizi di Office 365 (dopo la fase di finalizzazione della migrazione di [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Richiedi dispositivo conforme
    - Richiedi app approvata
    - Richiedi criteri di protezione delle app
    
  - L'interfaccia dei criteri di accesso condizionale fornisce un falso avviso relativo alle impostazioni predefinite di sicurezza abilitate per il tenant anche quando è disabilitata e i criteri di accesso condizionale esistono già per il tenant. È consigliabile ignorare l'avviso o usare il portale dei servizi di Office 365 per gestire i criteri di accesso condizionale. 

- Gli scenari di Intune sono supportati solo negli endpoint globali dopo il completamento della migrazione del tenant, incluse tutte le migrazioni dei carichi di lavoro di Office.

- Gli utenti di Microsoft Cloud Deutschland che usano il metodo di notifica app per dispositivi mobili per le richieste MFA visualizzano l'ObjectId (un GUID) dell'utente anziché il nome dell'entità utente (UPN) nell'app Microsoft Authenticator. Una volta completata la migrazione del tenant di Azure AD e ospitata nei servizi di Office 365, le nuove attivazioni di Microsoft Authenticator visualizzano gli UPN degli utenti. Gli account Microsoft Authenticator esistenti continueranno a visualizzare l'ObjectId dell'utente, ma continueranno a funzionare per le notifiche delle app per dispositivi mobili. 

- Per i tenant creati dopo il 22 ottobre 2019, le impostazioni predefinite di sicurezza possono essere abilitate automaticamente per il tenant quando viene eseguita la migrazione al servizio Office 365. Gli amministratori tenant possono scegliere di lasciare abilitate le impostazioni predefinite di sicurezza e di registrarsi per l'autenticazione a più fattori oppure possono disabilitare la funzionalità. Per ulteriori informazioni, vedere [Disabilitazione delle impostazioni predefinite di sicurezza.](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > Le organizzazioni che non sono abilitate automaticamente durante la migrazione potrebbero comunque essere registrate automaticamente in futuro, poiché la funzionalità per abilitare le impostazioni predefinite di sicurezza viene implementazione nel servizio Office 365. Gli amministratori che scelgono di disabilitare o abilitare in modo esplicito le impostazioni predefinite di sicurezza possono farlo aggiornando la funzionalità in **Azure Active Directory > proprietà**. Dopo che la funzionalità è stata abilitata in modo esplicito dall'amministratore, non verrà abilitata automaticamente.

- Dopo la migrazione del tenant, verrà visualizzato un avviso sulla versione di Azure AD Connect nel portale di Office 365 Germany e nel portale di Office 365. Può essere ignorato se l'avviso versione non mostra più l'avviso al termine della migrazione. Se viene visualizzato un avviso, prima o dopo la migrazione, in uno dei portali, Azure AD Connect deve essere aggiornato. The warning message says: "We detected you're using an obsolete directory sync tool. È consigliabile accedere all'Area download Microsoft per ottenere la versione più recente di Azure AD Connect."

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [AD FS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
