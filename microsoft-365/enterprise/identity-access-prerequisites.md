---
title: Lavoro prerequisito per l'implementazione di identità e il dispositivo accedere criteri - Microsoft 365 Enterprise | Documenti di Microsoft
description: Descrive i criteri per i consigli di Microsoft su come applicare i criteri e le configurazioni relativi all'identità e all'accesso ai dispositivi.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868934"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Lavoro prerequisito per l'implementazione di criteri di accesso di identità e dei dispositivi

In questo articolo vengono descritti i prerequisiti necessari implementare prima di distribuire l'identità consigliata e i criteri di accesso di dispositivi. In questo articolo viene inoltre le configurazioni di client piattaforma predefinito, che è consigliabile per offrire un'esperienza ottimale SSO per gli utenti, nonché i prerequisiti tecnici per l'accesso condizionale.


## <a name="prerequisites"></a>Prerequisiti

Prima di implementare l'identità consigliata e i criteri di accesso di dispositivi, esistono diversi prerequisiti che deve essere soddisfatti nell'organizzazione. Vedere la tabella seguente per i prerequisiti che si applicano all'ambiente. 


| Configurazione | Solo cloud | Active Directory con sincronizzazione delle password hash |  Federazione con ADFS |
| :------------- | :-----------: | :--------------: | :------------: |
|  [Configurare la sincronizzazione delle Password Hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Si deve essere abilitato per rilevare la perdita delle credenziali e per agire su di essi per rischio basato su accesso condizionale. **Nota:** Ciò è necessaria, indipendentemente dal fatto che l'organizzazione utilizza l'autenticazione gestito, come autenticazione pass-through (PTA) o l'autenticazione federata. |    | Sì | Sì |
| [Abilitare single sign-on semplice](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) per accedere automaticamente gli utenti quando si trovano nei rispettivi dispositivi aziendali connessi alla rete aziendale. |  | Sì |  |
| [Configure denominato reti](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure Active Directory Identity protezione raccoglie e l'analisi di tutti i dati della sessione disponibili per generare un punteggio di rischio. È consigliabile che specificare intervalli IP pubblici dell'organizzazione per la rete di Azure Active Directory denominato configurazione reti. Il traffico proveniente da questi intervalli viene assegnato un punteggio di riduzione dei rischi, in modo che il traffico dall'esterno dell'ambiente aziendale verrà considerato come punteggio di rischio. | Sì  | Sì | Sì |
|[Registrare tutti gli utenti per la reimpostazione della password self-service (SSPR) e l'autenticazione a più fattori (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). È consigliabile che eseguire la registrazione degli utenti di MFA di Azure anticipo. La protezione dell'identità di Azure Active Directory viene utilizzato per eseguire la verifica di protezione aggiuntive MFA di Azure. Inoltre, per la migliore esperienza di accesso, è consigliabile install utenti [Microsoft autenticatore App](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e l'app portale della società Microsoft nei rispettivi dispositivi. È possibile installarli dall'archivio di app per ogni piattaforma. | Sì | Sì | Sì |
| [Abilitare la registrazione automatica dei dispositivi dei computer Windows con dominio associato](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). L'accesso condizionale può garantire che il dispositivo che si collega al servizio sia un dispositivo con dominio associato o un dispositivo conforme. A tale scopo, nei computer Windows, il dispositivo deve essere registrato con Azure AD.  In questo articolo viene illustrato come configurare la registrazione automatica dei dispositivi. |   | Sì |  Sì |
| **Preparare il team di supporto**. Predisporre un piano per gli utenti che non riescono a portare a termine l'autenticazione a più fattori. Tale piano potrebbe prevedere la loro aggiunta a un gruppo di esclusione di criteri o la registrazione di nuove informazioni di autenticazione a più fattori a loro riguardo. Prima di apportare una di queste modifiche relative alla sicurezza, è necessario verificare che l'utente effettivo presenti la richiesta. Un passaggio efficace consiste nel richiedere ai responsabili degli utenti di offrire assistenza nel processo di approvazione. | Sì | Sì | Sì |
| [Configurare il writeback delle password nell'AD locale](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Il writeback delle password consente ad Azure AD di richiedere che gli utenti modifichino le loro password locali quando è stato rilevato un rischio elevato di compromissione di account. È possibile abilitare questa funzionalità con Azure AD Connect in due modi. È possibile abilitare il writeback delle password nella schermata delle funzionalità opzionali della procedura guidata di Azure AD Connect oppure è possibile abilitarlo tramite Windows PowerShell. |   | Sì | Sì |
| [Abilitare la protezione con identità Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Protezione Azure Active Directory Identity consente di rilevare potenziale vulnerabilità che interessano le identità dell'organizzazione e configurare i criteri di correzione automatica per utente rischi e dei rischi bassa, medio e alta accesso.  | Sì | Sì | Sì |
| **Abilitare l'autenticazione moderno** per [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e [Skype Business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Autenticazione moderno è un prerequisito per l'utilizzo di autenticazione a più fattori (MFA). Autenticazione moderno è abilitata per impostazione predefinita per Office 2016 client, SharePoint Online e OneDrive for Business. | Sì | Sì | Sì |
|||||



## <a name="recommended-client-configurations"></a>Configurazioni client consigliate
In questa sezione vengono descritte le configurazioni client della piattaforma predefinite consigliate per offrire un'esperienza SSO ottimale agli utenti, oltre ai prerequisiti tecnici per l'accesso condizionale.

### <a name="windows-devices"></a>Dispositivi Windows
È consigliabile usare Windows 10, versione 1703 o successive, poiché Azure è progettato per offrire un'esperienza di uso ottimale di SSO sia in locale che in Azure AD. I dispositivi aziendali o dell'istituto di istruzione devono essere configurati per unirsi ad Azure AD direttamente o, se l'organizzazione usa l'aggiunta a un dominio AD in locale, devono essere [configurati per la registrazione automatica e invisibile con Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Per i dispositivi Windows BYOD, gli utenti possono usare "Aggiungi account aziendale o dell'istituto di istruzione". Si noti che gli utenti del browser Chrome in Windows 10 devono [installare un'estensione](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) per poter ottenere la stessa esperienza di accesso ottimale degli utenti di Edge o Internet Explorer. Se l'organizzazione ha dispositivi Windows 7 aggiunti a un dominio, è possibile installare il pacchetto [Microsoft Workplace Join per i computer non Windows 10](https://www.microsoft.com/download/details.aspx?id=53554) per registrare i dispositivi con Azure AD.

### <a name="ios-devices"></a>Dispositivi iOS
È consigliabile installare l' [applicazione Microsoft autenticatore](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nei dispositivi utente prima di distribuire l'accesso condizionale o criteri di MFA. Come minimo necessario installare l'app quando gli utenti vengono chiesto di registrare i dispositivi con Azure Active Directory mediante l'aggiunta di un ufficio o scuola account o quando si installa l'app portale aziendale Intune per registrare i dispositivi in Gestione. Ciò dipende il criterio di accesso condizionale configurato.

### <a name="android-devices"></a>Dispositivi Android
È consigliabile che gli utenti installino l'[app Portale aziendale Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) e l'[app Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) prima che vengano distribuiti i criteri di accesso condizionale o quando richiesto durante determinati tentativi di autenticazione. Dopo l'installazione delle app, è possibile che venga richiesto agli utenti di registrarsi con Azure AD o di registrare il dispositivo con Intune. Ciò dipende dai criteri di accesso condizionale configurati.

È consigliabile anche che i dispositivi di proprietà dell'azienda vengano normalizzati in OEM e che le versioni che supportano Android for Work o Samsung Knox consentano che gli account di posta elettronica siano gestiti e protetti dai criteri MDM Intune.


### <a name="recommended-email-clients"></a>Client di posta elettronica consigliati
I client di posta elettronica seguenti supportano l'autenticazione moderno e accesso condizionale. 

|Piattaforma|Client|Versione/Note|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Abilitare l'autenticazione moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [aggiornamenti obbligatori](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook per iOS|[Ultima versione](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook per Android|[Ultima versione](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Mac OS**|Outlook|2016|
|**Linux**|Non supportato||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Piattaforme client consigliate per la protezione di documenti
I client seguenti sono consigliati nei casi in cui è stato applicato un criterio di protezione dei documenti.

|Piattaforma|Word, Excel o di PowerPoint|OneNote|App OneDrive|App SharePoint|Client di sincronizzazione di OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows 8.1|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows 10|Supportato|Supportato|N/D|N/D|Anteprima<sup>*</sup>|
|Windows Phone 10|Non supportato|Non supportato|Non supportato|Non supportato|Non supportato|
|Android|Supportato|Supportato|Supportato|Supportato|N/D|
|iOS|Supportato|Supportato|Supportato|Supportato|N/D|
|Mac OS|Anteprima pubblica|Anteprima pubblica|N/D|N/D|Non supportato|
|Linux|Non supportato|Non supportato|Non supportato|Non supportato|Non supportato|

<sup>*</sup>Ulteriori informazioni sull'utilizzo di access condizionale con il [Client di sincronizzazione OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Supporto client di Office 365
Per ulteriori informazioni sul supporto di client di Office 365, vedere gli articoli seguenti:
- [Supporto per applicazioni Client Office 365 - accesso condizionale](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Supporto per applicazioni Client Office 365 - Gestione applicazioni per dispositivi mobili](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Supporto per applicazioni Client Office 365 - autenticazione moderno](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protezione di account amministratore
Azure Active Directory fornisce un modo semplice per iniziare la protezione dell'accesso di amministratore con un criterio di accesso condizionale preconfigurato. All'interno di Azure Active Directory, passare a blade accesso condizionato e cercare questo criterio, ovvero **dei criteri di base: richiedono MFA per gli amministratori**. Fare clic sul criterio e selezionare **immediatamente i criteri di utilizzo**. 

Questo criterio è necessario MFA per i ruoli seguenti:
- Amministratori globali
- Amministratori di SharePoint
- Amministratori di Exchange
- Amministratori di accesso condizionato
- Amministratori della protezione

Per ulteriori informazioni, vedere [criteri di sicurezza di base per gli account di amministrazione di Azure Active Directory](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Ulteriori consigli includono quanto segue:
- Gestione delle identità con privilegi di Azure Active Directory per ridurre il numero di account amministrativi permanenti. Vedere [iniziare a utilizzare personali](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Utilizzare accesso privilegiato management in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) per proteggere l'organizzazione da violazioni che possono essere utilizzati esistenti privilegi account amministratore con la condizione accesso ai dati riservati o l'accesso alle impostazioni di configurazione critico. 
- Utilizzare gli account di amministratore di Office 365 solo per l'amministrazione. Gli amministratori devono disporre un utente diverso per gli account per l'utilizzo non amministrativi regolare e utilizzare solo il proprio account amministrativo quando necessario per completare un'attività associata alla funzione processo. Ruoli di [amministratore di Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) sono sostanzialmente maggiori privilegi ai servizi di Office 365.
- Seguire le procedure consigliate per la protezione di account con privilegi di Azure Active Directory come descritto in questo [articolo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Passaggi successivi

[Configurare i criteri di accesso di dispositivi e l'identità comuni](identity-access-policies.md)

