---
title: Risolvere problemi trovati dallo strumento di valutazione dell'idoneità
description: Azioni dettagliate da eseguire per ogni problema rilevato da uno strumento
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ff2ef15f93cef5255e8c8113facf51b833eff77d
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122361"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Risolvere problemi trovati dallo strumento di valutazione dell'idoneità

Per ogni controllo, lo strumento segnala uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è richiesta alcuna azione prima di completare la registrazione.        |
|Avviso    | Seguire i passaggi nello strumento o in questo articolo per un'esperienza ottimale con la registrazione e per gli utenti. È *possibile* completare la registrazione, ma è necessario risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito negativo se questi problemi non vengono risolti.* Seguire i passaggi descritti nello strumento o in questo articolo per risolverli.        |
|Error | Il ruolo di Azure Active Directory (AD) in uso non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

> [!NOTE]
> I risultati riportati da questo strumento riflettono lo stato delle impostazioni solo nel momento in cui è stato eseguito. Se successivamente si apportano modifiche ai criteri in Microsoft Intune, Azure Active Directory o Microsoft 365, gli elementi "Pronto" possono diventare "Non pronti". Per evitare problemi con le operazioni di Microsoft Managed Desktop, controllare le impostazioni specifiche descritte in questo articolo prima di modificare i criteri.

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

È possibile accedere alle impostazioni di Intune nell'interfaccia di amministrazione di Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Profilo di distribuzione Autopilot

Non dovresti avere profili Autopilot esistenti per gruppi assegnati o dinamici con dispositivi Microsoft Managed Desktop. Microsoft Managed Desktop usa Autopilot per effettuare il provisioning di nuovi dispositivi.

**Non pronto**

