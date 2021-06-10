---
title: Ulteriori Azure Active Directory per la migrazione da Microsoft Cloud Deutschland
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
description: 'Riepilogo: informazioni Azure Active Directory aggiuntive per il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a servizi Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 1e3871dc5a8a8a9ecbef29df21431aa3707871d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923851"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ulteriori Azure Active Directory per la migrazione da Microsoft Cloud Deutschland

Per completare lo spostamento dal cloud tedesco di Azure al cloud pubblico di Azure, è consigliabile che l'endpoint di autenticazione, Azure Active Directory (Azure AD) Graph e gli endpoint ms Graph per le applicazioni siano aggiornati a quelli del cloud commerciale quando l'endpoint OpenID Connessione (OIDC) avvia la segnalazione degli `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` endpoint cloud commerciali. 
 
**Quando è consigliabile apportare questa modifica?**

Riceverai una notifica nel portale di Azure/Office quando il tenant completa la migrazione dal cloud tedesco al cloud commerciale. Hai 30 giorni dopo aver ricevuto questa notifica per completare questi aggiornamenti in modo che l'app continui a funzionare per i tenant migrati dal cloud di Azure Germania al cloud pubblico di Azure.
 
Esistono tre condizioni preliminari per aggiornare l'autorità di accesso:

 - L'endpoint di individuazione OIDC per il tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` restituisce gli endpoint cloud pubblici di Azure AD.

 - Se il tenant è configurato per la federazione, Active Directory Federation Services (AD FS) viene aggiornato per la sincronizzazione con Azure AD Public. Puoi seguire le istruzioni per aggiornare le impostazioni Connessione Azure AD per apportare questa modifica.

 - Le applicazioni di risorse, se presenti, usate dalle applicazioni vengono modificate per accettare token firmati sia da Azure AD Germany che da Azure AD Public.
 
**Che tipo di applicazioni?**

Un'applicazione può essere una delle seguenti:

