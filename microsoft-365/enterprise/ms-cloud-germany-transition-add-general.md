---
title: Ulteriori informazioni generali per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Riepilogo: ulteriori informazioni generali sui servizi quando si passa da Microsoft Cloud Germany (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area datacenter tedesco.'
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551783"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ulteriori informazioni generali per la migrazione da Microsoft Cloud Deutschland

Nelle sezioni seguenti vengono fornite informazioni aggiuntive su servizi, considerazioni precedenti al lavoro e esperienza dei clienti.

## <a name="azure-active-directory"></a>Azure Active Directory

Per completare lo spostamento dal cloud tedesco di Azure al cloud pubblico di Azure, è consigliabile che l'endpoint di autenticazione, il grafico di Azure Active Directory (Azure AD) e gli endpoint MS Graph per le applicazioni vengano aggiornati a quelli del cloud commerciale quando l'endpoint OpenID Connect (OIDC) `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` inizia a segnalare gli endpoint del cloud commerciale. 
 
**Quando è necessario apportare questa modifica?**

Si riceverà una notifica in Azure/Office Portal quando il tenant completa la migrazione dal cloud tedesco al cloud commerciale. Si dispone di 30 giorni dopo la ricezione della notifica per completare gli aggiornamenti in modo che l'app continui a funzionare per i tenant migrati dal cloud di Azure Germany al cloud pubblico di Azure.
 
Sono disponibili tre condizioni per l'aggiornamento dell'autorità di accesso:

 - L'endpoint di individuazione di OIDC per il tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` restituisce gli endpoint del cloud pubblico di Azure ad.

 - Se il tenant è configurato per la Federazione, Active Directory Federation Services (AD FS) viene aggiornato per la sincronizzazione con Azure AD public. Per eseguire questa modifica, è possibile seguire le istruzioni per aggiornare le impostazioni di Azure AD Connect.

 - Le applicazioni di risorse, se presenti, utilizzate dalle applicazioni vengono modificate per accettare i token firmati sia da Azure AD Germany che da Azure AD public.
 
**Che tipo di applicazioni?**

Un'applicazione può essere una delle seguenti:

- App a pagina singola (SPA)
- Applicazione Web che consente di firmare negli utenti
- Applicazione Web che chiama le API Web
- API Web protetta
- API Web che chiama le API Web
- App desktop
- App daemon
- App per dispositivi mobili
 
> [!NOTE] 
> Quando un'applicazione passa all'utilizzo `login.microsoftonline.com` come autorità, i token verranno firmati da questa nuova autorità. Se si ospitano tutte le applicazioni di risorse in cui si chiamano altre app, sarà necessario consentire la convalida dei token LAX. Questo significa che l'app deve consentire ai token firmati sia i cloud pubblici di Azure AD Germany che quelli di Azure AD. Questa convalida del token LAX è necessaria finché tutte le applicazioni client che chiamano il servizio non vengono completamente migrate nel cloud pubblico di Azure AD. Dopo la migrazione, l'applicazione di risorse deve accettare solo i token firmati dal cloud pubblico di Azure AD.

**Operazioni necessarie per l'aggiornamento**

1. Se si ospita un'applicazione in Azure Germany utilizzata per autenticare gli utenti di Azure Germany o Office 365 Germany, assicurarsi che `https://login.microsoftonline.com` venga utilizzata come autorità nel contesto di autenticazione.

    - Vedere contesti di autenticazione di Azure AD.
    - Ciò vale sia per l'autenticazione per l'applicazione che per l'autenticazione a qualsiasi API che può essere chiamata dall'applicazione (ovvero, Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Aggiornare l'endpoint di Azure AD Graph in modo che sia `https://graph.windows.net` .

3. Aggiornare l'endpoint di MS Graph in modo che sia `https://graph.microsoft.com` .

4. Aggiornare gli endpoint di tipo cloud tedesco, ad esempio quelli per Exchange Online e SharePoint Online, che vengono utilizzati dalle applicazioni come quelli del cloud pubblico.

5. Aggiornare i parametri dell'ambiente in modo che siano `AzurePublic` (anziché `AzureGermany` ) in strumenti di amministrazione e script per:

    - Azure PowerShell
    - Azure AD PowerShell (MSOnline)
    - Azure AD PowerShell (AzureAD)
    - CLI di Azure
 
**Informazioni sulle applicazioni pubblicate**

Se si pubblica un'applicazione disponibile per gli utenti che si trovano all'esterno del tenant, potrebbe essere necessario modificare la registrazione dell'applicazione per garantire la continuità. Gli altri tenant che utilizzano l'applicazione possono essere spostati in un momento diverso rispetto a quello del tenant. Per evitare che l'accesso all'applicazione venga mai perso, è necessario acconsentire all'applicazione sincronizzata da Azure Germany a Azure Public.

### <a name="additional-considerations"></a>Considerazioni aggiuntive

Di seguito sono riportate alcune considerazioni aggiuntive su Azure AD:

- Per l'autenticazione federata:

  - Non è necessario creare, promuovere o abbassare di livello un dominio federato quando la transizione del tenant è in fase di elaborazione. Dopo aver completato la migrazione al servizio Azure AD (il tenant è completamente completo), è possibile riprendere la gestione dei domini federati.

  - Se si utilizza l'autenticazione federata con Active Directory Federation Services (AD FS), non è necessario apportare modifiche agli URI degli emittenti utilizzati per tutta l'autenticazione con servizi di dominio Active Directory (AD DS) locali durante la migrazione. La modifica degli URI degli emittenti comporterà errori di autenticazione per gli utenti del dominio. Gli URI dell'autorità emittente possono essere modificati direttamente in AD FS o quando un dominio viene convertito da gestito a federato e viceversa. Microsoft consiglia ai clienti di non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati dopo che la migrazione è stata completata completamente.

- Per la rete:

  - La creazione di reti con nome IPv6 non funziona nel portale di Azure `http://portal.microsoftazure.de/` . Utilizzare il portale di Azure `https://portal.azure.com` per creare reti con nome IPv6.
 
   - Non è possibile creare intervalli di indirizzi IP attendibili per le impostazioni del servizio di autenticazione a più fattori di Azure (AMF) dal portale Microsoft Cloud Deutschland. Utilizzare il portale di Azure AD per i servizi di Office 365 per creare intervalli di indirizzi IP attendibili di Azure AMF.


- Per l'accesso condizionale: 

  - I criteri di accesso condizionale con i seguenti controlli Grant non sono supportati finché non è stata completata la migrazione ai servizi di Office 365 (dopo la fase di migrazione di [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) ):

    - Richiedi dispositivo conforme
    - Richiedi app approvata
    - Richiedi criteri di protezione delle app
    
  - L'interfaccia dei criteri di accesso condizionale fornisce un falso avviso sui valori predefiniti di sicurezza abilitati per il tenant anche quando è disabilitato e i criteri di accesso condizionale esistono già per il tenant. È consigliabile ignorare l'avviso o utilizzare il portale dei servizi di Office 365 per gestire i criteri di accesso condizionale. 

- Gli scenari di Intune sono supportati solo dagli endpoint di tutto il mondo dopo il completamento della migrazione del tenant, incluse tutte le migrazioni dei carichi di lavoro di Office.

- Gli utenti di Microsoft Cloud Deutschland che utilizzano il metodo di notifica per dispositivi mobili per le richieste dell'AMF visualizzano il parametro ObjectId dell'utente (GUID) anziché il nome dell'entità utente (UPN) nell'app Microsoft Authenticator. Dopo che la migrazione del tenant di Azure AD è stata completata e ospitata nei servizi di Office 365, le nuove attivazioni di Microsoft Authenticator visualizzano gli utenti di UPN. Gli account di Microsoft Authenticator esistenti continueranno a visualizzare l'utente ObjectId, ma continueranno a funzionare per le notifiche delle app per dispositivi mobili. 

- Per i tenant creati dopo il 22 ottobre 2019, le impostazioni predefinite per la sicurezza possono essere abilitate automaticamente per il tenant quando viene eseguita la migrazione al servizio Office 365. Gli amministratori tenant possono scegliere di lasciare le impostazioni predefinite per la sicurezza abilitate e registrarsi per l'AMF oppure possono disabilitare la funzionalità. Per ulteriori informazioni, vedere [disattivazione delle impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)per la sicurezza. 

  > [!NOTE]
  > Le organizzazioni che non sono abilitate automaticamente durante la migrazione potrebbero essere ancora in corso di registrazione automatica in futuro, in quanto la funzionalità per abilitare le impostazioni predefinite per la sicurezza viene implementata nel servizio Office 365. Gli amministratori che scelgono di disabilitare o abilitare esplicitamente le impostazioni predefinite per la sicurezza possono farlo aggiornando la caratteristica in **Azure Active Directory > proprietà**. Dopo che la funzionalità è stata abilitata in modo esplicito dall'amministratore, non sarà abilitata automaticamente.

- Verrà visualizzato un messaggio di avviso relativo alla versione di Azure AD Connect nel portale Office 365 Germany e nel portale di Office 365 dopo la migrazione del tenant. Questa operazione può essere ignorata se l'avviso relativo alla versione non Visualizza più l'avviso dopo il completamento della migrazione. Se è presente un avviso, sia prima che dopo la migrazione, in entrambi i portale, è necessario aggiornare Azure AD Connect. Il messaggio di avviso dice: "è stato rilevato che si sta utilizzando uno strumento di sincronizzazione della directory obsoleto. Si consiglia di accedere all'area download Microsoft per ottenere la versione più recente di Azure AD Connect.

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` funzionerà solo dopo l'completa di Office 365. I collegamenti produrranno messaggi di errore "qualcosa è andato storto" fino a quel momento.

- Gli utenti di Outlook Web App che accedono a una cassetta postale condivisa nell'altro ambiente (ad esempio, un utente dell'ambiente Germany che accede a una cassetta postale condivisa nell'ambiente globale) verranno invitati a eseguire l'autenticazione una seconda volta. L'utente deve innanzitutto autenticare e accedere alla propria cassetta postale `outlook.office.de` , quindi aprire la cassetta postale condivisa `outlook.office365.com` . Sarà necessario eseguire l'autenticazione una seconda volta quando si accede alle risorse condivise ospitate nell'altro servizio.

- Per i clienti Microsoft Cloud Deutschland esistenti o quelli in fase di transizione, quando una cassetta postale condivisa viene aggiunta a Outlook utilizzando **File > Info > Aggiungi account**, la visualizzazione delle autorizzazioni del calendario potrebbe non riuscire (il client di Outlook tenta di utilizzare l'API REST `https://outlook.office.de/api/v2.0/Me/Calendars` ). I clienti che desiderano aggiungere un account per visualizzare le autorizzazioni del calendario possono aggiungere la chiave del registro di sistema, come descritto in [modifiche dell'esperienza utente per la condivisione di un calendario in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) per garantire che questa azione abbia esito positivo. Questa chiave del registro di sistema può essere distribuita a livello di organizzazione tramite criteri di gruppo.

- Durante la fase di migrazione, l'utilizzo dei cmdlet di PowerShell **New-migrationEndpoint**, **set-migrationEndpoint** e **test-MigrationsServerAvailability** può causare errori (errore sul proxy). Questo accade quando la cassetta postale di arbitraggio ha eseguito la migrazione in tutto il mondo, ma la cassetta postale di amministrazione non ha o viceversa. Per risolvere questo passaggio, durante la creazione della sessione tenant di PowerShell, utilizzare la cassetta postale di arbitraggio come suggerimento per il routing in **ConnectionURI**. Ad esempio: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se si utilizza Exchange Online ibrido:

    - È necessario rieseguire la procedura guidata di configurazione ibrida (HCW) per aggiornare la configurazione locale a Microsoft Cloud Deutschland prima della transizione e rieseguire HCW al momento della pulizia nei servizi di Office 365. Se si utilizzano domini personalizzati, potrebbe essere necessario un aggiornamento DNS aggiuntivo.

Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o sull'impatto su come eseguire l'amministrazione o l'utilizzo, esaminare la sezione Exchange Online sulle [azioni e sugli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md#exchange-online).

## <a name="office-services"></a>Servizi di Office

Il servizio utilizzato più di recente (MRU) in Office è un completa dal servizio Germany ai servizi di Office 365, non una migrazione. Solo i collegamenti MRU provenienti dal fianco dei servizi di Office 365 saranno visibili dopo la migrazione dal portale Office.com. I collegamenti MRU provenienti dal servizio Germany non sono visibili come collegamenti MRU nei servizi di Office 365. In Office 365, i collegamenti MRU sono accessibili solo dopo che la migrazione del tenant è stata completata.

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online e OneDrive

- Dopo aver completato la migrazione di SharePoint Online all'area tedesca, vengono ricreati gli indici dei dati. Le caratteristiche che dipendono dagli indici di ricerca possono essere intaccate durante la reindicizzazione completa.

- Se l'organizzazione utilizza ancora flussi di lavoro di SharePoint 2010, non funzionerà più dopo il 31 dicembre 2021. I flussi di lavoro di SharePoint 2013 rimarranno supportati, sebbene disattivati per impostazione predefinita per i nuovi tenant a partire dal 1 ° novembre 2020. Dopo aver completato la migrazione al servizio SharePoint Online, è consigliabile passare a Power automatizzate o ad altre soluzioni supportate.

- Dopo il completamento della migrazione di OneDrive all'area tedesca, vengono ricompilati gli indici di dati. Le caratteristiche che dipendono dagli indici di ricerca potrebbero essere intaccate durante la reindicizzazione.


## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Operazioni e impatto delle fasi di migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
