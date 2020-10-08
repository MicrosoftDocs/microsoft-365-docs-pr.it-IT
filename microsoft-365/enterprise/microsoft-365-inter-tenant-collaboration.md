---
title: Collaborazione tra tenant di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Informazioni su come la collaborazione di Microsoft 365 è compatibile con i tenant e le organizzazioni, consentendo a diverse organizzazioni di collaborare in modo sicuro.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00eacfc21d3223b5b9a1ad420cd5d1d85bf4ea8e
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384832"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Collaborazione tra tenant di Microsoft 365

Si supponga che due organizzazioni, Fabrikam e contoso, dispongano di un tenant di Microsoft 365 per le aziende e che desiderino collaborare su diversi progetti. alcuni dei quali sono in esecuzione per un periodo di tempo limitato e alcuni dei quali sono in corso. In che modo Fabrikam e contoso consentono alle persone e ai team di collaborare in modo più efficace tra i diversi tenant di Microsoft 365 in maniera sicura? Microsoft 365, in combinazione con la collaborazione B2B di Azure Active Directory (Azure AD), fornisce diverse opzioni. Questo articolo descrive alcuni scenari chiave che Fabrikam e Contoso possono prendere in considerazione.
  
Le opzioni di collaborazione tra tenant di Microsoft 365 includono l'utilizzo di una posizione centrale per file e conversazioni, la condivisione di calendari, l'utilizzo di messaggistica istantanea, le chiamate audio/video per la comunicazione e la protezione dell'accesso alle risorse e alle applicazioni. Usare le tabelle seguenti per selezionare le soluzioni e ottenere altre informazioni.
  