- [App a pagina singola (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [App Web che accede agli utenti](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [App Web che chiama API Web](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API Web protetta](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web che chiama API Web](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [App desktop](/azure/active-directory/develop/scenario-desktop-overview)
- [App Daemon](/azure/active-directory/develop/scenario-daemon-overview)
- [App per dispositivi mobili](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Quando un'applicazione passa `login.microsoftonline.com` all'uso come autorità, i token verranno firmati da questa nuova autorità. Se si ospitano applicazioni di risorse chiamate da altre app, sarà necessario consentire la convalida del token lax. Ciò significa che l'app deve consentire token firmati sia dal cloud pubblico di Azure AD Germany che da Azure AD. Questa convalida del token lax è necessaria fino a quando tutte le applicazioni client che chiamano il servizio non vengono migrate completamente nel cloud pubblico di Azure AD. Dopo la migrazione, l'applicazione di risorse deve accettare solo i token firmati dal cloud pubblico di Azure AD.

**Cosa è necessario aggiornare?**

1. Se stai ospitando un'applicazione in Azure Germania usata per autenticare gli utenti di Azure Germania o Office 365 Germany, assicurati che sia usata come autorità nel contesto `https://login.microsoftonline.com` di autenticazione.

    - Vedere Contesti di autenticazione di Azure AD.
    - Questo vale sia per l'autenticazione per l'applicazione che per tutte le API che l'applicazione potrebbe chiamare (ovvero Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Aggiornare l'endpoint Graph Azure AD in modo che sia `https://graph.windows.net` .

3. Aggiornare MS Graph endpoint su `https://graph.microsoft.com` .

4. Aggiornare gli endpoint cloud tedeschi (ad esempio quelli per Exchange Online e SharePoint Online) utilizzati dalle applicazioni per essere quelli del cloud pubblico.

5. Aggiornare i parametri dell'ambiente in modo che siano `AzurePublic` (anziché `AzureGermany` ) negli strumenti di amministrazione e negli script per:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**Informazioni sulle applicazioni pubblicate**

Se si pubblica un'applicazione disponibile per gli utenti esterni al tenant, potrebbe essere necessario modificare la registrazione dell'applicazione per garantire la continuità. Gli altri tenant che usano l'applicazione possono essere spostati in un momento diverso rispetto al tenant. Per garantire che non perdano mai l'accesso all'applicazione, dovrai acconsentire alla sincronizzazione dell'app da Azure Germania a Azure pubblico.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Ecco alcune considerazioni aggiuntive per Azure AD:

- Per l'autenticazione federata:

  - Non è necessario creare, alzare di livello o abbassare di livello un dominio federato mentre è in corso la transizione del tenant. Al termine della migrazione al servizio Azure AD (il tenant è completo), è possibile riprendere la gestione dei domini federati.

  - Se si utilizza l'autenticazione federata con Active Directory Federation Services (ADFS), non è consigliabile apportare modifiche agli URI dell'autorità emittente utilizzati per tutta l'autenticazione con Servizi di dominio Active Directory locale durante la migrazione. La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio. Gli URI dell'autorità emittente possono essere modificati direttamente in AD FS o quando un dominio viene convertito da gestito a federato e viceversa. Microsoft consiglia ai clienti di non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD da migrare. Gli URI dell'autorità emittente possono essere modificati al termine della migrazione.

- Per la rete:

  - La creazione di reti con nome IPv6 non funziona nel portale di Azure, `http://portal.microsoftazure.de/` . Usare il portale di Azure in per creare reti con `https://portal.azure.com` nome IPv6.
 
   - Non è possibile creare intervalli di indirizzi IP attendibili per le impostazioni del servizio Azure Multi-Factor Authentication (MFA) dal portale Microsoft Cloud Deutschland. Usare il portale di Azure AD per Office 365 per creare intervalli di indirizzi IP attendibili di Azure MFA.


- Per l'accesso condizionale: 

  - I criteri di accesso condizionale con i controlli di concessione seguenti non sono supportati fino al completamento della migrazione ai servizi Office 365 (dopo la fase di finalizzazione della migrazione di [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Richiedi dispositivo conforme
    - Richiedi app approvata
    - Richiedi criteri di protezione app
    
  - L'interfaccia dei criteri di accesso condizionale fornisce un falso avviso sull'attivazione delle impostazioni predefinite di sicurezza per il tenant anche quando è disabilitato e i criteri di accesso condizionale esistono già per il tenant. È consigliabile ignorare l'avviso o utilizzare il portale dei Office 365 per gestire i criteri di accesso condizionale. 

- Gli scenari di Intune sono supportati solo negli endpoint globali dopo il completamento della migrazione del tenant, incluse tutte le migrazioni dei carichi di lavoro di Office.

- Gli utenti di Microsoft Cloud Deutschland che usano il metodo di notifica app per dispositivi mobili per le richieste MFA visualizzano l'ObjectId (un GUID) dell'utente anziché il nome dell'entità utente (UPN) nell'app Microsoft Authenticator. Dopo che la migrazione del tenant di Azure AD è stata completata e ospitata nei servizi Office 365, le nuove Microsoft Authenticator degli utenti visualizzano gli UPN degli utenti. Gli Microsoft Authenticator esistenti continueranno a visualizzare l'ObjectId dell'utente, ma continueranno a funzionare per le notifiche delle app per dispositivi mobili. 

- Per i tenant creati dopo il 22 ottobre 2019, le impostazioni predefinite di sicurezza possono essere abilitate automaticamente per il tenant quando viene migrato nel servizio Office 365. Gli amministratori tenant possono scegliere di lasciare abilitate le impostazioni predefinite di sicurezza e di registrarsi per la MFA oppure possono disabilitare la funzionalità. Per ulteriori informazioni, vedere [Disabling security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Le organizzazioni che non sono abilitate automaticamente durante la migrazione potrebbero comunque essere registrate automaticamente in futuro in quanto la funzionalità per abilitare le impostazioni predefinite di sicurezza viene implementazione nel servizio Office 365. Gli amministratori che scelgono di disabilitare o abilitare in modo esplicito le impostazioni predefinite di sicurezza possono farlo aggiornando la funzionalità in **Azure Active Directory > proprietà**. Dopo che la funzionalità è stata abilitata in modo esplicito dall'amministratore, non verrà abilitata automaticamente.

- Verrà visualizzato un avviso sulla versione di Azure AD Connessione nel portale di Office 365 Germany e nel portale di Office 365 dopo la migrazione del tenant. Può essere ignorato se l'avviso versione non mostra più l'avviso al termine della migrazione. Se è presente un avviso, prima o dopo la migrazione, in uno dei portali, è necessario aggiornare Connessione azure AD. Il messaggio di avviso indica: "È stato rilevato che si sta utilizzando uno strumento di sincronizzazione della directory non obsoleto. Ti consigliamo di accedere all'Area download Microsoft per ottenere la versione più recente di Azure AD Connessione."

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)