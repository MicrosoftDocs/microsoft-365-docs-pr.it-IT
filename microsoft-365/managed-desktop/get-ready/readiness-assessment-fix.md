---
title: Risolvere problemi trovati dallo strumento di valutazione dell'idoneità
description: Azioni dettagliate da intraprendere per ogni problema rilevato dallo strumento
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c342ea9f662d883883755d2f67e5c25ffabddf83
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948410"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Risolvere problemi trovati dallo strumento di valutazione dell'idoneità

Per ogni controllo, lo strumento riporterà uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessario eseguire alcuna operazione prima di completare la registrazione.        |
|Consulenza    | Seguire la procedura descritta nello strumento o in questo articolo per la migliore esperienza di registrazione e per gli utenti. È *possibile* completare la registrazione, ma è necessario correggere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito negativo se non si correggeranno questi problemi.* Seguire la procedura descritta nello strumento o in questo articolo per risolverli.        |
|Error | Il ruolo di Azure Active Director (AD) utilizzato non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

### <a name="autopilot-deployment-profile"></a>Profilo di distribuzione Autopilot

Non è necessario disporre di profili Autopilot esistenti per i gruppi assegnati o dinamici utilizzati da Microsoft Managed Desktop. Microsoft Managed Desktop utilizza il pilota automatico per eseguire il provisioning di nuovi dispositivi.

**Non pronto**

Si dispone di un profilo Autopilot assegnato a tutti i dispositivi. Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.

**Consulenza**

Assicurarsi che i profili Autopilot siano destinati a un gruppo di Azure AD assegnato o dinamico che non includa i dispositivi desktop Microsoft gestiti che verranno creati in fase di registrazione. Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Dopo la registrazione di Microsoft Managed Desktop, impostare il criterio Autopilot per escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad.


### <a name="certificate-connectors"></a>Connettori per i certificati

Se si dispone di qualsiasi connettore di certificato utilizzato dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non possono avere errori. Solo uno dei seguenti consulenti si applicherà alla situazione, quindi controllali con attenzione.

**Consulenza**

Non sono presenti connettori di certificato. È possibile che non siano necessari connettori, ma è necessario valutare se potrebbe essere necessario un po' di connettività di rete per i dispositivi desktop Microsoft gestiti. Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

**Consulenza**

Almeno un connettore di certificato ha un errore. Se è necessario questo connettore per la connettività ai dispositivi Microsoft Managed Desktop, è necessario risolvere l'errore. Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


**Consulenza**

Si dispone di almeno un connettore di certificato e non vengono segnalati errori. Tuttavia, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Prepare certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Manage desktop.

**Non pronto**

Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti. Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa il gruppo di Azure AD degli account di servizio di Microsoft Managed Desktop che verranno creati in fase di registrazione. Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Consulenza**

Verificare che tutti i criteri di accesso condizionale siano esclusi dal gruppo di Azure AD degli **account di servizio sul posto di lavoro moderno** . Per i passaggi, vedere [regolare l'accesso condizionale](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access). Il gruppo di Azure AD dei **servizi di ambiente di lavoro moderno** è un gruppo dinamico creato per il servizio quando si esegue la registrazione. Sarà necessario tornare a escludere questo gruppo dopo la registrazione. Per ulteriori informazioni su questi account di servizio, vedere [standard operative Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore dell'accesso condizionale
- Ruolo con autorizzazioni di lettura globali
- Amministratore di dispositivi


### <a name="device-compliance-policies"></a>Criteri di conformità del dispositivo

I criteri di conformità dei dispositivi di Intune nell'organizzazione di Azure AD non devono essere destinati agli utenti di Microsoft Managed Desktop.

**Non pronto**

Si dispone di almeno un criterio di conformità che è destinato a tutti gli utenti. Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa gli utenti di Microsoft Managed Desktop. Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).

**Consulenza**

Verificare che i criteri di conformità non includano gli utenti di Microsoft Managed Desktop. Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-policies"></a>Criteri di configurazione del dispositivo

I criteri di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere destinati a qualsiasi dispositivo o utente di Microsoft Manage desktop.

**Non pronto**

Si dispone di almeno un criterio di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi. Reimpostare i criteri in modo che vengano indirizzati a un gruppo di Azure AD specifico che non includa alcun dispositivo desktop Microsoft gestito. Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

**Consulenza**

Verificare che i criteri di conformità non includano dispositivi o utenti desktop Microsoft gestiti. Per i passaggi, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restrizioni per il tipo di dispositivo

I dispositivi Microsoft Managed Desktop devono essere autorizzati a eseguire la registrazione in Intune.

**Non pronto**

Seguire la procedura descritta in [set Restriction](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) **consentitions** to change the setting to allow.


### <a name="enrollment-status-page"></a>Pagina stato registrazione

La pagina stato di registrazione (ESP) è attualmente abilitata. Se si partecipa all'anteprima pubblica di questa funzionalità, è possibile ignorare questo elemento. Per ulteriori informazioni, vedere [First-Run experience with Autopilot e la pagina status di registrazione](../get-started/esp-first-run.md).