Hai un profilo Autopilot assegnato a tutti i dispositivi. Per la procedura, vedi [Registrare i dispositivi Windows in Intune usando Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Dopo la registrazione di Microsoft Managed Desktop, imposta i criteri di Autopilot per escludere il gruppo **Modern Workplace Devices -All** Azure AD.

**Avviso**

Assicurati che i profili Autopilot siano assegnati a un gruppo azure AD assegnato o dinamico che non include i dispositivi Microsoft Managed Desktop. Per la procedura, vedi [Registrare i dispositivi Windows in Intune usando Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Dopo la registrazione di Microsoft Managed Desktop, imposta i profili Autopilot in modo da escludere il gruppo **Modern Workplace Devices -All** Azure AD.


### <a name="certificate-connectors"></a>Connettori di certificati

Se sono presenti connettori di certificato che verranno utilizzati dai dispositivi che si desidera registrare in Microsoft Managed Desktop, i connettori non dovrebbero contenere errori. Solo uno dei seguenti avvisi verrà applicato alla propria situazione, quindi controllali con attenzione.

**Avviso**

Nessun connettore di certificati presente. È possibile che non siano necessari connettori, ma è consigliabile valutare se potrebbero essere necessari alcuni connettori per la connettività di rete nei dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)

**Avviso**

Almeno un connettore di certificati presenta un errore. Se è necessario questo connettore per fornire certificati ai dispositivi Microsoft Managed Desktop, è necessario risolvere l'errore. Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)


**Avviso**

Si dispone di almeno un connettore di certificati e non vengono segnalati errori. Tuttavia, in preparazione della distribuzione, potrebbe essere necessario creare un profilo per riutilizzare il connettore per i dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale non devono impedire a Microsoft Managed Desktop di gestire l'organizzazione di Azure AD (tenant) in Intune e Azure AD.

**Non pronto**

Si dispone di almeno un criterio di accesso condizionale destinato a tutti gli utenti. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a questi account. Dopo la registrazione, puoi esaminare i criteri di accesso condizionale di Microsoft Managed Desktop in Microsoft Endpoint Manager. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Avviso**

Si dispone di criteri di accesso condizionale che potrebbero impedire a Microsoft Managed Desktop di gestire il servizio Microsoft Managed Desktop. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a questi account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Per eseguire questo controllo, avrai anche bisogno di uno di questi ruoli di Azure AD:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore accesso condizionale
- Ruolo con autorizzazioni di lettura globali
- Amministratore dei dispositivi


### <a name="device-compliance-policies"></a>Criteri di conformità dei dispositivi

I criteri di conformità dei dispositivi Intune nell'organizzazione di Azure AD potrebbero influire sui dispositivi Microsoft Managed Desktop.

**Non pronto**

Si dispone di almeno un criterio di conformità destinato a tutti gli utenti. Microsoft Managed Desktop include criteri di conformità che verranno applicati ai dispositivi Microsoft Managed Desktop.  Modificare il criterio in modo che sia di destinazione di un gruppo di Azure AD specifico che non include utenti o dispositivi Microsoft Managed Desktop. Per la procedura, vedere [Creare un criterio di conformità in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Avviso**

Assicurarsi che i criteri di conformità di cui si dispone non siano specifici per gli utenti di Microsoft Managed Desktop. Per la procedura, vedere [Creare un criterio di conformità in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Profili di configurazione dei dispositivi

I profili di configurazione dei dispositivi Intune nell'organizzazione di Azure AD non devono essere di destinazione di dispositivi o utenti Microsoft Manage Desktop.

**Non pronto**

Si dispone di almeno un profilo di configurazione destinato a tutti gli utenti, a tutti i dispositivi o a entrambi. Reimpostare il profilo in modo che sia di destinazione di un gruppo di Azure AD specifico che non include alcun dispositivo Microsoft Managed Desktop. Per la procedura, vedere [Creare un profilo con impostazioni personalizzate in Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

**Avviso**

Assicurarsi che i criteri di configurazione di cui si dispone non includano utenti o dispositivi Microsoft Managed Desktop. Per la procedura, vedere [Creare un profilo con impostazioni personalizzate in Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Restrizioni relative al tipo di dispositivo

I dispositivi Microsoft Managed Desktop devono essere autorizzati a registrarsi in Intune.

**Non pronto**

Attualmente hai almeno un criterio di restrizione della registrazione configurato per impedire la registrazione dei dispositivi Windows in Intune. Segui i passaggi descritti in [Impostare](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) le restrizioni di registrazione per ogni criterio di restrizione di registrazione destinato agli utenti di Microsoft Managed Desktop e modifica l'impostazione di **Windows (MDM)** su **Consenti.** Tuttavia, puoi impostare qualsiasi **dispositivo** Windows di proprietà personale **(MDM)** su **Blocca.** 


### <a name="enrollment-status-page"></a>Pagina Stato registrazione

Al momento la pagina di stato della registrazione (ESP) è abilitata. Se si intende partecipare all'anteprima pubblica di Microsoft Managed Desktop di questa funzionalità, è possibile ignorare questo elemento. Per ulteriori informazioni, vedere [First-run experience with Autopilot and the Enrollment Status Page.](../get-started/esp-first-run.md)

**Non pronto**

Il profilo predefinito ESP è impostato su Mostra **stato configurazione app e profili.** Disabilita questa impostazione o assicurati che le assegnazioni a qualsiasi gruppo di Azure AD non includano i dispositivi Microsoft Managed Desktop seguendo i passaggi descritti in [Configurare la pagina stato registrazione.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Avviso**

Assicurati che tutti i profili con l'impostazione Mostra stato di avanzamento configurazione **app** e profili non siano assegnati ad alcun gruppo di Azure AD che includa dispositivi Microsoft Managed Desktop. Per altre informazioni, vedi [Configurare la pagina stato registrazione.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Microsoft Store per le aziende viene utilizzato e viene distribuita l'app Portale aziendale in Microsoft Managed Desktop per consentire agli utenti di installare facoltativamente alcune app, ad esempio Microsoft Project e Microsoft Visio (se consentito).

**Non pronto**

Microsoft Store per le aziende non è abilitato o non è sincronizzato con Intune. Per altre informazioni, vedi Come gestire le app acquistate in volumi diversi da [Microsoft Store per](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) le aziende con Microsoft Intune e Installare il portale aziendale di Intune nei [dispositivi.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Autenticazione a più fattori

L'autenticazione a più fattori non deve impedire a Microsoft Managed Desktop di gestire l'organizzazione Azure AD (tenant) in Intune e Azure AD.


**Non pronto**

Alcuni criteri di autenticazione a più fattori sono impostati come **necessario** per i criteri di accesso condizionale assegnati a tutti gli utenti. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a questi account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Avviso**

L'autenticazione a più fattori è necessaria nei criteri di accesso condizionale che potrebbero impedire a Microsoft Managed Desktop di gestire il servizio Microsoft Managed Desktop. Durante la registrazione, verranno esclusi gli account del servizio Microsoft Managed Desktop dai criteri di accesso condizionale pertinenti e verranno applicati nuovi criteri di accesso condizionale per limitare l'accesso a questi account. Per ulteriori informazioni su questi account di servizio, vedere [Procedure operative standard.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Errore**

Il ruolo amministratore di Intune non dispone di autorizzazioni sufficienti per questo controllo. Per eseguire questo controllo, avrai anche bisogno di uno di questi ruoli di Azure AD:

- Ruolo con autorizzazioni di lettura per la sicurezza
- Amministratore della sicurezza
- Amministratore accesso condizionale
- Ruolo con autorizzazioni di lettura globali
- Amministratore dei dispositivi


### <a name="powershell-scripts"></a>Script di PowerShell

Windows PowerShell gli script non possono essere assegnati in modo che possano essere assegnati ai dispositivi Microsoft Managed Desktop.  

**Avviso**

Assicurarsi che gli Windows PowerShell script nell'organizzazione di Azure AD non siano mirati ad alcun utente o dispositivo Microsoft Manage Desktop. Non assegnare uno script di PowerShell per tutti gli utenti, tutti i dispositivi o entrambi. Modifica i criteri per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include alcun utente o dispositivo Microsoft Managed Desktop. Per altre informazioni, vedi [Usare gli script di PowerShell nei dispositivi Windows 10 in Intune.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Area geografica

L'area geografica deve essere supportata da Microsoft Managed Desktop.

**Non pronto**

L'area dell'organizzazione di Azure AD non è attualmente supportata da Microsoft Managed Desktop. Per ulteriori informazioni, vedere Lingue e aree geografiche [supportate da Microsoft Managed Desktop.](../service-description/regions-languages.md)

**Avviso**

Uno o più paesi in cui si trova l'organizzazione di Azure AD non sono supportati da Microsoft Managed Desktop. Per ulteriori informazioni, vedere Lingue e aree geografiche [supportate da Microsoft Managed Desktop.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Linee di base della sicurezza

I criteri di base della sicurezza non devono essere mirati ad alcun dispositivo Microsoft Managed Desktop.

**Non pronto**

Si dispone di un profilo di base della sicurezza destinato a tutti gli utenti, a tutti i dispositivi o a entrambi. Modifica i criteri per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include alcun dispositivo Microsoft Managed Desktop. Per la procedura, vedere [Usare le linee di base della sicurezza per configurare i dispositivi Windows 10 in Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante la registrazione, applicheremo una nuova linea di base per la sicurezza a tutti i dispositivi Microsoft Managed Desktop. Dopo la registrazione, puoi esaminare i criteri di base per la sicurezza di Microsoft Managed Desktop nell'area dei criteri **di** configurazione di Microsoft Endpoint Manager.

**Avviso**

Assicurarsi che tutti i criteri di base della sicurezza di cui si dispone escludono i dispositivi Microsoft Managed Desktop. Per la procedura, vedere [Usare le linee di base della sicurezza per configurare i dispositivi Windows 10 in Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante la registrazione, applicheremo una nuova linea di base per la sicurezza a tutti i dispositivi Microsoft Managed Desktop. Dispositivi **di lavoro moderni-** Tutti i gruppi di Azure AD sono un gruppo dinamico che creiamo quando ti iscrivi a Microsoft Managed Desktop, quindi dovrai tornare indietro per escludere questo gruppo dopo la registrazione. 


### <a name="windows-apps"></a>App di Windows

Esaminare le app che si desidera che gli utenti di Microsoft Managed Desktop diseervino.

**Avviso**

È consigliabile preparare un inventario delle app che devono essere disponibili per gli utenti di Microsoft Managed Desktop. Poiché queste app devono essere distribuite da Intune, valutare il riutilizzo delle app Intune esistenti. Prendi in considerazione l'uso del portale aziendale (vedi Installare il portale [aziendale intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) nei dispositivi e la pagina dello stato di registrazione (ESP) per distribuire le app agli utenti. Per altre informazioni, vedi [App in Microsoft Managed Desktop](apps.md) e [First-run experience con Autopilot e la pagina Stato registrazione.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)

Puoi chiedere al rappresentante dell'account Microsoft una query in Microsoft Endpoint Configuration Manager per identificare le app pronte per la migrazione a Intune o che devono essere rettificate.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop richiede che Windows Hello for Business sia abilitato.

**Non pronto**

Windows Hello for Business è disabilitato. Abilitarlo seguendo la procedura descritta in [Creare un criterio di Windows Hello for Business](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Avviso**

Windows Hello for Business non è configurato. Abilitalo seguendo la procedura descritta in [Creare un criterio di Windows Hello for Business.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Anelli di aggiornamento di Windows 10

Il criterio "Anello di aggiornamento di Windows 10" in Intune non deve essere mirato ad alcun dispositivo Microsoft Managed Desktop.

**Non pronto**

Si dispone di un criterio "anello di aggiornamento" destinato a tutti i dispositivi, a tutti gli utenti o a entrambi. Modifica i criteri per usare un'assegnazione destinata a un gruppo di Azure AD specifico che non include alcun dispositivo Microsoft Managed Desktop. Per la procedura, vedere Gestire gli aggiornamenti software di [Windows 10 in Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**Avviso**

Assicurati che tutti i criteri dell'anello di aggiornamento che hai escluso siano il **gruppo Modern Workplace Devices -All** Azure AD. Se sono stati assegnati gruppi di utenti di Azure AD a questi criteri, assicurarsi che tutti i criteri dell'anello di aggiornamento siano stati esclusi anche dal gruppo Ambiente di lavoro moderno **-** Tutti i gruppi di Azure AD a cui si aggiungono gli utenti di Microsoft Managed Desktop (o un gruppo equivalente). Per la procedura, vedere Gestire gli aggiornamenti software di [Windows 10 in Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) Sia i dispositivi moderni dell'area di **lavoro-** Tutti i gruppi di **Azure** AD sono gruppi che creiamo quando ti iscrivi a Microsoft Managed Desktop, quindi dovrai tornare indietro per escludere questo gruppo dopo la registrazione.


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

È possibile accedere alle impostazioni di Azure Active Directory nel [portale di Azure.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Registrazione intune

I dispositivi Windows 10 nell'organizzazione azure AD devono essere in grado di registrare automaticamente in Intune.

**Avviso**

Assicurati che **l'ambito utente MDM** sia impostato su **Alcuni** o **Tutti** e non **su Nessuno.** Se scegli **Some,** torna dopo la registrazione e seleziona il  gruppo **Modern Workplace -All** Azure AD per i gruppi o un gruppo equivalente per tutti gli utenti di Microsoft Managed Desktop.  Vedi [Configurare la registrazione per i dispositivi Windows con Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Sottoscrizioni ad hoc

Consiglia come controllare un'impostazione che (se impostata su "false") potrebbe impedire il corretto funzionamento di Enterprise State Roaming.

**Avviso**

Verificare che **AllowAdHocSubscriptions** sia impostato su **True.** In caso contrario, Enterprise State Roaming potrebbe non funzionare. Per ulteriori informazioni, vedere [Set-MsolCompanySettings.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming deve essere abilitato.

**Avviso**

Assicurati che Enterprise State Roaming sia abilitato per **Tutti o** per **i gruppi** selezionati. Per ulteriori informazioni, vedere [Abilitare Enterprise State Roaming in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenze

Per usare Microsoft Managed Desktop sono necessarie diverse licenze.

**Non pronto**

Non hai tutte le licenze necessarie per usare Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Tecnologie Microsoft Managed Desktop](../intro/technologies.md) e Altre informazioni sulle [licenze.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Account del servizio Microsoft Managed Desktop

Alcuni nomi di account potrebbero essere in conflitto con i nomi di account creati da Microsoft Managed Desktop per gestire il servizio Microsoft Managed Desktop.

**Non pronto**

Si dispone di almeno un nome di account in conflitto con i nomi di account creati da Microsoft Managed Desktop. Collaborare con il rappresentante dell'account Microsoft per escludere questi nomi di account. I nomi degli account non vengono elencati pubblicamente per ridurre al minimo i rischi per la sicurezza. 


### <a name="security-administrator-roles"></a>Ruoli di amministratore della sicurezza

Gli utenti con determinati ruoli di sicurezza devono disporre di tali ruoli assegnati in Microsoft Defender per Endpoint.

**Avviso**

Se sono presenti utenti assegnati a uno di questi ruoli nell'organizzazione di Azure AD, assicurarsi che questi ruoli siano assegnati anche in Microsoft Defender for Endpoint. In caso contrario, gli amministratori con questi ruoli non saranno in grado di accedere al portale di amministrazione.

- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali

Per ulteriori informazioni, vedere [Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Impostazione predefinita sicurezza

Le impostazioni predefinite di sicurezza in Azure Active Directory impediranno a Microsoft Managed Desktop di gestire i dispositivi.

**Non pronto**

Le impostazioni predefinite di sicurezza sono attivate. Disattiva le impostazioni predefinite di sicurezza e configura i criteri di accesso condizionale. Per ulteriori informazioni, vedere [Criteri di accesso condizionale comuni.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Reimpostazione password self-service

La reimpostazione della password in modalità self-service (SSPR) può essere abilitata per tutti gli utenti di Microsoft Managed Desktop esclusi gli account del servizio Microsoft Managed Desktop. Per altre informazioni, vedere Esercitazione: Consentire agli utenti di sbloccare il proprio account o reimpostare le [password usando la reimpostazione della password in modalità self-service di Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)

**Avviso**

Verificare che l'impostazione SSPR **Selezionata** includa gli utenti di Microsoft Managed Desktop, ma esclude gli account del servizio Microsoft Managed Desktop. Gli account del servizio Microsoft Managed Desktop non possono funzionare come previsto quando la RSPR è abilitata.  


### <a name="standard-user-role"></a>Ruolo utente standard

Oltre agli utenti a cui sono assegnati i ruoli di amministratore globale e amministratore dei dispositivi di Azure AD, gli utenti di Microsoft Managed Desktop saranno utenti standard senza privilegi di amministratore locale. A tutti gli altri utenti verrà assegnato un ruolo utente standard quando avviano il dispositivo Microsoft Managed Desktop.

**Avviso**

Dopo la registrazione, gli utenti di Microsoft Managed Desktop non avranno privilegi di amministratore locale nei propri dispositivi Microsoft Managed Desktop.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

**L'impostazione Consenti sincronizzazione solo su PC aggiunti a** domini specifici sarà in conflitto con Microsoft Managed Desktop. È possibile accedere alle impostazioni di OneDrive nell'interfaccia di amministrazione [di OneDrive.](https://admin.onedrive.com)

**Avviso**

Si usa l'impostazione **Consenti sincronizzazione solo su PC aggiunti a domini** specifici. Questa impostazione non funziona con Microsoft Managed Desktop. Disabilitare questa impostazione e configurare Invece OneDrive per l'uso di un criterio di accesso condizionale. Per [informazioni, vedere Pianificare una distribuzione di accesso](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) condizionale.
