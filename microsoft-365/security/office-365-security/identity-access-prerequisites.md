---
title: Lavoro prerequisito per l'implementazione di criteri di identità e di accesso ai dispositivi - Microsoft 365 per le aziende | Documenti Microsoft
description: In questo articolo vengono descritti i prerequisiti necessari per usare i criteri e le configurazioni di identità e accesso ai dispositivi.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: edce65314062f731673926195be791f77d1cb823
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952549"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Attività preliminari per l'implementazione di criteri di identità e di accesso ai dispositivi

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- Azure

In questo articolo vengono descritti i prerequisiti che gli amministratori devono soddisfare per utilizzare i criteri di identità e accesso ai dispositivi consigliati e per l'utilizzo dell'accesso condizionale. Vengono inoltre illustrate le impostazioni predefinite consigliate per la configurazione delle piattaforme client per la migliore esperienza single sign-on (SSO).

## <a name="prerequisites"></a>Prerequisiti

Prima di usare i criteri di identità e accesso ai dispositivi consigliati, l'organizzazione deve soddisfare i prerequisiti. I requisiti sono diversi per i vari modelli di identità e autenticazione elencati:

- Solo cloud
- Ibrido con autenticazione phS (Password Hash Sync)
- Ibrido con autenticazione pass-through (PTA)
- Federato

Nella tabella seguente vengono fornite informazioni dettagliate sulle funzionalità dei prerequisiti e sulla relativa configurazione che si applicano a tutti i modelli di identità, ad eccezione dei casi in cui viene fatto riferimento.

