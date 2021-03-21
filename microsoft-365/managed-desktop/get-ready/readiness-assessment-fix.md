---
title: Risolvere problemi trovati dallo strumento di valutazione dell'idoneità
description: Azioni dettagliate da eseguire per ogni problema rilevato da uno strumento
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925917"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Risolvere problemi trovati dallo strumento di valutazione dell'idoneità

Per ogni controllo, lo strumento segnala uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Prima di completare la registrazione non è necessaria alcuna azione.        |
|Avviso    | Seguire i passaggi nello strumento o in questo articolo per un'esperienza ottimale con la registrazione e per gli utenti. Puoi *completare* la registrazione, ma devi risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito negativo se questi problemi non vengono risolti.* Seguire i passaggi nello strumento o in questo articolo per risolverli.        |
|Errore | Il ruolo di Azure Active Directory (AD) in uso non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

> [!NOTE]
> I risultati riportati da questo strumento riflettono lo stato delle impostazioni solo nel momento in cui è stato eseguito. Se successivamente si apportano modifiche ai criteri in Microsoft Intune, Azure Active Directory o Microsoft 365, gli elementi che erano "Pronti" possono diventare "Non pronti". Per evitare problemi con le operazioni di Microsoft Managed Desktop, controllare le impostazioni specifiche descritte in questo articolo prima di modificare i criteri.

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

È possibile accedere alle impostazioni di Intune nell'interfaccia di amministrazione di Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Profilo di distribuzione Autopilot

Non dovresti avere profili Autopilot esistenti che hanno come destinazione gruppi assegnati o dinamici con i dispositivi Microsoft Managed Desktop. Microsoft Managed Desktop usa Autopilot per effettuare il provisioning di nuovi dispositivi.

**Non pronto**

Hai un profilo Autopilot assegnato a tutti i dispositivi. Per la procedura, vedi [Registrare i dispositivi Windows in Intune usando Windows Autopilot.](/mem/autopilot/enrollment-autopilot) Dopo la registrazione di Microsoft Managed Desktop, imposta il criterio Autopilot per escludere il **gruppo Modern Workplace Devices -All** Azure AD.

**Avviso**

Assicurati che i profili Autopilot siano assegnati a un gruppo di Azure AD assegnato o dinamico che non include i dispositivi Microsoft Managed Desktop. Per la procedura, vedi [Registrare i dispositivi Windows in Intune usando Windows Autopilot.](/mem/autopilot/enrollment-autopilot) Dopo la registrazione di Microsoft Managed Desktop, imposta i profili Autopilot in modo da escludere il **gruppo Modern Workplace Devices -All** Azure AD.


### <a name="certificate-connectors"></a>Connettori di certificato

Se si dispone di connettori di certificato che verranno utilizzati dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non dovrebbero avere errori. Solo uno dei seguenti avvisi verrà applicato alla situazione, quindi controllali con attenzione.

**Avviso**

Nessun connettore di certificato presente. È possibile che non siano necessari connettori, ma è consigliabile valutare se potrebbe essere necessario un po' per la connettività di rete nei dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)

**Avviso**

Almeno un connettore di certificato ha un errore. Se è necessario questo connettore per fornire certificati ai dispositivi Desktop gestito Microsoft, è necessario risolvere l'errore. Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)


**Avviso**

Si dispone di almeno un connettore di certificato e non vengono segnalati errori. Tuttavia, in preparazione della distribuzione, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Desktop gestito Microsoft. Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale non devono impedire a Microsoft Managed Desktop di gestire l'organizzazione di Azure AD (tenant) in Intune e Azure AD.

**Non pronto**

Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a tali account. Dopo la registrazione, è possibile esaminare i criteri di accesso condizionale di Microsoft Managed Desktop in Microsoft Endpoint Manager. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Avviso**

Si dispone di criteri di accesso condizionale che potrebbero impedire a Microsoft Managed Desktop di gestire il servizio Microsoft Managed Desktop. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a tali account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Per eseguire questo controllo, dovrai anche assegnare uno di questi ruoli di Azure AD:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore accesso condizionale
- Lettore globale
- Amministratore dispositivi


### <a name="device-compliance-policies"></a>Criteri di conformità dei dispositivi

I criteri di conformità dei dispositivi intune nell'organizzazione di Azure AD potrebbero influire sui dispositivi Desktop gestito Microsoft.

**Non pronto**

Si dispone di almeno un criterio di conformità destinato a tutti gli utenti. Microsoft Managed Desktop include criteri di conformità che verranno applicati ai dispositivi Microsoft Managed Desktop.  Modificare il criterio per impostare come destinazione un gruppo di Azure AD specifico che non include utenti o dispositivi Microsoft Managed Desktop. Per la procedura, vedere [Creare criteri di conformità in Microsoft Intune.](/mem/intune/protect/create-compliance-policy)

