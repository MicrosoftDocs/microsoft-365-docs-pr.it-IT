---
title: Lavoro prerequisito per l'implementazione dei criteri di identità e accesso ai dispositivi-Microsoft 365 per Enterprise | Documenti Microsoft
description: Vengono descritti i prerequisiti precedenti all'implementazione di criteri e configurazioni di identità e accesso ai dispositivi.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 67835f4140179c69b5e0f2cd0287e656dd4c49ad
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558551"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Lavoro prerequisito per l'implementazione dei criteri di identità e accesso ai dispositivi

In questo articolo vengono descritti i prerequisiti che devono essere implementati prima di poter distribuire i criteri di identità e accesso ai dispositivi consigliati. In questo articolo vengono inoltre illustrate le configurazioni dei client predefiniti della piattaforma consigliate per fornire la migliore esperienza Single Sign-on (SSO) agli utenti, nonché i prerequisiti tecnici per l'accesso condizionale.

## <a name="prerequisites"></a>Prerequisiti

Prima di implementare i criteri di identità e accesso ai dispositivi consigliati, esistono numerosi prerequisiti che l'organizzazione deve soddisfare per questi modelli di identità e autenticazione per Microsoft 365 e Office 365:

- Solo cloud
- Autenticazione di sincronizzazione hash con password (pH) ibrida
- Ibrido con autenticazione pass-through (PTA)
- Federati

Nella tabella seguente vengono illustrate le caratteristiche dei prerequisiti e la relativa configurazione che si applicano a tutti i modelli di identità, ad eccezione di quelli indicati. 

|Configurazione|Eccezioni|
|---|:---:|
|[Configurare pH](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Questo deve essere abilitato per rilevare le credenziali trapelate e per agire su di esse per l'accesso condizionale basato sui rischi. **Nota:** Ciò è necessario indipendentemente dal fatto che l'organizzazione utilizzi l'autenticazione federata.|Solo cloud|
|[Abilitare l'accesso Single Sign-on senza](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) problemi per la firma automatica degli utenti quando si trovano nei propri dispositivi di organizzazione connessi alla rete dell'organizzazione.|Solo cloud e federato|
|[Configurare le reti denominate](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection raccoglie e analizza tutti i dati di sessione disponibili per generare un punteggio di rischio. Si consiglia di specificare gli intervalli di indirizzi IP pubblici dell'organizzazione per la rete nella configurazione di Azure AD denominata Networks. Il traffico proveniente da queste gamme ha un punteggio di rischio ridotto e il traffico proveniente dall'esterno dell'ambiente dell'organizzazione riceve un punteggio di rischio maggiore.||
|[Registrare tutti gli utenti per la reimpostazione della password self-service (SSPR) e l'autenticazione a più fattori (AMF)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). È consigliabile registrare gli utenti per l'autenticazione a più fattori di Azure AD in anticipo. Azure AD Identity Protection utilizza l'autenticazione a più fattori di Azure AD per eseguire una verifica di sicurezza aggiuntiva. Inoltre, per la migliore esperienza di accesso, è consigliabile installare l' [app Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e l'app portale Microsoft Company sui propri dispositivi. Questi possono essere installati dall'App Store per ogni piattaforma.||
|[Abilitare la registrazione automatica del dispositivo dei computer Windows collegati al dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). L'accesso condizionale assicurerà che i dispositivi che si connettono alle app siano Uniti o conformi al dominio. A tale scopo, nei computer Windows, il dispositivo deve essere registrato con Azure AD.  In questo articolo viene illustrato come configurare la registrazione automatica dei dispositivi.|Solo cloud|
|**Preparare il team di supporto**. Predisporre un piano per gli utenti che non riescono a portare a termine l'autenticazione a più fattori. Questo potrebbe essere l'aggiunta a un gruppo di esclusione dei criteri o la registrazione di nuove informazioni sull'AMF. Prima di eseguire una di queste modifiche sensibili alla sicurezza, è necessario verificare che l'utente effettivo stia effettuando la richiesta. Un passaggio efficace consiste nel richiedere ai responsabili degli utenti di offrire assistenza nel processo di approvazione.||
|[Configurare il writeback delle password nell'AD locale](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Il writeback delle password consente a Azure AD di richiedere che gli utenti modifichino le password locali quando viene rilevato un compromesso per gli account ad alto rischio. È possibile abilitare questa funzionalità tramite Azure AD Connect in uno dei due modi seguenti: abilitare il **writeback della password** nella schermata funzionalità facoltative dell'installazione guidata di Azure ad Connect oppure abilitarla tramite Windows PowerShell.|Solo cloud|
|[Configurare la protezione delle password di Azure ad](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad). La protezione delle password di Azure AD rileva e blocca le password deboli note e le loro varianti, e può anche bloccare altri elementi vulnerabili specifici delle organizzazioni. Gli elenchi predefiniti di password escluse globalmente sono applicate automaticamente a tutti gli utenti dei tenant di Azure AD. È possibile definire altre voci in un elenco di password escluse personalizzato. Quando gli utenti modificano o reimpostano le loro password, gli elenchi di password escluse sono controllati per applicare l'uso di password sicure.||
|[Abilitare Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection). Azure AD Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione e configurare un criterio di correzione automatizzato per il rischio di accesso basso, medio e alto e rischi per gli utenti.||
|**Abilitare l'autenticazione moderna** per [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) e per [Skype for business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). L'autenticazione moderna è un prerequisito per l'utilizzo dell'AMF. L'autenticazione moderna è abilitata per impostazione predefinita per i client di Office 2016 e 2019, SharePoint e OneDrive for business.||
|

## <a name="recommended-client-configurations"></a>Configurazioni client consigliate

In questa sezione vengono descritte le configurazioni dei client della piattaforma predefinite che è consigliabile offrire agli utenti la migliore esperienza SSO, nonché i prerequisiti tecnici per l'accesso condizionale.

### <a name="windows-devices"></a>Dispositivi Windows

È consigliabile utilizzare Windows 10 (versione 2004 o successiva), in quanto Azure è stato creato per offrire la più agevole esperienza SSO possibile sia per l'ambiente locale che per Azure AD. Il lavoro o i dispositivi rilasciati dall'Istituto di istruzione devono essere configurati per partecipare direttamente a Azure AD o se l'organizzazione usa il dominio Active Directory locale, tali dispositivi devono essere [configurati per la registrazione automatica e invisibile all'utente di Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Per i dispositivi Windows BYOD, gli utenti possono utilizzare l' **account Aggiungi lavoro o dell'Istituto di istruzione**. Si noti che gli utenti del browser Google Chrome nei dispositivi Windows 10 devono [installare un'estensione](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) per ottenere la stessa esperienza di accesso agevole come utenti di Microsoft Edge. Inoltre, se l'organizzazione dispone di dispositivi Windows 8 o 8,1 con dominio, è possibile installare join di Microsoft area di lavoro per computer non Windows 10. [Scaricare il pacchetto per registrare](https://www.microsoft.com/download/details.aspx?id=53554) i dispositivi con Azure ad.

### <a name="ios-devices"></a>Dispositivi iOS

È consigliabile installare l' [app Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nei dispositivi utente prima di distribuire i criteri di accesso condizionale o dell'AMF. È necessario che l'app sia installata almeno quando agli utenti viene richiesto di registrare il proprio dispositivo con Azure AD aggiungendo un account aziendale o dell'Istituto di istruzione o quando si installa l'app Portal Company di Intune per registrare il dispositivo in gestione. Questo dipende dal criterio di accesso condizionale configurato.

### <a name="android-devices"></a>Dispositivi Android

Si consiglia agli utenti di installare l'app [portale aziendale di Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e l' [app Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) prima della distribuzione dei criteri di accesso condizionale o quando necessario durante alcuni tentativi di autenticazione. Dopo l'installazione delle app, è possibile che venga richiesto agli utenti di registrarsi con Azure AD o di registrare il dispositivo con Intune. Questo dipende dal criterio di accesso condizionale configurato.

È inoltre consigliabile che i dispositivi di proprietà dell'organizzazione siano standardizzati nei modelli OEM e nelle versioni che supportano Android per il lavoro o Samsung Knox per consentire gli account di posta elettronica, essere gestiti e protetti dal criterio MDM di Intune.

### <a name="recommended-email-clients"></a>Client di posta elettronica consigliati

I client di posta elettronica seguenti supportano l'autenticazione moderna e l'accesso condizionale. 

|Piattaforma|Client|Versione/Note|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Abilitare l'autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [Aggiornamenti necessari](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook per iOS|[Ultima versione](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook per Android|[Ultima versione](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 e 2016|
|**Linux**|Non supportato||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Piattaforme client consigliate per la protezione di documenti

Quando è stato applicato un criterio di protezione dei documenti, è consigliabile utilizzare i client seguenti.

|Piattaforma|Word/Excel/PowerPoint|OneNote|App OneDrive|App SharePoint|[Client di sincronizzazione di OneDrive](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Supportato|Supportato|N/D|N/D|Supportato|
|Windows 10|Supportato|Supportato|N/D|N/D|Supportato|
|Android|Supportato|Supportato|Supportato|Supportato|N/D|
|iOS|Supportato|Supportato|Supportato|Supportato|N/D|
|macOS|Supportato|Supportato|N/D|N/D|Non supportato|
|Linux|Non supportato|Non supportato|Non supportato|Non supportato|Non supportato|
|

### <a name="microsoft-365-client-support"></a>Supporto client di Microsoft 365

Per ulteriori informazioni sul supporto client in Microsoft 365, vedere gli articoli seguenti:

- [Supporto delle app client Microsoft 365-accesso condizionale](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Supporto delle app client Microsoft 365-autenticazione moderna](../../enterprise/microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protezione degli account amministratore

Per Microsoft 365 E3 o E5 o con licenze di Azure AD Premium P1 o P2 separate, è possibile richiedere l'autenticazione per gli account amministratore con un criterio di accesso condizionale creato manualmente. Per informazioni dettagliate, vedere [Conditional Access: require AMF for Administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) .

Per le edizioni di Microsoft 365 o Office 365 che non supportano l'accesso condizionale, è possibile abilitare le [impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per richiedere l'autenticazione a più fattori per tutti gli account.

Di seguito sono riportati alcuni suggerimenti aggiuntivi:

- Utilizzo di [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) per ridurre il numero di account amministrativi permanenti. 
- [Utilizzare la gestione degli accessi con privilegi](../../compliance/privileged-access-management-overview.md) per proteggere l'organizzazione da violazioni che possono utilizzare account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o accesso alle impostazioni di configurazione critiche. 
- Creare e utilizzare account distinti a cui sono assegnati i [ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *solo per l'amministrazione*. Gli amministratori devono disporre di un account utente specifico per l'utilizzo regolare non amministrativo e utilizzare un account amministrativo solo quando necessario per completare un'attività associata al ruolo o alla funzione del processo. 
- Seguire le [procedure consigliate](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) per la protezione degli account con privilegi in Azure ad.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 2: configurare i criteri di accesso condizionale e di identità comuni](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurare i criteri di identità e accesso ai dispositivi comuni](identity-access-policies.md)