**Non pronto**

Si dispone del set di profili ESP predefinito per **visualizzare lo stato di avanzamento della configurazione dei profili e delle app**. Disabilitare questa impostazione o verificare che le assegnazioni a un gruppo di Azure AD non includano i dispositivi Microsoft Managed Desktop attenendosi alla procedura descritta in [set up the registration status page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

**Consulenza**

Verificare che i profili con l'impostazione **Mostra avanzamento configurazione app e profilo** non siano assegnati a nessun gruppo di Azure ad che includa i dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [configurare la pagina stato di registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

### <a name="intune-enrollment"></a>Registrazione di Intune

I dispositivi Windows 10 nell'organizzazione di Azure AD devono essere registrati automaticamente in Intune.

**Consulenza**

Verificare che l'ambito dell'utente MDM sia impostato su **alcuni** o su **tutti** , non su **None**. Se si sceglie **alcuni** , tornare dopo la registrazione e selezionare la **moderna area di lavoro-tutto** il gruppo di Azure ad per i **gruppi**.


### <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Microsoft Store for business viene utilizzato in modo da poter scaricare il portale aziendale per distribuire alcune app, ad esempio Microsoft Project e Microsoft Visio.

**Non pronto**

Microsoft Store for business non è abilitato o non è sincronizzato con Intune. Per ulteriori informazioni, vedere [How to Manage volume purchased Apps from the Microsoft Store for business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on Devices](../get-started/company-portal.md).

### <a name="multi-factor-authentication"></a>Autenticazione a più fattori

Per l'autenticazione a più fattori non è necessario applicare accidentalmente gli account di servizio di Microsoft Managed Desktop.


**Non pronto**

Si dispone di alcuni criteri di autenticazione a più fattori (AMF) impostati come "necessari" per i criteri di accesso condizionale assegnati a tutti gli utenti. Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito. Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Consulenza**

Verificare che tutti i criteri di accesso condizionale che richiedono l'AMF escludano la **moderna area di lavoro-tutti i** gruppi di Azure ad. Per ulteriori informazioni, vedere [criteri di accesso condizionale](#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). La **moderna area di lavoro-tutti i** gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Sarà inoltre necessario uno qualsiasi dei ruoli di Azure AD assegnati per eseguire il controllo:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore dell'accesso condizionale
- Ruolo con autorizzazioni di lettura globali
- Amministratore di dispositivi


### <a name="powershell-scripts"></a>Script di PowerShell

Gli script di Windows PowerShell non possono essere assegnati in modo da indirizzare i dispositivi Microsoft Managed Desktop.  

**Consulenza**

Assicurarsi che gli script di Windows PowerShell nell'organizzazione Azure AD non vengano indirizzati a qualsiasi dispositivo o utente di Microsoft Manage desktop. Non assegnare uno script di PowerShell per indirizzare tutti gli utenti, tutti i dispositivi o entrambi. Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito. Per ulteriori informazioni, vedere [utilizzare gli script di PowerShell nei dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Area geografica

La propria area geografica deve essere supportata da Microsoft Managed Desktop.

**Non pronto**

L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop. Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).

**Consulenza**

Uno o più dei paesi in cui si trova l'organizzazione Azure AD non è supportato da Microsoft Managed Desktop. Per ulteriori informazioni, vedere [aree e lingue supportate da Microsoft Managed Desktop](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Linee di base per la sicurezza

I criteri di base di sicurezza non devono essere destinati ai dispositivi Microsoft Managed Desktop.

**Non pronto**

Si dispone di un profilo di base di sicurezza che è destinato a tutti gli utenti, tutti i dispositivi o entrambi. Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito. Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).

**Consulenza**

Assicurarsi che tutti i criteri di base di sicurezza che è possibile escludere i dispositivi Microsoft Managed Desktop. Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). I **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad è un gruppo dinamico creato quando ci si iscrive in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.


### <a name="windows-apps"></a>App di Windows

Esaminare le app desiderate dagli utenti di Microsoft Managed Desktop.

**Consulenza**

È consigliabile preparare un inventario delle app che si desidera vengano convogliate dagli utenti di Microsoft Desktop gestiti. Verificare che le app possano essere distribuite da Intune. Per ulteriori informazioni, vedere [app in Microsoft Managed Desktop](apps.md).

È possibile richiedere al rappresentante dell'account Microsoft una query in Microsoft endpoint Configuration Manager per identificare le applicazioni che sono pronte per la migrazione a Intune o che devono essere rettificate.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop richiede l'abilitazione di Windows Hello for business.

**Non pronto**

Windows Hello for business è disabilitato. Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Consulenza**