**Avviso**

Assicurarsi che i criteri di conformità non siano di destinazione per gli utenti di Microsoft Managed Desktop. Per la procedura, vedere [Creare criteri di conformità in Microsoft Intune.](/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Profili di configurazione dei dispositivi

I profili di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere di destinazione di alcun utente o dispositivo Microsoft Manage Desktop.

**Non pronto**

Hai almeno un profilo di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi. Reimpostare il profilo in modo che sia di destinazione di un gruppo di Azure AD specifico che non include dispositivi Desktop gestito Microsoft. Per la procedura, vedere [Creare un profilo con impostazioni personalizzate in Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)

**Avviso**

Assicurati che tutti i criteri di configurazione che hai non includano dispositivi o utenti Microsoft Managed Desktop. Per la procedura, vedere [Creare un profilo con impostazioni personalizzate in Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Restrizioni relative al tipo di dispositivo

I dispositivi Microsoft Managed Desktop devono essere autorizzati a registrarsi in Intune.

**Non pronto**

Al momento hai almeno un criterio di restrizione di registrazione configurato per impedire la registrazione dei dispositivi Windows in Intune. Seguire i passaggi descritti in Impostare restrizioni [di](/mem/intune/enrollment/enrollment-restrictions-set) registrazione per ogni criterio di restrizione di registrazione destinato agli utenti di Microsoft Managed Desktop e modificare l'impostazione **di Windows (MDM)** su **Consenti**. Puoi, tuttavia, impostare qualsiasi **dispositivo** **Windows (MDM)** di proprietà personale su **Blocca**. 


### <a name="enrollment-status-page"></a>Pagina Stato registrazione

Al momento la pagina esp (Enrollment Status Page) è abilitata. Se si intende partecipare all'anteprima pubblica di Microsoft Managed Desktop di questa funzionalità, è possibile ignorare questo elemento. Per ulteriori informazioni, vedere [First-run experience with Autopilot and the Enrollment Status Page.](../get-started/esp-first-run.md)

**Non pronto**

Il profilo predefinito ESP è impostato su Mostra stato **configurazione app e profilo**. Disabilitare questa impostazione o assicurarsi che le assegnazioni a qualsiasi gruppo di Azure AD non includano i dispositivi Microsoft Managed Desktop seguendo la procedura descritta in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

**Avviso**

Assicurati che tutti i profili con **l'impostazione** Mostra stato di avanzamento configurazione app e profili non siano assegnati ad alcun gruppo di Azure AD che include dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

### <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Usiamo Microsoft Store per le aziende e distribuiamo l'app Portale aziendale su Microsoft Managed Desktop per consentire agli utenti di installare facoltativamente alcune app, ad esempio Microsoft Project e Microsoft Visio (se consentito).

**Non pronto**

Microsoft Store per le aziende non è abilitato o non è sincronizzato con Intune. Per altre informazioni, vedi Come gestire le app acquistate in volume da [Microsoft Store per le aziende](/mem/intune/apps/windows-store-for-business) con Microsoft Intune e Installare il portale aziendale di Intune nei [dispositivi.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Autenticazione a più fattori

L'autenticazione a più fattori non deve impedire a Microsoft Managed Desktop di gestire l'organizzazione di Azure AD (tenant) in Intune e Azure AD.


**Non pronto**

Alcuni criteri di autenticazione a più fattori sono impostati come **obbligatori per** i criteri di accesso condizionale assegnati a tutti gli utenti. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a tali account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Avviso**

Nei criteri di accesso condizionale è necessaria l'autenticazione a più fattori che potrebbe impedire a Microsoft Managed Desktop di gestire il servizio Microsoft Managed Desktop. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a tali account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Per eseguire questo controllo, dovrai anche assegnare uno di questi ruoli di Azure AD:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore accesso condizionale
- Lettore globale
- Amministratore dispositivi


### <a name="powershell-scripts"></a>Script di PowerShell

Windows PowerShell gli script non possono essere assegnati in modo che possano essere assegnati ai dispositivi Desktop gestito Microsoft.  

**Avviso**

Assicurati che gli Windows PowerShell nell'organizzazione di Azure AD non siano mirati ad alcun utente o dispositivo Microsoft Manage Desktop. Non assegnare uno script di PowerShell per tutti gli utenti, tutti i dispositivi o entrambi. Modificare il criterio per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include dispositivi o utenti Microsoft Managed Desktop. Per altre informazioni, vedi [Usare script di PowerShell nei dispositivi Windows 10 in Intune.](/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Area geografica

L'area geografica deve essere supportata da Microsoft Managed Desktop.

**Non pronto**

L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop. Per ulteriori informazioni, vedere Lingue e [aree geografiche supportate da Microsoft Managed Desktop.](../service-description/regions-languages.md)

**Avviso**

Uno o più paesi in cui si trova l'organizzazione di Azure AD non sono supportati da Microsoft Managed Desktop. Per ulteriori informazioni, vedere Lingue e [aree geografiche supportate da Microsoft Managed Desktop.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Linee di base della sicurezza

I criteri di base della sicurezza non devono essere mirati ad alcun dispositivo Microsoft Managed Desktop.

**Non pronto**

Si dispone di un profilo di base di sicurezza destinato a tutti gli utenti, a tutti i dispositivi o a entrambi. Modificare il criterio per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include dispositivi Microsoft Managed Desktop. Per la procedura, vedi [Usare le linee di base della sicurezza per configurare i dispositivi Windows 10 in Intune.](/mem/intune/protect/security-baselines) Durante la registrazione, applicheremo una nuova linea di base per la sicurezza a tutti i dispositivi Microsoft Managed Desktop. Dopo la registrazione, è possibile esaminare i criteri di base per la sicurezza di Microsoft Managed Desktop nell'area **Criteri di** configurazione di Microsoft Endpoint Manager.

**Avviso**

Assicurati che tutti i criteri di base della sicurezza siano stati esclusi dai dispositivi Microsoft Managed Desktop. Per la procedura, vedi [Usare le linee di base della sicurezza per configurare i dispositivi Windows 10 in Intune.](/mem/intune/protect/security-baselines) Durante la registrazione, applicheremo una nuova linea di base per la sicurezza a tutti i dispositivi Microsoft Managed Desktop. Il **gruppo Modern Workplace Devices -All** Azure AD è un gruppo dinamico creato quando ti iscrivi a Microsoft Managed Desktop, quindi dovrai tornare per escludere questo gruppo dopo la registrazione. 


### <a name="windows-apps"></a>App di Windows

Esaminare le app che gli utenti di Microsoft Managed Desktop devono avere.

**Avviso**

È consigliabile preparare un inventario delle app che devono essere disponibili per gli utenti di Microsoft Managed Desktop. Poiché queste app devono essere distribuite da Intune, valutare il riutilizzo delle app intune esistenti. Prendere in considerazione l'uso del portale aziendale (vedere [Installare intune Portale](../get-started/company-portal.md) aziendale nei dispositivi e Pagina stato registrazione (ESP) per distribuire le app agli utenti. Per altre informazioni, vedi [App in Microsoft Managed Desktop](apps.md) e Esperienza di prima esecuzione con [Autopilot e pagina Stato registrazione.](../get-started/esp-first-run.md)

Puoi chiedere al rappresentante dell'account Microsoft una query in Microsoft Endpoint Configuration Manager per identificare le app che sono pronte per la migrazione a Intune o che necessitano di regolazioni.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop richiede che Windows Hello for Business sia abilitato.

**Non pronto**

Windows Hello for Business è disabilitato. Abilitarlo seguendo la procedura descritta in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Avviso**

Windows Hello for Business non è configurato. Abilitalo seguendo la procedura descritta in [Create a Windows Hello for Business policy.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Anelli di aggiornamento di Windows 10

Il criterio "Anello di aggiornamento di Windows 10" in Intune non deve essere mirato ad alcun dispositivo Microsoft Managed Desktop.

**Non pronto**

Hai un criterio "anello di aggiornamento" destinato a tutti i dispositivi, a tutti gli utenti o a entrambi. Modificare il criterio per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include dispositivi Desktop gestito Microsoft. Per la procedura, vedere Gestire gli aggiornamenti software di [Windows 10 in Intune.](/mem/intune/protect/windows-update-for-business-configure)

**Avviso**

Assicurati che tutti i criteri dell'anello di aggiornamento siano stati esclusi dal **gruppo Modern Workplace Devices -All** Azure AD. Se sono stati assegnati gruppi di utenti di Azure AD a questi criteri, assicurarsi che tutti i criteri dell'anello di aggiornamento siano stati esclusi anche dal gruppo Ambiente di lavoro moderno **-All** Azure AD a cui si aggiungono gli utenti di Microsoft Managed Desktop (o un gruppo equivalente). Per la procedura, vedere Gestire gli aggiornamenti software di [Windows 10 in Intune.](/mem/intune/protect/windows-update-for-business-configure) Entrambi i dispositivi workplace moderni **-All** e **Modern Workplace -Tutti** i gruppi di Azure AD sono gruppi che creiamo quando ti iscrivi a Microsoft Managed Desktop, quindi dovrai tornare per escludere questo gruppo dopo la registrazione.


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

È possibile accedere alle impostazioni di Azure Active Directory nel [portale di Azure.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Registrazione di Intune

I dispositivi Windows 10 nell'organizzazione di Azure AD devono essere in grado di eseguire automaticamente la registrazione in Intune.

**Avviso**

Assicurati che **l'ambito utente MDM** sia impostato su **Some** or **All** e non **su None.** Se si sceglie **Some**, tornare dopo la registrazione e selezionare il gruppo **Modern Workplace -All** Azure AD per **Groups** o un gruppo equivalente per tutti gli utenti di Microsoft Managed Desktop.  Vedi [Configurare la registrazione per i dispositivi Windows tramite Microsoft Intune.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Sottoscrizioni ad hoc

Consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento di Enterprise State Roaming.

**Avviso**

Verificare che **AllowAdHocSubscriptions** sia impostato su **True.** In caso contrario, Enterprise State Roaming potrebbe non funzionare. Per ulteriori informazioni, vedere [Set-MsolCompanySettings.](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming deve essere abilitato.

**Avviso**

Assicurati che Enterprise State Roaming sia abilitato per **Tutti o** per **i gruppi** selezionati. Per ulteriori informazioni, vedere [Enable Enterprise State Roaming in Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenze

Per utilizzare Microsoft Managed Desktop sono necessarie diverse licenze.

**Non pronto**

Non hai tutte le licenze necessarie per usare Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Tecnologie Desktop gestito Microsoft](../intro/technologies.md) e Altre informazioni sulle [licenze.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Account del servizio Microsoft Managed Desktop

Alcuni nomi di account potrebbero essere in conflitto con i nomi di account creati da Microsoft Managed Desktop per gestire il servizio Microsoft Managed Desktop.

**Non pronto**

Si dispone di almeno un nome di account che sarà in conflitto con i nomi di account creati da Microsoft Managed Desktop. Collaborare con il rappresentante dell'account Microsoft per escludere questi nomi di account. I nomi degli account non vengono elencati pubblicamente per ridurre al minimo i rischi per la sicurezza. 


### <a name="security-administrator-roles"></a>Ruoli di amministratore della sicurezza

Agli utenti con determinati ruoli di sicurezza devono essere assegnati tali ruoli in Microsoft Defender for Endpoint.

**Avviso**

Se hai utenti assegnati a uno di questi ruoli nell'organizzazione di Azure AD, assicurati che anche questi ruoli siano assegnati in Microsoft Defender for Endpoint. In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.

- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali

Per ulteriori informazioni, vedere [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Impostazione predefinita sicurezza

Le impostazioni predefinite di sicurezza in Azure Active Directory impediranno a Microsoft Managed Desktop di gestire i dispositivi.

**Non pronto**

Sono attivate le impostazioni predefinite di sicurezza. Disattivare Le impostazioni predefinite di sicurezza e configurare i criteri di accesso condizionale. Per ulteriori informazioni, vedere [Criteri di accesso condizionale comuni.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Reimpostazione password self-service

La reimpostazione della password self-service può essere abilitata per tutti gli utenti di Microsoft Managed Desktop esclusi gli account del servizio Microsoft Managed Desktop. Per ulteriori informazioni, vedere Esercitazione: Consentire agli utenti di sbloccare il proprio account o reimpostare le password utilizzando la reimpostazione della [password self-service](/azure/active-directory/authentication/tutorial-enable-sspr)di Azure Active Directory.

**Avviso**

Assicurati che l'impostazione SSPR **Selected** includa gli utenti di Microsoft Managed Desktop ma escludi gli account del servizio Microsoft Managed Desktop. Gli account del servizio Microsoft Managed Desktop non possono funzionare come previsto quando SSPR è abilitato.  


### <a name="standard-user-role"></a>Ruolo utente standard

Oltre agli utenti assegnati ad Azure AD ruoli di amministratore globale e amministratore del dispositivo, gli utenti di Microsoft Managed Desktop saranno utenti standard senza privilegi di amministratore locale. A tutti gli altri utenti verrà assegnato un ruolo utente standard quando avviano il dispositivo Desktop gestito Microsoft.

**Avviso**

Gli utenti di Microsoft Managed Desktop non avranno privilegi di amministratore locale nei propri dispositivi Microsoft Managed Desktop dopo la registrazione.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

**L'impostazione Consenti sincronizzazione solo su PC aggiunti a** domini specifici sarà in conflitto con Microsoft Managed Desktop. È possibile accedere alle impostazioni di OneDrive nell'interfaccia di amministrazione [di OneDrive.](https://admin.onedrive.com)

**Avviso**

Stai usando **l'impostazione Consenti sincronizzazione solo su PC aggiunti a domini** specifici. Questa impostazione non funziona con Microsoft Managed Desktop. Disabilitare questa impostazione e configurare Invece OneDrive per l'utilizzo di un criterio di accesso condizionale. Per [informazioni, vedere Plan a Conditional Access deployment.](/azure/active-directory/conditional-access/plan-conditional-access)