|Configurazione|Eccezioni|Licenze|
|---|:---:|---|
|[Configurare PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Questo deve essere abilitato per rilevare le credenziali perse e agire su di esse per l'accesso condizionale basato sul rischio. **Nota:** Questa operazione è necessaria indipendentemente dal fatto che l'organizzazione utilizzi l'autenticazione federata.|Solo cloud|Microsoft 365 E3 o E5|
|[Abilitare single sign-on semplice per](/azure/active-directory/connect/active-directory-aadconnect-sso) accedere automaticamente agli utenti quando si tratta di dispositivi dell'organizzazione connessi alla rete dell'organizzazione.|Solo cloud e federato|Microsoft 365 E3 o E5|
|[Configurare i percorsi denominati](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations). Azure AD Identity Protection raccoglie e analizza tutti i dati di sessione disponibili per generare un punteggio di rischio. È consigliabile specificare gli intervalli IP pubblici dell'organizzazione per la rete nella configurazione delle posizioni denominate di Azure AD. Al traffico proveniente da questi intervalli viene assegnato un punteggio di rischio ridotto e al traffico proveniente dall'esterno dell'ambiente dell'organizzazione viene assegnato un punteggio di rischio maggiore.||Microsoft 365 E3 o E5|
|[Registrare tutti gli utenti per la reimpostazione della password self-service (SSPR) e l'autenticazione](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)a più fattori (MFA). Ti consigliamo di registrare gli utenti per Azure AD Multi-Factor Authentication in anticipo. Azure AD Identity Protection usa Azure AD Multi-Factor Authentication per eseguire ulteriori verifiche della sicurezza. Inoltre, per la migliore esperienza di accesso, ti consigliamo agli utenti di installare [l'app Microsoft Authenticator](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) e l'app Microsoft Portale aziendale nei propri dispositivi. Questi possono essere installati dall'app store per ogni piattaforma.||Microsoft 365 E3 o E5|
|[Abilitare la registrazione automatica dei dispositivi dei](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)computer Windows dominio . L'accesso condizionale assicura che i dispositivi che si connettono alle app siano aggiunti a un dominio o siano conformi. A tale scopo, nei computer Windows, il dispositivo deve essere registrato con Azure AD.  In questo articolo viene illustrato come configurare la registrazione automatica dei dispositivi.|Solo cloud|Microsoft 365 E3 o E5|
|**Preparare il team di supporto**. Predisporre un piano per gli utenti che non riescono a portare a termine l'autenticazione a più fattori. Questo potrebbe essere l'aggiunta a un gruppo di esclusione dei criteri o la registrazione di nuove informazioni MFA per loro. Prima di apportare una di queste modifiche sensibili alla sicurezza, devi assicurarti che l'utente effettivo eserciti la richiesta. Un passaggio efficace consiste nel richiedere ai responsabili degli utenti di offrire assistenza nel processo di approvazione.||Microsoft 365 E3 o E5|
|[Configurare il writeback delle password nell'AD locale](/azure/active-directory/active-directory-passwords-getting-started). Il writeback delle password consente ad Azure AD di richiedere agli utenti di modificare le password locali quando viene rilevata una compromissione dell'account ad alto rischio. È possibile abilitare questa funzionalità usando Azure AD Connessione in uno dei due modi seguenti: abilitare il **writeback delle** password nella schermata delle funzionalità facoltative della configurazione guidata di Azure AD Connessione o abilitarla tramite Windows PowerShell.|Solo cloud|Microsoft 365 E3 o E5|
|[Configurare la protezione con password di Azure AD](/azure/active-directory/authentication/concept-password-ban-bad). La protezione delle password di Azure AD rileva e blocca le password deboli note e le loro varianti, e può anche bloccare altri elementi vulnerabili specifici delle organizzazioni. Gli elenchi predefiniti di password escluse globalmente sono applicate automaticamente a tutti gli utenti dei tenant di Azure AD. È possibile definire altre voci in un elenco di password escluse personalizzato. Quando gli utenti modificano o reimpostano le loro password, gli elenchi di password escluse sono controllati per applicare l'uso di password sicure.||Microsoft 365 E3 o E5|
|[Abilitare Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection). Azure AD Identity Protection consente di rilevare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione e di configurare un criterio di correzione automatizzato a basso, medio e alto rischio di accesso e rischio per gli utenti.||Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo E5 Security|
|**Abilitare l'autenticazione** moderna [Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) e [per Skype for Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). L'autenticazione moderna è un prerequisito per l'utilizzo di MFA. L'autenticazione moderna è abilitata per impostazione Office 2016 e 2019, SharePoint e OneDrive for Business.||Microsoft 365 E3 o E5|
|

## <a name="recommended-client-configurations"></a>Configurazioni client consigliate

In questa sezione vengono descritte le configurazioni client della piattaforma predefinita che è consigliabile offrire agli utenti la migliore esperienza SSO, nonché i prerequisiti tecnici per l'accesso condizionale.

### <a name="windows-devices"></a>Dispositivi Windows

È consigliabile Windows 10 (versione 2004 o successiva), poiché Azure è progettato per offrire l'esperienza SSO più fluida possibile sia per l'ambiente locale che per Azure AD. I dispositivi emessi dall'azienda o dall'istituto di istruzione devono essere configurati per l'aggiunta diretta ad Azure AD o se l'organizzazione usa l'aggiunta al dominio AD locale, questi dispositivi devono essere configurati per la registrazione automatica e invisibile all'utente [con Azure AD.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Per i dispositivi Windows BYOD, gli utenti possono usare Aggiungi account aziendale **o dell'istituto di istruzione.** Tieni presente che gli utenti del browser Google [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) Chrome nei dispositivi Windows 10 devono installare un'estensione per ottenere la stessa esperienza di accesso uniforme degli utenti Microsoft Edge utenti. Inoltre, se l'organizzazione ha dispositivi Windows 8 o 8.1 aggiunti al dominio, è possibile installare Microsoft Workplace Join per i computer non Windows 10. [Scaricare il pacchetto per registrare](https://www.microsoft.com/download/details.aspx?id=53554) i dispositivi con Azure AD.

### <a name="ios-devices"></a>Dispositivi iOS

Ti consigliamo di installare [l'app Microsoft Authenticator nei](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) dispositivi degli utenti prima di distribuire i criteri di accesso condizionale o MFA. Come minimo, l'app deve essere installata quando agli utenti viene richiesto di registrare il dispositivo con Azure AD aggiungendo un account aziendale o dell'istituto di istruzione o quando installano l'app portale aziendale intune per registrare il dispositivo nella gestione. Dipende dal criterio di accesso condizionale configurato.

### <a name="android-devices"></a>Dispositivi Android

È consigliabile che gli utenti installino [l'app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) Portale aziendale Intune e Microsoft Authenticator [prima](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) della distribuzione dei criteri di accesso condizionale o quando necessario durante determinati tentativi di autenticazione. Dopo l'installazione delle app, è possibile che venga richiesto agli utenti di registrarsi con Azure AD o di registrare il dispositivo con Intune. Dipende dal criterio di accesso condizionale configurato.

È inoltre consigliabile che i dispositivi di proprietà dell'organizzazione siano standardizzati negli OEM e nelle versioni che supportano Android for Work o Samsung Knox per consentire agli account di posta elettronica di essere gestiti e protetti dai criteri MDM di Intune.

### <a name="recommended-email-clients"></a>Client di posta elettronica consigliati

I client di posta elettronica seguenti supportano l'autenticazione moderna e l'accesso condizionale.

|Piattaforma|Client|Versione/Note|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Abilitare l'autenticazione moderna](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Aggiornamenti necessari](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook per iOS|[Ultima versione](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook per Android|[Ultima versione](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 e 2016|
|**Linux**|Non supportato||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Piattaforme client consigliate per la protezione di documenti

Quando viene applicato un criterio di protezione dei documenti, è consigliabile utilizzare i client seguenti.

|Piattaforma|Word/Excel/PowerPoint|OneNote|App OneDrive|App SharePoint|[Client di sincronizzazione di OneDrive](/onedrive/enable-conditional-access)|
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

- [Microsoft 365 Supporto app client - Accesso condizionale](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 Supporto app client - Autenticazione a più fattori](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protezione degli account amministratore

Per Microsoft 365 E3 O E5 o con licenze di Azure AD Premium P1 o P2 separate, è possibile richiedere l'autenticazione a più fattori per gli account amministratore con un criterio di accesso condizionale creato manualmente. Per [informazioni dettagliate, vedere Conditional Access: Require MFA for administrators.](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

Per le edizioni di Microsoft 365 o Office 365 che non supportano [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) l'accesso condizionale, è possibile abilitare le impostazioni predefinite di sicurezza per richiedere l'autenticazione a più fattori per tutti gli account.

Ecco alcuni suggerimenti aggiuntivi:

- Usare [Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started) per ridurre il numero di account amministrativi permanenti.
- [Utilizzare la gestione degli accessi](../../compliance/privileged-access-management-overview.md) privilegiati per proteggere l'organizzazione da violazioni che potrebbero utilizzare account di amministratore con privilegi esistenti con accesso permanente a dati sensibili o accesso a impostazioni di configurazione critiche.
- Creare e utilizzare account separati assegnati Microsoft 365 [di amministratore](../../admin/add-users/about-admin-roles.md) solo *per l'amministrazione*. Gli amministratori devono disporre del proprio account utente per un normale utilizzo non amministrativo e utilizzare un account amministrativo solo se necessario per completare un'attività associata al proprio ruolo o funzione lavorativa.
- Seguire [le procedure consigliate](/azure/active-directory/admin-roles-best-practices) per la protezione degli account con privilegi in Azure AD.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 2: Configurare l'identità comune e i criteri di accesso condizionale](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurare i criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md)