Windows Hello for business non è configurato. Abilitarlo attenendosi alla procedura descritta in [creare un criterio di Windows Hello for business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Anelli di aggiornamento di Windows 10

Il criterio "Windows 10 Update Ring" in Intune non deve essere indirizzato a qualsiasi dispositivo Microsoft Managed Desktop.

**Non pronto**

Si dispone di un criterio "anello di aggiornamento" che consente di indirizzare tutti i dispositivi, tutti gli utenti o entrambi. Modificare il criterio per l'utilizzo di un'assegnazione che è destinata a un gruppo di Azure AD specifico che non include alcun dispositivo desktop Microsoft gestito. Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

**Consulenza**

Verificare che tutti i criteri anello di aggiornamento siano esclusi dai **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad. Se è stato assegnato un gruppo di utenti di Azure AD a questi criteri, verificare che i criteri di aggiornamento siano stati esclusi anche dalla **moderna area di lavoro: tutti** i gruppi di Azure ad che includono gli utenti di Microsoft Managed Desktop. Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Sia i **dispositivi di lavoro moderni-tutti** che quelli **moderni-tutti** i gruppi di Azure ad sono assegnati ai gruppi creati quando si effettua la registrazione in Microsoft Managed Desktop, quindi sarà necessario tornare a escludere questo gruppo dopo la registrazione.


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory


### <a name="ad-hoc-subscriptions"></a>Abbonamenti ad hoc

Si consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento del roaming dello stato dell'organizzazione.

**Consulenza**

Verificare che **AllowAdHocSubscriptions** sia impostato su **true**. In caso contrario, il roaming dello stato dell'organizzazione potrebbe non funzionare. Per ulteriori informazioni, vedere [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Il roaming dello stato dell'organizzazione deve essere abilitato.

**Consulenza**

Verificare che il roaming dello stato dell'organizzazione sia abilitato per tutti o per **i** gruppi **selezionati** . Per ulteriori informazioni, vedere [Enable Enterprise state roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licenze

Per utilizzare Microsoft Managed Desktop è necessario disporre di un numero di licenze.

**Non pronto**

Non si dispone di tutte le licenze necessarie per l'utilizzo di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md) e [altro sulle licenze](prerequisites.md#more-about-licenses).


### <a name="security-account-names"></a>Nomi degli account di sicurezza

Alcuni nomi degli account di sicurezza potrebbero essere in conflitto con quelli creati da Microsoft Managed Desktop.

**Non pronto**

Si dispone di almeno un nome di account che sarà in conflitto con quelli creati da Microsoft Managed Desktop. Collaborare con il rappresentante dell'account Microsoft per escludere i nomi degli account.


### <a name="security-administrator-roles"></a>Ruoli di amministratore della sicurezza

Gli utenti con determinati ruoli di sicurezza devono avere quelli assegnati in Microsoft Defender per endpoint.

**Consulenza**

Se si dispone di uno di questi ruoli assegnati nell'organizzazione di Azure AD, assicurarsi che dispongano anche di questi ruoli assegnati in Microsoft Defender per endpoint. In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.

- Ruolo con autorizzazioni di lettura per la sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali

Per ulteriori informazioni, vedere [creare e gestire i ruoli per il controllo di accesso basato sui ruoli](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Impostazione predefinita per la sicurezza

Le impostazioni predefinite per la sicurezza in Azure Active Directory impediscono la gestione dei dispositivi da parte di Microsoft Managed Desktop.

**Non pronto**

Sono state attivate le impostazioni predefinite per la sicurezza. Disattivare le impostazioni predefinite per la sicurezza e configurare i criteri di accesso condizionale. Per ulteriori informazioni, vedere [criteri comuni di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Reimpostazione della password in modalità self-service

La reimpostazione della password self-service (SSPR) deve essere abilitata per tutti gli utenti che escludono gli account di servizio Microsoft Managed Desktop. Per ulteriori informazioni, vedere [esercitazione: consentire agli utenti di sbloccare l'account o reimpostare le password tramite la reimpostazione della password self-service di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Consulenza**

Verificare che l'impostazione SSPR **Selected** includa i dispositivi Microsoft Managed Desktop ma escluda gli account di servizio di Microsoft Managed Desktop. Gli account di servizio di Microsoft Managed Desktop non possono funzionare come previsto quando SSPR è abilitato.  


### <a name="standard-user-role"></a>Ruolo utente standard

A parte gli utenti a cui sono stati assegnati i ruoli di Azure AD di amministratore globale e amministratore di dispositivi, gli utenti di Microsoft Managed Desktop saranno utenti standard senza privilegi di amministratore locale. A tutti gli altri utenti verrà assegnato un ruolo utente standard quando avviano il dispositivo Microsoft Managed Desktop.

**Consulenza**

Gli utenti di Microsoft Managed Desktop non disporranno dei privilegi di amministratore locale nei dispositivi desktop Microsoft gestiti dopo la registrazione.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive-for-business"></a>OneDrive for Business

L'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** sarà in conflitto con Microsoft Managed Desktop.

**Consulenza**

Si sta utilizzando l'impostazione **Consenti sincronizzazione solo sui PC aggiunti a domini specifici** . Questa impostazione non funzionerà con Microsoft Managed Desktop. Disabilitare questa impostazione e configurare OneDrive for business per l'utilizzo di un criterio di accesso condizionale. Per informazioni, vedere [pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .

