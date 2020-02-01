---
title: Lavoro prerequisito per l'implementazione dei criteri di identità e accesso ai dispositivi-Microsoft 365 Enterprise | Documenti Microsoft
description: Descrive i criteri per i consigli di Microsoft su come applicare i criteri e le configurazioni relativi all'identità e all'accesso ai dispositivi.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c1af88f489072490777cc6f2c7edfc66fd038bdf
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601023"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Lavoro prerequisito per l'implementazione dei criteri di identità e accesso ai dispositivi

In questo articolo vengono descritti i prerequisiti che devono essere implementati prima di poter distribuire i criteri di identità e accesso ai dispositivi consigliati. In questo articolo vengono illustrate anche le configurazioni dei client di piattaforma predefinite che è consigliabile offrire agli utenti la migliore esperienza SSO, nonché i prerequisiti tecnici per l'accesso condizionale.


## <a name="prerequisites"></a>Prerequisiti

Prima di implementare i criteri di identità e accesso ai dispositivi consigliati, esistono numerosi prerequisiti che l'organizzazione deve soddisfare. Nella tabella seguente vengono illustrati i prerequisiti che si applicano all'ambiente. 


| Configurazione | Solo cloud | Active Directory con sincronizzazione hash delle password |  Autenticazione pass-through |  Federazione con ADFS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configurare la sincronizzazione hash delle password](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Questo deve essere abilitato per rilevare le credenziali trapelate e per agire su di esse per l'accesso condizionale basato sui rischi. **Nota:** Ciò è necessario indipendentemente dal fatto che l'organizzazione utilizzi l'autenticazione gestita, ad esempio l'autenticazione pass-through (PTA) o l'autenticazione federata. |    | Sì | Sì | Sì |
| [Abilitare l'accesso Single Sign-on senza](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) problemi per la firma automatica degli utenti quando si trovano nei propri dispositivi aziendali connessi alla rete aziendale. |  | Sì | Sì |  |
| [Configurare le reti denominate](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection raccoglie e analizza tutti i dati di sessione disponibili per generare un punteggio di rischio. Si consiglia di specificare gli intervalli di indirizzi IP pubblici dell'organizzazione per la rete nella configurazione di Azure AD denominata Networks. Il traffico proveniente da queste gamme ha un punteggio di rischio ridotto e il traffico proveniente dall'esterno dell'ambiente aziendale riceve un punteggio di rischio maggiore. | Sì  | Sì | Sì | Sì |
|[Registrare tutti gli utenti per la reimpostazione della password self-service (SSPR) e l'autenticazione a più fattori (AMF)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). È consigliabile registrare gli utenti per Azure Mae prima del tempo. Azure AD Identity Protection usa Azure MFA per eseguire una verifica della sicurezza aggiuntiva. Inoltre, per la migliore esperienza di accesso, è consigliabile installare l' [app Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e l'app portale Microsoft Company sui propri dispositivi. Questi possono essere installati dall'App Store per ogni piattaforma. | Sì | Sì | Sì | Sì |
| [Abilitare la registrazione automatica del dispositivo dei computer Windows collegati al dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). L'accesso condizionale assicurerà che i dispositivi che si connettono alle app siano Uniti o conformi al dominio. A tale scopo, nei computer Windows, il dispositivo deve essere registrato con Azure AD.  In questo articolo viene illustrato come configurare la registrazione automatica dei dispositivi. |   | Sì |  Sì |  Sì |
| **Preparare il team di supporto**. Predisporre un piano per gli utenti che non riescono a portare a termine l'autenticazione a più fattori. Questo potrebbe essere l'aggiunta a un gruppo di esclusione dei criteri o la registrazione di nuove informazioni sull'AMF. Prima di eseguire una di queste modifiche sensibili alla sicurezza, è necessario verificare che l'utente effettivo stia effettuando la richiesta. Un passaggio efficace consiste nel richiedere ai responsabili degli utenti di offrire assistenza nel processo di approvazione. | Sì | Sì | Sì | Sì |  
| [Configurare il writeback delle password nell'AD locale](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Il writeback delle password consente a Azure AD di richiedere che gli utenti modifichino le password locali quando viene rilevato un compromesso per gli account ad alto rischio. È possibile abilitare questa funzionalità tramite Azure AD Connect in uno dei due modi seguenti: abilitare il **writeback della password** nella schermata funzionalità facoltative dell'installazione guidata di Azure ad Connect oppure abilitarla tramite Windows PowerShell. |   | Sì | Sì | Sì |
| [Abilitare Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Azure AD Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione e configurare un criterio di correzione automatizzato per il rischio di accesso basso, medio e alto e rischi per gli utenti.  | Sì | Sì | Sì | Sì |
| **Abilitare l'autenticazione moderna** per [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e per [Skype for business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). L'autenticazione moderna è un prerequisito per l'utilizzo dell'autenticazione a più fattori (AMF). L'autenticazione moderna è abilitata per impostazione predefinita per i client di Office 2016, SharePoint Online e OneDrive for business. | Sì | Sì | Sì | Sì |
||||||



## <a name="recommended-client-configurations"></a>Configurazioni client consigliate
In questa sezione vengono descritte le configurazioni dei client della piattaforma predefinite che è consigliabile offrire agli utenti la migliore esperienza SSO, nonché i prerequisiti tecnici per l'accesso condizionale.

### <a name="windows-devices"></a>Dispositivi Windows
È consigliabile usare Windows 10, versione 1703 o successive, poiché Azure è progettato per offrire un'esperienza di uso ottimale di SSO sia in locale che in Azure AD. Il lavoro o i dispositivi rilasciati dall'Istituto di istruzione devono essere configurati per partecipare direttamente a Azure AD o se l'organizzazione usa il dominio Active Directory locale, tali dispositivi devono essere [configurati per la registrazione automatica e invisibile all'utente di Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Per i dispositivi Windows BYOD, gli utenti possono utilizzare l' **account Aggiungi lavoro o dell'Istituto di istruzione**. Si noti che gli utenti di Chrome-browser su Windows 10 devono [installare un'estensione](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) per ottenere la stessa esperienza di accesso liscio come utenti di Edge/IE. Inoltre, se l'organizzazione dispone di dispositivi Windows 7 appartenenti al dominio, è possibile installare join di Microsoft posto di lavoro per i computer non Windows 10 [scaricare il pacchetto per registrare](https://www.microsoft.com/download/details.aspx?id=53554) i dispositivi con Azure ad.

### <a name="ios-devices"></a>Dispositivi iOS
È consigliabile installare l'[app Microsoft Authenticator ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) sui dispositivi degli utenti prima di distribuire i criteri MFA o dell'accesso condizionale. È necessario che l'app sia installata almeno quando agli utenti viene richiesto di registrare il proprio dispositivo con Azure AD aggiungendo un account aziendale o dell'Istituto di istruzione o quando si installa l'app Portal Company di Intune per registrare il dispositivo in gestione. Ciò dipende dai criteri di accesso condizionale configurati.

### <a name="android-devices"></a>Dispositivi Android
È consigliabile che gli utenti installino l'[app Portale aziendale Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) e l'[app Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) prima che vengano distribuiti i criteri di accesso condizionale o quando richiesto durante determinati tentativi di autenticazione. Dopo l'installazione delle app, è possibile che venga richiesto agli utenti di registrarsi con Azure AD o di registrare il dispositivo con Intune. Ciò dipende dai criteri di accesso condizionale configurati.

È inoltre consigliabile che i dispositivi aziendali (COD) siano standardizzati nei modelli OEM e nelle versioni che supportano Android for Work o Samsung Knox per consentire gli account di posta elettronica, essere gestiti e protetti dal criterio MDM di Intune.


### <a name="recommended-email-clients"></a>Client di posta elettronica consigliati
I client di posta elettronica seguenti supportano l'autenticazione moderna e l'accesso condizionale. 

|Piattaforma|Client|Versione/Note|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [abilitare l'autenticazione moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [gli aggiornamenti necessari](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook per iOS|[Ultima versione](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook per Android|[Ultima versione](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Non supportato||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Piattaforme client consigliate per la protezione di documenti
Quando è stato applicato un criterio di protezione dei documenti, è consigliabile utilizzare i client seguenti.

|Piattaforma|Word/Excel/PowerPoint|OneNote|App OneDrive|App SharePoint|Client di sincronizzazione di OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows 8.1|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows 10|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows Phone 10|Non supportato|Non supportato|Non supportato|Non supportato|Non supportato|
|Android|Supportato|Supportato|Supportato|Supportato|N/D|
|iOS|Supportato|Supportato|Supportato|Supportato|N/D|
|macOS|Anteprima pubblica|Anteprima pubblica|N/D|N/D|Non supportato|
|Linux|Non supportato|Non supportato|Non supportato|Non supportato|Non supportato|

<sup>*</sup>Ulteriori informazioni sull'utilizzo dell'accesso condizionale con il [client di sincronizzazione di OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Supporto client di Office 365
Per ulteriori informazioni sul supporto client di Office 365, vedere gli articoli seguenti:
- [Supporto delle app client di Office 365-accesso condizionale](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Supporto delle app client di Office 365-gestione di applicazioni mobili](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Supporto delle app client di Office 365-autenticazione moderna](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protezione degli account amministratore
Azure AD offre un modo semplice per iniziare a proteggere l'accesso dell'amministratore con un criterio di accesso condizionale preconfigurato. In Azure Active Directory, andare a **accesso condizionale** e cercare questo criterio, **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**. Selezionare questo criterio e quindi selezionare **Usa criteri immediatamente**. 

Questo criterio richiede l'AMF per i ruoli seguenti:
- Amministratori globali
- Amministratori di SharePoint
- Amministratori di Exchange
- Amministratori degli accessi condizionali
- Amministratori della sicurezza

Per ulteriori informazioni, vedere [criteri di sicurezza di base per gli account di amministrazione di Azure ad](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Di seguito sono riportati alcuni suggerimenti:
- Usare Azure AD Privileged Identity Management per ridurre il numero di account amministrativi permanenti. Vedere [iniziare a usare PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Utilizzare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) per proteggere l'organizzazione da violazioni che possono utilizzare account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o accesso alle impostazioni di configurazione critiche. 
- Utilizzare gli account Administrator solo per l'amministrazione. Gli amministratori devono disporre di un account utente distinto per l'utilizzo regolare non amministrativo e utilizzare il proprio account amministrativo solo quando necessario per completare un'attività associata alla propria funzione processi. I ruoli di [amministratore di office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) dispongono di privilegi sostanzialmente superiori rispetto ai servizi di Office 365.
- Seguire le procedure consigliate per la protezione degli account con privilegi in Azure AD, come descritto in questo [articolo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Passaggi successivi

[Configurare i criteri di identità e accesso ai dispositivi comuni](identity-access-policies.md)