## <a name="exchange-online-collaboration-options"></a>Opzioni di collaborazione di Exchange Online

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Condividere i calendari con un'altra organizzazione Microsoft 365 |Gli amministratori possono configurare diversi livelli di accesso al calendario in Exchange Online per consentire alle aziende di collaborare con altre aziende e permettere agli utenti di condividere le pianificazioni (informazioni sulla disponibilità) con altre persone. | <ul><li>[Condivisione](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [Relazioni organizzative](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [Creare una relazione organizzativa](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [Modificare una relazione organizzativa ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [Rimuovere una relazione organizzativa](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [Condividere calendari con utenti esterni](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Controllare la modalità di condivisione dei calendari con persone esterne all'organizzazione | Gli amministratori applicano criteri di condivisione alle cassette postali degli utenti per controllare con chi possono essere condivise e il livello di accesso concesso |  <ul><li> [Criteri di condivisione](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [Creare un criterio di condivisione](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [Applicazione di un criterio di condivisione alle cassette postali](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [Modifica, disattivazione o rimozione di un criterio di condivisione](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|Configurare canali di posta elettronica protetti e controllare il flusso di posta con le organizzazioni partner | Gli amministratori creano connettori per applicare le opzioni di sicurezza agli scambi di posta elettronica con un'organizzazione partner o un provider di servizi. I connettori usano la crittografia con TLS (Transport Layer Security) e consentono di applicare restrizioni ai nomi di dominio o agli intervalli di indirizzi IP da cui i partner inviano messaggi di posta elettronica. |  <ul><li> [Come Exchange Online USA TLS per proteggere le connessioni di posta elettronica](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [Configurare il flusso di posta utilizzando i connettori](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [Domini remoti](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [Configurare i connettori per un flusso di posta elettronica sicuro con un'organizzazione partner](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [Procedure consigliate per il flusso di posta (panoramica)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Opzioni di collaborazione di SharePoint Online e OneDrive for Business

| Obiettivi della condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Condividere siti e documenti con utenti esterni | Gli amministratori configurano la condivisione a livello del tenant o della raccolta siti per gli account Microsoft autenticati, gli account aziendali o dell'istituto di istruzione autenticati o gli account guest. |  <ul><li> [Gestire la condivisione esterna per l'ambiente di SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Limitare la condivisione di contenuto di SharePoint e OneDrive in base al dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [Usare SharePoint Online come soluzione Extranet Business to Business (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Verifica e controllo della condivisione esterna per gli utenti finali | I proprietari di file di OneDrive for Business e gli utenti finali di SharePoint Online configurano la condivisione di siti e documenti e specificano le notifiche per tenere traccia della condivisione. |  <ul><li> [Configurare le notifiche per la condivisione esterna in OneDrive for Business](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Condividere file o cartelle di SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Opzioni di collaborazione di Skype for Business

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Skype for Business Online: messaggistica istantanea, chiamate e presenza con altri utenti di Skype for Business | Gli amministratori possono abilitare gli utenti di Skype for business online a messaggistica istantanea, effettuare chiamate audio/video e visualizzare la presenza con gli utenti in un altro tenant di Microsoft 365. | [Permettere agli utenti di contattare utenti di Skype for Business esterni](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype for Business Online: messaggistica istantanea, chiamate e presenza con utenti di Skype (consumer) | Gli amministratori possono consentire agli utenti di Skype for Business Online di usare la messaggistica istantanea, effettuare chiamate e vedere la presenza con utenti di Skype (consumer). | [Consentire agli utenti di Skype for Business di aggiungere contatti Skype](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Opzioni di Collaborazione B2B di Azure AD

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Collaborazione B2B di Azure Active Directory: condivisione di contenuto aggiungendo utenti esterni a un gruppo nella directory di un'organizzazione | Un amministratore globale per un tenant di Microsoft 365 può invitare persone in un altro tenant di Microsoft 365 ad unirsi alla propria directory, aggiungere tali utenti esterni a un gruppo e concedere l'accesso al contenuto, ad esempio i siti di SharePoint e le raccolte per il gruppo. |  <ul><li> [Che cos'è l'anteprima di Collaborazione B2B di Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Collaborazione B2B di Azure AD: nuovi aggiornamenti che facilitano la collaborazione tra aziende](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Condivisione esterna e collaborazione di Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [API e personalizzazione per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD and Identity Show: Collaborazione Business to Business (B2B) di Azure AD](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Opzioni di collaborazione di Microsoft 365

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Gruppi di Microsoft 365-posta elettronica, calendario, OneNote e file condivisi in una posizione centrale | I gruppi sono supportati in Business Essentials, Business Premium, per l’istruzione e nei piani Enterprise E1, E3 ed E5. Gli utenti di un tenant Microsoft 365 possono creare un gruppo e invitare persone in un altro tenant di Microsoft 365 come Guest. Ciò si applica anche a Dynamics CRM. |  <ul><li> [Informazioni sui gruppi di Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Accesso guest nei gruppi di Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Distribuire i gruppi di Microsoft 365](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Opzioni di collaborazione di Yammer

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Yammer: collaborazione con i social media aziendali | Se la caratteristica non è stata disabilitata da un amministratore di Yammer, gli utenti possono creare gruppi esterni per collaborare in Yammer tramite le conversazioni, aggiungendo Mi piace e seguendo i post, condividendo i file e usando le chat online. | [Creare e gestire gruppi esterni in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Opzioni di collaborazione di Teams

|Obiettivo di condivisione|Azione amministrativa|Informazioni sulle procedure|
|:-----|:-----|:-----|
|Collaborare in Teams con utenti esterni all'organizzazione | Un amministratore globale per l'invitante Microsoft 365 tenant deve abilitare la collaborazione esterna in teams. Gli amministratori globali e i proprietari del team potranno quindi invitare utenti che dispongono di un indirizzo di posta elettronica a collaborare in Teams.  <br/> Gli amministratori possono anche gestire e modificare guest già presenti nel proprio tenant. |  <ul><li> [Gestire l'accesso guest](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Attivare o disattivare l'accesso guest in Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [Usare PowerShell per controllare l'accesso guest](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [Elenco di controllo dell’accesso guest](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [Visualizzare gli utenti guest](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [Modificare le informazioni degli utenti guest](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|I proprietari del team possono invitare e gestire il modo in cui gli utenti possono collaborare all'interno del team.  |I proprietari del team hanno controlli supplementari sulle operazioni che gli utenti possono eseguire all'interno del team. |  <ul><li> [Aggiungere un utente guest](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Aggiungere un utente guest a un team](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Gestire l'accesso guest in Teams](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [Vedere chi è in un team o in un canale](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gli utenti guest di altri tenant possono visualizzare il contenuto in Teams e collaborare con altri membri | Nessuna. | [L'esperienza di accesso come utente guest](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Opzioni di collaborazione di Power BI

| Obiettivo di condivisione | Azione amministrativa | Informazioni sulle procedure |
|:-----|:-----|:-----|
|Power BI abilita gli utenti guest esterni a usare i contenuti condivisi tramite collegamenti. Questo consente agli utenti dell'organizzazione di distribuire contenuti in modo sicuro tra le diverse organizzazioni.<br/> | L'amministratore di Power BI può controllare se gli utenti possono invitare gli utenti esterni a visualizzare il contenuto all'interno dell'organizzazione.| [Distribuire il contenuto di Power BI a utenti guest esterni con Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Punti da tenere presente sulla collaborazione tra tenant di Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Condivisione di account utente, licenze, sottoscrizioni e archiviazione

Ogni organizzazione gestisce i propri account utente, identità, gruppi di sicurezza, abbonamenti, licenze e archiviazione. Gli utenti utilizzano le funzionalità di collaborazione in Microsoft 365 insieme ai criteri di condivisione e alle impostazioni di sicurezza per consentire l'accesso alle informazioni necessarie mantenendo il controllo delle risorse aziendali.
  
- **Account utente:** Gli account non possono essere condivisi o duplicati tra i tenant o le partizioni nei servizi di dominio Active Directory locali. 
    
- ** &amp; Abbonamenti alle licenze:** in Microsoft 365, le licenze provenienti da piani di licenza (denominati anche SKU o piani Microsoft 365) offrono agli utenti l'accesso ai servizi Microsoft 365 definiti per tali piani. 
    
- **Archiviazione:** Nei piani di gestione delle licenze Microsoft 365, i limiti software e il limite per SharePoint Online vengono gestiti separatamente dai limiti di archiviazione delle cassette postali. I limiti di archiviazione della cassetta postale vengono configurati e gestiti con Exchange Online. In entrambi gli scenari, lo spazio di archiviazione non può essere condiviso tra i tenant. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>È possibile condividere gli spazi dei nomi di dominio tra gli inquilini di Microsoft 365?

No. I nomi di dominio dell'organizzazione, ad esempio fabrikam.com o tailspintoys.com, possono essere associati e utilizzati solo con un singolo tenant di Microsoft 365. Ogni tenant deve disporre di uno spazio dei nomi specifico. Gli spazi dei nomi UPN, SMTP e SIP non possono essere condivisi tra i tenant.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Informazioni sui componenti ibridi e sulla collaborazione tra tenant di Microsoft 365?

I componenti ibridi locali, ad esempio un'organizzazione di Exchange e Azure AD Connect, non possono essere suddivisi tra più tenant.
 

